---
title: Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector
description: Erfahren Sie, wie Sie ein benutzerdefiniertes Schema für den Analytics-Quell-Connector erstellen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '587'
ht-degree: 100%

---

# Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Erstellen eines Schemas für den Analytics-Quell-Connector"
>abstract="Dieses Schema ist eine Kombination der Adobe Analytics ExperienceEvent-Feldgruppe mit allen Feldgruppen, aus denen das benutzerdefinierte Schema Ihrer Organisation besteht. Damit können Sie die vom Analytics-Quell-Connector verwendeten Felder dem Schema Ihrer Organisation zuordnen. Dies wird nur für historische Daten verwendet.<br><br>Die Erstellung dieses Schemas ist zwar technischer Natur, kann aber innerhalb von Stunden abgeschlossen werden, möglicherweise schneller, wenn Sie genau wissen, aus welchen Feldgruppen das benutzerdefinierte Schema Ihrer Organisation besteht."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="Erstellen des Analytics-Quell-Connectors für historische Daten"
>abstract="Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten in Customer Journey Analytics genutzt werden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Informationen zum Import historischer Daten in Customer Journey Analytics mit dem Analytics-Quell-Connector

Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten in Customer Journey Analytics genutzt werden.

Bei diesem Prozess wird davon ausgegangen, dass Sie [ein benutzerdefiniertes Schema für die Customer Journey Analytics Web SDK-Implementierung erstellen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), da Sie sich ein optimiertes Schema wünschen, das auf die Anforderungen Ihrer Organisation und die von Ihnen verwendeten spezifischen Platform-Anwendungen zugeschnitten ist.

Um mit dem Analytics-Quell-Connector historische Daten in Customer Journey Analytics zu importieren, ist Folgendes erforderlich:

1. Erstellen Sie ein benutzerdefiniertes Schema für den Analytics-Quell-Connector, wie unten beschrieben.

1. Wenn Sie noch nicht über einen Analytics-Quell-Connector verfügen, [erstellen Sie den Analytics-Quell-Connector und ordnen Sie Ihrem benutzerdefinierten Schema Felder zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Oder

   Wenn Sie bereits über einen Analytics-Quell-Connector verfügen, [ordnen Sie Ihrem XDM-Schema Felder aus dem Quell-Connector zu](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector

Sie sollten für Ihre Experience Platform-Web-SDK-Implementierung bereits [ein neues benutzerdefiniertes Schema erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), das mit Customer Journey Analytics verwendet werden kann. Dieses Schema sollte alle Feldgruppen für Felder enthalten, für die Sie Daten erfassen möchten.

Jetzt müssen Sie dieselben Feldgruppen aus Ihrem Web-SDK-Schema verwenden und sie einem neuen Schema hinzufügen, das Sie mit dem Analytics-Quell-Connector verwenden können.

Dieses Schema für den Analytics-Quell-Connector muss Folgendes enthalten:

* Alle Feldgruppen (einschließlich aller von Ihnen erstellten benutzerdefinierten Feldgruppen), die in Ihrem benutzerdefinierten Schema enthalten sind, das Sie für Ihre Web-SDK-Implementierung erstellt haben. (Alle benutzerdefinierten Felder, die nicht zu einer Standardfeldgruppe gehören, sollten Ihrem Web-SDK-Schema als Teil einer benutzerdefinierten Feldgruppe hinzugefügt worden sein.)

* Die Feldgruppe „Adobe Analytics ExperienceEvent Template“

So erstellen Sie ein benutzerdefiniertes Schema zur Verwendung mit dem Analytics-Quell-Connector:

1. Beginnen Sie in Adobe Experience Platform mit der Erstellung eines neuen benutzerdefinierten Schemas, wie unter [Erstellen eines benutzerdefinierten Schemas zur Verwendung mit Ihrer Customer Journey Analytics Web-SDK-Implementierung](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) beschrieben.

1. Fügen Sie alle Feldgruppen (einschließlich aller benutzerdefinierten Feldgruppen) hinzu, die in dem Schema enthalten sind, das Sie für Ihre Web-SDK-Implementierung erstellt haben.

1. Nachdem Sie diese Feldgruppen hinzugefügt haben, fügen Sie die Adobe Analytics ExperienceEvent-Feldgruppe hinzu:

   Wählen Sie im Abschnitt **[!UICONTROL Feldgruppen]** die Option **[!UICONTROL Hinzufügen]** aus, um eine zusätzliche Feldgruppe hinzuzufügen.

   ![Hinzufügen einer Feldgruppe zum Schema](assets/schema-add-field-group.png)

1. Suchen Sie nach der Feldgruppe **[!UICONTROL Adobe Analytics ExperienceEvent Template]** und wählen Sie sie aus.

   ![Hinzufügen der Adobe Analytics ExperienceEvent-Feldgruppe](assets/schema-experienceevent.png)

1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

{{upgrade-final-step}}
