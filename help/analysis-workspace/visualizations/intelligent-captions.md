---
description: Verwenden Sie intelligente Beschriftungen, um Erkenntnisse in natürlicher Sprache zu generieren und so Trends in Visualisierungen darzustellen.
title: Intelligente Beschriftungen
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: af8d4f07498211931e9549cadd4746eebb9f56f4
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 100%

---

# Intelligente Beschriftungen {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions"
>title="Intelligente Beschriftungen"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."


Die Funktion „Intelligente Beschriftungen“ nutzt fortschrittliche generative KI, um wichtige Erkenntnisse zu den am häufigsten verwendeten Workspace-Visualisierungen in natürlicher Sprache bereitzustellen.

Intelligente Beschriftungen richten sich an:

* Analystinnen und Analysten, die Narrative für andere Benutzende benötigen. Analystinnen und Analysten sind auf diese Erkenntnisse angewiesen, um ihren Benutzenden Kontext bereitstellen zu können.
* Business-Anwendende, die schnell allgemeine Erkenntnisse gewinnen möchten.

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [intelligente Beschriftungen](https://video.tv.adobe.com/v/3443147/?quality=12&learn=on&captions=ger){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


## Einsetzen intelligenter Beschriftungen {#launch}

Um automatisch generierte intelligente Beschriftungen für eine Visualisierung einzusetzen, wählen Sie oben rechts in der Visualisierung die Option ![Intelligente Beschriftungen](/help/assets/icons/AI.svg) aus. Durch diese Auswahl werden Erkenntnisse in natürlicher Sprache generiert.

![Einsetzen des Fensters „Analyse“ mit intelligenten Beschriftungen für „Produktansichten – Trend“. ](assets/intelligent-captions.gif)


Bedenken Sie Folgendes:

* Sie benötigen mindestens 3 Datenpunkte, um Beschriftungen erfolgreich zu generieren. Andernfalls tritt möglicherweise ein Fehler wie **[!UICONTROL Nicht genügend Daten für eine Analyse]** auf.

* Beschriftungen werden jedes Mal generiert, wenn sich die zugrunde liegenden ausgewählten Daten in der Tabelle ändern, auf der die Visualisierung basiert.

* Wenn eine verknüpfte Freiformtabelle mehrere Metriken enthält, werden Beschriftungen nur für die erste Metrik oder die Metrik generiert, die aktuell von der Benutzerin bzw. dem Benutzer ausgewählt ist. Es können jedoch Beschriftungen für mehrere Metriken für Visualisierungen vom Typ „Linie“ und „Bereich“ generiert werden.

* Wenn Sie das Projekt zu einem bestimmten Zeitpunkt speichern und später erneut laden, werden die Beschriftungen automatisch mit neuen Daten aktualisiert. Dasselbe gilt für geplante Projekte und PDF-Dateien, die aus einem Projekt exportiert werden.


## Visualisierungen {#visualizations}

Intelligente Beschriftungen werden in den folgenden Visualisierungen unterstützt:

* [Linie](line.md) (einschließlich mehrerer Linien)
* [Balken](bar.md)
* [Horizontalbalken](horizontal-bar.md)
* [Bereich](area.md) (einschließlich mehrerer Bereichslinien)
* [Ringdiagramm](donut.md)
* [Fallout](fallout/fallout-flow.md)
* [Fluss](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## Aktionen

Sie können die folgenden Aktionen für intelligente Beschriftungen ausführen:

### In Zwischenablage kopieren {#copy}

Sie können die Beschriftungen in die Zwischenablage kopieren und in PowerPoint oder andere Tools einfügen. Sie können einzelne Beschriftungen in der Einzelansicht oder alle Beschriftungen gleichzeitig in der erweiterten Beschriftungsansicht kopieren.

* Um die Beschriftungen zu kopieren, wählen Sie oben rechts im Dialogfeld „Beschriftungen“ die Option ![Beschriftungen in Zwischenablage kopieren](/help/assets/icons/Copy.svg) aus.

### Anzeigen aller oder einzelner intelligenter Beschriftungen  {#show-all-or-individual}

Sie können auswählen, ob alle intelligenten Beschriftungen gleichzeitig in einer erweiterten Ansicht oder einzelne intelligente Beschriftungen in einer Einzelansicht angezeigt werden sollen.

* Um alle intelligenten Beschriftungen anzuzeigen, wählen Sie ![Alle intelligenten Beschriftungen anzeigen](/help/assets/icons/Maximize.svg) aus.
* Um einzelne intelligente Beschriftungen anzuzeigen, wählen Sie ![Einzelne intelligente Beschriftungen anzeigen](/help/assets/icons/Minimize.svg) aus.

### Bearbeiten der Anzeige {#edit}

Sie können die Anzeige von Beschriftungen bearbeiten, z. B. eine bestimmte Kategorie von Erkenntnissen aus- oder einblenden.

1. Wählen Sie im Dialogfeld „Intelligente Beschriftungen“ die Option ![Sichtbarkeit intelligenter Beschriftungen bearbeiten](/help/assets/icons/EditInLight.svg) aus.

1. Wechseln Sie zwischen ![Sichtbarkeit ein-/ausschalten](/help/assets/icons/Visibility.svg), um eine bestimmte Erkenntnis (z. B. **[!UICONTROL Min.]**) einzublenden, und ![Sichtbarkeit ein-/ausschalten](/help/assets/icons/VisibilityOff.svg), um eine bestimmte Erkenntnis (z. B. **[!UICONTROL Spitze]**) auszublenden.

   ![Bearbeiten intelligenter Beschriftungen](assets/edit-intelligent-captions.png)

1. Wählen Sie **[!UICONTROL Anwenden]** aus.


### Feedback geben

Sie können Feedback zu den generierten intelligenten Beschriftungen geben. (Feedback kann nur in der erweiterten Beschriftungsansicht bereitgestellt werden.)

1. Wählen Sie im Dialogfeld „Intelligente Beschriftungen“ die Option ![Weitere Aktionen](/help/assets/icons/More.svg) aus.

1. Wählen Sie ![Gute Antwort](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Gute Antwort]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Schlechte Antwort]** oder ![Flag](/help/assets/icons/Flag.svg) **[!UICONTROL Bericht]** aus.

1. Geben Sie im Dialogfeld **[!UICONTROL Vielen Dank für Ihr Feedback]** Ihr Feedback ein und wählen Sie **[!UICONTROL Absenden]** aus, um das Feedback zu senden.

### Exportieren {#export}

Sie können intelligente Beschriftungen als Teil einer PDF exportieren, sofern das Projekt mit den generierten intelligenten Beschriftungen gespeichert wird.

### Ausschalten {#toggle}

Wenn Sie lieber keine intelligenten Beschriftungen verwenden möchten, können Sie die Funktion deaktivieren.

1. Navigieren Sie zu den [Visualisierungsvoreinstellungen](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Deaktivieren Sie **[!UICONTROL Intelligente Untertitel anzeigen]**.

   ![Optionen für die Visualisierung „Linie“ mit der Option zum Deaktivieren von „Intelligente Untertitel anzeigen“.](assets/toggle-captions.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**, um die Voreinstellung zu speichern.


## Intelligente Beschriftungen in mobilen Scorecards

Intelligente Beschriftungen sind auch in [mobilen Scorecards](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) von Customer Journey Analytics verfügbar.

## Funktionszugriff

Die folgenden Parameter regeln den Zugriff auf intelligente Beschriftungen:

* **Lösungsbasierter Zugriff**: Die Funktion „Intelligente Beschriftungen“ ist in Customer Journey Analytics verfügbar, aber nicht in Adobe Analytics.

* **Zugriff auf vertraglicher Grundlage**: Wenn Sie keine intelligenten Beschriftungen verwenden können, wenden Sie sich an die bzw. den Admin Ihrer Organisation oder die Adobe-Kundenbetreuung (Admin). Damit Sie intelligente Beschriftungen in Ihrer Organisation verwenden können, müssen Sie bestimmten rechtlichen Bedingungen im Zusammenhang mit generativer KI zustimmen.

* **Berechtigungen**: In der [!UICONTROL Adobe Admin Console] bestimmt die [!UICONTROL Reporting-Tools-Berechtigung] **[!UICONTROL Intelligente Beschriftungen]** den Zugriff. Sie als [Produktprofil-Admin](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) müssen diese Schritte in der [!UICONTROL Admin Console] ausführen:
   1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Dienste]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]**.
   1. Wählen Sie den Titel des Produktprofils aus, für das Zugriff auf die Funktion „Intelligente Beschriftungen“ gewährt werden soll.
   1. Wählen Sie im entsprechenden Produktprofil die Option **[!UICONTROL Berechtigungen]** aus.
   1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um **[!UICONTROL Reporting-Tools]** zu bearbeiten.
   1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) aus, um **Intelligente Beschriftungen** zu **[!UICONTROL Eingeschlossene Berechtigungseinträge]** hinzuzufügen.

      ![Hinzufügen einer Berechtigung](./assets/intelligent-captions-permissions.png)

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md#access-control).
