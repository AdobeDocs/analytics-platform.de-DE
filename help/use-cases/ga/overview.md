---
title: Migrieren von Daten von Google Analytics zu Customer Journey Analytics
description: Erfahren Sie mehr über den Workflow zum Verschieben von Daten von Google Analytics in Adobe Experience Platform und zum Anzeigen von Berichten in Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 79%

---

# Migrieren von Daten von Google Analytics zu Customer Journey Analytics

Wenn Sie Customer Journey Analytics erst seit Kurzem verwenden, kann es sein, dass Ihr Unternehmen Daten auf einer anderen Analyseplattform hat, z. B. Google Analytics. Sie können diese Schritte ausführen, um diese Daten in Adobe Experience Platform zu verschieben und so Berichte in Customer Journey Analytics anzuzeigen.

Workflows sind sowohl für historische Daten als auch für die aktuelle Datenerfassung verfügbar. Je nach Datenanforderungen Ihres Unternehmens können Sie einen oder beide Workflows ausführen.

## Übertragen von historischen Daten von Google Analytics nach Adobe Experience Platform

Die Aufnahme historischer Daten (Aufstockungsdaten) umfasst den Export der Daten aus Google und den Import dieser Daten in Adobe Experience Platform. Siehe [Aufnehmen von Daten aus Google Analytics in Adobe Experience Platform](backfill.md)

Sobald Sie historische Daten erfolgreich in Platform integriert haben, können Sie entweder [Streaming aktueller Daten konfigurieren](streaming.md) oder sofort mit der Berichterstellung zu aufgestockten Daten unter Customer Journey Analytics beginnen, indem Sie [eine Verbindung erstellen](/help/connections/create-connection.md).

## Konfigurieren einer vorhandenen Google Analytics-Implementierung für Adobe Experience Platform {#configure}

Zur Erfassung aktueller (Streaming-)Daten müssen Daten an das Adobe Experience Platform-Edge Network gesendet werden, das diese Daten dann an Adobe Experience Platform weiterleitet. Siehe [Einrichten des Streaming-Vorgangs von Google Analytics-Daten nach Adobe Experience Platform](streaming.md).

## Verbindung und Datenansicht in Customer Journey Analytics konfigurieren

Nachdem Sie historische Daten erfolgreich aufgenommen und/oder die Datenerfassung in Adobe Experience Platform konfiguriert haben, können Sie [eine Verbindung erstellen](/help/connections/create-connection.md), damit Customer Journey Analytics auf diese Daten verweisen kann.

Mit dieser Verbindung können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) erstellen und n Analysis Workspace verwenden.

## Erstellen von Berichten

Nachdem Sie Dimensionen und Metriken in einer Datenansicht konfiguriert haben, können Sie damit beginnen, die gewünschten Berichte mithilfe von Analysis Workspace zu generieren. Siehe [Bericht zu Google Analytics-Daten in Customer Journey Analytics](report.md).
