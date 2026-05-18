---
name: use-case-spec
description: >
  Creates detailed German use case specification documents with ID, name,
  authors, status, triggering event, actors, goal, preconditions, result, main
  scenario, alternative scenarios, exception scenarios, supplementary points,
  and business rules. Use when the user asks to "write a use case", "specify a
  use case", "document system behavior", "define scenarios", "write a
  functional spec", or mentions use case specification.
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

Verwende [assets/use-case.md](assets/use-case.md) als verbindliche
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
   Business Rules
5. Definiere Vorbedingungen, die vor Start des Use Cases erfüllt sein müssen
6. Schreibe das `Hauptszenario` als nummerierte Interaktion zwischen Akteur und System
7. Identifiziere `Alternativszenarien` für optionale oder gültige Varianten
8. Identifiziere `Ausnahmeszenarien` für Fehler, ungültige Eingaben, fehlende
   Berechtigungen, nicht verfügbare Systeme oder abgebrochene Abläufe
9. Beschreibe das `Ergebnis` als beobachtbaren Zustand nach erfolgreichem
   Abschluss und relevante Zustände bei Fehler oder Abbruch
10. Dokumentiere Abgrenzungen, Annahmen, offene Fragen und Quellen unter
    `Ergänzende Punkte` in den gleichnamigen Unterüberschriften
11. Dokumentiere fachliche Regeln separat unter `Business Rules`
12. Verwende die Statuswerte und Schreibregeln aus
    `references/use-case-reference.md`, aber gib sie nicht als eigenen
    `Reference`-Abschnitt im Use-Case-Dokument aus
13. Prüfe die Beschreibung auf Vollständigkeit, Klarheit und Nachvollziehbarkeit

## Quality Checks

- Der Use Case hat genau eine `ID`
- Die Abschnitte folgen der verbindlichen deutschen Struktur und Benennung
- `Status` verwendet genau einen dieser Werte: `Draft`, `Review`, `Approved`,
  `Implemented`, `Tested`, `Done`, `Obsolete`
- `Auslösendes Ereignis`, `Akteure`, `Ziel`, `Vorbedingungen` und `Ergebnis`
  sind konkret und überprüfbar
- Das `Hauptszenario` ist nummeriert und erreicht das Ziel des Akteurs
- Alternativ- und Ausnahmeszenarien nennen einen klaren Auslöser und einen
  Rücksprungpunkt oder Endzustand
- `Ergänzende Punkte` enthält genau die Unterüberschriften `Abgrenzungen`,
  `Annahmen`, `Offene Fragen` und `Quellen`; Einträge darunter stehen als
  Stichpunkte ohne Präfixe wie `Annahme:`, `Offene Frage:` oder `Quelle:`
- Business Rules stehen in einem separaten Abschnitt und sind nicht unter
  `Ergänzende Punkte` vermischt
- Schritte beschreiben beobachtbares Verhalten, keine Implementierungsdetails
- Das generierte Use-Case-Dokument enthält keinen `Reference`-Abschnitt mit
  Statuswerten oder Schreibregeln

## Reference

Siehe `references/use-case-reference.md` für zulässige Statuswerte und
Schreibregeln für Szenarioschritte. Verwende diese Regeln intern beim Schreiben
der Use-Case-Beschreibung, aber übernimm die Reference-Tabellen nicht in das
generierte Use-Case-Dokument.
