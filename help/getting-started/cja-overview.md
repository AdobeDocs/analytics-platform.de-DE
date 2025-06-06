---
title: Überblick über Customer Journey Analytics
description: Erfahren Sie, wie Sie mit Customer Journey Analytics Analysis Workspace mit Daten aus Experience Platform verwenden können.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: ht
source-wordcount: '985'
ht-degree: 100%

---

# Überblick über Customer Journey Analytics

Customer Journey Analytics ist eine Analytics-Lösung der nächsten Generation von Adobe, mit der Sie die Funktionen von Analysis Workspace mit Daten von Adobe Experience Platform nutzen können. Sie kann die Daten mehrerer Jahre aufschlüsseln, segmentieren, abfragen und visualisieren und wird mit der Fähigkeit von Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des **Experience-Datenmodells (XDM)** können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Mit dem **Abfrage-Service von Adobe Experience Platform** können Sie SQL-kompatible Tools und Frameworks verwenden, um alle Ihre Daten abzufragen und zu bearbeiten.

Die allgemeine Architektur von Customer Journey Analytics ist im Folgenden dargestellt:

![In diesem Abschnitt wird die Architektur von Customer Journey Analytics erläutert](assets/cja-architecture.png)


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Customer Journey-Analysen: Analytik für das Erlebnis-Business](https://video.tv.adobe.com/v/30090/?quality=12&learn=on){target="_blank"} finden Sie ein Einführungsvideo zu Customer Journey Analytics.

>[!ENDSHADEBOX]


## Vergleich von Customer Journey Analytics und herkömmlichem Adobe Analytics

Customer Journey Analytics ergänzt den Umfang von Adobe Analytics durch benutzerfreundliche kanalübergreifende Funktionen. Außerdem werden die Einschränkungen, die es in früheren Versionen von Adobe Analytics gibt, aufgehoben. Einige wichtige Verbesserungen sind:

* **Unbegrenzte Variablen und Ereignisse**: Die Konzepte von eVars, Props und Ereignissen existieren nicht mehr. Die Daten werden in erster Linie in Dimensionen und Metriken betrachtet. Datensätze können eine unbegrenzte Anzahl an eindeutigen Dimensionen und Metriken aufweisen.
* **Unbegrenzte Anzahl eindeutiger Werte**: Bei Adobe Experience Platform ist die Anzahl eindeutiger Werte nicht beschränkt.
* **Historische Daten ändern**: Mit Adobe Experience Platform können Daten entfernt oder korrigiert werden.
* **Report Suite-übergreifende Daten**: Vorhandene Implementierungen aus mehreren Datensätzen können in Platform kombiniert werden.

>[!TIP]
>
>Wenn Sie Adobe Analytics verwenden und Ihre Adobe Analytics-Daten in Customer Journey Analytics verwenden möchten, finden Sie weitere Informationen in der Schnellstartanleitung [Aufnehmen und Verwenden von Daten aus dem herkömmlichen Adobe Analytics](../data-ingestion/analytics.md) als Teil des Abschnitts [Datenaufnahme](../data-ingestion/data-ingestion.md).

Die erste Version von Customer Journey Analytics enthält viele der in Adobe Analytics enthaltenen Funktionen. Eine vollständige Liste finden Sie unter [Customer Journey Analytics-Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md).

## Wichtige Anwendungsfälle

Customer Journey Analytics unterstützt folgende Anwendungsfälle:

* **Kunden im Journey-Kontext anzeigen**: Sie können Daten sequenziell über mehrere Kanal hinweg anzeigen und analysieren. Daten aus Ihrem Callcenter, aus PoS-Systemen und aus Online-Eigenschaften können zu einer Berichterstellungsansicht zusammengefasst werden.
* **Einblicke für jedermann zugänglich machen**: Geben Sie allen Benutzern Datenzugriff, sodass mehr Benutzer datengestützte Geschäftsentscheidungen treffen können. Jeder in der Organisation, der für einen Aspekt des Kundenerlebnisses verantwortlich ist, kann auf der Grundlage vollständigerer Daten schneller echte Entscheidungen treffen.
* **Möglichkeiten der Datenwissenschaft für Ihre Analysten nutzen**: Mit Customer Journey Analytics können normale Menschen mithilfe der Datenwissenschaft tiefe Einblicke und Analysen gewinnen.
* **Datensätze visualisieren und mit ihnen mithilfe von Ad-hoc-Berichten interagieren**: Der Arbeitsbereich kann jeden Datensatz aus Adobe Experience Platform verwenden, sofern er einigen Grundregeln entspricht.
* **Nicht-Webdaten anzeigen**: Arbeitsbereich ist nicht mehr auf eine starre Definition eines „Treffers“ oder „Ereignisses“ beschränkt. Benutzerdefinierte Schemata ermöglichen die vollständige Kontrolle über Daten und Definitionen.
* **Mehr Kontrolle über die Datenmanipulationen**: Sie können Daten ändern, die Sie hochgeladen haben, Datensätze erstellen und sie in den Arbeitsbereich importieren. Adobe Experience Platform bietet Tools zum Abfragen, Extrahieren, Transformieren und Laden über den Abfrage-Service von Experience Platform.

## Voraussetzungen

Bevor Sie Customer Journey Analytics verwenden können, müssen die folgenden Voraussetzungen erfüllt sein:

* Ihr Unternehmen hat einen aktiven Vertrag mit Adobe Analytics für Select, Prime oder Ultimate mit dem Add-on Customer Journey Analytics. Wenn Sie sich nicht sicher sind, welche Art von Vertrag Sie haben oder ob Sie über das Customer Journey Analytics-Add-on verfügen, wenden Sie sich an Ihr Adobe-Accountteam.
* Ihre Organisation wurde für Adobe Experience Platform freigeschaltet.
* Sie können Customer Journey Analytics auch als eigenständiges Produkt erwerben, ohne dass Adobe Analytics erforderlich ist.

## Zugriffssteuerung

Siehe [Zugriffssteuerung](/help/technotes/access-control.md).

## Aktualisierungen der Terminologie

Verschiedene Funktionen von Customer Journey Analytics wurden gegenüber dem herkömmlichen Adobe Analytics umbenannt, um sie an Branchenstandards anzupassen. Unter anderem wurden folgende Aktualisierungen bei der Terminologie vorgenommen:

* Virtuelle Report Suites werden jetzt als „Datenansichten“ bezeichnet.
* Klassifizierungen werden jetzt als Suchdatensätze bezeichnet.
* Kundenattribute werden jetzt als Profildatensätze bezeichnet.
* Treffer-Container werden jetzt als Ereignis-Container bezeichnet.
* Besuchs-Container werden jetzt als Sitzungs-Container bezeichnet.
* Besucher-Container werden jetzt als Personen-Container bezeichnet.

## Weitere auf Adobe Experience Platform basierende Funktionen

Customer Journey Analytics ist eine von vielen Funktionen, die auf Adobe Experience Platform basieren. Mehrere andere Funktionen, die ebenfalls auf Experience Platform basieren, ermöglichen die optimale Datennutzung.

Mit Adobe Experience Platform können Sie Kundendaten und Inhalte aus beliebigen Systemen zentral zusammenführen und standardisieren sowie mithilfe von Datenwissenschaft und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern. Kundendaten in Platform werden als Datensätze gespeichert, die aus einem Schema und Datenstapeln bestehen. Weitere Informationen zu Platform finden Sie unter [Übersicht über die Adobe Experience Platform-Architektur](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=de).

Von der Datenerfassung bis zum direkten SQL-Zugriff sind mehrere Komponenten von Experience Platform für Customer Journey Analytics von zentraler Bedeutung und dienen als Ergänzung:

* [Abfrage-Service von Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de): Verwenden Sie Standard-SQL, um Daten von Adobe Experience Platform abzurufen, z. B. Adobe-Lösungsdaten, Erstanbieter-Kundendaten oder andere Platform-Daten. Es handelt sich dabei um ein Server-loses Tool, mit dem Sie beliebige Datensätze zusammenführen und die Abfrageergebnisse als neuen Datensatz erfassen können. Dieser kann in Berichten oder zur Aufnahme in den Profil-Service verwendet werden. Mit dem Abfrage-Service von Experience Platform können Sie Ökosysteme für die Datenanalyse erstellen und sich ein Bild über die Verbraucherinnen und Verbraucher über ihre verschiedenen Interaktionskanäle hinweg machen. Zu diesen Kanälen gehören beispielsweise PoS-Systeme, Web-, mobile und CRM-Systeme usw.
* [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de):
* [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=de)

## Videos

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Arbeiten mit Daten in Customer Journey Analytics](https://video.tv.adobe.com/v/32112/?quality=12&learn=on){target="_blank"} finden Sie ein Einführungsvideo zum Arbeiten mit Daten in Customer Journey Analytics.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Architektur und Integration](https://video.tv.adobe.com/v/32483/?quality=12&learn=on){target="_blank"} finden Sie ein Einführungsvideo zur Architektur und Integration von Customer Journey Analytics.

>[!ENDSHADEBOX]

>[!MORELIKETHIS]
>
>* [Schnellkurs zu Adobe Customer Journey Analytics für Analystinnen und Analysten](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/adobe-customer-journey-analytics-crash-course-for-analysts/ba-p/719261?profile.language=de)
>* [Optimieren Ihrer Denkweise und des Adobe Customer Journey Analytics-Workflows: Team-Modelle für Organisationen jeder Größe](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/optimizing-your-mindset-and-adobe-customer-journey-analytics/ba-p/721456?profile.language=de)
>* [Schaffen von organisatorischer Bereitschaft: Ein Leitfaden für die Skalierung von Adobe Customer Journey Analytics, bei dem die Mitarbeitenden im Vordergrund stehen](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/building-organizational-readiness-a-people-first-guide-to/ba-p/723273?profile.language=de)
