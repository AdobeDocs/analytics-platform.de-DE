---
title: Konfigurieren von Inhaltsanalysen
description: Eine Übersicht über die Konfiguration von Inhaltsanalysen
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 13%

---

# Konfigurieren von Inhaltsanalysen

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}

Die Konfiguration von Content Analytics besteht aus den folgenden Schritten:

![Konfiguration der Inhaltsanalyse](../assets/aca-configuration.svg)

1. Verwenden Sie den Inhaltsanalyseassistenten [Geführte Konfiguration](guided.md), um Sie durch alle Schritte zu führen, die zum Einrichten der Voraussetzungen für eine Konfiguration von Inhaltsanalysen erforderlich sind. Sie können Ihre Konfigurationen speichern und später zurückkehren.
1. Sobald Sie mit den Konfigurationswerten vertraut sind, können Sie die Konfiguration implementieren. Diese Implementierung erstellt alle erforderlichen Artefakte basierend auf den Konfigurationen im Assistenten. Die folgenden Artefakte werden erstellt, aktualisiert oder ausgewählt:
   * Benutzerdefinierte Journey-Analyse
      * Eine [Datenansicht](/help/data-views/data-views.md) ist ausgewählt.
      * Eine [Verbindung](/help/connections/overview.md) wird ausgewählt und automatisch aus der ausgewählten Datenansicht abgeleitet.
   * Experience Platform
      * Die Sandbox wird ausgewählt und automatisch von der Verbindung abgeleitet. Die erforderlichen Workflows und Services werden in der Sandbox aktiviert.
      * Inhaltsanalyseschemata werden in der Sandbox ausgewählt. Falls nicht verfügbar, werden die erforderlichen Schemata erstellt.
      * In der Sandbox ausgewählte Content Analytics-Datensätze. Wenn nicht verfügbar, werden die erforderlichen Datensätze erstellt.
   * Datenerfassung
      * Es wird ein Datenstrom erstellt und ein Experience Platform-Service im Datenstrom konfiguriert, um Daten an den Content Analytics-Erlebnisereignis-Datensatz zu streamen.
      * Eine Tag-Eigenschaft wird erstellt, wobei die Adobe Content Analytics-Erweiterung für die richtige Sandbox, den richtigen Datenstrom und andere Konfigurationsoptionen im Konfigurationsassistenten konfiguriert ist.
1. Nur wenn Sie [ Tag](manual.md)Eigenschaft manuell veröffentlichen, wird Content Analytics effektiv bereitgestellt und aktiviert.

1. Sie können nur einige begrenzte Änderungen an einer implementierten Konfiguration mithilfe des Assistenten [Geführte Konfiguration](guided.md) vornehmen. Ändern Sie beispielsweise die [Datenansicht](/help/data-views/data-views.md).
1. Sie können weitere Änderungen an einer implementierten Konfiguration über die [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der zugehörigen Tag-Eigenschaft vornehmen.
1. Nur wenn Sie [ Tag-Eigenschaft ](manual.md)manuell erneut veröffentlichen), werden die Konfigurationsänderungen aus Schritt 4 und 5 effektiv bereitgestellt und aktiviert.


Stellen Sie vor der Konfiguration von Content Analytics sicher, dass die folgenden Voraussetzungen erfüllt sind:


>[!PREREQUISITES]
>
>* Sie haben den Benutzeragenten und die IP-Adresse für den in Content Analytics verwendeten Feature Service auf die Zulassungsliste gesetzt. Die Benutzeragenten-Zeichenfolge ist `AdobeFeaturization/1.0`.
>* Sie verfügen über die Rolle eines Customer Journey Analytics-Produktadministrators mit den zusätzlichen Berechtigungen zum Verwalten von Verbindungen und Datenerfassungen. Die erforderlichen Experience Platform-Berechtigungen sind:
>  
>   | Kategorie | Berechtigung | Beschreibung |
>   |---|---|---|
>   | [!UICONTROL Datenerfassung] | Anzeigen von Datenströmen | Schreibgeschützter Zugriff auf Datenströme. |
>   | [!UICONTROL Datenerfassung] | Verwalten von Datenströmen | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Datenströmen. |
>   | [!UICONTROL Datenmodellierung] | [!UICONTROL Anzeigen von Schemata] | Schreibgeschützter Zugriff auf Schemata und zugehörige Ressourcen. |
>   | [!UICONTROL Datenmodellierung] | [!UICONTROL Verwalten von Schemata] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Schemata und zugehörigen Ressourcen. |
>   | [!UICONTROL Daten-Management] | [!UICONTROL Anzeigen von Datensätzen] | Schreibgeschützter Zugriff auf Datensätze und Schemata. |
>   | [!UICONTROL Daten-Management] | [!UICONTROL Datensätze verwalten] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Datensätzen. Schreibgeschützter Zugriff auf Schemata. |
>   | [!UICONTROL Datenaufnahme] | [!UICONTROL Verwalten von Quellen] | Zugriff zum Lesen, Erstellen, Bearbeiten und Deaktivieren von Quellen. |
>   | [!UICONTROL Identity Management] | [!UICONTROL Anzeigen von Identitäts-Namensräumen] | Schreibgeschützter Zugriff für Identitäts-Namensräume. |
>
>* Sie haben die folgenden wichtigen Konfigurationsoptionen sorgfältig geprüft:
>
>   * Ihre Website ist für Erlebnis-Reporting geeignet? Ein ordnungsgemäßes Reporting über Erlebnisse ist nur möglich, wenn die folgenden Bedingungen erfüllt sind:
>   * Der Site-Inhalt wird nur von URLs gesteuert.
>   * Die Seiten auf Ihrer Site sind mit der Seiten-URL reproduzierbar, und Sie wissen, welche optionalen URL-Parameter Erlebnisse fördern.
>* Sie haben ein klares Verständnis dafür, für welche Seiten Sie Inhaltsinteraktionsanalysen und Einblicke erfassen möchten.
>* Sie haben ein klares Verständnis dafür, für welche (Art von) Assets Sie die Inhaltsinteraktionsanalyse und -einblicke erfassen möchten.
>


>[!MORELIKETHIS]
>
>* [Geführte Konfiguration](guided.md)
>* [Manuelle Konfiguration](manual.md)
>* [Zugriffskontrolle](/help/technotes/access-control.md)
>


