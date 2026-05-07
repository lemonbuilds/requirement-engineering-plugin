---
name: user-stories
description: >
  Writes, reviews, splits, and documents user stories as a requirements
  engineer using IREB-aligned requirements quality criteria, INVEST, acceptance
  criteria, and SOPHIST-inspired precise language. Use when the user asks to
  write user stories, refine backlog items, formulate agile requirements,
  create epics and stories, add acceptance criteria, split stories, check story
  quality, or convert product ideas, features, PRDs, use cases, or requirements
  into user stories.
---

# User Stories

## Purpose

Create or update user stories that are clear, valuable, testable, and suitable
for a product backlog. Work in German by default when the surrounding project or
user request is German; otherwise use the project language.

Use SOPHIST-inspired precision for wording and IREB-style requirements quality:
unambiguous, complete enough for the context, consistent, verifiable, feasible,
necessary, and traceable.

## Default Output

Create or update `docs/user-stories.md` unless the user gives another target.
When a backlog already exists, preserve existing IDs and append or update
stories without renumbering unrelated entries.

Use this Markdown structure:

1. Context and assumptions
2. Personas or roles
3. Epics
4. User stories
5. Acceptance criteria
6. Dependencies, risks, and open questions

## Story Format

Use this story template unless the project already uses another one:

`Als <Rolle> moechte ich <Ziel/Faehigkeit>, damit <Nutzen/Wert>.`

For each story include:

| ID | Epic | Rolle | User Story | Akzeptanzkriterien | Prioritaet | Status |
|----|------|-------|------------|--------------------|------------|--------|

Use IDs such as `US-001`, `US-002`. Use priority values `High`, `Medium`, or
`Low` and status values `Open`, `Ready`, `In Progress`, `Done`, or `Blocked`,
unless the project defines other values.

## Acceptance Criteria

Write acceptance criteria in Given/When/Then form by default:

```gherkin
Given <Ausgangssituation>
When <Ereignis oder Aktion>
Then <beobachtbares Ergebnis>
```

Each criterion must be objectively testable and must describe observable system
behavior, not implementation details.

## Workflow

1. Read `docs/vision.md`, `docs/requirements.md`, `docs/use_cases/`, existing
   backlog files, or the user briefing.
2. Identify actors, goals, business value, constraints, dependencies, and terms.
3. Derive epics only when they help group multiple stories.
4. Write one user goal per story. Split compound goals.
5. Add acceptance criteria that cover the main success path and important
   alternatives or error cases.
6. Check each story against INVEST and requirements quality criteria.
7. Mark assumptions, conflicts, and open questions explicitly.
8. Preserve traceability to source requirements or use cases when source IDs are
   available.

## Quality Checks

Before finalizing, verify every story:

- Independent: Can be planned without unnecessary coupling to another story
- Negotiable: Leaves room for solution design while keeping the need clear
- Valuable: States a user or business benefit in the `damit` clause
- Estimable: Has enough scope clarity for sizing
- Small: Fits within one iteration or is split into smaller stories
- Testable: Has pass/fail acceptance criteria
- Precise: Avoids vague adjectives such as `einfach`, `schnell`,
  `benutzerfreundlich`, or `optimal` unless quantified in criteria
- Singular: Contains one user goal, not a bundle of features
- Traceable: Links to source IDs where available

## DO NOT

- Write tasks such as "Implement database table" as user stories unless the
  actor value is explicit
- Put multiple roles, goals, or benefits into one story
- Use acceptance criteria as hidden design instructions
- Write vague benefits such as "so that it is better"
- Omit acceptance criteria for stories intended to be implementation-ready
- Invent legal, compliance, or business rules without marking them as
  assumptions

## Reference

For detailed writing rules, splitting patterns, examples, and review heuristics,
read `references/story-writing-guide.md` when creating more than a few stories,
reviewing story quality, or resolving ambiguous phrasing.
