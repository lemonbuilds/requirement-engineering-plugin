# Use Case Reference

## Status

| Status | Beschreibung |
|--------|--------------|
| Draft | Erste Version, noch in Bearbeitung. |
| Review | Vollständig beschrieben und bereit zur fachlichen Prüfung. |
| Approved | Fachlich geprüft und für Umsetzung oder Planung freigegeben. |
| Implemented | Umsetzung ist abgeschlossen, Verifikation steht noch aus. |
| Tested | Tests sind abgeschlossen, finale Abnahme steht noch aus. |
| Done | Vollständig umgesetzt, getestet und abgenommen. |
| Obsolete | Nicht mehr gültig oder durch einen anderen Use Case ersetzt. |

## Schreibregeln für Szenarioschritte

| Gut | Vermeiden |
|-----|-----------|
| "Der Benutzer wählt Speichern." | "Der Benutzer triggert den onClick-Handler." |
| "Das System prüft das E-Mail-Format." | "Das System führt Regex `/^[\\w]+@[\\w]+$/` aus." |
| "Das System zeigt eine Fehlermeldung an." | "Das System wirft eine ValidationException." |
| "Der Benutzer erfasst das Anreisedatum." | "Der Benutzer befüllt die dateField-Komponente." |
| "Das System speichert die Reservierung." | "Das System führt `INSERT INTO reservations...` aus." |

## Qualitätsrichtlinien

- Verwende im Abschnitt `Status` genau einen Statuswert aus der Tabelle.
- Schreibe Szenarioschritte als beobachtbare Akteur- oder Systemhandlungen.
- Vermeide technische Implementierungsdetails wie Handler, Regex, Exceptions,
  Datenbankbefehle oder interne Komponenten.
- Gib diese Referenztabellen nicht im generierten Use-Case-Dokument aus.
