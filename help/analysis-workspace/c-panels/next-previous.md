---
description: Ein Bedienfeld, das die nächsten oder vorherigen Dimensionselemente für eine bestimmte Dimension anzeigt.
title: Bedienfeld „Nächstes oder vorheriges Element“
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 19%

---

# Bedienfeld „Nächstes oder vorheriges Element“ {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Nächstes oder vorheriges Objekt"
>abstract="Erstellen Sie ein Bedienfeld, um mehr über die vorherigen Dimensionen zu erfahren, aus denen Personen kommen, oder über die nächste Dimension, zu der sie gehen."

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Nächstes oder vorheriges Objekt"
>abstract="Analysieren Sie, von welchen Orten die Besucher am häufigsten kamen oder als Nächstes gehen. Geben Sie die Dimension, das Dimensionselement, die Richtung und den Container an, der für die Visualisierung verwendet werden soll."



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_In diesem Artikel wird das Bedienfeld Nächstes oder vorheriges Element in {_}![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Siehe [Bedienfeld „Nächstes oder vorheriges Element](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) für die_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-Version dieses Artikels._

>[!ENDSHADEBOX]

Das Bedienfeld **[!UICONTROL Nächstes oder vorheriges Element]** enthält eine Reihe von Tabellen und Visualisierungen, um das nächste oder vorherige Dimensionselement für eine bestimmte Dimension zu identifizieren. Vielleicht möchten Sie herausfinden, welche Seiten Kundinnen und Kunden am häufigsten besucht haben, nachdem sie die Startseite besucht haben.

## Verwenden {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="Container"
>abstract="Wählen Sie den Container aus, um den Umfang Ihrer Anfrage zu bestimmen."

So verwenden Sie ein Bedienfeld **[!UICONTROL Nächstes oder vorheriges Element]**:

1. Erstellen Sie ein Bedienfeld **[!UICONTROL Nächstes oder vorheriges Element]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.

### Bedienfeldeingabe

Sie können das Bedienfeld [!UICONTROL Nächstes oder vorheriges Element] mit den folgenden Eingabeeinstellungen konfigurieren:

![Bedienfeld „Nächstes oder vorheriges Element“](assets/next-or-previous-item.png)

| Eingabe | Beschreibung |
| --- | --- |
| **[!UICONTROL Dimension]** | Wählen Sie die Dimension aus, für die Sie die nächsten oder vorherigen Elemente untersuchen möchten. |
| **[!UICONTROL Dimensionselement]** | Wählen Sie das spezifische Dimensionselement in der Mitte Ihrer nächsten/vorherigen Anfrage aus. |
| **[!UICONTROL Richtung]** | Geben Sie an, ob Sie nach dem Dimensionselement [!UICONTROL Weiter] oder [!UICONTROL Zurück] suchen. |
| **[!UICONTROL Container]** | Wählen Sie den Container [!UICONTROL Sitzung] oder [!UICONTROL Person] (Standard) aus, um den Umfang Ihrer Anfrage zu bestimmen. |

{style="table-layout:auto"}

Wählen Sie **[!UICONTROL Erstellen]** aus, um das Bedienfeld zu erstellen.

### Bedienfeldausgabe

Das Bedienfeld [!UICONTROL Nächstes oder vorheriges Element] gibt einen umfangreichen Satz von Daten und Visualisierungen zurück, damit Sie besser verstehen können, welche Ereignisse bestimmten Dimensionselementen folgen oder vorausgehen.


![Nächste/Vorherige Bedienfeldausgabe](assets/next-or-previous-item-output.png)


| Visualisierung | Beschreibung |
| --- | --- |
| **[!UICONTROL Horizontalbalken]** | Listet die nächsten (oder vorherigen) Elemente basierend auf dem von Ihnen ausgewählten Dimensionselement auf. Wenn Sie den Mauszeiger über eine einzelne Leiste bewegen, wird das entsprechende Element in der Freiformtabelle hervorgehoben. |
| **[!UICONTROL Zusammenfassungszahl]** | Allgemeine Zusammenfassung der Anzahl aller nächsten oder vorherigen Dimensionselement-Vorkommen für den aktuellen Monat (bis jetzt). |
| **[!UICONTROL Freiformtabelle]** | Listet die nächsten (oder vorherigen) Elemente basierend auf dem von Ihnen ausgewählten Dimensionselement in einem Tabellenformat auf. Dies waren beispielsweise die beliebtesten Seiten (nach Vorkommen), zu denen Personen nach (oder vor) der Startseite oder Workspace-Seite gegangen sind. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
