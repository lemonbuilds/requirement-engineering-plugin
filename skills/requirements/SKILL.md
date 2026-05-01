---
name: requirements
description: >
  Erfasst, strukturiert und dokumentiert Software-Anforderungen in einem
  Anforderungskatalog mit funktionalen Anforderungen (Satzschablonen),
  messbaren nicht-funktionalen Anforderungen und Randbedingungen. Verwenden,
  wenn der User Anforderungen schreiben, ein PRD erstellen, Anforderungen
  sammeln, Feature-Spezifikationen dokumentieren, User Stories formulieren,
  Qualitätsanforderungen definieren oder Randbedingungen auflisten möchte.
---

# Requirements Engineer

## Zweck

Diese Skill hilft dabei, unscharfe Produktideen in einen strukturierten,
nachvollziehbaren und umsetzbaren Anforderungskatalog zu überführen.

Arbeite standardmässig auf Deutsch, ausser der User wünscht explizit eine
andere Sprache.

## Instructions

Erstelle oder aktualisiere den Anforderungskatalog in `docs/requirements.md`
auf Basis von `docs/vision.md`.

Das Dokument enthält funktionale Anforderungen, nicht-funktionale
Anforderungen und Randbedingungen in getrennten Markdown-Tabellen.

Wenn kein `docs/vision.md` vorhanden ist, nutze stattdessen das Briefing,
die User-Nachricht oder vorhandene Projektnotizen als Quelle und markiere
Annahmen explizit.

## DO NOT

- Mische unterschiedliche Anforderungstypen in einer Tabelle
- Überspringe bei funktionalen Anforderungen das Satzschablonen-Format
- Verwende doppelte IDs über alle Anforderungstypen hinweg
- Lasse die Spalte `Status` leer
- Formuliere NFRs ohne messbaren Zielwert oder Schwellenwert
- Verstecke Konflikte zwischen Anforderungen; benenne sie explizit

### Funktionale Anforderungen (FA)

Funktionale Anforderungen beschreiben, was das System tun soll.
Verwende immer eine der folgenden Satzschablonen, um die Anforderungen klar und konsistent zu formulieren:

1. Die selbstständige Systemaktivität
   `[Betrachtungsgegenstand] muss/sollte/wird [Objekt] [Verb].`
2. Die Benutzerinteraktion
   `[Betrachtungsgegenstand] muss/sollte/wird [wem?|was?] die Möglichkeit bieten [Objekt] zu [Verb].`
3. Die Schnittstellenanforderung
   `[Betrachtungsgegenstand] muss/sollte/wird fähig sein [Objekt] zu [Verb].`

| ID     | Titel | Anforderung | Priority | Status |
|--------|-------|------------|----------|--------|
| FR-001 | Beispiel | Der Onlineshop muss dem Benutzer die Möglichkeit bieten, Produkte von A-Z zu sortieren. | High | Open |
| FR-002 | Beispiel | Das Bibliothekssystem muss dem Bibliothekar die Möglichkeit
bieten, die Kundendaten zu drucken. | Medium | Open |

### Nicht-funktionale Anforderungen (NFA)

Nicht-funktionale Anforderungen beschreiben Qualitätsmerkmale und müssen
messbar sein.

| ID      | Titel | Anforderung | Category | Priority | Status |
|---------|-------|-------------|----------|----------|--------|
| NFR-001 | Beispiel | 95 Prozent aller Seitenaufrufe müssen innerhalb von 2 Sekunden abgeschlossen sein. | Performance | High | Open |
| NFR-002 | Beispiel | Das System muss während der Servicezeit eine Verfügbarkeit von 99,9 Prozent pro Monat erreichen. | Availability | High | Open |

### Randbedingungen (RB)

Randbedingungen beschreiben Grenzen, Vorgaben oder Einschränkungen der Lösung.

| ID    | Titel | Randbedingung | Category | Priority | Status |
|-------|-------|---------------|----------|----------|--------|
| RB-001 | Beispiel | Die Anwendung muss an das bestehende Identity-Management angebunden werden. | Technical | High | Open |
| RB-002 | Beispiel | Die erste produktive Version muss bis Ende Q2 bereitgestellt werden. | Schedule | High | Open |

## Reference

Siehe `REFERENCE.md` für ID-Präfixe, zulässige Werte für `Priority` und
`Status` sowie die vorgesehenen NFR- und Randbedingungs-Kategorien. Verwende diese
Werte konsistent und unverändert in den Tabellen.

## Requirement Quality Checks

Jede Anforderung muss vor der Finalisierung diese Checks bestehen:

| Check | Regel | Schlechtes Beispiel | Gutes Beispiel |
|-------|-------|---------------------|----------------|
| Messbar | NFRs müssen eine Zahl oder einen Schwellenwert enthalten | System soll schnell sein | Seiten laden in unter 2 Sekunden |
| Singulär | Eine Tabellenzeile enthält genau eine Anforderung | System soll Login und Export bieten | Zwei getrennte Anforderungen |
| Eindeutig | Keine subjektiven oder unklaren Begriffe | Benutzerfreundliche Oberfläche | WCAG 2.1 AA für Kernabläufe |
| Testbar | Es muss ein Pass/Fail-Test ableitbar sein | System ist zuverlässig | 99,9 Prozent Verfügbarkeit über 30 Tage |
| Eindeutige IDs | Keine doppelten IDs in irgendeiner Tabelle | Zwei Mal FR-001 | Jede ID wird genau einmal verwendet |

## Error Recovery

- Unvollständige Quelle: Liste fehlende Rollen, NFR-Kategorien oder Randbedingungen auf und bitte nur dann um Klärung, wenn eine belastbare Ausarbeitung sonst nicht möglich ist
- Mehrdeutige Anforderung: Formuliere sie in eine messbare Variante um und markiere den Schwellenwert als Annahme, falls keine Rückfrage möglich ist
- Widersprüchliche Anforderungen: Weise explizit auf den Konflikt hin, zum Beispiel zwischen Echtzeit-Anforderung und Batch-Randbedingung
- Fehlende Stakeholder-Rollen: Verwende vorläufig generische Rollen wie Benutzer, Administrator und System und kennzeichne sie zur späteren Validierung

## Workflow

1. Lies `docs/vision.md` oder das vorhandene Projektbriefing
2. Identifiziere Rollen, Ziele, NFR-Kategorien und Randbedingungen
3. Erstelle den Dokumentkopf in `docs/requirements.md`
4. Erfasse funktionale Anforderungen mit Satzschablonen mit `Priority` und `Status`
5. Erfasse nicht-funktionale Anforderungen mit messbaren Zielwerten, `Category`, `Priority` und `Status`
6. Erfasse Randbedingungen mit `Category`, `Priority` und `Status`
7. Prüfe alle Anforderungen gegen die Quality Checks
8. Stelle sicher, dass keine ID doppelt vorkommt und keine `Status`-Zelle leer bleibt
9. Markiere Annahmen, Konflikte und offene Fragen explizit

## Standardstruktur für `docs/requirements.md`

Das Ergebnis soll standardmässig diese Abschnitte enthalten:

1. Titel und Kontext
2. In Scope
3. Out of Scope
4. Funktionale Anforderungen
5. Nicht-funktionale Anforderungen
6. Randbedingungen
7. Risiken
8. Offene Fragen

## Zusatzhinweise

- Wenn der User ausdrücklich User Stories, NFRs, Risiken oder offene Fragen verlangt, nimm diese immer auf
- Wenn der User keine Quelle liefert, erstelle einen ersten Entwurf auf Basis plausibler Annahmen und kennzeichne diese sauber
- Halte die Formulierungen konkret, testbar und fachlich nachvollziehbar
- Bevorzuge klare deutsche Begriffe; übernimm englische Labels nur, wenn sie projektweit etabliert sind

## Trigger-Beispiele

Diese Skill ist passend bei Formulierungen wie:

- `Schreibe Anforderungen`
- `Erstelle ein PRD`
- `Sammle Anforderungen für dieses Feature`
- `Dokumentiere die Feature-Spezifikation`
- `Formuliere Anforderungen gemäß der Satzschablonen`
- `Definiere NFRs`
- `Liste Randbedingungen`
- `requirements catalog`
- `requirements analysis`
- `product requirements document`
- `feature specification`
