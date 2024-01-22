---
title: Standardkomponentenreferenz
description: Details und Informationen zu allen Standardkomponenten, die Sie jeder Datenansicht hinzufügen können.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 20f48259881bade1978909610055d6b20b894092
workflow-type: ht
source-wordcount: '980'
ht-degree: 100%

---

# Standardkomponentenreferenz

Die meisten Dimensionen und Metriken in Customer Journey Analytics basieren auf Schemaelementen aus Ihrem Adobe Experience Platform-Datensatz. Es stehen jedoch mehrere Komponenten zur Verfügung, die unabhängig von der verwendeten Verbindung zu einer Datenansicht hinzugefügt werden können.

[!UICONTROL Standardkomponenten] sind Komponenten, die nicht aus Datensatz-Schemafeldern, sondern vom System generiert werden. Einige Systemkomponenten sind erforderlich, um die Reporting-Funktionen in Analysis Workspace zu erleichtern, wohingegen andere Systemkomponenten optional sind.

![Standard-Komponenten](assets/dataview-standard-components.png)

## Erforderliche Standardkomponenten {#required}

Diese erforderlichen Standardkomponenten werden standardmäßig jeder Datendatei-Ansicht hinzugefügt. Sie sind von wesentlicher Bedeutung für die Reporting-Funktionen, die Customer Journey Analytics bietet.

| Name der Komponente | Dimension oder Metrik | Hinweise |
| --- | --- | --- |
| [!UICONTROL Personen] | Metrik | Basiert auf der Personen-ID, die in einer [!UICONTROL Verbindung] angegeben ist. |
| [!UICONTROL Sitzungen] | Metrik | Basiert auf den Sitzungseinstellungen der Datenansicht. |
| [!UICONTROL Ereignisse] | Metrik | Die Anzahl der Zeilen aus allen Ereignisdatensätzen in einer [!UICONTROL Verbindung]. |
| [!UICONTROL Minute] | Dimension | Die Minute, in der ein bestimmtes Ereignis aufgetreten ist (abgerundet). Das erste Dimensionselement ist die erste Minute im Datumsbereich und das letzte Dimensionselement die letzte Minute im Datumsbereich. |
| [!UICONTROL Stunde] | Dimension | Die Stunde, in der ein bestimmtes Ereignis aufgetreten ist (abgerundet). Das erste Dimensionselement ist die erste Stunde im Datumsbereich und das letzte Dimensionselement die letzte Stunde im Datumsbereich. |
| [!UICONTROL Tag] | Dimension | Der Tag, an dem ein bestimmtes Ereignis aufgetreten ist. Das erste Dimensionselement ist der erste Tag im Datumsbereich und das letzte Dimensionselement der letzte Tag im Datumsbereich. |
| [!UICONTROL Woche] | Dimension | Die Woche, in der ein bestimmtes Ereignis aufgetreten ist. Das erste Dimensionselement ist die erste Woche im Datumsbereich und das letzte Dimensionselement die letzte Woche im Datumsbereich. |
| [!UICONTROL Monat] | Dimension | Der Monat, in dem ein bestimmtes Ereignis aufgetreten ist. Das erste Dimensionselement ist der erste Monat im Datumsbereich und das letzte Dimensionselement der letzte Monat im Datumsbereich. |
| [!UICONTROL Quartal] | Dimension | Das Quartal, in dem ein bestimmtes Ereignis aufgetreten ist. Das erste Dimensionselement ist das erste Quartal im Datumsbereich und das letzte Dimensionselement das letzte Quartal im Datumsbereich. |
| [!UICONTROL Jahr] | Dimension | Das Jahr, in dem ein bestimmtes Ereignis aufgetreten ist. Das erste Dimensionselement ist das erste Jahr im Datumsbereich und das letzte Dimensionselement das letzte Jahr im Datumsbereich. |
| [!UICONTROL Sitzung beginnt] | Metrik | Die Anzahl der Ereignisse, die das erste Ereignis einer Sitzung waren. Bei Verwendung in einer Filterdefinition (wie beispielsweise „[!UICONTROL Sitzung beginnt] existiert“) wird nur das erste Ereignis jeder Sitzung gefiltert.<p>Diese Komponente muss in Ihrer Datenansicht für die folgende [berechnete Metrik](/help/components/calc-metrics/default-calcmetrics.md) enthalten sein, um in Workspace verfügbar zu sein: <ul><li>Startrate der Sitzung</li></p> |
| [!UICONTROL Sitzung endet] | Metrik | Die Anzahl der Ereignisse, die das letzte Ereignis einer Sitzung waren. Ähnlich wie [!UICONTROL Sitzung beginnt] kann dies auch in einer Filterdefinition verwendet werden, um bis zum letzten Ereignis jeder Sitzung zu filtern.<p>Diese Komponente muss in Ihrer Datenansicht für die folgende [berechnete Metrik](/help/components/calc-metrics/default-calcmetrics.md) enthalten sein, um in Workspace verfügbar zu sein: <ul><li>Endrate der Sitzung</li></p> |
| [!UICONTROL Aufgewendete Zeit (Sekunden)] | Metrik | Addiert die Zeit zwischen zwei verschiedenen Werten für eine Dimension.<p>Diese Komponente muss in Ihrer Datenansicht für die folgende [berechnete Metrik](/help/components/calc-metrics/default-calcmetrics.md) enthalten sein, um in Workspace verfügbar zu sein: <ul><li>Aufgewendete Zeit pro Person  </li><li>Aufgewendete Zeit pro Sitzung</li></p> |

{style="table-layout:auto"}

## Optionale Standardkomponenten {#optional}

Optionale Standardkomponenten sind unter **[!UICONTROL Datenansichten]** > **[!UICONTROL Datenansicht bearbeiten]** > Registerkarte **[!UICONTROL Komponenten]** > Registerkarte **[!UICONTROL Standardkomponenten]** verfügbar.

| Name der Komponente | Dimension oder Metrik | Anmerkungen und Werte |
| --- | --- | --- |
| [!UICONTROL Vormittag/Nachmittag] | Zeitunterteilungsdimension | Vormittag oder Nachmittag |
| [!UICONTROL Batch-ID] | Dimension | Stellt den Experience Platform-Batch dar, zu dem ein [!UICONTROL Ereignis] gehört hat. |
| [!UICONTROL Datensatz-ID] | Dimension | Stellt den Experience Platform-Datensatz dar, zu dem ein [!UICONTROL Ereignis] gehört hat. |
| [!UICONTROL Tag des Monats] | Zeitunterteilungsdimension | 1–31 |
| [!UICONTROL Wochentag] | Zeitunterteilungsdimension | Montag, Dienstag, Mittwoch, Donnerstag, Freitag, Samstag, Sonntag |
| [!UICONTROL Tag des Jahres] | Zeitunterteilungsdimension | 1–366 |
| [!UICONTROL Stunde des Tages] | Zeitunterteilungsdimension | 0–23 |
| [!UICONTROL  Monat des Jahres] | Zeitunterteilungsdimension | Januar–Dezember |
| [!UICONTROL Erstmalige Sitzungen] | Metrik | Die definierte erste Sitzung einer Person im Reporting-Zeitraum. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) |
| [!UICONTROL Rückkehrende Sitzungen] | Metrik | Die Anzahl der Sitzungen, die nicht die erste Sitzung einer Person waren. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) |
| [!UICONTROL Personen-ID] | Dimension | Für jedes in Experience Platform definierte Datensatzschema kann ein eigener Satz von einer oder mehreren Identitäten definiert und mit einem Identity-Namespace verknüpft werden. Jede dieser Identitäten kann als Personen-ID verwendet werden. Beispiele sind Cookie-ID, zugeordnete ID, Benutzer-ID und Trackingcode. Die Dimension [!UICONTROL Personen-ID] ist die Grundlage für die Kombination von Datensätzen und die Identifizierung von eindeutigen Personen in Customer Journey Analytics.<p>Mögliche Anwendungsfälle sind:<ul><li>Erstellen eines Filters für einen bestimmten Personen-ID-Wert, um alles nach dem Verhalten dieses Benutzers zu filtern.</li><li>Debugging: Prüfen, ob die Daten für eine bestimmte Cookie-ID (oder eine bestimmte Kunden-ID) vorhanden sind.</li><li>Identifizieren der Benutzer, die bei einem Callcenter angerufen haben.</li></ul> |
| [!UICONTROL Personen-ID-Namespace] | Dimension | Aus welchem ID-Typ die [!UICONTROL Personen-ID] besteht. Beispiele sind: `email address`, `cookie ID` und `Analytics ID` |
| [!UICONTROL Quartal des Jahres] | Zeitunterteilungsdimension | Q1, Q2, Q3, Q4 |
| [!UICONTROL Sitzung wiederholen] | Metrik | Die Anzahl der Sitzungen, die nicht die allererste Sitzung einer Person waren. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) |
| [!UICONTROL Sitzungstyp] | Dimension | Diese Dimension hat zwei Werte: 1) [!UICONTROL Erstmalig] und 2) Wiederkehrend. Der Zeileneintrag [!UICONTROL Erstmalig] enthält das gesamte Verhalten (d. h. die Metriken für diese Dimension) in einer Sitzung, die als erste Sitzung einer Person definiert wurde. Alles andere ist im Zeileneintrag [!UICONTROL Wiederkehrend] enthalten (vorausgesetzt, dass alles zu einer Sitzung gehört). Wenn Metriken nicht Teil einer Sitzung sind, fallen sie in den Bucket „Nicht zutreffend“ für diese Dimension. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) |
| [!UICONTROL Aufgewendete Zeit pro Ereignis] | Dimension | Sammelt die Metrik [!UICONTROL Verwendete Zeit] in Buckets des Typs [!UICONTROL Ereignis]. |
| [!UICONTROL Aufgewendete Zeit pro Sitzung] | Dimension | Fasst die Metrik [!UICONTROL Aufgewendete Zeit] in Behältern des Typs [!UICONTROL Sitzung] zusammen. |
| [!UICONTROL Aufgewendete Zeit pro Person] | Dimension | Fasst die Metrik [!UICONTROL Aufgewendete Zeit] in Behältern des Typs [!UICONTROL Person] zusammen. |
| [!UICONTROL Wochenende]/[!UICONTROL Wochentag] | Zeitunterteilungsdimension | Wochenende oder Wochentag |

{style="table-layout:auto"}
