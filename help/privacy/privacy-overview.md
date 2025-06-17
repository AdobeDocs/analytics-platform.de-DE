---
title: Customer Journey Analytics und Data Governance
description: Beschreibt, wie Data Governance in Customer Journey Analytics funktioniert.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 40706e3118cbaf7582d8625d307358b16f1836ac
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 90%

---

# Adobe Customer Journey Analytics und Data Governance

Im Allgemeinen werden alle Data-Governance-bezogenen Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen.

## Data Governance

Die Integration zwischen Adobe Customer Journey Analytics und [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=de) ermöglicht die Kennzeichnung sensibler Daten von Customer Journey Analytics und die Durchsetzung von Datenschutzrichtlinien.

Datenschutz-Label und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen.

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Labels hinzugefügt, die Benutzende darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Datenverantwortliche in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Dadurch können Ihre Customer Journey Analytics-Benutzenden die Daten sicherer nutzen, da sie wissen, dass sie mit den von den Datenverantwortlichen festgelegten Richtlinien übereinstimmen.

[Weitere Informationen](/help/data-views/data-governance.md)

## Datenschutzanfragen

Adobe bearbeitet Datenschutzanfragen gemäß den geltenden lokalen und internationalen Gesetzen.

Da Customer Journey Analytics in Adobe Experience Platform verfügbare Daten verwendet, bietet Adobe den [Adobe Experience Platform Privacy Service ](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) zum Senden von Datenzugriffs- und Löschanfragen an. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

## DSGVO

Customer Journey Analytics wird nicht in den zentralen Service der Datenschutz-Grundverordnung (DSGVO) eingebunden, sondern übernimmt stattdessen alle in Experience Platform vorgenommenen Änderungen. Customer Journey Analytics ist auf den Data Lake von Platform angewiesen, um DSGVO-Löschanfragen durchzusetzen und Customer Journey Analytics zu benachrichtigen, wenn Anfragen abgeschlossen sind. Alle Änderungen an betroffenen Batches in Customer Journey Analytics für Ereignis-Datensätze werden mit Platform-Daten synchronisiert. Profil- und Lookup-Datensätze, die von DSGVO-Löschanfragen betroffen sind, werden nach jeder Löschanfrage vollständig neu erfasst. Löschanfragen werden in der Regel innerhalb von 7 Tagen nach einem Löschereignis im Data Lake abgeschlossen.

## CCPA

Der California Consumer Privacy Act (CCPA) erweitert die Datenschutzrechte und den Verbraucherschutz für Einwohner von Kalifornien, USA. Dieses Gesetz trat am 1. Januar 2020 in Kraft.
Der CCPA bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden. Zusätzlich können sie dem Verkauf ihrer personenbezogenen Daten widersprechen.
In Übereinstimmung mit dem CCPA unterstützt Privacy Service Anfragen zur Abmeldung vom Verkauf personenbezogener Daten.

>[!MORELIKETHIS]
>
>* [Blog: Effektive Governance in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4?lang=de)
