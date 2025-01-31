---
title: Trichteranalyse
description: Vergleichen Sie die Konversionsraten zwischen den Schritten.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 3%

---

# Analyse [!UICONTROL Trichter] {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Trichter"
>abstract="Vergleichen Sie die Konversionsraten zwischen den Schritten."

<!-- markdownlint-enable MD034 -->

Die ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel ]**-Analyse bietet eine visuelle Darstellung einer wichtigen Benutzer-Journey in Ihrem Produkt. Die horizontale Achse stellt jeden Schritt dar, den ein Benutzer durchlaufen muss. Die vertikale Achse stellt den Prozentsatz der Benutzer oder Sitzungen bei jedem Schritt dar. Alle Schritte müssen in einer bestimmten Reihenfolge ausgeführt werden, können jedoch jederzeit innerhalb des Reporting-Fensters erfolgen.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?quality=12&learn=on){width="90%"}

## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Konversionsanalyse**: Sie können Konversionen in jeder Phase des Trichters analysieren, z. B. an einem Einzelhandelskasse, bei der Kontoregistrierung, im Abonnementablauf oder auf einem anderen wichtigen Journey in Ihrem Produkterlebnis. Indem Sie die Anzahl der Benutzer verfolgen, die von einem Schritt zum nächsten wechseln, können Sie Engpässe mit ungewöhnlichen oder unerwünschten Konversionsraten identifizieren. Diese Informationen sind nützlich, um zu verstehen, wo Sie Ihr Produkt-Journey verbessern können, um sofortige Ergebnisse zu erzielen.
* **Experimentanalyse**: Sie können Konversionsraten in einem Trichter vergleichen, der optionale Schritte oder Schritte zur Ausführung eines A/B-Experiments enthält. Diese Informationen können Ihnen dabei helfen, festzustellen, welche Trichtervariante zur höchsten Konversionsrate führt, sodass Sie mehr Benutzende auf diesem Pfad ermutigen können.
* **Onboarding-Optimierung**: Optimieren Sie den Onboarding-Prozess Ihres Produkts, indem Sie das Benutzerverhalten bei wichtigen Ereignissen untersuchen. Sie können ermitteln, mit welchen Schritten Benutzende zu kämpfen haben oder welche nicht abgeschlossen werden können.
* **Funktionsübernahme und -interaktion**: Erfahren Sie, wie Benutzer mit bestimmten Funktionen in Ihrem Produkt interagieren. Durch die Analyse des Fortschritts von Benutzenden mithilfe von funktionsbezogenen Schritten können Sie Anpassungsraten anzeigen und Bereiche identifizieren, in denen Benutzende bestimmte Funktionen möglicherweise nicht ausreichend nutzen. Anschließend können Sie diese Informationen verwenden, um sich auf Funktionsverbesserungen zu konzentrieren und so die Akzeptanzraten zu erhöhen.
* **Effektivität des Marketing-Kanals**: Messen der Effektivität von Marketing-Kanälen. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die mit verschiedenen Marketing-Kanälen interagiert haben, z. B. Paid Search, Display, Natural Search oder Direct. Sie können dann ihre Journey miteinander vergleichen, um zu sehen, welcher Kanal zu den besten Produktergebnissen führt.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Konversionstrends](conversion-trends.md).
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jeder Balken im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte umfassen.
   * [!UICONTROL Vergleichen]: Jeder Schritt bietet eine Option, um mehrere Ereignisse in einem Trichter-Schritt zu vergleichen und einen „Gabelungstrichter“ zu erstellen. Mit dieser Funktion können Sie die Reibung von zwei Journey nebeneinander vergleichen, ohne zwei separate Analysen zu erstellen. Dies ist nützlich, wenn es Schrittoptionen gibt oder ein A/B-Experiment im Trichter ausgeführt wird. Unter [Trichter](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) in Customer Journey Analytics-Tutorials finden Sie ein Video, in dem das Vergleichen von Trichtern erläutert wird.
* **[!UICONTROL Wird gezählt als]**: Der Umfang, den Sie auf den Trichter anwenden möchten. Die Optionen umfassen [!UICONTROL Sitzungen] und [!UICONTROL Benutzer].
   * [!UICONTROL Sitzungen]: Alle Schritte müssen innerhalb derselben Sitzung stattfinden, damit sie gezählt werden.
   * [!UICONTROL Benutzer]: Um gezählt zu werden, müssen alle Schritte innerhalb des ausgewählten Reporting-Fensters erfolgen.
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einschließen.

### Diagrammeinstellungen

Die [!UICONTROL Trichter]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Die Optionen umfassen [!UICONTROL Schritte].
* **[!UICONTROL Konversion von]**: Bestimmt die prozentuale Berechnung von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem [!UICONTROL ersten Schritt] oder [!UICONTROL vorherigen Schritt].

### Zeitvergleich

{{apply-time-comparison}}



### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Diese Einstellung hat keine Auswirkungen auf Nicht-Trend-Analysen wie [Trichter](funnel.md).
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
