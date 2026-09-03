---
title: Einstellungen für Produktnutzungsdaten
description: Sie können die Einstellungen zur Produktnutzung aktivieren, deaktivieren oder konfigurieren.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
autotag-review: '2026-05-19T09:31:13.042Z'
TQID: 'https://experienceleague.adobe.com/5aCc69OL9tJ1-5fq0OpSrqpYhLjZgbT1auS0csSDxUA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
  - id: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 100%

---

# Einstellungen für Produktnutzungsdaten {#product-usage-data-settings}

Auf der Seite _Dateneinstellungen_ erfolgt die Konfiguration der Produktnutzung. Auf dieser Seite können Sie die Produktnutzung für Ihre Organisation aktivieren oder deaktivieren. Sie können auch konfigurieren, unter welcher Adobe Experience Platform-Sandbox der Datensatz erstellt wird, und das Datenspeicherungsfenster bei Bedarf überschreiben. Es ist nur für Produktadmins sichtbar.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Produktnutzung]** > **[!UICONTROL Dateneinstellungen]**

>[!IMPORTANT]
>Wenn Sie diese Funktion aktivieren, müssen Sie die Nutzungsbedingungen akzeptieren, bevor Sie sie verwenden können. Wenn Sie diese Nutzungsbedingungen akzeptieren, tun Sie dies im Namen Ihrer gesamten Organisation.

Auf dieser Seite sind die folgenden Einstellungen verfügbar:

* **[!UICONTROL Produktnutzung aktivieren]**: Schaltet die Verfügbarkeit der Erfassung von Produktnutzungsdaten um. Wenn Sie die Produktnutzung aktivieren und sie dann später deaktivieren, werden der Datensatz, die Verbindung und die Datenansicht nicht gelöscht. Wenn das Tracking ausgeschaltet wird, ist es für Ihre gesamte Organisation deaktiviert.
* **[!UICONTROL Sandbox]**: Bestimmt die Adobe Experience Platform-Sandbox, unter der das Schema und der Datensatz erstellt werden. Die ausgewählte Sandbox hat keine Auswirkungen auf die Erfassung von Produktnutzungsdaten. Wenn Sie diese Sandbox-Einstellung ändern, werden alle vorhandenen Daten gelöscht. In der ausgewählten Sandbox werden ein neuer Datensatz, eine neue Verbindung und eine neue Datenansicht erstellt.
* **[!UICONTROL Datenspeicherungsfenster überschreiben]**: Jeder Datensatz verfügt über ein standardmäßiges Datenspeicherungsfenster. Wenn diese Einstellung deaktiviert ist, folgt die Produktnutzung diesem Standardzeitraum. Sie können diese Einstellung aktivieren, wenn Sie die Dauer der Datenspeicherung verkürzen möchten. Durch die Verkürzung des Datenspeicherungsfensters senken Sie Kosten und ermöglichen die Einhaltung von mitarbeiterspezifischen Datenschutzrichtlinien. Sie können die Datenspeicherung nicht über das standardmäßige Datenspeicherungsfenster des Datensatzes hinaus erweitern.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform-Sandbox"
>abstract="Bestimmt die Adobe Experience Platform-Sandbox, unter der das Schema und der Datensatz erstellt werden."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Überschreiben des Datenspeicherungsfensters"
>abstract="Verkürzen Sie die Verfügbarkeit von Produktnutzungsdaten, um Kosten zu reduzieren oder Datenschutzrichtlinien einzuhalten."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Adobe Experience Platform-Sandbox"
>abstract="Bestimmt die Adobe Experience Platform-Sandbox, unter der das Schema und der Datensatz erstellt werden."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Überschreiben des Datenspeicherungsfensters"
>abstract="Verkürzen Sie die Verfügbarkeit von Produktnutzungsdaten, um Kosten zu reduzieren oder Datenschutzrichtlinien einzuhalten."
