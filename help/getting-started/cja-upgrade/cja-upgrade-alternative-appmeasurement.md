---
title: Alternative Methoden beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die alternativen Methoden beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 19%

---

# Upgrade-Alternative: Verwenden der AppMeasurement-Datenerfassung mit der Experience Platform Web SDK und Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Verwenden der AppMeasurement-Logik mit der Web-SDK"
>abstract="Anstatt Daten über ein XDM-Objekt zu senden, senden Sie alle Ihre Variablen im AppMeasurement-Format über das Datenobjekt.<br><br>Mit dieser Option sparen Sie Implementierungszeit, da Sie Ihre AppMeasurement-Logik XDM zuordnen können, anstatt ein XDM-Objekt von Grund auf neu zu befüllen. Im Laufe der Zeit führt dies jedoch zu zusätzlicher Komplexität, da jedes Feld, das Sie in Zukunft hinzufügen, XDM im Datenstrom zugeordnet werden muss."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite bei der Beantwortung von Fragen in der Checkliste für das Customer Journey Analytics-Upgrade [](https://gigazelle.github.io/cja-ttv/).

Beim Upgrade auf Customer Journey Analytics empfiehlt Adobe [eine neue Implementierung der Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Abhängig von verschiedenen Faktoren, wie z. B. Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Upgrade-Schritte für Ihr Unternehmen möglicherweise nicht praktikabel.

Sie können die Datenerfassungslogik Ihrer AppMeasurement- oder Analytics-Erweiterung mit der Web-SDK verwenden, um Daten an Platform und Customer Journey Analytics zu senden, anstatt Daten mit dem XDM-Objekt zu erfassen. Diese Alternative führt jedoch im Laufe der Zeit zu zusätzlicher Komplexität.

## Vor- und Nachteile

Diese Methode schließt sich gegenseitig aus bei [Senden der gesamten Datenschicht an Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), da beide Methoden dieselbe Aufgabe erfüllen. (Diese Methode ist besser als das Senden der gesamten Datenschicht an Adobe. Er ist verfeinert, da Props und eVars alle Daten durchlaufen.__adobe.analytics._variable-name_.)

Beachten Sie die folgenden Vor- und Nachteile der Verwendung dieser Upgrade-Alternative:

| Vorteile | Nachteile |
|----------|---------|
| <ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Nicht auf die Adobe Analytics-Nomenklatur beschränkt (prop, eVar, event usw.)</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Damit können Sie Ihre AppMeasurement-Logik XDM zuordnen, anstatt ein XDM-Objekt von Grund auf neu zu befüllen.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Erhöht die Komplexität im**: Jedes Feld, das Sie in Zukunft hinzufügen, muss im Datenstrom XDM zugeordnet werden.<p>Jedes Mal, wenn ein neues Feld zu Ihrer Implementierung hinzugefügt wird, können Sie einen der folgenden Schritte ausführen:</p><ul><li>**Option 1** Füllen Sie eine neue beliebige eVar oder neue Prop im Datenobjekt und ordnen Sie sie dann dem gewünschten XDM-Feld zu.<p>Dieser Prozess sorgt für Konsistenz bei der Client-seitigen Implementierung, erfordert jedoch eine Zuordnung.</p></li><li>**Option 2:** Sie das Datenobjekt als Legacy-Implementierung und füllen Sie für alle neuen Felder nur das XDM-Objekt.<p>Dieser Prozess erfordert keine Zuordnung, aber er bedeutet, dass sich einige Ihrer Variablen nur in einem Datenobjekt befinden, während sich andere Variablen nur in einem XDM-Objekt befinden. Jedes Mal, wenn Sie eine Fehlerbehebung bei Ihrer Implementierung vornehmen müssen, müssen Sie zwei Stellen aufrufen. Stellen Sie sicher, dass dies in Ihren internen Workflows berücksichtigt wird.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Grundlegende Schritte

Die grundlegenden Schritte für die Migration einer Adobe Analytics-Implementierung (entweder AppMeasurement oder die Analytics-Erweiterung) zur Verwendung der Web-SDK zum Senden von Daten an Customer Journey Analytics sind:

1. (Optional) Migrieren Sie Ihre Adobe Analytics-Implementierung zur Verwendung der Adobe Experience Platform Web SDK und beginnen Sie mit dem Senden von Daten an Edge Network.

   Dies ist ein optionaler Schritt, mit dem Sie Ihre bestehende Adobe Analytics-Implementierung migrieren können, um die Web-SDK zu verwenden, und überprüfen können, ob alles in Adobe Analytics funktioniert. Nachdem dies konfiguriert wurde und die Daten in Adobe Analytics zufriedenstellend sind, können Sie Daten von Edge Network an Customer Journey Analytics senden.

   Diese Flexibilität ermöglicht ein methodischeres und durchdachtes Upgrade auf Customer Journey Analytics.

   Informationen dazu finden Sie in den folgenden Artikeln in der Adobe Analytics-Dokumentation:

   * [Migrieren zur Web-SDK mithilfe von Tags](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrieren zur Web-SDK mithilfe von JavaScript](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Senden von Daten von Edge Network an Customer Journey Analytics.

   1. Senden Sie alle Variablen im AppMeasurement-Format über das Datenobjekt.

      Weitere Informationen finden Sie unter [Zuordnung von Datenobjektvariablen zu Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Wenn Sie dies noch nicht getan haben, erstellen Sie ein XDM-Schema für Ihre Organisation.

      Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Schemas zur Verwendung mit Ihrer Customer Journey Analytics Web SDK-Implementierung](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Verwenden Sie die Datenstrom-Zuordnung , um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.

      Weitere Informationen finden Sie unter [Zuordnung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Datenvorbereitung für die Datenerfassung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) in der Experience Platform-Dokumentation.

