---
title: Trichteranalyse
description: Vergleichen Sie die Konversionsraten zwischen den Schritten.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
TQID: https://experienceleague.adobe.com/-AW7cK4fHNV58e539KKcqBx-pRpIpIRWcrS7CA9ZUYc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 694
ht-degree: 98%

---

# Analyse [!UICONTROL Trichter] {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Trichter"
>abstract="Vergleichen Sie die Konversionsraten zwischen den Schritten."

<!-- markdownlint-enable MD034 -->

Die ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Trichteranalyse &#x200B;]**&#x200B;bietet eine visuelle Darstellung einer wichtigen Benutzer-Journey in Ihrem Produkt. Die horizontale Achse stellt jeden Schritt dar, den eine Person ausführen muss. Die vertikale Achse stellt den Prozentsatz der Benutzenden oder Sitzungen bei jedem Schritt dar. Alle Schritte müssen in einer bestimmten Reihenfolge ausgeführt werden, können jedoch jederzeit innerhalb des Reporting-Fensters erfolgen.

>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Funnel-Reibungsanalyse](https://video.tv.adobe.com/v/3421663/?quality=12&learn=onn){target="_blank"} für ein Demovideo.

>[!ENDSHADEBOX]


## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Konversionsanalyse**: Sie können Konversionen in jeder Phase des Trichters analysieren, z. B. an einer Einzelhandelskasse, bei der Kontoregistrierung, im Abonnementablauf oder in einer anderen wichtigen Journey in Ihrem Produkterlebnis. Indem Sie die Anzahl der Personen verfolgen, die von einem Schritt zum nächsten fortfahren, können Sie Engpässe mit ungewöhnlichen oder unerwünschten Konversionsraten identifizieren. Diese Informationen helfen Ihnen, zu erkennen, wo Sie Ihre Produkt-Journey verbessern können, um sofortige Ergebnisse zu erzielen.
* **Experimentanalyse**: Sie können Konversionsraten in einem Trichter mit optionalen Schritten oder mit Schritten zur Ausführung eines A/B-Experiments vergleichen. Diese Informationen können Ihnen bei der Ermittlung der Trichtervariante helfen, die zur höchsten Konversionsrate führt, sodass Sie mehr Benutzende auf diesem Pfad aufmerksam machen können.
* **Onboarding-Optimierung**: Optimieren Sie den Onboarding-Prozess Ihres Produkts, indem Sie das Benutzerverhalten bei wichtigen Ereignissen untersuchen. Sie können ermitteln, welche Schritte Benutzenden Probleme bereiten oder welche Schritte nicht abgeschlossen werden können.
* **Funktionsübernahme und Interaktion**: Erfahren Sie, wie Benutzende mit bestimmten Funktionen in Ihrem Produkt interagieren. Durch die Analyse des Fortschritts von Benutzenden mithilfe von funktionsbezogenen Schritten können Sie Adoptionsraten anzeigen und Bereiche identifizieren, in denen Benutzende bestimmte Funktionen möglicherweise nicht ausreichend nutzen. Anschließend können Sie diese Informationen verwenden, um sich auf Funktionsverbesserungen zu konzentrieren und so die Akzeptanzraten zu erhöhen.
* **Effektivität des Marketing-Kanals**: Messen Sie die Effektivität von Marketing-Kanälen. Sie können ein Segment erstellen, das sich auf Benutzende konzentriert, die mit verschiedenen Marketing-Kanälen interagiert haben, z. B. Paid Search, Anzeige, Kostenlose Suche oder Direkt. Sie können dann ihre Journeys miteinander vergleichen, um zu sehen, welcher Kanal zu den besten Produktergebnissen führt.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Konversions-Trends](conversion-trends.md).
* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jeder Balken im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einschließen.
   * [!UICONTROL Vergleichen]: Jeder Schritt bietet eine Option, um mehrere Ereignisse in einem Trichter-Schritt zu vergleichen und einen verzweigten Trichter zu erstellen. Mit dieser Funktion können Sie die Reibung von zwei Journeys nebeneinander vergleichen, ohne zwei separate Analysen zu erstellen. Dies ist nützlich, wenn es Schrittoptionen gibt oder ein A/B-Experiment im Trichter ausgeführt wird. In den Customer Journey Analytics-Tutorials finden Sie unter [Trichter](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) ein Video, in dem das Vergleichen von Trichtern erläutert wird.
* **[!UICONTROL Zählt als]**: Der Umfang, den Sie auf den Trichter anwenden möchten. Die Optionen umfassen [!UICONTROL Sitzungen] und [!UICONTROL Benutzende].
   * [!UICONTROL Sitzungen]: Alle Schritte müssen innerhalb derselben Sitzung stattfinden, damit sie gezählt werden.
   * [!UICONTROL Benutzende]: Alle Schritte müssen innerhalb des ausgewählten Reporting-Fensters erfolgen, damit sie gezählt werden.
* **[!UICONTROL Segmente]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einschließen.

### Diagrammeinstellungen

Die [!UICONTROL Trichteranalyse] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Zu den Optionen gehören [!UICONTROL Schritte].
* **[!UICONTROL Konversion in]**: Bestimmt die prozentuale Berechnung von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konversion aus dem [!UICONTROL ersten Schritt] oder [!UICONTROL vorherigen Schritt].

### Zeitvergleich

{{apply-time-comparison}}



### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Diese Einstellung hat keine Auswirkungen auf Analysen ohne Trend, wie [Trichter](funnel.md).
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
