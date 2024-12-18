---
title: Einstellungen für Produktnutzungs-Opt-out
description: Verwalten Sie Opt-out-Einstellungen für einzelne Benutzer in Ihrer Organisation.
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 7%

---

# Einstellungen für Produktnutzungs-Opt-out {#product-usage-opt-out-settings}

{{release-limited-testing}}

Auf der Seite _Opt-out-Einstellungen_ können Sie Benutzer in Ihrer Organisation vom Tracking der Produktnutzung ausschließen oder erneut einbeziehen. Sie ist nur für Produktadministratoren sichtbar.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Produktnutzung]** > **[!UICONTROL Opt-out-Einstellungen]**

Die folgenden Einstellungen sind auf dieser Seite verfügbar:

* **[!UICONTROL Opt-out-Benutzer]**: Eine Dropdownliste mit allen Customer Journey Analytics-Benutzern in Ihrer Organisation. Wählen Sie einen Benutzer aus dieser Dropdownliste aus und wählen Sie **[!UICONTROL Opt-out]** aus, um diesen Benutzer vom Tracking der Produktnutzung auszuschließen. Dieser Benutzer wird der unten stehenden Tabelle [!UICONTROL Opt-out-Benutzerliste] hinzugefügt.
* **[!UICONTROL Opt-out-Benutzerliste]**: Eine Tabelle, die alle Benutzer anzeigt, die sich derzeit vom Tracking der Produktnutzung abgemeldet haben. Um einen Benutzer wieder für das Tracking der Produktnutzung zu aktivieren, aktivieren Sie das Kontrollkästchen neben einem bestimmten Benutzer und wählen Sie dann die Schaltfläche **[!UICONTROL Opt-in]** aus.

Adobe verwendet eine Kombination aus Client-seitigem und serverseitigem Tracking, um Produktnutzungsdaten für Ihr Unternehmen zu erfassen. Wenn ein Benutzer zum ersten Mal abgemeldet wird, werden ihm möglicherweise weiterhin clientseitige Tracking-Daten in seinem Debugger angezeigt, bis er sich abmeldet und wieder bei Customer Journey Analytics anmeldet. Die serverseitige Validierung von Adobe stellt sicher, dass clientseitige Tracking-Daten für abgemeldete Benutzer verworfen werden.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Opt-out-Benutzende"
>abstract="Schließen Sie Benutzende vom Produktnutzungs-Tracking aus."
