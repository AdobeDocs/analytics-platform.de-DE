---
description: Erfahren Sie, wie Admins mithilfe einer Datenansicht oder des Datenwörterbuchs Beschreibungen zu Komponenten hinzufügen können.
title: Komponentenbeschreibungen hinzufügen
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# Komponentenbeschreibungen hinzufügen

Mithilfe von Beschreibungen können Benutzende wissen, wie die verschiedenen Komponenten beim Erstellen von Projekten in Analysis Workspace oder beim Anzeigen von Berichten verwendet werden.

Customer Journey Analytics-Admins können mithilfe des Datenwörterbuchs oder innerhalb einer Datenansicht Beschreibungen für Komponenten (Dimensionen, Metriken, Segmente und Datumsbereiche) hinzufügen.

## Datenansicht

Sie können einer Komponente, die Sie Ihrer Datenansicht hinzugefügt haben, eine Beschreibung hinzufügen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md).

## Datenwörterbuch

Das Datenwörterbuch in Analysis Workspace hilft Benutzenden und Admins, die Komponenten in ihrer Customer Journey Analytics-Umgebung zu verfolgen und besser zu verstehen. Mit dem Datenwörterbuch können Admins Komponentenbeschreibungen direkt in Analysis Workspace hinzufügen.

Informationen zum Bearbeiten einer Komponentenbeschreibung im Datenwörterbuch finden Sie unter [Bearbeiten von Komponenteneinträgen im Datenwörterbuch](/help/components/data-dictionary/edit-entries-data-dictionary.md).

Allgemeine Informationen zum Datenwörterbuch finden Sie unter [Datenwörterbuch - Übersicht](/help/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Einstellungen der Datenansichtskomponente](/help/data-views/component-settings/overview.md)
>[Komponenteneinträge für Datenwörterbuch](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Beschreibungen automatisch generieren

{{release-limited-testing-section}}

Anstatt jede Beschreibung manuell zu schreiben, kann Customer Journey Analytics generative KI verwenden, um Beschreibungen für Sie zu schreiben. Sie können für eine einzelne Komponente eine Beschreibung oder für viele Komponenten gleichzeitig Beschreibungen erstellen.

Erzeugte Beschreibungen:

* Es sind nicht mehr als drei Sätze lang.
* Beenden Sie mit dem Text **[!UICONTROL Von Adobe mithilfe von KI generiert]**, damit die Benutzer wissen, dass die Beschreibung generiert wurde.
* Kann nach ihrer Erstellung bearbeitet werden.

### Voraussetzungen

Bevor Sie Beschreibungen generieren können, muss Ihr Unternehmen bestimmten rechtlichen Bedingungen für Generative AI zustimmen. Wenn Ihr Unternehmen diesen Bedingungen nicht zugestimmt hat, ist die Option zum Generieren von Beschreibungen abgeblendet. Wählen Sie das Informationssymbol ![Info](/help/assets/icons/InfoOutline.svg) neben der Option aus, um zu erfahren, wie Sie die Funktion aktivieren, oder wenden Sie sich an den Administrator Ihres Unternehmens oder das Adobe-Accountteam.

### Wie Beschreibungen generiert werden

Die generierten Beschreibungen basieren auf der Definition der Komponente und auf zusätzlichem Kontext darüber, wie die Komponente in Ihrer Datenansicht verwendet wird, z. B.:

* Die obersten Elemente einer Dimension
* Komponenten, die häufig mit der Komponente verwendet werden

Wenn eine berechnete Metrik oder ein Segment auf ein anderes Segment verweist, wird in der generierten Beschreibung die Definition des referenzierten Segments erläutert.

### Beschreibungen von verschiedenen Speicherorten generieren

Sie können Beschreibungen in den folgenden Bereichen von Customer Journey Analytics erstellen. Einige Speicherorte ermöglichen es Ihnen, Beschreibungen für mehrere Komponenten zu generieren, andere jedoch nicht.

Wählen Sie einen Speicherort aus, um zu erfahren, wie Sie dort Beschreibungen generieren können.

| Standort | Unterstützte Komponenten | Einzelne Komponente | Mehrere Komponenten |
| --- | --- | --- | --- |
| [Datenwörterbuch](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensionen</li><li>Metriken</li><li>Berechnete Metriken</li><li>Segmente</li><li>Datumsbereiche</li></ul> | Ja | Ja |
| [Datenansicht](/help/data-views/component-settings/overview.md) | <ul><li>Dimensionen</li><li>Metriken</li><li>Abgeleitete Felder</li><li>Freigegebene Metriken und Dimensionen (Weitere Informationen finden Sie unter [Freigegebene Metriken und Dimensionen](#generate-descriptions-for-shared-metrics-and-dimensions).)</li></ul> | Ja | Ja |
| [Segment Builder](/help/components/segments/seg-builder.md) | Segmente | Ja | Nein |
| [Segment-Manager](/help/components/segments/seg-manage.md#action-bar) | Segmente | Nein | Ja |
| [Generator für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | Berechnete Metriken | Ja | Nein |
| [Manager für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | Berechnete Metriken | Nein | Ja |
| [Generator für Datumsbereiche](/help/components/date-ranges/create.md#date-range-builder) | Datumsbereiche | Ja | Nein |
| [Datumsbereichs-Manager](/help/components/date-ranges/manage.md#action-bar) | Datumsbereiche | Nein | Ja |

{style="table-layout:auto"}

### Beschreibungen für freigegebene Metriken und Dimensionen generieren

Sie können Beschreibungen für freigegebene Metriken und Dimensionen nur in einer Datenansicht generieren, wie in der Tabelle unter [Beschreibungen von verschiedenen Speicherorten generieren](#generate-descriptions-from-various-locations) dargestellt. Sie können keine Beschreibungen über den Manager [Freigegebene Metriken und Dimensionen“ &#x200B;](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager).

Beachten Sie Folgendes, wenn Sie eine Beschreibung für eine freigegebene Metrik oder Dimension in einer Datenansicht generieren:

* Die Beschreibung gilt für alle Datenansichten, für die die Komponente freigegeben ist, und ersetzt alle vorhandenen Beschreibungen für diese Komponente in allen anderen Datenansichten und im Manager für freigegebene Metriken und Dimensionen.

* Die Beschreibung basiert auf dem Kontext der Datenansicht, in der Sie sie erzeugen (z. B. die obersten Dimensionselemente der Datenansicht).


