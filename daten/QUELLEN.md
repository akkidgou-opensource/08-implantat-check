# Datenquellen Implantat-Check

## Im Repo
| Datei oder Ordner | Inhalt | Herkunft und Lizenz |
|---|---|---|
| `hospi_orthopaedie/` | Rund 860 Fotos echter orthopädisch-unfallchirurgischer Siebe und Implantate, geordnet nach System, Modul und Teil. Dazu `uebersicht.csv`. | Auswahl aus [HOSPI-Tools, Zenodo 10.5281/zenodo.6796559](https://doi.org/10.5281/zenodo.6796559), CC BY 4.0 |
| `instrumentenbilder/` | 36 Fotos von 18 allgemeinchirurgischen Instrumenten (je 2), dazu `klassen.csv` | wie oben, kleine Auswahl |
| `siebliste_soll.csv` | Soll-Bestückung eines Kleinfragment-Siebs mit 20 Positionen | Frei erfunden für den Hackathon, kein Bezug zu einem Hersteller. Frei verwendbar. |
| `testfall_01_verbrauch.md` | Verbrauch einer OP als Liste und als Freitext, dazu die erwartete Bestellliste | Frei erfunden für den Hackathon. Frei verwendbar. |

Die CSV-Dateien verwenden das Semikolon als Trennzeichen, damit sie sich in Excel direkt öffnen lassen.

## Was in `hospi_orthopaedie/` steckt
Acht Systeme, jeweils mit Unterordnern je Modul und Teil:

| Ordner | Was es ist |
|---|---|
| `AO_Modular_Hand_System` | Handsystem: Platten, Bohrer und Instrumente in den Größen 1,0 bis 2,4 mm |
| `Trimed_Wrist_Fixation_System` | Handgelenk: palmare Platten, Pegs und Schrauben, Instrumente |
| `Synthes_LCP_Large_Fragment_Set` | Großfragment: Platten, Schrauben, Instrumente |
| `VA_Clavicle_Plating_Set` | Klavikula-Platten |
| `AO_Universal_Spinal_System` | Wirbelsäule: Stäbe, Klemmen, Instrumente |
| `Centerpiece_Laminoplasty_Set` | Laminoplastie: Platten und Instrumente |
| `Hoffman_3_External_Fixation_Set`, `Hoffman_Compact` | Fixateur externe |

Zwei Arten von Bildern (Spalte `art` in `uebersicht.csv`):
- **Sieb-Übersicht:** Ordner, deren Name auf `Set` endet. Sie zeigen ganze Siebe, Schraubenracks mit Längenbeschriftung und Module, je Sieb bis zu 40 Bilder aus verschiedenen Blickwinkeln. Das ist das Material für den Foto-Ansatz.
- **Einzelteil:** ein Bild je Platte, Bohrer oder Instrument, als Katalog zum Nachschlagen.

## Was ihr über die Bilder wissen müsst
- Die Bilder sind klein (600 × 400 Pixel). Aufdrucke und Lasermarkierungen sind oft nicht lesbar.
- Zu den Sieb-Fotos gibt es keine Angabe, was fehlt, und keine Vorher-Nachher-Paare mit bekanntem Verbrauch. Was als verbraucht gilt, müsst ihr selbst festlegen, oder ihr übt den Abgleich mit der erfundenen Siebliste.
- Die Ordnernamen sind die englischen Bezeichnungen des Datensatzes und enthalten Herstellernamen. Für den Hackathon sind sie nur Beispielmaterial.
- Der vollständige Datensatz hat rund 21.000 Orthopädie-Bilder (2 GB). Wer mehr braucht, lädt ihn über den Link oben.

## Weitere offene Bilddatensätze (nur verlinkt)
| Quelle | Inhalt | Lizenz laut Anbieter | Hinweis |
|---|---|---|---|
| [Labeled Surgical Tools and Images (Kaggle)](https://www.kaggle.com/datasets/dilavado/labeled-surgical-tools) | Rund 3.000 Fotos von vier Instrumenten auf einem Tablett, mit Markierungen | Open Database License | 158 MB, Download braucht ein kostenloses Kaggle-Konto. |
| [UFG_SIC (GitHub)](https://github.com/Atabuzzaman/UFG_SIC) | Fotos von 95 Instrumententypen aus drei Sieben, aus zwei Blickwinkeln | siehe Projektseite | Begleitdaten zu einem Beitrag auf einem CVPR-Workshop 2025. |

## Empfehlung für den Hackathon
1. Mit `siebliste_soll.csv` und `testfall_01_verbrauch.md` den Abgleich von Hand und per Freitext bauen (Spickzettel Block 3 bis 5).
2. Für den Foto-Ansatz (Block 6) ein Schraubenrack aus `hospi_orthopaedie/` wählen, z. B. aus einem Ordner `..._Hand_Module_Set`, und die KI zählen lassen, welche Positionen belegt sind.
3. Eigene Testbilder ergänzen: Siebliste ausdrucken, verbrauchte Positionen durchstreichen, fotografieren.

## Bei Verwendung angeben
Rodrigues M, Mayo M, Patros P. Evaluation of Deep Learning Techniques on a Novel Hierarchical Surgical Tool Dataset. Australasian Joint Conference on Artificial Intelligence 2021. Datensatz: HOSPI-Tools, Zenodo, doi:10.5281/zenodo.6796559 (CC BY 4.0).
