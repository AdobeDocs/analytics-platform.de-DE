---
title: Zugriffssteuerung für Customer Journey Analytics
description: Informationen über die Implementierung der Zugriffssteuerung in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 81e08ecb593b6ba789c479d0e648cbe7ba0a82d6
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 96%

---

# Zugriffssteuerung

Drei Zugriffsebenen oder drei Rollen gelten in Customer Journey Analytics: Produktadmin-Rolle, Produktprofil-Admin-Rolle und Benutzerzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden in diesem Artikel granulare Möglichkeiten zur Einschränkung des Zugriffs behandelt, beispielsweise die Workspace-Kuratierung und die Zugriffssteuerung auf Zeilen- und Werteebene.

## Rollenbasierte Zugriffssteuerung

Die folgenden rollenbasierten Zugriffssteuerungsebenen sind verfügbar.

### Produktadmin-Rolle

Benutzende, denen die Rolle „Produktadmin“ zugewiesen ist, erhalten standardmäßig die erforderlichen Berechtigungen, um die meisten Aufgaben in Customer Journey Analytics auszuführen. Für einige Aufgaben sind jedoch zusätzliche Berechtigungen erforderlich.

So fügen Sie eine Person als Produktadmin hinzu:

1. Öffnen Sie die [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Wählen Sie [!UICONTROL **Customer Journey Analytics**] > Registerkarte [!UICONTROL **Admins**] > [!UICONTROL **Admin hinzufügen**] aus.

   Die hinzugefügten Personen erhalten die [Standardberechtigungen für Produktadmins](#product-admin-default-permissions). Bei Bedarf können Sie ihnen auch [zusätzliche Berechtigungen](#product-admin-additional-permissions) erteilen.

#### Standardberechtigungen für Produktadmins

Produktadmins sind berechtigt, die meisten Aufgaben in Customer Journey Analytics auszuführen.

Produktadmins erhalten standardmäßig die erforderlichen Berechtigungen, um die folgenden Aufgaben auszuführen:

* Aktualisieren/Löschen von Projekten, Segmenten, berechneten Metriken, Zielgruppen, Kommentaren oder von anderen Benutzenden erstellten Segmenten
* Freigeben von Workspace-Projekten für alle Benutzenden
* Anzeigen der Berichtsaktivität im [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportieren vollständiger Tabellen](/help/analysis-workspace/export/export-cloud.md) aus Analysis Workspace

#### Zusätzliche Berechtigungen für Produktadmins

Neben dem Hinzufügen als Produktadmin zum **Customer Journey Analytics-Produktprofil** in der [Admin Console](https://adminconsole.adobe.com/enterprise/) sind zusätzliche Berechtigungen erforderlich, damit die folgenden Aufgaben in Customer Journey Analytics durchgeführt werden können:

* Erstellen, Aktualisieren und Löschen von [Datenansichten](/help/data-views/data-views.md).
* Erstellen, Aktualisieren und Löschen von [Verbindungen](/help/connections/overview.md)

  Um diese Aufgabe ausführen zu können, müssen Benutzende Teil eines **Experience Platform-Produktprofils** sein, das die folgenden Berechtigungen bietet:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL Mindestens eine] | Zugriff auf relevante Sandboxes für Verbindungen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Anzeigen von Schemata] | Schreibgeschützter Zugriff auf Schemata und zugehörige Ressourcen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Verwalten von Schemata] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Schemata und zugehörigen Ressourcen. |
  | [!UICONTROL Daten-Management] | [!UICONTROL Anzeigen von Datensätzen] | Schreibgeschützter Zugriff auf Datensätze und Schemata. |
  | [!UICONTROL Identitätsverwaltung] | [!UICONTROL Anzeigen von Identity-Namespaces] | Schreibgeschützter Zugriff für Identity-Namespaces. |

  Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Verwalten von Berechtigungen für ein Produktprofil](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/ui/permissions).


* Wenn Journey Optimizer in Customer Journey Analytics integriert ist und Journey Optimizer-Verbindungen vorhanden sind, müssen auch Journey-Berechtigungen hinzugefügt werden, um auf Verbindungen zugreifen zu können:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Journeys] | [!UICONTROL Anzeigen von Journey-Ereignissen, Datenquellen und Aktionen] | Schreibgeschützter Zugriff auf Journey-Ereignisse, benutzerdefinierte Journey-Aktionen und Journey-Datenquellen. |
  | [!UICONTROL Journeys] | [!UICONTROL Verwalten von Journey-Ereignissen, Datenquellen und Aktionen] | Lesen, Erstellen, Bearbeiten und Löschen von Ereignissen, Quellen oder Aktionen. |
  | [!UICONTROL Journeys] | [!UICONTROL Anzeigen von Journeys] | Schreibgeschützter Zugriff auf Journeys. |
  | [!UICONTROL Journeys] | [!UICONTROL Verwalten von Journeys] | Lesen, Erstellen, Bearbeiten und Löschen von Journeys. |

* Exportieren von Datensätzen zu [Zielen](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets)

  Um diese Aufgabe ausführen zu können, müssen Benutzende Teil eines **Experience Platform-Produktprofils** sein, das die folgenden Berechtigungen bietet:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Ziele] | [!UICONTROL Verwalten von Zielen] | Zugriff zum Lesen, Erstellen und Löschen von Zielverbindungen und Zielkonten. |
  | [!UICONTROL Ziele] | [!UICONTROL Aktivieren von Zielen] | Ermöglicht Benutzerinnen und Benutzern das Aktivieren von Segmenten für vorhandene Ziele. Aktiviert den Zuordnungsschritt im Aktivierungs-Workflow. Diese Berechtigung erfordert, dass Benutzenden, die Daten für Ziele aktivieren, auch die Berechtigung „Anzeigen von Zielen“ gewährt wird. |

  Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Verwalten von Berechtigungen für ein Produktprofil](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/ui/permissions).

* Verwenden der [BI-Erweiterung](../data-views/bi-extension.md)

  Für Benutzende, die die BI-Erweiterung verwenden möchten, muss ein Produktadmin

   * sicherstellen, dass die Experience Platform-Berechtigungen für die Person eine Rolle enthalten, die über die Ressource „Abfrage-Service“ mit den Optionen „Verwalten von Abfragen“ und „Verwalten der Abfrage-Service-Integration“ verfügt. Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Verwalten von Berechtigungen für ein Produktprofil](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/ui/permissions).

     | Kategorie | Berechtigung | Beschreibung |
     |---|---|---|
     | [!UICONTROL Abfrage-Service] | [!UICONTROL Verwalten von Abfragen] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen strukturierter SQL-Abfragen für Platform-Daten. |
     | [!UICONTROL Abfrage-Service] | [!UICONTROL Verwalten der Integration des Abfrage-Service] | Zugriff auf das Erstellen, Aktualisieren und Löschen nicht ablaufender Anmeldedaten für den Zugriff auf den Abfrage-Service. |

   * sicherstellen, dass die Person über die richtigen Customer Journey Analytics-Berechtigungen verfügt:
      * Berechtigung zum Zugriff auf die relevanten Datenansichten. Siehe [!UICONTROL Datenansichten] unter [Zugriff auf Benutzerebene](#user-level-access).
      * Berechtigung zum Zugriff auf die Customer Journey Analytics-BI-Erweiterung. Siehe [!UICONTROL Datenansichts-Tools] unter [Zugriff auf Benutzerebene](#user-level-access).

### Produktprofil-Admin-Rolle

Ein Produktprofil ist ein Satz von Berechtigungen. Produktadmins erstellen Produktprofile und können Produktprofil-Admins zuweisen, um ein oder mehrere Produktprofile zu verwalten. Ein Produktprofil-Admin kann dann:

* die zugewiesenen Produktprofile verwalten. Beispielsweise das Hinzufügen oder Entfernen von Benutzenden oder Benutzergruppen und das Ändern der Berechtigungen für die Produktprofile.

* Datenansichten in Customer Journey Analytics bearbeiten, die Teil eines zugewiesenen Produktprofils sind. Produktprofil-Admins können keine neuen Datenansichten erstellen.

### Zugriff auf Benutzerebene

In der folgenden Tabelle sind die wichtigsten Zugriffsberechtigungen für verschiedene Customer Journey Analytics-Funktionen aufgeführt, die Sie für relevante Benutzende konfigurieren können. Sie können verschiedene Benutzerzugriffsebenen über Produktprofile verwalten. Ein Produktprofil kombiniert eine Reihe von Berechtigungen, die Sie dann einzelnen Benutzenden oder Benutzergruppen zuweisen können.

Die Registerkarte **[!UICONTROL Berechtigungen]** ist Teil jedes Produktprofils in der [Admin Console](https://adminconsole.adobe.com/enterprise/). 

![Admin Console-Berechtigungen](assets/permissions.png)

| Kategorie | Berechtigung | Beschreibung |
| --- | --- | ---|
| [!UICONTROL Datenansichten] | *Name der Datenansicht* | Wenn **[!UICONTROL Auto-Include]** auf **[!UICONTROL Ein]** umgeschaltet wird, können Benutzende, die Teil dieses Produktprofils sind, alle vorhandenen und neu erstellten Datenansichten anzeigen. Wenn diese Einstellung auf **[!UICONTROL Aus]** gesetzt ist, können bestimmte Datenansichten ausgewählt werden, auf die Benutzende Zugriff haben. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zugriff auf geführte Analysen] | Ermöglicht Benutzenden den Zugriff auf [Geführte Analyse](/help/guided-analysis/overview.md). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Erstellung berechneter Metriken] | Ermöglicht Benutzenden die Erstellung von [berechneten Metriken](/help/components/calc-metrics/calc-metr-overview.md). Benutzer können nur die berechneten Metriken, die sie erstellen, oder die berechneten Metriken, die für sie freigegeben wurden, taggen, freigeben, löschen oder umbenennen. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Erstellung von Segmenten] | Ermöglicht Benutzenden die Erstellung von [Segmenten](/help/components/segments/seg-overview.md). Benutzer können nur die Segmente, die sie erstellen, oder die Segmente, die für sie freigegeben wurden, taggen, freigeben, löschen oder umbenennen. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Labs-Zugriff] | Ermöglicht Benutzenden den Zugriff auf die Registerkarte [Labs](/help/labs/labs.md) in Customer Journey Analytics. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Anmerkungserstellung] | Ermöglicht Benutzenden die Erstellung von [Anmerkungen](/help/components/annotations/overview.md). Benutzende können nur die Anmerkungen taggen, freigeben, löschen und umbenennen, die sie erstellen oder die für sie freigegeben sind. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zielgruppenansicht] | Ermöglicht Benutzenden die Ansicht von [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zielgruppenerstellung] | Ermöglicht Benutzenden die Erstellung [Zielgruppen](/help/components/audiences/audiences-overview.md). Erfordert [Segmente verwalten](https://experienceleague.adobe.com/de/docs/experience-platform/access-control/home) in Adobe Experience Platform. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Daten-Storytelling] | Ermöglicht Benutzenden das [Generieren von Folien-Präsentationen basierend auf Workspace-Projekten](/help/analysis-workspace/curate-share/generate-slides.md). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Zugriff auf Auditprotokolle] | Erzwingt die Berechtigungsprüfung für die [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) und die Benutzeroberfläche für Audit-Protokolle. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Freigeben von Projekt-Links für alle] | Ermöglicht Benutzenden das [Freigeben von Projekten für alle](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/curate-share/share-projects). |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Prognose] | Ermöglicht Benutzenden den Zugriff auf die [Prognose](../analysis-workspace/c-forecast/forecasting.md)-Funktion in Analysis Workspace |
| [!UICONTROL Reporting-Tools] | [!UICONTROL KI-Assistent: Produktkenntnisse] | Ermöglicht Benutzenden den Zugriff auf den [KI-Assistenten](../ai-assistant.md) für Produktkenntnisse. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Data Insights Agent] | Ermöglicht Benutzenden den Zugriff auf die [Data Insights Agent](../data-analysis-ai.md) für KI-gesteuerte Dateneinblicke. |
| [!UICONTROL Reporting-Tools] | [!UICONTROL Intelligente Untertitel] | Ermöglicht Benutzenden den Zugriff auf [intelligente Beschriftungen](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Tools für die Datenansicht] | [!UICONTROL Vollständiger Tabellenexport] | Ermöglicht Benutzenden das [Exportieren von vollständigen Tabellen in die Cloud](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Tools für die Datenansicht] | [!UICONTROL CJA BI-Erweiterung] | Ermöglicht Benutzenden die Verwendung der [BI-Erweiterung](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Workspace-Projektkuratierung

Eine weitere Ebene der Zugriffskontrolle kann auf der Workspace-Berichtsebene verwendet werden. Der Zugriff auf bestimmte Komponenten kann für bestimmte Benutzende eingeschränkt werden. Weitere Informationen dazu, wie Sie Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) auf Workspace-Projektebene einschränken und wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden und unterliegen somit einer Änderung in Customer Journey Analytics. Wenn sie geändert werden, ändert sich auch die Berichterstellung rückwirkend.

## Anwendungsbeispiele

Hier sind einige Anwendungsfälle, die zeigen, wie die Zugriffskontrolle in realen Szenarien eingesetzt werden kann.

### Zugriff durch Dritte

Sie können Team-Führungskräften eines Drittanbieters, mit dem Ihr Unternehmen zusammenarbeitet, Zugriff auf die Produktprofilverwaltung gewähren. Diese Admins können diesem Produktprofil Benutzende des Teams aus dem Unternehmen hinzufügen. Diese Produktprofil-Admins können Zugriff auf bestimmte Datenansichten gewähren und andere Benutzende auf Drittanbieterseite zu diesem Produktprofil hinzufügen. Produktprofil-Admins können Datenansichten an die Anforderungen des Drittanbieter-Teams anpassen.

### Zugriffskontrolle auf Zeilenebene

Sie möchten Benutzenden nur auf die Daten eines bestimmten Tages Zugriff gewähren. So könnte der Zugriff auf diese speziellen Zeilen beschränkt werden:

1. Erstellen Sie ein Segment in den [!UICONTROL Einstellungen] einer bestimmten Datenansicht, wobei [!UICONTROL Tag] dem Datum entspricht, für den Sie den Datenzugriff ermöglichen möchten. Weitere Informationen finden Sie unter [Erstellen einer Datenansicht](/help/data-views/create-dataview.md#settings-filters).
1. Speichern Sie die Datenansicht, die das Segment auf den Datenteil der Datensätze in der zugrunde liegenden Verbindung anwendet. Alle Zeilen, die nicht zur Segmentdefinition passen, werden automatisch aus der Datenansicht ausgeschlossen und stehen Analysis Workspace bei Verwendung dieser Datenansicht nicht zur Verfügung.
1. Erstellen Sie ein neues [Produktprofil](#product-profile-admin-role) in der Admin Console, fügen Sie dem Produktprofil Benutzende hinzu und nehmen Sie nur diese spezifische Datenansicht in das Produktprofil auf.

### Zugriffskontrolle auf Wertebene

Benutzende, die Zugriff auf eine Datenansicht haben, können nur mit den Metriken und Dimensionen arbeiten, die vom Admin in diese Datenansicht aufgenommen worden sind. Admins können die Komponenteneinstellungen [Einschließen/Ausschließen](/help/data-views/component-settings/include-exclude-values.md) oder [Wert-Bucketing](../data-views/component-settings/value-bucketing.md) in einer Datenansicht verwenden, um bestimmte Dimensionswerte aus einer Datenansicht auszuschließen oder zu aggregieren.

Beispiel: Sie erstellen eine Metrik namens *Hypertonie* in einer Datenansicht aus einer Komponente, die individuelle Patientendaten aus dem Datensatz enthält. Sie verwenden Werte-Bucketing, um nur Zugriff auf Werte mit Buckets zu gewähren, sodass Benutzende der Daten die individuellen Patientendaten nicht sehen.
