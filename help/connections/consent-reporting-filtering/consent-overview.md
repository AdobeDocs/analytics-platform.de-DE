---
title: Übersicht über Einverständnisberichte und -filter
description: Erfahren Sie, wie Sie Berichte über die Zugehörigkeit zu einer Besuchereinverständnisrichtlinie erstellen und nicht einwilligende Besucher zur Aufnahmezeit in Customer Journey Analytics filtern.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 990
ht-degree: 2%

---

# Übersicht über das Reporting und die Filterung von Einverständnissen

Einverständnisberichte und -filter verwenden die in Ihren Adobe Experience Platform-Profildatensätzen gespeicherten Einverständnisrichtlinien-Mitgliedschaftsdaten, um Ihnen dabei zu helfen, Berichte über das Einverständnis der Besuchenden zu erstellen und optional nicht einverstandene Besuchende auszuschließen, bevor ihre Daten in Customer Journey Analytics aufgenommen werden.

Das folgende Diagramm und die zugehörige Tabelle zeigen eine allgemeine Darstellung davon, wie durch Einverständnisberichte und -filterung Einverständnisrichtliniendaten in Analysis Workspace verfügbar gemacht und Besucherdaten zum Zeitpunkt der Aufnahme gefiltert werden:

![Übersicht über Einverständnisberichte und -filter](assets/consent-overview.png)

| Nummer | Funktion | Funktion |
|---------|----------|---------|
| 1 | Konfiguration des Einverständnisberichts und der Filterung | Die Konfigurationsschnittstelle in Customer Journey Analytics, die zum Aktivieren der Einverständnisberichterstattung und optional zum Filtern des Einverständnisses verwendet wird. |
| 2 | Sandbox | Muss den Profildatensatz enthalten, der die Einverständnisrichtlinien-Mitgliedschaftsdaten enthält, zu denen Sie einen Bericht erstellen möchten. |
| 3 | Profildatensatz | Enthält die Daten zur Einverständnisrichtlinien-Mitgliedschaft für jeden Besucher. Die Zugehörigkeit zu einer Einverständnisrichtlinie wird im `consentPoliciesIDMap` Feld eines Profildatensatzes gespeichert. Dieser Profildatensatz wird der ausgewählten Verbindung hinzugefügt. <p>Das Profil jedes Besuchers listet die Einverständnisrichtlinien auf, denen der Besucher entspricht. Customer Journey Analytics liest dieses Feld, um Einverständnisrichtlinien für das Reporting verfügbar zu machen und zu bewerten, welche Besucherinnen und Besucher während der Aufnahme einbezogen werden sollen.</p> |
| 4 | Datensatz für die Suche nach Einverständnisrichtlinien | Stellt benutzerfreundliche Richtliniennamen und Beschreibungen für das Reporting bereit. Der Lookup-Datensatz wird automatisch erstellt und mit Experience Platform synchronisiert. Pro Sandbox ist maximal ein Einverständnisrichtlinien-Lookup-Datensatz vorhanden. |
| 5 | Verbindung | Die Verbindung, in der Einverständnisberichte und -filter angewendet werden. Alle Datenansichten unter der Verbindung übernehmen die Konfiguration. |
| 6 | Komponenten der Einverständnisrichtlinie | Neue Dimensionen, Metriken und ein abgeleitetes Feld, die die Zugehörigkeit zu einer Einverständnisrichtlinie darstellen. Diese Komponenten werden automatisch erstellt und stehen für das Reporting in Analysis Workspace zur Verfügung. |
| 7 | Filterung der Aufnahmezeit | Wenn der Filter aktiviert ist, werden Besucher, die nicht zustimmen, während der Aufnahme ausgeschlossen, basierend auf den von Ihnen konfigurierten Marketing-Aktionen. |

## Einverständnis-Reporting vs. Filterung

Einverständnisberichte und -filterung sind zwei separate Funktionen. Sie können die Einverständnisberichterstattung selbst aktivieren oder sowohl das Reporting als auch das Filtern gemeinsam aktivieren.

### Einverständnisberichte

Wenn Sie die Einverständnisberichterstattung aktivieren, fügt Customer Journey Analytics den Datenansichten unter der konfigurierten Verbindung einen Satz von Einverständnisrichtlinien-Komponenten hinzu. Mit diesen Komponenten können Sie mithilfe der Mitgliedschaftsdaten zu Einverständnisrichtlinien in Ihren Experience Platform-Profildatensätzen in Analysis Workspace berichten, welche Besucher mit den verschiedenen Einverständnisrichtlinien übereinstimmen.

Damit Berichte lesbar bleiben, synchronisiert Customer Journey Analytics Richtliniennamen und Beschreibungen aus Experience Platform in einen Einverständnisrichtlinien-Suchdatensatz. Wenn eine Richtlinie in Experience Platform erstellt, aktualisiert, umbenannt oder gelöscht wird, wird der Lookup-Datensatz automatisch aktualisiert.

Informationen zu den Komponenten, die durch Einverständnisberichte erstellt werden, finden Sie unter [Analysieren von Einverständnisrichtliniendaten](/help/connections/consent-reporting-filtering/consent-analyze.md).

### Einverständnisfilterung

>[!IMPORTANT]
>
>Ausgefilterte (ausgeschlossene) Einverständnisdaten werden nicht in Customer Journey Analytics gespeichert und können nicht für frühere Datumsangaben wiederhergestellt werden, indem die Konfiguration aktualisiert wird.

Wenn Sie die Einverständnisfilterung aktivieren, schließt Customer Journey Analytics Besucher, die nicht einverstanden sind, zum Zeitpunkt der Aufnahme aus. Da die Filterung zum Zeitpunkt der Aufnahme erfolgt, treten die Daten für ausgeschlossene Besucher nie in Customer Journey Analytics ein und sind nicht für das Reporting verfügbar.

Beachten Sie bei der Verwendung der Einverständnisfilterung Folgendes:

* Customer Journey Analytics bestimmt die Einverständnisrichtlinien, die für die von Ihnen konfigurierten Marketing-Aktionen gelten.

  Eine Marketing-Aktion stellt eine Kategorie der Datennutzung dar. Customer Journey Analytics bestimmt, welche Einverständnisrichtlinien für jede Marketing-Aktion gelten, und Sie aktivieren die Filterung für jede Marketing-Aktion unabhängig, wenn Sie [Ihre Konfiguration erstellen](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration).

  | Marketing-Aktion | Beschreibung |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Standard-Customer Journey Analytics-Reporting in Analysis Workspace. |
  | **[!UICONTROL Datenwissenschaft]** | Anwendungsfälle für erweiterte Analysen, maschinelles Lernen und Datenwissenschaft. |

* Die Daten eines Besuchers werden nur dann aufgenommen, wenn der Besucher den **Einverständnisrichtlinien**. Wenn einem Besucher eine anwendbare Richtlinie fehlt, werden die Daten dieses Besuchers ausgeschlossen.

## Konfigurieren von Einverständnisberichten und -filtern

Wenn Sie das Reporting und die Filterung von Einverständnissen konfigurieren, wählen Sie die Sandbox und den Profildatensatz aus, die Ihre Einverständnisrichtlinien-Mitgliedschaftsdaten enthalten, wählen Sie die zu konfigurierende Verbindung bzw. die zu konfigurierenden Verbindungen aus und wählen Sie aus, ob die Daten für jede Marketing-Aktion gefiltert werden sollen. Customer Journey Analytics erstellt dann automatisch den Einverständnisrichtlinien-Lookup-Datensatz und die Einverständnisrichtlinien-Komponenten.

Weitere Informationen finden Sie unter [Konfigurieren von Einverständnisberichten und -filterung](/help/connections/consent-reporting-filtering/consent-configure.md).

## Konfigurieren von Einverständnisberichten und -filtern

Sie können Einverständnisberichte und Filterkonfigurationen verwalten, nachdem sie erstellt wurden. Sie können Konfigurationen anzeigen, bearbeiten und löschen.

Informationen zum Verwalten vorhandener Konfigurationen finden Sie unter [Verwalten von Einverständnisberichten und Filterkonfigurationen](/help/connections/consent-reporting-filtering/consent-manage.md).

## Analysieren von Einverständnisrichtliniendaten

Wenn Einverständnisrichtlinien-Daten in Customer Journey Analytics verfügbar sind, können Sie Berichte dazu erstellen, welche Besucherinnen und Besucher mit welchen Einverständnisrichtlinien übereinstimmen, und diese insight verwenden, um Einverständniszielgruppen in allen Ihren Berichten zu verstehen.

Weitere Informationen finden Sie unter [Analysieren von Einverständnisrichtliniendaten](/help/connections/consent-reporting-filtering/consent-analyze.md).

## Rollen- und Berechtigungsanforderungen für Einverständnisberichte und -filter

Die folgenden Customer Journey Analytics-Rollen und Experience Platform-Berechtigungen sind für das Reporting und die Filterung von Einverständnissen erforderlich:

| Funktion | Anforderungen an Customer Journey Analytics-Rollen oder -Berechtigungen | Experience Platform-Berechtigungsanforderungen |
|---------|----------|----------|
| [Erstellen von Reporting- und Filterkonfigurationen für Einverständnisse](/help/connections/consent-reporting-filtering/consent-configure.md) | Systemadministrator | <ul><li>Datensätze: lesen, schreiben</li><li>Schemata: Lesen, Schreiben</li></ul> <p>Für den Profildatensatz, der die Daten zur Einverständnisrichtlinien-Mitgliedschaft enthält, ist Lesezugriff erforderlich. Schreibzugriff ist erforderlich, da ein Einverständnisrichtlinien-Lookup-Datensatz erstellt und synchronisiert wird.</p> |
| Anzeigen von Einverständnisrichtlinien-Komponenten in der Datenansicht | Produktprofil-Administrator für das Produktprofil, dem die Datenansicht zugewiesen ist <p>Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md).</p> | k. A. |
| Verwenden von Einverständnisrichtlinien-Komponenten in Analysis Workspace | Zugriff auf eine Datenansicht, in der die Komponenten der Einverständnisrichtlinie hinzugefügt wurden | k. A. |

## Anwendungsfälle für Einverständnisberichte und -filterung

Anwendungsfälle, die den Wert des Einverständnisberichts und der -filterung hervorheben, finden Sie unter [Einverständnisberichte und -filterung](/help/connections/consent-reporting-filtering/consent-use-cases.md).

## Grenzwerte für Einverständnisberichte und -filter

Beachten Sie die folgenden Einschränkungen beim [Konfigurieren von Einverständnisberichten und -filtern](/help/connections/consent-reporting-filtering/consent-configure.md):

* Eine einzelne Sandbox kann nur über einen einzigen Einverständnisrichtlinien-Lookup-Datensatz verfügen. Mehrere Konfigurationen in derselben Sandbox teilen diesen Lookup-Datensatz.

* Eine Verbindung kann nur einer einzigen Reporting- und Filterkonfiguration für Einverständnis zugeordnet werden.
