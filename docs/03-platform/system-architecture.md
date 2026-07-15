---
document_id: PLT-002
title: System Architecture
version: 1.0.0
status: Active
owner: Mohan G.C.
reviewed_by:
last_updated: 2026-07-15
review_frequency: Every 6 months
category: Platform
tags:
  - architecture
  - system-design
  - platform
  - backend
  - frontend
audience:
  - Developers
  - AI Engineers
  - Contributors
purpose: >
  Define the overall system architecture, major components,
  interactions, and architectural principles for the Code and Core platform.
---

## System Architecture

## Purpose

This document describes the overall architecture of the Code and Core platform.

It explains how the frontend, backend, AI services, databases, authentication, storage, and external integrations interact to deliver a scalable educational platform.

---

## Architecture Style

Code and Core adopts a modular, service-oriented architecture with clear separation of responsibilities.

Core architectural characteristics include:

- API-first
- Modular design
- Stateless backend services
- AI-native workflows
- Documentation-first development
- Secure by design
- Scalable infrastructure

---

## High-Level Architecture

```text
                         Users
                           │
          ┌────────────────┼────────────────┐
          │                │                │
      Learners       Instructors      Administrators
          │                │                │
          └────────────────┼────────────────┘
                           │
                     Next.js Frontend
                           │
                     REST API Gateway
                           │
     ┌──────────────┬──────────────┬──────────────┐
     │              │              │              │
 Authentication  Course API   AI Services   Admin API
     │              │              │              │
     └──────────────┼──────────────┼──────────────┘
                    │              │
              PostgreSQL      Vector Database
                    │              │
                    └──── Object Storage ────┘
```

---

## Major Components

## Frontend

Responsibilities:

- User interface
- Dashboard
- Course pages
- Documentation viewer
- AI chat interface
- Profile management

Technology:

- Next.js
- TypeScript
- Tailwind CSS

---

## Backend

Responsibilities:

- Business logic
- Authentication
- API management
- Database access
- User management
- Course management

Technology:

- FastAPI
- Python

---

## AI Layer

Responsibilities:

- AI Tutor
- Nepali AI Assistant
- RAG
- Prompt management
- Agent workflows
- Model evaluation

---

## Database Layer

Stores:

- Users
- Courses
- Lessons
- Progress
- AI metadata
- Permissions
- Organizational data

Technology:

- PostgreSQL

---

## Vector Database

Stores:

- Embeddings
- Documentation
- Knowledge base
- Course content
- Research documents

Purpose:

Enable Retrieval-Augmented Generation (RAG).

---

## Object Storage

Stores:

- Videos
- PDFs
- Images
- Robotics resources
- Course downloads
- Assignment files

---

## External Services

Examples include:

- GitHub
- Email provider
- Payment gateway
- Video hosting
- AI model providers

All integrations should use well-defined interfaces to simplify replacement or extension.

---

## Communication Flow

1. User sends a request from the frontend.
2. Backend authenticates the request.
3. Backend processes business logic.
4. Data is retrieved or updated.
5. AI services are invoked if required.
6. Response is returned to the frontend.

---

## Security Considerations

- HTTPS only
- JWT authentication
- Role-based authorization
- Input validation
- Secure secret management
- Audit logging
- Dependency monitoring

---

## Scalability Strategy

The platform should support:

- Horizontal API scaling
- Independent AI services
- Database optimization
- Caching
- Asynchronous background jobs
- CDN for static assets

---

## Observability

Operational visibility includes:

- Structured logging
- Health checks
- Metrics
- Performance monitoring
- Error tracking
- Audit logs

---

## Architecture Principles

- Keep components loosely coupled.
- Prefer composition over duplication.
- Minimize external dependencies.
- Design for maintainability.
- Document architectural decisions using ADRs.

---

## Future Enhancements

Potential future capabilities:

- Mobile applications
- Microservices where justified
- Event-driven workflows
- Real-time collaboration
- Offline learning support
- Multi-region deployments

---

## Related Documents

- PLT-001 — Platform Architecture Overview
- PLT-003 — Frontend Architecture
- PLT-004 — Backend Architecture
- PLT-005 — AI Architecture
- PLT-006 — Data Architecture

---

## Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-07-15 | Initial release  |
