---
title: Auditprotokolle
description: Erfahren Sie, wie Sie Customer Journey Analytics-Auditprotokolle anzeigen und verwalten können.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 9ed7b541ebb1a89b286040c4ea96025b08029499
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 97%

---

# Auditprotokolle {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="Benutzer-ID"
>abstract="Die Benutzer-ID lässt sich ermitteln, indem Sie in einem Protokolleintrag, der die gewünschte Person enthält, auf die Infoschaltfläche klicken."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="Komponenten-ID"
>abstract="Die Komponenten-ID lässt sich ermitteln, indem Sie in einem Protokolleintrag, der die gewünschte Komponente enthält, auf die Infoschaltfläche klicken."

<!-- markdownlint-enable MD034 -->


Um die Transparenz und Sichtbarkeit der im System durchgeführten Aktivitäten zu erhöhen, ermöglicht Ihnen Adobe Customer Journey Analytics, die Benutzeraktivität für verschiedene Services und Funktionen mithilfe von Auditprotokollen zu erfassen. Diese Protokolle bilden ein Audit-Protokoll, das Ihnen bei der Fehlerbehebung helfen und Ihr Unternehmen dabei unterstützen kann, die Richtlinien zur Datenverwaltung in Unternehmen und die gesetzlichen Anforderungen wie den Health Insurance Portability and Accountability Act (HIPAA) einzuhalten.

In einem Auditprotokoll wird festgehalten, **wer** **welche** Aktion **wann** ausgeführt hat. Jede in einem Protokoll aufgezeichnete Aktion enthält Metadaten, die den Aktionstyp, das Datum und die Uhrzeit, die E-Mail-ID des/der Benutzenden, der/die die Aktion ausgeführt hat, und zusätzliche Attribute des Aktionstyps angeben.

In diesem Artikel werden Auditprotokolle in Customer Journey Analytics behandelt, einschließlich der Frage, wie sie in der Benutzeroberfläche angezeigt und verwaltet werden können.

## Zugriff auf Auditprotokolle

Wenn diese Funktion für Ihr Unternehmen aktiviert ist, werden bei Aktivitäten automatisch Auditprotokolle aufgezeichnet. Sie müssen die Datenerfassung in Auditprotokollen nicht manuell aktivieren.

Um Auditprotokolle anzeigen und exportieren zu können, benötigen Sie in der Adobe-Konsole die Zugriffsberechtigung **[!UICONTROL Zugriff auf Auditprotokolle]**. Informationen zum Verwalten individueller Berechtigungen für Customer Journey Analytics-Funktionen finden Sie in der [Dokumentation zur Zugriffssteuerung](../technotes/access-control.md).

## Administratorprotokoll in der Benutzeroberfläche anzeigen

Navigieren Sie in Customer Journey Analytics zu **[!UICONTROL Tools]** > **[!UICONTROL Auditprotokolle]**.

Das Auditprotokoll für den heutigen und gestrigen Tag wird standardmäßig angezeigt.

![Auditprotokoll mit Hervorhebung von „Heute“ und „Gestern“. ](assets/audit_ui.png)

Sie können auswählen, welche Spalten sichtbar sein sollen, indem Sie oben rechts zur Spaltenauswahl wechseln.

## Anzeigen von Informationen zu einzelnen Protokolleinträgen

Doppelklicken Sie auf die Info-Schaltfläche (i) neben einer Beschreibung.

![Auditprotokoll mit hervorgehobener Schaltfläche „Info“. ](assets/info-button-audit.png)

Die folgenden Informationen werden angezeigt:

* **[!UICONTROL Aktionsname]**: Die durchgeführte Aktion. Mögliche Werte sind:
   * API_REQUEST: Jede Aktion löst eine Backend-API-Anfrage aus. Es werden Details zur API-Anfrage angezeigt.
   * APPROVE: Es wurde eine Aktion „Genehmigung“ durchgeführt.
   * CREATE: Es wurde eine Aktion „Erstellen“ durchgeführt.
   * DELETE: Es wurde eine Aktion „Löschen“ durchgeführt.
   * BEARBEITEN: Es wurde eine Aktion „Bearbeiten“ durchgeführt.
   * EMBARGO: Wenn Sie eine Anfrage im [Reporting Activity Manager](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests) einschränken, wird die Aktion im Auditprotokoll unter EMBARGO aufgezeichnet.
   * EXPORT: Es wurde eine Aktion „Export“ durchgeführt.
   * ORG_CHANGE: Es wurde eine Aktion „Organisationsänderung“ durchgeführt.
   * REFRESH: Es wurde eine Aktion „Aktualisieren“ durchgeführt.
   * SHARE: Es wurde eine Aktion „Freigeben“ durchgeführt.
   * TRANSFER: Es wurde eine Aktion „Übertragen“ ausgeführt.
   * UNAPPROVE: Es wurde eine Aktion „Genehmigung aufheben“ durchgeführt.
   * UNSHARE: Es wurde eine Aktion „Freigabe aufheben“ durchgeführt.
* **[!UICONTROL Erstellungsdatum]**: Datum und Uhrzeit der Durchführung der Aktion.
* **[!UICONTROL Beschreibung]**: Eine Zusammenfassung der Aktion.
* **[!UICONTROL Benutzername]**: Die Benutzerin oder der Benutzer, die bzw. der die Aktion durchgeführt hat. Manchmal fehlt der Benutzername. Erwägen Sie, die Funktion [Produktnutzung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/tools/product-usage/usage-overview) zu verwenden, da sie immer den Namen der Anmeldebenutzerin bzw. des Anmeldebenutzers enthält.
* **[!UICONTROL E-Mail]**: Die E-Mail-Adresse der Benutzerin oder des Benutzers, die bzw. der die Aktion durchgeführt hat.
* **[!UICONTROL Name der Komponente]**: Die Komponente, für die die Benutzerin oder der Benutzer eine Aktion durchgeführt hat.
* **[!UICONTROL Typ der Komponente]**: Der Typ der Komponente. Mögliche Werte sind:
   * ANNOTATION
   * AUDIENCE
   * CALCULATED_METRIC
   * CONNECTION
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTER
   * IMS_ORG
   * MOBILE
   * PROJECT (Workspace)
   * REPORT
   * SCHEDULED_PROJECT
   * USER
   * USER_GROUP
* **[!UICONTROL Komponenten-ID]**: Die ID der Komponente, für die die Benutzerin oder der Benutzer eine Aktion durchgeführt hat.
* **[!UICONTROL IMS-Org-ID]**: Die IMS-ID der Organisation im Format `ABC123@AdobeOrg`.
* **[!UICONTROL Log ID]**: Eine eindeutige ID für diesen Protokolleintrag.
* **[!UICONTROL Benutzer-ID]**: Die eindeutige ID, die die Benutzerin oder den Benutzer identifiziert, die bzw. der die Aktion durchgeführt hat.
* **[!UICONTROL Benutzertyp]**: Der verwendete Authentifizierungstyp. Zu gültigen Werten gehören:
   * IMS
   * OKTA

### Filtern von Auditprotokollen

Wählen Sie das Trichtersymbol (![Filter](assets/filter-icon.png)), um eine Liste von Filterfeldern anzuzeigen, mit denen die Ergebnisse eingegrenzt werden können. Unabhängig von den ausgewählten Filtern werden nur die letzten 1.000 Datensätze angezeigt.

![Auditprotokoll mit den für den Datumsbereich angezeigten Filtern.](assets/filters.png)

Die Benutzeroberfläche verfügt für Protokolle über folgende Filter:

| Filter | Beschreibung |
| --- | --- |
| [!UICONTROL Datumsbereich] | Sie können nach einem Datumsbereich filtern, indem Sie ein Datum auswählen. Sie können einen Datumsbereich auswählen, indem Sie den Cursor über mehrere Daten ziehen. Standardmäßig sind das heutige und das gestrige Datum ausgewählt. |
| [!UICONTROL Aktion] | Filtern Sie nach einem der oben aufgeführten Aktionsnamen. |
| [!UICONTROL Benutzer-ID] | Filtern nach der Benutzer-ID eines/einer bestimmten Benutzenden. Die Benutzer-ID finden Sie, indem Sie auf die Info-Schaltfläche (i) neben einem Benutzernamen klicken. |
| [!UICONTROL E-Mail] | Filtern nach der E-Mail-Adresse eines/einer bestimmten Benutzenden. Die E-Mail-Adresse finden Sie, indem Sie auf die Info-Schaltfläche (i) neben einem Benutzernamen klicken. |
| [!UICONTROL Komponenten-ID] | Filtern nach einer bestimmten Komponenten-ID. Die Komponenten-ID finden Sie, indem Sie auf die Info-Schaltfläche (i) für die gewünschte Komponente klicken. |
| [!UICONTROL Typ der Komponente] | Filtern Sie nach einem der oben aufgeführten Komponententypen. |

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
| [!UICONTROL Projekt &#x200B;] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
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

Alle Aktionen, die Sie in der Benutzeroberfläche ausführen können, können auch über API-Aufrufe ausgeführt werden. Weitere Informationen finden Sie im [Referenzdokument zur Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs).
