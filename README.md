# 08 · Implantat-Check

> Prototyp für den AKKI Hackathon 2026. Nur Testdaten, kein Medizinprodukt, kein Ersatz für die Zählkontrolle im OP.

**Bereich:** OP

**Idee:** Die KI gleicht das verwendete OP-Sieb und Material mit der Planung ab und erstellt automatisch eine Bestell- und Nachschubliste für Implantate und Schrauben.

## Warum
Der Abgleich von Hand zwischen Sieb, OP-Bericht und Nachbestellung ist fehleranfällig und zeitaufwändig.

## Was am Ende stehen soll
- Erfassung des verwendeten Materials (Foto vom Sieb oder Eingabe)
- Abgleich mit der Planungs- oder Sieb-Liste
- Automatische Erstellung einer Bestell- und Nachschubliste

**Erfolgskriterium:** Für mindestens einen Testfall liegt eine korrekte Bestellliste vor.

## So startet ihr
1. Oben auf **Code → Download ZIP** klicken und entpacken.
2. Im entpackten Ordner ein Terminal öffnen und `claude` eingeben.
3. `SPICKZETTEL.md` öffnen und mit Block 1 beginnen.
4. Zwischenstände hochladen: siehe `GITHUB_ANLEITUNG.md`.

## Was in diesem Repo liegt
| Datei | Wofür |
|---|---|
| `SPICKZETTEL.md` | Umsetzungsplan für 8 Stunden, Block für Block |
| `CLAUDE.md`, `AGENTS.md` | Dieselben Regeln für den Coding-Agenten (Claude Code liest die erste, Codex die zweite Datei) |
| `GITHUB_ANLEITUNG.md` | Eure Arbeit auf GitHub bringen, ohne Git-Kenntnisse |
| `daten/QUELLEN.md` | Offene Bilddatensätze und Hinweise zu den Testdaten |
| `daten/siebliste_soll.csv` | Frei erfundene Soll-Bestückung eines Siebs |
| `daten/testfall_01_verbrauch.md` | Frei erfundener OP-Verbrauch mit erwarteter Bestellliste |
| `daten/instrumentenbilder/` | 36 Fotos von 18 chirurgischen Instrumenten mit `klassen.csv` |

## Stolpersteine
- Beim Foto-Ansatz die Bildqualität beachten: Schrauben im Rack sehen sich sehr ähnlich
- Mit Testdaten arbeiten statt mit einer echten Implantat-Datenbank
- Das Rechnen (Soll minus Ist) gehört in den Programmcode, nicht in die KI

## Für Erfahrene
- Foto des Schraubenracks: Die KI zählt leere Plätze je Reihe
- Verbrauch direkt aus einem diktierten OP-Bericht herauslesen
- Bestellliste als CSV oder E-Mail-Entwurf ausgeben
