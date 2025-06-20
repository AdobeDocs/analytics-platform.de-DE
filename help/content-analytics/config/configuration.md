---
title: Konfigurieren von der Inhaltsanalyse
description: Ein Überblick über die Konfiguration von Inhaltsanalysen
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: f149a2bd7f184f4e8f6e67979649e2d9f609d603
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 72%

---

# Konfigurieren von der Inhaltsanalyse

In diesem Artikel wird allgemein beschrieben, wie Sie Content Analytics konfigurieren.

Bevor Sie Content Analytics konfigurieren, müssen Sie sicherstellen[ dass die ](#prerequisites) Voraussetzungen erfüllt sind, dass Sie über die erforderliche [Zugriffskontrolle](#access-control) verfügen und dass Sie die [Einschränkungen](#limitations) kennen.


Allgemeine Schritte

![Konfiguration von Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Verwenden Sie den Assistenten für die [geführte Konfiguration](guided.md) von Content Analytics, der Sie durch alle Schritte führt, die zum Erfüllen der Voraussetzungen für eine Content Analytics-Konfiguration erforderlich sind. Sie können Ihre Konfigurationen jederzeit speichern und zu einem späteren Zeitpunkt dorthin zurückkehren.
1. Sobald Sie mit den Konfigurationswerten zufrieden sind, können Sie die Konfiguration implementieren. Diese Implementierung erstellt alle erforderlichen Artefakte, basierend auf der Konfiguration mit dem Assistenten.
1. Erst wenn Sie die Tags-Eigenschaft [manuell veröffentlichen](manual.md), wird die Content Analytics-Konfiguration tatsächlich bereitgestellt und die Datenerfassung gestartet.

1. Sie können nur einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des Assistenten für [geführte Konfigurationen](guided.md) vornehmen, beispielsweise das Ändern der [Datenansicht](/help/data-views/data-views.md).
1. Mit der [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der zugehörigen Tags-Eigenschaft können Sie weitere Änderungen an einer implementierten Konfiguration in der zugehörigen Tags-Eigenschaft vornehmen.
1. Erst wenn Sie die Tags-Eigenschaft [erneut manuell veröffentlichen](manual.md), wird die geänderte Konfiguration tatsächlich bereitgestellt und basierend auf Ihren Änderungen die Datenerfassung gestartet.


## Voraussetzungen

Stellen Sie vor dem Konfigurieren von Content Analytics sicher, dass die folgenden Voraussetzungen erfüllt sind:

* Sie haben den Benutzeragenten und die IP-Adresse für den in Content Analytics verwendeten Featurisierungs-Service auf die Zulassungsliste gesetzt. Die zu konfigurierende Benutzeragenten-Zeichenfolge lautet: <code>AdobeFeaturization/1.0</code>.
* Wenn Sie den [Web SDK mit JavaScript](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/library){target="_blank"} für die reguläre Verhaltensdatenerfassung implementiert haben, stellen Sie sicher, dass Sie den Standardnamen &quot;<code>&quot; verwenden</code> für die JavaScript-Bibliothek.
* Sie verfügen über die Customer Journey Analytics-Rolle „Produktadministrator“ mit zusätzlichen Berechtigungen zum Verwalten von Verbindungen und Datenansichten.
* Wenn Sie Content Analytics-Erlebnisse erfassen möchten, stellen Sie sicher, dass Sie die [Content Analytics-](manual.md#versioning) basierend auf den Änderungen auf Ihren Web-Seiten einrichten und aktualisieren.
* Sie müssen über [Berechtigungen für die Datenerfassung“ ](https://experienceleague.adobe.com/de/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Berechtigungen für Experience Platform](https://experienceleague.adobe.com/de/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Berechtigungen für die Datenerfassung in Experience Platform](https://experienceleague.adobe.com/de/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Sie haben die folgenden wichtigen Konfigurationsoptionen sorgfältig geprüft:

   * Ihre Site ist für das Reporting zu Erlebnissen geeignet. Ein ordnungsgemäßes Reporting zu Erlebnissen ist nur möglich, wenn die folgenden Bedingungen erfüllt sind:
      * Die Seiten auf der Site müssen unter Verwendung der Seiten-URL reproduzierbar sein.
      * Der Textinhalt, der von einem bestimmten Benutzer angezeigt wird, kann mithilfe der Seiten-URL reproduziert werden und hängt nicht von Cookies oder anderen Personalisierungsmechanismen ab.
   * Sie haben ein klares Verständnis dafür, für welche Seiten Sie Analysen und Erkenntnisse zur Inhaltsinteraktion erfassen möchten.
   * Sie haben ein klares Verständnis dafür, für welche (Art von) Assets Sie Analysen und Erkenntnisse zur Inhaltsinteraktion erfassen möchten.


## Zugriffssteuerung

>[!IMPORTANT]
>
>Es gibt keine Content Analytics-Berechtigung, die Sie konfigurieren können, um den Content Analytics-Zugriff für einzelne Benutzende oder Benutzergruppen zu aktivieren oder zu deaktivieren.
>

Um einzelnen Benutzenden oder einer Benutzergruppe Zugriff auf Content Analytics zu gewähren, müssen Sie der Person oder der Benutzergruppe den Zugriff auf eine oder mehrere [für Content Analytics konfigurierte Datenansichten](guided.md#data-view) gestatten.

Dieser Zugriff setzt Folgendes voraus:

1. Die für Content Analytics aktivierte Datenansicht ist als Teil der Berechtigungen „Datenansicht“ für ein bestimmtes Customer Journey Analytics-Produktprofil enthalten.
1. Bei diesem Customer Journey Analytics-Produktprofil handelt es sich um eines der Produktprofile, die der Person oder der Benutzergruppe zugewiesen sind.

## Einschränkungen

Das für Content Analytics-Ereignisdaten verwendete Schema befindet sich im Systembesitz. Ein systemeigenes Schema kann nicht geändert werden, was Folgendes bedeutet:

* Sie können keine Feldergruppen zur Unterstützung von Funktionen wie Geolokalisierung, Bot-Erkennung oder Gerätesuche einbeziehen.
* Es kann keine spezifische Kennung hinzugefügt werden, um [feldbasiertes Stitching](/help/stitching/fbs.md) zu unterstützen.

>[!MORELIKETHIS]
>
>* [Geführte Konfiguration](guided.md)
>* [Manuelle Konfiguration](manual.md)
>* [Zugriffskontrolle](/help/technotes/access-control.md)
>
