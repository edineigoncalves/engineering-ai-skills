# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)
and this project follows [Semantic Versioning](https://semver.org/).

---

## [1.0.0] - 2026-09-16

### Added

- Initial public release of System Design Coach.
- Added three session modes:
  - `Coached`
  - `Interview`
  - `Pressure`
- Added adaptive session initialization based on:
  - Session mode
  - Target role and seniority
  - System Design problem
  - Technical gaps
  - Available time
- Added adaptive System Design interview flow covering:
  - Requirements clarification
  - Functional requirements
  - Non-functional requirements
  - Capacity estimation
  - High-level architecture
  - Data modeling
  - API design
  - Scalability
  - Reliability
  - Consistency
  - Transactions
  - Caching
  - Messaging
  - Observability
  - Security
  - Trade-offs
  - Bottlenecks
- Added adaptive follow-up questions based on candidate decisions instead of predefined question lists.
- Added progressive assistance for `Coached` mode:
  - Guided Question
  - Conceptual Hint
  - Direct Explanation
- Added realistic failure scenario exploration for `Interview` and `Pressure` modes.
- Added support for challenging:
  - Scalability assumptions
  - Consistency models
  - Failure handling
  - Cost decisions
  - Operational efficiency
  - Architectural trade-offs
- Added plausible requirement changes during `Pressure` mode.
- Added consistency rules to prevent interview requirements and assumptions from changing unexpectedly.
- Added time-aware session behavior to prioritize high-impact architectural decisions when time is limited.
- Added structured evaluation criteria for:
  - Requirements
  - Architecture
  - Scalability
  - Reliability
  - Data
  - Trade-offs
  - Communication
  - Seniority signals
- Added evidence-based session feedback covering:
  - Strengths
  - Gaps
  - Impact
  - Improvement areas
- Added session quality classifications:
  - Below Expectations
  - Developing
  - Meets Expectations
  - Strong
- Added demonstrated seniority signals:
  - Junior
  - Mid-level
  - Senior
  - Staff-level
- Added English project documentation in `README.md`.
- Added Portuguese documentation in `README.pt-br.md`.
- Added semantic versioning strategy for future releases.

---

## Versioning

This project follows Semantic Versioning:

```text
MAJOR.MINOR.PATCH
```

- **MAJOR** — Breaking changes to behavior, modes, or core skill structure.
- **MINOR** — New capabilities, evaluation areas, modes, or significant improvements.
- **PATCH** — Bug fixes, instruction clarifications, documentation updates, or minor behavioral adjustments.
