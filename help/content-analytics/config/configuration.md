---
title: Konfigurieren von Inhaltsanalysen
description: Eine Übersicht über die Konfiguration von Inhaltsanalysen
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 20%

---

# Konfigurieren von Inhaltsanalysen

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}


Um die Inhaltsanalyse für Ihr Unternehmen zu konfigurieren, verwenden Sie die Inhaltsanalyse [geführte Konfiguration](guided.md). Der Konfigurationsassistent führt Sie durch alle Schritte, die zum Einrichten der Voraussetzungen für eine automatische Konfiguration von Content Analytics erforderlich sind.

Nach erfolgreicher Implementierung können Sie einige Änderungen mithilfe des Assistenten für geführte Konfigurationen vornehmen. Darüber hinaus [ jedoch möglicherweise ](manual.md)manuelle Änderungen“ erforderlich.

## Voraussetzungen

Stellen Sie vor der Konfiguration von Content Analytics sicher, dass die folgenden Voraussetzungen erfüllt sind:

* Sie haben den Benutzeragenten und die IP-Adresse für den in Content Analytics verwendeten Feature Service auf die Zulassungsliste gesetzt. Die Benutzeragenten-Zeichenfolge ist `AdobeFeaturization/1.0`.
* Sie verfügen über die Rolle eines Customer Journey Analytics-Produktadministrators mit den zusätzlichen Berechtigungen zum Verwalten von Verbindungen und Datenerfassungen. Die erforderlichen Experience Platform-Berechtigungen sind:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Datenerfassung] | Anzeigen von Datenströmen | Schreibgeschützter Zugriff auf Datenströme. |
  | [!UICONTROL Datenerfassung] | Verwalten von Datenströmen | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Datenströmen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Anzeigen von Schemata] | Schreibgeschützter Zugriff auf Schemata und zugehörige Ressourcen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Verwalten von Schemata] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Schemata und zugehörigen Ressourcen. |
  | [!UICONTROL Daten-Management] | [!UICONTROL Anzeigen von Datensätzen] | Schreibgeschützter Zugriff auf Datensätze und Schemata. |
  | [!UICONTROL Daten-Management] | [!UICONTROL Datensätze verwalten] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Datensätzen. Schreibgeschützter Zugriff auf Schemata. |
  | [!UICONTROL Datenaufnahme] | [!UICONTROL Verwalten von Quellen] | Zugriff zum Lesen, Erstellen, Bearbeiten und Deaktivieren von Quellen. |
  | [!UICONTROL Identity Management] | [!UICONTROL Anzeigen von Identitäts-Namensräumen] | Schreibgeschützter Zugriff für Identitäts-Namensräume. |

* Sie haben die folgenden wichtigen Konfigurationsoptionen sorgfältig geprüft:

   * Ihre Website ist für Erlebnis-Reporting geeignet? Ein ordnungsgemäßes Reporting über Erlebnisse ist nur möglich, wenn die folgenden Bedingungen erfüllt sind:
      * Der Site-Inhalt wird nur von URLs gesteuert.
      * Die Seiten auf Ihrer Site sind mit der Seiten-URL reproduzierbar, und Sie wissen, welche optionalen URL-Parameter Erlebnisse fördern.
   * Sie haben ein klares Verständnis dafür, für welche Seiten Sie Inhaltsinteraktionsanalysen und Einblicke erfassen möchten.
   * Sie haben ein klares Verständnis dafür, für welche (Art von) Assets Sie die Inhaltsinteraktionsanalyse und -einblicke erfassen möchten.


>[!MORELIKETHIS]
>* [Geführte Konfiguration](guided.md)
>* [Manuelle Konfiguration](manual.md)
>* [Zugriffskontrolle](/help/technotes/access-control.md)
>


