---
title: Alternative Methoden beim Upgrade auf Customer Journey Analytics
description: Erfahren Sie mehr über die alternativen Methoden beim Upgrade auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 47%

---

# Alternative zum Upgrade: Verwenden der AppMeasurement-Datenerfassung mit dem Experience Platform-Web-SDK und Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Verwenden der AppMeasurement-Logik mit dem Web-SDK"
>abstract="Statt Daten über ein XDM-Objekt zu senden, senden Sie alle Variablen im AppMeasurement-Format über das Datenobjekt.<br><br>Mit dieser Option sparen Sie Implementierungszeit, da Sie die AppMeasurement-Logik XDM zuordnen können, anstatt ein XDM-Objekt von Grund auf neu zu befüllen. Im Laufe der Zeit führt dies jedoch zu zusätzlicher Komplexität, da jedes Feld, das Sie in Zukunft hinzufügen, im Datenstrom XDM zugeordnet werden muss."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="AppMeasurement-Logik so ändern, dass sie auf das Web-SDK verweist"
>abstract="Dieser Schritt wird angezeigt, weil Sie ausgewählt haben, einen Implementierungsbefehl zu verwenden. Kopieren Sie die AppMeasurement-Logik oder ändern Sie sie, um das Datenobjekt anstelle des s-Objekts zu füllen. Ändern Sie beispielsweise die Zuweisung von s.eVar1 zu „data“.__adobe.analytics.eVar1 und wiederholen Sie den Vorgang für alle Analytics-Variablen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Beim Upgrade auf Customer Journey Analytics empfiehlt Adobe [eine neue Implementierung der Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Abhängig von verschiedenen Faktoren, wie z. B. Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Upgrade-Schritte für Ihr Unternehmen möglicherweise nicht praktikabel.

Sie können die Datenerfassungslogik Ihrer AppMeasurement- oder Analytics-Erweiterung mit der Web-SDK verwenden, um Daten an Platform und Customer Journey Analytics zu senden, anstatt Daten mit dem XDM-Objekt zu erfassen. Diese Alternative führt jedoch im Laufe der Zeit zu zusätzlicher Komplexität.

## Vor- und Nachteile

Diese Methode schließt sich gegenseitig aus bei [Senden der gesamten Datenschicht an Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), da beide Methoden dieselbe Aufgabe erfüllen. (Diese Methode ist besser als das Senden der gesamten Datenschicht an Adobe. Er ist verfeinert, da Props und eVars alle Daten durchlaufen.__adobe.analytics._variable-name_.)

Beachten Sie die folgenden Vor- und Nachteile der Verwendung dieser Upgrade-Alternative:

| Vorteile | Nachteile |
|----------|---------|
| Dies ist der bevorzugte Aktualisierungspfad, wenn Ihre Adobe Analytics-Implementierung bereits die Web-SDK verwendet.<ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde. </li><li>Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren.</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.).</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet eine Option zur Nutzung eines XDM-Schemas**: Sie können Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein XDM-Schema erstellen und Felder im Datenobjekt Ihrem XDM-Schema zuordnen. [XDM-Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home#xdm-schemas) sind flexible Schemata, um die erforderlichen Felder und nur die relevanten Felder zu definieren. <p>Weitere Informationen zu den Vorteilen bei der Verwendung eigener XDM-Schemata finden Sie unten unter „Verwenden Ihres eigenen XDM-Schemas“.</p></li><li>**Behält Regeln und Datenelemente bei**: Es sind zwar neue Regelaktionen erforderlich, Sie können aber vorhandene Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Zukunftssicher**: Wenn Sie sich für die Nutzung Ihres eigenen XDM-Schemas entscheiden, sind zukünftige Implementierungsaktualisierungen einfacher.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Erhöht die Komplexität im**: Jedes Feld, das Sie in Zukunft hinzufügen, muss im Datenstrom XDM zugeordnet werden.<p>Jedes Mal, wenn ein neues Feld zu Ihrer Implementierung hinzugefügt wird, können Sie einen der folgenden Schritte ausführen:</p><ul><li>**Option 1** Füllen Sie eine neue beliebige eVar oder neue Prop im Datenobjekt und ordnen Sie sie dann dem gewünschten XDM-Feld zu.<p>Dieser Prozess sorgt für Konsistenz bei der Client-seitigen Implementierung, erfordert jedoch eine Zuordnung.</p></li><li>**Option 2:** Sie das Datenobjekt als Legacy-Implementierung und füllen Sie für alle neuen Felder nur das XDM-Objekt.<p>Dieser Prozess erfordert keine Zuordnung, aber er bedeutet, dass sich einige Ihrer Variablen nur in einem Datenobjekt befinden, während sich andere Variablen nur in einem XDM-Objekt befinden. Jedes Mal, wenn Sie eine Fehlerbehebung bei Ihrer Implementierung vornehmen müssen, müssen Sie zwei Stellen aufrufen. Stellen Sie sicher, dass dies in Ihren internen Workflows berücksichtigt wird.</p></li></ul> |

{style="table-layout:auto"}

## Grundlegende Schritte

Die grundlegenden Schritte für die Migration einer Adobe Analytics-Implementierung (entweder AppMeasurement oder die Analytics-Erweiterung) zur Verwendung der Web-SDK zum Senden von Daten an Customer Journey Analytics sind:

1. Migrieren Sie Ihre Adobe Analytics-Implementierung zur Verwendung der Adobe Experience Platform Web SDK und beginnen Sie mit dem Senden von Daten an Edge Network.

   In diesem Schritt können Sie Ihre bestehende Adobe Analytics-Implementierung migrieren, um die Web-SDK zu verwenden. Sie können optional Daten an Adobe Analytics senden, um zu überprüfen, ob alles in Adobe Analytics funktioniert, bevor Sie Daten an Customer Journey Analytics senden. Nachdem dies konfiguriert wurde und die Daten in Adobe Analytics zufriedenstellend sind, können Sie Daten von Edge Network an Customer Journey Analytics senden.

   Diese Flexibilität ermöglicht ein methodischeres und durchdachtes Upgrade auf Customer Journey Analytics.

   Informationen dazu finden Sie in den folgenden Artikeln in der Adobe Analytics-Dokumentation:

   * [Migrieren zur Web-SDK mithilfe von Tags](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrieren zur Web-SDK mithilfe von JavaScript](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Senden von Daten von Edge Network an Platform.

   1. Senden Sie alle Variablen im AppMeasurement-Format über das Datenobjekt.

      Weitere Informationen finden Sie unter [Zuordnung von Datenobjektvariablen zu Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Wählen Sie Ihr Schema.

      Sie können wählen, ob Sie Ihr bestehendes Adobe Analytics-Schema verwenden möchten, oder ein XDM-Schema erstellen, das bei der Verwendung anderer Platform-Services besser an die Anforderungen Ihres Unternehmens angepasst wird.

      Adobe empfiehlt, ein XDM-Schema zu erstellen. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Schemas zur Verwendung mit Ihrer Customer Journey Analytics Web SDK-Implementierung](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

      +++Verwenden des Adobe Analytics-Schemas

      | Vorteile | Nachteile |
      |----------|---------|
      | <p>Vorteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Einfaches Upgrade<p>Wenn Sie mit dem Adobe Experience Platform Web SDK bereits Daten an Adobe Analytics senden, können Sie Ihrem Datastream einen zusätzlichen Dienst hinzufügen, um Daten an Adobe Experience Platform zu senden (der dann in Ihrer Customer Journey Analytics-Konfiguration verwendet werden kann).</p></li></ul> | <p>Nachteile der Verwendung des Adobe Analytics-Schemas:</p><ul><li>Die Nutzung des Adobe Analytics-Schemas schränkt Sie zwar nicht in Bezug auf seine Verwendung mit anderen Platform-Anwendungen ein, führt aber zu einem Schema, das unnötig komplex ist. Dies liegt daran, dass das Adobe Analytics-Schema viele Adobe Analytics-spezifische Objekte enthält, die wahrscheinlich nicht von Ihrer Organisation verwendet werden.<p>Wenn Änderungen am Schema erforderlich sind, müssen Sie Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></li></ul> |

+++

      +++Erstellen eines XDM-Schemas

      | Vorteile | Nachteile |
      |----------|---------|
      | <ul><p>Vorteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></ul> | <p>Nachteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie mit dem Senden von Daten an Platform beginnen.</li></ul> |

+++

   1. Verwenden Sie die Datenstrom-Zuordnung , um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.

      Weitere Informationen finden Sie unter [Zuordnung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Datenvorbereitung für die Datenerfassung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) in der Experience Platform-Dokumentation.

{{upgrade-final-step}}.




