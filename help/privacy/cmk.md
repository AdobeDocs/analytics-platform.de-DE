---
title: Vom Kunden verwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenverwaltete Schlüssel für Customer Journey Analytics einrichten.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 66%

---

# Vom Kunden verwaltete Schlüssel

Adobe Customer Journey Analytics bietet die Option für [Gesundheitsschild](https://www.adobe.com/trust/compliance/hipaa-ready.html) Kunden von Privacy &amp; Security Shield verwenden einen Azure Customer Managed Key (CMK), der auf Ihre Customer Journey Analytics-Daten angewendet werden soll.  Beachten Sie, dass dieser Prozess vom [Einrichten von Adobe Experience Platform-CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=de) getrennt ist.

>[!NOTE]
>
>Vom Kunden verwaltete Schlüssel sind derzeit nur für Unternehmen verfügbar, die das Add-on-Angebot für [Healthcare Shield oder Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html?lang=de) gekauft haben.

## Einrichten von CMK für Customer Journey Analytics

Führen Sie die folgenden Schritte aus, um CMK für Customer Journey Analytics einzurichten:

1. Stellen Sie sicher, dass Sie über eine Berechtigung für Adobe Customer Journey Analytics CMK verfügen, indem Sie sich mit Ihrem Adobe Account-Team in Verbindung setzen.
1. Stellen Sie sicher, dass Sie in Azure ein Administrator mit einer privilegierten Rolle sind, z. B. „Anwendungsadministrator“, „Cloud-Anwendungsadministrator“ oder „globaler Administrator“. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/active-directory/roles/permissions-reference)
1. Erstellen Sie ein neues Azure Key Vault, das nur mit Customer Journey Analytics verwendet werden soll. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/key-vault/general/)
1. Gewähren Sie dem Adobe Azure-Programm Zugriff auf den Schlüssel im Schlüsseltresor. Dies ist die Adobe-Anwendungs-ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, um die CMK-Einrichtung anzufordern. Fügen Sie den Azure-URI in Ihr Ticket ein. Der URI befindet sich im Feld **Schlüsselkennung** Ihres Azure-Schlüssels.

   ![](assets/key-identifier.png)

1. Die Kundenunterstützung von Adobe bestätigt den Abschluss der CMK-Anwendung auf Ihren Customer Journey Analytics-Daten.

Alle von Platform verwendeten Daten werden während der Übertragung und im Ruhezustand verschlüsselt, um Ihre Daten sicher zu halten – mit oder ohne CMK. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=de) zur Verschlüsselung in Adobe Experience Platform.
