---
title: Einstellungen für Produktnutzungsdaten
description: Sie können die Einstellungen zur Produktnutzung aktivieren, deaktivieren oder konfigurieren.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '356'
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
