---
title: Fehlen von Berechtigungen
description: Erfahren Sie, wie Sie Probleme beheben können, die durch fehlende Berechtigungen verursacht werden
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# Fehlen von Berechtigungen

Customer Journey Analytics funktioniert nicht ordnungsgemäß, wenn bestimmte Adobe Experience Platform-Berechtigungen nicht vorhanden sind.

Beispiel: Nach der Erstellung einer [Verbindung](../connections/overview.md) und [Datenansicht](../data-views/data-views.md) wird möglicherweise die folgende Fehlermeldung im Abschnitt [Komponenten](/help/data-views/create-dataview.md#components) angezeigt:


>[!BEGINSHADEBOX]

*[!UICONTROL Beim Abrufen der DULE-Richtlinien ist ein Fehler aufgetreten. Bitte überprüfen Sie die Kontoberechtigungen, Richtlinien oder Labels.  Meldung: Verboten.]*

>[!ENDSHADEBOX]


1. Stellen Sie sicher, dass Sie über die richtige Zugriffskontrolle verfügen:

   * Sie müssen über System- oder Produktadministratorberechtigungen für eine Organisation verfügen, die ein Experience Platform-Produkt besitzt. Weiterführende Informationen dazu finden Sie unter [Zugriffskontrolle – Übersicht](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/home#platform-permissions).

   * Sie müssen eine Benutzerin oder ein Benutzer im Produktprofil „AEP-Default-All-Users“ sein. Fragen Sie Ihre Admins, ob Sie nicht berechtigt sind, sich diesem Profil hinzuzufügen. Weitere Informationen finden Sie unter [Zugriffskontrolle – Hierarchie und Workflow](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/home#access-control-hierarchy-and-workflow).


1. Navigieren Sie zur Benutzeroberfläche von Adobe Experience Cloud.

1. Wählen Sie **[!UICONTROL Berechtigungen]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Rollen]** aus.

1. Navigieren Sie zur entsprechenden Rolle.

1. Wählen Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** aus, um die Rolle zu bearbeiten.

1. Vergewissern Sie sich, dass **[!UICONTROL Richtlinien zur Datennutzung verwalten]** und **[!UICONTROL Richtlinien zur Datennutzung anzeigen]** zum Container **[!UICONTROL Data Governance]** hinzugefügt werden.

1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Änderungen zu speichern.
