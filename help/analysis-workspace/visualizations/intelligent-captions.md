---
description: Verwenden Sie intelligente Beschriftungen, um Erkenntnisse in natürlicher Sprache zu generieren und Trends in Visualisierungen darzustellen.
title: Intelligente Beschriftungen
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 5d391a73fb30ebc8f443f5a88357c866df03ce96
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 19%

---

# Intelligente Beschriftungen {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="Intelligente Beschriftungen: Bereich"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="Intelligente Beschriftungen: Balken"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="Intelligente Beschriftungen: Ringdiagramm"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="Intelligente Beschriftungen: Horizontalbalken"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="Intelligente Beschriftungen: Linie"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="Intelligente Beschriftungen: Fallout"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="Intelligente Beschriftungen: Fluss"
>abstract="Generieren Sie Erkenntnisse in natürlicher Sprache, um Daten für diese Visualisierung leichter verstehen und interpretieren zu können."

<!-- markdownlint-enable MD034 -->

Die Funktion für intelligente Beschriftungen verwendet die erweiterte generative KI , um wichtige Einblicke in die am häufigsten verwendeten Workspace-Visualisierungen in natürlicher Sprache zu erhalten.

Intelligente Beschriftungen sind auf Folgendes ausgerichtet:

* Analysten, die Narrative benötigen, um sie mit anderen Benutzern zu teilen. Analysten benötigen diese Einblicke, um ihren Benutzern einen Kontext bieten zu können.
* Geschäftsbenutzer, die schnell allgemeine Erkenntnisse gewinnen möchten.

>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intelligente ](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"}) für ein Demovideo.

>[!ENDSHADEBOX]

## Intelligente Beschriftungen starten {#launch}

Um automatisch generierte intelligente Beschriftungen für eine Visualisierung zu starten, wählen Sie ![Intelligente Beschriftungen](/help/assets/icons/AI.svg) oben rechts in der Visualisierung aus. Diese Auswahl generiert Erkenntnisse in natürlicher Sprache.

![Fenster „Analyse starten“ mit den intelligenten Beschriftungen für Produktansichten - Trend. ](assets/intelligent-captions.gif)


Bedenken Sie Folgendes:

* Sie benötigen mindestens 3 Datenpunkte, um Beschriftungen erfolgreich zu generieren. Andernfalls tritt möglicherweise ein Fehler auf wie **[!UICONTROL Nicht genügend Daten zum Analysieren]**.

* Beschriftungen werden jedes Mal generiert, wenn sich die zugrunde liegenden ausgewählten Daten in der Tabelle ändern, die die Visualisierung ermöglicht.

* Wenn eine verknüpfte Freiformtabelle mehrere Metriken enthält, werden Beschriftungen nur für die erste Metrik oder die Metrik generiert, die derzeit vom Benutzer ausgewählt wird. Es können jedoch Beschriftungen für mehrere Metriken für die Linien- und Bereichsvisualisierungen generiert werden.

* Wenn Sie das Projekt an einem bestimmten Punkt speichern und später erneut laden, werden die Beschriftungen automatisch mit neuen Daten aktualisiert. Dasselbe gilt für geplante Projekte und das PDF von Dateien, die aus einem Projekt exportiert wurden.


## Visualisierungen {#visualizations}

Intelligente Beschriftungen werden in den folgenden Visualisierungen unterstützt:

* [Line](line.md) (einschließlich mehrzeilig)
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

Sie können die Untertitel in eine Zwischenablage kopieren und in einen PowerPoint oder andere Tools einfügen. Sie können einzelne Beschriftungen in der Einzelansicht kopieren, oder Sie können alle Beschriftungen gleichzeitig in die erweiterte Beschriftungsansicht kopieren.

* Um die Beschriftungen zu kopieren![ wählen Sie oben ](/help/assets/icons/Copy.svg) im Dialogfeld „Beschriftungen“ die Option „Beschriftungen in Zwischenablage kopieren“ aus.

### Alle oder einzelne intelligente Beschriftungen anzeigen  {#show-all-or-individual}

Sie können alle intelligenten Beschriftungen gleichzeitig in einer erweiterten Ansicht anzeigen, oder Sie können einzelne intelligente Beschriftungen einzeln anzeigen.

* Um alle intelligenten Beschriftungen anzuzeigen, wählen Sie ![Alle intelligenten Beschriftungen anzeigen](/help/assets/icons/Maximize.svg) aus.
* Um einzelne intelligente Beschriftungen einzeln anzuzeigen, wählen Sie ![Einzelne intelligente Beschriftungen anzeigen](/help/assets/icons/Minimize.svg).

### Anzeige bearbeiten {#edit}

Sie können die Anzeige von Beschriftungen bearbeiten, z. B. das Ausblenden oder Einblenden einer bestimmten Kategorie von Einblicken.

1. Wählen ![Sichtbarkeit intelligenter Beschriftungen bearbeiten](/help/assets/icons/EditInLight.svg) im Dialogfeld „Intelligente Beschriftungen“ aus.

1. Schalten Sie zwischen ![Sichtbarkeit ein/aus](/help/assets/icons/Visibility.svg) um eine bestimmte Einsicht anzuzeigen (z. B **[!UICONTROL Min]**) oder ![Sichtbarkeit ein/aus](/help/assets/icons/VisibilityOff.svg) um eine bestimmte Einsicht auszublenden (z. B. **[!UICONTROL Spike]**).

   ![Intelligente Beschriftungen bearbeiten](assets/edit-intelligent-captions.png)

1. Wählen Sie **[!UICONTROL Anwenden]** aus.


### Feedback geben

Sie können Feedback zu den generierten intelligenten Beschriftungen geben (Feedback kann nur in der erweiterten Beschriftungsansicht bereitgestellt werden).

1. Wählen ![Weitere Aktionen](/help/assets/icons/More.svg) im Dialogfeld für intelligente Beschriftungen aus.

1. Wählen Sie ![Gute Antwort](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Gute Antwort]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Schlechte Antwort]** oder ![Flag](/help/assets/icons/Flag.svg)**[!UICONTROL Report]**.

1. Geben Sie im **[!UICONTROL Vielen Dank für Ihr Feedback]** Ihr Feedback ein und wählen Sie **[!UICONTROL Senden]**, um das Feedback zu senden.

### Exportieren {#export}

Sie können intelligente Untertitel als Teil eines PDF exportieren, sofern das Projekt mit den generierten intelligenten Untertiteln gespeichert wird.

### Aus-Schalter {#toggle}

Wenn Sie intelligente Untertitel nicht anzeigen möchten, können Sie die Funktion deaktivieren.

1. Navigieren Sie zu [Visualisierungseinstellungen](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Deaktivieren Sie **[!UICONTROL Intelligente Beschriftungen anzeigen]**.

   ![Optionen für die Linienvisualisierung, in der die Option zum Deaktivieren von „Intelligente Beschriftungen anzeigen“ angezeigt wird.](assets/toggle-captions.png)

1. Wählen **[!UICONTROL Speichern]**, um die Voreinstellung zu speichern.


## Intelligente Beschriftungen in mobilen Scorecards

Intelligente Beschriftungen sind auch in Customer Journey Analytics (mobile [) ](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).

## Funktionszugriff

Die folgenden Parameter regeln den Zugriff auf intelligente Beschriftungen:

* **Lösungszugriff**: Die Funktion für intelligente Beschriftungen ist auf Customer Journey Analytics verfügbar, aber nicht in Adobe Analytics.

* **Vertragszugriff**: Wenn Sie keine intelligenten Beschriftungen verwenden können, wenden Sie sich an den Administrator oder den Adobe-Kontobeauftragten Ihres Unternehmens (Admin). Bevor Sie intelligente Beschriftungen in Ihrer Organisation verwenden können, müssen Sie bestimmten rechtlichen Begriffen im Zusammenhang mit Generative AI zustimmen.

* **Berechtigungen**: In der [!UICONTROL Adobe Admin Console] bestimmt die Berechtigung  Reporting-Tools **[!UICONTROL Intelligente Beschriftungen]** den Zugriff. Ein [Produktprofil-Administrator](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) muss diese Schritte in der [!UICONTROL Admin Console ausführen]:
   1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]**.
   1. Wählen Sie den Titel des Produktprofils aus, für das Sie Zugriff auf intelligente Beschriftungen gewähren möchten.
   1. Wählen Sie im spezifischen Produktprofil die Option **[!UICONTROL Berechtigungen]** aus.
   1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um **[!UICONTROL Reporting-Tools]** zu bearbeiten.
   1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) aus, um **Intelligente Beschriftungen** zu **[!UICONTROL Enthaltene Berechtigungselemente]** hinzuzufügen.

      ![Berechtigung hinzufügen](./assets/intelligent-captions-permissions.png)

   1. Wählen **[!UICONTROL Speichern]**, um die Berechtigungen zu speichern.

Weitere Informationen [ Sie unter ](/help/technotes/access-control.md#access-control)Zugriffssteuerung“.
