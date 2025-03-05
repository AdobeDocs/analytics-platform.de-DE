---
title: Erstellen oder Bearbeiten einer Verbindung
description: Beschreibt, wie sich in Customer Journey Analytics eine Verbindung zu einem Experience Platform-Datensatz erstellen oder bearbeiten lässt.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: baf0a1f1d0bdc0d3c60d9375e20c1de3f39f1702
workflow-type: tm+mt
source-wordcount: '4278'
ht-degree: 99%

---

# Erstellen oder Bearbeiten einer Verbindung {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="Hinzugefügte Einträge"
>abstract="Die Anzahl der Datensätze (Zeilen), die einer Verbindung im für die entsprechenden Datensätze ausgewählten Zeitintervall hinzugefügt wurden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="Übersprungene Einträge"
>abstract="Die Anzahl der Datensätze (Zeilen), die bei der Datenübertragung für eine Verbindung im für die entsprechenden Datensätze ausgewählten Zeitintervall übersprungen werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="Gelöschte Einträge"
>abstract="Die Anzahl der Datensätze (Zeilen), die im ausgewählten Zeitintervall für die ausgewählten Datensätze aus einer Verbindung entfernt wurden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="Zuletzt hinzugefügt"
>abstract="Zeitstempel des letzten Batches aus einem beliebigen Datensatz, der an eine Verbindung übertragen wurde."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="Rollierendes Datenfenster aktivieren"
>abstract="Definieren Sie die Datenspeicherung als rollierendes Fenster in Monaten auf Verbindungsebene."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="Durchschnittliche Anzahl der täglichen Nutzung"
>abstract="Wählen Sie einen Bereich für die Anzahl der erwarteten täglichen Ereignisse für die gesamte Verbindung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsadded"
>title="Hinzugefügte Einträge"
>abstract="Die Anzahl der Datensätze (Zeilen), die einer Verbindung im für die entsprechenden Datensätze ausgewählten Zeitintervall hinzugefügt wurden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsskipped"
>title="Übersprungene Einträge"
>abstract="Die Anzahl der Datensätze (Zeilen), die bei der Datenübertragung für eine Verbindung im für die entsprechenden Datensätze ausgewählten Zeitintervall übersprungen werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsdeleted"
>title="Gelöschte Einträge"
>abstract="Die Anzahl der Datensätze (Zeilen), die im ausgewählten Zeitintervall für die ausgewählten Datensätze aus einer Verbindung entfernt wurden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_lastadded"
>title="Zuletzt hinzugefügt"
>abstract="Zeitstempel des letzten Batches aus einem beliebigen Datensatz, der an eine Verbindung übertragen wurde."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_enablerollingdatawindow"
>title="Rollierendes Datenfenster aktivieren"
>abstract="Definieren Sie die Datenspeicherung als rollierendes Fenster in Monaten auf Verbindungsebene."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_averagenumberofdailyuses"
>title="Durchschnittliche Anzahl der täglichen Nutzung"
>abstract="Wählen Sie einen Bereich für die Anzahl der erwarteten täglichen Ereignisse für die gesamte Verbindung."

<!-- markdownlint-enable MD034 -->


Beim Workflow für die Erstellung und Bearbeitung von Verbindungen können alle Einstellungen zur Datensatz- und Verbindungskonfiguration mit einem unterstützenden Workflow zentral auf dem Bildschirm durchgeführt werden. Er ermöglicht Ihnen eine präzise Auswahl, Konfiguration und Prüfung von Datensätzen. Außerdem können Sie wichtige Informationen angeben, z. B. Datensatztyp, Größe, Schema, Datensatz-ID, Batch-Status, Aufstockungsstatus, Personen-IDs und vieles mehr, um das Risiko einer falschen Verbindungskonfiguration zu verringern. Im Folgenden finden Sie einen Überblick über die Funktionen:

* Sie können bei der Erstellung der Verbindung ein rollierendes Fenster zur Datenaufbewahrung aktivieren.
* Sie können Datensätze zu einer Verbindung hinzufügen und daraus entfernen. (Wenn Sie einen Datensatz entfernen, wird er aus der Verbindung entfernt und wirkt sich auf alle zugehörigen Datenansichten und zugrunde liegenden Analysis Workspace-Projekte aus.)
* Sie können für einzelne Datensätze Aufstockungsdaten aktivieren und anfordern.
* Sie können Datensätze bearbeiten, z. B. um eine weitere Aufstockung anzufordern.
* Sie können für einzelne Datensätze vorhandene Daten importieren.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Erstellen und Bearbeiten einer Verbindung](https://video.tv.adobe.com/v/343044/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


## Voraussetzungen

Die maximale Anzahl der Datensätze, die einer Verbindung hinzugefügt werden können, ist auf 100 begrenzt. Die Mischung hängt davon ab, welches Customer Journey Analytics-Paket Ihr Unternehmen erworben hat.

Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

| ****-Paket auswählen | **Stiftungs-**-Paket |
| --- | --- |
| Jede Kombination aus bis zu 100 Ereignis-/Profil-/Lookup-/Zusammenfassungsdatensätzen | Ein Ereignisdatensatz pro Verbindung |
|  | Bis zu 99 Profil-, Lookup- oder Zusammenfassungsdatensätze pro Verbindung |

{style="table-layout:auto"}

## Erstellen und Konfigurieren der Verbindung {#create-connection}

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Verbindungen]** aus dem Hauptmenü aus.
1. Wählen Sie **[!UICONTROL Neue Verbindung erstellen]** aus.

   ![Unbenannte Verbindungseinstellungen](assets/create-conn1.png)

1. Konfigurieren Sie die Verbindungseinstellungen.

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Name der Verbindung]** | Geben Sie einen eindeutigen Namen für die Verbindung ein. |
   | **[!UICONTROL Beschreibung der Verbindung]** | Beschreiben Sie den Zweck dieser Verbindung. |
   | **[!UICONTROL Sandbox]** | Wählen Sie eine Sandbox in Experience Platform aus, die die Datensätze enthält, zu denen Sie eine Verbindung herstellen möchten.<p>Adobe Experience Platform bietet [Sandboxes](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home) bereit, die eine einzelne Platform-Instanz in separate virtuelle Umgebungen aufteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu erleichtern. Sie können sich Sandboxes als „Datensilos“ vorstellen. Sandboxes dienen der Steuerung des Zugriffs auf Datensätze.<p>Nachdem Sie die Sandbox ausgewählt haben, werden in der linken Leiste alle Datensätze in der Sandbox angezeigt, aus denen Sie Daten abrufen können. |
   | **[!UICONTROL Rollierendes Datenfenster aktivieren]** | Wenn diese Option aktiviert ist, können Sie auf Verbindungsebene die Customer Journey Analytics-Datenspeicherung als rollierendes Fenster in Monaten (z. B. 1 Monat, 3 Monate und 6 Monate) definieren.<p>Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung jedoch Profil- oder Suchdatensätze enthält (neben einem oder mehreren Ereignisdatensätzen), werden diese Daten über denselben Zeitraum gespeichert.<p> Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.<p>Wenn Sie die Standardeinstellung unverändert (d. h. deaktiviert) lassen, hat die Adobe Experience Platform-Einstellung zur Datenspeicherung Vorrang vor der Aufbewahrungsfrist. Wenn also in Experience Platform Daten von einem Zeitraum von 25 Monaten enthalten sind, erhält Customer Journey Analytics durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in Customer Journey Analytics die verbleibenden 15 Monate beibehalten. |
   | **[!UICONTROL Hinzufügen von Datensätzen]** (siehe unten) | Fügen Sie Datensätze hinzu, wenn in Ihrer Datensatzliste keine Datensätze erscheinen. |
   | **[!UICONTROL Datensatzname]** | Wählen Sie einen oder mehrere Datensätze für die Customer Journey Analytics-Übertragung und dann die Option **[!UICONTROL Hinzufügen]** aus.<p>(Wenn Sie viele Datensätze zur Auswahl haben, können Sie mithilfe der Suchleiste „Datensätze suchen“ über der Liste der Datensätze nach den richtigen suchen.) |
   | **[!UICONTROL Zuletzt aktualisiert]** | Nur für Ereignis-Datensätze wird diese Einstellung automatisch auf das Standard-Zeitstempelfeld von Ereignis-basierten Schemas in Experience Platform gesetzt. „K. A.“ bedeutet, dass dieser Datensatz keine Daten enthält. |
   | **[!UICONTROL Anzahl der Datensätze]** | Die Gesamtzahl der Einträge im Vormonat für den Datensatz in Experience Platform. |
   | **[!UICONTROL Schema]** | Das [Schema](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition), auf dessen Grundlage der Datensatz in Adobe Experience Platform erstellt wurde. |
   | **[!UICONTROL Typ des Datensatzes]** | Customer Journey Analytics legt für jeden Datensatz, den Sie dieser Verbindung hinzugefügt haben, automatisch den Datensatztyp anhand der eingehenden Daten fest. Es gibt 3 verschiedene Datensatztypen: Ereignis-, Profil- und Such-Daten. Eine Erläuterung der Datensatztypen finden Sie in der unten stehenden Tabelle. |
   | **[!UICONTROL Granularität]** | Die Granularität der Daten im Datensatz; gilt nur für Zusammenfassungsdatensätze. |
   | **[!UICONTROL Datenquellentyp]** | Der Datenquellentyp des Datensatzes. Gilt nicht für Zusammenfassungsdatensätze. |
   | **[!UICONTROL Personen-ID]** | Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>WICHTIG: Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. In [diesem Videos](https://www.youtube.com/watch?v=G_ttmGl_LRU) sehen Sie, wie Sie eine Identität in Experience Platform definieren. |
   | **[!UICONTROL Schlüssel]** | Nur für Lookup-Datensätze (z. B. _id). |
   | **[!UICONTROL Übereinstimmender Schlüssel]** | Nur für Lookup-Datensätze (z. B. _id). |
   | **[!UICONTROL Neue Daten importieren]** | Auf „Ein“ oder „Aus“ einstellen. |
   | **[!UICONTROL Aufstockungsdaten]** | Sie können die Aufstockung der Daten in einem Datensatz anfordern. Zum Beispiel können Sie anfragen, die Daten der letzten sieben Tage aufzustocken. Konfigurieren Sie den Datensatz ordnungsgemäß und testen Sie Ihre Verbindung. Wenn alle Einstellungen korrekt sind, können Sie alle verbleibenden Daten mühelos aufstocken.<p>Darüber hinaus können Sie den Import neuer Daten nach Datensatz aktivieren. |
   | **[!UICONTROL Aufstockungsstatus]** | Dieser Status gibt an, ob Aufstockungsdaten verarbeitet werden. |


## Hinzufügen und Konfigurieren von Datensätzen {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_primaryid"
>title="Primäre ID "
>abstract="Wählen Sie die richtige primäre ID für Ihre Verbindung aus: „Person“ für ein B2C-Szenario. „Konto“ für ein B2B-Szenario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_optionalcontainers"
>title="Optionale Container"
>abstract="Wählen Sie weitere Container aus.<br/><br/>**[!UICONTROL Globales Konto ]**: ermöglicht die Konfiguration globaler Konten in einer Verbindung.<br/>**[!UICONTROL Opportunity]**: ermöglicht die Konfiguration von Opportunities in einer Verbindung.<br/>**[!UICONTROL Käufergruppe ]**: ermöglicht die Konfiguration von Käufergruppen in einer Verbindung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_personid"
>title="Personen-ID"
>abstract="Wählen Sie eine Personen-ID aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountid"
>title="Konto-ID"
>abstract="Wählen Sie eine Konto-ID (die eindeutige Kennung für ein Konto) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountfield"
>title="Kontofeld"
>abstract="Wählen Sie ein Feld aus, das die Konto-ID (die eindeutige Kennung für ein Konto) darstellt."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_globalaccountid"
>title="Globale Konto-ID"
>abstract="Wählen Sie eine globale Konto-ID (die eindeutige Kennung für ein globales Konto) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityid"
>title="Opportunity-ID"
>abstract="Wählen Sie eine Opportunity-ID (die eindeutige Kennung für eine Opportunity) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_buyinggroupid"
>title="Käufergruppen-ID"
>abstract="Wählen Sie eine Käufergruppen-ID (die eindeutige Kennung für eine Käufergruppe) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="Passender Schlüssel"
>abstract="Wählen Sie, wie Sie teilnehmen möchten: basierend auf einem passenden Schlüssel oder einem passenden Container.<br/><br/>**[!UICONTROL Passender Schlüssel ]**: Wählen Sie ein Feld aus, das einem der Ereignisdatensätze hinzugefügt werden soll. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen Ereignisdatensatz hinzugefügt oder konfiguriert.<br/>**[!UICONTROL Passender Container]**: Wählen Sie einen Container aus, der verwendet werden soll, um mit einem der Ereignis-Datensätze zu verknüpfen. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen oder mehrere Container konfiguriert."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="Neue Daten importieren"
>abstract="Alle neuen Batches, die dem Experience Platform-Datensatz hinzugefügt werden, werden automatisch in diese Verbindung aufgenommen und für die Analyse verfügbar gemacht."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="Aufstockung des Datensatzes"
>abstract="Mit dieser Option werden die vorhandenen (historischen) Daten von Experience Platform für diesen Datensatz in der Verbindung aufgestockt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="Datensatz transformieren"
>abstract="Mit dieser Option wird der Datensatz so transformiert, dass er für personenbezogene Suchvorgänge in B2B-Szenarien verwendet werden kann. Sobald diese Option aktiviert ist, ist die Transformation des Datensatzes nicht mehr umkehrbar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_connectionmap"
>title="Verbindungszuordnung"
>abstract="Die Verbindungszuordnung visualisiert die Beziehungen zwischen Ereignis-, Personen-, Konto- und relevanten Lookup-Datensätzen (wie Opportunites, Kampagnenmitgliedern und mehr)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_primaryid"
>title="Primäre ID "
>abstract="Wählen Sie die richtige primäre ID für Ihre Verbindung aus: „Person“ für ein B2C-Szenario. „Konto“ für ein B2B-Szenario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_optionalcontainers"
>title="Optionale Container"
>abstract="Wählen Sie weitere Container aus.<br/><br/>**[!UICONTROL Globales Konto ]**: ermöglicht die Konfiguration globaler Konten in einer Verbindung.<br/>**[!UICONTROL Opportunity]**: ermöglicht die Konfiguration von Opportunities in einer Verbindung.<br/>**[!UICONTROL Käufergruppe ]**: ermöglicht die Konfiguration von Käufergruppen in einer Verbindung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_personid"
>title="Personen-ID"
>abstract="Wählen Sie eine Personen-ID aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountid"
>title="Konto-ID"
>abstract="Wählen Sie eine Konto-ID (die eindeutige Kennung für ein Konto) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountfield"
>title="Kontofeld"
>abstract="Wählen Sie ein Feld aus, das die Konto-ID (die eindeutige Kennung für ein Konto) darstellt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_globalaccountid"
>title="Globale Konto-ID"
>abstract="Wählen Sie eine globale Konto-ID (die eindeutige Kennung für ein globales Konto) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_opportunityid"
>title="Opportunity-ID"
>abstract="Wählen Sie eine Opportunity-ID (die eindeutige Kennung für eine Opportunity) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_buyinggroupid"
>title="Käufergruppen-ID"
>abstract="Wählen Sie eine Käufergruppen-ID (die eindeutige Kennung für eine Käufergruppe) aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_matchingkey"
>title="Passender Schlüssel"
>abstract="Wählen Sie, wie Sie teilnehmen möchten: basierend auf einem passenden Schlüssel oder einem passenden Container.<br/><br/>**[!UICONTROL Passender Schlüssel ]**: Wählen Sie ein Feld aus, das einem der Ereignisdatensätze hinzugefügt werden soll. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen Ereignisdatensatz hinzugefügt oder konfiguriert.<br/>**[!UICONTROL Passender Container]**: Wählen Sie einen Container aus, der verwendet werden soll, um mit einem der Ereignis-Datensätze zu verknüpfen. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen oder mehrere Container konfiguriert."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_importnewdata"
>title="Neue Daten importieren"
>abstract="Alle neuen Batches, die dem Experience Platform-Datensatz hinzugefügt werden, werden automatisch in diese Verbindung aufgenommen und für die Analyse verfügbar gemacht."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_datasetbackfill"
>title="Aufstockung des Datensatzes"
>abstract="Mit dieser Option werden die vorhandenen (historischen) Daten von Experience Platform für diesen Datensatz in der Verbindung aufgestockt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_transformdataset"
>title="Datensatz transformieren"
>abstract="Mit dieser Option wird der Datensatz so transformiert, dass er für personenbezogene Suchvorgänge in B2B-Szenarien verwendet werden kann. Sobald diese Option aktiviert ist, ist die Transformation des Datensatzes nicht mehr umkehrbar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_connectionmap"
>title="Verbindungszuordnung"
>abstract="Die Verbindungszuordnung visualisiert die Beziehungen zwischen Ereignis-, Personen-, Konto- und relevanten Lookup-Datensätzen (wie Opportunites, Kampagnenmitgliedern und mehr)."

<!-- markdownlint-enable MD034 -->


Mit dem neuen Workflow können Sie beim Erstellen einer Verbindung einen Experience Platform-Datensatz hinzufügen.

1. Wählen Sie im Dialogfeld „Verbindungseinstellungen“ die Option **[!UICONTROL Datensätze hinzufügen]** aus.

1. Im Schritt [!UICONTROL Auswählen von Datensätzen] wird eine Liste der Experience Platform-Datensätze angezeigt.

   ![Auswählen von Datensätzen](assets/select-datasets.png)

   Für jeden Datensatz zeigt die Liste Folgendes an:

   | Spalte | Beschreibung |
   |---|---|
   | Datensatz | Der Name des Datensatzes. Wählen Sie den Namen aus, um zum Datensatz in Experience Platform weitergeleitet zu werden. Wählen Sie ![Informationen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) aus, um ein Popup-Fenster mit weiteren Details zum Datensatz anzuzeigen. Sie können **[!UICONTROL In Platform bearbeiten]** auswählen, um den Datensatz direkt in Experience Platform zu bearbeiten. |
   | Typ des Datensatzes | Der Typ des Datensatzes: „Ereignis“, „Profil“, „Suche“ oder „Lookup“. |
   | Anzahl der Einträge | Die Gesamtzahl der Einträge im Vormonat für den Datensatz in Experience Platform. |
   | Schema | Das Schema für den Datensatz. Wählen Sie den Namen aus, um zum Schema in Experience Platform weitergeleitet zu werden. |
   | Letzter Batch | Der Status des letzten Batches, der in Experience Platform aufgenommen wurde. Weitere Informationen finden Sie unter [Batch-Status](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/batch/troubleshooting#batch-states). |
   | Datensatz-ID | Die ID des Datensatzes. |
   | Zuletzt aktualisiert | Der Zeitstempel für die letzte Aktualisierung des Datensatzes. |


1. Wählen Sie einen oder mehrere Datensätze und anschließend die Option **[!UICONTROL Weiter]** aus. Mindestens ein Ereignisdatensatz muss Teil der Verbindung sein.
   * Um die für die Liste der Datensätze angezeigten Spalten zu ändern, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus und wählen Sie die Spalten aus, die im Dialogfeld [!UICONTROL Tabelle anpassen] angezeigt werden sollen.
   * Um nach einem bestimmten Datensatz zu suchen, verwenden Sie das ![Suchfeld](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Um die ausgewählten Datensätze ein- oder auszublenden, wählen Sie ![Auswählen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg), **[!UICONTROL Ausgewählte ausblenden]** oder **[!UICONTROL Ausgewählte anzeigen]** aus.
   * Um einen Datensatz aus der Liste der ausgewählten Datensätze zu entfernen, verwenden Sie ![Schließen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Um alle ausgewählten Datensätze zu entfernen, wählen Sie **[!UICONTROL Alle löschen]**.




1. Konfigurieren Sie nun die Datensätze einzeln.

   ![Konfigurieren von Datensätzen](assets/add-dataset.png)

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Personen-ID]** | Nur für Ereignis- und Profildatensätze verfügbar. Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity). <p>Beim Wert für die ausgewählte Personen-ID wird zwischen Groß- und Kleinschreibung unterschieden. Beispielsweise sind `abc123` und `ABC123` zwei verschiedene Werte. |
   | **[!UICONTROL Zeitstempel]** | Nur für Ereignis- und Zusammenfassungsdatensätze wird diese Einstellung automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in Experience Platform gesetzt. |
   | **[!UICONTROL Schlüssel]** | Nur für Lookup-Datensätze verfügbar. Der für einen Lookup-Datensatz zu verwendende Schlüssel. |
   | **[!UICONTROL Passender Schlüssel]** | Nur für Lookup-Datensätze verfügbar. Der passende Schlüssel, der in einem der Ereignisdatensätze hinzugefügt werden soll. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen Ereignisdatensatz hinzugefügt oder konfiguriert. |
   | **[!UICONTROL Zeitzone]** | Nur für Zusammenfassungsdaten verfügbar. Wählen Sie die entsprechende Zeitzone für die Zeitreihen-Zusammenfassungsdaten aus. |
   | **[!UICONTROL Datenquellentyp]** | Wählen Sie einen Datenquellentyp aus. <br/>Hierzu gehören: <ul><li>[!UICONTROL Web-Daten]</li><li>[!UICONTROL App-Daten]</li><li>[!UICONTROL PoS-Daten]</li><li>[!UICONTROL CRM-Daten]</li><li>[!UICONTROL Umfragedaten]</li><li>[!UICONTROL Callcenter-Daten]</li><li>[!UICONTROL Produktdaten]</li><li> [!UICONTROL Kontodaten]</li><li> [!UICONTROL Transaktionsdaten]</li><li>[!UICONTROL Kunden-Feedback-Daten]</li><li> [!UICONTROL Sonstige]</li></ul>Dieses Feld wird verwendet, um sich einen Überblick über die verwendeten Datenquellen zu verschaffen. |
   | **[!UICONTROL Importieren neuer Daten]** | Aktivieren Sie diese Option, wenn eine fortlaufende Verbindung hergestellt werden soll. Mit einer fortlaufenden Verbindung sind neue Daten-Batches, die den Datensätzen hinzugefügt werden, automatisch in Workspace verfügbar. |
   | **[!UICONTROL Aufstockung des Datensatzes]** | Aktivieren Sie **[!UICONTROL Aufstockung aller vorhandenen Daten]**, um sicherzustellen, dass alle vorhandenen Daten aufgestockt werden.<br/><br/>Wählen Sie **[!UICONTROL Aufstockung anfordern]** aus, um eine Aufstockung mit historischen Daten für einen bestimmten Zeitraum durchzuführen. Sie können bis zu 10 Aufstockungszeiträume für Datensätze definieren.<ol><li>Definieren Sie den Zeitraum durch Eingabe von Start- und Enddaten oder Auswahl von Datumsangaben mithilfe des ![Kalenders](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Wählen Sie **[!UICONTROL Aufstockung in Warteschlange stellen]** aus, um die Aufstockung der Liste hinzuzufügen, oder **[!UICONTROL Abbrechen]**, um den Vorgang abzubrechen.</li></ol>Wählen Sie für jeden Eintrag ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) aus, um den Zeitraum zu bearbeiten, oder ![Löschen](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg), um den Eintrag zu löschen.<br/><br/>Bei Aufstockungen:<ul><li>Sie können jeden Datensatz einzeln aufstocken.</li><li>Neue Daten, die einem Datensatz in der Verbindung hinzugefügt werden, werden priorisiert, sodass diese neuen Daten die geringste Latenz aufweisen.</li><li>Alle (historischen) Aufstockungsdaten werden langsamer importiert. Die Menge historischer Daten beeinflusst die Latenz.</li><li>Der Analytics-Quell-Connector importiert Daten aus bis zu 13 Monaten (unabhängig von ihrer Größe) für Produktions-Sandboxes. Die Aufstockung in Nicht-Produktions-Sandboxes ist dagegen auf 3 Monate beschränkt.</li></ul> |
   | **[!UICONTROL Datensatz transformieren]** | Für bestimmte B2B-Lookup-Datensätze können Sie die Umwandlung eines Datensatzes für geeignete personenbasierte B2B-Reporting-Szenarien aktivieren. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](transform-datasets-b2b-lookups.md). |
   | **[!UICONTROL Aufstockungsstatus]** | Mögliche Statusindikatoren sind:<ul><li>Erfolgreich</li><li>X Aufstockung(en) werden verarbeitet</li><li>Aus</li></ul> |
   | **[!UICONTROL Datensatz-ID]** | Diese ID wird automatisch generiert. |
   | **[!UICONTROL Beschreibung]** | Die Beschreibung, die diesem Datensatz bei seiner Erstellung gegeben wurde. |
   | **[!UICONTROL Datensatzgröße]** | Die Größe des Datensatzes. |
   | **[!UICONTROL Schema]** | Das Schema, auf dessen Grundlage der Datensatz in Adobe Experience Platform erstellt wurde. |
   | **[!UICONTROL Datensatz]** | Der Name des Datensatzes. |
   | **[!UICONTROL Vorschau: *Datensatzname *]** | Vorschau des Datensatzes mit Spalten für Datum, persönlicher ID und Kennung. |
   | **[!UICONTROL Entfernen]** | Sie können den Datensatz löschen oder entfernen und die Personen-ID ändern, ohne die gesamte Verbindung zu löschen. Durch Löschen oder Entfernen reduzieren sich die Kosten für die Datenaufnahme sowie der aufwändige Prozess der Neuerstellung der gesamten Verbindung und der zugehörigen Datenansichten. |

   {style="table-layout:auto"}

## Verbindungsvorschau {#preview}

Um die von Ihnen erstellte Verbindung in einer Vorschau anzuzeigen, wählen Sie im Dialogfeld „Verbindungseinstellungen“ die Option **[!UICONTROL Verbindungsvorschau]** aus.

![Verbindungsvorschau](assets/create-conn4.png)

Diese Vorschau enthält einige Spalten zur Verbindungskonfiguration. Welche Spaltentypen angezeigt werden, hängt von Ihren individuellen Datensätzen ab.

## Datensatztypen {#dataset-types}

[!UICONTROL Customer Journey Analytics] legt für jeden Datensatz, den Sie dieser Verbindung hinzufügen, automatisch den Datensatztyp anhand der eingehenden Daten fest.

>[!IMPORTANT]
>
>Fügen Sie mindestens einen Ereignis- oder Zusammenfassungsdatensatz als Teil einer Verbindung hinzu.

Es gibt verschiedene Datensatztypen: [!UICONTROL Ereignis]-, [!UICONTROL Profil], [!UICONTROL Lookup]- und [!UICONTROL Zusammenfassungsdaten].

| Typ des Datensatzes | Beschreibung | Zeitstempel | Schema | Personen-ID |
|---|---|---|---|---|
| **[!UICONTROL Ereignis]** | Daten, die Ereignisse im Laufe der Zeit darstellen. Beispiele hierfür sind Web-Besuche, Interaktionen, Transaktionen, PoS-Daten, Umfragedaten, Ad-Impression-Daten usw. Diese Daten können etwa typische Clickstream-Daten mit einer Kunden- oder Cookie-ID und einem Zeitstempel sein. Bei Ereignisdaten können Sie entscheiden, welche ID als Personen-ID verwendet wird. | Wird automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in [!UICONTROL Experience Platform] gesetzt. | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Zeitreihen“ basiert. Beispiele sind „XDM-Erlebnisereignis“ oder „XDM-Entscheidungsereignis“. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jedes in Experience Platform definierte Datensatzschema kann ein eigener Satz von einer oder mehreren Identitäten definiert und mit einem Identity-Namespace verknüpft werden. Jede dieser Identitäten kann als Personen-ID verwendet werden. Beispiele sind Cookie-ID, zugeordnete ID, Benutzer-ID und Trackingcode. |
| **[!UICONTROL Suche]** | Sie können Datensätze als Suchvorgänge von Feldern in allen Datensatztypen hinzufügen: Profil-, Lookup- und Ereignisdatensätze. (Letztere wurden immer unterstützt.) Diese zusätzliche Funktion erweitert die Fähigkeit von Customer Journey Analytics, komplexe Datenmodelle, einschließlich B2B, zu unterstützen. Diese Daten werden verwendet, um nach Werten oder Schlüsseln in Ihren Ereignis-, Profil- oder Suchdaten zu suchen. Sie können bis zu zwei Ebenen von Suchvorgängen hinzufügen. (Beachten Sie Folgendes: [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md) können nicht als übereinstimmende Schlüssel für die Suche in Verbindungen verwendet werden.) Beispielsweise können Sie Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten Produktnamen zuordnen. Sehen Sie sich hierfür das [B2B-Beispiel](/help/use-cases/b2b/example.md) an. | -/- | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Eintrag“ basiert, mit Ausnahme der Klasse „XDM-Individuelles Profil“. | -/- |
| **[!UICONTROL Profil]** | Daten, die auf Personen, Benutzende oder Kundinnen bzw. Kunden in den [!UICONTROL Ereignisdaten] angewendet werden. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen. | -/- | Jedes integrierte oder benutzerdefinierte Schema, das auf der Klasse „XDM-Individuelles Profil“ basiert. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Jeder Datensatz (ausgenommen Zusammenfassungsdatensätze), der in [!DNL Experience Platform] definiert ist, verfügt über einen eigenen Satz von einer oder mehreren definierten Personen-IDs. Beispiele sind Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw.<br>![Personen-ID ](assets/person-id.png)**Hinweis**: Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, spiegelt sich dies in der Berichterstattung wider. Um Datensätze zusammenzuführen, müssen Sie dieselbe Personen-ID verwenden. |
| **Zusammenfassung** | Zeitreihendaten, die nicht an eine einzelne Personen-ID gebunden sind. Zusammenfassungsdaten stellen aggregierte Daten auf einer anderen Aggregationsebene dar, z. B. Kampagnen. Sie können diese Daten im Customer Journey Analytics verwenden, um verschiedene Anwendungsfälle zu unterstützen. Weitere Informationen finden Sie [Zusammenfassungsdaten](/help/data-views/summary-data.md). | Wird automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata des Typs „Zusammenfassungsmetriken“ in Experience Platform gesetzt. Es wird nur die Granularität „Stündlich“ oder „Täglich“ unterstützt. | Jedes integrierte oder benutzerdefinierte Schema, das auf der Klasse „XDM-Zusammenfassungsmetriken“ basiert. | -/- |

>[!MORELIKETHIS]
>
>Blog: [So nutzen Sie Ereignis-, Lookup- und Profildatensätze in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-to-leverage-event-lookup-and-profile-datasets-in-adobe/ba-p/681478)

## Verwenden von numerischen Feldern als Suchschlüssel und Nachschlagewerte {#numeric}

Diese Suchfunktion ist nützlich, wenn Sie ein numerisches Feld, z. B. Kosten oder Marge, zu einem zeichenfolgenbasierten Schlüsselfeld hinzufügen möchten. Numerische Werte können als Schlüssel oder als Werte in die Suche einbezogen werden. In Ihrem Lookup-Schema können numerische Werte mit z. B. Ihren Produktnamen, COGS, Kampagnen-Marketing-Kosten oder Margen verknüpft sein. Im Folgenden finden Sie ein Beispiel für ein Lookup-Schema in Adobe Experience Platform:

![Lookup-Schema](assets/schema.png)

Es wird jetzt unterstützt, dass diese Werte als Metriken oder Dimensionen in Customer Journey Analytics-Berichte eingefügt werden können. Wenn Sie Ihre Verbindung einrichten und Lookup-Datensätze abrufen, können Sie die Datensätze bearbeiten, um die [!UICONTROL Schlüssel] und [!UICONTROL Übereinstimmungsschlüssel] auszuwählen:

![Datensatz bearbeiten](assets/lookup-dataset.png)

Wenn Sie eine Datenansicht einrichten, die auf dieser Verbindung basiert, fügen Sie die numerischen Werte als Komponenten zur Datenansicht hinzu. Jedes Projekt, das auf dieser Datenansicht basiert, kann dann über diese numerischen Werte berichten.

## Identity Map als Personen-ID verwenden {#id-map}

In Customer Journey Analytics kann die Identity Map für ihre Personen-ID verwendet werden. Identity Map ist eine Zuordnungs-Datenstruktur, mit der Schlüssel-/Wert-Paare hochgeladen werden können. Die Schlüssel sind Identity-Namespaces und der Wert ist eine Struktur, die den Identitätswert enthält. Die Identity Map ist für jede hochgeladene Zeile/jedes hochgeladene Ereignis vorhanden und wird für jede Zeile entsprechend aufgefüllt.

Die Identity Map ist für jeden Datensatz verfügbar, der ein auf der [ExperienceEvent XDM](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home)-Klasse basierendes Schema verwendet. Wenn Sie einen solchen Datensatz für eine Customer Journey Analytics-Verbindung auswählen, können Sie entweder ein Feld als primäre ID oder die Identity Map auswählen:

![](assets/idmap1.png)

Wenn Sie Identity Map auswählen, erhalten Sie zwei zusätzliche Konfigurationsoptionen:

| Option | Beschreibung |
|---|---|
| **[!UICONTROL Primären ID-Namespace verwenden]** | Mit dieser Option wird Customer Journey Analytics angewiesen, nach der Identität in der Identitätszuordnung zu suchen, die mit dem Attribut `primary=true` markiert ist, und diese Identität als Personen-ID für die entsprechende Zeile zu verwenden. Diese Identität ist der Primärschlüssel, der in Experience Platform für die Partitionierung verwendet wird. Sie ist auch der Hauptkandidat für die Customer Journey Analytics-Personen-ID (je nachdem, wie der Datensatz in einer Customer Journey Analytics-Verbindung konfiguriert ist). |
| **[!UICONTROL Namespace]** | (Diese Option ist nur verfügbar, wenn Sie den primären ID-Namespace nicht verwenden.) Identity-Namespaces sind eine Komponente des [Experience Platform Identity Service](https://experienceleague.adobe.com/de/docs/experience-platform/identity/features/namespaces). Namespaces dienen als Indikatoren für den Kontext, auf den sich eine Identität bezieht. Wenn Sie einen Namespace angeben, sucht Customer Journey Analytics in der Identitätszuordnung jeder Zeile nach diesem Namespace-Schlüssel und verwendet die Identität unter diesem Namespace als Personen-ID für die entsprechende Zeile. Da Customer Journey Analytics nicht alle Zeilen in einem Datensatz durchsuchen kann, um festzustellen, welche Namespaces vorhanden sind, werden alle möglichen Namespaces in der Dropdown-Liste angezeigt. Sie müssen wissen, welche Namespaces in den Daten angegeben sind. Diese Namespaces werden nicht automatisch erkannt. |

{style="table-layout:auto"}

### Identity Map-Randfälle {#id-map-edge}

In dieser Tabelle werden die beiden Konfigurationsoptionen angezeigt, wenn Randfälle vorhanden sind, und wie sie behandelt werden:

| Option | Keine IDs in der Identitätszuordnung | Mehrere IDs, keine als primär markiert | Es wurden mehrere IDs als primär markiert | Einzelne ID, als primär markiert oder nicht | Ungültiger Namespace mit einer als primär markierten ID |
|---|---|---|---|---|---|
| **[!UICONTROL Primären ID-Namespace verwenden] aktiviert** | Customer Journey Analytics ignoriert die Zeile. | Customer Journey Analytics ignoriert die Zeile, da keine primäre ID angegeben ist. | Alle unter allen Namespaces als primär markierten IDs werden in eine Liste extrahiert. Sie werden dann alphabetisch sortiert. Bei dieser neuen Sortierung wird der erste Namespace mit seiner ersten ID als Personen-ID verwendet. | Die einzelne ID wird als Personen-ID verwendet. | Obwohl der Namespace möglicherweise ungültig ist (nicht in Adobe Experience Platform vorhanden), verwendet Customer Journey Analytics die primäre ID unter diesem Namespace als Personen-ID. |
| **[!UICONTROL Spezifischer Identity Map-Namespace] ausgewählt** | Customer Journey Analytics ignoriert die Zeile. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. (Bei der Erstellung der Verbindung kann nur ein gültiger Namespace ausgewählt werden. Daher ist es nicht möglich, einen ungültigen Namespace/eine ungültige ID als Personen-ID zu verwenden.) |

{style="table-layout:auto"}

## Berechnen der durchschnittlichen Anzahl von täglichen Ereignissen {#average-number}

Diese Berechnung wird für jeden Datensatz in der Verbindung durchgeführt.

1. Wechseln Sie zu [Adobe Experience Platform-Abfrage-Services](https://experienceleague.adobe.com/de/docs/experience-platform/query/home) und erstellen Sie eine Abfrage.

   Die Abfrage würde wie folgt aussehen:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In diesem Beispiel ist „analytics_demo_data“ der Name des Datensatzes.

2. Um alle in Adobe Experience Platform vorhandenen Datensätze anzuzeigen, führen Sie die Abfrage `Show Tables` durch.


## Algorithmisches Bereinigen großer Lookup-Datensätze

Beim Erstellen einer Verbindung können Sie große Datensätze zu Suchzwecken hinzufügen. Ein Beispiel hierfür wäre ein Datensatz, der einen Produktkatalog darstellt, sodass beim Erstellen von Berichten und Visualisierungen nach beschreibenden Produktinformationen gesucht werden kann. Ein solch großer Lookup-Datensatz kann die maximal 10 Millionen eindeutigen Lookups überschreiten. Dieser Grenzwert ist derzeit als Schutzmechanismus implementiert und führt dazu, dass zusätzliche Daten übersprungen werden.

Sie können eine algorithmische Bereinigung eines großen Lookup-Datensatzes anfordern. Bei dieser algorithmischen Bereinigung bleiben nur Daten im Lookup-Datensatz, die mit den Schlüsseln in Ihrem Ereignisdatensatz übereinstimmen. Auf diese Weise müssen Sie nicht den gesamten unbereinigten Lookup-Datensatz laden. Alte oder seltener verwendete Elemente werden entfernt, was sich geringfügig auf Berichte auswirken kann, jedoch erhebliche Vorteile bringt. Der Algorithmus bezieht die letzten 90 Tage ein und führt wöchentlich Aktualisierungen durch.

Wenden Sie sich an Ihr Adobe-Support-Team, um weitere Informationen zu erhalten und diese Funktion zu aktivieren.
