---
title: Content Analytics-Komponenten
description: Erfahren Sie mehr über die Details der spezifischen Content Analytics-Komponenten, wie Dimensionen, (berechnete) Metriken und abgeleitete Felder
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1023
ht-degree: 86%

---


# Content Analytics-Komponenten

Content Analytics fügt die folgenden Komponentenkategorien (Dimensionen, [berechnete] Metriken, abgeleitete Felder) zu den bereits verfügbaren Komponenten in Customer Journey Analytics hinzu:

* [Erlebnismetadaten](#experience-metadata)
* [Erlebnisattribute](#experience-attributes)
* [Erlebnisereignisse](#experience-events)
* [Asset-Metadaten](#asset-metadata)
* [Asset-Attribute](#asset-attributes)
* [Asset-Ereignisse](#asset-events)
* [Berechnete Metriken](#calculated-metrics)

In den folgenden Tabellen gibt ![KI generiert](/help/assets/icons/AI.svg) ein von KI/ML generiertes Attribut-/Wert-Paar an.

## Erlebnismetadaten

| Titel | Beschreibung | Typ |
|---|---|---|
| ID SOURCE | Für Content Analytics lautet der Wert `ContentAnalytics`. | Dimension |
| Kanal | Kanal für das Erlebnis. Wert ist entweder `Web` oder `Mobile`. | Dimension |
| Content Experience ID | Eindeutige ID für das Erlebnis. <br>Für **Web**: URL der Webseite. <br/>Für **granulares Web**: Ein Client-seitiger Hash-Wert, der auf der Inhalts-Payload (Texte, Bilder, CTAS) mit dem Präfix `web-` basiert. <br/>Für **mobile**: Ein Client-seitiger Hash-Wert, der auf der Inhalts-Payload (Texte, Bilder, CTAs) mit dem Präfix `mobile-` basiert. | Dimension |
| Content Experience Source | Für **web**: die URL der Web-Seite.<br/>Für **mobil**: Der Name des Bildschirms, der über die Experience Platform Mobile SDK übergeben wird. | Dimension |
| Erlebniskanal (veraltet) | Kanal für das Erlebnis. Wert ist entweder `Web` oder `Mobile`. | Dimension |
| Erlebnis-Extras | Alle anderen zusätzlichen Daten, die Sie verfolgen möchten. Wie externe ID oder Platzierung. | Dimension |
| Erlebnis – URL der Miniaturansicht | URL für die Miniatur des Erlebnisses. | Dimension |
| Erlebnis – Horizontale Prozentsatz-Tiefe | Quantifizierbarer Wert der horizontalen Prozentsatz-Tiefe des Erlebnisses. | Dimension<br/>Abgeleitetes Feld |
| Erlebnis – Vertikale Prozentsatz-Tiefe | Quantifizierbarer Wert der vertikalen Prozentsatz-Tiefe des Erlebnisses. | Dimension<br/>Abgeleitetes Feld |

{style="table-layout:fixed"}



## Erlebnisattribute

| Titel | Beschreibung | Typ |
|---|---|---|
| Erlebnis – Attribute | ![KI generiert](/help/assets/icons/AI.svg) Vollständige Liste aller Namen und Werte von Erlebnisattributen. | Dimension<br>Abgeleitetes Feld |
| Erlebnis – Lesbarkeit – Wert | ![KI generiert](/help/assets/icons/AI.svg) Lesbarkeitswert für das Erlebnis. | Dimension |
| Erlebnis – Keywords | ![KI-generiert](/help/assets/icons/AI.svg) Keywords für das Erlebnis. | Dimension<br>Abgeleitetes Feld |
| Erlebnis – Überzeugungsstrategien | ![KI-generiert](/help/assets/icons/AI.svg) Im jeweiligen Erlebnis vorhandene Überzeugungsstrategien. Die möglichen Werte sind: soziale Identität, Social Proof, Autorität, Konkretheit, Fuß in der Tür, Überwindung von Reaktanz, Reziprozität, Verankerung und Vergleich, soziale Wirkung, Mangel und Anthropomorphismus. | Dimension<br/>Abgeleitetes Feld |
| Erlebnis – Narrative | ![KI-generiert](/help/assets/icons/AI.svg) Narrative, die das Erlebnis aus der Perspektive einer Marketing-Fachkraft aufgrund der Relevanz aufbaut. | Dimension<br/>Abgeleitetes Feld |
| Erlebnis – Töne | ![KI-generiert](/help/assets/icons/AI.svg) Töne, die das Erlebnis aus der Perspektive einer Marketing-Fachkraft aufgrund der Relevanz aufbaut. | Dimension<br/>Abgeleitetes Feld |
| Erlebnis – Marketing-Emotionen | ![KI generiert](/help/assets/icons/AI.svg) Die Emotionen, die beim Lesen des als Teil des Erlebnisses verwendeten Texts bei der Leserin bzw. dem Leser geweckt werden: Dringlichkeit, Exklusivität, Ermutigung, Herausforderung, Neugier, Leistung, Vertrauen, Einfachheit und Faszination. | Dimension<br/>Abgeleitetes Feld |
| Erlebnis – Anzahl der Emojis | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Emojis für das Erlebnis. | Metrik |
| Erlebnis – Hashtag-Anzahl | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Hashtags für das Erlebnis. | Metrik |
| Erlebnis – Satzanzahl | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Sätze für das Erlebnis. | Metrik |
| Erlebnis – Stoppwörter-Verhältnis | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Stoppwörter für das Erlebnis. | Metrik |
| Erlebnis – Anzahl der Textzitate | ![KI-generiert](/help/assets/icons/AI.svg) Anzahl der Textzitate für das Erlebnis. | Metrik |
| Erlebnis – Wortanzahl | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Wörter für das Erlebnis. | Metrik |
| Erlebnis – Wortanzahl pro Satz | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Wörter pro Satz für das Erlebnis. | Metrik |

{style="table-layout:fixed"}


## Erlebnisereignisse

| Titel | Beschreibung | Typ |
|---|---|---|
| Erlebnis – Ansichten | Quantifizierbares Maß für die Anzahl der Ansichten des Erlebnisses. | Metrik |
| Erlebnis – Klicks | Quantifizierbares Maß für die Anzahl der Klicks des Erlebnisses. | Metrik |

{style="table-layout:fixed"}


## Asset-Metadaten

| Titel | Beschreibung | Typ |
|---|---|---|
| Element-ID | Eindeutige Kennung des Assets. Die Asset-Binärdatei bestimmt die Eindeutigkeit. Wenn sich die Asset-Binärdatei ändert, ändert sich die ID. Die eindeutige ID kann die URL sein, es kann aber auch ein Hash erstellt werden. | Dimension |
| Asset-Quelle | | Dimension |
| Asset – HTML-Pfad | Verketteter HTML-Pfad für das Asset. | Dimension |
| Asset – Link-URL | Nächster Seitenanker für das Asset. | Dimension |
| Asset – Anzeigebreite | Anzeigebreite des Inhalts-Assets. | Dimension |
| Asset – Anzeigehöhe | Anzeigehöhe des Inhalts-Assets. | Dimension |
| Asset – Absolut – Links | Absolute linke Seite des Inhalts-Assets. | Dimension |
| Asset – Absolut – Oben | Absolute Oberseite des Inhalts-Assets. | Dimension |
| Asset-Extras | Alle anderen zusätzlichen Daten, die Sie verfolgen möchten. Wie externe ID oder Platzierung. | Dimension |

{style="table-layout:fixed"}


## Asset-Attribute

| Titel | Beschreibung | Typ |
|---|---|---|
| Asset – Attribute | ![KI-generiert](/help/assets/icons/AI.svg) Vollständige Liste aller Namen und Werte von Asset-Attributen. | Dimension<br>Abgeleitetes Feld |
| Asset – Ausrichtung | ![KI-generiert](/help/assets/icons/AI.svg) Ausrichtung des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Gesamtton | ![KI generiert](/help/assets/icons/AI.svg) Gesamtton des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Vordergrundfarben | ![KI-generiert](/help/assets/icons/AI.svg) Vordergrundfarben des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Hintergrundfarben | ![KI-generiert](/help/assets/icons/AI.svg) Hintergrundfarben des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Tags | ![KI-generiert](/help/assets/icons/AI.svg) Tags für das Asset. | Dimension<br/>Abgeleitetes Feld |
| Asset – Szenen | ![KI-generiert](/help/assets/icons/AI.svg) Szenen für das Asset. | Dimension<br/>Abgeleitetes Feld |
| Asset – Objekte | ![KI-generiert](/help/assets/icons/AI.svg) Objekte des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Fotografie-Stile | ![KI-generiert](/help/assets/icons/AI.svg) Fotografie-Stile des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Bildtyp | ![KI-generiert](/help/assets/icons/AI.svg) Bildtyp des Assets. Mögliche Werte sind: Foto, Skizze, Bild, Digital_Cartoon, Infografiken, Grapfik_Design, Collage und Software_Screenshot. | Dimension<br/>Abgeleitetes Feld |
| Asset – Kamerapositionen | ![KI-generiert](/help/assets/icons/AI.svg) Kamerapositionen des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Kameraumgebung | ![KI-generiert](/help/assets/icons/AI.svg) Kameraumgebung des Assets. | Dimension<br/>Abgeleitetes Feld |
| Asset – Personenkategorien | ![KI-generiert](/help/assets/icons/AI.svg) Personenkategorien für das Asset. Mögliche Werte sind: Person, Mann, Frau, Gesellschaftsgruppe, Menschenmenge, Menschen, Junge, Mädchen und Kind. | Dimension<br/>Abgeleitetes Feld |
| Asset – Dichte der visuellen Inhalte | ![KI-generiert](/help/assets/icons/AI.svg) Dichte der visuellen Inhalte des Assets. Mögliche Werte sind: niedrig, mittel oder hoch. Eine niedrige Inhaltsdichte impliziert eine geringe Menge an Informationen pro Flächeneinheit des Bildes. | Dimension |
| Asset – Verteilung der visuellen Aufmerksamkeit | ![KI generiert](/help/assets/icons/AI.svg) Verteilung der visuellen Aufmerksamkeit des Assets. Mögliche Werte sind: niedrig, mittel oder hoch. Die Verteilung der Aufmerksamkeit bezieht sich auf den Grad, in dem die Aufmerksamkeit einer Betrachterin bzw. eines Betrachters auf verschiedene Teile eines Bildes aufgeteilt wird. | Dimension<br/>Abgeleitetes Feld |
| Asset – Lichtverhältnisse | ![KI-generiert](/help/assets/icons/AI.svg) Lichtverhältnisse des Assets. Mögliche Werte sind: goldene Stunde, blaue Stunde, Mittag, bedeckt, Nacht, High-Key, Low-Key, Tageslicht, glühend, Kaltlicht, bunt und Studio. | Dimension<br/>Abgeleitetes Feld |
| Asset – Kameraeinstellung | ![KI-generiert](/help/assets/icons/AI.svg) Kameraeinstellung des Assets. Mögliche Werte sind: schnelle Verschlussgeschwindigkeit, lange Belichtung, Bokeh-Unschärfe, Bewegungsunschärfe, Tilt-Shift, Blitz, Weitwinkel, Schwarzweiß, Surreal, Doppelbelichtung, Makro und normaler Modus. | Dimension<br/>Abgeleitetes Feld |

{style="table-layout:fixed"}


## Asset-Ereignisse

| Titel | Beschreibung | Typ |
|---|---|---|
| Asset – Ansichten | Quantifizierbares Maß für die Anzahl der Ansichten des Assets. | Metrik |
| Asset – Klicks | Quantifizierbares Maß für die Anzahl der Klicks des Assets. | Metrik |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## Berechnete Metriken

| Titel | Beschreibung | Typ |
|---|---|---|
| Asset – Clickthrough-Rate | Asset-Klicks/Asset-Ansichten | Berechnete Metrik |
| Klickrate der Erlebnisse | Erlebnis-Klicks/Erlebnis-Ansichten | Berechnete Metrik |

{style="table-layout:fixed"}

