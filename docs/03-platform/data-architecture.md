---
document_id: PLT-006
title: Data Architecture
version: 1.0.0
status: Active
owner: Mohan G.C.
last_updated: 2026-07-15
review_frequency: Every 6 months
category: Platform
tags:
  - database
  - postgres
  - vector-db
  - storage
  - architecture
purpose: >
  Define the data architecture, storage strategy,
  database domains, relationships, and lifecycle
  management for the Code and Core platform.
---

## Data Architecture

---

## Purpose

This document defines how data is organized, stored, secured, and managed across the Code and Core platform.

The architecture separates operational data, AI knowledge, analytics, and media assets into appropriate storage systems to improve scalability, maintainability, and performance.

---

## Data Principles

The platform follows these principles:

- Single Source of Truth
- Normalize where practical
- Denormalize only for performance
- Data security by default
- Version important data
- Audit significant changes
- Backup critical data
- Minimize duplication

---

## Storage Architecture

The platform uses multiple storage systems.

```text
                Application
                     │
      ┌──────────────┼──────────────┐
      │              │              │
 PostgreSQL     Vector Database   Object Storage
      │              │              │
 Structured     AI Knowledge      Files & Media
```

---

## Primary Database

Technology:

- PostgreSQL

Stores:

- Users
- Roles
- Courses
- Lessons
- Enrollments
- Assessments
- Certificates
- Organizations
- AI metadata
- Audit logs

---

## Vector Database

Purpose:

Semantic search for AI systems.

Stores:

- Documentation embeddings
- Course embeddings
- Research embeddings
- ADR embeddings
- FAQ embeddings
- Conversation context

Used by:

- RAG
- AI Tutor
- Documentation Assistant
- Research Assistant

---

## Object Storage

Stores:

- Videos
- PDFs
- Images
- Robotics assets
- Assignments
- Downloads
- Course resources

---

## Core Business Domains

## Identity

Entities:

- User
- Role
- Permission
- Session
- Profile

---

## Learning

Entities:

- Course
- Module
- Lesson
- Enrollment
- Progress
- Certificate

---

## Assessment

Entities:

- Quiz
- Question
- Answer
- Submission
- Result

---

## AI

Entities:

- Conversation
- Message
- Prompt
- Agent
- Evaluation
- Feedback

---

## Documentation

Entities:

- Document
- Version
- ADR
- Category
- Tag

---

## Robotics

Entities:

- Project
- Component
- Sensor
- Lesson
- Experiment

---

## Relationships

```text
User
 │
 ├── Enrollments
 │
 ├── Conversations
 │
 ├── Progress
 │
 └── Certificates

Course
 │
 ├── Modules
 │
 ├── Lessons
 │
 ├── Assessments
 │
 └── Resources
```

---

## Data Lifecycle

```text
Create
   ↓
Validate
   ↓
Store
   ↓
Use
   ↓
Update
   ↓
Archive
   ↓
Delete
```

---

## Database Standards

Every table should include:

- id
- created_at
- updated_at
- created_by (where applicable)
- updated_by (where applicable)

Soft deletion should be considered for important records.

---

## Indexing Strategy

Indexes should be created for:

- Foreign keys
- Frequently queried fields
- User email
- Course slug
- Document slug
- Search fields

Composite indexes should be added based on query patterns.

---

## Migrations

Database changes should:

- Use migration tools
- Be version controlled
- Be reversible where possible
- Be tested before production

---

## Backup Strategy

Critical databases should have:

- Automated backups
- Recovery testing
- Retention policy
- Off-site storage for production

---

## Data Security

Requirements:

- Encryption in transit
- Encryption at rest where supported
- Access control
- Audit logging
- Least privilege
- Secure secrets management

---

## Future Growth

The architecture supports:

- Multi-tenancy
- Analytics warehouse
- Event storage
- Data lake integration
- Additional AI knowledge sources

---

## Related Documents

- PLT-002 — System Architecture
- PLT-004 — Backend Architecture
- PLT-005 — AI Architecture
- PLT-007 — Deployment Architecture
- COM-018 — Data & AI Governance Standards

---

## Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0.0   | 2026-07-15 | Initial release  |
