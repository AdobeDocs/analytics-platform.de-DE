---
title: Zugriffssteuerung für Customer Journey Analytics
description: Erfahren Sie, wie Sie die Zugriffskontrolle in Customer Journey Analytics implementieren.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: b76a877d6ae20a111e5d2476a5045b34a9208ccf
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 22%

---

# Zugriffssteuerung

Drei Zugriffsebenen oder drei Rollen steuern Customer Journey Analytics: Produktadministratorrolle, Produktprofil-Administratorrolle und Benutzerzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden in diesem Artikel detailliertere Möglichkeiten zur Einschränkung des Zugriffs erläutert, z. B. die Workspace-Kuratierung und die Zugriffssteuerung auf Zeilen- und Werteebene.

## Rollenbasierte Zugriffssteuerung

Die folgenden rollenbasierten Zugriffssteuerungsebenen sind verfügbar.

### Rolle des Produktadministrators

Benutzende, denen die Rolle „Produktadministrator“ zugewiesen ist, erhalten standardmäßig die erforderlichen Berechtigungen, um die meisten Aufgaben in Customer Journey Analytics auszuführen. Für einige Aufgaben sind jedoch zusätzliche Berechtigungen erforderlich.

So fügen Sie einen Benutzer als Produktadministrator hinzu:

1. Zur [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Wählen Sie [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administratoren**] Registerkarte > [!UICONTROL **Administrator hinzufügen**] aus.

   Die hinzugefügten Benutzer erhalten die [Standardberechtigungen für Produktadministratoren](#product-admin-default-permissions). Bei Bedarf können Sie ihnen auch [zusätzliche Berechtigungen](#product-admin-additional-permissions) erteilen.

#### Standardberechtigungen für Produktadministratoren

Produktadministratoren sind berechtigt, die meisten Aufgaben in Customer Journey Analytics auszuführen.

Produktadministratoren erhalten standardmäßig die erforderlichen Berechtigungen, um die folgenden Aufgaben auszuführen:

* Aktualisieren und Löschen von Projekten, Segmenten, berechneten Metriken, Zielgruppen, Anmerkungen oder Segmenten, die von anderen Benutzern erstellt wurden
* Freigeben von Workspace-Projekten für alle Benutzenden
* Verwalten der Berichtsaktivität im [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportieren von vollständigen Tabellen](/help/analysis-workspace/export/export-cloud.md) aus Analysis Workspace

#### Zusätzliche Berechtigungen für Produktadministrator

Zusätzlich zur Hinzufügung als Produktadministrator zum **Customer Journey Analytics-Produktprofil** in der [Admin Console](https://adminconsole.adobe.com/enterprise/) sind zusätzliche Berechtigungen erforderlich, um die folgenden Aufgaben in Customer Journey Analytics durchzuführen:

* Erstellen, Aktualisieren und Löschen [Datenansichten](/help/data-views/data-views.md).
* Erstellen, Aktualisieren und Löschen [Verbindungen](/help/connections/overview.md)

  Um diese Aufgabe ausführen zu können, müssen Benutzende Teil eines **Experience Platform-Produktprofils** sein, das die folgenden Berechtigungen bietet:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL Mindestens einer] | Zugriff auf relevante Sandboxes für Verbindungen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Anzeigen von Schemata] | Schreibgeschützter Zugriff auf Schemata und zugehörige Ressourcen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Verwalten von Schemata] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Schemata und zugehörigen Ressourcen. |
  | [!UICONTROL Daten-Management] | [!UICONTROL Anzeigen von Datensätzen] | Schreibgeschützter Zugriff auf Datensätze und Schemata. |
  | [!UICONTROL Identity Management] | [!UICONTROL Anzeigen von Identitäts-Namensräumen] | Schreibgeschützter Zugriff für Identitäts-Namensräume. |

  Weitere Informationen zu Berechtigungen für Experience Platform finden Sie [Verwalten von Berechtigungen für ein Produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).


* Wenn Journey Optimizer in Customer Journey Analytics integriert ist, wo Journey Optimizer-Verbindungen vorhanden sind, müssen auch Journey-Berechtigungen hinzugefügt werden, um auf -Verbindungen zugreifen zu können:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Journeys] | [!UICONTROL Anzeigen von Journey-Ereignissen, Datenquellen und Aktionen] | Schreibgeschützter Zugriff auf Journey-Ereignisse, Journey benutzerdefinierter Aktionen und Journey-Datenquellen. |
  | [!UICONTROL Journeys] | [!UICONTROL Verwalten von Journey-Ereignissen, Datenquellen und Aktionen] | Lesen, Erstellen, Bearbeiten und Löschen von Ereignissen, Quellen oder Aktionen. |
  | [!UICONTROL Journeys] | [!UICONTROL Journey anzeigen] | Schreibgeschützter Zugriff auf Journey. |
  | [!UICONTROL Journeys] | [!UICONTROL Journey verwalten] | Lesen, Erstellen, Bearbeiten und Löschen von Journey |

* Exportieren von Datensätzen zu [Zielen](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets)

  Um diese Aufgabe ausführen zu können, müssen Benutzende Teil eines **Experience Platform-Produktprofils** sein, das die folgenden Berechtigungen bietet:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Ziele] | [!UICONTROL Verwalten von Zielen] | Zugriff auf das Lesen, Erstellen und Löschen von Zielverbindungen und Zielkonten. |
  | [!UICONTROL Ziele] | [!UICONTROL Aktivieren von Zielen] | Benutzern erlauben, Segmente für vorhandene Ziele zu aktivieren. Aktiviert den Zuordnungsschritt im Aktivierungs-Workflow. Diese Berechtigung erfordert auch, dass Benutzenden, die Daten für Ziele aktivieren möchten, die Berechtigung Ziele anzeigen gewährt wird. |

  Weitere Informationen zu Berechtigungen für Experience Platform finden Sie [Verwalten von Berechtigungen für ein Produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Verwenden der [BI-Erweiterung](../data-views/bi-extension.md)

  Für Benutzer, die die BI-Erweiterung verwenden möchten, Produktadministrator

   * Sie müssen sicherstellen, dass die Experience Platform-Berechtigungen für den -Benutzer eine Rolle enthalten, die über die Ressource „Abfrage-Service“ mit den Optionen „Abfragen verwalten“ und „Abfrage-Service-Integration verwalten“ verfügt. Weitere Informationen zu Berechtigungen für Experience Platform finden Sie [Verwalten von Berechtigungen für ein Produktprofil](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

     | Kategorie | Berechtigung | Beschreibung |
     |---|---|---| 
     | [!UICONTROL Abfrage-Service] | [!UICONTROL Verwalten von Abfragen] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen strukturierter SQL-Abfragen für Platform-Daten. |
     | [!UICONTROL Abfrage-Service] | [!UICONTROL Verwalten der Integration des Abfrage-Service] | Zugriff auf das Erstellen, Aktualisieren und Löschen nicht ablaufender Anmeldedaten für den Zugriff auf den Abfrage-Service. |

   * Er muss sicherstellen, dass der Benutzer über die richtigen Customer Journey Analytics-Berechtigungen verfügt:
      * Berechtigung zum Zugriff auf die relevanten Datenansichten. Siehe [!UICONTROL Datenansichten] in [Zugriff auf Benutzerebene](#user-level-access).
      * Berechtigung für den Zugriff auf die Customer Journey Analytics BI-Erweiterung. Siehe [!UICONTROL Datenansichts-Tools] unter [Zugriff auf Benutzerebene](#user-level-access).

### Rolle des Produktprofil-Administrators

Ein Produktprofil ist ein Satz von Berechtigungen. Produktadministratoren erstellen Produktprofile und können Produktprofiladministratoren zuweisen, um ein oder mehrere Produktprofile zu verwalten. Ein Produktprofil-Administrator kann dann:

* Verwalten Sie die zugewiesenen Produktprofile. Beispielsweise das Hinzufügen oder Entfernen von Benutzenden oder Benutzergruppen und das Ändern der Berechtigungen für die Produktprofile.

* Bearbeiten Sie in Customer Journey Analytics Datenansichten, die Teil eines zugewiesenen Produktprofils sind. Produktprofil-Admins können keine neuen Datenansichten erstellen.

### Zugriff auf Benutzerebene

In der folgenden Tabelle sind die wichtigsten Zugriffsberechtigungen für verschiedene Customer Journey Analytics-Funktionen aufgeführt, die Sie für relevante Benutzende konfigurieren können. Sie können verschiedene Benutzerzugriffsebenen über Produktprofile verwalten. Ein Produktprofil kombiniert eine Reihe von Berechtigungen, die Sie dann einzelnen Benutzern oder Benutzergruppen zuweisen können.

Die **[!UICONTROL Berechtigungen]** ist Teil jedes Produktprofils in der [Admin Console](https://adminconsole.adobe.com/enterprise/).

![Admin Console-Berechtigungen](assets/permissions.png)

| Kategorie | Berechtigung | Beschreibung |
| --- | --- | ---|
| [!UICONTROL Datenansichten] | *Name der Datenansicht* | Wenn **[!UICONTROL Auto-Include]** auf **[!UICONTROL Ein]** umgeschaltet wird, können Benutzende, die Teil dieses Produktprofils sind, alle vorhandenen und neu erstellten Datenansichten anzeigen. Wenn diese Einstellung auf **[!UICONTROL Aus]** gesetzt ist, können bestimmte Datenansichten ausgewählt werden, auf die Benutzende Zugriff haben. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zugriff auf Analysis Workspace] | Benutzern Zugriff auf [Analysis Workspace ](/help/analysis-workspace/home.md). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zugriff auf geführte Analysen] | Ermöglicht Benutzenden den Zugriff auf [Geführte Analyse](/help/guided-analysis/overview.md). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Erstellung berechneter Metriken] | Ermöglicht Benutzenden die Erstellung [berechneter Metriken](/help/components/calc-metrics/calc-metr-overview.md). Benutzer können nur die berechneten Metriken, die sie erstellen, oder die berechneten Metriken, die für sie freigegeben wurden, taggen, freigeben, löschen, umbenennen, genehmigen oder die Genehmigung aufheben. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Erstellung von Segmenten] | Benutzenden die Erstellung von [Segmenten](/help/components/segments/seg-overview.md) ermöglichen. Benutzer können nur die Segmente, die sie erstellen, oder die Segmente, die für sie freigegeben wurden, taggen, freigeben, löschen, umbenennen, genehmigen oder die Genehmigung aufheben. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Labs-Zugriff] | Ermöglicht Benutzenden den Zugriff auf die [Labs](/help/labs/labs.md) in Customer Journey Analytics. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Anmerkungserstellung] | Benutzern die Erstellung von [Anmerkungen](/help/components/annotations/overview.md) ermöglichen. Benutzer können nur die Anmerkungen taggen, freigeben, löschen und umbenennen, die sie erstellen oder die für sie freigegeben sind. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zielgruppenansicht] | Benutzern die Ansicht [Zielgruppen](/help/components/audiences/audiences-overview.md) ermöglichen. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zielgruppenerstellung] | Ermöglicht Benutzenden die Erstellung [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zugriff auf Auditprotokolle] | Erzwingen Sie die Berechtigungsprüfung für die [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) und die Benutzeroberfläche für Auditprotokolle. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Projekt-Links für alle freigeben] | Benutzer [Projekte für alle freigeben.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Prognose] | Ermöglicht Benutzenden den Zugriff auf die [Prognose](../analysis-workspace/c-forecast/forecasting.md) Funktion in Analysis Workspace |
| [!UICONTROL Reporting-Tools] | [!UICONTROL KI-Assistent: Produktkenntnisse] | Ermöglicht Benutzenden den Zugriff auf den [KI-](../ai-assistant.md)) für Produktkenntnisse. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Intelligente Untertitel] | Benutzern Zugriff auf [intelligente Beschriftungen](/help/analysis-workspace/visualizations/intelligent-captions.md) ermöglichen. |
| [!UICONTROL Datenansichts-Tools] | [!UICONTROL Vollständiger Tabellenexport] | Benutzerinnen und [ können jetzt vollständige Tabellen in die Cloud ](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Datenansichts-Tools] | [!UICONTROL CJA BI-Erweiterung] | Benutzerinnen und Benutzern die Verwendung der [BI-Erweiterung](../data-views/bi-extension.md) ermöglichen. |

{style="table-layout:auto"}

## Workspace-Projektkuratierung

Eine weitere Ebene der Zugriffskontrolle kann auf der Workspace-Berichtsebene verwendet werden. Der Zugriff auf bestimmte Komponenten kann für bestimmte Benutzende eingeschränkt werden. Weitere Informationen dazu, wie Sie Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) auf Workspace-Projektebene einschränken und wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden und unterliegen somit einer Änderung in Customer Journey Analytics. Wenn sie geändert werden, ändert sich auch die Berichterstellung rückwirkend.

## Anwendungsbeispiele

Hier sind einige Anwendungsfälle, die zeigen, wie die Zugriffskontrolle in realen Szenarien eingesetzt werden kann.

### Zugriff durch Dritte

Sie können einem Teamleiter eines Drittanbieters, mit dem Ihr Unternehmen zusammenarbeitet, Zugriff auf die Produktprofilverwaltung gewähren. Dieser Administrator kann diesem Produktprofil Benutzer aus dem Team des Unternehmens hinzufügen. Dieser Produktprofil-Administrator kann Zugriff auf bestimmte Datenansichten gewähren und andere Benutzer innerhalb des Drittanbieters zu diesem Produktprofil hinzufügen. Der Produktprofil-Administrator kann Datenansichten an die Anforderungen des Drittanbieter-Teams anpassen.

### Zugriffskontrolle auf Zeilenebene

Benutzerinnen und Benutzern soll nur der Zugriff auf Daten eines Tages gewährt werden. So könnte der Zugriff auf diese speziellen Zeilen beschränkt werden:

1. Erstellen Sie ein Segment in [!UICONTROL Einstellungen] einer bestimmten Datenansicht, wobei [!UICONTROL Tag] dem Datum entspricht, an dem die Daten zugänglich sein sollen. Weitere Informationen [ Sie unter ](/help/data-views/create-dataview.md#settings-filters)Datenansicht erstellen“.
1. Speichern Sie die Datenansicht, die das Segment auf den Datenteil der Datensätze in der zugrunde liegenden Verbindung anwendet. Alle Zeilen, die nicht zur Segmentdefinition passen, werden automatisch aus der Datenansicht ausgeschlossen und stehen Analysis Workspace bei Verwendung dieser Datenansicht nicht zur Verfügung.
1. Erstellen Sie ein neues [Produktprofil](#product-profile-admin-role) in der Admin Console, fügen Sie Benutzer zum Produktprofil hinzu und nehmen Sie nur diese spezifische Datenansicht in das Produktprofil auf.

### Zugriffskontrolle auf Wertebene

Benutzende, die Zugriff auf eine Datenansicht haben, können nur mit den Metriken und Dimensionen arbeiten, die der Administrator in diese Datenansicht aufgenommen hat. Admins können die Komponenteneinstellungen [Einschließen/Ausschließen](/help/data-views/component-settings/include-exclude-values.md) oder [Wert-Bucketing](../data-views/component-settings/value-bucketing.md) in einer Datenansicht verwenden, um bestimmte Dimensionswerte aus einer Datenansicht auszuschließen oder zu aggregieren.

Beispiel: Sie erstellen eine Metrik namens *Hypertonie* in einer Datenansicht aus einer Komponente, die individuelle Patientendaten aus dem Datensatz enthält. Sie verwenden Werte-Bucketing, um nur Zugriff auf Werte mit Buckets zu gewähren, sodass Benutzende der Daten die individuellen Patientendaten nicht sehen.


