---
title: Zugriffssteuerung für Customer Journey Analytics
description: Erfahren Sie, wie Sie die Zugriffskontrolle in Customer Journey Analytics implementieren können.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 30133a5d825c3623a5f46a972e787cf60626edf3
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 22%

---

# Zugriffssteuerung

Für die Customer Journey Analytics gibt es drei Zugriffsebenen bzw. drei Benutzerrollen: die Rolle des Produktadministrators, die Rolle des Produktprofiladministrators und den Zugriff auf Benutzerebene. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden in diesem Artikel detailliertere Möglichkeiten zum Beschränken des Zugriffs beschrieben, wie z. B. die Kuratierung und Zeilenebene von Workspace sowie die Zugriffskontrolle auf Wertebene.

## Rollenbasierte Zugriffssteuerung

Die folgenden rollenbasierten Zugriffssteuerungsebenen sind verfügbar.

### Rolle des Produktadministrators

Benutzern, denen die Rolle &quot;Produkt-Administrator&quot;zugewiesen wurde, werden standardmäßig die erforderlichen Berechtigungen erteilt, um die meisten Aufgaben innerhalb von Customer Journey Analytics auszuführen. Einige Aufgaben erfordern jedoch zusätzliche Berechtigungen.

So fügen Sie einen Benutzer als Produktadministrator hinzu:

1. Wechseln Sie zur [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Wählen Sie die Registerkarte [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] > [!UICONTROL **Admin hinzufügen**].

   Die Benutzer, die Sie hinzugefügt haben, erhalten die Standardberechtigungen des [Produktadministrators](#product-admin-default-permissions). Sie können ihnen bei Bedarf auch [zusätzliche Berechtigungen](#product-admin-additional-permissions) gewähren.

#### Standardberechtigungen für Produktadministratoren

Produktadministratoren haben die Berechtigung, die meisten Aufgaben innerhalb von Customer Journey Analytics auszuführen.

Produktadministratoren erhalten die erforderlichen Berechtigungen, um standardmäßig die folgenden Aufgaben auszuführen:

* Datenansichten erstellen, aktualisieren und löschen
* Projekte, Filter, berechnete Metriken, Zielgruppen, Anmerkungen oder von anderen Benutzern erstellte Filter aktualisieren und löschen
* Freigeben von Workspace-Projekten für alle Benutzenden
* Berichtaktivität im [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md) verwalten
* [ Vollständige Tabellen exportieren](/help/analysis-workspace/export/export-cloud.md) aus Analysis Workspace

#### Zusätzliche Berechtigungen für Produktadministratoren

Zusätzlich zum Hinzufügen als Produktadministrator zum **Customer Journey Analytics-Produktprofil** in der [Admin Console](https://adminconsole.adobe.com/enterprise/) sind zusätzliche Berechtigungen erforderlich, um die folgenden Aufgaben innerhalb von Customer Journey Analytics durchzuführen:

* Daten erstellen, aktualisieren und löschen [Verbindungen](/help/connections/overview.md)

  Um diese Aufgabe durchzuführen, müssen Benutzer Teil eines **Experience Platform-Produktprofils** sein, das über die folgenden Berechtigungen verfügt:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Anzeigen von Schemata] | Schreibgeschützter Zugriff auf Schemata und zugehörige Ressourcen. |
  | [!UICONTROL Datenmodellierung] | [!UICONTROL Verwalten von Schemata] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Schemata und zugehörigen Ressourcen. |
  | [!UICONTROL Daten-Management] | [!UICONTROL Anzeigen von Datensätzen] | Schreibgeschützter Zugriff auf Datensätze und Schemata. |
  | [!UICONTROL Daten-Management] | [!UICONTROL Datensätze verwalten] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen von Datensätzen. Schreibgeschützter Zugriff auf Schemata. |
  | [!UICONTROL Datenaufnahme] | [!UICONTROL Verwalten von Quellen] | Zugriff zum Lesen, Erstellen, Bearbeiten und Deaktivieren von Quellen. |
  | [!UICONTROL Identity Management] | [!UICONTROL Anzeigen von Identitäts-Namensräumen] | Schreibgeschützter Zugriff für Identitäts-Namensräume. |

  Weitere Informationen zu Experience Platform-Berechtigungen finden Sie unter [Berechtigungen für ein Produktprofil verwalten](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Exportieren von Datensätzen in [Ziele](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)

  Um diese Aufgabe durchzuführen, müssen Benutzer Teil eines **Experience Platform-Produktprofils** sein, das über die folgenden Berechtigungen verfügt:

  | Kategorie | Berechtigung | Beschreibung |
  |---|---|---|
  | [!UICONTROL Ziele] | [!UICONTROL Verwalten von Zielen] | Zugriff auf das Lesen, Erstellen und Löschen von Zielverbindungen und Zielkonten. |
  | [!UICONTROL Ziele] | [!UICONTROL Aktivieren von Zielen] | Benutzer können Segmente für vorhandene Ziele aktivieren. Aktiviert den Zuordnungsschritt im Aktivierungs-Workflow. Diese Berechtigung erfordert auch, dass dem Benutzer, der Daten für Ziele aktivieren möchte, die Berechtigung zum Anzeigen von Zielen erteilt wird. |

  Weitere Informationen zu Experience Platform-Berechtigungen finden Sie unter [Berechtigungen für ein Produktprofil verwalten](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Verwenden der [BI-Erweiterung](../data-views/bi-extension.md)

  Damit Benutzer die BI-Erweiterung verwenden können, muss ein Produkt-Administrator

   * muss sicherstellen, dass die Experience Platform-Berechtigungen für den Benutzer eine Rolle enthalten, die über die Query Service-Ressource mit den Optionen Abfragen verwalten und Query Service-Integration verwalten verfügt. Weitere Informationen zu Experience Platform-Berechtigungen finden Sie unter [Berechtigungen für ein Produktprofil verwalten](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

     | Kategorie | Berechtigung | Beschreibung |
     |---|---|---| 
     | [!UICONTROL Abfragedienst] | [!UICONTROL Verwalten von Abfragen] | Zugriff auf das Lesen, Erstellen, Bearbeiten und Löschen strukturierter SQL-Abfragen für Platform-Daten. |
     | [!UICONTROL Abfragedienst] | [!UICONTROL Verwalten der Integration des Abfrage-Service] | Zugriff auf das Erstellen, Aktualisieren und Löschen nicht ablaufender Anmeldedaten für den Zugriff auf den Abfrage-Service. |

   * muss die entsprechenden Customer Journey Analytics-Berechtigungen für den Benutzer sicherstellen:
      * Zugriffsberechtigung auf die entsprechenden Datenansichten. Siehe [!UICONTROL Datenansichten] in [Zugriff auf Benutzerebene](#user-level-access).
      * Zugriffsberechtigung auf die Customer Journey Analytics BI-Erweiterung. Siehe [!UICONTROL Datenansichts-Tools] in [Zugriff auf Benutzerebene](#user-level-access).

## Administratorrolle für Produktprofile

Ein Produktprofil ist ein Satz von Berechtigungen. Produktadministratoren erstellen Produktprofile und können Produktprofiladministratoren zuweisen, um ein oder mehrere Produktprofile zu verwalten. Ein Produktprofiladministrator kann dann:

* Verwalten Sie die zugewiesenen Produktprofile. Zum Beispiel das Hinzufügen oder Entfernen von Benutzern oder Benutzergruppen und das Ändern der Berechtigungen für die Produktprofile.

* Bearbeiten Sie unter Customer Journey Analytics Datenansichten, die Teil eines zugewiesenen Produktprofils sind. Produktprofiladministratoren können keine neuen Datenansichten erstellen.

## Zugriff auf Benutzerebene

In der folgenden Tabelle sind die wichtigsten Zugriffsberechtigungen für verschiedene Customer Journey Analytics-Funktionen aufgeführt, die Sie für relevante Benutzer konfigurieren können. Sie können unterschiedliche Benutzerzugriffsebenen über Produktprofile verwalten. Ein Produktprofil kombiniert mehrere Berechtigungen, die Sie dann einzelnen Benutzern oder Benutzergruppen zuweisen können.

Die Registerkarte **[!UICONTROL Berechtigungen]** ist Teil jedes Produktprofils in der Admin Console [3}.](https://adminconsole.adobe.com/enterprise/)

![Admin Console-Berechtigungen](assets/permissions.png)

| Kategorie | Berechtigung | Beschreibung |
| --- | --- | ---|
| [!UICONTROL Datenansichten] | *Name der Datenansicht* | Wenn **[!UICONTROL Auto-Include]** auf **[!UICONTROL Ein]** umgeschaltet wird, können Benutzende, die Teil dieses Produktprofils sind, alle vorhandenen und neu erstellten Datenansichten anzeigen. Wenn diese Einstellung auf **[!UICONTROL Aus]** gesetzt ist, können bestimmte Datenansichten ausgewählt werden, auf die Benutzende Zugriff haben. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Zugriff auf Analysis Workspace] | Benutzer können auf [Analysis Workspace](/help/analysis-workspace/home.md) zugreifen. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL  Geführter Analysezugriff] | Ermöglichen Benutzern den Zugriff auf die [Geführte Analyse](/help/guided-analysis/overview.md). |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Erstellung berechneter Metriken] | Ermöglicht Benutzern das Erstellen von [berechneten Metriken](/help/components/calc-metrics/calc-metr-overview.md). Benutzer können nur die berechneten Metriken, die sie erstellen, löschen, umbenennen, genehmigen oder deren Genehmigung aufheben, oder die für sie freigegebenen berechneten Metriken. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Filter-Erstellung] | Ermöglicht Benutzern das Erstellen von [Filtern](/help/components/filters/filters-overview.md). Benutzer können nur die von ihnen erstellten Filter oder die für sie freigegebenen Filter taggen, freigeben, löschen, umbenennen, genehmigen oder deren Genehmigung aufheben. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Labs-Zugriff] | Benutzer können auf die Registerkarte [Labs](/help/labs/labs.md) im Customer Journey Analytics zugreifen. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Anmerkungserstellung] | Ermöglicht Benutzern das Erstellen von [Anmerkungen](/help/components/annotations/overview.md). Benutzer können nur die Anmerkungen, die sie erstellen, oder für sie freigegebene Anmerkungen taggen, freigeben, löschen und umbenennen. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Zielgruppenerstellung] | Ermöglicht Benutzern das Erstellen von [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Zugriff auf Auditprotokolle] | Erzwingen Sie die Berechtigungsprüfung für die Benutzeroberfläche der [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) und der Prüfprotokolle. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Projektlinks für jedermann freigeben] | Benutzer können [Projekte für alle freigeben.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Prognose] | Ermöglichen Sie Benutzern den Zugriff auf die Funktion [Prognosen](../analysis-workspace/c-forecast/forecasting.md) in Analysis Workspace |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL KI-Assistent: Produktkenntnis] | Ermöglichen Sie Benutzern Zugriff auf den [KI-Assistenten](../ai-assistant.md), um Produktwissen zu erhalten. |
| [!UICONTROL Berichterstellungs-Tools] | [!UICONTROL Intelligente Beschriftungen] | Benutzer können auf [intelligente Beschriftungen](/help/analysis-workspace/visualizations/intelligent-captions.md) zugreifen. |
| [!UICONTROL Tools für die Datenansicht] | [!UICONTROL Vollständiger Tabellenexport] | Benutzer [können vollständige Tabellen in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Tools für die Datenansicht] | [!UICONTROL CJA BI-Erweiterung] | Benutzer können die [BI-Erweiterung](../data-views/bi-extension.md) verwenden. |

{style="table-layout:auto"}

## Workspace-Projektkuratierung

Eine weitere Ebene der Zugriffskontrolle kann auf der Workspace-Berichtsebene verwendet werden. Der Zugriff auf bestimmte Komponenten kann für bestimmte Benutzende eingeschränkt werden. Weitere Informationen zum Eingrenzen von Komponenten (Dimensionen, Metriken, Filter, Datumsbereiche) auf Workspace-Projektebene und dazu, wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden und können sich daher im Customer Journey Analytics ändern. Wenn sie geändert werden, ändert sich auch die Berichterstellung rückwirkend.

## Anwendungsbeispiele

Hier sind einige Anwendungsfälle, die zeigen, wie die Zugriffskontrolle in realen Szenarien eingesetzt werden kann.

### Zugriff durch Dritte

Sie können der Produktprofilverwaltung Zugriff auf einen Teamleiter eines Drittanbieters gewähren, der in Ihrem Unternehmen tätig ist. Dieser Administrator kann diesem Produktprofil Benutzer aus dem Team des Unternehmens hinzufügen. Dieser Produktprofiladministrator kann Zugriff auf bestimmte Datenansichten gewähren und weitere Benutzer innerhalb des Drittanbieters zu diesem Produktprofil hinzufügen. Der Produktprofiladministrator kann Datenansichten ändern, um die Anforderungen des Drittanbieterteams zu erfüllen.

### Zugriffskontrolle auf Zeilenebene

Angenommen, Sie möchten Benutzern Zugriff auf Daten von nur einem Tag gewähren. So könnte der Zugriff auf diese speziellen Zeilen beschränkt werden:

1. Erstellen Sie einen Filter in den [!UICONTROL Einstellungen] einer bestimmten Datenansicht, wobei [!UICONTROL Tag] dem Datum entspricht, an dem sie Datenzugriff haben sollen. Weitere Informationen finden Sie unter [Datenansicht erstellen](/help/data-views/create-dataview.md#settings-filters) .
1. Speichern Sie die Datenansicht, die den Filter auf den Datenbereich der Datensätze in der zugrunde liegenden Verbindung anwendet. Alle Zeilen, die nicht in die Filterdefinition passen, werden automatisch aus der Datenansicht ausgeschlossen und stehen Analysis Workspace bei Verwendung dieser Datenansicht nicht zur Verfügung.
1. Erstellen Sie ein neues [Produktprofil](#product-profile-admin-role) in der Admin Console, fügen Sie Benutzer zum Produktprofil hinzu und schließen Sie nur diese spezifische Datenansicht zum Produktprofil ein.

### Zugriffskontrolle auf Wertebene

Benutzer, die Zugriff auf eine Datenansicht haben, können nur mit den Metriken und Dimensionen arbeiten, die der Administrator in diese Datenansicht aufgenommen hat. Administratoren können die Komponenteneinstellungen [Einschluss-/Ausschlussfunktion](/help/data-views/component-settings/include-exclude-values.md) oder [Wertaufzeichnung](../data-views/component-settings/value-bucketing.md) in Datenansichten verwenden, um bestimmte Dimensionswerte aus einer Datenansicht auszuschließen oder zu aggregieren.

Beispiel: Sie erstellen eine Metrik namens *Hypertonie* in einer Datenansicht aus einer Komponente, die individuelle Patientendaten aus dem Datensatz enthält. Sie verwenden Wertaufschlüsselung, um nur Zugriff auf zusammengefasste Werte zu ermöglichen, sodass Benutzer der Daten die individuellen Patientendaten nicht sehen können.


