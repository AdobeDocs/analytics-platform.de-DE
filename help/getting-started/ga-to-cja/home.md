---
title: Wechsel von Google Analytics 4 zu Customer Journey Analytics
description: Lernen Sie die wichtigsten Konzepte kennen, um Berichte in Customer Journey Analytics zu erhalten, die sich an Analysten richten, die mit Google Analytics 4 vertraut sind.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Wechsel von Google Analytics 4 zu Customer Journey Analytics

Dieses Handbuch hilft Analysten, die mit Google Analytics 4 vertraut sind, die entsprechenden Konzepte und Berichte in Adobe Customer Journey Analytics kennenzulernen. Wenn Sie für die technische Implementierung und nicht für das Reporting verantwortlich sind, finden Sie unter [Upgrade von einer Analyselösung eines Drittanbieters auf Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md) Anleitungen zur Einrichtung von Web-SDK und zur Datenaufnahme. Wenn Ihr Unternehmen weiterhin bestehende Google Analytics-Daten nach Adobe Experience Platform migrieren muss, finden Sie weitere Informationen unter [Migrieren von Daten aus Google Analytics](/help/use-cases/third-party/ga/overview.md).

## Hauptunterschiede zwischen GA4 und Customer Journey Analytics

GA4 und Customer Journey Analytics verfolgen dieselbe grundlegende Philosophie: Jede Benutzerinteraktion ist ein Ereignis, und die Analyse wird in einem leeren Arbeitsflächen-Tool ausgeführt, in dem Sie Dimensionen und Metriken per Drag-and-Drop verschieben können, um benutzerdefinierte Ansichten zu erstellen. Wenn Sie mit GA4 Explore vertraut sind, ist Analysis Workspace wahrscheinlich sofort erkennbar.

Die wichtigsten Unterschiede bestehen darin, dass Customer Journey Analytics über GA4 hinausgeht:

* **Kanalübergreifende Daten**: Customer Journey Analytics kann in derselben Analyse Web-Analysen mit Offline-Datenquellen (wie Callcenter-Datensätzen, CRM-Aktivitäten, Treueprogrammen oder E-Mail-Interaktionen) kombinieren. GA4 ist auf digitale Interaktionen beschränkt, die über die SDK erfasst werden.
* **Berichtszeitverarbeitung**: Customer Journey Analytics wendet Logik wie Attributionsmodelle, Sitzungsdefinitionen und Segmentregeln zur Abfragezeit und nicht zur Sammlungszeit an. Änderungen an Sitzungsdefinitionen oder Attributionsmodellen gelten rückwirkend für alle historischen Daten ohne erneute Verarbeitung.
* **Flexible Sitzungsdefinitionen**: Die Sitzungszeitüberschreitungsdauer, Ereignisse zum Sitzungsbeginn und Ereignisse zum Sitzungsende können in Customer Journey Analytics pro Datenansicht konfiguriert werden. Das Sitzungs-Timeout von GA4 ist anpassbar (30-Minuten-Standard, bis zu 7 Stunden und 55 Minuten), gilt aber für die gesamte Eigenschaft, und das Verhalten beim Starten und Beenden einer Sitzung ist unveränderlich.
* **Identitätszuordnung**: Die Zuordnungsfunktion von Customer Journey Analytics kann geräte- und kanalübergreifende Interaktionen mit derselben Person verknüpfen, wodurch genauere Personenzählungen erzeugt werden als beim integrierten Identitätsmodell von GA4.

## Konto- und Datenstruktur

GA4 und Customer Journey Analytics organisieren Daten auf Plattformebene unterschiedlich.

| GA4 | Customer Journey Analytics |
|---|---|
| Google-Konto | Adobe IMS-Organisation |
| Eigenschaft | Verbindung + Datenansicht |
| Datenstrom | [!UICONTROL Ereignisdatensatz] in Platform |
| Datenfilter | Komponentenfilter für Datenansichten |
| Untereigenschaft | Separate Datenansicht mit angewendeten Filtern |
| Rollup-Eigenschaft | Verbindung mit mehreren Datensätzen |

Der wichtigste strukturelle Unterschied besteht darin, dass eine GA4-Eigenschaft sowohl die Datenverdrahtung als auch das Reporting als ein einzelnes Objekt verarbeitet. Customer Journey Analytics unterteilt diese Konzepte in zwei verschiedene Ebenen:

* Eine **Verbindung** verknüpft einen oder mehrere Adobe Experience Platform-Datensätze mit Customer Journey Analytics. In diesem Schritt werden Daten in einem für das Reporting optimierten Format in Customer Journey Analytics aufgenommen.
* Eine **Datenansicht** wird auf einer Verbindung erstellt und definiert, welche Dimensionen, Metriken und Einstellungen für das Reporting verfügbar sind. Dies ist die Reporting-Konfigurationsebene.

Beide müssen vorhanden sein, bevor Sie Daten in Customer Journey Analytics analysieren können. In Customer Journey Analytics gibt es keine Report Suites.

## Erste Schritte in Analysis Workspace

GA4 Explore und Analysis Workspace sind beide leere, Drag-and-Drop-Analyse-Tools für die Arbeitsfläche. Das Interaktionsmodell ist dasselbe, die Terminologie unterscheidet sich geringfügig.

| GA4 erkunden | Analysis Workspace |
|---|---|
| Exploration-Arbeitsfläche | Panel |
| Diagramm- oder Visualisierungstyp | Visualisierung |
| Dimension | Dimension |
| Metrik | Metrik |
| Segment oder Filter | Segment |
| Anzahl der Ereignisse | [!UICONTROL Ereignisse] |
| Benutzende | [!UICONTROL Personen] |
| Sitzungen | [!UICONTROL Sitzungen] |

>[!TIP]
>
>GA4-Segment-Container werden als Benutzer, Sitzungen und Ereignisse bezeichnet. In Customer Journey Analytics sind die entsprechenden Container **[!UICONTROL Person]**, **[!UICONTROL Session]** und **[!UICONTROL Event]**. Die Scoping-Logik ist dieselbe.

>[!MORELIKETHIS]
>
>* [Migrieren von Daten aus Google Analytics](/help/use-cases/third-party/ga/overview.md)
