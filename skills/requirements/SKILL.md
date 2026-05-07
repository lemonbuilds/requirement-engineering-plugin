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

Erstelle oder aktualisiere den Anforderungskatalog in
`docs/requirements/requirements.md` auf Basis von `docs/vision/vision.md`.

Das Dokument enthält funktionale Anforderungen, nicht-funktionale
Anforderungen und Randbedingungen in getrennten Markdown-Tabellen.

Wenn kein `docs/vision/vision.md` vorhanden ist, nutze stattdessen das
Briefing, die User-Nachricht oder vorhandene Projektnotizen als Quelle und
markiere Annahmen explizit.

## DO NOT

- Mische unterschiedliche Anforderungstypen in einer Tabelle
- Überspringe bei funktionalen Anforderungen das Satzschablonen-Format
- Verwende doppelte IDs über alle Anforderungstypen hinweg
- Lasse die Spalte `Status` leer
- Formuliere NFRs ohne messbaren Zielwert oder Schwellenwert
- Verstecke Konflikte zwischen Anforderungen; benenne sie explizit

### Funktionale Anforderungen (FA)

Funktionale Anforderungen beschreiben, was das System tun soll.
Formuliere funktionale Anforderungen nach dem FunktionsMASTER. Jede funktionale
Anforderung muss einen Betrachtungsgegenstand, eine rechtliche Verbindlichkeit,
genau ein Prozesswort und genau ein Objekt enthalten. Ergänze eine Bedingung
nur dann, wenn sie fachlich notwendig ist.

#### Rechtliche Verbindlichkeit

Verwende die Schlüsselwörter bewusst. Schreibe sie in den Anforderungen
normal klein, sofern sie nicht am Satzanfang stehen:

- `muss`: verpflichtende Anforderung
- `sollte`: gewünschte, nicht verpflichtende Anforderung
- `wird`: zukünftige Absicht, die später verpflichtend werden soll

#### FunktionsMASTER ohne Bedingung

1. Selbsttätige Systemaktivität
   `[Betrachtungsgegenstand] muss/sollte/wird [Objekt] [Prozesswort].`
2. Benutzerinteraktion
   `[Betrachtungsgegenstand] muss/sollte/wird [Akteur] die Möglichkeit bieten, [Objekt] zu [Prozesswort].`
3. Schnittstellenanforderung
   `[Betrachtungsgegenstand] muss/sollte/wird fähig sein, [Objekt] zu [Prozesswort].`

#### FunktionsMASTER mit Bedingung

Wenn eine Anforderung nur unter einer logischen oder zeitlichen Bedingung gilt,
stelle die Bedingung voran und verwende eine der folgenden Konjunktionen:

- `falls`: logische Bedingung oder fachlicher Fall
- `sobald`: auslösendes Ereignis oder Zeitpunkt
- `solange`: andauernder Zeitraum oder Zustand

Schablonen mit Bedingung:

1. Selbsttätige Systemaktivität
   `[Falls/Sobald/Solange Bedingung], muss/sollte/wird [Betrachtungsgegenstand] [Objekt] [Prozesswort].`
2. Benutzerinteraktion
   `[Falls/Sobald/Solange Bedingung], muss/sollte/wird [Betrachtungsgegenstand] [Akteur] die Möglichkeit bieten, [Objekt] zu [Prozesswort].`
3. Schnittstellenanforderung
   `[Falls/Sobald/Solange Bedingung], muss/sollte/wird [Betrachtungsgegenstand] fähig sein, [Objekt] zu [Prozesswort].`

#### Analysepflicht vor dem Schreiben

Prüfe für jede funktionale Anforderung:

- System: Welcher Betrachtungsgegenstand ist verantwortlich?
- Verbindlichkeit: Ist die Anforderung Pflicht, Wunsch oder zukünftige Absicht?
- Funktionstyp: selbsttätige Systemaktivität, Benutzerinteraktion oder Schnittstellenanforderung?
- Akteur oder Fremdsystem: Wer interagiert mit dem System oder liefert Informationen?
- Objekt: Was wird verarbeitet, angezeigt, gespeichert, übertragen oder geprüft?
- Prozesswort: Welches Vollverb beschreibt genau eine Funktion?
- Bedingung: Gilt die Anforderung immer oder nur falls, sobald oder solange etwas zutrifft?

Vermeide mehrere Prozesswörter in einer Anforderung. Teile zusammengesetzte
Aussagen wie "suchen und exportieren" in getrennte Anforderungen auf.

| ID     | Titel | Anforderung | Priority | Status |
|--------|-------|------------|----------|--------|
| FA-001 | Produktsuche | Der Onlineshop muss dem Kunden die Möglichkeit bieten, Produkte nach Namen zu suchen. | High | Open |
| FA-002 | Verfügbarkeitsprüfung | Sobald der Kunde ein Produkt in den Warenkorb legt, muss der Onlineshop die Lagerverfügbarkeit prüfen. | High | Open |
| FA-003 | Zahlungsfreigabe | Der Onlineshop muss fähig sein, Zahlungsfreigaben vom Zahlungsdienstleister zu empfangen. | High | Open |

### Nicht-funktionale Anforderungen (NFA)

Nicht-funktionale Anforderungen beschreiben Qualitätsmerkmale und müssen
messbar sein.

| ID      | Titel | Anforderung | Category | Priority | Status |
|---------|-------|-------------|----------|----------|--------|
| NFA-001 | Antwortzeit | 95 Prozent aller Seitenaufrufe müssen innerhalb von 2 Sekunden abgeschlossen sein. | Performance | High | Open |
| NFA-002 | Verfügbarkeit | Das System muss während der Servicezeit eine Verfügbarkeit von 99,9 Prozent pro Monat erreichen. | Availability | High | Open |

### Randbedingungen (RB)

Randbedingungen beschreiben Grenzen, Vorgaben oder Einschränkungen der Lösung.

| ID    | Titel | Randbedingung | Category | Priority | Status |
|-------|-------|---------------|----------|----------|--------|
| R-001 | Identity Management | Die Anwendung muss an das bestehende Identity-Management angebunden werden. | Technical | High | Open |
| R-002 | Go-live | Die erste produktive Version muss bis Ende Q2 bereitgestellt werden. | Schedule | High | Open |

## Reference

Siehe `references/requirements-reference.md` für ID-Präfixe, zulässige Werte
für `Priority` und `Status` sowie die vorgesehenen NFA- und
Randbedingungs-Kategorien. Verwende diese Werte konsistent und unverändert in
den Tabellen.

## Requirement Quality Checks

Jede Anforderung muss vor der Finalisierung diese Checks bestehen:

| Check | Regel | Schlechtes Beispiel | Gutes Beispiel |
|-------|-------|---------------------|----------------|
| Messbar | NFRs müssen eine Zahl oder einen Schwellenwert enthalten | System soll schnell sein | Seiten laden in unter 2 Sekunden |
| Singulär | Eine Tabellenzeile enthält genau eine Anforderung | System soll Login und Export bieten | Zwei getrennte Anforderungen |
| Eindeutig | Keine subjektiven oder unklaren Begriffe | Benutzerfreundliche Oberfläche | WCAG 2.1 AA für Kernabläufe |
| Testbar | Es muss ein Pass/Fail-Test ableitbar sein | System ist zuverlässig | 99,9 Prozent Verfügbarkeit über 30 Tage |
| Eindeutige IDs | Keine doppelten IDs in irgendeiner Tabelle | Zwei Mal FA-001 | Jede ID wird genau einmal verwendet |
| MASTER-konform | Funktionale Anforderungen enthalten System, Verbindlichkeit, Funktionstyp, Objekt und genau ein Prozesswort | Das System muss Bestellungen suchen und exportieren. | Das System muss dem Sachbearbeiter die Möglichkeit bieten, Bestellungen zu suchen. |

## Error Recovery

- Unvollständige Quelle: Liste fehlende Rollen, NFA-Kategorien oder Randbedingungen auf und bitte nur dann um Klärung, wenn eine belastbare Ausarbeitung sonst nicht möglich ist
- Mehrdeutige Anforderung: Formuliere sie in eine messbare Variante um und markiere den Schwellenwert als Annahme, falls keine Rückfrage möglich ist
- Widersprüchliche Anforderungen: Weise explizit auf den Konflikt hin, zum Beispiel zwischen Echtzeit-Anforderung und Batch-Randbedingung
- Fehlende Stakeholder-Rollen: Verwende vorläufig generische Rollen wie Benutzer, Administrator und System und kennzeichne sie zur späteren Validierung

## Workflow

1. Lies `docs/vision/vision.md` oder das vorhandene Projektbriefing
2. Identifiziere Rollen, Ziele, NFA-Kategorien und Randbedingungen
3. Erstelle `docs/requirements/` falls der Ordner nicht existiert
4. Erstelle den Dokumentkopf in `docs/requirements/requirements.md`
5. Analysiere funktionale Anforderungen nach System, Verbindlichkeit, Funktionstyp, Akteur/Fremdsystem, Objekt, Prozesswort und optionaler Bedingung
6. Erfasse funktionale Anforderungen nach dem FunktionsMASTER mit `Priority` und `Status`
7. Erfasse nicht-funktionale Anforderungen mit messbaren Zielwerten, `Category`, `Priority` und `Status`
8. Erfasse Randbedingungen mit `Category`, `Priority` und `Status`
9. Prüfe alle Anforderungen gegen die Quality Checks
10. Stelle sicher, dass keine ID doppelt vorkommt und keine `Status`-Zelle leer bleibt
11. Markiere Annahmen, Konflikte und offene Fragen explizit

## Standardstruktur für `docs/requirements/requirements.md`

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
