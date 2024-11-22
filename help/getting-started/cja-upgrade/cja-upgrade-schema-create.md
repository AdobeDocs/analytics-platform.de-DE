---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 48%

---

# Erstellen eines XDM-Schemas zur Verwendung mit Ihrer Customer Journey Analytics Web SDK-Implementierung

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

>[!IMPORTANT]
>
>Bevor Sie mit der Erstellung Ihres XDM-Schemas beginnen, wenden Sie sich an Ihr Datenteam und andere Beteiligte in Ihrer Organisation, um das ideale Schema für Customer Journey Analytics und die anderen von Ihnen verwendeten Adobe Experience Platform-Anwendungen zu ermitteln. Weitere Informationen finden Sie unter [Architektur Ihres Schemas für die Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Adobe empfiehlt beim Upgrade auf Customer Journey Analytics die Erstellung eines benutzerdefinierten Experience-Datenmodell (XDM)-Schemas. Ein benutzerdefiniertes Schema ermöglicht ein optimiertes Schema, das auf die Anforderungen Ihres Unternehmens und die spezifischen Platform-Anwendungen zugeschnitten ist, die Sie verwenden. Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.

## Erstellen des Schemas

Das von Ihnen definierte XDM-Schema stellt das Modell der Daten dar, die Sie in Adobe Experience Platform erfassen.

So erstellen Sie ein benutzerdefiniertes Schema:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. Wählen Sie in Adobe Experience Platform in der linken Leiste **[!UICONTROL Schemas]** in [!UICONTROL DATENVERWALTUNG] aus.

1. Wählen Sie **[!UICONTROL Schema erstellen]** aus.

1. Wählen Sie im Schritt **[!UICONTROL Select a class]** des Assistenten Schema erstellen Folgendes:

   1. Wählen Sie **[!UICONTROL Erlebnisereignis]** aus.

      ![Erstellen eines Schemas, das Erlebnisereignis hervorhebt](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Mit einem Erlebnisereignis-Schema wird das _Verhalten_ eines Profils modelliert (z. B. Name der Szene, Schaltfläche zum Hinzufügen zum Warenkorb). Das Schema „Individuelles Profil“ wird verwendet, um die _Attribute_ eines Profils zu modellieren (z. B. Name, E-Mail, Geschlecht).

   1. Klicken Sie auf **[!UICONTROL Weiter]**.


1. Im Schritt [!UICONTROL Name und Überprüfung] des Assistenten [!UICONTROL Schema erstellen]:

   1. Geben Sie einen **[!UICONTROL Anzeigenamen des Schemas]** und (optional) eine **[!UICONTROL Beschreibung]** ein.

      ![Schema-Fenster mit dem Namen der Schemafelder erstellen](assets/create-ee-schema-wizard-step-2.png)

   1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Fügen Sie alle Feldergruppen hinzu, die alle Felder enthalten, die Sie in Ihr Schema aufnehmen möchten.

   Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   1. Wählen Sie im Abschnitt **[!UICONTROL Feldgruppen]** die Option **[!UICONTROL + Hinzufügen]** aus.

      ![Hinzufügen der Feldergruppe](assets/add-field-group-button.png)

   1. Wählen Sie im Dialog [!UICONTROL Feldergruppen hinzufügen] die Feldergruppe **[!UICONTROL AEP Web SDK ExperienceEvent]** aus der Liste aus.

      ![Die Feldergruppe „AEP Web SDK ExperienceEvent“](assets/select-aepwebsdk-experienceevent.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören, z. B. `web > webPageDetails > name`.

      ![Vorschau der Feldergruppe „AEP Web SDK ExperienceEvent“](assets/aepwebsdk-experiencevent-preview.png)

      Wählen Sie **[!UICONTROL Zurück]** aus, um die Vorschau zu schließen.

   1. (Optional) Wählen Sie alle zusätzlichen Feldergruppen aus, die Sie einbeziehen möchten.

   1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. (Optional) Wenn Sie benutzerdefinierte Felder haben, die Sie in Ihr Schema aufnehmen möchten, erstellen Sie eine benutzerdefinierte Feldergruppe und fügen Sie die benutzerdefinierten Felder zur Feldergruppe hinzu.

   1. Wählen Sie im Abschnitt **[!UICONTROL Feldgruppen]** die Option **[!UICONTROL + Hinzufügen]** aus.

      ![Hinzufügen der Feldergruppe](assets/add-field-group-button.png)

   1. Wählen Sie im Dialogfeld [!UICONTROL Feldergruppen hinzufügen] die Option **[!UICONTROL Neue Feldergruppe erstellen]**.

   1. Geben Sie einen Anzeigenamen und eine optionale Beschreibung an und wählen Sie dann **[!UICONTROL Feldgruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL +]** neben Ihrem Schemanamen im Bedienfeld [!UICONTROL Struktur] aus.

   ![Beispiel für die Schaltfläche zum Hinzufügen eines Feldes zum Schema](assets/example-schema-plus.png)

1. Geben Sie im Bedienfeld [!UICONTROL Feldeigenschaften] als Namen `Identification` und als [!UICONTROL Anzeigename]**[!UICONTROL Identifikation]** ein, wählen Sie als [!UICONTROL Typ] **[!UICONTROL Objekt]** und als [!UICONTROL Feldergruppe] **[!UICONTROL ExperienceEvent Core v2.1]** aus.

   >[!NOTE]
   >
   >Wenn diese Feldergruppe nicht verfügbar ist, suchen Sie nach einer anderen Feldergruppe, die Identitätsfelder enthält. Oder [erstellen Sie eine neue Feldergruppe](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) und [fügen Sie der Feldergruppe neue Identitätsfelder hinzu](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (z. B. `ecid`, `crmId` und andere, die Sie benötigen) und wählen Sie diese neue Feldergruppe aus.

   ![Identifizierungsobjekt](assets/identification-field.png)

   Das Identifizierungsobjekt fügt Ihrem Schema Identifizierungsfunktionen hinzu. In Ihrem Fall möchten Sie Profile, die Ihre Site besuchen, mithilfe der Experience Cloud-ID und der E-Mail-Adresse identifizieren. Es gibt viele weitere Attribute, mit denen Sie die Identifizierung Ihrer Person verfolgen können (z. B. Kunden-ID, Treueprogramm-ID).

   Wählen Sie **[!UICONTROL Anwenden]** aus, um dieses Objekt zu Ihrem Schema hinzuzufügen.

1. Wählen Sie im soeben hinzugefügten Identifizierungsobjekt das Feld **[!UICONTROL ECID]** aus und danach im rechten Bedienfeld **[!UICONTROL Identität]** und **[!UICONTROL Primäre Identität]** sowie die Option **[!UICONTROL ECID]** in der Liste [!UICONTROL Identity-Namespace].

   ![Spezifizieren Sie die ECID als Identität](./assets/specify-identity.png)

   Sie spezifizieren die Experience Cloud-Identität als primäre Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen, die dieselbe ECID haben, zu kombinieren (Stitching).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im ECID-Attribut.

1. Wählen Sie das Feld **[!UICONTROL E-Mail]** im soeben hinzugefügten Identifizierungsobjekt aus und danach **[!UICONTROL Identität]** und **[!UICONTROL E-Mail]** in der Liste [!UICONTROL Identity-Namespace] im Bedienfeld [!UICONTROL Feldeigenschaften].

   ![Spezifizieren von E-Mail als Identität](./assets/specify-email-identity.png)

   Sie spezifizieren die E-Mail-Adresse als weitere Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen zu kombinieren (Stitching).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im E-Mail-Attribut.

   Wählen Sie **[!UICONTROL Speichern]** aus.

1. (Optional) Wenn Sie Customer Journey Analytics in RTCDP integrieren möchten, wählen Sie das Stammelement Ihres Schemas aus, das den Namen des Schemas anzeigt, und wählen Sie dann den Schalter **[!UICONTROL Profil]** aus.

   Sie werden aufgefordert, das Schema für das Profil zu aktivieren. Nach der Aktivierung werden Daten, die auf der Basis dieses Schemas in Datensätze aufgenommen werden, zum Echtzeit-Kundenprofil hinzugefügt.

   Weitere Informationen finden Sie im Abschnitt [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >Nachdem Sie ein Schema für ein Profil aktiviert haben, kann es für das Profil nicht deaktiviert werden.

   ![Aktivieren eines Schemas für ein Profil](./assets/enable-for-profile.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

   Sie haben ein Minimalschema erstellt, das die Daten modelliert, die Sie auf Ihrer Website erfassen können. Mithilfe des Schemas können Profile anhand der Experience Cloud-Identität und -E-Mail-Adresse identifiziert werden. Durch die Aktivierung des Schemas für das Profil können die auf Ihrer Website erfassten Daten zum Echtzeit-Kundenprofil hinzugefügt werden.

   Neben den Verhaltensdaten können Sie auch Profilattributdaten auf Ihrer Website erfassen (z. B. Details zu Profilen, die einen Newsletter abonnieren).

   Um diese Profildaten zu erfassen, gehen Sie folgendermaßen vor:

   * Erstellen Sie ein Schema basierend auf der Klasse „XDM Individual Profile“.

   * Fügen Sie die Feldergruppe „Profile Core v2“ zum Schema hinzu.

   * Fügen Sie ein Identifizierungsobjekt hinzu, das auf der Feldergruppe „Profile Core v2“ basiert.

   * Definieren Sie die Experience Cloud-ID als primäre Kennung und die E-Mail als Kennung.

   * Aktivieren Sie dieses Schema für das Profil

   Weitere Informationen zum Hinzufügen und Entfernen von Feldergruppen und einzelnen Feldern zu einem Schema finden Sie unter [Erstellen und Bearbeiten von Schemata über die Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=de).

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
