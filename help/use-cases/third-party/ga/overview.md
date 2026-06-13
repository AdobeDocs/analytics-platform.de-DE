---
title: Migrieren von Daten aus Google Analytics
description: Erfahren Sie mehr über den Workflow zum Verschieben von Daten von Google Analytics in Adobe Experience Platform und zum Anzeigen von Berichten in Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 70%

---

# Migrieren von Daten aus Google Analytics

>[!BEGINSHADEBOX]

Dieses Handbuch behandelt die Datenmigration für Administratoren. Wenn Sie als Analyst Ihre GA4-Berichte in Customer Journey Analytics finden möchten, lesen Sie [Wechsel von Google Analytics 4 zu Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md) und [GA4-Berichte in Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

>[!ENDSHADEBOX]

Wenn Sie Customer Journey Analytics erst seit Kurzem verwenden, kann es sein, dass Ihr Unternehmen Daten auf einer anderen Analyseplattform hat, z. B. Google Analytics. Sie können diese Schritte ausführen, um diese Daten in Adobe Experience Platform zu verschieben und so Berichte in Customer Journey Analytics anzuzeigen.

Workflows sind sowohl für historische Daten als auch für die aktuelle Datenerfassung verfügbar. Je nach Datenanforderungen Ihres Unternehmens können Sie einen oder beide Workflows ausführen.

## Übertragen von historischen Daten von Google Analytics nach Adobe Experience Platform

Die Aufnahme historischer Daten (Aufstockungsdaten) umfasst den Export der Daten aus Google und den Import dieser Daten in Adobe Experience Platform. Siehe [Aufnehmen von Daten aus Google Analytics in Adobe Experience Platform](backfill.md)

Nachdem Sie historische Daten erfolgreich nach Platform übertragen haben, können Sie entweder [Streaming aktueller Daten konfigurieren](streaming.md) oder sofort mit dem Reporting über aufgestockte Daten in Customer Journey Analytics beginnen, indem Sie [eine Verbindung erstellen](/help/connections/create-connection.md).

## Konfigurieren einer vorhandenen Google Analytics-Implementierung für Adobe Experience Platform {#configure}

Zur Aufnahme aktueller (Streaming-)Daten müssen diese an Adobe Experience Platform Edge Network gesendet werden, von wo sie dann an Adobe Experience Platform weitergeleitet werden. Siehe [Einrichten des Streaming-Vorgangs von Google Analytics-Daten nach Adobe Experience Platform](streaming.md).

## Konfigurieren einer Verbindung und Datenansicht in Customer Journey Analytics

Nachdem Sie historische Daten erfolgreich aufgenommen und/oder die Datenerfassung in Adobe Experience Platform konfiguriert haben, können Sie [eine Verbindung erstellen](/help/connections/create-connection.md), damit Customer Journey Analytics auf diese Daten verweisen kann.

Mit dieser Verbindung können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) erstellen und n Analysis Workspace verwenden.

## Erstellen von Berichten

Nachdem Sie Dimensionen und Metriken in einer Datenansicht konfiguriert haben, können Sie damit beginnen, die gewünschten Berichte mithilfe von Analysis Workspace zu generieren. Siehe [Bericht zu Google Analytics-Daten in Customer Journey Analytics](report.md).
