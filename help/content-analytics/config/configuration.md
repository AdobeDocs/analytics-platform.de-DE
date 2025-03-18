---
title: Konfigurieren von Inhaltsanalysen
description: Eine Übersicht über die Konfiguration von Inhaltsanalysen
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 11%

---

# Konfigurieren von Inhaltsanalysen

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}

Die Konfiguration von Content Analytics besteht aus den folgenden Schritten:

![Konfiguration der Inhaltsanalyse](../assets/aca-configuration.svg)

1. Verwenden Sie den Content Analytics [Konfigurationsassistenten](guided.md) um Sie durch alle Schritte zu führen, die zum Einrichten der Voraussetzungen für eine Konfiguration von Content Analytics erforderlich sind. Sie können Ihre Konfigurationen speichern und später zurückkehren.
1. Sobald Sie mit den Konfigurationswerten vertraut sind, können Sie die Konfiguration implementieren. Diese Implementierung erstellt alle erforderlichen Artefakte, basierend auf den Konfigurationen im Assistenten. Die folgenden Artefakte werden erstellt, aktualisiert oder ausgewählt:
   * Customer Journey Analytics
      * Eine [Datenansicht](/help/data-views/data-views.md) ist ausgewählt.
      * Eine [Verbindung](/help/connections/overview.md) wird ausgewählt und automatisch aus der ausgewählten Datenansicht abgeleitet.
   * Experience Platform
      * Die Sandbox wird ausgewählt und automatisch von der Verbindung abgeleitet. Die erforderlichen Workflows und Services werden in der Sandbox aktiviert.
      * Content Analytics-Schemata werden in der Sandbox ausgewählt. Falls nicht verfügbar, werden die erforderlichen Schemata erstellt.
      * Content Analytics-Datensätze sind in der Sandbox ausgewählt. Wenn nicht verfügbar, werden die erforderlichen Datensätze erstellt.
   * Datenerfassung
      * Es wird ein Datenstrom erstellt und ein Experience Platform-Service im Datenstrom konfiguriert, um Daten an den Content Analytics-Erlebnisereignis-Datensatz zu streamen.
      * Eine Tags-Eigenschaft wird erstellt, wobei die Adobe Content Analytics-Erweiterung für die richtige Sandbox, den richtigen Datenstrom und andere Konfigurationsoptionen im Konfigurationsassistenten konfiguriert wird.
1. Nur wenn Sie [die Tags](manual.md)Eigenschaft manuell veröffentlichen, wird Ihre Content Analytics-Konfiguration effektiv bereitgestellt und aktiviert.

1. Sie können nur einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des Assistenten [Geführte Konfiguration](guided.md) vornehmen. Ändern Sie beispielsweise die [Datenansicht](/help/data-views/data-views.md).
1. Sie können weitere Änderungen an einer implementierten Konfiguration vornehmen. Verwenden Sie die Erweiterung [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der zugehörigen Tags-Eigenschaft.
1. Nur wenn [ die Tags](manual.md)Eigenschaft manuell erneut veröffentlichen, werden die Konfigurationsänderungen aus Schritt 4 und 5 effektiv bereitgestellt und aktiviert.


## Voraussetzungen

Stellen Sie vor dem Konfigurieren von Content Analytics sicher, dass die folgenden Voraussetzungen erfüllt sind:

* Sie haben den Benutzeragenten und die IP-Adresse für den in Content Analytics verwendeten Feature Service auf die Zulassungsliste gesetzt. Die zu konfigurierende Benutzeragenten-Zeichenfolge lautet: <code>AdobeFeatureIzation/1.0</code>.
* Sie verfügen über die Rolle eines Customer Journey Analytics-Produktadministrators mit den zusätzlichen Berechtigungen zum Verwalten von Verbindungen und Datenansichten.
* Sie verfügen über die erforderlichen Experience Platform-Berechtigungen:

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

   * Ihre Site ist für das Reporting zu Erlebnissen geeignet. Ein ordnungsgemäßes Reporting zu Erlebnissen ist nur möglich, wenn die folgenden Bedingungen erfüllt sind:
      * Sie können auf den Site-Inhalt nur über öffentlich zugängliche URLs zugreifen. Für den Zugriff auf die Website sind keine personalisierten Token, Cookies oder andere Mechanismen erforderlich, die nicht über die URL verfügbar sind.
      * Die Seiten auf Ihrer Site sind mit der Seiten-URL reproduzierbar, und Sie wissen, welche optionalen URL-Parameter Erlebnisse fördern.
   * Sie haben ein klares Verständnis dafür, für welche Seiten Sie Inhaltsinteraktionsanalysen und Einblicke erfassen möchten.
   * Sie haben ein klares Verständnis dafür, für welche (Art von) Assets Sie die Inhaltsinteraktionsanalyse und -einblicke erfassen möchten.


## Zugriffssteuerung

>[!IMPORTANT]
>
>Es gibt keine Content Analytics-Berechtigung, die Sie konfigurieren können, um den Content Analytics-Zugriff für einzelne Benutzende oder Benutzergruppen zu aktivieren oder zu deaktivieren.
>

Um einem Benutzer oder einer Benutzergruppe Zugriff auf Content Analytics zu gewähren, müssen Sie dem Benutzer oder der Benutzergruppe Zugriff auf eine oder mehrere [Datenansichten) gewähren, die für Content Analytics konfiguriert ](guided.md#data-view).

Dieser Zugriff beinhaltet:

1. Die für Content Analytics aktivierte Datenansicht ist als Teil der Datenansichtsberechtigungen für ein bestimmtes Customer Journey Analytics-Produktprofil enthalten.
1. Dieses spezifische Customer Journey Analytics-Produktprofil ist eines der Produktprofile, die dem Benutzer oder der Benutzergruppe zugewiesen sind.

>[!MORELIKETHIS]
>
>* [Geführte Konfiguration](guided.md)
>* [Manuelle Konfiguration](manual.md)
>* [Zugriffskontrolle](/help/technotes/access-control.md)
>
