---
document_id: PLT-005
title: AI Architecture
version: 1.0.0
status: Active
owner: Mohan G.C.
last_updated: 2026-07-15
review_frequency: Every 6 months
category: Platform
tags:
  - ai
  - rag
  - llm
  - agents
  - memory
  - architecture
purpose: >
  Define the architecture for AI-powered services including
  LLM integration, Retrieval-Augmented Generation (RAG),
  agent orchestration, memory, evaluation, and educational workflows.
---

## AI Architecture

---

## Purpose

The AI platform enables intelligent educational experiences through modular AI services.

The architecture supports:

- AI Tutor
- Nepali AI Assistant
- Coding Assistant
- Robotics Assistant
- Documentation Assistant
- Research Assistant
- Administrative AI

The design allows new AI capabilities to be added without redesigning the platform.

---

## AI Principles

The AI platform follows these principles:

- AI assists humans rather than replacing them.
- Human oversight is maintained for high-impact decisions.
- AI services are modular and reusable.
- Responses should be grounded in trusted knowledge.
- Privacy and security are integrated into AI workflows.
- Every significant AI interaction should be observable and measurable.

---

## High-Level AI Architecture

```text
Users
   │
Frontend
   │
FastAPI Backend
   │
AI Gateway
   │
────────────────────────────────────
│        Agent Orchestrator        │
────────────────────────────────────
│ AI Tutor                         │
│ Nepali Assistant                 │
│ Coding Assistant                 │
│ Robotics Assistant               │
│ Research Assistant               │
│ Documentation Assistant          │
────────────────────────────────────
            │
      RAG Pipeline
            │
Embedding Model
            │
Vector Database
            │
Knowledge Sources
            │
LLM Provider
            │
Response
```

---

## AI Gateway

The AI Gateway acts as the single entry point for all AI requests.

Responsibilities include:

- Authentication
- Rate limiting
- Model routing
- Prompt preparation
- Logging
- Cost tracking
- Evaluation hooks

---

## Agent Orchestrator

The orchestrator selects the most appropriate AI agent for each request.

Initial agents include:

## AI Tutor

Supports:

- Course explanations
- Quiz assistance
- Personalized learning
- Study plans

---

## Nepali AI Assistant

Supports:

- Nepali language understanding
- Localized educational guidance
- Computer assistance
- Translation

---

## Coding Assistant

Supports:

- Python
- Java
- C/C++
- JavaScript
- FastAPI
- Next.js
- Debugging

---

## Robotics Assistant

Supports:

- Arduino
- Sensors
- Electronics
- Circuit design
- Python robotics
- Raspberry Pi

---

## Documentation Assistant

Supports:

- Writing
- Review
- Templates
- ADR creation
- Standards compliance

---

## Research Assistant

Supports:

- Literature review
- Paper summarization
- Experiment planning
- Research documentation

---

## Retrieval-Augmented Generation (RAG)

The RAG pipeline improves response quality by retrieving trusted organizational knowledge.

Knowledge sources include:

- Documentation
- Courses
- ADRs
- Research
- FAQs
- Project documentation

Pipeline:

```text
User Query
     ↓
Embedding
     ↓
Vector Search
     ↓
Relevant Context
     ↓
Prompt Assembly
     ↓
LLM
     ↓
Grounded Response
```

---

## Memory System

The platform supports multiple memory types.

## Session Memory

Current conversation only.

---

## User Memory

Preferences

Learning progress

Goals

Language preferences

---

## Organizational Memory

Documentation

ADRs

Standards

Knowledge Base

---

## AI Memory

Prompt history

Evaluations

Feedback

Agent learning metadata

---

## Model Layer

The platform supports multiple LLM providers.

Selection criteria include:

- Performance
- Cost
- Latency
- Licensing
- Reliability
- Privacy

Models should be replaceable without major architectural changes.

---

## Prompt Management

Prompt templates should be:

- Version controlled
- Documented
- Tested
- Reviewed
- Reusable

---

## AI Evaluation

Every AI service should be evaluated for:

- Accuracy
- Groundedness
- Hallucination rate
- Response quality
- Safety
- Latency
- User satisfaction

---

## Safety

AI systems should:

- Respect privacy
- Refuse harmful requests
- Protect confidential information
- Follow organizational governance
- Support human oversight

---

## Observability

Metrics include:

- Response time
- Retrieval accuracy
- Token usage
- Error rate
- Agent utilization
- User feedback

---

## Future AI Roadmap

Future capabilities include:

- Voice Assistant
- Vision Models
- Robotics Control
- Workflow Automation
- Multi-Agent Collaboration
- Personalized Learning Agents
- Offline AI Models

---

## Related Documents

- PLT-002 — System Architecture
- PLT-004 — Backend Architecture
- PLT-006 — Data Architecture
- COM-018 — Data & AI Governance Standards

---

## Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-07-15 | Initial release  |
