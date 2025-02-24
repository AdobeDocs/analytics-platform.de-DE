---
title: Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics
description: Erfahren Sie, wie Sie von einer Analyselösung eines Drittanbieters auf Customer Journey Analytics aktualisieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: d2d945724e7972bd4a29fa13291577bb76288229
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 14%

---

# Upgrade von der Analyselösung eines Drittanbieters auf Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Ein Produkt außerhalb von Adobe Analytics"
>abstract="Eine Implementierung, die Daten für ein anderes Produkt als Adobe Analytics erfasst, z. B. Google Analytics. Durch Auswahl dieser Option werden mehrere Optionen im Fragebogen deaktiviert, die beim Upgrade auf Customer Journey Analytics von einem Nicht-Adobe Analytics-Produkt nicht angewendet werden können."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite bei der Beantwortung von Fragen in der Checkliste für das Customer Journey Analytics-Upgrade [](https://gigazelle.github.io/cja-ttv/).

Das empfohlene Upgrade von einer anderen Analyselösung als Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung der Experience Platform Web SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit Web SDK empfiehlt Adobe auch die Aufnahme historischer Daten aus der Analyselösung eines Drittanbieters in Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Verwenden Sie den folgenden Prozess, wenn Sie von einer Analyselösung eines Drittanbieters wie Google Analytics zu Customer Journey Analytics wechseln:

1. Befolgen Sie [Schritte für detaillierte empfohlene Upgrades](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Diese Schritte sind für Unternehmen vorgesehen, die ein Upgrade von Adobe Analytics durchführen. Wenn Sie diese Schritte ausführen, verstehen Sie Folgendes:

   * Sie müssen einen Datenstrom erstellen.

   * Sie können keine Projekte und Komponenten aus einer Nicht-Adobe Analytics-Lösung migrieren.

   * Abhängig von Ihrer Analyselösung kann ein Quell-Connector für die Aufnahme historischer Daten verfügbar sein. Weitere Informationen finden Sie unter [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) in [Übersicht über Source-Connectoren](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) in der Dokumentation zu Experience Platform.


Wenden Sie sich an den Adobe-Support, wenn Sie konkretere Ratschläge, Anleitungen oder Unterstützung benötigen.

