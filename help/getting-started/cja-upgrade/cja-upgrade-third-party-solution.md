---
title: Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics
description: Erfahren Sie, wie Sie ein Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics durchführen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
autotag-review: '2026-05-19T08:20:34.368Z'
TQID: 'https://experienceleague.adobe.com/fwYoa9oeIs2tujyDEWUj-GaAgpZQNBwup-YsHIe-TdU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 100%

---

# Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Ein Produkt, das nicht Adobe Analytics ist"
>abstract="Eine Implementierung, die Daten für ein Produkt erfasst, das nicht Adobe Analytics ist, z. B. Google Analytics. Durch Auswahl dieser Option werden mehrere Optionen im Upgrade-Leitfaden deaktiviert, die beim Upgrade auf Customer Journey Analytics von einem Produkt, bei dem es sich nicht um Adobe Analytics handelt, nicht anwendbar sind."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Der empfohlene Prozess für das Upgrade von einer anderen Analyselösung als Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit dem Web SDK empfiehlt Adobe auch die Aufnahme historischer Daten aus der Analyselösung eines Drittanbieters in Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Verwenden Sie den folgenden Prozess, wenn Sie von einer Analyselösung eines Drittanbieters wie Google Analytics auf Customer Journey Analytics umsteigen:

1. Befolgen Sie die [detaillierten empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Diese Schritte sind für Organisationen vorgesehen, die ein Upgrade von Adobe Analytics durchführen. Beachten Sie beim Ausführen dieser Schritte Folgendes:

   * Sie müssen einen Datenstrom erstellen.

   * Sie können keine Projekte und Komponenten aus einer anderen Lösung als Adobe Analytics migrieren,

   * Abhängig von Ihrer Analyselösung kann ein Quell-Connector für die Aufnahme historischer Daten verfügbar sein. Weitere Informationen finden Sie unter [Analytics](https://experienceleague.adobe.com/de/docs/experience-platform/sources/home#analytics) in [Überblick über Source-Connectoren](https://experienceleague.adobe.com/de/docs/experience-platform/sources/home) in der Dokumentation zu Experience Platform.


Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

