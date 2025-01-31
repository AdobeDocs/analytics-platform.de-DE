---
title: Einstellungen für Produktnutzungsdaten
description: Produktnutzungseinstellungen aktivieren, deaktivieren oder konfigurieren.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 23%

---

# Einstellungen für Produktnutzungsdaten {#product-usage-data-settings}

Die _Dateneinstellungen_ übernimmt die Konfiguration der Produktnutzung. Mithilfe dieser Seite können Sie die Produktnutzung für Ihr Unternehmen aktivieren oder deaktivieren. Sie können auch konfigurieren, unter welcher Adobe Experience Platform-Sandbox der Datensatz erstellt wird, und das Datenaufbewahrungsfenster bei Bedarf überschreiben. Sie ist nur für Produktadministratoren sichtbar.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Produktnutzung]** > **[!UICONTROL Dateneinstellungen]**

>[!IMPORTANT]
>Wenn Sie diese Funktion aktivieren, müssen Sie die Nutzungsbedingungen akzeptieren, bevor Sie sie verwenden können. Wenn Sie diese Nutzungsbedingungen akzeptieren, tun Sie dies im Namen Ihrer gesamten Organisation.

Folgende Einstellungen sind auf dieser Seite verfügbar:

* **[!UICONTROL Produktnutzung aktivieren]**: Schaltet die Verfügbarkeit der Datenerfassung für die Produktnutzung um. Wenn Sie die Produktnutzung aktivieren und sie dann später deaktivieren, werden der Datensatz, die Verbindung und die Datenansicht nicht gelöscht. Das Tracking ist für Ihre Organisation global deaktiviert, wenn es deaktiviert ist.
* **[!UICONTROL Sandbox]**: Bestimmt die Adobe Experience Platform-Sandbox, unter der das Schema und der Datensatz erstellt werden. Die ausgewählte Sandbox hat keine Auswirkungen auf die Erfassung von Produktnutzungsdaten. Wenn Sie diese Sandbox-Einstellung ändern, werden alle vorhandenen Daten gelöscht. Ein neuer Datensatz, eine neue Verbindung und eine neue Datenansicht werden in der ausgewählten Sandbox erstellt.
* **[!UICONTROL Datenaufbewahrungsfenster überschreiben]**: Jeder Datensatz verfügt über ein standardmäßiges Datenaufbewahrungsfenster. Wenn diese Einstellung deaktiviert ist, folgt die Produktnutzung diesem Standardzeitraum. Sie können diese Einstellung aktivieren, wenn Sie die Aufbewahrungsdauer der Daten verkürzen möchten. Verkürzung des Zeitfensters für die Datenaufbewahrung, Senkung der Kosten und Einhaltung von mitarbeiterspezifischen Datenschutzrichtlinien. Sie können die Datenaufbewahrung nicht über das standardmäßige Datenaufbewahrungsfenster des Datensatzes hinaus erweitern.

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
