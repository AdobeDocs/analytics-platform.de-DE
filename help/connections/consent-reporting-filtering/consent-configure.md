---
title: Konfigurieren von Einverständnisberichten und -filtern
description: Erfahren Sie, wie Sie mit dem Bereitstellungsassistenten Einverständnisberichte und optionale Aufnahmezeitfilter für eine Verbindung in Customer Journey Analytics aktivieren können.
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
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 2%

---

# Konfigurieren von Einverständnisberichten und -filtern

Systemadministratoren können die Einverständnisberichterstattung und optional die Einverständnisfilterung für eine oder mehrere Verbindungen aktivieren. Übersichtsinformationen finden Sie unter [Übersicht über Einverständnisberichte und -filter](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>Die Einverständnisfilterung schließt Besucherdaten aus, die zum Zeitpunkt der Aufnahme keine Zustimmung erteilt haben. Daten, die durch Filtern ausgeschlossen werden, werden nicht in Customer Journey Analytics gespeichert und können nicht für frühere Datumsangaben wiederhergestellt werden. Überprüfen Sie die Auswahl Ihrer Marketing-Aktionen sorgfältig, bevor Sie die Filterung aktivieren.

## Erstellen einer Konfiguration

Wenn Sie eine Konfiguration für das Reporting und die Filterung von Einverständnissen erstellen, wählen Sie die Sandbox und den Profildatensatz aus, die Ihre Einverständnisrichtlinien-Mitgliedschaftsdaten enthalten, wählen Sie die zu konfigurierende Verbindung bzw. die zu konfigurierenden Verbindungen aus und wählen Sie aus, ob die Daten für jede Marketing-Aktion gefiltert werden sollen. Customer Journey Analytics erstellt dann automatisch den Einverständnisrichtlinien-Lookup-Datensatz und die Einverständnisrichtlinien-Komponenten.

So erstellen Sie eine Reporting- und Filterkonfiguration für Einverständnisse:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Einverständnisberichte und -filter]** aus.

1. Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus.

1. Geben **[!UICONTROL im Abschnitt]** die folgenden Informationen an:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Name]** | Geben Sie einen Namen für die Konfiguration an. |
   | **[!UICONTROL Sandbox]** | Wählen Sie die Experience Platform-Sandbox aus, die den Profildatensatz mit den Mitgliedschaftsdaten Ihrer Einverständnisrichtlinie enthält. <p>Pro Sandbox ist maximal ein Einverständnisrichtlinien-Lookup-Datensatz vorhanden. Mehrere Konfigurationen in derselben Sandbox verwenden denselben Lookup-Datensatz.</p> |

1. Wählen Sie **[!UICONTROL Abschnitt]** Profildatensatz) den Profildatensatz aus, der die Einverständnisrichtlinien-Mitgliedschaftsdaten enthält (das `consentPoliciesIDMap` Feld), zu dem Sie einen Bericht erstellen möchten. Wenn Sie die Einverständnisberichterstattung aktivieren, wird dieser Profildatensatz zu der von Ihnen ausgewählten Verbindung hinzugefügt, sofern er nicht bereits Teil davon ist.

1. Wählen Sie im **[!UICONTROL Verbindung]** die Option **[!UICONTROL Verbindung auswählen]**, aktivieren Sie das Kontrollkästchen neben einer oder mehreren zu konfigurierenden Verbindungen und klicken Sie dann auf **[!UICONTROL Verbindung verwenden]**.

   Einverständnisberichte und -filter werden auf Verbindungsebene angewendet. Alle Datenansichten unter einer konfigurierten Verbindung übernehmen dasselbe Verhalten.

1. Klicken **[!UICONTROL Abschnitt „Datenansichten]** auf **[!UICONTROL Datenansichten auswählen]**.

1. Aktivieren Sie im Dialogfeld Datenansichten das Kontrollkästchen neben einer oder mehreren Datenansichten, die Sie für das Einverständnisbericht verwenden möchten. Diese Datenansichten werden automatisch mit Experience Platform-Einverständnisdaten für das Reporting konfiguriert.

1. Wählen **[!UICONTROL Datenansichten verwenden]** aus.

1. (Optional) Im Abschnitt **[!UICONTROL Filtern]** können Sie die Filterung für die folgenden Marketing-Aktionen aktivieren:

   >[!NOTE]
   >
   >Wenn die Filterung nach einer Marketing-Aktion aktiviert ist, nimmt Customer Journey Analytics die Daten eines Besuchers nur dann auf, wenn der Besucher mit **allen** Einverständnisrichtlinien übereinstimmt, die für diese Marketing-Aktion gelten. Weitere Informationen finden Sie unter [Einverständnisfilter](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) in [Übersicht über Einverständnisberichte und -filter](/help/connections/consent-reporting-filtering/consent-overview.md).

   | Marketing-Aktion | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Filtern von Daten, die für standardmäßige Customer Journey Analytics-Berichte in Analysis Workspace verwendet werden. |
   | **[!UICONTROL Datenwissenschaft]** | Filtern Sie Daten, die für erweiterte Analysen, maschinelles Lernen und datenwissenschaftliche Anwendungsfälle verwendet werden. |

1. Wählen **[!UICONTROL Erstellen]** aus, um die Konfiguration zu erstellen.

   Wenn Sie die Berichterstellung aktiviert haben, wird Customer Journey Analytics automatisch:

   * Fügt den ausgewählten Profildatensatz zur Verbindung hinzu.
   * Erstellt einen Einverständnisrichtlinien-Lookup-Datensatz für die Sandbox (sofern noch nicht vorhanden) und synchronisiert Richtliniennamen und Beschreibungen aus Experience Platform.
   * Fügt die Komponenten der Einverständnisrichtlinie (Dimensionen, Metriken und ein abgeleitetes Feld) zu den Datenansichten innerhalb der konfigurierten Verbindung hinzu.

1. Sehen Sie sich nach Abschluss [&#x200B; Konfiguration die Komponenten der Einverständnisrichtlinie in der Datenansicht an](#view-consent-policy-components-in-the-data-view) um sicherzustellen, dass sie verfügbar sind.

## Anzeigen von Einverständnisrichtlinien-Komponenten in der Datenansicht

Nachdem Sie [Konfiguration erstellt haben](#create-a-configuration) können Sie überprüfen, ob die Komponenten der Einverständnisrichtlinie zu den Datenansichten unter der konfigurierten Verbindung hinzugefügt wurden.

Um die Komponenten der Einverständnisrichtlinie in der Datenansicht anzuzeigen, müssen Sie Produktprofiladministrator für das Produktprofil sein, dem die Datenansicht zugewiesen ist. Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md).

So zeigen Sie die Komponenten der Einverständnisrichtlinie in der Datenansicht an:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Datenansichten]** aus.

1. Öffnen Sie eine Datenansicht, die mit der konfigurierten Verbindung verknüpft ist.

1. Im Abschnitt **[!UICONTROL Dimensionen]** sollten jetzt die folgenden Dimensionen verfügbar sein:

   * **[!UICONTROL Einverständnisrichtlinien-ID]**

   * **[!UICONTROL Richtlinienname]**

   * **[!UICONTROL Richtlinienbeschreibung]**

1. Im Abschnitt **[!UICONTROL Metriken]** sollten jetzt die folgenden Metriken verfügbar sein:

   * **[!UICONTROL Besucher mit Einverständnis]**

   * **[!UICONTROL Ereignisse mit Einverständnis]**

   * **[!UICONTROL Eindeutige Einverständnisrichtlinien]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Verwenden Sie die Komponenten der Einverständnisrichtlinie in Analysis Workspace.

   Benutzende, die Zugriff auf die Datenansicht in Analysis Workspace haben, können nun die neuen Komponenten sehen und in ihren Analysen verwenden. Informationen zur Verwendung der Einverständnisrichtlinien-Komponenten in Analysis Workspace finden Sie unter [Analysieren von Einverständnisrichtlinien-Daten](/help/connections/consent-reporting-filtering/consent-analyze.md).
