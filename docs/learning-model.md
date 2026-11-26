# The learning model

The site uses one structure for lessons, labs, and portfolio work:

## Unlearn

Name the misconception. Examples:

- “A context window is the model's permanent memory.”
- “More retrieved documents always make RAG better.”
- “An agent is just a chatbot with a larger prompt.”

The statement should be specific enough to test.

## Understand

Explain the mechanism in plain language. Define the vocabulary before using it. Prefer one small diagram or trace over a page of abstractions.

## Build

Implement the smallest version that makes the mechanism visible. Keep the inputs synthetic and the setup reproducible. A build can be a script, notebook, API, service, or deployment manifest.

## Break

Try the cases that make the model fail:

- missing or conflicting context
- token or memory limits
- malformed tool input
- retries and duplicate side effects
- permissions that are too broad
- latency, throughput, cost, or GPU-memory pressure

Record what failed, why it failed, and which signal would reveal the problem in production.

## Operate

Describe how the system should be run safely. Include tests, observability, privacy, secrets, access control, rollback, and a clear boundary for human approval.

## A lesson is complete when it leaves evidence

The public evidence for a topic should be compact:

| Evidence | What it proves |
| --- | --- |
| Explanation | You can describe the mechanism without copying the source wording. |
| Build | You can make the idea work in a constrained example. |
| Break test | You understand a meaningful failure mode. |
| Measurement | You can compare quality, latency, cost, throughput, or memory. |
| Operating note | You can place the idea in a secure production system. |

This is intentionally different from recording that a course was completed.
