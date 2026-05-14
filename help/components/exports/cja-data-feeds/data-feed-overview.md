---
description: Erfahren Sie, wie Sie mit Daten-Feeds Rohdaten aus Customer Journey Analytics abrufen können. Erfahren Sie mehr über die Voraussetzungen für die Verwendung von Daten-Feeds und die nächsten Schritte.
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Überblick über Analytics-Daten-Feed
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 21%

---

# Übersicht über Daten-Feeds

Daten-Feeds sind eine leistungsstarke Methode, um Rohdaten aus Customer Journey Analytics zu erhalten. Sie können diese Rohdaten nach Ermessen Ihres Unternehmens auf anderen Plattformen außerhalb von Adobe verwenden. Die Daten werden in stündlichen Stapeln am Ende jeder Stunde oder in täglichen Stapeln am Ende jedes Tages bereitgestellt.

## Voraussetzungen

Stellen Sie sicher, dass Sie alle folgenden Anforderungen erfüllen, bevor Sie Daten-Feeds verwenden:

* Eine funktionierende Implementierung mit Daten, die in Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link --> aufgenommen werden
* Ihr Konto ist ein Analytics-Produktadministrator oder Ihr Konto gehört zu einem Produktprofil mit Zugriff auf Daten-Feeds <!--???-->
* Ein Bucket, der für {DNL Amazon S3}, {DNL Google Cloud Platform}, {DNL Azure RBAC} oder {DNL Azure SAS}

## Erste Schritte

Um mit der Verwendung von Daten-Feeds in Customer Journey Analytics zu beginnen, sollten Sie zunächst verstehen, wie sich Daten-Feeds in Customer Journey Analytics von Daten-Feeds in Adobe Analytics unterscheiden. Nachdem Sie die Unterschiede verstanden haben, können Sie Adobe Analytics-Daten-Feeds Customer Journey Analytics zuordnen und dann mit der Erstellung eines Daten-Feeds beginnen.

1. [Verstehen Sie die Unterschiede zwischen Daten-Feeds in Customer Journey Analytics und Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Ordnen Sie Adobe Analytics-Daten-Feed-Spalten Customer Journey Analytics zu](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Erstellen eines Daten-Feeds](/help/components/exports/cja-data-feeds/create-feed.md).
