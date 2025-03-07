---
title: Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector
description: Erfahren Sie, wie Sie ein benutzerdefiniertes Schema für den Analytics Source Connector erstellen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 23%

---

# Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Erstellen eines Schemas für den Analytics-Quell-Connector"
>abstract="Dieses Schema ist eine Kombination der Adobe Analytics Experience-Ereignisfeldergruppe mit allen Feldergruppen, aus denen das benutzerdefinierte Schema Ihrer Organisation besteht. Damit können Sie die vom Analytics-Quell-Connector verwendeten Felder dem Schema Ihrer Organisation zuordnen. Dies wird nur für historische Daten genutzt.<br><br>Die Erstellung dieses Schemas ist zwar technischer Natur, kann aber in Stunden abgeschlossen werden, möglicherweise auch schneller, wenn Sie genau wissen, aus welchen Feldergruppen das benutzerdefinierte Schema Ihrer Organisation besteht."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Erfahren Sie, wie der Analytics-Quell-Connector historische Daten in Customer Journey Analytics importieren kann

Sie können den Analytics-Quell-Connector verwenden, um Daten von Adobe Analytics Report Suites in Adobe Experience Platform zu importieren. Diese Daten können dann als Verlaufsdaten in Customer Journey Analytics verwendet werden.

Bei diesem Prozess wird davon ausgegangen, dass Sie [ein benutzerdefiniertes Schema zur Verwendung mit Ihrer Customer Journey Analytics Web SDK-Implementierung erstellen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), da Sie ein optimiertes Schema wünschen, das auf die Anforderungen Ihres Unternehmens und die von Ihnen verwendeten spezifischen Platform-Programme zugeschnitten ist.

Um den Analytics-Quell-Connector zu verwenden, um historische Daten in Customer Journey Analytics zu importieren, ist Folgendes erforderlich:

1. Erstellen Sie ein benutzerdefiniertes Schema für den Analytics-Quell-Connector, wie unten beschrieben.

1. Wenn Sie noch keinen Analytics-Quell-Connector haben, erstellen [ den Analytics-Quell-Connector und ordnen Sie Felder Ihrem benutzerdefinierten Schema zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Oder

   Wenn Sie bereits über einen Analytics-Quell-Connector verfügen[ ordnen Sie (Felder aus dem Quell-Connector Ihrem XDM-Schema zu](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Erstellen eines benutzerdefinierten Schemas für den Analytics-Quell-Connector

Sie sollten bereits [ein neues benutzerdefiniertes Schema erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) für Ihre Experience Platform Web SDK-Implementierung zur Verwendung mit Customer Journey Analytics erstellt haben. Dieses Schema sollte alle Feldergruppen für Felder enthalten, für die Sie Daten erfassen möchten.

Jetzt müssen Sie dieselben Feldergruppen aus Ihrem Web SDK-Schema verwenden und sie einem neuen Schema hinzufügen, das Sie mit dem Analytics-Quell-Connector verwenden können.

Dieses Schema für den Analytics-Quell-Connector muss Folgendes enthalten:

* Alle Feldergruppen (einschließlich aller von Ihnen erstellten benutzerdefinierten Feldergruppen), die in Ihrem benutzerdefinierten Schema enthalten sind, das Sie für Ihre Web SDK-Implementierung erstellt haben. (Alle benutzerdefinierten Felder, die nicht zu einer Standardfeldgruppe gehören, sollten Ihrem Web SDK-Schema als Teil einer benutzerdefinierten Feldgruppe hinzugefügt worden sein.)

* Die Feldergruppe der Adobe Analytics ExperienceEvent-Vorlage

So erstellen Sie ein benutzerdefiniertes Schema zur Verwendung mit dem Analytics-Quell-Connector:

1. Beginnen Sie in Adobe Experience Platform mit der Erstellung eines neuen benutzerdefinierten Schemas, wie unter [Erstellen eines benutzerdefinierten Schemas zur Verwendung mit Ihrer Customer Journey Analytics Web SDK-Implementierung](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) beschrieben.

1. Fügen Sie alle Feldergruppen (einschließlich benutzerdefinierter Feldergruppen) hinzu, die in dem Schema enthalten sind, das Sie für Ihre Web SDK-Implementierung erstellt haben.

1. Nachdem Sie diese Feldergruppen hinzugefügt haben, fügen Sie die Feldergruppe Adobe Analytics ExperienceEvent hinzu:

   Wählen Sie im **[!UICONTROL Feldergruppen]** die Option **[!UICONTROL Hinzufügen]** aus, um eine zusätzliche Feldergruppe hinzuzufügen.

   ![Feldergruppe zum Schema hinzufügen](assets/schema-add-field-group.png)

1. Suchen Sie nach der Feldergruppe **[!UICONTROL Adobe Analytics ExperienceEvent Template]** und wählen Sie sie aus.

   ![Fügen Sie die Adobe Analytics ExperienceEvent-Feldergruppe hinzu](assets/schema-experienceevent.png)

1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

{{upgrade-final-step}}
