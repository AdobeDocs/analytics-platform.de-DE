---
description: Erfahren Sie, wie Sie mit Daten-Feeds Rohdaten aus Customer Journey Analytics abrufen können. Erfahren Sie mehr über die Voraussetzungen für die Verwendung von Daten-Feeds und die nächsten Schritte.
keywords: Clickstream;Daten-Feed;Daten-Feed;Data Feed
title: Überblick über Analytics-Daten-Feed
feature: Components
hide: true
hidefromtoc: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 50b82943d4c59f612240ffc8d83a8a08f09b8331
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# Übersicht über Daten-Feeds

Daten-Feeds sind eine leistungsstarke Methode, um Rohdaten aus Customer Journey Analytics zu erhalten. Diese Rohdaten können nach Ermessen Ihrer Organisation auf anderen Plattformen außerhalb von Adobe verwendet werden. Die Daten werden in stündlichen Stapeln am Ende jeder Stunde oder in täglichen Stapeln am Ende jedes Tages bereitgestellt.

## Voraussetzungen

Bevor Sie Daten-Feeds verwenden, müssen Sie alle folgenden Anforderungen erfüllen.

* Eine funktionierende Implementierung mit Daten, die in Adobe Customer Journey Analytics aufgenommen werden. <!-- For more information, see Data ingestion overview - add link -->
* Ihr Konto ist ein Analytics-Produktadministrator oder Ihr Konto gehört zu einem Produktprofil mit Zugriff auf Daten-Feeds. <!--???-->
* Ein Bucket, der auf Amazon S3, Google Cloud Platform, Azure RBAC oder Azure SAS konfiguriert ist.<!--Which cloud providers do we support??-->
* (Legacy: Nur für ältere FTP- und SFTP-Zieltypen erforderlich) Eine FTP-Site und Anmeldedaten stehen zur Verfügung (FTP-Anmeldedaten werden von Ihrem Unternehmen bereitgestellt)<!--Delete???-->

## Vergleichen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics

Die Daten-Feed-Funktion in Customer Journey Analytics unterscheidet sich von Adobe Analytics. Weitere Informationen finden Sie unter [Vergleichen von Daten-Feeds in Customer Journey Analytics und Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).


## Nächste Schritte

Die folgenden Ressourcen helfen Ihnen dabei, den grundlegenden Workflow beim Abrufen von Daten-Feeds zu verstehen. Sobald Sie den grundlegenden Workflow kennen, können Sie mit Teams in Ihrer Organisation zusammenarbeiten, um Rohdaten in einer Datenbank zu speichern oder in sie aufzunehmen.

* Best Practices für Daten-Feeds <!--add link--> Best Practices für die Erstellung und Verwaltung von Daten-Feeds.
* Erstellen eines Daten-Feeds<!--add link-->: Technische Details zum Erstellen eines Daten-Feeds und ausführlichere Erläuterung der einzelnen Felder
* Daten-Feeds verwalten<!--add link--> Weitere Informationen zum Navigieren in der Daten-Feed-Benutzeroberfläche
* Daten-Feed-Inhalte <!--add link-->: Verstehen Sie, was sich in der komprimierten Datei befindet
* Datenspaltendefinitionen <!--add link-->: Eine umfassende Liste aller verfügbaren Spalten.

<!-- Is this still the output users can download from the destination? I aske Jun. -->

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigieren in der Daten-Feed-Oberfläche](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Ermitteln Ihrer Daten-Feed-ID](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]
