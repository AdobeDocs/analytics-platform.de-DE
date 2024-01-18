---
title: Zugriffssteuerung für Customer Journey Analytics
description: Erfahren Sie, wie Sie die Zugriffskontrolle in Customer Journey Analytics implementieren können.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: ae968e46c5822c9209ecf78735df0914f33cb0d2
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 61%

---

# Zugriffssteuerung für Customer Journey Analytics

Customer Journey Analytics wird durch drei Zugriffsebenen oder drei Rollen gesteuert: Produktadministratorrolle, Produktprofil-Administratorrolle und Benutzerzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden granulare Möglichkeiten zur Einschränkung des Zugriffs behandelt, beispielsweise die Workspace-Kuratierung und die Zugriffskontrolle auf Zeilen- und Werteebene.

## Produktadministrator-Rolle

Benutzern, denen die Rolle &quot;Produktadministrator&quot;zugewiesen wurde, werden standardmäßig die erforderlichen Berechtigungen erteilt, um die meisten Aufgaben innerhalb von Customer Journey Analytics auszuführen. Einige Aufgaben erfordern jedoch zusätzliche Berechtigungen.

So fügen Sie einen Benutzer als Produktadministrator hinzu:

1. Navigieren Sie zu [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Auswählen [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administratoren**] tab > [!UICONTROL **Admin hinzufügen**].

   Den Benutzern, die Sie hinzugefügt haben, wird die [Produktadministratorstandardberechtigungen](#product-admin-default-permissions). Sie können sie auch [zusätzliche Berechtigungen](#product-admin-additional-permissions) bei Bedarf.

### Produktadministratorstandardberechtigungen

Produktadministratoren haben die Berechtigung, die meisten Aufgaben innerhalb von Customer Journey Analytics auszuführen.

Produktadministratoren erhalten standardmäßig die erforderlichen Berechtigungen, um die folgenden Aufgaben auszuführen:

* Datenansichten erstellen, aktualisieren und löschen
* Projekte, Filter, berechnete Metriken, Zielgruppen, Anmerkungen oder von anderen Benutzern erstellte Filter aktualisieren und löschen
* Freigeben von Workspace-Projekten für alle Benutzenden
* Berichtaktivität im [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)

### Zusätzliche Berechtigungen für Produktadministratoren

Zusätzlich dazu, als Produkt-Admin im **Customer Journey Analytics-Produktprofil** im [Admin Console](https://adminconsole.adobe.com/enterprise/), sind zusätzliche Berechtigungen erforderlich, um die folgenden Aufgaben innerhalb von Customer Journey Analytics durchzuführen:

* Erstellen, Aktualisieren und Löschen von Daten [Verbindungen](/help/connections/overview.md)

  Um diese Aufgabe ausführen zu können, müssen Benutzer Teil eines **Experience Platform-Produktprofil** , der die folgenden Berechtigungen bereitstellt:
   * Datenmodellierung: Schemas anzeigen, Schemas verwalten
   * Daten-Management: Datensätze anzeigen, Datensätze verwalten
   * Datenaufnahme: Quellen verwalten
   * Anzeigen von Identity-Namespaces

     Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

* Exportieren von Datensätzen in Cloud [Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de)

  >[!AVAILABILITY]
  >
  >Die Möglichkeit, Datensätze in die Cloud zu exportieren, befindet sich in der eingeschränkten Testphase der Veröffentlichung und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Informationen zum Customer Journey Analytics-Veröffentlichungsprozess finden Sie unter [Customer Journey Analytics-Funktionsveröffentlichungen](/help/release-notes/releases.md).

  Um diese Aufgabe ausführen zu können, benötigen Benutzer außerdem die folgenden Experience Platform-Berechtigungen:
   * Verwalten von Zielen
   * Aktivieren von Zielen

     Weitere Informationen zu Berechtigungen für Experience Platform-Ziele finden Sie unter [Ziele - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=en#access-controls).

## Produktprofil-Administratorrolle

Ein Produktprofil ist ein Satz von Berechtigungen. Produktprofil-Admins können Folgendes:

* Individuelle Produktprofile erstellen und verwalten, beispielsweise neue Benutzende hinzufügen oder Benutzergruppen und ihre zugehörigen Produktprofile verwalten.

* Bearbeiten Sie in Customer Journey Analytics Datenansichten, die Teil eines von ihnen verwalteten Produktprofils sind. Sie können keine neuen Datenansichten erstellen.

## Zugriff auf Benutzerebene

Benutzende in Customer Journey Analytics können keine Datenansichten oder Verbindungen erstellen, bearbeiten oder anzeigen. Anwender können in Admin Console Filter, Projekte, Zielgruppen und berechnete Metriken mit speziellen Berechtigungen erstellen.

## Workspace-Projektkuratierung

Eine weitere Ebene der Zugriffskontrolle kann auf der Workspace-Berichtsebene verwendet werden. Der Zugriff auf bestimmte Komponenten kann für bestimmte Benutzende eingeschränkt werden. Weitere Informationen zum Eingrenzen von Komponenten (Dimensionen, Metriken, Filter, Datumsbereiche) auf Workspace-Projektebene und dazu, wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) und können sich daher im Customer Journey Analytics ändern. Wenn sie geändert werden, ändert sich auch die Berichterstellung rückwirkend.

## Anwendungsbeispiele

Hier sind einige Anwendungsfälle, die zeigen, wie die Zugriffskontrolle in realen Szenarien eingesetzt werden kann.

### Zugriff durch Dritte

Ein Drittanbieter, mit dem Ihr Unternehmen zusammenarbeitet, hat einen Teamleiter, der als Produktprofil-Admin festgelegt werden kann. Dieser Admin kann diesem Produktprofil dann Benutzende seines Teams hinzufügen. Dieser Admin kann Zugriff auf bestimmte Datenansichten gewähren und andere Benutzende zu diesem Produktprofil hinzufügen. Außerdem können sie die Datenansichten, über die sie die Kontrolle haben, an die Anforderungen ihrer Teams anpassen.

### Zugriffskontrolle auf Zeilenebene

Angenommen, die Benutzenden sollen nur auf die Daten eines bestimmten Tages zugreifen können. So könnte der Zugriff auf diese speziellen Zeilen beschränkt werden:

1. Erstellen Sie einen Filter auf einer Customer Journey Analytics, wobei **[!UICONTROL Tag]** entspricht dem Datum, auf das Sie Datenzugriff haben möchten.
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
| **[!UICONTROL Zugriff auf Auditprotokolle]** | Diese Berechtigung erzwingt die Berechtigungsprüfung für die [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) und die Benutzeroberfläche für Administratorprotokolle. |
| **[!UICONTROL Verwaltung der Reporting-Nutzung]** | Ermöglicht Benutzenden das Anzeigen und Löschen aller in ihrem Unternehmen laufenden Berichte. |
| **[!UICONTROL Anzeige der Reporting-Nutzung]** | Ermöglicht Benutzenden die Anzeige aller gleichzeitigen Berichtsanfragen. |
| [!UICONTROL **Vollständiger Tabellenexport**] | Ermöglicht Benutzern [vollständige Tabellen in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Erstellung berechneter Metriken]** | Ermöglicht Benutzenden die Erstellung von [berechneten Metriken](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter-Erstellung]** | Ermöglicht Benutzenden die Erstellung von [Filtern](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs-Zugriff]** | Ermöglicht Benutzern den Zugriff auf [Labs](/help/labs/labs.md) Registerkarte in Customer Journey Analytics. |
| **[!UICONTROL Anmerkungserstellung]** | Ermöglicht Benutzenden das Erstellen von [Anmerkungen](/help/components/annotations/overview.md). |
| **[!UICONTROL Zielgruppenerstellung]** | Ermöglicht Benutzenden das Erstellen von [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Zielgruppenansicht]** | Ermöglicht Benutzenden die Ansicht von [Zielgruppen](/help/components/audiences/audiences-overview.md). |

{style="table-layout:auto"}
