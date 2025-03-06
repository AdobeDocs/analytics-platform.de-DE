---
title: Inhaltsanalysekomponenten
description: Details zu den spezifischen Inhaltsanalysekomponenten, wie Dimensionen, (berechnete) Metriken und abgeleitete Felder
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: cd31712c1dde1fc39f4d0dc81555c19b7690bcab
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 17%

---

# Inhaltsanalysekomponenten

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}

Content Analytics fügt die folgenden Komponentenkategorien (Dimensionen, (berechnete) Metriken, abgeleitete Felder) zu den bereits verfügbaren Komponenten in Customer Journey Analytics hinzu:

* [Erlebnis-Metadaten](#experience-metadata)
* [Erlebnisattribute](#experience-attributes)
* [Erlebnisereignisse](#experience-events)
* [Asset-Metadaten](#asset-metadata)
* [Asset-Attribute](#asset-attributes)
* [Assets-Ereignisse](#asset-events)
* [Berechnete Metriken ](#calculated-metrics)

In den folgenden Tabellen ![KI generiert](/help/assets/icons/AI.svg) einen von KI/ML generierten Wert an.

## Erlebnis-Metadaten

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Erlebniskanal | Kanal für das Erlebnis. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Quelle | Source-URL des Erlebnisses. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis-ID | Eindeutige ID für das Erlebnis. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Name des Erlebnisses | Name für das Erlebnis. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Beschreibung | Beschreibung für das Erlebnis. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – URL der Miniaturansicht | URL für die Miniaturansicht des Erlebnisses. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Horizontale Prozentsatz-Tiefe | Quantifizierbarer Wert der horizontalen Prozenttiefe des Erlebnisses. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Vertikal – Prozentsatz – Tiefe | Quantifizierbarer Wert der vertikalen Prozenttiefe des Erlebnisses. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Horizontale Pixel-Tiefe | Quantifizierbarer Wert der horizontalen Pixeltiefe des Erlebnisses. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Vertikale Pixel-Tiefe | Quantifizierbarer Wert der vertikalen Pixeltiefe des Erlebnisses. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |

{style="table-layout:fixed"}



## Erlebnisattribute

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Erlebnis – Lesbarkeit – Wert | ![KI generiert](/help/assets/icons/AI.svg) Lesbarkeitswert für das Erlebnis. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Keywords | ![KI-generiert](/help/assets/icons/AI.svg) Schlüsselwörter für das Erlebnis. | Dimension Von <br> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Überzeugungsstrategien | ![KI generiert](/help/assets/icons/AI.svg) Überredungsstrategien, die im jeweiligen Erlebnis vorhanden sind. Die möglichen Werte sind: soziale Identität, sozialer Beweis, Autorität, Konkretheit, Fuß in der Tür, Überwindung von Reaktanz, Reziprozität, Verankerung und Vergleich, soziale Wirkung, Mangel und Anthropomorphismus. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Narrative | ![KI generiert](/help/assets/icons/AI.svg) Erzählungen, die das Erlebnis basierend auf der Relevanz aus der Sicht eines Marketing-Experten erstellt. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Töne | ![KI generiert](/help/assets/icons/AI.svg) Töne, die das Erlebnis basierend auf der Relevanz aus der Sicht eines Marketing-Experten erstellt | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Marketing-Emotionen | ![KI generiert](/help/assets/icons/AI.svg) Die Emotion, die beim Lesen des Erlebnisses aufgerufen wird: Dringlichkeit, Exklusivität, Ermutigung, Herausforderung, Neugier, Leistung, Vertrauen, Einfachheit und Faszination. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Erlebnis – Anzahl der Emojis | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Emojis für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Anzahl der Erlebnis-Hashtags | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Hashtags für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Erlebnis – Satzanzahl | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Sätze für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Erlebnis – Stoppwörter-Verhältnis | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Stoppwörter für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Erlebnis – Anzahl der Textzitate | ![KI-generiert](/help/assets/icons/AI.svg) Anzahl der Textanführungszeichen für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Erlebnis – Wortanzahl | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Wörter für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Erlebnis – Wortanzahl pro Satz | ![KI generiert](/help/assets/icons/AI.svg) Anzahl der Wörter pro Satz für das Erlebnis. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |

{style="table-layout:fixed"}


## Erlebnisereignisse

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Erlebnisansichten | Quantifizierbares Maß für die Anzahl der Ansichten des Erlebnisses. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Erlebnis-Klicks | Quantifizierbares Maß für die Anzahl der Klicks des Erlebnisses. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |

{style="table-layout:fixed"}


## Asset-Metadaten

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Asset-Quelle | Öffentlich zugängliche Quell-URL für das Asset. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Element-ID | Eindeutige Kennung des Assets. Die Asset-Binärdatei bestimmt die Eindeutigkeit. Wenn sich die Asset-Binärdatei ändert, ändert sich die ID nicht. Die eindeutige ID kann die URL sein, es kann aber auch ein Hash erstellt werden. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset-Name | Name des Assets. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset-Typ | Typ des Assets. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – URL der Miniaturansicht | URL für die Miniaturansicht des Assets. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – HTML-Pfad | Verketteter HTML-Pfad für das Asset. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Link-URL | Nächster Seitenanker für das Asset. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Anzeigebreite | Anzeigebreite des Inhalts-Assets. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Anzeigehöhe | Anzeigehöhe des Inhalts-Assets. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Absolut – Links | Inhalts-Asset – Absolut – Links. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Absolut – Oben | Inhalts-Asset – Absolut – Oben. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Erstellt von | Kennung für die Asset-Erstellung. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Erstellungsdatum | Asset-Erstellungsdatum. | Dimension | Zuletzt verwendet \| Sitzung |
| Asset – Zuletzt aktualisiert von | Kennung für die Asset-Aktualisierung. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Zuletzt aktualisiert – Datum | Aktualisierungsdatum des Assets. | Dimension | Zuletzt verwendet \| Sitzung |

{style="table-layout:fixed"}


## Asset-Attribute

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Asset – Ausrichtung | ![KI-generiert](/help/assets/icons/AI.svg) Ausrichtung des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Gesamtton | ![KI generiert](/help/assets/icons/AI.svg) Gesamtton des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Vordergrundfarben | ![KI-generiert](/help/assets/icons/AI.svg) Vordergrundfarben des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset-Hintergrundfarbe | ![KI-generiert](/help/assets/icons/AI.svg) Hintergrundfarben des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Tags | ![KI-generiert](/help/assets/icons/AI.svg) Tags für das Asset. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Szenen | ![KI-generiert](/help/assets/icons/AI.svg) Szenen für das Asset. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Objekte | ![KI-generiert](/help/assets/icons/AI.svg) Objekte des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Fotografie-Stile | ![KI-generiert](/help/assets/icons/AI.svg) Fotostile des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Bildtyp | ![KI-generiert](/help/assets/icons/AI.svg) Bildtyp des Assets. Mögliche Werte sind: Foto, Skizze, Malerei, Digital_Cartoon, Infografiken, Graphic_Design, Collage und Software_Screenshot. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Kamerapositionen | ![KI-generiert](/help/assets/icons/AI.svg) Kamerapositionen des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Kameraumgebung | ![KI-generiert](/help/assets/icons/AI.svg) Kameraannäherungen des Assets. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Personenkategorien | ![KI generiert](/help/assets/icons/AI.svg) Personenkategorien für das Asset. Mögliche Werte sind: Person, Mann, Frau, soziale Gruppe, Menge, Menschen, Junge, Mädchen und Kind. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Dichte der visuellen Inhalte | ![KI-generiert](/help/assets/icons/AI.svg) Visuelle Inhaltsdichte des Assets. Mögliche Werte sind: niedrig, mittel oder hoch. Eine geringe Inhaltsdichte bedeutet eine geringe Menge an Informationen pro Flächeneinheit des Bildes. | Dimension | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Verteilung der visuellen Aufmerksamkeit | ![KI generiert](/help/assets/icons/AI.svg) Die visuelle Aufmerksamkeit des Assets. Mögliche Werte sind: niedrig, mittel oder hoch. Aufmerksamkeitsstreuung bezieht sich auf den Grad, in dem die Aufmerksamkeit eines Betrachters auf verschiedene Teile eines Bildes aufgeteilt wird. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Lichtverhältnisse | ![KI generiert](/help/assets/icons/AI.svg) Beleuchtungszustand des Assets. Mögliche Werte sind: goldene Stunde, blaue Stunde, Mittag, Bewölkung, Nacht, High-Key, Low-Key, Tagesbeleuchtung, Glühlampe, fluoreszierend, farbig und Studio. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |
| Asset – Kameraeinstellung | ![KI-generiert](/help/assets/icons/AI.svg) Kameraeinstellung des Assets. Mögliche Werte sind: schnelle Verschlusszeit, lange Belichtung. Bokeh-Weichzeichnung, Bewegungsunschärfe, Neigungsverschiebungsunschärfe, Blitz, Weitwinkel, Schwarz-Weiß, Surreal, Doppelbelichtung, Makro und Normalmodus. | Dimension Von <br/> abgeleitetes Feld | \| anzeigen Kein Wert<br/>Zuletzt verwendet \| Sitzung |

{style="table-layout:fixed"}


## Asset-Ereignisse

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Asset-Ansichten | Quantifizierbares Maß für die Anzahl der Ansichten des Assets. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |
| Kreativelement-Klicks | Quantifizierbares Maß für die Anzahl der Klicks des Assets. | Metrik | Werte zählen<br/>Dezimalzahl \| Dezimalstellen: 0 |

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

| Anrede/Titel | Beschreibung | Typ | Einstellungen |
|---|---|---|---|
| Clickthrough-Rate für Assets | Asset-Klicks/-Ansichten | Berechnete Metrik | |
| Clickthrough-Rate des Erlebnisses | Erlebnis-Klicks/Erlebnis-Ansichten | Berechnete Metrik | |

{style="table-layout:fixed"}
