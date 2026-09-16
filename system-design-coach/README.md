````md
# System Design Coach

A reusable AI skill for practicing System Design interviews through adaptive questioning, architectural reasoning, trade-off analysis, and structured feedback.

Instead of generating a complete architecture for the candidate, System Design Coach behaves like an interviewer or coach and encourages the candidate to reason through the problem.

---

## Overview

System Design interviews require more than knowing technologies or common architecture patterns.

Candidates are expected to:

- Clarify ambiguous requirements
- Identify functional and non-functional requirements
- Estimate scale when relevant
- Make architectural decisions
- Explain trade-offs
- Identify bottlenecks
- Handle failure scenarios
- Discuss consistency and reliability
- Consider operational concerns
- Communicate decisions clearly

System Design Coach is designed to help candidates practice these skills interactively.

The goal is not to memorize architectures.

The goal is to improve architectural reasoning.

---

## Core Principles

The skill follows a few important principles:

- Reasoning over memorization
- Decisions over technology names
- Trade-offs over "perfect" architectures
- Adaptive follow-ups instead of predefined question lists
- Relevant topics instead of architecture checklists
- Progressive assistance when the candidate gets stuck
- Evidence-based feedback at the end of the session

There is no assumption that a System Design problem has a single correct architecture.

---

## Modes

System Design Coach supports three modes.

### Coached

Designed for learning and practice.

The coach:

- Asks one question at a time
- Lets the candidate reason before providing feedback
- Uses guiding questions when the candidate gets stuck
- Explores decisions before correcting them
- Provides feedback during the session
- Explains concepts when necessary

The goal is to develop reasoning rather than provide immediate answers.

---

### Interview

Simulates a realistic System Design interview.

The interviewer:

- Presents the problem with limited initial information
- Expects the candidate to clarify requirements
- Generates follow-up questions from the candidate's decisions
- Does not provide hints or corrections during the simulation
- Evaluates decisions and trade-offs
- Provides structured feedback at the end

This mode is intended to reproduce the dynamics of a real technical interview.

---

### Pressure

A more demanding interview simulation designed primarily for Senior-level candidates and above.

Pressure mode inherits the rules of Interview mode and adds additional challenges such as:

- Challenging assumptions
- Introducing realistic failure scenarios
- Questioning scalability decisions
- Challenging consistency models
- Introducing plausible requirement changes
- Exploring operational concerns
- Discussing cost and operational efficiency
- Requiring candidates to defend architectural trade-offs

The mode increases difficulty without becoming intentionally adversarial.

---

## Session Flow

A typical session may explore:

```text
Problem
   ↓
Requirements clarification
   ↓
Functional requirements
   ↓
Non-functional requirements
   ↓
Scale estimation
   ↓
High-level architecture
   ↓
Data model
   ↓
API / interface design
   ↓
Core components
   ↓
Data flow
   ↓
Scalability
   ↓
Reliability and failure handling
   ↓
Consistency and transactions
   ↓
Observability
   ↓
Security
   ↓
Trade-offs
   ↓
Bottlenecks
   ↓
Final review
```
````

This is not a mandatory checklist.

The session adapts to the problem, available time, candidate seniority, and architectural decisions made during the discussion.

---

## Adaptive Follow-ups

One of the main behaviors of System Design Coach is adaptive questioning.

Follow-up questions are generated from the candidate's answer rather than from a predefined list.

They may explore:

- Architectural decisions
- Unjustified assumptions
- Risks
- Bottlenecks
- Trade-offs
- Failure scenarios
- Missing requirements

For example:

```text
Candidate:
"I would use Kafka between these services."

Coach:
"What requirement makes asynchronous communication useful here?"
```

A later follow-up could explore:

```text
"What happens if the same event is delivered twice?"
```

The conversation follows the candidate's architecture rather than forcing a predefined solution.

---

## Progressive Help

In Coached mode, the skill uses progressive assistance when the candidate gets stuck.

```text
Guided Question
      ↓
Conceptual Hint
      ↓
Direct Explanation
```

The coach always starts with the least intrusive level of help.

### Guided Question

Helps the candidate discover the next step independently.

### Conceptual Hint

Provides direction without revealing the complete answer.

### Direct Explanation

Provides a direct explanation with examples when the candidate remains stuck or explicitly requests the answer.

---

## Areas That May Be Explored

Depending on the problem, the coach may explore areas such as:

- Requirements discovery
- Capacity estimation
- High-level architecture
- Data modeling
- API design
- Scalability
- Horizontal scaling
- Database replication
- Partitioning and sharding
- Caching
- Messaging
- Asynchronous processing
- Backpressure
- Reliability
- Failure recovery
- Consistency models
- Distributed transactions
- Idempotency
- Outbox Pattern
- Saga Pattern
- Observability
- Security
- Cost
- Operational efficiency
- Architectural trade-offs

These areas are references, not mandatory steps.

The coach should only explore topics that materially affect the system being designed.

---

## Failure Scenarios

Interview and Pressure modes can introduce realistic failure scenarios based on the architecture proposed by the candidate.

Examples include:

- Traffic increases significantly
- A database node fails
- A message broker becomes unavailable
- A message is delivered more than once
- A worker crashes during processing
- A region becomes unavailable
- A cache fails
- An external dependency times out
- A customer generates disproportionate traffic

The scenarios should be connected to the candidate's architecture rather than introduced randomly.

---

## Evaluation

The candidate may be evaluated across several dimensions.

### Requirements

Ability to discover and clarify important functional and non-functional requirements.

### Architecture

Ability to create a coherent architecture with clear component responsibilities.

### Scalability

Ability to identify bottlenecks and propose appropriate scaling strategies.

### Reliability

Ability to reason about failures, retries, idempotency, recovery, and resilience.

### Data

Ability to choose appropriate storage models and reason about access patterns and consistency.

### Trade-offs

Ability to explain decisions, recognize disadvantages, and consider alternatives.

### Communication

Ability to structure the discussion and explain architectural decisions clearly.

### Seniority Signals

For Senior-level candidates and above, the evaluation also considers:

- Production-oriented thinking
- Operational awareness
- Cost awareness
- Risk identification
- Decision-making under ambiguity
- Prioritization
- Simplicity
- Failure recovery
- Architecture evolution
- Cross-team concerns
- Recognition of limitations

---

## Feedback

At the end of a session, feedback focuses on four areas:

### Strength

What the candidate did well.

### Gap

What important area was missing or weak.

### Impact

Why that gap matters in a real system or interview.

### Improvement

What the candidate should practice or improve next.

Feedback should be based on evidence observed during the session.

---

## Session Assessment

When appropriate, the session can be classified by quality:

- Below Expectations
- Developing
- Meets Expectations
- Strong

The coach can also identify demonstrated seniority signals:

- Junior
- Mid-level
- Senior
- Staff-level

Seniority signals represent only what was demonstrated during the session and are not intended to be a definitive assessment of the candidate's professional level.

---

## Example Prompts

### Coached Mode

```text
Use System Design Coach in Coached mode.

I want to practice designing a payment processing platform for a Senior Backend Engineer interview.

I have 45 minutes.
```

### Interview Mode

```text
Run a realistic System Design interview.

Target role: Senior Backend Engineer
Mode: Interview
Duration: 45 minutes

Choose the problem for me.
```

### Pressure Mode

```text
Use Pressure mode for a Senior/Staff System Design interview.

Challenge my architectural decisions, scalability assumptions,
failure handling, consistency model, and operational costs.

Do not give me hints during the interview.
```

### Focused Practice

```text
Use Coached mode.

I want to practice System Design specifically around:
- idempotency
- distributed transactions
- messaging
- failure recovery

Choose an appropriate problem for me.
```

---

## Repository Structure

```text
system-design-coach/
├── SKILL.md
├── README.md
├── README.pt-br.md
└── CHANGELOG.md
```

### `SKILL.md`

Contains the actual behavior and instructions used by the System Design Coach.

### `README.md`

English documentation for the project.

### `README.pt-br.md`

Portuguese documentation.

### `CHANGELOG.md`

Tracks changes between versions.

---

## Design Philosophy

System Design Coach is intentionally not an architecture generator.

A candidate can memorize that a system might use:

```text
API Gateway
Redis
Kafka
PostgreSQL
Kubernetes
```

and still struggle in a System Design interview.

The important questions are:

```text
Why is this component necessary?

What requirement does it solve?

What trade-off does it introduce?

What happens when it fails?

What happens when traffic grows?

What would make you change this decision?
```

System Design Coach is designed around those questions.

---

## Versioning

This project follows semantic versioning.

```text
MAJOR.MINOR.PATCH
```

Example:

```text
v1.0.0
```

- **MAJOR** — Breaking behavior or structural changes
- **MINOR** — New capabilities or modes
- **PATCH** — Fixes, clarification, or small behavioral improvements

---

## Current Version

`v1.0.0`

Initial public version of System Design Coach.

---

## License

See the repository license for usage and distribution terms.
