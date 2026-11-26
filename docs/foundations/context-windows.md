# Context windows

## Unlearn

> “A context window is the model's permanent memory.”

It is not. A context window is the bounded amount of text and other input the model can attend to for one request. Durable memory, retrieval, application state, and model weights are different mechanisms.

## Understand

For each request, an application assembles an input such as:

```text
system instructions
+ conversation history
+ retrieved documents
+ tool results
+ the current user message
→ model input window
→ model response
```

The next request may include some of the earlier material again, but the model does not automatically retain every prior token. The application decides what to keep, summarize, retrieve, or discard.

Three limits matter:

| Limit | What it changes |
| --- | --- |
| Capacity | How much input and output can fit in one request. |
| Relevance | Whether the model can use the important material among the noise. |
| Cost and latency | How much work grows as more tokens are sent and processed. |

## Visual model

```text
┌──────────────┐   ┌──────────────────────┐   ┌─────────────────┐
│ App state    │──▶│ Context assembler    │──▶│ Model request   │
│ memory       │   │ history + retrieval │   │ bounded window  │
│ documents    │   │ tools + user input  │   │                 │
└──────────────┘   └──────────────────────┘   └────────┬────────┘
                                                       │
                                                       ▼
                                                response + telemetry
```

## Build

The following toy helper makes the budget visible. It counts characters instead of real tokens, so it is useful for reasoning about overflow, not for production billing.

```python
from dataclasses import dataclass


@dataclass
class ContextBudget:
    limit: int

    def assemble(self, *parts: str) -> str:
        context = "\n\n".join(part.strip() for part in parts if part.strip())
        if len(context) > self.limit:
            raise ValueError(
                f"context is {len(context)} characters; limit is {self.limit}"
            )
        return context


budget = ContextBudget(limit=120)
prompt = budget.assemble(
    "System: answer with evidence.",
    "Retrieved note: a context window is request-scoped input.",
    "User: explain the difference between context and memory.",
)
print(prompt)
```

## Break it

Try the helper with these cases:

1. Add a long irrelevant document. What fails first: capacity, relevance, or both?
2. Remove the retrieved note. Can the response still be grounded?
3. Add conflicting notes. What should the application do before asking the model?
4. Replace the toy character count with a real tokenizer. How does the estimate change?

The lesson is not that a larger context is bad. It is that context assembly is an application responsibility with measurable tradeoffs.

## Production reality

- Keep the system instruction and user data boundaries explicit.
- Retrieve only the material needed for the current task.
- Log token counts, latency, retrieval identifiers, and truncation decisions without logging sensitive content by default.
- Treat summaries as lossy transformations. Preserve the source when the decision is important.
- Set a failure path for overflow and insufficient evidence instead of silently dropping context.

## Lab

Build a context-budget wrapper around one small application. Add a test for overflow, a test for missing evidence, and a metric that records the number of characters or tokens selected for each request. Publish the wrapper and the failure cases together.

## Check your understanding

1. **Does a larger context window create durable memory?** No. It increases the amount of request-scoped input that can be processed.
2. **Who decides what enters the context?** Usually the application, through history management, retrieval, summarization, and tool-result handling.
3. **Why can irrelevant context hurt?** It competes with relevant evidence and can make the model's next-token prediction less focused.
4. **What should happen when evidence is missing?** The application should expose that condition and choose an explicit fallback, such as asking a clarifying question.
5. **What should be measured?** At minimum, selected input size, output size, latency, cost proxy, retrieval quality, and truncation or failure events.
