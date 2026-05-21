---
title: Erstellen eines abgeleiteten Marketing-Kanal-Felds für Customer Journey Analytics
description: Erfahren Sie, wie Sie ein abgeleitetes Marketing-Kanal-Feld für Customer Journey Analytics erstellen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
TQID: https://experienceleague.adobe.com/nwxJ3KEss3SlZxpGB-CW4qDW9QpQqXL1kN-VslhuAVE
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 291
ht-degree: 100%

---

# Erstellen eines abgeleiteten Marketing-Kanal-Felds für Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Erstellen eines abgeleiteten Marketing-Kanal-Felds"
>abstract="Abgeleitete Felder werden in einer Datenansicht erstellt.<br><br>Die Verwendung einer standardmäßigen Marketing-Kanaleinrichtung dauert nur einige Minuten. Das Erstellen einer hochgradig benutzerdefinierten Marketing-Kanaleinrichtung kann mehrere Stunden dauern."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Bei Verwendung des Analytics-Quell-Connectors fließen Marketing-Kanal-Daten über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Verwenden von Marketing-Kanal-Dimensionen](/help/use-cases/aa-data/marketing-channels.md).

Um Marketing-Kanäle in Customer Journey Analytics bei Verwendung des Experience Platform-Web-SDK zu verwenden, können Sie mithilfe von abgeleiteten Feldern in einer Datenansicht dieselben Marketing-Kanäle und Verarbeitungsregeln für Customer Journey Analytics neu erstellen.

1. Wählen Sie in Customer Journey Analytics die Datenansicht aus, der Sie Marketing-Kanäle hinzufügen möchten.

1. Wählen Sie in der Datenansicht die Registerkarte **[!UICONTROL Komponenten]** aus.

1. Wählen Sie in der linken Leiste **[!UICONTROL Abgeleitetes Feld erstellen]** aus.

1. Wählen Sie im Dialogfeld **[!UICONTROL Abgeleitetes Feld erstellen]** im Dropdown-Menü **[!UICONTROL Funktionsvorlagen]** aus.

   ![Erstellen von Feldfunktionsvorlagen für abgeleitete Felder](assets/derived-field-create.png)

1. Ziehen Sie die Vorlage **[!UICONTROL Marketing-Kanäle]** auf die leere Arbeitsfläche.

1. Passen Sie die Logik für jeden Marketing-Kanal an, um sicherzustellen, dass sie mit der Logik übereinstimmt, die Sie zum Identifizieren der einzelnen Kanäle verwenden.

   Sie können die Namen der Ausgabekanäle ändern oder eine Logik hinzufügen, um zusätzliche Kanäle zu identifizieren, die für Ihre Organisation spezifisch sind.

1. Geben Sie in der rechten Spalte einen Namen und eine Beschreibung für den Marketing-Kanal an.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

   Ihr neues abgeleitetes Feld wird als Teil von Schemafeldern in der linken Leiste Ihrer Datenansicht zu „Abgeleitete Felder“ > „Container“ hinzugefügt.

{{upgrade-final-step}}
