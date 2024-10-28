---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 56%

---

# Erstellen eines XDM-Schemas zur Verwendung mit Customer Journey Analytics

>[!NOTE]
>
>Diese Dokumentation sollte verwendet werden, nachdem der Fragebogen [Adobe Analytics zum Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) ausgefüllt wurde.
> 
>Führen Sie die Schritte auf dieser Seite nur aus, nachdem Sie alle vorherigen Schritte ausgeführt haben, die dynamisch für Ihr Unternehmen generiert wurden.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics auf Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

>[!IMPORTANT]
>
>Bevor Sie mit der Erstellung Ihres XDM-Schemas beginnen, wenden Sie sich an Ihr Datenteam und andere Beteiligte in Ihrer Organisation, um das ideale Schema für Customer Journey Analytics und die anderen von Ihnen verwendeten Adobe Experience Platform-Anwendungen zu ermitteln. Weitere Informationen finden Sie unter [Architektur Ihres Schemas für die Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Adobe empfiehlt, beim Upgrade auf Customer Journey Analytics ein Experience-Datenmodell (XDM)-Schema zu erstellen. Ein XDM-Schema ermöglicht ein optimiertes Schema, das auf die Bedürfnisse Ihres Unternehmens und die spezifischen von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist. Wenn Änderungen am Schema erforderlich sind, müssen Sie nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.

## Erstellen des Schemas

Das von Ihnen definierte XDM-Schema stellt das Modell der Daten dar, die Sie in Adobe Experience Platform erfassen.

So erstellen Sie ein Schema:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. Wählen Sie in Adobe Experience Platform in der linken Leiste **[!UICONTROL Schemas]** in [!UICONTROL DATENVERWALTUNG] aus.

1. Wählen Sie **[!UICONTROL Schema erstellen]** aus.

1. Im Schritt Klasse auswählen des Assistenten Schema erstellen :

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

1. Auf der Registerkarte Struktur des Beispielschemas:

   1. Wählen Sie **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen] aus.

      ![Hinzufügen der Feldergruppe](assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   1. Wählen Sie im Dialog [!UICONTROL Feldergruppen hinzufügen] die Feldergruppe **[!UICONTROL AEP Web SDK ExperienceEvent]** aus der Liste aus.

      ![Die Feldergruppe „AEP Web SDK ExperienceEvent“](assets/select-aepwebsdk-experienceevent.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören, z. B. `web > webPageDetails > name`.

      ![Vorschau der Feldergruppe „AEP Web SDK ExperienceEvent“](assets/aepwebsdk-experiencevent-preview.png)

      Wählen Sie **[!UICONTROL Zurück]** aus, um die Vorschau zu schließen.

   1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

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

1. Wählen Sie das Stammelement Ihres Schemas aus, das den Namen des Schemas trägt, und wählen Sie dann den Umschalter **[!UICONTROL Profil]** aus.

   Sie werden aufgefordert, das Schema für das Profil zu aktivieren. Nach der Aktivierung werden Daten, die auf der Basis dieses Schemas in Datensätze aufgenommen werden, zum Echtzeit-Kundenprofil hinzugefügt.

   Weitere Informationen finden Sie im Abschnitt [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >    Nachdem Sie ein für ein Profil aktiviertes Schema gespeichert haben, kann es für das Profil nicht mehr deaktiviert werden.

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

1. Führen Sie die Aktualisierungsschritte aus, die für Ihr Unternehmen dynamisch vom Fragenkatalog [Adobe Analytics zu Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) generiert wurden.

