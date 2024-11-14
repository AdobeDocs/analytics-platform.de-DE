---
title: Erstellen eines abgeleiteten Marketing-Kanal-Felds für Customer Journey Analytics
description: Erfahren Sie, wie Sie ein abgeleitetes Marketing-Kanal-Feld für Customer Journey Analytics erstellen.
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

# Erstellen eines abgeleiteten Marketing-Kanal-Felds für Customer Journey Analytics

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Bei Verwendung des Analytics-Quell-Connectors fließen die Daten der Marketing-Kanäle über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Verwenden von Marketing-Kanal-Dimensionen](/help/use-cases/aa-data/marketing-channels.md).

Um bei Verwendung des Experience Platform Web SDK Marketingkanäle in Customer Journey Analytics zu verwenden, können Sie abgeleitete Felder in einer Datenansicht verwenden, um dieselben Marketingkanäle und Verarbeitungsregeln für Customer Journey Analytics neu zu erstellen.

1. Wählen Sie unter Customer Journey Analytics die Datenansicht aus, der Sie Marketingkanäle hinzufügen möchten.

1. Wählen Sie in der Datenansicht die Registerkarte **[!UICONTROL Komponenten]** aus.

1. Wählen Sie in der linken Leiste **[!UICONTROL abgeleitetes Feld erstellen]** aus.

1. Wählen Sie im Dialogfeld **[!UICONTROL abgeleitetes Feld erstellen]** die Option **[!UICONTROL Funktionsvorlagen]** aus dem Dropdown-Menü.

   ![Vorlagen für abgeleitete Feldfunktionen erstellen](assets/derived-field-create.png)

1. Ziehen Sie die Vorlage **[!UICONTROL Marketingkanäle]** auf die leere Arbeitsfläche.

1. Passen Sie die Logik für jeden Marketing-Kanal an, um sicherzustellen, dass sie mit der Logik übereinstimmt, die Sie zur Identifizierung der einzelnen Kanäle in Ihrer Adobe Analytics-Umgebung verwenden.

   Sie können die Namen der Ausgabekanäle ändern oder eine Logik hinzufügen, um zusätzliche unternehmensspezifische Kanäle zu identifizieren.

1. Geben Sie in der rechten Spalte einen Namen und eine Beschreibung für den Marketing-Kanal an.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

   Ihr neues abgeleitetes Feld wird zum Container Abgeleitete Felder > als Teil der Schemafelder in der linken Leiste Ihrer Datenansicht hinzugefügt.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
