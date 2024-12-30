---
title: Konfigurieren des Streaming-Vorgangs von Google Analytics-Daten
description: Erfahren Sie, wie Sie Ihre Implementierung einrichten, um eine Google-Datenschicht nach Adobe Experience Platform zu senden.
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 89%

---

# Konfigurieren des Streaming-Vorgangs von Google Analytics-Daten

Auf dieser Seite wird beschrieben, wie Sie Ihre Live-Daten von Google Analytics in Adobe Experience Platform aufnehmen und so in einer Datenansicht in Customer Journey Analytics auf diesen Datensatz verweisen können. Sie können die Schritte auf dieser Seite mit [der Aufnahme von historischen Google Analytics-Daten in Adobe Experience Platform](backfill.md) kombinieren, wodurch ein Datensatz mit historischen Daten generiert wird. Kombinieren Sie einen Streaming-Datensatz mit einem Aufstockungsdatensatz, um eine lückenlose Ansicht historischer und aktueller Daten in Customer Journey Analytics zu erhalten.

Die Konfiguration der Datenerfassung umfasst die folgenden Schritte:

1. Implementieren von [Tags für Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de). Siehe [Schnellstartanleitung](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=de), um eine einfache Implementierung einzurichten.
1. Installieren der [Google Data Layer-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=de). Diese Erweiterung ist eine Alternative zur Installation der Web SDK-Erweiterung und ist speziell für eine Google-Datenschicht konzipiert.
1. [Erstellen eines Datenstroms](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=de) in der Adobe Experience Platform-Datenerfassung. Konfigurieren des Datenspeichers, um Daten an Adobe Experience Platform zu senden Aktuell müssen Sie jedes Google-Datenschichtobjekt dem entsprechenden XDM-Feld hier zuordnen. Adobe plant, in Zukunft einen einfacheren Zuordnungs-Workflow zur Verfügung zu stellen.

Nachdem Sie die gewünschten Tags auf Ihrer Site implementiert und veröffentlicht haben, können Sie mit [Verbindung erstellen](/help/connections/create-connection.md) und dann [Datenansicht erstellen](/help/data-views/create-dataview.md) fortfahren.
