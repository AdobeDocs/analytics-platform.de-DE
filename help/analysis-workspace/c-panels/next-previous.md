---
description: Ein Bedienfeld, das die nächsten oder vorherigen Dimensionselemente für eine bestimmte Dimension anzeigt.
title: Bedienfeld „Nächstes oder vorheriges Element“
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Bedienfeld „Nächstes oder vorheriges Element“ {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="Nächstes oder vorheriges Element"
>abstract="Erstellen Sie ein Bedienfeld, um die vorherigen Dimensionen zu verstehen, aus denen Personen kommen, oder die nächste Dimension, zu der Benutzer gehen."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="Verschachteln oder vorheriges Element"
>abstract="Analysieren Sie, von wo aus Besucher am häufigsten kamen oder zum nächsten gelangen.<br/><br/>**Dimension**: Wählen Sie eine Dimension aus. Beispiel: **Seite**.<br/>**Dimension item**: Wählen Sie ein bestimmtes Dimensionselement aus. Beispiel: **Homepage**.<br/>**Richtung**: Wählen Sie **Weiter** aus, um die Dimensionselemente unmittelbar neben dem ausgewählten Dimensionselement anzuzeigen. Wählen Sie &quot;**Zurück**&quot;, um die Dimensionselemente anzuzeigen, die zu Ihrem ausgewählten Dimensionselement führen.<br/>**Container**: Wählen Sie **Sitzung** aus, um die nächsten/vorherigen Dimensionselemente innerhalb derselben Sitzung anzuzeigen, oder wählen Sie **Person** aus, um das nächste/vorherige Dimensionselement für dieselbe Person anzuzeigen."

<!-- markdownlint-enable MD034 -->



Das Bedienfeld **[!UICONTROL Nächstes oder vorheriges Element]** enthält eine Reihe von Tabellen und Visualisierungen, um das nächste oder vorherige Dimensionselement für eine bestimmte Dimension zu identifizieren. Sie können beispielsweise untersuchen, welche Seiten Kunden nach dem Besuch der Startseite am häufigsten besucht haben.

## Verwenden Sie stattdessen 

So verwenden Sie ein Bedienfeld vom Typ **[!UICONTROL Nächstes oder vorheriges Element]** :

1. Erstellen Sie ein Bedienfeld &quot;**[!UICONTROL Nächstes oder vorheriges Element]**&quot;. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).

1. Geben Sie die [Eingabe](#panel-input) für das Bedienfeld an.

1. Beobachten Sie die [Ausgabe](#panel-output) für das Bedienfeld.

### Bedienfeldeingabe

Sie können den Bereich [!UICONTROL Nächstes oder vorheriges Element] mit den folgenden Eingabeeinstellungen konfigurieren:

![Nächster oder vorheriger Elementbereich](assets/next-or-previous-item.png)

| Eingabe | Beschreibung |
| --- | --- |
| **[!UICONTROL Dimension]** | Wählen Sie die Dimension aus, für die Sie die nächsten oder vorherigen Elemente untersuchen möchten. |
| **[!UICONTROL Dimensionselement]** | Wählen Sie das spezifische Dimensionselement in der Mitte Ihrer nächsten/vorherigen Anfrage aus. |
| **[!UICONTROL Richtung]** | Geben Sie an, ob Sie nach dem Dimensionselement [!UICONTROL Weiter] oder dem Dimensionselement [!UICONTROL Zurück] suchen. |
| **[!UICONTROL Container]** | Wählen Sie den Container [!UICONTROL Sitzung] oder [!UICONTROL Person] (Standard) aus, um den Umfang Ihrer Anfrage zu bestimmen. |

{style="table-layout:auto"}

Wählen Sie **[!UICONTROL Build]** aus, um das Bedienfeld zu erstellen.

### Bedienfeldausgabe

Das Bedienfeld [!UICONTROL Nächstes oder vorheriges Element] gibt einen umfangreichen Satz an Daten und Visualisierungen zurück, damit Sie besser verstehen können, welche Vorkommen bestimmten Dimensionselementen folgen oder vorausgehen.


![Nächste/Vorherige Bereichsausgabe](assets/next-or-previous-item-output.png)


| Visualisierung | Beschreibung |
| --- | --- |
| **[!UICONTROL Horizontalbalken]** | Führt die nächsten (oder vorherigen) Elemente basierend auf dem von Ihnen ausgewählten Dimensionselement auf. Wenn Sie den Mauszeiger über eine einzelne Leiste bewegen, wird das entsprechende Element in der Freiformtabelle markiert. |
| **[!UICONTROL Zusammenfassungszahl]** | Allgemeine Zusammenfassungsnummer aller nächsten oder vorherigen Dimensionselementvorkommen für den aktuellen Monat (bisher) |
| **[!UICONTROL Freiformtabelle]** | Führt die nächsten (oder vorherigen) Elemente basierend auf dem von Ihnen ausgewählten Dimensionselement im Tabellenformat auf. Hierbei handelte es sich beispielsweise um die beliebtesten Seiten (nach Vorfällen), die Besucher nach (oder vor) der Startseite oder Workspace-Seite aufriefen. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Erstellen eines Bedienfelds](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>