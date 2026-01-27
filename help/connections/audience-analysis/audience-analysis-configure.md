---
title: Zielgruppenanalyse konfigurieren
description: Erfahren Sie, wie Sie die Zielgruppenanalyse konfigurieren
solution: Customer Journey Analytics
feature: Audiences
role: Admin
source-git-commit: e59bb52d5e9d79ba72036d5a00ed8abc69dcf735
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 12%

---

# Zielgruppenanalyse konfigurieren {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Zusammenführungsrichtlinie"
>abstract="Zusammenführungsrichtlinien kombinieren Profildaten aus mehreren Datensätzen zu einheitlichen Kundenprofilen, die für die Erstellung von Zielgruppen verwendet werden. Wählen Sie „Standardzeitbasiert“, wenn Sie mehrere Zusammenführungsrichtlinien sehen und sich nicht sicher sind, welche ausgewählt werden soll. Oder wenden Sie sich an Ihr Daten-Team, um zu erfahren, welche Zielgruppen mit den einzelnen Zusammenführungsrichtlinien verknüpft sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="Sandbox"
>abstract="Wählen Sie die Sandbox aus, die die richtigen Experience Platform-Profildatensätze enthält. Diese Datensätze müssen die Zielgruppendaten enthalten, über die Sie in Analysis Workspace einen Bericht erstellen möchten. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="Personen-ID"
>abstract="Wählen Sie ein Feld aus dem Schema aus, das die Personen-ID darstellt. Die Auswahl ist auf die Liste der Felder im Schema beschränkt, die als Identität markiert sind und einen Identity-Namespace haben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="Primären Identity-Namespace verwenden"
>abstract="Aktivieren Sie diese Option, wenn Customer Journey Analytics die Identität in der Identitätszuordnung finden soll, die mit dem Attribut primary=true markiert ist, und diese Identität dann als Personen-ID für diese Zeile verwenden soll. Diese Identität ist der Primärschlüssel, der in Experience Platform für die Partitionierung verwendet wird. <br/>Wenn Sie diese Option deaktiviert lassen, wählen Sie unten aus dem Feld Identity-Namespace einen Namespace aus. Customer Journey Analytics durchsucht die Identitätszuordnung jeder Zeile nach diesem Namespace-Schlüssel und verwendet die Identität unter diesem Namespace als Personen-ID für diese Zeile."

<!-- markdownlint-enable MD034 -->

Mit der Zielgruppenanalyse können Sie Zielgruppenzugehörigkeitsdaten aus Experience Platform-Profildatensätzen in eine Customer Journey Analytics-Verbindung aufnehmen. Zielgruppen werden als neue Dimensionen zur Verwendung in Analysis Workspace verfügbar. Weitere Übersichtsinformationen zur Zielgruppenanalyse finden Sie unter [Zielgruppenanalyse - Übersicht](/help/connections/audience-analysis/audience-analysis-overview.md).

>[!IMPORTANT]
>
>Zielgruppendaten werden jede Nacht neu verarbeitet und generiert, sodass die Zielgruppendaten nur für die Analyse am Vortag („gestern„) korrekt sind.
>
>Audiences stehen in Customer Journey Analytics-Datenansichten am Tag nach der Erstellung der Zielgruppenanalysekonfiguration zur Verfügung.

## Erstellen einer Zielgruppenanalysekonfiguration

Wählen Sie beim Erstellen einer Zielgruppenanalysekonfiguration die Sandbox und die Zusammenführungsrichtlinie aus, die mit den Experience Platform-Zielgruppen verknüpft sind, die Sie analysieren möchten. Customer Journey Analytics erstellt einen neuen Lookup-Datensatz und fügt dann den Lookup-Datensatz und den Profildatensatz automatisch zur ausgewählten Verbindung hinzu.

Nur Systemadministratoren können Zielgruppenanalysekonfigurationen erstellen.

So erstellen Sie eine Zielgruppenanalysekonfiguration:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Zielgruppenanalysekonfiguration]** aus.

   ![Zielgruppenanalyse-Hauptseite](assets/audience-analysis-empty.png)

1. Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus.

   ![Erstellen einer Zielgruppenanalysekonfiguration](assets/audience-analysis-create.png)

1. Geben **[!UICONTROL im Abschnitt]** die folgenden Informationen an:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Name]** | Geben Sie einen Namen für die Konfiguration an. |
   | **[!UICONTROL Sandbox]** | Wählen Sie die Experience Platform-Sandbox aus, die den Profildatensatz enthält, den Sie zu Ihrer Verbindung hinzufügen möchten. Eine einzelne Sandbox kann bis zu 100 Zielgruppenanalysekonfigurationen unterstützen. <p>Adobe Experience Platform bietet [Sandboxes](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home) bereit, die eine einzelne Platform-Instanz in separate virtuelle Umgebungen aufteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu erleichtern. Sie können sich Sandboxes als „Datensilos“ vorstellen. Sandboxes dienen der Steuerung des Zugriffs auf Datensätze.</p> |

1. Geben **[!UICONTROL im Abschnitt]** Profildatensatz“ die folgenden Informationen an:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Zusammenführungsrichtlinie]** | Wählen Sie die Zusammenführungsrichtlinie aus, die dem Profildatensatz entspricht, den Sie für die Zielgruppenanalyse verwenden möchten. <p>Zusammenführungsrichtlinien bestimmen, wie Adobe Experience Platform Profildaten aus mehreren Datensätzen zu einheitlichen Kundenprofilen kombiniert, die für die Erstellung von Zielgruppen verwendet werden. Die ausgewählte Zusammenführungsrichtlinie wirkt sich darauf aus, welche Profilattribute in Ihren Zielgruppen enthalten sind. Jeden Tag wird in Experience Platform ein Schnappschuss dieser Daten generiert. Dieser Snapshot bietet eine statische Ansicht der Daten zu einem bestimmten Zeitpunkt und enthält keine Ereignisdaten.</p><p>Wählen Sie die **[!UICONTROL Standardzeitbasierte]** Zusammenführungsrichtlinie aus, wenn Sie mehrere Zusammenführungsrichtlinien sehen und sich nicht sicher sind, welche ausgewählt werden soll. Sie können auch Ihr Daten-Team konsultieren, um besser zu verstehen, welche Zielgruppen mit den einzelnen Zusammenführungsrichtlinien verknüpft sind.</p> |
   | **[!UICONTROL Profildatensatz]** | Der Profildatensatz, der mit der ausgewählten Zusammenführungsrichtlinie verknüpft ist. Dieser Profildatensatz enthält die Experience Platform-Zielgruppendaten, die Sie analysieren möchten. Dieser Profildatensatz wird der ausgewählten Verbindung hinzugefügt.<p>Nachdem Sie eine Zusammenführungsrichtlinie ausgewählt haben, wird der Export des Profilschnappschusses angezeigt. Beispiel: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>Weitere Informationen finden Sie unter [Profilattributdatensätze](https://experienceleague.adobe.com/de/docs/experience-platform/dashboards/query#profile-attribute-datasets) im Handbuch zu Experience Platform-Dashboards.</p> |

1. Klicken Sie **[!UICONTROL Abschnitt]** Verbindung“ auf **[!UICONTROL Verbindung auswählen]**.

1. Aktivieren Sie im Dialogfeld Verbindungen das Kontrollkästchen neben der Verbindung, der Sie den Profildatensatz hinzufügen möchten, und klicken Sie dann auf **[!UICONTROL Verbindung verwenden]**.

   Eine Verbindung kann nur mit einer Zielgruppenanalysekonfiguration verknüpft werden.

1. Geben Sie die folgenden Informationen an, um die Verbindung zu konfigurieren:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Personen-ID]** | Wählen Sie ein Feld aus dem Schema aus, das die Personen-ID darstellt.<p>Die Auswahl ist auf die Liste der Felder im Schema beschränkt, die als Identität markiert sind und keinen Identity-Namespace haben. **[!UICONTROL IdentityMap]** ist standardmäßig ausgewählt und für die meisten Konfigurationen geeignet. </p><p>Wenn keine Personen-IDs zur Auswahl stehen, bedeutet dies, dass eine oder mehrere Personen-IDs nicht im Schema definiert wurden. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity).</p> |
   | **[!UICONTROL Primären Identity-Namespace verwenden]** | Diese Option wird angezeigt, wenn Sie **[!UICONTROL Identitätszuordnung]** für die Personen-ID auswählen. <p>Aktivieren Sie diese Option, wenn Customer Journey Analytics die Identität in der Identitätszuordnung finden soll, die mit dem Attribut primary=true markiert ist, und diese Identität dann als Personen-ID für diese Zeile verwenden soll. Diese Identität ist der Primärschlüssel, der in Experience Platform für die Partitionierung verwendet wird. Diese Identität ist auch der primäre Kandidat für die Verwendung als Personen-ID für Customer Journey Analytics (je nachdem, wie der Datensatz in einer Customer Journey Analytics-Verbindung konfiguriert ist).</p> |
   | **[!UICONTROL Identity-Namespace]** | Diese Option wird angezeigt, wenn Sie **[!UICONTROL Identitätszuordnung]** für die Personen-ID auswählen. Diese Option ist deaktiviert, wenn Sie den Primären ID-Namespace verwenden. <p>Identity-Namespaces sind eine Komponente von [Experience Platform Identity Service](https://experienceleague.adobe.com/de/docs/experience-platform/identity/features/namespaces). Namespaces dienen als Indikatoren für den Kontext, auf den sich eine Identität bezieht. Wenn Sie einen Namespace angeben, durchsucht Customer Journey Analytics die Identitätszuordnung jeder Zeile nach diesem Namespace-Schlüssel und verwendet die Identität unter diesem Namespace als Personen-ID für diese Zeile. Da Customer Journey Analytics nicht alle Zeilen vollständig durchsuchen kann, um zu bestimmen, welche Namespaces vorhanden sind, werden alle möglichen Namespaces im Dropdown-Menü angezeigt. Sie müssen wissen, welche Namespaces in den Daten angegeben sind. Diese Namespaces werden nicht automatisch erkannt.</p> |

   <!-- Add this when B2B releases for AuA **[!UICONTROL Account ID]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}|  (only displayed for account-based connections) The Account ID that is used to support account-based reporting for the dataset. -->

1. Klicken **[!UICONTROL Abschnitt „Datenansichten]** auf **[!UICONTROL Datenansichten auswählen]**.

1. Aktivieren Sie im Dialogfeld Datenansichten das Kontrollkästchen neben einer oder mehreren Datenansichten, die Sie bei der Analyse von Experience Platform-Zielgruppendaten in Analysis Workspace verwenden möchten. Diese Datenansichten werden für das Reporting automatisch mit Experience Platform-Zielgruppendaten konfiguriert.

1. Wählen **[!UICONTROL Datenansichten verwenden]** aus.

1. Wählen **[!UICONTROL Erstellen]** aus, um die Konfiguration zu erstellen.

   >[!IMPORTANT]
   >
   >Da der Profildatensatz einmal täglich aktualisiert wird, sind Zielgruppen in Customer Journey Analytics-Datenansichten am Tag nach der Erstellung der Zielgruppenanalysekonfiguration verfügbar.


1. Überprüfen Sie nach 24 [&#x200B; mithilfe von Zielgruppendimensionen in der &#x200B;](#view-audience-dimensions-in-the-data-view), ob die Zielgruppendimensionen in den von Ihnen ausgewählten Datenansichten verfügbar sind.

## Anzeigen von Zielgruppendimensionen in der Datenansicht

Nachdem Sie [Zielgruppenanalyse-Konfiguration erstellen](#create-an-audience-analysis-configuration) können Sie überprüfen, ob Zielgruppendimensionen zu den Datenansichten hinzugefügt wurden, die Sie während der Konfiguration ausgewählt haben.

Um Zielgruppendimensionen in der Datenansicht anzuzeigen, müssen Sie Produktprofil-Administrator für das Produktprofil sein, dem die Datenansicht zugewiesen ist. Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md).

So zeigen Sie die Dimensionen der Zielgruppenanalyse in der Datenansicht an:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Datenansichten]** aus.

1. Im Abschnitt **[!UICONTROL Dimensionen]** sollten jetzt die folgenden Dimensionen verfügbar sein:

   * **[!UICONTROL Zielgruppenname]**

   * **[!UICONTROL Zielgruppenherkunft]**

   * **[!UICONTROL Herkunft der Zielgruppe beendet]**

   * **[!UICONTROL Name der verlassenen Zielgruppe]**

   Beachten Sie, dass jede dieser Dimensionen dem Profildatensatz hinzugefügt wurde, der mit der Zusammenführungsrichtlinie verknüpft ist, die Sie während der Konfiguration der Zielgruppenanalyse ausgewählt haben. Jede Dimension wurde dem neuen erstellten Lookup-Datensatz hinzugefügt.

   ![Zielgruppendimensionen in der Datenansicht verfügbar](assets/audience-analysis-dataview-dataset.png)

1. Verwenden Sie die Zielgruppenanalysedimensionen in Analysis Workspace.

   Benutzende, die Zugriff auf die Verwendung der Datenansicht in Analysis Workspace haben, können jetzt die neuen Dimensionen sehen und sie in ihren Analysen verwenden. Informationen zur Verwendung der Zielgruppenanalysedimensionen in Analysis Workspace finden Sie unter [&#x200B; von Experience Platform-Zielgruppen in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).


