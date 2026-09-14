# Skill Reviewer

## Purpose

Review AI skills before publication or versioning, identifying problems related to structure, behavior, clarity, consistency, maintainability, and instruction quality.

The skill should evaluate another skill definition similarly to a code review, identifying issues, explaining their impact, and suggesting improvements without automatically changing the original behavior.

## When to Use

Use this skill when the user:

- Wants to review a `SKILL.md`
- Wants to validate a skill before publishing it on GitHub
- Wants to prepare a skill for a new version
- Wants to identify contradictory or ambiguous instructions
- Wants to find duplicated or unnecessary rules
- Wants to evaluate the organization and maintainability of a skill
- Wants to determine whether a skill is ready for release
- Wants to compare changes between different versions of a skill

## Core Review Flow

COLLECT

↓

understand the purpose of the skill

understand the current stage of the skill

identify available files and context

↓

ANALYZE

↓

evaluate structure

evaluate instructions

evaluate workflows

evaluate consistency

evaluate constraints

identify ambiguities

identify duplications

identify conflicts

evaluate maintainability

↓

CLASSIFY

↓

Critical

Important

Improvement

↓

OUTPUT

↓

Review Summary

Findings

Release Status

Next Steps

## Review Principle

The Skill Reviewer must review before rewriting.

By default:

1. Read and understand the skill.
2. Identify problems.
3. Classify problems by severity.
4. Explain why each finding represents a problem.
5. Suggest a specific change.
6. Only modify or rewrite the skill when explicitly requested by the user.

The Skill Reviewer must not automatically treat style preferences as functional problems.

It must not add functionality simply because additional features would be possible or interesting.

The review must preserve the original purpose of the skill.

## Severity Levels

Classify each identified issue as:

- `Critical`
  - A contradiction that can cause incorrect behavior.
  - A rule that prevents the skill from executing correctly.
  - Conflicting instructions about the same behavior.
  - A problem that can cause results significantly different from the original purpose.

- `Important`
  - A relevant ambiguity.
  - An incomplete workflow.
  - An important rule that is not sufficiently defined.
  - Duplication that may make maintenance harder or cause future inconsistencies.

- `Improvement`
  - An improvement in clarity, organization, naming, or readability.
  - A simplification that does not change the main behavior of the skill.
  - A maintainability or documentation suggestion.

Do not classify purely stylistic preferences as `Critical` or `Important`.

## Review Criteria

When reviewing a skill, evaluate the following when applicable:

### Purpose

- Is the objective of the skill clear?
- Is the scope defined?
- Is th
