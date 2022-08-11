---
title: Customer Journey Analytics und Data Governance
description: Beschreibt, wie Data Governance in Customer Journey Analytics funktioniert.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 51%

---

# Customer Journey Analytics und Data Governance

Im Allgemeinen werden alle Data Governance-bezogenen Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen.

## Data Governance

Die Integration zwischen CJA und [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) ermöglicht die Kennzeichnung sensibler CJA-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbezeichnungen und Richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Arbeitsablauf für CJA-Datenansichten angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen.

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Beschriftungen hinzugefügt, die Benutzer darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Data Stewards in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Daher können Ihre CJA-Benutzer Daten in dem Bewusstsein, dass sie den von Data Stewards definierten Richtlinien entsprechen, sicherer verwenden.

[Weitere Informationen](/help/data-views/data-governance.md)

## DSGVO

Customer Journey Analytics wird nicht in den zentralen Service der Datenschutz-Grundverordnung (DSGVO) eingebunden, sondern übernimmt stattdessen alle in Experience Platform vorgenommenen Änderungen. Wir sind darauf angewiesen, dass Platform Data Lake die DSGVO-Löschanfragen durchführt und uns benachrichtigt, wenn diese in der Pipeline abgeschlossen sind. Wir überwachen die Pipeline und synchronisieren alle Änderungen, die an betroffenen Batches in Customer Journey Analytics für Ereignis-Datensätze vorgenommen wurden. Profil- und Nachschlagedatensätze, die von DSGVO-Löschanfragen betroffen sind, werden nach jeder Löschanfrage vollständig neu erfasst. Wir garantieren, dass Löschanfragen innerhalb von sieben Tagen ab dem Löschvorgang in Data Lake ausgeführt werden.

## CCPA

Der California Consumer Privacy Act (CCPA) erweitert die Datenschutzrechte und den Verbraucherschutz für Einwohner von Kalifornien, USA. Dieses Gesetz trat am 1. Januar 2020 in Kraft.
Der CCPA bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden. Zusätzlich können sie dem Verkauf ihrer personenbezogenen Daten widersprechen.
Zur Vorbereitung auf den CCPA unterstützt der Datenschutzdienst Anfragen zur Abmeldung vom Verkauf personenbezogener Daten.
