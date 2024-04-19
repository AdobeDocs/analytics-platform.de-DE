---
title: Berichtsaktivität im Reporting Activity Manager anzeigen
description: Erfahren Sie, wie Sie Kapazitätsprobleme bei Spitzen während der Berichterstellung mit Reporting Activity Manager diagnostizieren und beheben können.
solution: Customer Journey Analytics
feature: Basics
exl-id: 1f5b2a42-162e-45a7-9fd4-8c1557f48bb8
role: Admin
source-git-commit: cbff0bc58150373df041f9e1594feee0b5bcc2ce
workflow-type: tm+mt
source-wordcount: '2007'
ht-degree: 7%

---

# Berichtsaktivität im Reporting Activity Manager anzeigen

Die [!UICONTROL Reporting Activity Manager] ermöglicht es Administratoren, während Spitzenzeiten der Berichterstellung schnell Probleme mit der Berichtskapazität zu diagnostizieren und zu beheben.

Weitere Informationen zum Reporting Activity Manager, einschließlich der wichtigsten Vorteile und Berechtigungsanforderungen, finden Sie unter [Übersicht über die Berichterstellung in Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md).

## Berichtsaktivität für alle Verbindungen anzeigen {#view-all-report-suites}

1. Gehen Sie unter Customer Journey Analytics zu **[!UICONTROL Instrumente]** > **[!UICONTROL Reporting Activity Manager]**.

   Eine Liste Ihrer aktivierten Basisverbindungen wird angezeigt.

   ![Berichtsaktivität mit Anzeige der Berichtswarteschlange](assets/reporting-activity1.png)

1. Um die Gesamtzahl der Berichtsanfragen für alle Verbindungen in Ihrem Unternehmen anzuzeigen, erweitern Sie [!UICONTROL **Mehr anzeigen**] , um die [!UICONTROL **Monatliche Berichtsanforderungen**] Diagramm.

   Sie können die Anzahl der Berichtsanfragen in Ihrer Organisation für den aktuellen Monat und den Vormonat anzeigen.

   ![Berichtsaktivität mit Anzeige der Berichtswarteschlange](assets/reporting-activity-monthly.png)

1. (Optional) Sie können die Liste der Verbindungen durchsuchen oder filtern:

   * Verwenden Sie das Suchfeld, um nach einer bestimmten Verbindung zu suchen. Beginnen Sie mit der Eingabe des Verbindungsnamens oder der ID und die Liste der Verbindungen wird bei der Eingabe aktualisiert.

   * Wählen Sie die [!UICONTROL **Filter**] icon ![Filtersymbol](assets/filter-icon.png) um die Liste der Filteroptionen zu erweitern. Sie können nach [!UICONTROL **Favoriten**] oder [!UICONTROL **Status**].

     Um eine Verbindung als Favoriten zu markieren, wählen Sie das Sternsymbol links neben dem Verbindungsnamen aus.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Zeigen Sie Nutzungsinformationen zu den einzelnen Verbindungen an. Die in der Tabelle angezeigten Daten stellen die Berichtsaktivität für die Verbindung zum Zeitpunkt des letzten Ladevorgangs der Seite dar.

   Die folgenden Spalten sind verfügbar:

   | UI-Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Verbindung]** | Die Verbindung, deren Berichtsaktivität Sie überwachen. |
   | **[!UICONTROL Datenansichten]** | Zeigt alle Datenansichten an, die die Verbindung verwenden. Die Datenansichtskonfiguration kann Berichtsanforderungen komplexer machen. |
   | **[!UICONTROL Kapazitätsauslastung]** | Der Prozentsatz der verwendeten Berichtskapazität der Verbindung in Echtzeit. <p>**Hinweis** Eine Nutzungskapazität von 100 % bedeutet nicht unbedingt, dass Sie sofort mit dem Abbrechen von Berichtsanfragen beginnen sollten. 100 % der Nutzkapazität können gesund sein, wenn die durchschnittliche Wartezeit vernünftig ist. Andererseits könnte die Nutzungskapazität von 100 % auf ein Problem hindeuten, wenn auch die Anzahl der Anforderungen in der Warteschlange wächst.</p> |
   | **[!UICONTROL Warteschlangen]** | Die Anzahl der zu verarbeitenden Anforderungen. <!-- ??? --> |
   | **[!UICONTROL Wartezeit der Warteschlange]** | Die durchschnittliche Wartezeit, bevor die Verarbeitung von Anforderungen beginnt. <!-- ???? --> |
   | **[!UICONTROL Status]** | Folgende Status sind möglich: <ul><li>[!UICONTROL **Aktiv**] (blau): In den letzten 2 Stunden wurden Berichte zur Verbindung ausgeführt. Die in der Tabelle angezeigten Daten stellen die Berichtskapazität für die Verbindung zum Zeitpunkt des letzten Ladevorgangs der Seite dar.</li><li>[!UICONTROL **Inaaktiv**] (grau): In den letzten 2 Stunden wurden für die Verbindung keine Berichte ausgeführt, sodass keine Daten für die Verbindung angezeigt werden.</li></ul> |

   {style="table-layout:auto"}

## Berichtsaktivität für eine einzelne Verbindung anzeigen

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Instrumente**] > [!UICONTROL **Reporting Activity Manager**].

1. Wählen Sie den verknüpften Titel der Verbindung aus, für die Sie Details anzeigen möchten.

   Berichtsaktivitätsdaten werden für die ausgewählte Verbindung angezeigt.

1. (Optional) Wenn eine Verbindung zum ersten Mal im Reporting Activity Manager geladen wird, stellen die angezeigten Daten die aktuellen Nutzungsmetriken dar. Um aktualisierte Metriken nach dem ersten Laden anzuzeigen, wählen Sie die [!UICONTROL **Aktualisieren**] -Schaltfläche, um die Seite manuell zu aktualisieren.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Verwenden Sie die verfügbaren Diagramme und Tabellen, um die Berichtsaktivität in der Verbindung zu verstehen.

   * [Diagramme anzeigen](#view-graphs)

   * [Tabelle anzeigen](#view-table)

### Diagramme anzeigen

Die folgenden Diagramme helfen Ihnen dabei, die in der Verbindung stattfindenden Aktivitäten besser zu verstehen.

Wenn keine Diagramme sichtbar sind, wählen Sie die [!UICONTROL **Diagramme anzeigen**] Schaltfläche.

#### Auslastungsdiagramm {#utilization}

Das Nutzungsdiagramm zeigt die Nutzung der Berichte für die ausgewählte Verbindung über die letzten 2 Stunden.

Bewegen Sie den Mauszeiger über das Diagramm, um Zeitpunkte anzuzeigen, an denen der Prozentsatz der Nutzungskapazität für diese Minute am höchsten war.

* **X-Achse**: Die Berichtsverwendungskapazität der letzten 2 Stunden.
* **Y-Achse**: Der Prozentsatz der Berichtsverwendungskapazität nach Minuten.

  ![Nutzungsdiagramm](assets/utilization-graph.png)

#### Diagramm &quot;Unique Users&quot;

Das Diagramm Unique Users zeigt die Berichtsaktivität für die ausgewählte Verbindung über die letzten 2 Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um die Zeitpunkte anzuzeigen, an denen die maximale Anzahl von Benutzern für diese Minute lag.

* **X-Achse**: Die Berichterstellungsaktivität über den letzten 2-Stunden-Zeitraum.
* **Y-Achse**: Die Anzahl der Benutzer, die nach Minuten Berichterstellungsanfragen gestellt haben.

  ![Diagramm &quot;Unique Users&quot;](assets/distinct-users-graph.png)

#### Anforderungsdiagramm

Das Anforderungsdiagramm zeigt die Anzahl der verarbeiteten und in die Warteschlange gestellten Anforderungen für die ausgewählte Verbindung in den letzten 2 Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um die Zeitpunkte anzuzeigen, an denen die maximale Anzahl von Anforderungen für diese Minute am höchsten war.

* **X-Achse**: Die Anzahl der verarbeiteten und in die Warteschlange gestellten Anforderungen im letzten 2-Stunden-Zeitraum.
* **Y-Achse**: Die Anzahl der verarbeiteten Anforderungen (grün) und Anforderungen in der Warteschlange (violett) nach Minuten.

  ![Diagramm &quot;Unique Users&quot;](assets/requests-graph.png)

#### Einreihungsdiagramm

Das Queuing-Diagramm zeigt die durchschnittliche Wartezeit der Warteschlange (in Sekunden) für Reporting-Anforderungen für die ausgewählte Verbindung über die letzten 2 Stunden an.

Bewegen Sie den Mauszeiger über das Diagramm, um Zeitpunkte anzuzeigen, an denen die maximale durchschnittliche Wartezeit für diese Minute am höchsten war.

* **X-Achse**: Die durchschnittliche Wartezeit in der Warteschlange für Berichterstellungsanfragen während des letzten 2-Stunden-Zeitraums.
* **Y-Achse**: Die durchschnittliche Wartezeit (in Sekunden).

  ![Diagramm &quot;Unique Users&quot;](assets/queueing-graph.png)

### Tabelle anzeigen {#view-table}

Beachten Sie beim Anzeigen der Tabelle Folgendes:

* Sie können die Anzeige der Daten auf eine der folgenden Registerkarten oben in der Datentabelle einstellen: [!UICONTROL **Anfrage**], [!UICONTROL **Benutzer**], [!UICONTROL **Projekt**] oder [!UICONTROL **Anwendung**].

* Sie können die Liste der Verbindungen durchsuchen oder filtern:

   * Verwenden Sie das Suchfeld, um nach einer bestimmten Verbindung zu suchen. Beginnen Sie mit der Eingabe des Verbindungsnamens oder der ID und die Liste der Verbindungen wird bei der Eingabe aktualisiert.

   * Wählen Sie die [!UICONTROL **Filter**] icon ![Filtersymbol](assets/filter-icon.png) um die Liste der Filteroptionen zu erweitern. Sie können nach [!UICONTROL **Status**], [!UICONTROL **Komplexität**], [!UICONTROL **Anwendung**], [!UICONTROL **Benutzer**] oder [!UICONTROL **Projekt**].

   * Sie können [!UICONTROL **Ausblenden von Diagrammen**] , um nur die Tabelle anzuzeigen.

![Tabellenregisterkarten](assets/report-activity-tabs.png)

#### Daten nach Anforderung anzeigen

Wenn Sie die [!UICONTROL **Anfrage**] -Tab, stehen in der Tabelle die folgenden Spalten zur Verfügung:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Antrags-ID**] | Eine eindeutige ID, die zur Fehlerbehebung verwendet werden kann. Um die ID zu kopieren, wählen Sie die Anforderung und dann die Option aus. [!UICONTROL **Anforderungs-IDs kopieren**]. |
| [!UICONTROL **Zeitablauf**] | Dauer der Ausführung der Anfrage. |
| [!UICONTROL **Startzeit**] | Der Zeitpunkt, zu dem die Anfrage verarbeitet wurde (basierend auf der Ortszeit des Administrators). |
| [!UICONTROL **Wartezeit**] | Wie lange die Anfrage vor der Verarbeitung gewartet hat. Dieser Wert liegt im Allgemeinen bei &quot;0&quot;, wenn ausreichend Kapazität vorhanden ist. |
| [!UICONTROL **Programm**] | Die von [!UICONTROL Reporting Activity Manager] unterstützten Programme sind: <ul><li>Analysis Workspace-Benutzeroberfläche</li><li>Geplante Projekte im Workspace</li><li>Report Builder</li><li>Builder-Benutzeroberfläche: Segment, Berechnete Metriken, Anmerkungen, Zielgruppen usw.</li><li>API-Aufrufe von der 2.0-API</li><li>Intelligente Warnhinweise<li>Vollständiger Tabellenexport</li><li>Für alle Links freigeben</li><li>Geführte Analyse</li><li>Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt</li></li></ul><p>**Hinweis:** Wenn der Wert dieser Spalte [!UICONTROL **unbekannt**] bedeutet dies, dass die Metadaten der Anfrage für den Benutzer nicht verfügbar sind.</p> |
| [!UICONTROL **Benutzer**] | Der Benutzer, der die Anfrage initiiert hat. <p>**Hinweis:** Wenn der Wert dieser Spalte [!UICONTROL **unbekannt**] bedeutet dies, dass die Metadaten der Anfrage für den Benutzer nicht verfügbar sind.</p> |
| [!UICONTROL **Projekt**] | Workspace-Projektnamen, API-Bericht-IDs usw. wurden gespeichert. (Metadaten können von Programm zu Programm variieren.)<p>**Hinweis:** Wenn der Wert dieser Spalte [!UICONTROL **unbekannt**] bedeutet dies, dass das Projekt nicht gespeichert wurde oder dass die Metadaten der Anfrage für den Benutzer nicht verfügbar sind.</p> |
| [!UICONTROL **Status**] | Statusindikatoren: <ul><li>**Läuft**: Die Anfrage wird derzeit verarbeitet.</li><li>**Ausstehend**: Die Anfrage wartet auf die Verarbeitung.</li></ul> |
| [!UICONTROL **Komplexität**] | Nicht alle Anforderungen benötigen dieselbe Verarbeitungszeit. Die Anforderungskomplexität kann dabei helfen, eine allgemeine Vorstellung davon zu erhalten, wie viel Zeit für die Verarbeitung der Anfrage erforderlich ist. <p>Mögliche Werte:</p> <ul><li>[!UICONTROL **Niedrig**]</li><li>[!UICONTROL **Mittel**]</li><li>[!UICONTROL **Hoch**]</li></ul>Dieser Wert wird durch die Werte in den folgenden Spalten beeinflusst:<ul><li>[!UICONTROL **Monatsgrenzen**]</li><li>[!UICONTROL **Spalten**]</li><li>[!UICONTROL **Segmente**]</li></ul> |
| [!UICONTROL **Monatsgrenzen**] | Die Anzahl der Monate, die in einer Anfrage enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Spalten**] | Die Anzahl der Metriken und Aufschlüsselungen in der Anforderung. Mehr Spalten erhöhen die Komplexität der Anforderung. |
| [!UICONTROL **Segmente**] | Die Anzahl der Segmente, die auf die Anforderung angewendet werden. Weitere Segmente erhöhen die Komplexität der Anforderung. |

{style="table-layout:auto"}

#### Daten nach Benutzer anzeigen

Wenn Sie die [!UICONTROL **Benutzer**] -Tab, stehen in der Tabelle die folgenden Spalten zur Verfügung:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Benutzer**] | Der Benutzer, der die Anfrage initiiert hat. Wenn der Wert dieser Spalte [!UICONTROL **Nicht erkannt**], bedeutet dies, dass sich der Benutzer in einem Anmeldeunternehmen befindet, für das Sie keine Administratorberechtigungen haben. |
| [!UICONTROL **Anzahl der Anfragen**] | Die Anzahl der vom Benutzer initiierten Anfragen. |
| [!UICONTROL **Anzahl der Projekte**] | Die Anzahl der mit dem Benutzer verknüpften Projekte. <!-- ??? --> |
| [!UICONTROL **Programm**] | Die von [!UICONTROL Reporting Activity Manager] unterstützten Programme sind: <ul><li>Analysis Workspace-Benutzeroberfläche</li><li>Geplante Projekte im Workspace</li><li>Report Builder</li><li>Builder-Benutzeroberfläche: Segment, Berechnete Metriken, Anmerkungen, Zielgruppen usw.</li><li>API-Aufrufe von der 2.0-API</li><li>Intelligente Warnhinweise<li>Vollständiger Tabellenexport</li><li>Für alle Links freigeben</li><li>Geführte Analyse</li><li>Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt</li></li></ul> |
| [!UICONTROL **Durchschn. Komplexität**] | Die durchschnittliche Komplexität von Anforderungen, die vom Benutzer initiiert wurden. <p>Nicht alle Anforderungen benötigen dieselbe Verarbeitungszeit. Die Anforderungskomplexität kann dabei helfen, eine allgemeine Vorstellung davon zu erhalten, wie viel Zeit für die Verarbeitung der Anfrage erforderlich ist.</p><p>Der Wert in dieser Spalte basiert auf einem Wert, der durch die Werte in den folgenden Spalten bestimmt wird:</p><ul><li>[!UICONTROL **Durchschnittliche Monatsgrenzen**]</li><li>[!UICONTROL **Durchschn. Spalten**]</li><li>[!UICONTROL **Durchschn. Segmente**]</li></ul> |
| [!UICONTROL **Durchschnittliche Monatsgrenzen**] | Die durchschnittliche Anzahl der Monate, die in den Anforderungen enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Spalten**] | Die durchschnittliche Anzahl von Metriken und Aufschlüsselungen in den enthaltenen Anforderungen. Mehr Spalten erhöhen die Komplexität der Anforderung. |
| [!UICONTROL **Durchschn. Segmente**] | Die durchschnittliche Anzahl von Segmenten, die auf die enthaltenen Anforderungen angewendet werden. Weitere Segmente erhöhen die Komplexität der Anforderung. |

{style="table-layout:auto"}

#### Daten nach Projekt anzeigen

Wenn Sie die [!UICONTROL **Projekt**] -Tab, stehen in der Tabelle die folgenden Spalten zur Verfügung:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Projekt**] | Das Projekt, bei dem die Anfragen initiiert wurden. |
| [!UICONTROL **Anzahl der Anfragen**] | Die Anzahl der mit dem Projekt verknüpften Anforderungen. |
| [!UICONTROL **Anzahl der Benutzer**] | Die Anzahl der mit dem Projekt verknüpften Benutzer. <!-- ??? --> |
| [!UICONTROL **Programm**] | Die von [!UICONTROL Reporting Activity Manager] unterstützten Programme sind: <ul><li>Analysis Workspace-Benutzeroberfläche</li><li>Geplante Projekte im Workspace</li><li>Report Builder</li><li>Builder-Benutzeroberfläche: Segment, Berechnete Metriken, Anmerkungen, Zielgruppen usw.</li><li>API-Aufrufe von der 2.0-API</li><li>Intelligente Warnhinweise<li>Vollständiger Tabellenexport</li><li>Für alle Links freigeben</li><li>Geführte Analyse</li><li>Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt</li></li></ul> |
| [!UICONTROL **Durchschn. Komplexität**] | Die durchschnittliche Komplexität der Anforderungen, die im Projekt enthalten sind. <p>Nicht alle Anforderungen benötigen dieselbe Verarbeitungszeit. Die Anforderungskomplexität kann dabei helfen, eine allgemeine Vorstellung davon zu erhalten, wie viel Zeit für die Verarbeitung der Anfrage erforderlich ist.</p><p>Der Wert in dieser Spalte basiert auf einem Wert, der durch die Werte in den folgenden Spalten bestimmt wird:</p><ul><li>[!UICONTROL **Durchschnittliche Monatsgrenzen**]</li><li>[!UICONTROL **Durchschn. Spalten**]</li><li>[!UICONTROL **Durchschn. Segmente**]</li></ul> |
| [!UICONTROL **Durchschnittliche Monatsgrenzen**] | Die durchschnittliche Anzahl der Monate, die in den Anforderungen enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Spalten**] | Die durchschnittliche Anzahl von Metriken und Aufschlüsselungen in den enthaltenen Anforderungen. Mehr Spalten erhöhen die Komplexität der Anforderung. |
| [!UICONTROL **Durchschn. Segmente**] | Die durchschnittliche Anzahl von Segmenten, die auf die enthaltenen Anforderungen angewendet werden. Weitere Segmente erhöhen die Komplexität der Anforderung. |

{style="table-layout:auto"}

#### Daten nach Anwendung anzeigen

Wenn Sie die [!UICONTROL **Anwendung**] -Tab, stehen in der Tabelle die folgenden Spalten zur Verfügung:

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL **Programm**] | Die Anwendung, in der die Anfragen initiiert wurden. |
| [!UICONTROL **Anzahl der Anfragen**] | Die Anzahl der mit der Anwendung verknüpften Anforderungen. |
| [!UICONTROL **Anzahl der Benutzer**] | Die Anzahl der mit der Anwendung verknüpften Benutzer. <!--???--> |
| [!UICONTROL **Anzahl der Projekte**] | Die Anzahl der mit der Anwendung verknüpften Projekte. <!--???--> |
| [!UICONTROL **Durchschn. Komplexität**] | Die durchschnittliche Komplexität der mit der Anwendung verknüpften Anforderungen. <p>Nicht alle Anforderungen benötigen dieselbe Verarbeitungszeit. Die Anforderungskomplexität kann dabei helfen, eine allgemeine Vorstellung davon zu erhalten, wie viel Zeit für die Verarbeitung der Anfrage erforderlich ist.</p><p>Der Wert in dieser Spalte basiert auf einem Wert, der durch die Werte in den folgenden Spalten bestimmt wird:</p>Der Wert in dieser Spalte basiert auf einem Wert, der durch die Werte in den folgenden Spalten bestimmt wird:<ul><li>[!UICONTROL **Durchschnittliche Monatsgrenzen**]</li><li>[!UICONTROL **Durchschn. Spalten**]</li><li>[!UICONTROL **Durchschn. Segmente**]</li></ul> |
| [!UICONTROL **Durchschnittliche Monatsgrenzen**] | Die durchschnittliche Anzahl der Monate, die in den Anforderungen enthalten sind. Mehr Monatsgrenzen erhöhen die Komplexität der Anfrage. |
| [!UICONTROL **Durchschn. Spalten**] | Die durchschnittliche Anzahl von Metriken und Aufschlüsselungen in den enthaltenen Anforderungen. Mehr Spalten erhöhen die Komplexität der Anforderung. |
| [!UICONTROL **Durchschn. Segmente**] | Die durchschnittliche Anzahl von Segmenten, die auf die enthaltenen Anforderungen angewendet werden. Weitere Segmente erhöhen die Komplexität der Anforderung. |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
