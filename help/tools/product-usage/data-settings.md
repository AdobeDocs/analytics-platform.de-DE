---
title: Einstellungen für Produktnutzungsdaten
description: Produktnutzungseinstellungen aktivieren, deaktivieren oder konfigurieren.
hide: true
hidefromtoc: true
source-git-commit: b3d33561cc29aa1d37efa9f943bc145c16be814c
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 14%

---

# Einstellungen für Produktnutzungsdaten {#product-usage-data-settings}

{{release-limited-testing}}

Die Seite _Dateneinstellungen_ verarbeitet Ihre Produktverwendungskonfiguration. Sie können diese Seite verwenden, um die Produktnutzung für Ihr Unternehmen zu aktivieren oder zu deaktivieren. Sie können auch konfigurieren, unter welcher Adobe Experience Platform-Sandbox der Datensatz erstellt wird, und das Datenaufbewahrungsfenster bei Bedarf überschreiben. Sie ist nur für Produktadministratoren sichtbar.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Produktnutzung]** > **[!UICONTROL Dateneinstellungen]**

>[!IMPORTANT]
>Wenn Sie diese Funktion aktivieren, müssen Sie die Nutzungsbedingungen akzeptieren, bevor Sie sie verwenden können. Wenn Sie diese Geschäftsbedingungen akzeptieren, tun Sie dies im Namen Ihrer gesamten Organisation.

Die folgenden Einstellungen sind auf dieser Seite verfügbar:

* **[!UICONTROL Produktnutzung aktivieren]**: Schaltet die Verfügbarkeit der Datenerfassung zur Produktnutzung um. Wenn Sie die Produktnutzung aktivieren und sie später deaktivieren, werden der Datensatz, die Verbindung und die Datenansicht nicht gelöscht. Das Tracking ist für Ihr Unternehmen global deaktiviert, wenn es deaktiviert wurde.
* **[!UICONTROL Sandbox]**: Bestimmt die Adobe Experience Platform-Sandbox, unter der das Schema und der Datensatz erstellt werden. Die von Ihnen ausgewählte Sandbox wirkt sich nicht auf die Datenerfassung zur Produktnutzung aus. Wenn Sie diese Sandbox-Einstellung ändern, werden alle vorhandenen Daten gelöscht. In der ausgewählten Sandbox wird ein neuer Datensatz, eine neue Verbindung und eine neue Datenansicht erstellt.
* **[!UICONTROL Datenaufbewahrungsfenster überschreiben]**: Jeder Datensatz verfügt über ein standardmäßiges Datenaufbewahrungsfenster. Wenn diese Einstellung deaktiviert ist, folgt bei der Produktnutzung der standardmäßige Zeitraum. Sie können diese Einstellung aktivieren, wenn Sie die Aufbewahrungsdauer der Daten verkürzen möchten. Die Verkürzung des Zeitfensters für die Datenaufbewahrung hilft Ihnen, Kosten zu senken und die Einhaltung von firmenspezifischen Datenschutzrichtlinien zu ermöglichen. Sie können die Datenaufbewahrung nicht über das standardmäßige Datenaufbewahrungsfenster des Datensatzes hinaus erweitern.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform-Sandbox"
>abstract="Bestimmt die Adobe Experience Platform-Sandbox, unter der das Schema und der Datensatz erstellt werden."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Überschreiben des Datenspeicherungsfensters"
>abstract="Verkürzen Sie die Verfügbarkeit von Produktnutzungsdaten, um Kosten zu reduzieren oder Datenschutzrichtlinien einzuhalten."
