# 48-week roadmap

This roadmap is the public teaching sequence distilled from the private learning workbook. It covers development, model work, GPU engineering, inference, security, and platform operations.

## Phase map

| Weeks | Phase | Outcome |
| --- | --- | --- |
| 1–4 | Foundations | Explain AI systems, write typed Python, and call models directly. |
| 5–10 | AI application development | Ship a tested, stateful AI service. |
| 11–16 | RAG engineering | Build, evaluate, and secure a cited retrieval system. |
| 17–22 | Agents and LangGraph | Build durable workflows with tools, approvals, and tests. |
| 23–24 | MCP | Expose safe capabilities through authenticated MCP services. |
| 25–28 | Model development | Train, adapt, evaluate, and release a small open model. |
| 29–34 | GPU and inference | Profile workloads and serve models with measurable performance. |
| 35–38 | LLMOps and security | Trace, evaluate, threat-model, and operate AI systems. |
| 39–42 | Cloud production | Deploy managed-model and cloud-native workloads safely. |
| 43–44 | AI platform | Build a serving platform with quotas, secrets, and GPU visibility. |
| 45–48 | Capstone | Deliver a portfolio-ready Cloud Migration Copilot. |

## Portfolio milestones

| Target | Milestone | Evidence |
| --- | --- | --- |
| Week 1 | Environment ready | Secrets excluded, model call works, tests and CI run. |
| Week 4 | Direct LLM client | Typed CLI, structured output, cost, latency, retries, and tests. |
| Week 10 | Full-stack Incident Assistant | FastAPI, UI, persistence, streaming, authentication, and tests. |
| Week 16 | Cloud Runbook RAG Assistant | Visible retrieval, citations, permissions, and 40 test cases. |
| Week 22 | Infrastructure Assessment Agent | Durable state, reliable tools, approvals, limits, and adversarial tests. |
| Week 24 | Cloud Operations MCP Server | Read-only tools, schemas, authorization, audit, and threat model. |
| Week 28 | Fine-tuned open model | QLoRA adapter, evaluation, quantization, and model card. |
| Week 31 | GPU performance benchmark | CPU/GPU time, memory, precision, throughput, and bottlenecks. |
| Week 33 | High-throughput inference service | TTFT, TPOT, concurrency, throughput, and VRAM usage. |
| Week 34 | Kubernetes GPU workload | GPU scheduling, MIG or MPS decision, utilization metrics, and alerts. |
| Week 38 | Evaluation and security pipeline | 60+ cases plus prompt-injection and tool-permission tests. |
| Week 42 | Production AWS deployment | IAM, private access, autoscaling, observability, rollback, and cost report. |
| Week 44 | AI platform reference | Serving, registry, quotas, secrets, and GPU monitoring. |
| Week 48 | Cloud Migration Copilot | RAG, agent, MCP, GPU inference, managed fallback, evaluation, and operations guide. |

## Week by week

| Week | Phase | Focus | Build or public output |
| ---: | --- | --- | --- |
| 1 | Foundations | AI, ML, deep learning, GenAI, and LLM vocabulary | Glossary, use-case map, and limits summary |
| 2 | Foundations | Transformers, attention, embeddings, and tokenization | Transformer and attention explanation |
| 3 | Foundations | Typed Python, environments, async, Git, and tests | Typed package with unit tests and CI |
| 4 | Foundations | Model APIs, messages, sampling, structured output, and token cost | CLI client with JSON output, latency, and cost |
| 5 | Application development | FastAPI, Pydantic, REST, and dependency injection | Typed AI API with OpenAPI documentation |
| 6 | Application development | Async clients, streaming, retries, timeouts, and rate limits | Resilient streaming model client |
| 7 | Application development | Prompt design, structured outputs, and evaluation-driven iteration | Prompt suite with automated test cases |
| 8 | Application development | Function calling, tool schemas, validation, and error handling | Tool-calling service with validated inputs |
| 9 | Application development | PostgreSQL, Redis, conversation state, auth, and secrets | Stateful API with persistence and authentication |
| 10 | Application development | Full-stack AI product, Docker, tests, and CI | Incident Analysis Assistant |
| 11 | RAG engineering | Embeddings, cosine similarity, and retrieval metrics | Embedding comparison notebook |
| 12 | RAG engineering | Ingestion, parsing, cleaning, chunking, and metadata | Repeatable document ingestion pipeline |
| 13 | RAG engineering | PostgreSQL and pgvector semantic search | Search API backed by pgvector |
| 14 | RAG engineering | Hybrid search, reranking, query rewriting, and compression | Three-strategy retrieval benchmark |
| 15 | RAG engineering | Citations, streaming, and insufficient-evidence handling | Cited RAG service with visible chunks |
| 16 | RAG engineering | Evaluation, groundedness, injection, and permissions | Cloud Runbook RAG Assistant |
| 17 | Agents and LangGraph | Workflow versus agent; raw tool-calling loop | Agent loop with stopping limits |
| 18 | Agents and LangGraph | Tool design, idempotency, observations, retries, and recovery | Reliable read-only tool agent |
| 19 | Agents and LangGraph | LangGraph state, nodes, edges, routing, and parallel branches | Stateful graph with conditional routing |
| 20 | Agents and LangGraph | Persistence, memory, checkpoints, and human approval | Durable graph with approval checkpoint |
| 21 | Agents and LangGraph | Agentic RAG, orchestrator-worker, and multi-agent patterns | Agentic RAG workflow with evaluator |
| 22 | Agents and LangGraph | Testing, permissions, sandboxing, and security | Infrastructure Assessment Agent |
| 23 | MCP | Hosts, clients, servers, tools, resources, and transports | MCP client and local server prototype |
| 24 | MCP | Remote MCP, auth, authorization, audit, and threat modeling | Cloud Operations MCP server |
| 25 | Model development | PyTorch tensors, autograd, loops, and neural networks | Small neural network with evaluation |
| 26 | Model development | Transformers, tokenizers, datasets, and Trainer | Fine-tuned small transformer |
| 27 | Model development | Dataset preparation, LoRA, QLoRA, and experiment tracking | QLoRA experiment on a rented GPU |
| 28 | Model development | Quantization, evaluation, model cards, and responsible release | Quantized model and model card |
| 29 | GPU and inference | SMs, Tensor Cores, VRAM, bandwidth, and CUDA execution | GPU architecture notes and calculations |
| 30 | GPU and inference | CUDA Python, nvidia-smi, kernels, transfers, and profiling | CPU versus GPU workload comparison |
| 31 | GPU and inference | Profiler, mixed precision, torch.compile, and CUDA graphs | Profile and optimization report |
| 32 | GPU and inference | Batching, KV cache, PagedAttention, and quantization | Batch, memory, and throughput benchmark |
| 33 | GPU and inference | vLLM, TGI, TensorRT-LLM, TTFT, and TPOT | Comparative inference benchmark and API |
| 34 | GPU and inference | GPU Operator, scheduling, MIG, MPS, and DCGM | Kubernetes GPU workload and dashboard |
| 35 | LLMOps and security | Tracing, sessions, prompts, tokens, latency, and cost | Instrumented RAG and agent apps |
| 36 | LLMOps and security | Golden datasets, RAG evaluation, judges, and human review | Evaluation suite with 60 cases |
| 37 | LLMOps and security | Prompt injection, PII, tool permissions, and supply chain | Threat model and adversarial tests |
| 38 | LLMOps and security | SLOs, load tests, performance, cost, and regression CI | Quality, latency, throughput, and cost dashboard |
| 39 | Cloud production | Gateways, queues, caching, fallbacks, quotas, and tenant isolation | Production API with caching and fallback |
| 40 | Cloud production | Bedrock, IAM, VPC access, guardrails, and knowledge bases | Least-privilege Bedrock application |
| 41 | Cloud production | SageMaker training, GPU selection, endpoints, and autoscaling | Endpoint with cost-performance report |
| 42 | Cloud production | Terraform, CI/CD, canaries, load tests, rollback, and recovery | Reproducible cloud deployment pipeline |
| 43 | AI platform | KServe, Kubeflow, Knative, and model autoscaling | Autoscaling inference service and pipeline |
| 44 | AI platform | Registry, secrets, quotas, GPU observability, and chargeback | Reference AI platform with GPU monitoring |
| 45 | Capstone | Cloud Migration Copilot architecture, data model, API, and threat model | Architecture, backlog, contracts, and tests |
| 46 | Capstone | UI, RAG, LangGraph agent, and MCP integration | Working end-to-end application |
| 47 | Capstone | Managed-model and self-hosted GPU inference paths | Bedrock fallback plus GPU-served model |
| 48 | Capstone | Evaluation, security, load testing, optimization, docs, and demo | Portfolio demo and operations guide |

The machine-readable source is [`roadmap.yml`](https://github.com/balajirajmohan/Unlearn-AI--With-Me/blob/main/roadmap.yml). The private workbook remains the place for personal schedules, actual hours, costs, and notes.
