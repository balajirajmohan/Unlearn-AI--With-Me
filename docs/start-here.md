# Start here

There is no single correct entry point. Choose the route that matches the work you want to do, then use the roadmap to widen your coverage.

## I am completely new to AI

Start with:

1. [Context windows](foundations/context-windows.md) to practice the lesson format.
2. Weeks 1–4 in the [roadmap](roadmap.md) for foundations and direct model APIs.
3. The [glossary](glossary.md) as a reference, not as a memorization list.

Your first useful output is a short explanation in your own words, a small working example, and a list of limits you can observe.

## I am building AI applications

Start with:

1. The [first LLM API lab](labs/first-llm-api.md).
2. Weeks 5–16 for typed APIs, tools, state, RAG, citations, and evaluation.
3. Weeks 17–24 for agents and MCP once you can test the underlying application reliably.

Keep the scope small. A good first application has a clear input, a measurable output, a failure path, and tests that do not depend on a live model call.

## I am moving from DevOps or platform engineering

Start with:

1. Weeks 29–38 for GPU execution, inference, observability, and security.
2. Weeks 39–44 for Bedrock, SageMaker, KServe, and the platform boundary.
3. The capstone in weeks 45–48 to connect managed and self-hosted paths.

You can backfill application fundamentals as needed. Production AI still depends on clear contracts, evaluation, permissions, and useful telemetry.

## How to use each page

For every topic, write down five things:

- the assumption you had to unlearn
- the explanation you would give to another engineer
- the smallest build that demonstrates the idea
- the failure or adversarial case you tested
- the operating tradeoff you would document for production

If a page does not help you do one of those five things, it is probably too abstract or too broad.
