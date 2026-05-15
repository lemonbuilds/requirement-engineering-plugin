---
name: use-case-spec
description: >
  Creates detailed German use case specification documents with ID, name,
  authors, status, triggering event, actors, goal, preconditions, result, main
  scenario, alternative scenarios, exception scenarios, supplementary points,
  business rules, and reference guidance. Use when the user asks to "write a use
  case", "specify a use case", "document system behavior", "define scenarios",
  "write a functional spec", or mentions use case specification.
---

# Use Case Specification

## Purpose

Dieser Skill erstellt oder aktualisiert genau eine detaillierte
Use-Case-Beschreibung für $ARGUMENTS in `docs/use_cases/`.

Schreibe Use-Case-Beschreibungen standardmässig auf Deutsch, ausser der User
fordert ausdrücklich eine andere Sprache.

## Instructions

Erstelle oder aktualisiere genau eine Use-Case-Beschreibung für $ARGUMENTS in
`docs/use_cases/`.

Verwende [templates/use-case.md](templates/use-case.md) als verbindliche
Struktur.

Benenne die Ausgabedatei `UC-XXX-short-name.md`, zum Beispiel
`docs/use_cases/UC-012-bestellung-im-kundenauftrag-abschliessen.md`.

Jede Use-Case-Beschreibung muss eine vollständige Interaktion zwischen einem
oder mehreren Akteuren und dem System beschreiben, um ein Ziel zu erreichen.

Nutze `docs/requirements/requirements.md` und
`docs/use_case_diagramm/use_cases.puml` als Quellen, wenn beide Dateien
existieren. Wenn eine Quelle fehlt, arbeite mit der vorhandenen Quelle weiter
und kennzeichne Annahmen ausdrücklich.

## DO NOT

- Vage oder unvollständige Szenarien schreiben
- Nummerierte Schritte im `Hauptszenario` weglassen
- Relevante Alternativ- oder Ausnahmeszenarien weglassen
- `Ergebnis` undefiniert lassen
- Mehrere Use Cases in einem Dokument vermischen
- Technische Implementierungsdetails in Ablaufschritten verwenden

## Workflow

1. Lies das Anforderungsdokument und das Use-Case-Diagramm
2. Identifiziere genau den einen zu dokumentierenden Use Case
3. Erstelle `docs/use_cases/`, falls der Ordner nicht existiert
4. Fülle die Pflichtabschnitte in dieser Reihenfolge: ID, Name, Autoren, Status,
   Auslösendes Ereignis, Akteure, Ziel, Vorbedingungen, Ergebnis,
   Hauptszenario, Alternativszenarien, Ausnahmeszenarien, Ergänzende Punkte,
   Business Rules, Reference
5. Definiere Vorbedingungen, die vor Start des Use Cases erfüllt sein müssen
6. Schreibe das `Hauptszenario` als nummerierte Interaktion zwischen Akteur und System
7. Identifiziere `Alternativszenarien` für optionale oder gültige Varianten
8. Identifiziere `Ausnahmeszenarien` für Fehler, ungültige Eingaben, fehlende
   Berechtigungen, nicht verfügbare Systeme oder abgebrochene Abläufe
9. Beschreibe das `Ergebnis` als beobachtbaren Zustand nach erfolgreichem
   Abschluss und relevante Zustände bei Fehler oder Abbruch
10. Dokumentiere Annahmen, Hinweise, Traceability und offene Fragen unter
    `Ergänzende Punkte`
11. Dokumentiere fachliche Regeln separat unter `Business Rules`
12. Behalte Statuswerte und Schreibregeln unter `Reference` bei
13. Prüfe die Beschreibung auf Vollständigkeit, Klarheit und Nachvollziehbarkeit

## Quality Checks

- Der Use Case hat genau eine `ID`
- Die Abschnitte folgen der verbindlichen deutschen Struktur und Benennung
- `Status` verwendet einen der Werte aus `Reference`
- `Auslösendes Ereignis`, `Akteure`, `Ziel`, `Vorbedingungen` und `Ergebnis`
  sind konkret und überprüfbar
- Das `Hauptszenario` ist nummeriert und erreicht das Ziel des Akteurs
- Alternativ- und Ausnahmeszenarien nennen einen klaren Auslöser und einen
  Rücksprungpunkt oder Endzustand
- Ergänzende Punkte sind konkret und für diesen Use Case relevant
- Business Rules stehen in einem separaten Abschnitt und sind nicht unter
  `Ergänzende Punkte` vermischt
- Schritte beschreiben beobachtbares Verhalten, keine Implementierungsdetails

## Example Use Case

# Use Case: Reservierung erstellen

## ID

UC-001

## Name

Reservierung erstellen

## Autoren

- Requirements Engineer

## Status

Draft

## Auslösendes Ereignis

Ein Rezeptionsmitarbeiter startet die Erstellung einer neuen Reservierung.

## Akteure

- Primärakteur: Rezeptionsmitarbeiter
- Sekundärakteur: Gast

## Ziel

Der Rezeptionsmitarbeiter erstellt eine verbindliche Zimmerreservierung für
einen Gast.

## Vorbedingungen

- Der Rezeptionsmitarbeiter ist am System angemeldet.
- Für den gewünschten Zeitraum ist mindestens eine Zimmerkategorie verfügbar.

## Ergebnis

- Die Reservierung ist mit dem Status `Bestätigt` gespeichert.
- Die Verfügbarkeit ist für den reservierten Zeitraum aktualisiert.
- Der Gast erhält eine Reservierungsbestätigung.

## Hauptszenario

1. Der Rezeptionsmitarbeiter wählt die Funktion `Neue Reservierung`.
2. Das System zeigt das Reservierungsformular an.
3. Der Rezeptionsmitarbeiter erfasst die Kontaktdaten des Gasts.
4. Der Rezeptionsmitarbeiter wählt Anreise- und Abreisedatum.
5. Das System zeigt verfügbare Zimmerkategorien für den Zeitraum an.
6. Der Rezeptionsmitarbeiter wählt eine Zimmerkategorie aus.
7. Das System berechnet den Gesamtpreis.
8. Der Rezeptionsmitarbeiter bestätigt die Reservierung.
9. Das System speichert die Reservierung und zeigt eine Bestätigungsnummer an.

## Alternativszenarien

### A1: Gast existiert bereits

- Auslöser: Die E-Mail-Adresse des Gasts ist bereits gespeichert.
- Ablauf:
  1. Das System zeigt die vorhandenen Gastdaten an.
  2. Der Rezeptionsmitarbeiter bestätigt oder aktualisiert die Gastdaten.
  3. Der Use Case wird in Schritt 4 des Hauptszenarios fortgesetzt.

## Ausnahmeszenarien

### E1: Keine Zimmer verfügbar

- Auslöser: Für den gewählten Zeitraum ist keine Zimmerkategorie verfügbar.
- Ablauf:
  1. Das System zeigt eine Meldung zur fehlenden Verfügbarkeit an.
  2. Der Rezeptionsmitarbeiter passt den Zeitraum an oder bricht den Vorgang ab.
  3. Bei angepasstem Zeitraum wird der Use Case in Schritt 4 fortgesetzt,
     andernfalls endet der Use Case ohne Reservierung.

## Ergänzende Punkte

- Annahme: Bestätigungsnachrichten werden per E-Mail versendet.
- Offene Frage: Ob Anzahlungen für längere Aufenthalte erforderlich sind.
- Quelle: FA-001

## Business Rules

### BR-001: Mindestaufenthalt

Reservierungen müssen mindestens eine Übernachtung umfassen.

### BR-002: Vorausbuchungsfrist

Reservierungen dürfen höchstens 365 Tage im Voraus erstellt werden.

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
