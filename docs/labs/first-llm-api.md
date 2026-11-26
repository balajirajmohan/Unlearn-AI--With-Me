# First LLM API lab

This lab is about the application boundary around a model call. The provider can change. The contract, tests, retries, timeouts, and secret handling should remain understandable.

## Goal

Build a small command-line client that:

- accepts a user question
- sends a typed request to a model adapter
- returns structured JSON
- records latency and an estimated token or cost signal
- fails clearly when the provider is unavailable

## Suggested contract

```python
from dataclasses import dataclass


@dataclass
class ModelResult:
    answer: str
    input_units: int
    output_units: int
    latency_ms: float


class ModelClient:
    def complete(self, question: str) -> ModelResult:
        raise NotImplementedError
```

Implement the adapter for the provider you choose. Keep credentials in an environment variable or a secret manager. Do not commit keys, `.env` files, request logs, or customer data.

## Test before the live call

Use a fake client for unit tests. Test:

1. valid structured output
2. empty input
3. timeout and retry limits
4. malformed provider output
5. an unavailable provider

The test suite should run without network access. A live smoke test can be a separate, explicit command.

## Break it

Measure what changes when you:

- increase the prompt size
- request a longer answer
- force a timeout
- repeat the same request
- return invalid JSON from the fake provider

Write down the behavior you want users to see. “The model failed” is not an operating policy.

## Deliverable

Publish the client, fake provider, tests, a short latency and cost note, and a README that explains how to run the live smoke test without exposing a secret.
