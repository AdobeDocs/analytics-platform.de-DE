---
title: Erstellen eines XDM-Schemas für den Analytics-Quell-Connector
description: Erfahren Sie, wie Sie ein XDM-Schema für den Analytics-Quell-Connector erstellen.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 8%

---

# Erstellen eines XDM-Schemas für den Analytics-Quell-Connector

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

## Erfahren Sie, wie der Analytics-Quell-Connector historische Daten in Customer Journey Analytics integrieren kann.

Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics-Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten im Customer Journey Analytics verwendet werden.

Bei diesem Vorgang wird davon ausgegangen, dass Sie beim Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) ein XDM-Schema erstellen möchten, da Sie ein optimiertes Schema wünschen, das auf die Anforderungen Ihres Unternehmens und die von Ihnen verwendeten spezifischen Platform-Anwendungen zugeschnitten ist.[

Um den Analytics-Quell-Connector zu verwenden, um historische Daten in Customer Journey Analytics zu importieren, müssen Sie Folgendes tun:

1. Erstellen Sie ein XDM-Schema für den Analytics-Quell-Connector, wie unten beschrieben.

1. Wenn Sie noch keinen Analytics-Quell-Connector haben, erstellen Sie den Analytics-Quell-Connector und ordnen Sie Felder Ihrem XDM-Schema zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).[

   Oder

   Wenn Sie bereits über einen Analytics-Quell-Connector verfügen, ordnen Sie Felder vom Quell-Connector Ihrem XDM-Schema zu ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).[

1. [Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Erstellen eines XDM-Schemas für den Analytics-Quell-Connector

Sie sollten bereits [ ein neues XDM-Schema erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), damit Ihre Experience Platform Web SDK-Implementierung mit Customer Journey Analytics verwendet werden kann. Dieses Schema sollte alle Feldergruppen für Felder enthalten, für die Sie Daten erfassen möchten.

Jetzt müssen Sie dieselben Feldergruppen aus Ihrem Web SDK-Schema verwenden und sie zu einem neuen Schema hinzufügen, das Sie mit dem Analytics-Quell-Connector verwenden können.

Dieses Schema für den Analytics-Quell-Connector muss Folgendes enthalten:

* Alle Feldergruppen (einschließlich aller von Ihnen erstellten benutzerdefinierten Feldergruppen), die in Ihrem benutzerdefinierten Schema enthalten sind, das Sie für Ihre Web SDK-Implementierung erstellt haben. (Alle benutzerdefinierten Felder, die nicht zu einer Standardfeldgruppe gehören, sollten Ihrem Web SDK-Schema als Teil einer benutzerdefinierten Feldergruppe hinzugefügt worden sein.)

* Die Feldergruppe &quot;Adobe Analytics ExperienceEvent-Vorlage&quot;

Erstellen des XDM-Schemas zur Verwendung mit dem Analytics-Quell-Connector:

1. Beginnen Sie in Adobe Experience Platform mit der Erstellung eines neuen XDM-Schemas, wie unter [Erstellen eines XDM-Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) beschrieben.

1. Fügen Sie alle Feldergruppen (einschließlich aller benutzerdefinierten Feldergruppen) hinzu, die im Schema enthalten sind, das Sie für Ihre Web SDK-Implementierung erstellt haben.

1. Fügen Sie nach dem Hinzufügen dieser Feldergruppen die Adobe Analytics ExperienceEvent -Feldergruppe hinzu:

   Wählen Sie im Abschnitt **[!UICONTROL Feldergruppen]** die Option **[!UICONTROL Hinzufügen]** aus, um eine zusätzliche Feldergruppe hinzuzufügen.

   ![Feldergruppe zum Schema hinzufügen](assets/schema-add-field-group.png)

1. Suchen Sie nach der Feldergruppe **[!UICONTROL Adobe Analytics ExperienceEvent Template]** und wählen Sie sie aus.

   ![Hinzufügen der Adobe Analytics ExperienceEvent-Feldergruppe](assets/schema-experienceevent.png)

1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
