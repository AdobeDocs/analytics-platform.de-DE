---
title: Customer Journey Analytics und Data Governance
description: Beschreibt, wie Data Governance in Customer Journey Analytics funktioniert.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 74%

---

# Adobe Customer Journey Analytics und Data Governance

Im Allgemeinen werden alle Data-Governance-bezogenen Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen.

## Data Governance

Die Integration zwischen Adobe Customer Journey Analytics und [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=de) ermöglicht die Kennzeichnung sensibler Customer Journey Analytics-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen.

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Beschriftungen hinzugefügt, die Benutzer darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Datenverantwortliche in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Daher können Ihre Customer Journey Analytics-Benutzer Daten in dem Bewusstsein, dass sie den von Data Stewards definierten Richtlinien entsprechen, sicherer verwenden.

[Weitere Informationen](/help/data-views/data-governance.md)

## DSGVO

Customer Journey Analytics wird nicht in den zentralen Service der Datenschutz-Grundverordnung (DSGVO) eingebunden, sondern übernimmt stattdessen alle in Experience Platform vorgenommenen Änderungen. Wir sind darauf angewiesen, dass Platform Data Lake die DSGVO-Löschanfragen durchführt und uns benachrichtigt, wenn diese in der Pipeline abgeschlossen sind. Wir überwachen die Pipeline und synchronisieren alle Änderungen, die an betroffenen Batches in Customer Journey Analytics für Ereignis-Datensätze vorgenommen wurden. Profil- und Nachschlagedatensätze, die von DSGVO-Löschanfragen betroffen sind, werden nach jeder Löschanfrage vollständig neu erfasst. Wir garantieren, dass Löschanfragen innerhalb von sieben Tagen ab dem Löschvorgang in Data Lake ausgeführt werden.

## CCPA

Der California Consumer Privacy Act (CCPA) erweitert die Datenschutzrechte und den Verbraucherschutz für Einwohner von Kalifornien, USA. Dieses Gesetz trat am 1. Januar 2020 in Kraft.
Der CCPA bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden. Zusätzlich können sie dem Verkauf ihrer personenbezogenen Daten widersprechen.
In Übereinstimmung mit dem CCPA unterstützt Privacy Service Anfragen zur Abmeldung vom Verkauf personenbezogener Daten.
