---
title: Attributionsbedienfeld
description: Verwendung und Interpretation des Attributionsbedienfelds in Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: c89a28323c9d40a7265cd22994a0d1c484f4c7ee
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 80%

---

# Attributionsbedienfeld {#attribution-panel}

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_button"
>title="Attribution"
>abstract="Vergleichen und visualisieren Sie im Handumdrehen eine beliebige Anzahl von Attributionsmodellen unter Verwendung verschiedener Dimensionen und Konversionskennzahlen."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ-Bedienfeld"

>[!CONTEXTUALHELP]
>id="cja_workspace_attribution_panel"
>title="Attributionsbedienfeld"
>abstract="Vergleichen und visualisieren Sie im Handumdrehen eine beliebige Anzahl von Attributionsmodellen unter Verwendung verschiedener Dimensionen und Konversionskennzahlen.<br/><br/>**Parameter **<br/>**Kanal**<br/> Die Dimension, der zugeschrieben werden soll. Dabei kann es sich um Marketing-Kanäle, Kampagnen oder beliebige andere Dimensionen handeln.<br/>**Modelle**<br/> Das Modell bestimmt, wie Guthaben zu Touchpoints zugewiesen wird.<br/>**Lookback-Fenster**<br/> Diese Einstellung bestimmt das Fenster der Datenzuordnung, auf das bei jeder Konvertierung die Anwendung erfolgt."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ-Bedienfeld"


Das [!UICONTROL Attributionsbedienfeld] bietet eine einfache Möglichkeit, eine Analyse zu erstellen, mit der verschiedene Attributionsmodelle verglichen werden. Es handelt sich um eine Funktion, die Ihnen einen speziellen Arbeitsbereich bietet, um Attributionsmodelle zu verwenden und zu vergleichen.

Customer Journey Analytics erweitert die Attribution und ermöglicht Ihnen Folgendes:

* Die Attribution über bezahlte Medien definieren: Dimensionen, Metriken, Kanäle oder Ereignisse können auf Modelle (z. B. die interne Suche) angewendet werden, nicht nur Marketing-Kampagnen.
* Den Vergleich für unbegrenzte Attributionsmodelle verwenden: Vergleichen Sie dynamisch so viele Modelle, wie Sie möchten.
* Implementierungsänderungen vermeiden: Mit der Berichtszeitverarbeitung und kontextabhängigen Sitzungen kann der Journey-Kontext für Kunden integriert und zur Laufzeit angewendet werden.
* Die Sitzung erstellen, die Ihrem Attributionsszenario am ehesten entspricht.
* Die Attribution nach Filtern aufschlüsseln: Vergleichen Sie problemlos die Leistung Ihrer Marketing-Kanäle über alle wichtigen Filter hinweg (z. B. Neu- mit Bestandskunden, Produkt X vs. Produkt Y, Loyalitätsgrad oder CLV).
* Wechsel zwischen Kanälen und Multi-Touch-Analyse beachten: Verwenden Sie Venn-Diagramme und Histogramme und erstellen Sie Trends anhand von Attributionsergebnissen.
* Wichtige Marketing-Sequenzen visuell analysieren: Erkunden Sie zur Konversion führende Pfade visuell mithilfe von mehrknotigen Fluss- und Fallout-Visualisierungen.
* Berechnete Metriken erstellen: Verwenden Sie eine beliebige Anzahl an Attributionszuordnungsmethoden.

## Erstellen eines Attributionsbedienfeldes

1. Klicken Sie links auf das Bedienfeldsymbol.
1. Ziehen Sie das [!UICONTROL Attributionsbedienfeld] in Ihr Analysis Workspace-Projekt.

   ![Das Fenster &quot;Neues Projekt&quot;, in dem der Bereich &quot;Attribution&quot;hervorgehoben wird.](assets/Attribution_Panel_1.png)

1. Fügen Sie eine Metrik hinzu, die Sie zuordnen möchten, und fügen Sie eine beliebige Dimension hinzu, gegen die Sie zuordnen möchten. Beispiele sind Marketing-Kanäle oder benutzerdefinierte Dimensionen wie interne Promotions.

   ![Das Fenster &quot;Attributionsbereich&quot;mit mehreren ausgewählten Dimensionen und Metriken.](assets/attribution_panel2.png)

1. Wählen Sie die Attributionsmodelle und das Lookback-Fenster aus, die Sie vergleichen möchten.

1. Das Attributionsbedienfeld gibt einen umfangreichen Satz an Daten und Visualisierungen zurück, die die Attribution für die ausgewählte Dimension und Metrik vergleichen.

   ![Die Visualisierungen des Attributionsbedienfelds, die ausgewählte Metriken und Dimensionen vergleichen.](assets/attr_panel_vizs.png)

## Visualisierungen der Attribution

* **Gesamtmetrik**: Die Gesamtanzahl der im Berichtszeitfenster aufgetretenen Konversionen. Hierbei handelt es sich um die Konversionen, die über die von Ihnen ausgewählte Dimension hinweg mit Attributen versehen werden.
* **Balkendiagramm für den Vergleich der Metrik-Attribution**: Vergleicht visuell die zugeordneten Konversionen über die einzelnen Dimensionselemente der von Ihren ausgewählten Dimension hinweg. Jede Balkenfarbe stellt ein bestimmtes Attributionsmodell dar.
* **Attributionsvergleichstabelle**: Zeigt dieselben Daten wie das Balkendiagramm in Tabellenform an. Durch die Auswahl verschiedener Spalten oder Zeilen in dieser Tabelle werden das Balkendiagramm sowie mehrere andere Visualisierungen im Bedienfeld gefiltert. Diese Tabelle verhält sich ähnlich wie jede andere Freiformtabelle in Workspace. So können Sie Komponenten wie Metriken, Filter oder Aufschlüsselungen hinzufügen.
* **Überlagerungsdiagramm**: Ein Venn-Diagramm, das die drei wichtigsten Dimensionselemente zeigt und wie oft sie gemeinsam an einer Konversion beteiligt sind. Beispielsweise gibt die Größe der Blasenüberschneidung an, wie oft Konversionen auftraten, wenn eine Person beiden Dimensionselementen ausgesetzt war. Durch die Auswahl anderer Zeilen in der angrenzenden Freiformtabelle wird die Visualisierung entsprechend Ihrer Auswahl aktualisiert.
* **Leistungsdetails**: Hiermit können Sie bis zu drei Attributionsmodelle visuell mit einem Streudiagramm vergleichen.
* **Trendleistung**: Zeigt den Trend der zugeordneten Konvertierungen für das Element der obersten Dimension. Durch die Auswahl anderer Zeilen in der angrenzenden Freiformtabelle wird die Visualisierung entsprechend Ihrer Auswahl aktualisiert.
* **Fluss**: Hiermit können Sie sehen, mit welchen Kanälen am häufigsten interagiert wird und in welcher Reihenfolge sie auf dem Journey einer Person angeordnet sind.
