---
adr_id: ADR-002
title: Domain-Based Documentation Architecture
status: Accepted
version: 1.0.0
date: 2026-07-15
decision_makers:
  - Mohan G.C.
category: Documentation
related_documents:
  - COM-011
related_adrs:
  - ADR-001
---

## ADR-002: Domain-Based Documentation Architecture

## Status

Accepted

---

## Context

As Code and Core expands into education, software engineering, AI, robotics, research, and operations, storing all documentation in a single directory or organizing it only by document type will make navigation and maintenance increasingly difficult.

A scalable documentation structure is required to ensure information remains easy to locate and manage over time.

---

## Decision

Code and Core adopts a **Domain-Based Documentation Architecture**.

Documentation shall be organized by functional domains rather than by document type.

Each domain owns and maintains its related documents while following the organization's documentation standards.

---

## Rationale

This decision:

- Improves scalability.
- Simplifies navigation.
- Encourages ownership.
- Reduces duplication.
- Aligns documentation with organizational structure.
- Supports future growth without major restructuring.

---

## Repository Structure

```text
docs/
├── 00-company/
├── 01-courses/
├── 02-operations/
├── 03-platform/
├── 04-ai/
├── 05-robotics/
├── 06-youtube/
├── 07-corporate/
├── 08-community/
├── 09-research/
├── assets/
└── templates/
```

---

## Consequences

## Positive

- Better organization.
- Easier navigation.
- Clear ownership.
- Supports long-term expansion.

## Negative

- Initial planning required.
- Domain boundaries may evolve as the organization grows.

---

## Alternatives Considered

## Organize by Document Type

Example:

```text
Policies/
Standards/
Guides/
```

Rejected because related information becomes scattered across multiple folders.

---

## Flat Documentation Structure

Rejected because it does not scale as the number of documents increases.

---

## Implementation

- Every new document must belong to an existing domain.
- New domains require organizational approval.
- Navigation in MkDocs must reflect the domain structure.

---

## Related Documents

- COM-011 — Documentation Standards
- COM-010 — Operational Standards

---

## Related ADRs

- ADR-001 — Documentation First

---

## Review

Review when organizational domains change or significant restructuring is required.

---

## Revision History

| Version | Date | Description |
| ------- | ---- | ----------- |
| 1.0.0 | 2026-07-15 | Initial release |
