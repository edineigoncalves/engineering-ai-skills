# Interview Coach

Interview Coach is an AI skill designed to help senior software engineers prepare for technical and behavioral interviews.

It evaluates job requirements against the candidate's real experience, identifies preparation risks and knowledge gaps, prioritizes what to study, and supports realistic or coached interview simulations.

## What It Does

Interview Coach can help you:

- Analyze a job description before an interview
- Compare job requirements against your experience
- Identify technical strengths, gaps, and unknown areas
- Prioritize preparation based on interview impact
- Create a preparation backlog
- Practice technical questions
- Practice behavioral questions using STAR
- Improve technical and behavioral answers
- Run coached mock interviews
- Run realistic mock interviews
- Evaluate interview readiness
- Use public GitHub projects as additional technical evidence

## Operating Modes

### Preparation Mode

Use this mode before an interview.

The coach analyzes:

```text
Job Requirements
        ↓
Candidate Experience
        ↓
Requirement Assessment
        ↓
Strengths / Risks / Gaps
        ↓
Preparation Priorities
        ↓
Preparation Backlog
```

Technical requirements are classified as:

- `Strong Match`
- `Partial Match`
- `Gap`
- `Unknown`

Preparation priorities are classified as:

- `High`
- `Medium`
- `Low`

When enough evidence is available, overall role fit can be classified as:

- `Strong Fit`
- `Moderate Fit`
- `Low Fit`
- `Insufficient Evidence`

### Mock Interview Mode

Mock Interview Mode supports two styles.

#### Coached Mock

The coach asks one question at a time, evaluates the answer, provides feedback, and continues the interview.

Useful when the goal is learning and improving during the simulation.

#### Realistic Mock

The coach behaves more like a real interviewer.

During the simulation, it does not provide:

- Hints
- Corrections
- Suggested answers
- Feedback

Evaluation is provided only after the mock interview ends.

## Technical Interviews

Technical answers can be evaluated based on:

### Knowledge

- Technical correctness
- Depth

### Engineering Judgment

- Rationale
- Trade-offs

### Production Readiness

- Scalability
- Security
- Observability
- Monitoring
- Cost
- High-volume behavior

The goal is not only to determine whether an answer is technically correct, but whether it demonstrates senior-level engineering judgment.

## Behavioral Interviews

Behavioral preparation uses the STAR framework:

```text
Situation
Task
Action
Result
```

The coach also looks for senior-level signals such as:

- Ownership
- Decision making
- Trade-offs
- Impact

Interview Coach never invents candidate experience, responsibilities, decisions, results, or metrics.

## Candidate Context

The skill can use available candidate information such as:

- Resume or CV
- Professional experience
- Projects
- Technologies
- Previous answers
- Conversation context
- Public GitHub profile

Missing information is not automatically considered a gap.

When there is not enough evidence to evaluate a requirement, it is classified as `Unknown`.

## GitHub Analysis

When a public GitHub profile is provided, Interview Coach can use repositories as additional evidence of technical experience.

It may analyze areas such as:

- Languages
- Frameworks
- Architecture
- Testing
- Documentation
- CI/CD
- Infrastructure as code
- Engineering practices

GitHub is treated as complementary evidence and not as a complete representation of professional experience.

## Example — Interview Preparation

```text
Use Interview Coach.

I have a Senior Backend Engineer interview tomorrow.

Here is the job description:

[paste job description]

Here is my resume:

[paste resume]

Analyze my fit, identify the highest-risk gaps,
and create a preparation backlog.
```

## Example — Coached Mock

```text
Start a Coached Mock interview for a Senior Backend Engineer role.

Focus on Java, Spring Boot, Kafka, PostgreSQL,
distributed systems and AWS.

Ask one question at a time.
```

## Example — Realistic Mock

```text
Start a Realistic Mock interview for a Senior Backend Engineer role.

Do not give me hints or feedback during the interview.

Give me the complete assessment only after the interview ends.
```

## Example — Fast Preparation

```text
I have a Senior Backend Engineer interview in 30 minutes.

Prepare me for Java, Spring Boot, microservices,
Kafka, PostgreSQL and AWS.

Prioritize only the highest-risk topics.
```

## Skill Definition

The AI behavior and evaluation rules are defined in:

`SKILL.md`

## Language

The skill definition is written in English, but Interview Coach can interact with the candidate in their preferred language.

For international interview preparation, the candidate can explicitly request that the mock interview be conducted in English or another interview language.

## Design Principles

Interview Coach follows a few core principles:

- Evidence over assumptions
- `Unknown` is not automatically a `Gap`
- Prioritize instead of trying to study everything
- Evaluate senior engineering judgment, not only memorized knowledge
- Never fabricate candidate experience
- Preserve realistic interview behavior when using Realistic Mock
