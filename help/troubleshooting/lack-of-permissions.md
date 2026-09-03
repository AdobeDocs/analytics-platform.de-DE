---
title: Fehlen von Berechtigungen
description: Erfahren Sie, wie Sie Probleme beheben können, die durch fehlende Berechtigungen verursacht werden
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 94%

---

# Fehlen von Berechtigungen

Customer Journey Analytics funktioniert nicht ordnungsgemäß, wenn bestimmte Adobe Experience Platform-Berechtigungen nicht vorhanden sind.

Beispiel: Nach der Erstellung einer [Verbindung](../connections/overview.md) und [Datenansicht](../data-views/data-views.md) wird möglicherweise die folgende Fehlermeldung im Abschnitt [Komponenten](/help/data-views/create-dataview.md#components) angezeigt:


>[!BEGINSHADEBOX]

*[!UICONTROL Beim Abrufen der DULE-Richtlinien ist ein Fehler aufgetreten. Überprüfen Sie Kontoberechtigungen, Richtlinien oder Beschriftungen. Meldung: Verboten.]*

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
