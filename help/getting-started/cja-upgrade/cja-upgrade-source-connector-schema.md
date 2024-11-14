---
title: Erstellen eines XDM-Schemas für den Analytics-Quell-Connector
description: Erfahren Sie, wie Sie ein XDM-Schema für den Analytics-Quell-Connector erstellen.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Erstellen eines XDM-Schemas für den Analytics-Quell-Connector

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Sie sollten bereits [ ein neues XDM-Schema erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), damit Ihre Experience Platform Web SDK-Implementierung mit Customer Journey Analytics verwendet werden kann. Dieses Schema sollte alle Feldergruppen für Felder enthalten, für die Sie Daten erfassen möchten.

Zusätzlich zum XDM-Schema, das Sie bereits für Ihre Web SDK-Implementierung erstellt haben, müssen Sie jetzt ein zweites XDM-Schema erstellen, das mit dem Analytics-Quell-Connector verwendet werden kann, um historische Daten in Customer Journey Analytics zu übertragen.

Dieses zweite Schema muss Folgendes enthalten:

* Alle Feldergruppen (einschließlich aller benutzerdefinierten Feldergruppen), die in dem Schema enthalten sind, das Sie für Ihre Web SDK-Implementierung erstellt haben. (Alle benutzerdefinierten Felder, die nicht zu einer Standardfeldgruppe gehören, sollten Ihrem Web SDK-Schema als Teil einer benutzerdefinierten Feldergruppe hinzugefügt worden sein.)

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

