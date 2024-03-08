---
title: Fehlende Berechtigungen
description: Erfahren Sie, wie Sie Probleme beheben können, die durch fehlende Berechtigungen verursacht werden.
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Fehlende Berechtigungen

Customer Journey Analytics funktioniert nicht ordnungsgemäß, wenn bestimmte Adobe Experience Platform-Berechtigungen nicht vorhanden sind.

Beispiel: nach der Erstellung eines [Verbindung](../connections/overview.md) und [Datenansicht](../data-views/data-views.md)kann die folgende Fehlermeldung in der [Komponenten](/help/data-views/create-dataview.md#components) Abschnitt:


>[!BEGINSHADEBOX]

*[!UICONTROL Beim Abrufen von DULE-Richtlinien ist etwas schiefgelaufen. Überprüfen Sie die Kontoberechtigungen, Richtlinien oder Bezeichnungen. Nachricht: Verboten.]*

>[!ENDSHADEBOX]


1. Stellen Sie sicher, dass Sie über die richtige Zugriffskontrolle verfügen:

   * Sie müssen über System- oder Produktadministratorberechtigungen für eine Organisation verfügen, die über ein Experience Platform-Produkt verfügt. Siehe [Zugriffskontrolle - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) für weitere Informationen.

   * Sie müssen ein Benutzer im Produktprofil &quot;AEP-Default-All-Users&quot;sein. Fragen Sie Ihren Administrator, ob Sie nicht berechtigt sind, sich diesem Profil hinzuzufügen. Siehe [Zugriffssteuerungshierarchie und Workflow](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) für weitere Informationen.


1. Navigieren Sie zur Adobe Experience Platform-Benutzeroberfläche.

1. Auswählen **[!UICONTROL Berechtigungen]** über die linke Leiste.

1. Auswählen **[!UICONTROL Rollen]**.

1. Navigieren Sie zur entsprechenden Rolle.

1. Auswählen ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** , um die Rolle zu bearbeiten.

1. Sichern **[!UICONTROL Richtlinien zur Datennutzung verwalten]** und **[!UICONTROL Datennutzungsrichtlinien anzeigen]** werden der **[!UICONTROL Data Governance]** Container.

1. Auswählen **[!UICONTROL Speichern]** , um die Änderungen zu speichern.
