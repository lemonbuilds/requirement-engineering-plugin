# Use Case: [Name]

## ID

UC-XXX

## Name

[Beschreibender Name]

## Autoren

- [Name oder Rolle]

## Status

Draft | Review | Approved | Implemented | Tested | Done | Obsolete

## Auslösendes Ereignis

[Ereignis, das den Use Case startet]

## Akteure

- Primärakteur: [Rolle]
- Sekundärakteure: [Weitere beteiligte Rollen oder Systeme]

## Ziel

[Ziel, das der Primärakteur mit diesem Use Case erreichen will]

## Vorbedingungen

- [Bedingung, die vor Start des Use Cases erfüllt sein muss]

## Ergebnis

- [Beobachtbarer Zustand nach erfolgreichem Abschluss]
- [Relevanter Zustand bei Abbruch oder Fehler, falls zutreffend]

## Hauptszenario

1. [Aktion des Akteurs oder beobachtbare Systemreaktion]
2. [Nächster Schritt]
3. [Fortsetzen, bis das Ziel erreicht ist]

## Alternativszenarien

### A1: [Name des Alternativszenarios]

- Auslöser: [Bedingung, die dieses Szenario auslöst]
- Ablauf:
  1. [Schritt, der vom Hauptszenario abweicht]
  2. [Fortsetzung oder Rückkehr ins Hauptszenario]

## Ausnahmeszenarien

### E1: [Name des Ausnahmeszenarios]

- Auslöser: [Fehler, ungültige Eingabe, fehlende Berechtigung oder Abbruch]
- Ablauf:
  1. [Systemreaktion oder Akteurshandlung]
  2. [Endzustand oder Rückkehrpunkt]

## Ergänzende Punkte

- Annahme: [Explizite Annahme]
- Offene Frage: [Noch zu klärender Punkt]
- Quelle: [Anforderung, Use-Case-Diagramm oder Stakeholder-Hinweis]

## Business Rules

### BR-XXX: [Rule Name]

[Description of the business rule that applies to this use case]

## Reference

### Status Values

| Status | Description |
|--------|-------------|
| Draft | Initial version, still being written. |
| Review | Complete, awaiting stakeholder review. |
| Approved | Reviewed and approved for implementation. |
| Implemented | Implementation complete, pending testing. |
| Tested | All tests pass, pending final acceptance. |
| Done | Fully implemented, tested, and accepted. |
| Obsolete | No longer valid, superseded by another use case. |

### Step Writing Guidelines

| Do | Don't |
|----|-------|
| "User clicks Save button" | "User triggers onClick handler" |
| "System validates the email format" | "System runs regex `/^[\\w]+@[\\w]+$/`" |
| "System displays error message" | "System throws ValidationException" |
| "User enters check-in date" | "User populates dateField component" |
| "System stores the reservation" | "System executes `INSERT INTO reservations...`" |
