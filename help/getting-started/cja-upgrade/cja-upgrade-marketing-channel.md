---
title: Erstellen eines von einem Marketing-Kanal abgeleiteten Felds zum Customer Journey Analytics
description: Erfahren Sie, wie Sie ein abgeleitetes Feld für den Marketing-Kanal für das Customer Journey Analytics erstellen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: ef6afb2872b88c82801ceb279dd757e6e1f5e78c
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 5%

---

# Erstellen eines von einem Marketing-Kanal abgeleiteten Felds zum Customer Journey Analytics

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem [Fragebogen für das Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert wurden](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

Bei Verwendung des Analytics-Quell-Connectors fließen Daten von Marketing-Kanälen über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Verwenden von Marketing-Kanal-Dimensionen](/help/use-cases/aa-data/marketing-channels.md).

Um Marketing-Kanäle beim Customer Journey Analytics mit der Experience Platform Web SDK zu verwenden, können Sie abgeleitete Felder in einer Datenansicht verwenden, um dieselben Marketing-Kanäle und Verarbeitungsregeln für das Customer Journey Analytics neu zu erstellen.

1. Wählen Sie in Customer Journey Analytics die Datenansicht aus, der Sie Marketing-Kanäle hinzufügen möchten.

1. Wählen Sie in der Datenansicht die Registerkarte **[!UICONTROL Komponenten]** aus.

1. Wählen **[!UICONTROL Abgeleitetes Feld erstellen]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Dialogfeld]** Abgeleitetes Feld erstellen **[!UICONTROL aus dem Dropdown-Menü]** Funktionsvorlagen“ aus.

   ![Erstellen abgeleiteter Feldfunktionsvorlagen](assets/derived-field-create.png)

1. Ziehen Sie die Vorlage **[!UICONTROL Marketing]** Kanäle“ auf die leere Arbeitsfläche.

1. Passen Sie die Logik für jeden Marketing-Kanal an, um sicherzustellen, dass sie mit der Logik übereinstimmt, die Sie zum Identifizieren der einzelnen Kanäle in Ihrer Adobe Analytics-Umgebung verwenden.

   Sie können die Namen der Ausgabekanäle ändern oder eine Logik hinzufügen, um zusätzliche Kanäle zu identifizieren, die für Ihr Unternehmen spezifisch sind.

1. Geben Sie in der rechten Spalte einen Namen und eine Beschreibung für den Marketing-Kanal an.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

   Ihr neues abgeleitetes Feld wird dem Container Abgeleitete Felder > als Teil von Schemafeldern in der linken Leiste Ihrer Datenansicht hinzugefügt.

1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
