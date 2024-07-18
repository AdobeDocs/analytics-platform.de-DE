---
title: Kanalübergreifende Journey-Analyse
description: Analysieren und extrahieren Sie Einblicke aus Kundeninteraktionen über die Customer Journey.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 61%

---

# Kanalübergreifende Analyse

Die kanalübergreifende Analyse ermöglicht eine zentrale, konsolidierte Ansicht des Kundenverhaltens über verschiedene Kanäle hinweg, indem Daten aus verschiedenen Web-, Mobile- und Offline-Eigenschaften vereinheitlicht werden. Beispielsweise können Sie diese konsolidierte Ansicht verwenden, um Kundeninteraktionen auf Desktop- und Mobilgeräten zu analysieren, um das Kundenverhalten zu verstehen und Einblicke zu gewinnen, um digitale Kundenerlebnisse zu optimieren. Sie können auch kanalübergreifend Kundeninteraktionen analysieren, einschließlich digitaler und Offline-Kanäle wie Support-Interaktionen und In-Store-Käufe, um die Customer Journey besser zu verstehen und zu optimieren.

## Implementierungsschritte

![Ablauf der Implementierungsschritte, wie in diesem Abschnitt beschrieben.](../assets/cca-architecture.png)

1. [Erstellen Sie Schemata](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) für aufzunehmende Daten.
1. [Erstellen Sie Datensätze](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=de) für aufzunehmende Daten.
1. [Daten in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=de) aufnehmen:
   1. Ereignisbasierte Daten ![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) von einer Website oder App über den Quell-Connector für Edge Network oder Analytics.
   2. Profildaten ![Profil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (z. B. aus einem CRM-System, Callcenter-Anwendung, Treueanwendung).
   3. Suchdaten ![lookup](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (z. B. Produktname, Kategorie aus einem Produktinformationssystem).

1. Verwenden Sie eine gemeinsame Namespace-ID für alle Datensätze. Verwenden Sie die [Zuordnung](../../stitching/overview.md) , um jeden ereignisbasierten Datensatz ![Datenaktualisierung](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) zu erhöhen, um die allgemeine ID für jede Zeile anzugeben. Beachten Sie, dass Customer Journey Analytics derzeit für die Zuordnung weder das Experience Platform-Profil noch die Identitäts-Services verwendet.
1. Führen Sie eine benutzerdefinierte Datenvorbereitung durch, um sicherzustellen, dass ein gemeinsamer Schlüssel aus Zeitreihendaten in Customer Journey Analytics aufgenommen werden kann.
1. Weisen Sie Suchdaten eine primäre ID zu, die mit einem Feld in den Ereignisdaten verknüpft werden kann. Zählt bei der Lizenzierung als Zeilen.
1. Legen Sie dieselbe primäre ID für Profildaten als primäre ID der Ereignisdaten fest.
1. [Erstellen Sie eine Verbindung](../../connections/overview.md) , um die relevanten Datensätze von Experience Platform auf Customer Journey Analytics zu erfassen.
1. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) für die Verbindung, um die spezifischen Dimensionen und Metriken auszuwählen, die in die Ansicht aufgenommen werden sollen. Die Einstellungen für Attribution und Zuordnung werden auch in der Datenansicht konfiguriert. Diese Einstellungen werden zur Berichtszeit berechnet.
1. [Erstellen Sie ein Projekt](/help/analysis-workspace/home.md) , um Dashboards und Berichte in Analysis Workspace zu konfigurieren.

## Zu beachten

Beachten Sie bei der Erstellung dieses Workflows die folgenden Punkte.

* Für die kanalübergreifende Analyse von Daten ist für jeden Datensatz derselbe ID-Namespace erforderlich.
* Für den Vereinigungsprozess verschiedener Datensätze ist ein gemeinsamer primärer Personen-/Entitätsschlüssel für die Datensätze erforderlich.
* Sekundäre schlüsselbasierte Vereinigungen werden derzeit nicht unterstützt.
* Der Stitching-Prozess ermöglicht die Neuzuweisung von Identitäten in Zeilen basierend auf vorübergehenden ID-Informationen (z. B. einer Authentifizierungs-ID) aus Datensätzen, die dieselbe beständige ID aufweisen. Dies ermöglicht die Auflösung verschiedener Datensätze zu einer einheitlichen ID für die Analyse auf der Personenebene und nicht auf der Geräte- oder Cookie-Ebene.
* Objekte und Attribute desselben XDM-Felds werden in Customer Journey Analytics zu einer Dimension zusammengeführt. Um mehrere Attribute aus verschiedenen Datensätzen mit derselben Customer Journey Analytics-Dimension zusammenzuführen, sollten die Datensätze auf dasselbe XDM-Feld oder Schema verweisen.

