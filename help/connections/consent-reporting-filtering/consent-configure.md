---
title: Konfigurieren von Einverständnisberichten und -filtern
description: Erfahren Sie, wie Sie in Customer Journey Analytics eine Konfiguration erstellen, um die Einverständnisberichterstattung und die optionale Aufnahmezeitfilterung für eine Verbindung zu aktivieren.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
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
source-git-commit: 4661a066f90991e6fb149c6909ef4a9f75cf02ac
workflow-type: tm+mt
source-wordcount: 1326
ht-degree: 11%

---

# Konfigurieren von Einverständnisberichten und -filtern {#configure-consent-reporting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-merge-policy"
>title="Zusammenführungsrichtlinie"
>abstract="Zusammenführungsrichtlinien kombinieren Profildaten aus mehreren Datensätzen zu einheitlichen Kundenprofilen, die für die Erstellung von Zielgruppen verwendet werden. Wählen Sie die Zusammenführungsrichtlinie aus, die dem Profildatensatz entspricht, der die Einverständnisrichtlinien-Mitgliedschaftsdaten enthält (das `consentPoliciesIDMap` Feld), über die Sie einen Bericht erstellen möchten. Sie können sich auch an Ihr Daten-Team wenden, um zu erfahren, welche Zielgruppen den jeweiligen Zusammenführungsrichtlinien zugeordnet sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-sandbox"
>title="Sandbox"
>abstract="Wählen Sie die Sandbox aus, die die korrekten Experience Platform-Profildatensätze enthält. Diese Datensätze müssen die Einverständnisdaten enthalten, zu denen Sie in Analysis Workspace einen Bericht erstellen möchten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-person-id"
>title="Personen-ID"
>abstract="Wählen Sie ein Feld aus dem modellbasierten Schema aus, das die Personen-ID darstellt. Die Auswahl ist auf die Liste der Felder im Schema beschränkt, die als „Identität“ markiert sind und keinen Identity-Namespace haben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-identity-namespace"
>title="Primären Identity-Namespace verwenden"
>abstract="Aktivieren Sie diese Option, wenn Customer Journey Analytics die Identität in der Identitätszuordnung finden soll, die mit dem Attribut primary=true gekennzeichnet ist, und diese Identität als Personen-ID für diese Zeile verwendet. Diese Identität ist der Primärschlüssel, der in Experience Platform für die Partitionierung verwendet wird. <br/>Wenn Sie diese Option deaktiviert lassen, wählen Sie im Feld „Identity-Namespace“ weiter unten einen Namespace aus. Customer Journey Analytics durchsucht die Identitätszuordnung jeder Zeile nach diesem Namespace-Schlüssel und verwendet die unter diesem Namespace aufgeführte Identität als Personen-ID für die jeweilige Zeile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-reporting"
>title="Reporting aktivieren"
>abstract="Aktivieren Sie diese Option, um mit Analysis Workspace Berichte zu den in Ihrer Verbindung verfügbaren Einverständnisdaten zu erstellen. Dimensionen und Metriken der Einverständnisrichtlinie werden zu den von Ihnen ausgewählten Datenansichten hinzugefügt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-filtering"
>title="Filter aktivieren"
>abstract="Aktivieren Sie diese Option, um Besucherdaten, die nicht mit dem Einverständnis des Benutzers übereinstimmen, von der Aufnahme in Customer Journey Analytics auszuschließen. Wenn diese Option aktiviert ist, werden die Daten eines Besuchers nur dann aufgenommen, wenn der Besucher allen unten aktivierten Einverständnisrichtlinien entspricht. <br>Diese Option richtet sich an Organisationen, die nicht einverständnispflichtige Besucherdaten zum Zeitpunkt der Aufnahme ausschließen müssen."

<!-- markdownlint-enable MD034 -->

Systemadministratoren können die Einverständnisberichterstattung und optional die Einverständnisfilterung für eine oder mehrere Verbindungen aktivieren. Übersichtsinformationen finden Sie unter [Übersicht über Einverständnisberichte und -filter](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>Die Einverständnisfilterung schließt Besucherdaten aus, die zum Zeitpunkt der Aufnahme keine Zustimmung erteilt haben. Daten, die durch Filtern ausgeschlossen werden, werden nicht in Customer Journey Analytics gespeichert und können nicht für frühere Datumsangaben wiederhergestellt werden. Überprüfen Sie die Auswahl Ihrer Marketing-Aktionen sorgfältig, bevor Sie die Filterung aktivieren.

## Erstellen einer Konfiguration

Wenn Sie eine Konfiguration für das Reporting und die Filterung von Einverständnissen erstellen, wählen Sie die Sandbox und die Zusammenführungsrichtlinie aus, die Ihre Mitgliedschaftsdaten für die Einverständnisrichtlinie enthalten, wählen Sie die zu konfigurierende Verbindung bzw. die zu konfigurierenden Verbindungen aus und wählen Sie aus, ob die Daten für jede Marketing-Aktion gefiltert werden sollen. Customer Journey Analytics erstellt dann automatisch den Einverständnisrichtlinien-Lookup-Datensatz und die Einverständnisrichtlinien-Komponenten.

So erstellen Sie eine Reporting- und Filterkonfiguration für Einverständnisse:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Einverständnisberichte und -filter]** aus.

1. Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus.

   ![Einverständniskonfigurationsseite](assets/consent-configure.png)

1. Geben **[!UICONTROL im Abschnitt]** die folgenden Informationen an:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Name]** | Geben Sie einen Namen für die Konfiguration an. |
   | **[!UICONTROL Sandbox]** | Wählen Sie die Experience Platform-Sandbox aus, die den Profildatensatz mit den Mitgliedschaftsdaten Ihrer Einverständnisrichtlinie enthält. <p>Pro Sandbox ist maximal ein Einverständnisrichtlinien-Lookup-Datensatz vorhanden. Mehrere Konfigurationen in derselben Sandbox verwenden denselben Lookup-Datensatz.</p> |

1. Wählen Sie im **[!UICONTROL Profildatensatz]** im Feld **[!UICONTROL Zusammenführungsrichtlinie]** die Zusammenführungsrichtlinie aus, die dem Profildatensatz entspricht, der die Einverständnisrichtlinien-Mitgliedschaftsdaten enthält (das `consentPoliciesIDMap`), über die Sie einen Bericht erstellen möchten. Wenn Sie die Einverständnisberichterstattung aktivieren, wird dieser Profildatensatz zu der von Ihnen ausgewählten Verbindung hinzugefügt, sofern er nicht bereits Teil davon ist.<p>Zusammenführungsrichtlinien bestimmen, wie Adobe Experience Platform Profildaten aus mehreren Datensätzen zu einheitlichen Kundenprofilen kombiniert, die für Einverständnisrichtlinien-Mitgliedschaftsdaten verwendet werden. Jeden Tag wird in Experience Platform ein Schnappschuss dieser Daten generiert. Dieser Snapshot bietet eine statische Ansicht der Daten zu einem bestimmten Zeitpunkt und enthält keine Ereignisdaten.</p><p>Wählen Sie die **[!UICONTROL Standardzeitbasierte]** Zusammenführungsrichtlinie aus, wenn Sie mehrere Zusammenführungsrichtlinien sehen und sich nicht sicher sind, welche ausgewählt werden soll. Sie können sich auch an Ihr Daten-Team wenden, um besser zu verstehen, welche Einverständnisdaten mit den einzelnen Zusammenführungsrichtlinien verknüpft sind.</p>

1. Wählen Sie im **[!UICONTROL Verbindung]** die Option **[!UICONTROL Verbindung auswählen]**, aktivieren Sie das Kontrollkästchen neben der zu konfigurierenden Verbindung und klicken Sie dann auf **[!UICONTROL Verbindung verwenden]**.

   Einverständnisberichte und -filter werden auf Verbindungsebene angewendet. Alle Datenansichten unter einer konfigurierten Verbindung übernehmen dasselbe Verhalten.

1. Wählen **[!UICONTROL im Feld]** Personen-ID“ ein Feld aus dem modellbasierten Schema aus, das die Personen-ID darstellt. Die Auswahl ist auf die Liste der Felder im Schema beschränkt, die als „Identität“ markiert sind und keinen Identity-Namespace haben.

1. Wählen Sie aus, ob das Reporting für die Einverständnisdaten aktiviert werden soll.

   Informationen dazu, wann das Reporting aktiviert wird, finden Sie unter [Einverständnisberichte vs. Filterung](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering).

   So aktivieren und konfigurieren Sie Berichte:

   1. Wählen Sie im **[!UICONTROL Reporting]** die Option **[!UICONTROL Reporting aktivieren]** aus.

   1. Wählen Sie alle mit der Verbindung verknüpften Datenansichten aus, die Sie beim Analysieren von Platform-Einverständnisdaten in Analysis Workspace verwenden möchten. Klicken **[!UICONTROL Abschnitt „Datenansichten]** auf **[!UICONTROL Datenansichten auswählen]**.

   1. Aktivieren Sie im Dialogfeld Datenansichten das Kontrollkästchen neben einer oder mehreren Datenansichten, die Sie für das Einverständnisbericht verwenden möchten. Diese Datenansichten werden automatisch mit Experience Platform-Einverständnisdaten für das Reporting konfiguriert.

   1. Wählen **[!UICONTROL Datenansichten verwenden]** aus.

1. Wählen Sie aus, ob die Filterung aktiviert werden soll, sodass Besucher, die nicht zustimmen, bei der Aufnahme ausgeschlossen werden.

   Wenn das Filtern aktiviert ist, nimmt Customer Journey Analytics die Daten eines Besuchers nur dann auf, wenn der Besucher allen aktivierten Einverständnisrichtlinien entspricht.

   Informationen dazu, wann die Filterung aktiviert werden sollte, finden Sie unter [Einverständnisberichte vs. Filterung](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering).

   So aktivieren und konfigurieren Sie die Filterung:

   1. Wählen Sie im **[!UICONTROL Filtern]** die Option **[!UICONTROL Filtern aktivieren]** aus, um Einverständnisdaten zu filtern.

   1. Aktivieren Sie die Filterung für eine oder beide der folgenden Marketing-Aktionen:

      >[!NOTE]
      >
      >Wenn die Filterung nach einer Marketing-Aktion aktiviert ist, nimmt Customer Journey Analytics die Daten eines Besuchers nur dann auf, wenn der Besucher mit **allen** Einverständnisrichtlinien übereinstimmt, die für diese Marketing-Aktion gelten. Weitere Informationen finden Sie unter [Einverständnisfilter](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) in [Übersicht über Einverständnisberichte und -filter](/help/connections/consent-reporting-filtering/consent-overview.md).

      Marketing-Aktionen sind an die Datennutzungskennzeichnungen und -richtlinien gebunden, die Sie in Experience Platform konfigurieren. Weitere Informationen finden Sie unter [Bezeichnungen, Richtlinien und Marketing-Aktionen](/help/data-views/data-governance.md).

      | Marketing-Aktion | Beschreibung |
      | --------- | ---------- |
      | **[!UICONTROL Analytics-Daten]** | Filtern von Daten, die für standardmäßige Customer Journey Analytics-Berichte in Analysis Workspace verwendet werden. |
      | **[!UICONTROL Datenwissenschaftsdaten]** | Filtern Sie Daten, die für erweiterte Analysen, maschinelles Lernen und datenwissenschaftliche Anwendungsfälle verwendet werden. |

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
