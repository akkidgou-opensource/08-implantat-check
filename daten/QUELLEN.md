# Datenquellen Implantat-Check

## Im Repo
| Datei | Inhalt | Herkunft und Lizenz |
|---|---|---|
| `siebliste_soll.csv` | Soll-Bestückung eines Kleinfragment-Siebs mit 20 Positionen | Frei erfunden für den Hackathon, kein Bezug zu einem Hersteller. Frei verwendbar. |
| `testfall_01_verbrauch.md` | Verbrauch einer OP als Liste und als Freitext, dazu die erwartete Bestellliste | Frei erfunden für den Hackathon. Frei verwendbar. |
| `instrumentenbilder/` | 36 Fotos von 18 chirurgischen Instrumenten (je 2), dazu `klassen.csv` mit der Bezeichnung je Bild | Auswahl aus [HOSPI-Tools, Zenodo 10.5281/zenodo.6796559](https://doi.org/10.5281/zenodo.6796559), CC BY 4.0 |

Die CSV-Datei verwendet das Semikolon als Trennzeichen, damit sie sich in Excel direkt öffnen lässt.

## Offene Bilddatensätze (nur verlinkt, zu groß für das Repo)
| Quelle | Inhalt | Lizenz laut Anbieter | Hinweis |
|---|---|---|---|
| [HOSPI-Tools (Zenodo 10.5281/zenodo.6796559)](https://doi.org/10.5281/zenodo.6796559) | Fotos chirurgischer Instrumente und Implantate aus Allgemeinchirurgie und Orthopädie, geordnet nach Fach, Sieb und Instrument | CC BY 4.0 | Gesamt 2,5 GB. Die kleine Auswahl `HOSPI_Tools_small_yolov5.zip` hat 172 MB. |
| [Labeled Surgical Tools and Images (Kaggle)](https://www.kaggle.com/datasets/dilavado/labeled-surgical-tools) | Rund 3.000 Fotos von vier Instrumenten auf einem Tablett, mit Markierungen | Open Database License | 158 MB, Download braucht ein kostenloses Kaggle-Konto. |
| [UFG_SIC (GitHub)](https://github.com/Atabuzzaman/UFG_SIC) | Fotos von 95 Instrumententypen aus drei Sieben, aus zwei Blickwinkeln | siehe Projektseite | Begleitdaten zu einem Beitrag auf einem CVPR-Workshop 2025. |

## Ehrliche Einschätzung
Die offenen Datensätze zeigen einzelne Instrumente, keine bestückten Schraubenracks mit fehlenden Positionen. Für genau diese Aufgabe gibt es keinen fertigen offenen Datensatz. Der schnellste Weg zu brauchbaren Testbildern ist deshalb, sie selbst herzustellen:
1. Siebliste als Tabelle ausdrucken, verbrauchte Positionen durchstreichen, fotografieren.
2. Oder ein Übungssieb ohne Patientenbezug fotografieren, falls jemand eines mitbringen darf.

## Bei Verwendung angeben
Rodrigues M, Mayo M, Patros P. Evaluation of Deep Learning Techniques on a Novel Hierarchical Surgical Tool Dataset. Australasian Joint Conference on Artificial Intelligence 2021.
