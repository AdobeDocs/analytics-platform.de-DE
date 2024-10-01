---
title: Auditprotokolle
description: Erfahren Sie, wie Sie Customer Journey Analytics-Auditprotokolle anzeigen und verwalten.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 31381cd397a821cc3ff1b3c15ae968a7260a6e9e
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 66%

---

# Auditprotokolle {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_userid"
>title="Benutzer-ID"
>abstract="Die Benutzer-ID finden Sie, indem Sie auf die Schaltfläche „Info“ auf einem Protokolleintrag klicken, der den/die gewünschte(n) Benutzende(n) enthält."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_componentid"
>title="Komponenten-ID"
>abstract="Die Komponenten-ID finden Sie, indem Sie auf die Schaltfläche „Info“ auf einem Protokolleintrag klicken, der die gewünschte Komponente enthält."

<!-- markdownlint-enable MD034 -->


Um die Transparenz und Sichtbarkeit der im System durchgeführten Aktivitäten zu erhöhen, können Sie mit Adobe Customer Journey Analytics die Benutzeraktivität für verschiedene Dienste und Funktionen in Form von &quot;Prüfprotokollen&quot;überprüfen. Diese Protokolle bilden einen Prüfpfad, der Ihnen bei der Fehlerbehebung helfen kann und Ihrem Unternehmen ermöglicht, betriebliche Datenverwaltungsrichtlinien und gesetzliche Anforderungen wie den Health Insurance Portability and Accountability Act (HIPAA) einzuhalten.

In einem Auditprotokoll wird festgehalten, **wer** **welche** Aktion **wann** ausgeführt hat. Jede in einem Protokoll aufgezeichnete Aktion enthält Metadaten, die den Aktionstyp, das Datum und die Uhrzeit, die E-Mail-ID des/der Benutzenden, der/die die Aktion ausgeführt hat, und zusätzliche Attribute des Aktionstyps angeben.

In diesem Thema werden Auditprotokolle im Customer Journey Analytics behandelt, einschließlich der Anzeige und Verwaltung dieser Protokolle in der Benutzeroberfläche.

## Zugriff auf Auditprotokolle

Wenn diese Funktion für Ihr Unternehmen aktiviert ist, werden bei Aktivitäten automatisch Auditprotokolle aufgezeichnet. Sie müssen die Datenerfassung in Auditprotokollen nicht manuell aktivieren.

Um Auditprotokolle anzeigen und exportieren zu können, benötigen Sie in der Adobe-Konsole die Zugriffsberechtigung **[!UICONTROL Zugriff auf Auditprotokolle]**. Informationen zum Verwalten individueller Berechtigungen für Customer Journey Analytics-Funktionen finden Sie in der Dokumentation zur [Zugriffskontrolle](../technotes/access-control.md).

## Administratorprotokoll in der Benutzeroberfläche anzeigen

Navigieren Sie unter Customer Journey Analytics zu **[!UICONTROL Tools]** > **[!UICONTROL Prüfprotokolle]**.

Das Auditprotokoll für den heutigen und gestrigen Tag wird standardmäßig angezeigt.

![Markierung des Auditprotokolls heute und gestern. ](assets/audit_ui.png)

Sie können auswählen, welche Spalten sichtbar sein sollen, indem Sie oben rechts zur Spaltenauswahl wechseln.

## Anzeigen von Informationen zu einzelnen Protokolleinträgen

Doppelklicken Sie auf die Info-Schaltfläche (i) neben einer Beschreibung.

![Prüfprotokoll, das die Infoschaltfläche hervorhebt. ](assets/info-button-audit.png)

Die folgenden Informationen werden angezeigt:

* **[!UICONTROL Aktionsname]**: Die durchgeführte Aktion. Mögliche Werte:
   * API_ANFRAGE
   * Genehmigen
   * ERSTELLEN
   * DELETE
   * BEARBEITEN
   * EMBARGO
   * EXPORTIEREN
   * ORG_CHANGE
   * AKTUALISIEREN
   * FREIGEBEN
   * TRANSFER
   * UNGENEHMIGEN
   * UNSHARE
* **[!UICONTROL Erstellungsdatum]**: Das Datum und die Uhrzeit, zu der die Aktion durchgeführt wurde.
* **[!UICONTROL Beschreibung]**: Eine Zusammenfassung der Aktion.
* **[!UICONTROL Benutzername]**: Der Benutzer, der die Aktion ausgeführt hat.
* **[!UICONTROL E-Mail]**: Die E-Mail-Adresse des Benutzers, der die Aktion ausgeführt hat.
* **[!UICONTROL Komponentenname]**: Die Komponente, auf die der Benutzer eine Aktion ausgeführt hat.
* **[!UICONTROL Komponententyp]**: Der Typ der Komponente. Mögliche Werte:
   * ANMERKUNG
   * ZIELGRUPPE
   * CALCULATED_METRIC
   * VERBINDUNG
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTER
   * IMS_ORG
   * MOBILE
   * PROJEKT
   * BERICHT
   * ZEDULED_PROJECT
   * BENUTZER
   * USER_GROUP
* **[!UICONTROL Komponenten-ID]**: Die ID der Komponente, für die der Benutzer eine Aktion ausgeführt hat.
* **[!UICONTROL IMS-Organisations-ID]**: Die IMS-ID des Unternehmens im Format `ABC123@AdobeOrg`.
* **[!UICONTROL Log ID]**: Eine eindeutige ID, die diesen Protokolleintrag identifiziert.
* **[!UICONTROL Benutzer-ID]**: Die eindeutige ID, mit der der Benutzer identifiziert wird, der die Aktion ausgeführt hat.
* **[!UICONTROL Benutzertyp]**: Der verwendete Authentifizierungstyp. Zu gültigen Werten gehören:
   * IMS
   * OKTA

### Filtern von Auditprotokollen

Wählen Sie das Trichtersymbol (![Filter](assets/filter-icon.png)), um eine Liste von Filterfeldern anzuzeigen, mit denen die Ergebnisse eingegrenzt werden können. Unabhängig von den ausgewählten Filtern werden nur die letzten 1.000 Datensätze angezeigt.

![Prüfprotokoll, das die für den Datenbereich angezeigten Filter anzeigt.](assets/filters.png)

Die Benutzeroberfläche verfügt für Protokolle über folgende Filter:

| Filter | Beschreibung |
| --- | --- |
| [!UICONTROL Datumsbereich] | Sie können nach einem Datumsbereich filtern, indem Sie ein Datum auswählen. Sie können einen Datumsbereich auswählen, indem Sie den Cursor über mehrere Daten ziehen. Standardmäßig sind das heutige und das gestrige Datum ausgewählt. |
| [!UICONTROL Aktion] | Filtern Sie nach einem beliebigen Aktionsnamen, der oben aufgeführt ist. |
| [!UICONTROL Benutzer-ID] | Filtern nach der Benutzer-ID eines/einer bestimmten Benutzenden. Die Benutzer-ID finden Sie, indem Sie auf die Info-Schaltfläche (i) neben einem Benutzernamen klicken. |
| [!UICONTROL E-Mail] | Filtern nach der E-Mail-Adresse eines/einer bestimmten Benutzenden. Die E-Mail-Adresse finden Sie, indem Sie auf die Info-Schaltfläche (i) neben einem Benutzernamen klicken. |
| [!UICONTROL Komponenten-ID] | Filtern nach einer bestimmten Komponenten-ID. Die Komponenten-ID finden Sie, indem Sie auf die Info-Schaltfläche (i) für die gewünschte Komponente klicken. |
| [!UICONTROL Typ der Komponente] | Filtern Sie nach einem beliebigen Komponententyp, der oben aufgeführt ist. |

{style="table-layout:auto"}

## Von Auditprotokollen erfasste Ereignistypen

In der folgenden Tabelle ist aufgeführt, welche Aktionen für welche Komponenten durch Auditprotokolle aufgezeichnet werden:

| Typ der Komponente | Aktionen |
| --- | --- |
| [!UICONTROL Anmerkung] | <ul><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Zielgruppe] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li><li>Exportieren</li><li>Aktualisieren</li></ul> |
| [!UICONTROL Berechnete Metrik] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Verbindung] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Datenansicht] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Datumsbereich] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Filter] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL IMS-Organisation] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Projekt ] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Bericht] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Geplantes Projekt] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Benutzer] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Benutzergruppe] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |

{style="table-layout:auto"}

## Herunterladen von Auditprotokollen

Sie können Auditprotokolle im CSV- oder JSON-Format herunterladen. Alle angewendeten Filter oder ausgewählten Spalten werden in den heruntergeladenen Dateien übernommen.

1. Klicken Sie in der rechten oberen Ecke des Bildschirms auf **[!UICONTROL Herunterladen]**.
1. Geben Sie das Format an.
1. Klicken Sie erneut auf **[!UICONTROL Herunterladen]**.

## Verwalten von Auditprotokollen in der API

Alle Aktionen, die Sie in der Benutzeroberfläche ausführen können, können auch über API-Aufrufe ausgeführt werden. Weitere Informationen finden Sie im Referenzdokument [Customer Journey Analytics API-Referenz](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) .
