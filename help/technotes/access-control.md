---
title: Zugriffssteuerung für Customer Journey Analytics
description: Erfahren Sie, wie Sie die Zugriffskontrolle in Customer Journey Analytics implementieren können.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Zugriffssteuerung für Customer Journey Analytics

Für die Customer Journey Analytics gibt es drei Zugriffsebenen oder drei Benutzerrollen: Produktadministratorrolle, Produktprofil-Administratorrolle und Benutzerzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden in diesem Artikel detailliertere Möglichkeiten zum Beschränken des Zugriffs beschrieben, wie z. B. die Kuratierung und Zeilenebene von Workspace sowie die Zugriffskontrolle auf Wertebene.

## Produktadministrator-Rolle

Benutzern, denen die Rolle &quot;Produktadministrator&quot;zugewiesen wurde, werden standardmäßig die erforderlichen Berechtigungen erteilt, um die meisten Aufgaben innerhalb von Customer Journey Analytics auszuführen. Einige Aufgaben erfordern jedoch zusätzliche Berechtigungen.

So fügen Sie einen Benutzer als Produktadministrator hinzu:

1. Wechseln Sie zur [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Wählen Sie die Registerkarte [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] > [!UICONTROL **Admin hinzufügen**].

   Den von Ihnen hinzugefügten Benutzern werden die Standardberechtigungen [Produkt-Admin](#product-admin-default-permissions) zugewiesen. Sie können ihnen bei Bedarf auch [zusätzliche Berechtigungen](#product-admin-additional-permissions) gewähren.

### Produktadministratorstandardberechtigungen

Produktadministratoren haben die Berechtigung, die meisten Aufgaben innerhalb von Customer Journey Analytics auszuführen.

Produktadministratoren erhalten standardmäßig die erforderlichen Berechtigungen, um die folgenden Aufgaben auszuführen:

* Datenansichten erstellen, aktualisieren und löschen
* Projekte, Filter, berechnete Metriken, Zielgruppen, Anmerkungen oder von anderen Benutzern erstellte Filter aktualisieren und löschen
* Freigeben von Workspace-Projekten für alle Benutzenden
* Berichtaktivität im [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md) verwalten
* [ Vollständige Tabellen exportieren](/help/analysis-workspace/export/export-cloud.md) aus Analysis Workspace

### Zusätzliche Berechtigungen für Produktadministratoren

Zusätzlich zum Hinzufügen als Produktadministrator zum **Customer Journey Analytics-Produktprofil** in der [Admin Console](https://adminconsole.adobe.com/enterprise/) sind zusätzliche Berechtigungen erforderlich, um die folgenden Aufgaben innerhalb von Customer Journey Analytics durchzuführen:

* Daten erstellen, aktualisieren und löschen [Verbindungen](/help/connections/overview.md)

  Um diese Aufgabe durchzuführen, müssen Benutzer Teil eines **Experience Platform-Produktprofils** sein, das über die folgenden Berechtigungen verfügt:
   * Datenmodellierung: Schemas anzeigen, Schemas verwalten
   * Daten-Management: Datensätze anzeigen, Datensätze verwalten
   * Datenaufnahme: Quellen verwalten
   * Anzeigen von Identity-Namespaces

     Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

* Exportieren von Datensätzen in Cloud [Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de)

  Um diese Aufgabe ausführen zu können, benötigen Benutzer die folgenden Experience Platform-Berechtigungen:

   * Verwalten von Zielen
   * Aktivieren von Zielen

     Weitere Informationen zu Berechtigungen für Experience Platform-Ziele finden Sie unter [Ziele - Übersicht](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home).

* Verwenden der [BI-Erweiterung](../data-views/bi-extension.md)

  Damit Benutzer die BI-Erweiterung, einen Produkt-Admin, verwenden können

   * muss sicherstellen, dass die Experience Platform-Berechtigungen für den Benutzer eine Rolle enthalten, die über die Query Service-Ressource mit den Optionen Abfragen verwalten und Query Service-Integration verwalten verfügt. Siehe [Berechtigungen für ein Produktprofil verwalten](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).
   * muss die entsprechenden Customer Journey Analytics-Berechtigungen für den Benutzer sicherstellen:
      * Zugriffsberechtigung auf die entsprechenden Datenansichten. Siehe Datenansichten in den [Customer Journey Analytics-Berechtigungen in Admin Console](#customer-journey-analytics-permissions-in-admin-console).
      * Zugriffsberechtigung auf die CJA BI-Erweiterung. Siehe Datenansichtswerkzeuge in den [Customer Journey Analytics-Berechtigungen in Admin Console](#customer-journey-analytics-permissions-in-admin-console).

## Produktprofil-Administratorrolle

Ein Produktprofil ist ein Satz von Berechtigungen. Produktprofil-Admins können Folgendes:

* Erstellen und verwalten Sie einzelne Produktprofile. Zum Beispiel das Hinzufügen neuer Benutzer oder das Verwalten von Benutzergruppen und den zugehörigen Produktprofilen.

* Bearbeiten Sie in Customer Journey Analytics Datenansichten, die Teil eines von ihnen verwalteten Produktprofils sind. Sie können keine neuen Datenansichten erstellen.

## Zugriff auf Benutzerebene

In der folgenden Matrix werden die wichtigsten Zugriffsberechtigungen für verschiedene Customer Journey Analytics-Funktionen für Nicht-Produktadministratoren und Customer Journey Analytics-Produktadministratoren beschrieben. Anhand dieser Berechtigungen können Benutzer anhand ihrer Rolle und Verantwortlichkeiten innerhalb des Unternehmens effektiv zu navigieren und Customer Journey Analytics zu verwenden.

| Produktfunktionen | Nicht-Produkt-Admins (Benutzer) | Produktadministratoren |
| --- | --- | --- |
| **Datenansichten** | Kann nicht anzeigen/aktualisieren/erstellen/löschen | Kann erstellen/aktualisieren/löschen |
| **Verbindungen** | Kann nicht anzeigen/aktualisieren/erstellen/löschen | Kann erstellen/aktualisieren/löschen |
| **Filter** | Kann erstellen | Kann erstellen |
| **Projekte** | Kann erstellen | Kann erstellen/aktualisieren/löschen |
| **Zielgruppen** | Kann mit speziellen Berechtigungen in Admin Console erstellen | Kann erstellen |
| **Berechnete Metriken** | Kann mit speziellen Berechtigungen in Admin Console erstellen | Kann erstellen |

{style="table-layout:auto"}

## Workspace-Projektkuratierung

Eine weitere Ebene der Zugriffskontrolle kann auf der Workspace-Berichtsebene verwendet werden. Der Zugriff auf bestimmte Komponenten kann für bestimmte Benutzende eingeschränkt werden. Weitere Informationen zum Eingrenzen von Komponenten (Dimensionen, Metriken, Filter, Datumsbereiche) auf Workspace-Projektebene und dazu, wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden und können sich daher im Customer Journey Analytics ändern. Wenn sie geändert werden, ändert sich auch die Berichterstellung rückwirkend.

## Anwendungsbeispiele

Hier sind einige Anwendungsfälle, die zeigen, wie die Zugriffskontrolle in realen Szenarien eingesetzt werden kann.

### Zugriff durch Dritte

Ein Drittanbieter, mit dem Ihr Unternehmen zusammenarbeitet, hat einen Teamleiter, der als Produktprofil-Admin festgelegt werden kann. Dieser Administrator kann diesem Produktprofil Benutzer aus dem Team des Unternehmens hinzufügen. Dieser Admin kann Zugriff auf bestimmte Datenansichten gewähren und andere Benutzende zu diesem Produktprofil hinzufügen. Außerdem können sie die Datenansichten, über die sie die Kontrolle haben, an die Anforderungen ihrer Teams anpassen.

### Zugriffskontrolle auf Zeilenebene

Angenommen, die Benutzenden sollen nur auf die Daten eines bestimmten Tages zugreifen können. So könnte der Zugriff auf diese speziellen Zeilen beschränkt werden:

1. Erstellen Sie einen Filter in der Customer Journey Analytics, bei dem **[!UICONTROL Tag]** dem Datum entspricht, zu dem sie Datenzugriff haben sollen.
1. Fügen Sie in [!UICONTROL Datenansichten] > [!UICONTROL Einstellungen] den Filter zu der Datenansicht hinzu.
1. Wenn Sie nun die Datenansicht speichern, wird der Filter automatisch auf den Datensatz angewendet. Alle Zeilen, die nicht der Filterdefinition entsprechen, werden jetzt automatisch aus der bearbeiteten Datenansicht ausgeschlossen.
1. Erstellen Sie ein neues Produktprofil in der Admin Console, fügen Sie Benutzende hinzu und beschränken Sie deren Zugriff auf diese Datenansicht.

### Zugriffskontrolle auf Wertebene

Benutzende, die Zugriff auf eine Datenansicht haben, können nur mit den Metriken und Dimensionen arbeiten, die vom Admin in diese Datenansicht aufgenommen worden sind. Admins können die [Funktion zum Ein- oder Ausschließen](/help/data-views/component-settings/include-exclude-values.md) in Datenansichten verwenden, um beispielsweise bestimmte Dimensionswerte aus einer Datenansicht auszuschließen.

Hier ist ein Beispiel aus dem Gesundheitswesen: Angenommen, in einer Datenansicht wird eine Metrik mit der Bezeichnung „Hypertonie“ aus einem Datensatz erstellt, der diese Daten enthält. Die Tatsache, dass es sich um eine Metrik handelt, ermöglicht es, den aggregierten Wert dieser Metrik zu sehen, aber nicht die einzelnen Patientinnen und Patienten, die unter diese Metrik fallen.

## Customer Journey Analytics-Berechtigungen in Admin Console

Die Registerkarte **[!UICONTROL Berechtigungen]** ist Teil jedes Produktprofils in [Admin Console](https://adminconsole.adobe.com/enterprise/). Benutzende können zu bestimmten Produktprofilen hinzugefügt werden. Anschließend werden Rechte für bestimmte Datenansichten zugewiesen und festgelegt, welche Berechtigungen die Benutzenden in einem Produktprofil haben. Im Folgenden finden Sie die Customer Journey Analytics-spezifischen Berechtigungen:

![Admin Console-Berechtigungen](assets/permissions.png)

| Berechtigung | Definition |
| --- | --- |
| **[!UICONTROL Datenansichten]** | Wenn **[!UICONTROL Auto-Include]** auf **[!UICONTROL Ein]** umgeschaltet wird, können Benutzende, die Teil dieses Produktprofils sind, alle vorhandenen und neu erstellten Datenansichten anzeigen. Wenn diese Einstellung auf **[!UICONTROL Aus]** gesetzt ist, können bestimmte Datenansichten ausgewählt werden, auf die Benutzende Zugriff haben. |
| **[!UICONTROL Reporting-Tools]**: |   |
| **[!UICONTROL Zugriff auf Auditprotokolle]** | Diese Berechtigung erzwingt die Berechtigungsprüfung für die [API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) und die Benutzeroberfläche für Administratorprotokolle. |
| **[!UICONTROL Zugriff auf Analysis Workspace]** | Ermöglicht Benutzern den Zugriff auf Analysis Workspace unter Customer Journey Analytics. |
| [!UICONTROL **Geführter Analysezugriff**] | Ermöglicht Benutzern das Erstellen von [geführten Analyseprojekten](/help/guided-analysis/overview.md). |
| [!UICONTROL **Prognose**] | Ermöglichen des Zugriffs auf die Prognosefunktion in Analysis Workspace |
| **[!UICONTROL Verwaltung der Reporting-Nutzung]** | Ermöglichen Benutzern das Anzeigen und Löschen von Berichten, die in ihrem Unternehmen ausgeführt werden. |
| **[!UICONTROL Anzeige der Reporting-Nutzung]** | Ermöglicht Benutzern das Anzeigen aller gleichzeitigen Berichtsanforderungen. |
| [!UICONTROL **Vollständiger Tabellenexport**] | Benutzer [können vollständige Tabellen in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Erstellung berechneter Metriken]** | Ermöglicht Benutzern das Erstellen von [berechneten Metriken](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter-Erstellung]** | Ermöglicht Benutzern das Erstellen von [Filtern](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs-Zugriff]** | Benutzer können auf die Registerkarte [Labs](/help/labs/labs.md) im Customer Journey Analytics zugreifen. |
| **[!UICONTROL Anmerkungserstellung]** | Ermöglicht Benutzern das Erstellen von [Anmerkungen](/help/components/annotations/overview.md). |
| **[!UICONTROL Zielgruppenerstellung]** | Ermöglicht Benutzern das Erstellen von [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Zielgruppenansicht]** | Benutzer können [Zielgruppen](/help/components/audiences/audiences-overview.md) anzeigen. |
| [!UICONTROL **Projektlinks für jedermann freigeben**] | Benutzer können [Projekte für alle freigeben.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL Tools für die Datenansicht]**: |   |
| [!UICONTROL **Vollständiger Tabellenexport**] | Benutzer [können vollständige Tabellen in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL [!UICONTROL CJA BI-Erweiterung]]** | Benutzer können die [BI-Erweiterung](../data-views/bi-extension.md) verwenden. |

{style="table-layout:auto"}
