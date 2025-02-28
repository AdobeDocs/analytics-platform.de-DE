---
title: Komponenteneinstellung „Werte einschließen/ausschließen“
description: Ein Dimensionselement kann abhängig von seinem Wert bedingt ein- oder ausgeschlossen werden.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 69%

---

# Komponenteneinstellung „Werte einschließen/ausschließen“ {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="Werte einschließen/ausschließen"
>abstract="Filtern Sie eine Metrik so, dass nur Werte gezählt werden, die bestimmten Kriterien entsprechen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="Werte einschließen/ausschließen"
>abstract="Schränken Sie eine Dimension so ein, dass nur Werte eingeschlossen werden, die bestimmten Kriterien entsprechen. Ein- und Ausschlüsse erfolgen vor der Zuordnung und den Filtern in Berichten. Ermitteln Sie, ob bei der angegebenen Filterlogik zwischen Groß- und Kleinschreibung unterschieden wird."

<!-- markdownlint-enable MD034 -->

„Werte einschließen/ausschließen“ ermöglicht die Erstellung von Regeln, die vom Wert eines Dimensionselements abhängen. Werte, die die von Ihnen festgelegten Kriterien nicht erfüllen, werden in Analysis Workspace so behandelt, als wären sie nicht vorhanden, obwohl die Daten noch im zugrunde liegenden Datensatz vorhanden sind.

![Datenansichtsfenster mit hervorgehobener Option „Werte einschließen/ausschließen“](../assets/include-exclude.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Werteinschluss/-ausschluss festlegen] | Ein Kontrollkästchen, mit dem Sie Bedingungen aktivieren können, wenn Daten in einer Datenansicht enthalten sind. |
| [!UICONTROL Von Schreibweise abhängig] | Sichtbar bei Datentypen des Zeichenfolgen-Schemas. Standardmäßig ist diese Einstellung aktiviert. Diese Einstellung gilt nur für die Logik [!UICONTROL Werte einschließen/ausschließen], nicht für den resultierenden Wert. Sie können damit angeben, ob bei der Regel zwischen Groß- und Kleinschreibung unterschieden wird. |
| [!UICONTROL Übereinstimmung] | Hier können Sie angeben, welche Werte Sie vor der Attribution und den Filtern für das Reporting berücksichtigen möchten (z. B. nur Werte mit dem Wort „Fehler“). Sie können Folgendes angeben **[!UICONTROL Wenn alle Kriterien erfüllt sind]** oder **[!UICONTROL Wenn beliebige Kriterien erfüllt sind]**. Trennen Sie jeden Wert durch ein Leerzeichen. |
| [!UICONTROL Kriterien] | Hier können Sie die Übereinstimmungslogik angeben, die auf eine bestimmte Filterregel angewendet werden soll.<ul><li>**Zeichenfolge**: [!UICONTROL Enthält die Phrase], [!UICONTROL Enthält einen der Begriffe], [!UICONTROL Enthält alle Begriffe], [!UICONTROL Enthält keinen der Begriffe], [!UICONTROL Enthält nicht die Phrase], [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Beginnt mit], [!UICONTROL Endet mit]</li><li>**Double/Integer**: [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Ist größer als], [!UICONTROL Ist kleiner als], [!UICONTROL Ist größer oder gleich], [!UICONTROL Ist kleiner oder gleich]</li><li>**Datum**: [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Ist später als], [!UICONTROL Ist vor], [!UICONTROL Tritt innerhalb]</li></ul> |
| [!UICONTROL Übereinstimmungsoperand] | Hiermit können Sie den Übereinstimmungsoperanden angeben, auf den der Übereinstimmungsoperator angewendet werden soll.<ul><li>**Zeichenfolge**: Textfeld</li><li>**Dezimalzahl/Ganzzahl**: Textfeld mit Pfeilen nach oben/unten für numerische Werte</li><li>**Datum**: Auswahl der Tagesgranularität (Kalender)</li><li>**Datum Uhrzeit**: Auswahl der Datums- und Uhrzeitgranularität</li></ul> |
| [!UICONTROL Regel hinzufügen] | Hier können Sie einen zusätzlichen Übereinstimmungsoperator und -operanden angeben. |

{style="table-layout:auto"}
