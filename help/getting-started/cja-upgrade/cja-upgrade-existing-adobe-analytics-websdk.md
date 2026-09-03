---
title: Konfigurieren der vorhandenen Adobe Analytics Web-SDK-Implementierung zum Senden von Daten an Platform
description: Erfahren Sie, wie Sie Ihre bestehende Adobe Analytics Web SDK-Implementierung konfigurieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
autotag-review: '2026-05-19T08:14:03.113Z'
TQID: 'https://experienceleague.adobe.com/pexrlZnVd2fHINcn6W3XC7el5jnCrDZ08c-TLgX1L4E'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1050
ht-degree: 63%

---

# Konfigurieren der vorhandenen Adobe Analytics Web-SDK-Implementierung zum Senden von Daten an Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Entfernen von Adobe Analytics als Dienst aus dem Datenstrom"
>abstract="Wenn die Web SDK-Daten voll funktionsfähig sind, wenden Sie sich an Ihre Platform-Admins, um Adobe Analytics als Dienst aus dem Datenstrom zu entfernen. Vergewissern Sie sich zunächst, dass Ihre Benutzerinnen und Benutzer von Adobe Analytics zu Customer Journey Analytics gewechselt haben."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Wenn Ihre Adobe Analytics-Implementierung bereits Adobe Experience Platform Web SDK verwendet, können Sie mit dem Senden von Daten an Platform beginnen, indem Sie einen Datenstrom einrichten. Wenn Sie bereits Daten an Platform senden, können Sie auch einfach eine Verbindung zwischen Platform-Datensätzen und Customer Journey Analytics herstellen.


## Vor- und Nachteile

Beachten Sie die folgenden Vor- und Nachteile bei der Konfiguration Ihrer bestehenden Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform:

| Vorteile | Nachteile |
|----------|---------|
| Dies ist der bevorzugte Upgrade-Pfad, wenn Ihre Adobe Analytics-Implementierung bereits das Web-SDK verwendet.<ul><li>**Bietet alle Vorteile des Hostings von Daten in Experience Edge Network**: <p>Dazu gehören:</p><ul><li>Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von [Anwendungsfällen für die Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de) entwickelt wurde</li><li>Konsolidieren Sie die Implementierung für die Adobe CX Enterprise-Datenerfassung zwischen anderen CX Enterprise-Produkten (AJO, RTCDP usw.)</li><li>Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)</li></ul><li>**Nutzt Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, aber keine völlig neue Implementierung. Sie können die vorhandene Datenschicht und den bestehenden Code mit minimal geänderter Implementierungslogik verwenden, ohne dass sich dies auf Ihre vorhandenen Adobe Analytics-Berichte auswirkt.</li><li>**Bietet eine Option zur Nutzung eines XDM-Schemas**: Sie können Ihr vorhandenes Adobe Analytics-Schema verwenden oder ein XDM-Schema erstellen und Felder im Datenobjekt Ihrem XDM-Schema zuordnen. [XDM-Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home#xdm-schemas) sind flexible Schemata, um die erforderlichen Felder und nur die relevanten Felder zu definieren. <p>Weitere Informationen zu den Vorteilen bei der Verwendung eigener XDM-Schemata finden Sie unten unter „Verwenden Ihres eigenen XDM-Schemas“.</p></li><li>**Behält Regeln und Datenelemente bei**: Es sind zwar neue Regelaktionen erforderlich, Sie können aber vorhandene Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Zukunftssicher**: Wenn Sie sich für die Nutzung Ihres eigenen XDM-Schemas entscheiden, sind zukünftige Implementierungsaktualisierungen einfacher.</li></ul> | <ul><li>**Erfordert eine Zuordnung zum Senden von Daten an Platform**: Wenn Ihre Organisation für die Verwendung von Customer Journey Analytics bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im Datenobjekt ein Eintrag im Datastream-Zuordnungs-Tool ist, das es einem XDM-Schemafeld zuweist. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Implementierungsänderungen sind nicht erforderlich. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li><li>**Erhöht die Komplexität im**: Jedes Feld, das Sie in Zukunft hinzufügen, muss im Datenstrom XDM zugeordnet werden.<p>Jedes Mal, wenn ein neues Feld zu Ihrer Implementierung hinzugefügt wird, können Sie einen der folgenden Schritte ausführen:</p><ul><li>**Option 1** Füllen Sie eine neue beliebige eVar oder neue Prop im Datenobjekt und ordnen Sie sie dann dem gewünschten XDM-Feld zu.<p>Dieser Prozess sorgt für Konsistenz bei der Client-seitigen Implementierung, erfordert jedoch eine Zuordnung.</p></li><li>**Option 2:** Sie das Datenobjekt als Legacy-Implementierung und füllen Sie für alle neuen Felder nur das XDM-Objekt.<p>Dieser Prozess erfordert keine Zuordnung, aber er bedeutet, dass sich einige Ihrer Variablen nur in einem Datenobjekt befinden, während sich andere Variablen nur in einem XDM-Objekt befinden. Jedes Mal, wenn Sie eine Fehlerbehebung bei Ihrer Implementierung vornehmen müssen, müssen Sie zwei Stellen aufrufen. Stellen Sie sicher, dass dies in Ihren internen Workflows berücksichtigt wird.</p></li></ul> |

{style="table-layout:auto"}

## Implementierungsschritte

1. Senden von Daten von Edge Network an Platform. Senden Sie alle Variablen im AppMeasurement-Format über das Datenobjekt.

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
   | <ul><p>Vorteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.</li><p>Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.</p></ul> | <p>Nachteile der Aktualisierung auf Ihr eigenes XDM-Schema:</p><ul><li>Die Aktualisierung Ihres Schemas ist ein zeitaufwendiger Prozess, der erforderlich ist, bevor Sie Daten an Platform senden können.</li></ul> |

   +++

1. Verwenden Sie die Datenstrom-Zuordnung , um alle Felder im Datenobjekt Ihrem XDM-Schema zuzuordnen.

   Weitere Informationen finden Sie unter [Zuordnung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) in [Datenvorbereitung für die Datenerfassung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) in der Experience Platform-Dokumentation.

{{upgrade-final-step}}
