---
title: Upgrade von Adobe Analytics auf Customer Journey Analytics
description: Erfahren Sie mehr über die empfohlenen Schritte beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 57%

---

# Upgrade von Adobe Analytics auf Customer Journey Analytics

Beim Upgrade von Adobe Analytics auf Customer Journey Analytics können Sie die [empfohlenen Upgrade-Schritte](#recommended-upgrade-steps-for-most-organizations) befolgen. Für die individuellen Bedingungen Ihrer Organisation können Sie alternativ [Upgrade-Schritte dynamisch generieren](#dynamically-generate-upgrade-steps-for-your-organization).

## Empfohlene Upgrade-Schritte für die meisten Organisationen {#upgrade-process}

Der empfohlene Prozess für das Upgrade von Adobe Analytics auf Customer Journey Analytics ist eine neue Implementierung des Experience Platform-Web-SDK, der bevorzugten Datenerfassungsmethode für Customer Journey Analytics. In Verbindung mit dem Web-SDK empfiehlt Adobe außerdem die Verwendung des Analytics-Quell-Connectors, der Sie bei der Umstellung auf Customer Journey Analytics unterstützt. Verwenden Sie den Analytics-Quell-Connector, um historische Daten aus Adobe Analytics beizubehalten und einen direkten Datenvergleich durchzuführen.

Nachdem Sie mit dem Experience Platform-Web-SDK genügend historische Daten gesichert haben und vollständig auf Customer Journey Analytics umgestiegen sind, kann der Analytics-Quell-Connector deaktiviert und ausschließlich das Web-SDK verwendet werden.

>[!NOTE]
>
>Wenn die in diesem Abschnitt beschriebenen Upgrade-Schritte für Ihr Unternehmen nicht sinnvoll sind, können Sie im Customer Journey Analytics Upgrade Guide dynamisch Upgrade-Schritte generieren, die auf die individuellen Umstände Ihres Unternehmens zugeschnitten sind. (Um über Customer Journey Analytics auf das Handbuch zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Workspace]** und dann **[!UICONTROL Upgrade auf Customer Journey Analytics]** im linken Bereich aus. Folgen Sie den Anweisungen auf dem Bildschirm.)

### Allgemein empfohlener Upgrade-Prozess {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Historische Daten aus Adobe Analytics"
>abstract="Übertragen Ihrer historischen Daten aus Adobe Analytics-Report Suites in Adobe Experience Platform und Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementieren des Experience Platform-Web-SDK (für die fortlaufende Datenerfassung)**

   Eine neue Implementierung des Experience Platform-Web-SDK ist die beste Möglichkeit, Daten für Customer Journey Analytics zu erfassen. Es bietet die beste Grundlage für eine optimale Nutzung von Customer Journey Analytics, da es die leistungsfähigste, unkomplizierteste und zukunftssicherste Methode zur Implementierung von Customer Journey Analytics ist.

   * Reporting und Datenverfügbarkeit sind hochperformant, da Adobe Experience Platform zur Unterstützung von Anwendungsfällen für die Echtzeit-Personalisierung entwickelt wurde

   * Sie können die Implementierung für die Adobe Experience Cloud-Datenerfassung zwischen anderen Experience Cloud-Produkten (AJO, RTCDP usw.) konsolidieren

   * Es besteht keine Abhängigkeit von der Adobe Analytics-Nomenklatur (Prop, eVar, Ereignis usw.)

1. **Einrichten des Adobe Analytics-Quell-Connectors (zum Übermitteln historischer Daten)**

   Für einen reibungslosen Wechsel zur Verwendung des Experience Platform-Web-SDK mit Customer Journey Analytics empfiehlt Adobe außerdem die Verwendung des Adobe Analytics-Quell-Connectors. Auf diese Weise können Sie historische Daten beibehalten und Daten aus Ihrer bestehenden Adobe Analytics-Implementierung in Customer Journey Analytics gemeinsam mit den Daten aus Ihrer neuen Experience Platform-Web-SDK-Implementierung anzeigen.

   Der Analytics-Quell-Connector ermöglicht Folgendes:

   * Übertragen Ihrer historischen Daten aus Adobe Analytics-Report Suites in Adobe Experience Platform und Customer Journey Analytics.

     Sie können den Analytics-Quell-Connector so lange ausführen, wie Sie die historischen Daten aus Adobe Analytics beibehalten müssen.

   * Anzeigen der mit Ihrer ursprünglichen Adobe Analytics-Implementierung (entweder AppMeasurement, Analytics-Erweiterung oder Web-SDK-Erweiterung) erfassten Daten in Customer Journey Analytics. Sie können diese Daten direkt mit denen Ihrer neuen Web-SDK-Implementierung vergleichen.

     Sie können den Analytics-Quell-Connector so lange ausführen, bis Sie mit den Unterschieden vertraut sind. <!--elaborate on what those differences are? -->

   Der Analytics-Quell-Connector ist als eigenständige Implementierung keine empfohlene langfristige Methode zur Verwendung von Customer Journey Analytics. Dies liegt an der hohen Latenz, überladenen und komplexen Schemata, der Abhängigkeit von der Adobe Analytics-Nomenklatur (prop, eVar usw.) und der Schwierigkeit, schließlich vom Analytics-Quell-Connector zur empfohlenen Web-SDK-Implementierung zu wechseln.

### Detaillierte empfohlene Upgrade-Schritte

Die folgenden Schritte beschreiben den empfohlenen Prozess für das Upgrade von Adobe Analytics auf Customer Journey Analytics.

Jeder Schritt bietet eine allgemeine Erklärung eines detaillierteren Prozesses. Folgen Sie dem Link für jeden Schritt und führen Sie die zugehörigen Aufgaben aus. Kehren Sie dann zu dieser Seite zurück und fahren Sie mit dem nächsten Schritt im Prozess fort.

1. [Planen Sie Ihre XDM-Schemaarchitektur](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Erstellen Sie das gewünschte benutzerdefinierte Schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Beachten Sie beim Erstellen Ihres Schemas die folgenden Optionen:

   * Wenn Sie Customer Journey Analytics mit RTCDP integrieren möchten, müssen Sie die Option **[!UICONTROL Profil]** für Ihr Schema aktivieren, wie in [Erstellen eines XDM-Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) beschrieben. Wenn diese Option aktiviert ist und Daten auf der Basis dieses Schemas in Datensätze aufgenommen werden, werden diese Daten zum Echtzeit-Kundenprofil hinzugefügt.

   * Wenn Sie Streaming-Mediendaten einbeziehen möchten, müssen Sie [Ihr Schema für die Aufnahme und Verwendung von Streaming-Daten konfigurieren](/help/data-ingestion/streaming.md).

1. [Erstellen Sie einen Datensatz in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Optional) Wenn Sie Klassifizierungsdaten in Adobe Analytics verwenden, können Sie Ihrem Datensatz in Customer Journey Analytics Klassifizierungsdaten hinzufügen.

   Erstellen Sie dazu [für jede Dimension mit Klassifizierungsdaten einen Lookup-Datensatz](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Bei Adobe Analytics-Implementierungen mit AppMeasurement oder der Analytics-Erweiterung (Tags) [erstellen Sie einen Datenstromsin Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Bei Adobe Analytics-Implementierungen mit der Web-SDK ist bereits ein Datenstrom vorhanden. Weitere Informationen finden Sie unter [Konfigurieren Ihrer bestehenden Adobe Analytics Web SDK-Implementierung zum Senden von Daten an Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Fügen Sie Adobe Experience Platform als Service zu Ihrem Datenstrom hinzu](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Optional) Wenn Sie Customer Journey Analytics mit Adobe Journey Optimizer integrieren möchten, verwenden Sie das Personalisierungsobjekt in Ihrer Implementierung zur Verwendung in Adobe Journey Optimizer.

1. Erweitern Sie den Abschnitt, in dem beschrieben wird, wie Sie das Experience Platform-Web-SDK für Ihre Customer Journey Analytics-Implementierung implementieren möchten, und führen Sie dann die zugehörigen Schritte aus:

   +++Manuelle Implementierung (JS-Datei)

   1. [alloy.js zu Ihrer Site hinzufügen](https://experienceleague.adobe.com/de/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Befüllen Sie ein XDM-Objekt und senden Sie es an den Datenstrom.

   +++

   +++Tags

   1. [Erstellen Sie eine Tag-Eigenschaft und fügen Sie die Adobe Experience Platform-Web-SDK-Erweiterung hinzu](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Adobe Experience Platform-Web-SDK-Erweiterung zu Ihrer Tag-Eigenschaft hinzufügen](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Loader-Tag auf Ihrer Site implementieren](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Hinzufügen von XDM-Datenerfassungslogik zum Tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

   +++

+++ API

   1. Edge Network-API verwenden, um Daten zum gewünschten Datenstrom zu senden.

+++

1. [Validieren, dass Web-SDK-Implementierung Daten zum Datensatz sendet](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Verbindung in Customer Journey Analytics erstellen](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Optional) Webdaten mit Daten aus anderen Kanälen verbinden, z. B. Daten des Callcenters.

   Sie erreichen dies, indem Sie Ihrer Customer Journey Analytics-Verbindung zusätzliche Datensätze hinzufügen, wie unter [Importieren von Callcenter- und Web-Daten](/help/use-cases/cross-channel/call-center.md) beschrieben.

1. [Datenansicht in Customer Journey Analytics erstellen](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Überprüfen Sie, ob Daten in die Datenansicht in Customer Journey Analytics fließen](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. Verwenden Sie in Ihrer Adobe Analytics[Umgebung das Analytics-Inventar](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/analytics-inventory), um einen umfassenden Überblick über Ihre Adobe Analytics-Umgebung zu erhalten, einschließlich der Anzahl der Projekte und Komponenten, Report Suites, Benutzer und mehr.

1. [Projekte und Komponenten migrieren](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Optional) Wenn Sie Marketing-Kanäle in Adobe Analytics verwenden, können Sie [ein abgeleitetes Marketing-Kanal-Feld in Customer Journey Analytics erstellen](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Abgeleitete Felder sind ein wichtiger Aspekt des Echtzeit-Reportings in Adobe Customer Journey Analytics. Mit einem abgeleiteten Feld können Sie mithilfe eines anpassbaren Regel-Builders spontan (häufig komplexe) Datenmanipulationen definieren.

   Eine Verwendung abgeleiteter Felder besteht in der Definition eines abgeleiteten Marketing-Kanal-Felds, das den richtigen Marketing-Kanal auf der Grundlage einer oder mehrerer Bedingungen bestimmt (z. B. URL-Parameter, Seiten-URL, Seitenname).

   Verwenden Sie [die Funktionsvorlage Marketing-Kanäle](/help/data-views/derived-fields/derived-fields.md#marketing-channels) in abgeleiteten Feldern, um schnell ein abgeleitetes Feld für Marketing-Kanäle zu erstellen.

1. Vergleichen Sie Daten in Adobe Analytics aus Ihrer alten Implementierung mit Daten in Customer Journey Analytics aus Ihrer neuen Implementierung und stellen Sie sicher, dass Sie die Unterschiede und ihre Ursachen verstehen. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Übertragen von historischen Daten aus Adobe Analytics mithilfe des Analytics-Quell-Connectors:

   >[!NOTE]
   >
   >Führen Sie die folgenden Schritte aus, wenn Sie zuvor noch keinen Analytics-Quell-Connector erstellt haben.
   >
   >Wenn Sie bereits den Analytics-Quell-Connector mit Customer Journey Analytics verwenden, führen Sie die Schritte unter [Wechsel vom Analytics-Quell-Connector zum Web-SDK für Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) aus.

   1. [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Wenn Sie noch nicht über einen Analytics-Quell-Connector verfügen, [erstellen Sie den Analytics-Quell-Connector und ordnen Sie Ihrem XDM-Schema Felder zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Oder

      Wenn Sie bereits über einen Analytics-Quell-Connector verfügen, [ordnen Sie Ihrem XDM-Schema Felder aus dem Quell-Connector zu](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Fügen Sie den Datensatz des Analytics-Quell-Connectors zur Verbindung hinzu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Benutzer-Onboarding planen.

   Wie in Adobe Analytics ist auch in Customer Journey Analytics der Analysis Workspace das wichtigste Werkzeug für die Benutzenden. Es gibt jedoch einige wesentliche Unterschiede bei der Verwendung von Analysis Workspace in Customer Journey Analytics, die die Benutzenden kennen sollten.

   Sie sollten Ihren Benutzenden ausreichend Zeit (3–6 Monate) geben, um sich mit den wichtigsten Unterschieden von Analysis Workspace in Customer Journey Analytics vertraut zu machen.

   Informationen zu einigen der wichtigsten Unterschiede zwischen Adobe Analytics und Customer Journey Analytics finden Sie im [Benutzerhandbuch für Adobe Analytics-Benutzende](/help/getting-started/aa-to-cja-user.md).

1. Erfahren Sie mehr über [die Unterstützung von Funktionn in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). Die meisten Adobe Analytics-Funktionen werden in Customer Journey Analytics unterstützt, und viele zusätzliche Funktionen sind in Customer Journey Analytics verfügbar.

1. Deaktivieren Sie Adobe Analytics, wenn Ihre Customer Journey Analytics-Web-SDK-Implementierung abgeschlossen ist und Sie mit den erfassten Daten vertraut sind.

   Adobe empfiehlt, die Adobe Analytics-Umgebung nach der Implementierung von Customer Journey Analytics noch eine gewisse Zeit lang in Betrieb zu halten.

   Weitere Informationen zur Verwendung von Adobe Analytics während und nach einem Upgrade sowie zum empfohlenen Zeitpunkt für die Deaktivierung von Adobe Analytics finden Sie unter [Beurteilen, wie lange Adobe Analytics nach dem Upgrade auf Customer Journey Analytics benötigt wird](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Dynamische Generierung von Upgrade-Schritten für Ihre Organisation

Abhängig von verschiedenen Faktoren, wie z. B. Timeline- und Ressourcenbeschränkungen, sind die empfohlenen Upgrade-Schritte, die unter [Grundlegendes zu den empfohlenen Upgrade-Schritten](#recommended-upgrade-steps-for-most-organizations) beschrieben werden, möglicherweise für Ihr Unternehmen nicht praktikabel. In diesem Fall können Sie die Upgrade-Schritte für die individuellen Bedingungen in Ihrem Unternehmen dynamisch generieren. Der Prozess zum Generieren dieser Schritte unterscheidet sich, je nachdem, ob Sie bereits Zugriff auf Customer Journey Analytics haben.

### Für Kunden, die Zugriff auf Customer Journey Analytics haben

So generieren Sie Upgrade-Schritte dynamisch für die individuellen Bedingungen Ihrer Organisation:

1. Vervollständigen Sie das Customer Journey Analytics-Upgrade-Handbuch.

   Wählen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Workspace]** und dann **[!UICONTROL Upgrade auf Customer Journey Analytics]** im linken Bereich aus. Befolgen Sie die Anweisungen auf dem Bildschirm.

   Nach Abschluss dieses Upgrade-Handbuchs erhalten Sie eine schrittweise Anleitung mit den optimalen Upgrade-Schritten, die speziell auf die Anforderungen Ihres Unternehmens zugeschnitten sind. Dies sind die Upgrade-Schritte, die am besten zu Ihrer bestehenden Adobe Analytics-Umgebung und Ihren Zielen für Customer Journey Analytics passen. Die Upgrade-Schritte sind als freigebbarer Link oder als herunterladbare CSV-Datei verfügbar.

1. Befolgen Sie die generierte schrittweise Anleitung zum Upgrade auf Customer Journey Analytics.

### Für Kunden, die noch keinen Zugriff auf Customer Journey Analytics haben

So generieren Sie Upgrade-Schritte dynamisch für die individuellen Bedingungen Ihrer Organisation:

1. Wenden Sie sich an Ihr Adobe-Accountteam , um das Customer Journey Analytics-Upgrade-Handbuch abzuschließen.

   Ihr Adobe Account Team führt Sie durch das Upgrade-Handbuch und stellt Ihnen eine CSV-Datei zur Verfügung, die die Fragen, Antworten und die dynamisch generierten Upgrade-Schritte enthält, die für Ihr Unternehmen spezifisch sind.

   Machen Sie sich vor der Kontaktaufnahme mit Ihrem Adobe-Account-Team mit den Fragen vertraut, die im Customer Journey Analytics-Upgrade-Handbuch enthalten sind, und ermitteln Sie Ihre Antworten. Das Customer Journey Analytics-Upgrade-Handbuch enthält die folgenden Fragen und möglichen Antworten:


   | Frage | Verfügbare Antworten | Zusätzliche Informationen |
   |---------|----------|---------|
   | Wählen Sie die Option aus, die Ihre aktuelle Adobe Analytics-Implementierung beschreibt. Diese Informationen können sich auf alternative Upgrade-Optionen auswirken, die Ihnen beim Upgrade auf Customer Journey Analytics möglicherweise zur Verfügung stehen. | Wählen Sie eine aus: <ul><li>**AppMeasurement:**<br/> Eine JavaScript-Implementierung, die AppMeasurement.js auf einer Seite lädt und Daten mithilfe des s-Objekts (z. B. s.eVar1) an Adobe sendet.</li><li>**Adobe Analytics-Erweiterung (Tags):** <br/>Eine Tags-Implementierung, die die Adobe Experience Platform-Datenerfassung (früher Launch) lädt. Für das Tag ist die Adobe Analytics-Erweiterung installiert.</li><li>**Experience Platform Web SDK-Erweiterung (Tags):**<br/> Eine Tags-Implementierung, die die Adobe Experience Platform-Datenerfassung (früher Launch) lädt. Für das Tag ist die Web SDK-Erweiterung installiert.</li><li>**Experience Platform Web SDK (alloy.js):** Eine JavaScript-Implementierung, die die Web SDK-Bibliothek (alloy.js) auf einer Seite lädt und Daten mithilfe einer JSON-Payload an Adobe sendet.</li><li>**Bulk Data Insertion-API:**<br/> Eine Implementierung, die die Dateneinfüge-API oder die Bulk-Dateneinfüge-API verwendet.</li><li>**Experience Platform Mobile SDK:**<br/> Eine Implementierung, die die Adobe Experience Platform Mobile SDK verwendet.</li><li>**AppMeasurement mit einem Drittanbieter-Tag-Management-Tool:**<br/> Eine Implementierung, die ein Drittanbieter-Tag-Management-Tool verwendet.</li><li>**Produkt, das nicht von Adobe Analytics stammt**<br/> Eine Implementierung, die Daten für ein anderes Produkt als Adobe Analytics erfasst, z. B. Google Analytics. Durch Auswahl dieser Option werden mehrere Optionen im Aktualisierungshandbuch deaktiviert, die beim Upgrade von einem Produkt, das nicht Adobe Analytics ist, auf Customer Journey Analytics nicht anwendbar sind. </li><li>**Ich weiß nicht:**<br/> Wenn Sie nicht die Person sind, die Ihre Implementierung verwaltet, können Sie diese Option vorübergehend auswählen.</li></ul><p>Wählen Sie aus, falls zutreffend:<ul><li>**In unserer Implementierung wird derzeit der Analytics-Quell-Connector verwendet**<br/> Der Analytics-Quell-Connector ermöglicht es Ihnen, einfach Wert aus Customer Journey Analytics zu ziehen, erfordert jedoch, dass Sie sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen. Dieser Leitfaden kann Sie bei zu einer unabhängigen Web SDK-Implementierung unterstützen.</li></ul></p> | <ul><li>[Machen Sie sich mit Ihrer Adobe Analytics-Implementierung und deren Auswirkungen auf Ihr Upgrade auf Customer Journey Analytics vertraut](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | Die meisten Funktionen von Adobe Analytics sind ohne Weiteres in Customer Journey Analytics verfügbar. Die folgenden Funktionen müssen jedoch während des Aktualisierungsprozesses übertragen werden. Wählen Sie die Funktionen aus, die Sie verwenden möchten. | Wählen Sie alles aus, was zutrifft:<ul><li>**Historische Daten aus Adobe Analytics:**</br> Holen Sie Ihre historischen Adobe Analytics Report Suite-Daten in Adobe Experience Platform und Customer Journey Analytics.</li><li>**Komponenten und Projekte aus Adobe Analytics:**</br> Komponenten aus Adobe Analytics umfassen: Projekte (mit den zugehörigen Freiformtabellen und Visualisierungen), Segmente und berechnete Metriken.</li><li>**Activity Map-Überlagerung und Linktracking:**</br> Eine Browser-Erweiterung, mit der Sie Linktracking-Daten als Überlagerung auf Ihrer Site anzeigen können.</li><li>**Klassifizierungsdaten:**</br> Gruppieren oder Kategorisieren von Daten als separate Dimensionen.</li><li>**Marketing-Kanäle:**</br> Erstellen Sie Regeln, die kategorisieren, wie Kunden zu Ihrer Site gelangen.</li><li>**Data Warehouse:**</br> Exportieren Sie verarbeitete Daten aus Adobe Analytics im Tabellenformat.</li><li>**Daten-Feeds:**&#x200B;Ein exakter Ersatz für Daten-Feeds ist in Customer Journey Analytics noch nicht verfügbar. Ähnliche Funktionen können jedoch mit Funktionen wie dem vollständigen Tabellenexport, dem Platform-Datensatzexport, der BI-Tool-Integration und der Reporting-API erreicht werden.</br></li><li>**Streaming-Mediendaten:**</br> Add-on für Adobe Analytics und Customer Journey Analytics, das auf die Datenerfassung von Medien wie Audio, Video oder Streaming-Inhalten spezialisiert ist.</li></ul> | <ul><li>[Grundlegendes zur Adobe Analytics-Funktionsunterstützung beim Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | Die meisten neuen Funktionen sind ohne Weiteres in Customer Journey Analytics verfügbar. Die folgenden Funktionen müssen jedoch während des Aktualisierungsprozesses übertragen werden. Wählen Sie die Funktionen aus, die Sie verwenden möchten. | Wählen Sie alles aus, was zutrifft:<ul><li>**Erfasste Daten mit Daten aus anderen Quellen (z. B. Kontaktcenter-Daten) verknüpfen:**</br>(Empfohlen) Verknüpfen Sie Daten aus verschiedenen Web-, Mobile- und Offline-Eigenschaften, um eine einzelne, konsolidierte Ansicht des Kundenverhaltens zu erstellen. Diese Fähigkeit, Analysedaten aus anderen Kanälen zu kombinieren, ist der wichtigste Anwendungsfall für Customer Journey Analytics.</li><li>**Treffer aus anderen Datensätzen mithilfe einer benutzerdefinierten Dimension zusammenfügen:**<br/> Wenn einer Ihrer Datensätze keine primäre Kennung (z. B. eine Experience Cloud-ID) aufweist, können Sie diese Daten dennoch mithilfe einer anderen Dimension zusammenfügen, z. B. Benutzername zur Anmeldung oder E-Mail-Adresse.</li><li>**Integration mit Adobe Journey Optimizer**<br/> Stellen Sie Kunden vernetzte, kontextuelle und personalisierte Erlebnisse bereit.</li><li>**Integration mit Adobe Real-Time CDP:**<br/> Kombinieren Sie Profildaten aus verschiedenen Quellen, um Zielgruppen und Segmente basierend auf Benutzereigenschaften zu generieren.</li><li>**Integration mit Adobe Target (A4T):**<br/> Adobe empfiehlt für Personalisierungs-Anwendungsfälle die Integration mit Adobe Journey Optimizer. Die Integration mit Adobe Target ist möglich, ist aber nur eine kurzfristige Lösung.</li><li>**Integration mit Adobe Audience Manager:**<br/> Adobe empfiehlt für zielgruppenbasierte Anwendungsfälle die Integration mit Adobe Real-Time CDP. Die Integration mit Audience Manager ist möglich, ist aber nur eine kurzfristige Lösung.</li></ul> | [Grundlegendes zu den Customer Journey Analytics-spezifischen Funktionen](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Wählen Sie aus, wie Sie Adobe Analytics und Customer Journey Analytics letztendlich verwenden möchten: | Wählen Sie eine aus: <ul><li>**Ich beabsichtige, von Adobe Analytics vollständig zu Customer Journey Analytics zu wechseln:**<br/>(Empfohlen) Adobe empfiehlt, vollständig von Adobe Analytics zu Customer Journey Analytics zu wechseln. Während der Übergangszeit sollten Sie Adobe Analytics zusammen mit Customer Journey Analytics ausführen, um nebeneinander Datenvergleiche durchzuführen. Wenn Sie mit den Daten zurechtkommen, können Sie Adobe Analytics deaktivieren.</li><li>**Ich beabsichtige, beide Analytics-Produkte beizubehalten:**<br/>(Nicht empfohlen) Wenn Sie diese Option auswählen, umfasst Ihr Vertrag mit Adobe sowohl Adobe Analytics als auch Customer Journey Analytics, was für Ihr Unternehmen im Laufe der Zeit teurer werden kann.</li></ul> | [Ermitteln Sie, wann Adobe Analytics nach dem Upgrade auf Customer Journey Analytics deaktiviert werden soll](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Wählen Sie aus, wie Sie Ihr Customer Journey Analytics-Schema konfigurieren möchten: | Wählen Sie eine aus: <ul><li>**Ich möchte ein auf meine Organisation zugeschnittenes Schema verwenden:**</br>(Empfohlen) Das Anpassen Ihres Schemas ermöglicht Ihrer Organisation, nur das zu verfolgen, was Sie benötigen, und den Overhead zu vermeiden, der mit unübersichtlichen und nicht benötigten Feldern verbunden ist. Diese Option umfasst Feldgruppen, die vom Web-SDK hinzugefügt wurden, und benutzerdefinierte Feldgruppen für Ihre Organisation.</li><li>**Ich möchte das standardmäßige Adobe Analytics-Schema verwenden:**</br>(Nicht empfohlen) Das Adobe Analytics-Schema enthält mehr als tausend Felder, was zu einer Überlastung und Komplexität des Schemas führen kann. Ihre Organisation wäre gezwungen, weiterhin das Konzept von Props und eVars einzuhalten. Dabei handelt es sich um ein Altkonzept, das nicht in Customer Journey Analytics verwendet wird. Die Integration mit anderen Adobe Experience Platform-Services ist schwieriger.</li></ul> | [Wählen Sie Ihr Schema für Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Wählen Sie aus, wie Sie Customer Journey Analytics implementieren möchten: | <ul><li>**Manuelle Implementierung (alloy.js):**<br/> Fügen Sie die Web SDK-Bibliothek (alloy.js) auf jeder Seite Ihrer Site ein.</li><li>**Tags:**<br/>(Empfohlen) Wenn Sie noch keine Tags verwenden, installieren Sie den Tag-Loader auf Ihrer Site. Wenn Sie bereits Tags verwenden, können Sie die Web-SDK-Erweiterung zu Ihrer Tag-Eigenschaft hinzufügen. Diese Option umfasst Implementierungen, bei denen Tags in der Datenerfassung von Adobe Experience Platform und in Tag-Management-Systemen von Drittanbietern verwendet werden.</li><li>**API:**<br/> Verwenden Sie die Datenerfassungs-API, um Daten direkt an einen Datenstrom zu senden. Es werden sowohl nicht authentifizierte (Client-zu-Server) als auch authentifizierte (Server-zu-Server) Typen unterstützt.</li></ul> | [Grundlegendes zu den Implementierungsoptionen von Web SDK beim Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Optional) Wählen Sie eine alternative Upgrade-Methode | <ul><li>**Nur den Analytics-Quell-Connector verwenden:**<br/>(Nicht empfohlen) Sie können den Analytics-Quell-Connector als einzigen Implementierungspfad für Customer Journey Analytics verwenden.<p>Diese Option spart Implementierungszeit, indem Daten schnell an Customer Journey Analytics gesendet werden. Sie hat jedoch verschiedene Nachteile, wie z. B. eine höhere Latenz und Schwierigkeiten, in Zukunft von Adobe Analytics zu wechseln.</p></li><li>**Ich möchte meine AppMeasurement-Logik mit dem Web-SDK verwenden:**<br/> Anstatt Daten über ein XDM-Objekt zu senden, senden Sie alle Ihre Variablen im AppMeasurement-Format über das Datenobjekt.<p>Diese Option spart Implementierungszeit, da Sie Ihre AppMeasurement-Logik XDM zuordnen können, anstatt ein XDM-Objekt von Grund auf neu zu befüllen. Im Laufe der Zeit führt dies jedoch zu zusätzlicher Komplexität, da jedes Feld, das Sie in Zukunft hinzufügen, im Datenstrom XDM zugeordnet werden muss.</p></li><li>**Ich möchte meine Datenschicht ohne zusätzliche Konfiguration an Adobe senden:**<br/> Anstatt Daten über ein XDM-Objekt zu senden, können Sie über das Datenobjekt Ihre gesamte Datenschicht an Adobe senden.<p>Diese Option spart Implementierungszeit, da Sie Ihre Datenschicht XDM zuordnen können, anstatt ein XDM-Objekt von Grund auf neu zu befüllen. Diese Zuordnung ist jedoch sehr aufwändig, da eine erhebliche Datenmenge vorhanden ist, die Adobe nicht ohne weiteres interpretieren kann. Außerdem führt diese Option im Laufe der Zeit zu zusätzlicher Komplexität, da jedes Feld, das Sie den Daten später hinzufügen, im Datenstrom XDM zugeordnet werden muss.</p></li></ul> | <ul><li>[Upgrade-Alternative: Verwenden Sie den Analytics-Quell-Connector ausschließlich für das Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Upgrade-Alternative: Verwenden Sie die AppMeasurement-Datenerfassung mit der Experience Platform Web SDK und Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Upgrade-Alternative: Senden Sie Ihre Datenschicht an Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Nachdem Sie dieses Upgrade-Handbuch mit Ihrem Adobe-Account-Team abgeschlossen haben, erhalten Sie eine CSV-Datei mit den Fragen, Ihren Antworten und den dynamisch generierten Upgrade-Schritten, die am besten zu Ihrer bestehenden Adobe Analytics-Umgebung und Ihren Zielen für Customer Journey Analytics passen.

1. Befolgen Sie die in der CSV-Datei generierten schrittweisen Anweisungen, um auf Customer Journey Analytics zu aktualisieren.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
