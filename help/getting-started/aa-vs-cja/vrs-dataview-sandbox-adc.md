---
title: Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics-Quell-Connector
description: Erfahren Sie mehr über virtuelle Reporting-Umgebungen und Sandbox-Umgebungen.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/U-90bs2lmli3TxdxDyu2jQZvIU29C80tbiHSDyAmGFA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 785
ht-degree: 94%

---

# Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics-Quell-Connector

Adobe bietet eine Vielzahl von Möglichkeiten zum Erstellen virtueller Reporting-Umgebungen und Sandbox-Umgebungen. Es ist nützlich, die Ähnlichkeiten und Unterschiede zwischen den folgenden Funktionen und ihren Beziehungen zum [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) zu überblicken:

* Virtual Report Suites in Adobe Analytics
* Customer Journey Analytics-Datenansichten
* Adobe Experience Platform-Sandboxes

## Virtual Report Suites in Adobe Analytics

Weitere Informationen finden Sie unter [Virtual Report Suites – Übersicht](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=de).

Eine Virtual Report Suite:

* Kann auf Adobe Analytics-Segmenten basieren.
* Kann auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten auf Basis einer Adobe Analytics-Report Suite zur Verwendung durch verschiedene Unternehmens-Teams.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzer in Adobe Analytics zu steuern und diese Daten zu kuratieren.
* Bietet optional Funktionen für die [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) für Adobe Analytics. In diesem Fall kann eine Virtual Report Suite verwendet werden, um eine benutzerdefinierte Definition für „Besuch“ zu erstellen.
* Wird zur Berichtslaufzeit angewendet, ähnlich wie die Segmentauswertung. Dies geschieht, _nachdem_ die Daten in Adobe Analytics erfasst und gespeichert wurden.
* Ist für [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) in Adobe Analytics erforderlich.
* Weist dieselbe Anzahl von Variablen für die Verwendung auf wie eine standardmäßige Report Suite in Analytics (250 eVars, 250 Eigenschaften, 1.000 Ereignisse), allerdings kann durch Kuratierung der Virtual Report Suite begrenzt werden, welche Variablen für Benutzende verfügbar sind.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Einschränkungen einer Virtual Report Suite:

* Sie ist kein Mittel zur Kombination von Report Suites.
* Sie ist nicht in Adobe Analytics Data Warehouse verfügbar.
* Sie ist nicht als Quelle für Datenflüsse in Adobe Experience Platform über den Analytics-Quell-Connector verfügbar. Nur vollständige (nicht virtuelle) Report Suites sind für die Verwendung mit dem Analytics-Quell-Connector verfügbar.


## Customer Journey Analytics-Datenansichten

Weitere Informationen finden Sie unter [Datenansichten – Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de).

Eine Datenansicht:

* Kann auf Customer Journey Analytics-Segmenten basieren.
* Kann auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten auf Basis einer Customer Journey Analytics-Verbindung, die von verschiedenen Unternehmens-Teams verwendet werden können.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzende in Customer Journey Analytics zu steuern und diese Daten zu kuratieren.
* Bietet leistungsstarke, zerstörungsfreie Optionen zum Transformieren und Verbessern von Daten, die über eine Customer Journey Analytics-Verbindung in Customer Journey Analytics eingehen.
* Basiert auf den Customer Journey Analytics-Funktionen für die Verarbeitung zum Zeitpunkt der Berichtserstellung.
* Ermöglicht Benutzern das Erstellen einer benutzerdefinierten Definition für „Sitzung“.
* Wird zur Berichtslaufzeit angewendet, ähnlich wie eine Segmentauswertung. Dies geschieht, _nachdem_ der Quell-Connector (z. B. Adobe Analytics) Daten in einen Datensatz im Adobe Experience Platform Data Lake geschrieben hat und _nachdem_ die Daten über eine Customer Journey Analytics-Verbindung in Customer Journey Analytics aufgenommen wurden.
* Ermöglicht eine unbegrenzte Anzahl von Variablen, allerdings kann die Kuratierung einschränken, welche Variablen für Benutzer verfügbar sind.
* Ermöglicht die benutzerdefinierte Benennung von Containern für Ereignisse, Sitzungen und Personen.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Einschränkungen einer Datenansicht:

* Sie stellt direkt keine Möglichkeit bereit, Report Suites oder andere Datensätze zu kombinieren. Stattdessen werden Datensätze in einer Customer Journey Analytics-Verbindung kombiniert. Die kombinierten Daten aus der Customer Journey Analytics-Verbindung können in allen Datenansichten verwendet werden, die auf dieser Verbindung basieren.

## Adobe Experience Platform-Sandboxes

Weitere Informationen finden Sie unter [Sandboxes – Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Eine Adobe Experience Platform-Sandbox:

* Bietet eine Möglichkeit, eine einzelne Adobe Experience Platform-Instanz in separate virtuelle Umgebungen (Entwicklung, Test, Staging, Produktion usw.) zu unterteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu unterstützen.
* Kann als Container betrachtet werden, der alle Daten und Programme für eine bestimmte Umgebung enthält.

Einschränkungen einer Adobe Experience Platform-Sandbox:

* Sie bietet keine vergleichbaren Funktionen wie Virtual Report Suites, Customer Journey Analytics-Verbindungen oder -Datenansichten.
* Report Suites können damit nicht mit oder ohne andere Datensätze kombiniert werden. Die Datensätze innerhalb einer Sandbox können jedoch innerhalb einer Customer Journey Analytics-Verbindung kombiniert werden.

Beachten Sie Folgendes:

* Daten aus verschiedenen Sandboxes können nicht in Customer Journey Analytics kombiniert werden.
* Der Analytics-Quell-Connector sendet Report Suite-Daten _in_ eine bestimmte Sandbox. Jede Report Suite kann als Quelle für eine einzelne Sandbox konfiguriert werden. Weitere Details finden Sie in der [Dokumentation zum Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de).
