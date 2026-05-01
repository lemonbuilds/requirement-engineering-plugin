# Requirements Reference

## ID Prefixes

| Prefix | Typ | Beispiel |
|--------|-----|----------|
| FA | Funktionale Anforderung | FA-001 |
| NFA | Nicht-funktionale Anforderung | NFA-001 |
| R | Randbedingung | R-001 |

Verwende pro Anforderungstyp fortlaufende, eindeutige IDs. IDs duerfen ueber
alle Tabellen hinweg nicht doppelt vorkommen.

## Priorität

| Priorität | Beschreibung |
|----------|--------------|
| High | Muss vorhanden sein. Kernfunktionalitaet oder kritische Qualitaet. |
| Medium | Sollte vorhanden sein. Wichtig, aber das System funktioniert auch ohne. |
| Low | Optional. Kann in spaetere Releases verschoben werden. |

## Status

| Status | Beschreibung |
|--------|--------------|
| Open | Anforderung ist definiert, aber noch nicht umgesetzt. |
| In Progress | Anforderung befindet sich aktuell in Umsetzung. |
| Implemented | Umsetzung ist abgeschlossen, Verifikation steht noch aus. |
| Verified | Anforderung wurde getestet und bestaetigt. |
| Deferred | Anforderung wurde auf einen spaeteren Release verschoben. |
| Rejected | Anforderung wurde aus dem Scope entfernt. |

## Qualitätsanforderungen Kategorien

| Category | Beschreibung |
|----------|--------------|
| Performance | Geschwindigkeit, Durchsatz, Antwortzeit |
| Scalability | Faehigkeit, Wachstum und Laststeigerung zu bewaeltigen |
| Availability | Verfuegbarkeit, Ausfallsicherheit |
| Security | Authentifizierung, Autorisierung, Verschluesselung |
| Usability | Nutzererlebnis, Barrierefreiheit |
| Maintainability | Codequalitaet, Dokumentation, Modularitaet |
| Portability | Plattformunabhaengigkeit, Flexibilitaet beim Deployment |

## Randbedingungen Kategorien

| Category | Beschreibung |
|----------|--------------|
| Technical | Technologie-Stack, Plattformen, Integrationen |
| Business | Budget, Ressourcen, organisatorische Vorgaben |
| Schedule | Deadlines, Meilensteine, Zeitvorgaben |
| Regulatory | Rechtliche Vorgaben, Compliance, Branchenstandards |
| Operational | Betrieb, Wartung, Support-Anforderungen |

## Qualitätsrichtlinien

- Jede Anforderung beschreibt genau einen Sachverhalt
- Jede NFR ist messbar formuliert
- Jede funktionale Anforderung nutzt eine der definierten Satzschablonen
- Jede Tabellenzeile hat eine gefuellte Prioritaet und einen gefuellten Status
- Konflikte, Annahmen und offene Fragen werden ausserhalb der Tabellen explizit dokumentiert
