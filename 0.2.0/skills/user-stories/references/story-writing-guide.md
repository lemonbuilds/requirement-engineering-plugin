# User Story Writing Guide

## Writing Principles

Use user stories as agile requirements, not as implementation tasks. A story
must express a role, a goal or capability, and a reason that explains the value.

Prefer this German template:

`Als <Rolle> möchte ich <Ziel/Fähigkeit>, damit <Nutzen/Wert>.`

Use a different template only when the project already has one. Keep the same
semantic parts: actor, intent, value.

## IREB-Aligned Quality Criteria

Check stories and acceptance criteria against these criteria:

- Eindeutig: Terms have one meaning in the project context.
- Verständlich: Stakeholders can understand the story without technical
  translation.
- Vollständig genug: The story has the necessary context for the current
  refinement level.
- Konsistent: No contradiction with other stories, requirements, business rules,
  or constraints.
- Prüfbar: Acceptance criteria allow a clear pass/fail decision.
- Realisierbar: The story does not demand impossible behavior under known
  constraints.
- Notwendig: The story contributes to an explicit user or business objective.
- Verfolgbar: Source, epic, requirement, or use case links are preserved when
  available.

## SOPHIST-Inspired Precision

Apply these language rules:

- Use active, simple sentences.
- Name the real actor, not generic "user", when a role is known.
- Use one process verb per story goal. Split "search and export" into separate
  stories unless the value only exists as one inseparable goal.
- Replace weak adjectives with measurable criteria.
- Avoid passive voice and solution bias unless a constraint requires it.
- Define domain terms or flag them as open questions when they are ambiguous.
- Distinguish requirements from assumptions, examples, and design ideas.

## INVEST Review

- Independent: Remove artificial dependencies. Keep real business or technical
  dependencies visible.
- Negotiable: Describe need and value, not the exact UI or architecture unless
  constrained.
- Valuable: The `damit` clause must matter to a user, customer, business,
  regulator, operator, or support role.
- Estimable: Add missing scope boundaries, data objects, or business rules.
- Small: Split stories that require multiple roles, workflows, objects, or
  outcomes.
- Testable: Add bullet-point criteria with observable results.

## Acceptance Criteria Patterns

Use Markdown bullet points for acceptance criteria:

- The export file contains order number, order date, status, and total amount.
- The system keeps cancelled reservations visible for 90 days.
- After the customer submits an order with items in the cart, the system creates
  an order confirmation with a unique order number.

Every criterion should identify:

- Preconditions or relevant state
- Trigger or user/system action
- Observable outcome
- Boundary, exception, or error behavior when important

## Splitting Patterns

Split large stories by:

- Workflow step: create, review, approve, archive
- Business rule: standard case, exception, escalation
- Data object: profile data, payment data, notification settings
- Channel or interface: web portal, API, email import
- Role: customer, support agent, administrator
- Quality level: minimal viable behavior first, advanced validation later

Do not split only by technical layer such as frontend/backend/database unless
the team explicitly manages technical enabler stories.

## Story Types

Functional user story:

`Als Sachbearbeiter möchte ich Kundenaufträge nach Status filtern, damit ich offene Aufträge schneller bearbeiten kann.`

Enabler story:

Use enabler stories sparingly. State the enabled user or business outcome:

`Als Entwicklungsteam möchten wir die Zahlungsanbieter-Sandbox anbinden, damit Zahlungsabläufe vor der Produktivschaltung testbar sind.`

Spike:

Use a spike only for learning. Add a timebox and decision output:

`Als Produktteam möchten wir die regulatorischen Anforderungen an Identitätsprüfung klären, damit wir den Registrierungsprozess belastbar schneiden können.`

## Output Example

Story index table:

| ID | Epic | Rolle | Titel | Datei | Priorität | Status |
|----|------|-------|-------|-------|-----------|--------|
| US-001 | Registrierung | Neukunde | Konto erstellen | [US-001-konto-erstellen.md](US-001-konto-erstellen.md) | High | Ready |

Story file `docs/user_stories/US-001-konto-erstellen.md`:

````markdown
# User Story: Konto erstellen

| Feld | Wert |
|------|------|
| ID | US-001 |
| Epic | Registrierung |
| Rolle | Neukunde |
| Priorität | High |
| Status | Ready |

## User Story

Als Neukunde möchte ich ein Konto mit E-Mail-Adresse erstellen, damit ich
Bestellungen dauerhaft verwalten kann.

## Akzeptanzkriterien

- Wenn der Neukunde die Registrierung mit einer noch nicht registrierten
  E-Mail-Adresse absendet, erstellt das System ein Kundenkonto.
- Nach erfolgreicher Registrierung sendet das System eine Bestätigungs-E-Mail
  an die angegebene E-Mail-Adresse.

## Traceability

- Quelle: FA-001

## Abhängigkeiten, Risiken und offene Fragen

- Keine bekannt.
````

## Review Smells

- Story has no `damit` clause or the benefit repeats the goal.
- Actor is "System" for a user-facing need.
- Acceptance criterion cannot be tested without reading source code.
- Story contains "and", "sowie", or a long comma chain in the goal.
- Criteria introduce major behavior not stated or implied by the story.
- Story depends on unknown terms, roles, or rules without an open question.
