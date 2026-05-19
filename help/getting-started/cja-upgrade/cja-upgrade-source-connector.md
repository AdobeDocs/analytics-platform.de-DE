---
title: Erstellen des Analytics-Quell-Connectors und Zuordnen von Feldern
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector erstellen und Felder zuordnen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
autotag-review: '2026-05-19T08:18:13.585Z'
TQID: 'https://experienceleague.adobe.com/IQVDwcpMVnEa-dFXbNkpmHQRofC6d8z2ocf-PIaK--Q'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 758
ht-degree: 100%

---

# Erstellen des Analytics-Quell-Connectors und Zuordnen von Feldern {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Erstellen des Analytics-Quell-Connectors"
>abstract="Verwenden Sie den Analytics-Quell-Connector, um Report-Suite-Daten für die Verwendung in Customer Journey Analytics aufzunehmen.<br><br>Die Erstellung des Analytics-Quell-Connectors dauert mit den Standardeinstellungen nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Erstellen des Analytics-Quell-Connectors und Zuordnen von Schemafeldern"
>abstract="Der Quell-Connector muss wissen, wie Adobe Analytics-Felder dem Schema Ihrer Organisation zugeordnet werden. Verwenden Sie diese Oberfläche, um den Quell-Connector mit dieser Zuordnung bereitzustellen. Dieser Schritt gehört zum Hinzufügen historischer Daten zu Customer Journey Analytics.<br><br>Wie lange dieser Schritt dauert, hängt stark von der Anzahl der Dimensionen und Metriken ab, die Sie zuordnen müssen. Dieser Schritt ist weniger schwer als mühsam und eintönig. Die Datenstromzuordnung dauert voraussichtlich etwa eine Woche."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Informationen zum Import historischer Daten in Customer Journey Analytics mit dem Analytics-Quell-Connector

Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten in Customer Journey Analytics genutzt werden.

Bei diesem Prozess wird davon ausgegangen, dass Sie [ein benutzerdefiniertes Schema für die Customer Journey Analytics Web SDK-Implementierung erstellen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), da Sie sich ein optimiertes Schema wünschen, das auf die Anforderungen Ihrer Organisation und die von Ihnen verwendeten spezifischen Platform-Anwendungen zugeschnitten ist.

Um mit dem Analytics-Quell-Connector historische Daten in Customer Journey Analytics zu importieren, ist Folgendes erforderlich:

1. [Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Wenn Sie noch nicht über einen Analytics-Quell-Connector verfügen, erstellen Sie den Analytics-Quell-Connector und ordnen Sie Ihrem benutzerdefinierten Web SDK-Schema Felder zu, wie nachfolgend beschrieben.

   Oder

   Wenn Sie bereits über einen Analytics-Quell-Connector verfügen, [ordnen Sie Ihrem benutzerdefinierten Web SDK-Schema Felder aus dem Quell-Connector zu](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Erstellen des Analytics-Quell-Connectors und Zuordnen von Feldern

Nach Ihrem benutzerdefinierten Schema müssen Sie den Adobe Analytics-Quell-Connector erstellen, der für historische Daten verwendet werden soll. (Weitergehende allgemeine Richtlinien zum Erstellen eines Quell-Connectors finden Sie unter [Erstellen einer Adobe Analytics-Quellverbindung in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de).)

So erstellen Sie einen Adobe Analytics-Quell-Connector für historische Daten:

1. Wählen Sie in der Platform-Benutzeroberfläche im Abschnitt **[!UICONTROL Verbindungen]** in der linken Leiste die Option **[!UICONTROL Quellen]** aus.

1. Wählen Sie **[!UICONTROL Adobe-Anwendungen]** aus der Liste der [!UICONTROL KATEGORIEN] aus.

1. Wählen Sie auf der Adobe Analytics-Kachel die Option **[!UICONTROL Daten hinzufügen]** aus.

   ![Adobe Experience Platform-Fenster mit den hervorgehobenen Auswahlen Quellen, Adobe-Anwendungen und Daten hinzufügen.](./assets/sources-overview.png)

1. Wählen Sie **[!UICONTROL Report Suite]** und dann aus der Liste der Report Suites die Report Suite aus, die die historischen Daten enthält, die in Customer Journey Analytics verwendet werden sollen.

   ![Adobe Experience Platform-Fenster mit der Report Suite-Liste](./assets/report-suites.png)

1. Wählen Sie oben rechts im Bildschirm die Option **[!UICONTROL Weiter]** aus.

1. Wählen Sie **[!UICONTROL Benutzerdefiniertes Schema]** und dann das Schema aus, das Sie unter [Erstellen eines benutzerdefinierten Schemas mit der Adobe Analytics-Feldergruppe](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md) erstellt haben. <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Ordnen Sie jede Adobe Analytics-Dimension einer benutzerdefinierten Schemadimension zu.

   1. Wählen Sie im Abschnitt **[!UICONTROL Standardfelder zuordnen]** die Registerkarte **[!UICONTROL Benutzerdefiniert]** aus.

   1. Wählen Sie **[!UICONTROL Neue Zuordnung hinzufügen]** aus.

   ![Zuordnen von Schemafeldern](assets/schema-mapping.png)

   1. Wählen Sie unter **[!UICONTROL Quellfeld]** ein Adobe Analytics-Feld aus der Feldergruppe „Adobe Analytics ExperienceEvent Template“ aus. Wählen Sie dann unter **[!UICONTROL Zielfeld]** das benutzerdefinierte Feld im XDM-Schema aus, dem es zugeordnet werden soll.

      Aufgrund der inhärenten Architekturunterschiede zwischen AppMeasurement und XDM verfügen nicht alle Adobe Analytics-Felder über ein entsprechendes Feld in XDM.

   1. Wiederholen Sie diesen Vorgang für jedes Feld in der Feldergruppe „Adobe Analytics ExperienceEvent Template“, mit dem Sie Daten in Adobe Analytics erfassen.

1. Wählen Sie oben rechts im Bildschirm die Option **[!UICONTROL Weiter]** aus.

1. Benennen Sie den Datenfluss und geben Sie (optional) eine Beschreibung ein.

   ![Adobe Experience Platform-Fenster mit hervorgehobenem Abschnitt Datenflussdetail](./assets/dataflow-detail.png)

1. Wählen Sie oben rechts im Bildschirm die Option **[!UICONTROL Weiter]** aus.

1. Überprüfen Sie die Verbindung und wählen Sie **[!UICONTROL Beenden]** aus.

   ![Adobe Experience Platform-Fenster mit den zur Überprüfung hervorgehobenen Abschnitten Verbinden und Datentyp](./assets/review.png)

   Nachdem die Verbindung erstellt wurde, wird der Datenfluss automatisch erstellt, um einen Datensatz mit den Adobe Analytics-Daten aus Ihrer Report Suite aufzufüllen. Der Datenfluss nimmt bis zu 13 Monate historischer Daten für Produktions-Sandboxes auf. Die Aufstockung in Nicht-Produktions-Sandboxes ist dagegen auf drei Monate beschränkt.

   Wenn Sie mit den Analytics-Quell-Connector historische Daten in Ihre Customer Journey Analytics Web SDK-Implementierung importieren, müssen Sie diesen automatisch erstellten Datensatz der für Ihre Web SDK-Implementierung erstellten Verbindung hinzufügen.

{{upgrade-final-step}}
