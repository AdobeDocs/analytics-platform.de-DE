---
title: Erstellen der Quell-Connector- und Zuordnungsfelder für Analytics
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector und die Zuordnungsfelder erstellen.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 3%

---

# Erstellen der Quell-Connector- und Zuordnungsfelder für Analytics

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics-Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten im Customer Journey Analytics verwendet werden.

Bei den folgenden Schritten wird davon ausgegangen, dass Sie beim Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) ein XDM-Schema erstellen möchten, da Sie ein optimiertes Schema wünschen, das auf die Anforderungen Ihres Unternehmens und die von Ihnen verwendeten Platform-Anwendungen zugeschnitten ist.[

Nachdem Sie Ihr XDM-Schema erstellt haben, müssen Sie den Adobe Analytics-Quell-Connector erstellen, der für historische Daten verwendet werden soll.

Umfassendere, allgemeine Richtlinien zum Erstellen eines Quell-Connectors finden Sie unter [Erstellen einer Adobe Analytics-Quellverbindung in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de).

So erstellen Sie einen Adobe Analytics-Quell-Connector zur Verwendung für historische Daten:

1. Wählen Sie in der Platform-Benutzeroberfläche im Abschnitt **[!UICONTROL Verbindungen]** in der linken Leiste **[!UICONTROL Quellen]** aus.

1. Wählen Sie **[!UICONTROL Adobe-Anwendungen]** aus der Liste der [!UICONTROL KATEGORIEN] aus.

1. Wählen Sie **[!UICONTROL Daten hinzufügen]** in der Adobe Analytics-Kachel aus.

   ![Adobe Experience Platform-Fenster mit ausgewählten Quellen zusammen mit Adobe-Anwendungen und hervorgehobenen Daten hinzufügen](./assets/sources-overview.png).

1. Wählen Sie **[!UICONTROL Report Suite]** und dann aus der Liste der Report Suites die Report Suite aus, die die historischen Daten enthält, die Sie im Customer Journey Analytics verwenden möchten.

   ![Adobe Experience Platform-Fenster mit der Report Suites-Liste](./assets/report-suites.png)

1. Wählen Sie oben rechts im Bildschirm **[!UICONTROL Weiter]** aus.

1. Wählen Sie **[!UICONTROL Benutzerdefiniertes Schema]** und dann das Schema aus, das Sie in [Erstellen eines XDM-Schemas mit der Adobe Analytics-Feldergruppe](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md) erstellt haben. <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Ordnen Sie jede Adobe Analytics-Dimension einer benutzerdefinierten XDM-Schemadimension zu.

   1. Wählen Sie im Abschnitt **[!UICONTROL Standardfelder zuordnen]** die Registerkarte **[!UICONTROL Benutzerdefiniert]** aus.

   1. Wählen Sie **[!UICONTROL Neue Zuordnung hinzufügen]** aus.

   ![Schemafelder zuordnen](assets/schema-mapping.png)

   1. Wählen Sie im Feld **[!UICONTROL Source]** ein Adobe Analytics -Feld aus der Feldergruppe Adobe Analytics ExperienceEvent Template aus. Wählen Sie dann im Feld **[!UICONTROL Ziel]** das XDM-Feld aus, dem Sie es zuordnen möchten.

   1. Wiederholen Sie diesen Vorgang für jedes Feld in der Feldergruppe &quot;Adobe Analytics ExperienceEvent Template&quot;, mit dem Sie Daten in Adobe Analytics erfassen.

1. Wählen Sie oben rechts im Bildschirm **[!UICONTROL Weiter]** aus.

1. Benennen Sie den Datenfluss und geben Sie (optional) eine Beschreibung ein.

   ![Adobe Experience Platform-Fenster, das den Detailabschnitt des Datenflusses hervorhebt](./assets/dataflow-detail.png)

1. Wählen Sie oben rechts im Bildschirm **[!UICONTROL Weiter]** aus.

1. Überprüfen Sie die Verbindung und wählen Sie dann **[!UICONTROL Beenden]** aus.

   ![Adobe Experience Platform-Fenster, das die Abschnitte Verbinden und Datentyp zur Überprüfung hervorhebt](./assets/review.png)

   Nachdem die Verbindung erstellt wurde, wird der Datenfluss automatisch erstellt, um einen Datensatz mit den Adobe Analytics-Daten aus Ihrer Report Suite zu füllen. Der Datenfluss erfasst bis zu 13 Monate historischer Daten für Produktions-Sandboxes. Die Aufstockung in Nicht-Produktions-Sandboxes ist auf drei Monate beschränkt.

   Wenn Sie den Analytics-Quell-Connector verwenden, um historische Daten in Ihre Customer Journey Analytics Web SDK-Implementierung zu übertragen, müssen Sie diesen automatisch erstellten Datensatz zu der Verbindung hinzufügen, die Sie für Ihre Web SDK-Implementierung erstellt haben.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[




