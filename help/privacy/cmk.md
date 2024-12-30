---
title: Vom Kunden verwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenseitig verwaltete Schlüssel für das Customer Journey Analytics einrichten.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 57%

---

# Vom Kunden verwaltete Schlüssel

Adobe Customer Journey Analytics bietet Kunden von [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) und Privacy &amp; Security Shield die Option, einen Azure Customer Managed Key (CMK) zu verwenden, der auf Ihre Customer Journey Analytics-Daten angewendet wird.  Beachten Sie, dass dieser Prozess vom [Einrichten von Adobe Experience Platform-CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=de) getrennt ist.

>[!NOTE]
>
>Vom Kunden verwaltete Schlüssel sind derzeit nur für Unternehmen verfügbar, die das Add-on-Angebot für [Healthcare Shield oder Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html) gekauft haben.

## Einrichten von CMK für Customer Journey Analytics

Führen Sie die folgenden Schritte aus, um CMK für Customer Journey Analytics einzurichten:

1. Stellen Sie sicher, dass Sie eine Berechtigung für Adobe Customer Journey Analytics CMK haben, indem Sie sich an Ihr Adobe-Konto-Team wenden.
1. Stellen Sie sicher, dass Sie in Azure ein Administrator mit einer privilegierten Rolle sind, z. B. „Anwendungsadministrator“, „Cloud-Anwendungsadministrator“ oder „globaler Administrator“. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/active-directory/roles/permissions-reference)
1. Erstellen Sie einen neuen Azure-Schlüsseltresor, der nur mit Customer Journey Analytics verwendet werden soll. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/key-vault/general/)
1. Gewähren Sie dem Adobe Azure-Programm Zugriff auf den Schlüssel im Schlüsseltresor. Dies ist die Adobe-Anwendungs-ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, um die CMK-Einrichtung anzufordern. Fügen Sie den Azure-URI in Ihr Ticket ein. Der URI befindet sich im Feld **Schlüsselkennung** Ihres Azure-Schlüssels.

   ![Schlüsselkennungsfelder, die den URI für https://cmkoberontest.vault.azure.net anzeigen](assets/key-identifier.png)

1. Die Adobe-Kundenunterstützung bestätigt den Abschluss der CMK-Anwendung auf Ihren Customer Journey Analytics-Daten.

Alle von Platform verwendeten Daten werden während der Übertragung und im Ruhezustand verschlüsselt, um Ihre Daten sicher zu halten – mit oder ohne CMK. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=de) zur Verschlüsselung in Adobe Experience Platform.
