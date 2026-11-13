# Testfall 01: Verbrauch und erwartete Bestellliste (frei erfunden)

**Achtung:** Siebliste, Artikelnummern und Fall sind für den Hackathon ausgedacht. Es gibt keinen Bezug zu einem echten Hersteller oder Eingriff.

**Regel für diesen Testfall:** Jedes verbrauchte oder verworfene Teil wird 1:1 nachbestellt.

## Verbrauch als Liste
| Artikelnummer | Bezeichnung | Größe | Verbraucht |
|---|---|---|---|
| DEMO-PL-01 | Radiusplatte palmar winkelstabil links schmal | 3-Loch | 1 |
| DEMO-WS-16 | Winkelstabile Schraube 2,4 mm | 16 mm | 2 |
| DEMO-WS-18 | Winkelstabile Schraube 2,4 mm | 18 mm | 3 (2 implantiert, 1 verworfen) |
| DEMO-WS-20 | Winkelstabile Schraube 2,4 mm | 20 mm | 2 |
| DEMO-KS-14 | Kortikalisschraube 2,4 mm | 14 mm | 1 |
| DEMO-KD-12 | Kirschner-Draht | 1,2 mm | 2 |

## Derselbe Verbrauch als Freitext (für Block 5)
```
Palmare Platte links, die schmale mit drei Loch. Distal sechs winkelstabile Schrauben: zweimal 16, zweimal 18, zweimal 20. Eine 18er ist runtergefallen und wurde verworfen. Im Schaft eine Kortikalisschraube 14 Millimeter. Zwei K-Drähte 1,2 zur temporären Fixierung, danach entfernt und entsorgt. Außerdem eine Unterlegscheibe verwendet.
```

## Erwartete Bestellliste
| Artikelnummer | Bezeichnung | Größe | Bestellmenge |
|---|---|---|---|
| DEMO-PL-01 | Radiusplatte palmar winkelstabil links schmal | 3-Loch | 1 |
| DEMO-WS-16 | Winkelstabile Schraube 2,4 mm | 16 mm | 2 |
| DEMO-WS-18 | Winkelstabile Schraube 2,4 mm | 18 mm | 3 |
| DEMO-WS-20 | Winkelstabile Schraube 2,4 mm | 20 mm | 2 |
| DEMO-KS-14 | Kortikalisschraube 2,4 mm | 14 mm | 1 |
| DEMO-KD-12 | Kirschner-Draht | 1,2 mm | 2 |

**Erwartet unter „bitte prüfen“:** Unterlegscheibe (steht nicht auf der Siebliste).

## Prüffragen
- Stimmen alle sechs Positionen und Mengen?
- Wurde die verworfene 18er-Schraube mitgezählt?
- Landet die Unterlegscheibe in „bitte prüfen“, statt einer Artikelnummer zugeordnet zu werden?
