---
title: Erstellen eines von einem Marketing-Kanal abgeleiteten Felds für Customer Journey Analytics
description: Erfahren Sie, wie Sie ein abgeleitetes Feld für einen Marketing-Kanal für Customer Journey Analytics erstellen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 25%

---

# Erstellen eines von einem Marketing-Kanal abgeleiteten Felds für Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Erstellen eines von einem Marketing-Kanal abgeleiteten Felds"
>abstract="Abgeleitete Felder werden in einer Datenansicht erstellt.<br><br>Die Verwendung einer standardmäßigen Einrichtung für Marketing-Kanäle dauert nur einige Minuten. Das Erstellen einer hochgradig benutzerdefinierten Einrichtung für Marketing-Kanäle kann mehrere Stunden dauern."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Bei Verwendung des Analytics-Quell-Connectors fließen Daten von Marketing-Kanälen über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Verwenden von Marketing-Kanal-Dimensionen](/help/use-cases/aa-data/marketing-channels.md).

Um Marketing-Kanäle in Customer Journey Analytics bei Verwendung der Experience Platform Web SDK zu verwenden, können Sie abgeleitete Felder in einer Datenansicht verwenden, um dieselben Marketing-Kanäle und Verarbeitungsregeln für Customer Journey Analytics neu zu erstellen.

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

{{upgrade-final-step}}
