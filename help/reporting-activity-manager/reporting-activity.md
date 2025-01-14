---
title: Anzeigen von Berichtsaktivitäten in Reporting Activity Manager
description: Erfahren Sie, wie Sie Kapazitätsprobleme bei Spitzen während der Berichterstellung mit Reporting Activity Manager diagnostizieren und beheben können.
solution: Customer Journey Analytics
feature: Basics
exl-id: 1f5b2a42-162e-45a7-9fd4-8c1557f48bb8
role: Admin
source-git-commit: a530738bb02888d637e5ff4edaa1aa2535a9034c
workflow-type: tm+mt
source-wordcount: '2043'
ht-degree: 10%

---

# Anzeigen von Berichtsaktivität {#view-reporting-activity}

Mit [!UICONTROL Reporting Activity Manager] können Administratoren Probleme mit der Berichtskapazität während Spitzenzeiten beim Reporting schnell diagnostizieren und beheben.

Weitere Informationen zu Reporting Activity Manager, einschließlich der wichtigsten Vorteile und Berechtigungsanforderungen, finden Sie unter [Reporting Activity Manager - Übersicht](/help/reporting-activity-manager/reporting-activity-overview.md).

## Für alle Verbindungen {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="Verbindungen"
>abstract="Diese Tabelle zeigt die Verbindungen, für die Sie zur Verwaltung der Reporting-Aktivität berechtigt sind. Informationen zu den einzelnen Verbindungen finden Sie in den jeweiligen Spalten der Tabelle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_reportingactivitymanager_connections"
>title="Verbindungen"
>abstract="Diese Tabelle zeigt die Verbindungen, für die Sie zur Verwaltung der Reporting-Aktivität berechtigt sind. Informationen zu den einzelnen Verbindungen finden Sie in den jeweiligen Spalten der Tabelle."

<!-- markdownlint-enable MD034 -->


1. Gehen Sie in Customer Journey Analytics zu **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

   Eine Liste Ihrer aktivierten Basisverbindungen wird angezeigt.

   ![Berichtsaktivität, die die Berichtswarteschlange anzeigt](assets/reporting-activity1.png)

1. Um die Gesamtzahl der Berichtsanfragen für alle Verbindungen in Ihrer Organisation anzuzeigen, erweitern Sie [!UICONTROL **Mehr anzeigen**] um das Diagramm [!UICONTROL **Monatliche Berichtsanfragen**] anzuzeigen.

   Sie können die Anzahl der Berichtsanfragen innerhalb Ihrer Organisation für den aktuellen Monat und den vorherigen Monat anzeigen.

   ![Berichtsaktivität, die die Berichtswarteschlange anzeigt](assets/reporting-activity-monthly.png)

1. (Optional) Sie können die Liste der Verbindungen durchsuchen oder filtern:

   * Verwenden Sie das Suchfeld, um nach einer bestimmten Verbindung zu suchen. Beginnen Sie mit der Eingabe des Verbindungsnamens oder der ID, und die Liste der Verbindungen wird während der Eingabe aktualisiert.

   * Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um die Liste der Filteroptionen zu erweitern. Sie können nach &quot;[!UICONTROL **&quot;**] &quot;[!UICONTROL **&quot;**].

     Um eine Verbindung als Favorit zu markieren, wählen Sie das Sternsymbol links neben dem Verbindungsnamen aus.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Anzeigen von Nutzungsinformationen zu jeder Verbindung. Die in der Tabelle angezeigten Daten stellen die Berichtsaktivität für die Verbindung zum Zeitpunkt des letzten Seitenladevorgangs dar.

   Die folgenden Spalten sind verfügbar:

   | UI-Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Verbindung]** | Die Verbindung, deren Berichtsaktivität Sie überwachen. |
   | **[!UICONTROL Datenansichten]** | Zeigt alle Datenansichten an, die die Verbindung verwenden. Die Konfiguration von Datenansichten kann Berichtsanfragen komplexer machen. |
   | **[!UICONTROL Kapazitätsauslastung]** | Der Prozentsatz der Berichtskapazität der Verbindung, der in Echtzeit verwendet wird. <p>**Hinweis** Bei einer Nutzungskapazität von 100 % sollten Sie nicht unbedingt sofort mit dem Abbrechen von Berichtsanfragen beginnen. Eine 100%ige Nutzungskapazität kann in Ordnung sein, wenn die durchschnittliche Wartezeit angemessen ist. Andererseits könnte eine 100%ige Nutzungskapazität ein Problem darstellen, wenn auch die Anzahl der Anfragen in der Warteschlange zunimmt.</p> |
   | **[!UICONTROL Anforderungen in der Warteschlange]** | Die Anzahl der Anforderungen, die auf die Verarbeitung warten. <!-- ??? --> |
   | **[!UICONTROL Warteschlangenwartezeit]** | Die durchschnittliche Wartezeit, bevor Anforderungen verarbeitet werden. <!-- ???? --> |
   | **[!UICONTROL Status]** | Mögliche Status sind: <ul><li>[!UICONTROL **Aktiv**] (blau): Für die Verbindung wurden in den letzten 2 Stunden Berichte ausgeführt. Die in der Tabelle angezeigten Daten stellen die Berichtskapazität für die Verbindung zum Zeitpunkt des letzten Ladens der Seite dar.</li><li>[!UICONTROL **Inaktiv**] (grau): In den letzten 2 Stunden wurden noch nie Berichte zur Verbindung ausgeführt, sodass keine Daten für die Verbindung angezeigt werden.</li></ul> |

   {style="table-layout:auto"}

## Für eine einzelne Verbindung

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Tools**] > [!UICONTROL **Reporting Activity Manager**].

1. Wählen Sie den verknüpften Titel der Verbindung aus, für die Sie Details anzeigen möchten.

   Aktivitätsdaten des Berichts werden für die von Ihnen ausgewählte Verbindung angezeigt.

1. (Optional) Beim ersten Laden einer Verbindung im Reporting Activity Manager stellen die angezeigten Daten die aktuellen Nutzungsmetriken dar. Um aktualisierte Metriken nach dem ersten Laden anzuzeigen, klicken Sie auf die Schaltfläche [!UICONTROL **Aktualisieren**], um die Seite manuell zu aktualisieren.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Verwenden Sie die verfügbaren Diagramme und Tabellen, um die Berichtsaktivität in der Verbindung zu verstehen.

   * [Diagramme anzeigen](#view-graphs)

   * [Tabelle anzeigen](#view-table)

### Diagramme anzeigen

Die folgenden Diagramme helfen Ihnen, die in der Verbindung stattfindenden Aktivitäten besser zu verstehen.

Wenn keine Diagramme sichtbar sind, wählen Sie die Schaltfläche [!UICONTROL **Diagramme anzeigen**] aus.

#### Auslastungsdiagramm {#utilization}

Das Diagramm Auslastung zeigt die Berichtsauslastung für die ausgewählte Verbindung in den letzten 2 Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um die Zeitpunkte anzuzeigen, an denen der Prozentsatz der Nutzungskapazität für diese Minute am höchsten war.

* **X-axis**: Die Berichtsnutzungskapazität in den letzten 2 Stunden.
* **Y-Achse**: Der Prozentsatz der Reporting-Nutzungskapazität in Minuten.

  ![Auslastungsdiagramm](assets/utilization-graph.png)

#### Diagramm mit unterschiedlichen Benutzern

Das Diagramm Unterschiedliche Benutzer zeigt die Berichtsaktivität für die ausgewählte Verbindung in den letzten 2 Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um die Zeitpunkte anzuzeigen, an denen die maximale Anzahl von Benutzern für diese Minute am höchsten war.

* **X-axis**: Die Berichtsaktivität über den letzten Zeitrahmen von 2 Stunden.
* **Y-Achse**: Die Anzahl der Benutzer, die Berichtsanfragen gestellt haben, pro Minute.

  ![Diagramm „Unterschiedliche Benutzer“](assets/distinct-users-graph.png)

#### Anforderungsdiagramm

Das Diagramm Anfragen zeigt die Anzahl der verarbeiteten Anfragen und der in der Warteschlange befindlichen Anfragen für die ausgewählte Verbindung in den letzten zwei Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um die Zeitpunkte anzuzeigen, an denen die maximale Anzahl von Anfragen für diese Minute am höchsten war.

* **X-axis**: Die Anzahl der verarbeiteten Anfragen und der Anfragen in der Warteschlange innerhalb der letzten 2 Stunden.
* **Y-Achse**: Die Anzahl der verarbeiteten Anfragen (grün) und der in die Warteschlange gestellten Anfragen (violett) pro Minute.

  ![Diagramm „Unterschiedliche Benutzer“](assets/requests-graph.png)

#### Warteschlangengraph

Das Diagramm Warteschlange zeigt die durchschnittliche Wartezeit der Warteschlange (in Sekunden) für Berichtsanfragen für die ausgewählte Verbindung in den letzten 2 Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um die Zeitpunkte anzuzeigen, an denen die maximale durchschnittliche Wartezeit für diese Minute am höchsten war.

* **X-axis**: Die durchschnittliche Wartezeit in der Warteschlange für Berichtsanfragen während der letzten 2 Stunden.
* **Y-Achse**: Die durchschnittliche Wartezeit (in Sekunden).

  ![Diagramm „Unterschiedliche Benutzer“](assets/queueing-graph.png)

### Tabelle anzeigen {#view-table}

Beachten Sie beim Anzeigen der Tabelle Folgendes:

* Sie können Daten anzeigen, indem Sie eine der folgenden Registerkarten oben in der Datentabelle auswählen: [!UICONTROL **Anfrage**], [!UICONTROL **Benutzer**], [!UICONTROL **Projekt**] oder [!UICONTROL **Anwendung**].

* Sie können die Liste der Verbindungen durchsuchen oder filtern:

   * Verwenden Sie das Suchfeld, um nach einer bestimmten Verbindung zu suchen. Beginnen Sie mit der Eingabe des Verbindungsnamens oder der ID, und die Liste der Verbindungen wird während der Eingabe aktualisiert.

   * Wählen Sie das [!UICONTROL **Filter**]-Symbol ![Filtersymbol](assets/filter-icon.png) aus, um die Liste der Filteroptionen zu erweitern. Sie können nach [!UICONTROL **Status**], [!UICONTROL **Komplexität**], [!UICONTROL **Anwendung**], [!UICONTROL **Benutzer**] oder [!UICONTROL **Projekt**] filtern.

   * Sie können auf [!UICONTROL **Diagramme ausblenden**] klicken, um nur die Tabelle anzuzeigen.

![Tabellenregisterkarten](assets/report-activity-tabs.png)

#### Daten nach Anfrage anzeigen

Wenn Sie die Registerkarte [!UICONTROL **Anfrage**] auswählen, sind in der Tabelle die folgenden Spalten verfügbar:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Anfrage-ID**] | Eine eindeutige ID, die zu Fehlerbehebungszwecken verwendet werden kann. Um die ID zu kopieren, wählen Sie die Anfrage aus und wählen Sie dann die Option [!UICONTROL **Anfrage-IDs kopieren**] aus. |
| [!UICONTROL **Laufzeitumgebung**] | Die Dauer der Anfrage. |
| [!UICONTROL **Startzeit**] | Wann die Verarbeitung der Anfrage begann (basierend auf der Ortszeit des Administrators). |
| [!UICONTROL **Wartezeit**] | Die Wartezeit für die Anfrage vor der Verarbeitung. Dieser Wert liegt im Allgemeinen bei „0“, wenn genügend Kapazität vorhanden ist. |
| [!UICONTROL **Programm**] | Die von [!UICONTROL Reporting Activity Manager] unterstützten Programme sind: <ul><li>Analysis Workspace-Benutzeroberfläche</li><li>Geplante Projekte im Workspace</li><li>Report Builder</li><li>Builder-Benutzeroberflächen: Segment, berechnete Metriken, Anmerkungen, Zielgruppen usw.</li><li>API-Aufrufe von der 2.0-API</li><li>Warnhinweise<li>Vollständiger Tabellenexport</li><li>Für alle freigeben - Links</li><li>Geführte Analyse</li><li>Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt</li></li></ul><p>**Hinweis:** Wenn der Wert dieser Spalte [!UICONTROL **Unbekannt**] lautet, bedeutet dies, dass die Anfragemetadaten für den Benutzer nicht verfügbar sind.</p> |
| [!UICONTROL **Benutzende**] | Der Benutzer, der die Anfrage initiiert hat. <p>**Hinweis:** Wenn der Wert dieser Spalte [!UICONTROL **Unbekannt**] lautet, bedeutet dies, dass die Anfragemetadaten für den Benutzer nicht verfügbar sind.</p> |
| [!UICONTROL **Projekt**] | Gespeicherte Workspace-Projektnamen, API-Berichts-IDs usw. (Metadaten können von Programm zu Programm variieren.)<p>**Hinweis:** Wenn der Wert dieser Spalte [!UICONTROL **Unbekannt**] lautet, bedeutet dies, dass das Projekt nicht gespeichert wurde oder dass die Anfragemetadaten für den Benutzer nicht verfügbar sind.</p> |
| [!UICONTROL **Status**] | Statusindikatoren: <ul><li>**Läuft**: Die Anfrage wird derzeit verarbeitet.</li><li>**Ausstehend**: Die Anfrage wartet auf die Verarbeitung.</li></ul> |
| [!UICONTROL **Komplexität**] | Nicht alle Anfragen benötigen die gleiche Verarbeitungszeit. Die Anfragekomplexität kann dabei helfen, einen allgemeinen Eindruck von der für die Verarbeitung der Anfrage benötigten Zeit zu gewinnen. <p>Mögliche Werte:</p> <ul><li>[!UICONTROL **Niedrig**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **Hoch**]</li></ul>Dieser Wert wird durch die Werte in den folgenden Spalten beeinflusst:<ul><li>[!UICONTROL **Monatsgrenzen**]</li><li>[!UICONTROL **Spalten**]</li><li>[!UICONTROL **Segmente**]</li></ul> |
| [!UICONTROL **Monatsgrenzen**] | Die Anzahl der Monate, die in einer Anfrage enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Spalten**] | Die Anzahl der Metriken und Aufschlüsselungen in der Anfrage. Weitere Spalten erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Segmente**] | Die Anzahl der Segmente, die auf die Anfrage angewendet werden. Weitere Segmente erhöhen die Komplexität der Anfrage. |

{style="table-layout:auto"}

#### Daten nach Benutzer anzeigen

Wenn Sie die Registerkarte [!UICONTROL **Benutzer**] auswählen, sind die folgenden Spalten in der Tabelle verfügbar:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Benutzende**] | Der Benutzer, der die Anfrage initiiert hat. Wenn der Wert dieser Spalte &quot;[!UICONTROL **&quot; lautet**] bedeutet dies, dass sich der Benutzer in einer Unternehmensanmeldung befindet, für die Sie keine Administratorrechte haben. |
| [!UICONTROL **Anzahl der Anfragen**] | Die Anzahl der vom Benutzer initiierten Anfragen. |
| [!UICONTROL **Anzahl der Projekte**] | Die Anzahl der dem Benutzer zugeordneten Projekte. <!-- ??? --> |
| [!UICONTROL **Programm**] | Die von [!UICONTROL Reporting Activity Manager] unterstützten Programme sind: <ul><li>Analysis Workspace-Benutzeroberfläche</li><li>Geplante Projekte im Workspace</li><li>Report Builder</li><li>Builder-Benutzeroberflächen: Segment, berechnete Metriken, Anmerkungen, Zielgruppen usw.</li><li>API-Aufrufe von der 2.0-API</li><li>Warnhinweise<li>Vollständiger Tabellenexport</li><li>Für alle freigeben - Links</li><li>Geführte Analyse</li><li>Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt</li></li></ul> |
| [!UICONTROL **Durchschn. Komplexität**] | Die durchschnittliche Komplexität der vom Benutzer initiierten Anfragen. <p>Nicht alle Anfragen benötigen die gleiche Verarbeitungszeit. Die Anfragekomplexität kann dabei helfen, einen allgemeinen Eindruck von der für die Verarbeitung der Anfrage benötigten Zeit zu gewinnen.</p><p>Der Wert in dieser Spalte basiert auf einem Score, der durch die Werte in den folgenden Spalten bestimmt wird:</p><ul><li>[!UICONTROL **Durchschn. Monatsgrenzen**]</li><li>[!UICONTROL **Durchschn. Spalten**]</li><li>[!UICONTROL **Durchschn. Segmente**]</li></ul> |
| [!UICONTROL **Durchschn. Monatsgrenzen**] | Die durchschnittliche Anzahl der Monate, die in den Anfragen enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Spalten**] | Die durchschnittliche Anzahl der Metriken und Aufschlüsselungen in den enthaltenen Anfragen. Weitere Spalten erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Segmente**] | Die durchschnittliche Anzahl der Segmente, die auf die enthaltenen Anfragen angewendet werden. Weitere Segmente erhöhen die Komplexität der Anfrage. |

{style="table-layout:auto"}

#### Daten nach Projekt anzeigen

Wenn Sie die Registerkarte [!UICONTROL **Projekt**] auswählen, sind die folgenden Spalten in der Tabelle verfügbar:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Projekt**] | Das Projekt, in dem die Anfragen initiiert wurden. |
| [!UICONTROL **Anzahl der Anfragen**] | Die Anzahl der mit dem Projekt verknüpften Anfragen. |
| [!UICONTROL **Anzahl der Benutzer**] | Die Anzahl der mit dem Projekt verknüpften Benutzer. <!-- ??? --> |
| [!UICONTROL **Programm**] | Die von [!UICONTROL Reporting Activity Manager] unterstützten Programme sind: <ul><li>Analysis Workspace-Benutzeroberfläche</li><li>Geplante Projekte im Workspace</li><li>Report Builder</li><li>Builder-Benutzeroberflächen: Segment, berechnete Metriken, Anmerkungen, Zielgruppen usw.</li><li>API-Aufrufe von der 2.0-API</li><li>Warnhinweise<li>Vollständiger Tabellenexport</li><li>Für alle freigeben - Links</li><li>Geführte Analyse</li><li>Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt</li></li></ul> |
| [!UICONTROL **Durchschn. Komplexität**] | Die durchschnittliche Komplexität der im Projekt enthaltenen Anfragen. <p>Nicht alle Anfragen benötigen die gleiche Verarbeitungszeit. Die Anfragekomplexität kann dabei helfen, einen allgemeinen Eindruck von der für die Verarbeitung der Anfrage benötigten Zeit zu gewinnen.</p><p>Der Wert in dieser Spalte basiert auf einem Score, der durch die Werte in den folgenden Spalten bestimmt wird:</p><ul><li>[!UICONTROL **Durchschn. Monatsgrenzen**]</li><li>[!UICONTROL **Durchschn. Spalten**]</li><li>[!UICONTROL **Durchschn. Segmente**]</li></ul> |
| [!UICONTROL **Durchschn. Monatsgrenzen**] | Die durchschnittliche Anzahl der Monate, die in den Anfragen enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Spalten**] | Die durchschnittliche Anzahl der Metriken und Aufschlüsselungen in den enthaltenen Anfragen. Weitere Spalten erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Segmente**] | Die durchschnittliche Anzahl der Segmente, die auf die enthaltenen Anfragen angewendet werden. Weitere Segmente erhöhen die Komplexität der Anfrage. |

{style="table-layout:auto"}

#### Daten nach Anwendung anzeigen

Wenn Sie die Registerkarte [!UICONTROL **Anwendung**] auswählen, sind die folgenden Spalten in der Tabelle verfügbar:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Programm**] | Die Anwendung, in der die Anfragen initiiert wurden. |
| [!UICONTROL **Anzahl der Anfragen**] | Die Anzahl der mit der Anwendung verknüpften Anfragen. |
| [!UICONTROL **Anzahl der Benutzer**] | Die Anzahl der mit der Anwendung verknüpften Benutzer. <!--???--> |
| [!UICONTROL **Anzahl der Projekte**] | Die Anzahl der mit der Anwendung verknüpften Projekte. <!--???--> |
| [!UICONTROL **Durchschn. Komplexität**] | Die durchschnittliche Komplexität der mit der Anwendung verbundenen Anfragen. <p>Nicht alle Anfragen benötigen die gleiche Verarbeitungszeit. Die Anfragekomplexität kann dabei helfen, einen allgemeinen Eindruck von der für die Verarbeitung der Anfrage benötigten Zeit zu gewinnen.</p><p>Der Wert in dieser Spalte basiert auf einem Score, der durch die Werte in den folgenden Spalten bestimmt wird:</p>Der Wert in dieser Spalte basiert auf einem Score, der durch die Werte in den folgenden Spalten bestimmt wird:<ul><li>[!UICONTROL **Durchschn. Monatsgrenzen**]</li><li>[!UICONTROL **Durchschn. Spalten**]</li><li>[!UICONTROL **Durchschn. Segmente**]</li></ul> |
| [!UICONTROL **Durchschn. Monatsgrenzen**] | Die durchschnittliche Anzahl der Monate, die in den Anfragen enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Spalten**] | Die durchschnittliche Anzahl der Metriken und Aufschlüsselungen in den enthaltenen Anfragen. Weitere Spalten erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Segmente**] | Die durchschnittliche Anzahl der Segmente, die auf die enthaltenen Anfragen angewendet werden. Weitere Segmente erhöhen die Komplexität der Anfrage. |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
