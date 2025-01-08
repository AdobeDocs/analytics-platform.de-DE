---
title: Kundenverwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenverwaltete Schlüssel für das Customer Journey Analytics einrichten.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 15%

---

# Kundenverwaltete Schlüssel

Adobe Customer Journey Analytics bietet Kunden von [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) und Privacy &amp; Security Shield die Option, kundenverwaltete Schlüssel (CMK) zum Customer Journey Analytics von Daten zu verwenden. Beachten Sie, dass dieser Prozess vom [Adobe Experience Platform CMK-Setup getrennt ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Vom Kunden verwaltete Schlüssel sind nur für Organisationen verfügbar, die das Add-on-Angebot [Healthcare Shield oder Privacy &amp; Security Shield](https://experienceleague.adobe.com/de/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield) erworben haben.

## Einrichten von kundenverwalteten Schlüsseln für das Customer Journey Analytics auf Azure

Führen Sie die folgenden Schritte aus, um CMK für das Customer Journey Analytics einzurichten, das auf Azure ausgeführt wird:

1. Stellen Sie sicher, dass Sie eine Berechtigung für Adobe Customer Journey Analytics CMK haben und dass Ihr Unternehmen Adobe Experience Platform verwendet, das auf Azure ausgeführt wird. Sie können diese Berechtigungen überprüfen, indem Sie sich an Ihr Adobe-Account-Team wenden.
1. Stellen Sie sicher, dass Sie in Azure ein Administrator mit einer privilegierten Rolle sind, z. B. „Anwendungsadministrator“, „Cloud-Anwendungsadministrator“ oder „globaler Administrator“. Weitere Informationen finden Sie unter {0](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference) Integrierte Microsoft Entra-Rollen .[
1. Erstellen Sie einen neuen Azure-Schlüsseltresor, der nur mit Customer Journey Analytics verwendet werden soll. Weitere Informationen finden Sie in der Dokumentation zum Microsoft Azure](https://learn.microsoft.com/de-de/azure/key-vault/general/)Schlüsseltresor .[
1. Gewähren Sie dem Adobe Azure-Programm Zugriff auf den Schlüssel im Schlüsseltresor. Weitere [ finden Sie unter „Konfigurieren von kundenverwalteten Schlüsseln für ](https://learn.microsoft.com/de-de/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault) vorhandenes Konto“. Die Adobe-Anwendungs-ID lautet:

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, um die CMK-Einrichtung anzufordern. Fügen Sie den Azure-URI in Ihr Ticket ein. Der URI befindet sich im Feld **Schlüsselkennung** Ihres Azure-Schlüssels:

   ![Schlüsselkennungsfelder, die den URI für https://cmkoberontest.vault.azure.net anzeigen](assets/key-identifier.png)

1. Adobe Kundenunterstützung bestätigt den Abschluss der CMK-Anwendung auf Ihren Customer Journey Analytics-Daten.

Alle von Platform verwendeten Daten werden während der Übertragung und im Ruhezustand verschlüsselt, um Ihre Daten sicher zu halten, mit oder ohne kundenverwaltete Schlüssel. Informationen zur Adobe Experience Platform-Verschlüsselung finden Sie unter [Datenverschlüsselung in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption).

## Einrichten von kundenverwalteten Schlüsseln zum Customer Journey Analytics auf Amazon Web Services

>[!AVAILABILITY]
>
>Dieser Abschnitt gilt für Implementierungen von Experience Platform, die auf Amazon Web Services (AWS) ausgeführt werden. Experience Platform, das auf AWS ausgeführt wird, steht derzeit einer begrenzten Anzahl von Kunden zur Verfügung. Weitere Informationen zur unterstützten Experience Platform-Infrastruktur finden Sie in der Übersicht zur [Experience Platform-Multi-Cloud](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud).

Wenn Ihr Unternehmen Adobe Experience Platform mit Amazon Web Services verwendet, ist CMK bereits für Sie konfiguriert. Es ist keine zusätzliche Einrichtung erforderlich.
