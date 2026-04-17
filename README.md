# Adaptive Query-Routing Agentic System

## Overview
This project implements an adaptive multi-agent Retrieval-Augmented Generation (RAG) system that dynamically routes user queries to specialized models based on domain and complexity. Unlike traditional single-model pipelines, this system improves accuracy, relevance, and efficiency by leveraging multiple domain-specific agents.

## Problem Statement
Generic LLM pipelines use the same model and retrieval flow for all queries, regardless of domain or reasoning type. This leads to:
- Reduced response quality
- Poor domain-specific accuracy
- Increased hallucination risk
- Inefficient use of context

The objective of this project is to design a system that intelligently routes queries to the most suitable model or agent.

## Methodology
The system follows a multi-stage pipeline:
1. User query is received
2. Routing agent analyzes query type
3. Query is either:
   - Answered directly (simple queries), or
   - Decomposed into sub-queries (complex queries)
4. Sub-queries are routed to domain-specific agents
5. Retrieved responses are synthesized into a final answer

As described in the project methodology section  [oai_citation:0‡pRAGmatic_AI_GenAI_miniproject.pdf](sediment://file_000000008ab0720bad6df11dc01fffe1), the system combines query understanding, agent orchestration, and response generation into a unified workflow.

## Architecture
- Router Agent: Determines query type and routing path
- General Agent: Handles simple queries
- Medical Agent: Processes biomedical queries
- Math Agent: Solves mathematical problems
- Synthesizer Agent: Combines outputs into final response

## Implementation
### Phase 1
- Single base model (LLaMA 3.3 70B) used for all agents
- Specialization achieved through prompt engineering

### Phase 2
- Replaced prompt-based specialization with dedicated models:
  - Router & Simple QA: LLaMA 3.1 8B
  - Medical Agent: BioMistral 7B
  - Math Agent: Qwen3 32B
  - Synthesizer: LLaMA 3.3 70B

This improved true domain expertise and response quality.

## Features
- Multi-agent architecture
- Dynamic query routing
- Domain-specific processing
- Context-aware response generation
- Hybrid local and API-based model usage

## Results
Key observations from evaluation  [oai_citation:1‡pRAGmatic_AI_GenAI_miniproject.pdf](sediment://file_000000008ab0720bad6df11dc01fffe1):
- Improved answer quality compared to single-model systems
- Better domain-specific reasoning
- Approximately 70% cost reduction compared to always using large models
- More consistent and reliable outputs
- Trade-off: increased latency for complex queries

## Conclusion
The project demonstrates that orchestrating multiple specialized models is more effective than relying on a single large model. Adaptive routing significantly enhances performance, efficiency, and reliability in domain-specific question answering.

## Team
- Dishan D (PES1UG23CS196)
- Gujjar R Suman Rao (PES1UG23CS223)
- Yash Michael Tharappan (PES1UG23CS713)

## Guide
- Dr. Shylaja S S

## Course
UE23CS342BA4 – Generative AI and its Applications
