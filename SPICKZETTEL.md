# Spickzettel Implantat-Check · 8 Stunden

Acht Blöcke. Jeden Prompt in Claude Code kopieren, das Ergebnis prüfen, dann weiter. Der Plan beginnt mit der sicheren Variante (Eingabe per Text) und nimmt das Foto erst danach dazu.

| Block | Zeit | Thema |
|---|---|---|
| 1 | 30 Min. | Setup |
| 2 | 45 Min. | Vorgaben: Regeln für Abgleich und Bestellung |
| 3 | 60 Min. | Siebliste anzeigen, Verbrauch eingeben |
| 4 | 45 Min. | Abgleich und Bestellliste |
| 5 | 75 Min. | KI liest den Verbrauch aus Freitext |
| 6 | 75 Min. | KI liest den Verbrauch vom Foto |
| 7 | 60 Min. | Testen und Robustheit |
| 8 | 60 Min. | Ergebnis, Demo, Pitch |

Bleiben 30 Minuten Puffer.

## Block 1 · Setup
Schlüssel eintragen: `.env.example` zu `.env` kopieren und den ausgehändigten Schlüssel eintragen (im Texteditor, nicht über Claude Code).
```
Lies README.md und CLAUDE.md und sieh dir daten/siebliste_soll.csv und daten/testfall_01_verbrauch.md an. Prüfe, ob Node.js ab Version 20 installiert ist, und lege die leeren Ordner prompt und ergebnisse an. Beschreibe mir in fünf Sätzen, was die Siebliste enthält.
```
**Fertig, wenn:** Node passt, `.env` existiert, alle kennen die Testdaten.

## Block 2 · Vorgaben (ohne Code)
In `spec.md` festlegen:
- Wann wird nachbestellt? (z. B. jedes verbrauchte Teil wird ersetzt, oder erst unter einem Mindestbestand)
- Was passiert bei Teilen, die nicht auf der Siebliste stehen?
- Was passiert bei unklaren Angaben? (Vorschlag: nie raten, als „bitte prüfen“ markieren)
- Wer gibt die Bestellliste frei? Die App bestellt nie selbst.

**Fertig, wenn:** die Regeln von zwei Personen gegengelesen sind, idealerweise eine davon aus der OP-Pflege.

## Block 3 · Siebliste anzeigen, Verbrauch eingeben
```
Baue die Grundversion: server.js und public/index.html. Die Seite lädt daten/siebliste_soll.csv und zeigt sie als Tabelle mit Artikelnummer, Bezeichnung, Größe und Soll-Menge. In jeder Zeile gibt es Plus- und Minus-Tasten für „verbraucht“. Eine andere CSV-Datei im selben Format lässt sich hochladen. Der Hinweis aus CLAUDE.md ist immer sichtbar.
```
**Fertig, wenn:** der Verbrauch aus Testfall 01 von Hand eingetragen werden kann.

## Block 4 · Abgleich und Bestellliste
```
Ergänze den Button „Bestellliste erstellen“. Berechne im Programmcode (ohne KI) je Artikel Soll minus Verbrauch und wende die Regeln aus spec.md an. Zeige die Bestellliste als Tabelle mit Artikelnummer, Bezeichnung, Größe und Bestellmenge, dazu eine Liste „bitte prüfen“ für Unklares. Buttons „Als CSV speichern“ und „Drucken“.
```
**Fertig, wenn:** die Bestellliste für Testfall 01 genau der erwarteten Liste in `daten/testfall_01_verbrauch.md` entspricht.

## Block 5 · KI liest den Verbrauch aus Freitext
```
Ergänze ein Textfeld „Verbrauch als Freitext“ (z. B. aus dem OP-Bericht). Ein Endpunkt /api/verbrauch schickt Text und Siebliste an die Anthropic Messages API. Die KI ordnet jede Angabe einer Artikelnummer der Siebliste zu und antwortet als JSON: artikelnummer, menge, originaltext, sicher (ja/nein). Was sich nicht eindeutig zuordnen lässt, kommt in „bitte prüfen“. Die Mengen rechnet weiterhin der Programmcode. Schlüssel und Modell kommen nur aus .env.
```
**Fertig, wenn:** der Freitext aus Testfall 01 dieselbe Bestellliste ergibt wie die Eingabe von Hand.

## Block 6 · KI liest den Verbrauch vom Foto
Zwei Wege zu Testbildern: Fotos echter Schraubenracks liegen in `daten/hospi_orthopaedie/` (Ordner, deren Name auf `Set` endet). Oder selbst herstellen: Siebliste als Tabelle ausdrucken, verbrauchte Positionen von Hand durchstreichen, fotografieren.
```
Ergänze den Button „Sieb fotografieren / Bild wählen“. Das Bild wird im Browser verkleinert und an /api/verbrauch-foto geschickt. Die KI gibt im selben JSON-Format zurück, welche Positionen fehlen oder durchgestrichen sind, und nennt, was sie nicht erkennen konnte. Das Ergebnis wird vor dem Abgleich zur Bestätigung angezeigt und lässt sich korrigieren. Das Bild wird nicht gespeichert.
```
**Fertig, wenn:** ein Foto erkannt und vor dem Abgleich bestätigt werden kann.

## Block 7 · Testen und Robustheit
- Testfall 01 auf allen drei Wegen (Hand, Freitext, Foto) durchspielen, Abweichungen notieren
- Einen zweiten Testfall selbst schreiben und als Blind-Fall beiseitelegen
```
Mache die App robuster: verständliche Meldungen bei ungültiger CSV, fehlendem Netz und Zeitüberschreitung. Verbrauch größer als Soll wird als Fehler markiert. Unbekannte Artikel landen in „bitte prüfen“.
```
**Fertig, wenn:** drei dokumentierte Durchläufe vorliegen.

## Block 8 · Ergebnis, Demo, Pitch
- Blind-Fall **einmal** laufen lassen, Ergebnis nicht nachbessern
- `ergebnis.md`: Aufbau, Trefferzahl je Eingabeweg, Limitationen (erfundene Siebliste, selbst gemachte Fotos)
- Demo zweimal durchspielen, Screenshots als Backup
- Pitch: Problem, Live-Demo, wie getestet, nächste Schritte
