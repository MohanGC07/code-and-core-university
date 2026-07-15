---
document_id: PLT-004
title: Backend Architecture
version: 1.0.0
status: Active
owner: Mohan G.C.
last_updated: 2026-07-15
review_frequency: Every 6 months
category: Platform
tags:
  - backend
  - fastapi
  - architecture
  - api
  - python
purpose: >
  Define the backend architecture, project structure,
  services, APIs, authentication, data access,
  background jobs, and development standards
  for the Code and Core platform.
---

## Backend Architecture

---

## Purpose

The backend provides the core business logic for the platform.

It exposes APIs, manages users, courses, AI services,
authentication, databases, storage, and external integrations.

The backend is designed to be modular, scalable,
testable, and easy to maintain.

---

## Technology Stack

| Layer | Technology |
| --------- | ----------- |
| Framework | FastAPI |
| Language | Python |
| Validation | Pydantic |
| ORM | SQLAlchemy |
| Database | PostgreSQL |
| Authentication | JWT |
| Background Jobs | Celery |
| Cache | Redis |
| File Storage | S3 Compatible Storage |
| Documentation | OpenAPI |

---

## Backend Principles

The backend follows:

- API First
- Modular Architecture
- Separation of Concerns
- Dependency Injection
- Secure by Design
- Testability
- Documentation First
- Version Controlled APIs

---

## High-Level Architecture

```text
Next.js Frontend
        │
 REST API
        │
FastAPI Backend
        │
 ├── Authentication
 ├── User Service
 ├── Course Service
 ├── AI Service
 ├── Robotics Service
 ├── Analytics Service
 ├── Notification Service
 └── Admin Service
        │
 PostgreSQL
 Redis
 Object Storage
 AI Providers
```

---

## Project Structure

```text
backend/

app/
│
├── api/
│   ├── v1/
│   ├── auth/
│   ├── users/
│   ├── courses/
│   ├── ai/
│   ├── robotics/
│   ├── admin/
│   └── analytics/
│
├── core/
│
├── config/
│
├── database/
│
├── models/
│
├── schemas/
│
├── repositories/
│
├── services/
│
├── dependencies/
│
├── middleware/
│
├── security/
│
├── workers/
│
├── utils/
│
├── tests/
│
└── main.py
```

---

## Layered Architecture

```text
API Layer

↓

Service Layer

↓

Repository Layer

↓

Database
```

Each layer has one responsibility.

Business logic should never be inside API routes.

---

## API Layer

Responsibilities

- Receive requests
- Validate input
- Call services
- Return responses
- Handle errors

---

## Service Layer

Contains

- Business logic
- AI orchestration
- Course management
- User management
- Notifications
- Analytics

---

## Repository Layer

Responsible for

- Database queries
- CRUD operations
- Transactions
- Persistence

Repositories should never contain business logic.

---

## Database Layer

Stores

- Users
- Courses
- Lessons
- Enrollments
- AI Conversations
- Documents
- Permissions
- Audit Logs

---

## Authentication

Authentication uses

- JWT Access Token
- Refresh Token
- Role Based Access Control

Roles

- Admin
- Instructor
- Learner

Future

- OAuth
- Google Login
- GitHub Login

---

## AI Services

The AI module manages

- RAG
- AI Tutor
- Prompt Templates
- Embeddings
- Model Routing
- Chat History
- Agent Execution

---

## Background Tasks

Examples

- Email
- Notifications
- Embedding generation
- Video processing
- Report generation
- Scheduled jobs

Technology

- Celery
- Redis

---

## Error Handling

Every API returns

- Status
- Message
- Error Code
- Details (when appropriate)

Standardized error responses improve consistency.

---

## Logging

The backend records

- Authentication
- API requests
- Errors
- AI requests
- Database failures
- Background jobs

---

## Security

Requirements

- HTTPS
- Input validation
- Rate limiting
- Secure headers
- JWT validation
- Password hashing
- Secret management

---

## Testing

Testing includes

- Unit Tests
- Integration Tests
- API Tests
- Security Tests

---

## Performance

Optimization strategies

- Redis caching
- Async endpoints
- Pagination
- Query optimization
- Background processing

---

## Future Expansion

The architecture supports

- Microservices
- Event-driven messaging
- AI orchestration
- Multiple AI providers
- Multi-tenancy
- Mobile APIs

---

## Related Documents

- PLT-001
- PLT-002
- PLT-003
- PLT-005

---

## Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-07-15 | Initial release  |
