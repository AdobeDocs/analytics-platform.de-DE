---
description: Verwenden Sie intelligente Beschriftungen, um Einblicke in natürliche Sprachen zu generieren, damit Trends schnell in Visualisierungen auftauchen können.
title: Intelligente Beschriftungen
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 6a193f2fd179809afac6808f3fb958c020f53a8d
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 5%

---

# Intelligente Beschriftungen

Intelligente Untertitel verwenden fortschrittliches maschinelles Lernen und generative KI, um wertvolle Einblicke in natürliche Sprachen für Workspace-Visualisierungen bereitzustellen. Die erste Version bietet automatisch generierte Einblicke für die [Linie](line.md) -Visualisierung. Es folgen weitere Visualisierungen.

Intelligente Beschriftungen sind auf Folgendes ausgerichtet:

* Analysten, die Geschichten benötigen, um sie für andere Benutzer freizugeben. Analysten benötigen diese Einblicke, um ihren Benutzern Kontext bieten zu können.
* Geschäftsbenutzer, die schnell allgemeine Schnellzugriffe entdecken möchten.

Untertitel sind für alle Customer Journey Analytics-Benutzer verfügbar und erfordern keine speziellen Berechtigungen.

## Intelligente Beschriftungen starten {#launch}

Um automatisch generierte Untertitel für eine Linienvisualisierung zu starten, klicken Sie oben rechts in der Visualisierung auf das Symbol **[!UICONTROL Intelligente Untertitel]** .

![Das Fenster &quot;Analyse starten&quot;mit den intelligenten Beschriftungen für den Trend zu Produktansichten. ](assets/intell-caps-1.png)

Einblicke in natürliche Sprachen werden jetzt generiert.

Bedenken Sie Folgendes

* Sie benötigen mindestens 3 Datenpunkte, um Beschriftungen erfolgreich zu generieren. Andernfalls wird möglicherweise ein Fehler wie **[!UICONTROL Nicht genügend Daten zur Analyse]** ausgegeben.

* Beschriftungen werden jedes Mal generiert, wenn sich die zugrunde liegenden ausgewählten Daten in der Tabelle ändern, die die Visualisierung steuert.

* Wenn die Tabelle mehrere Metriken enthält, werden Untertitel nur für die erste Metrik oder die Metrik generiert, die aktuell vom Benutzer ausgewählt wird.

* Wenn Sie das Projekt an einem bestimmten Punkt speichern und später erneut laden, werden die Beschriftungen automatisch mit neuen Daten aktualisiert. Dasselbe gilt für geplante Projekte und PDF-Dateien, die aus einem Projekt exportiert werden.

Im Folgenden finden Sie ein Beispiel dafür, wie intelligente Beschriftungen aussehen könnten:

![Intelligente Beschriftungen für die Linienvisualisierung, einschließlich Saisonabhängigkeit, Min., Max., Spitze und Rückgang.](assets/captions.png)

## Aktionen

Sie können die folgenden Aktionen für intelligente Untertitel durchführen:

### In Zwischenablage kopieren {#copy}

Sie können die Beschriftungen in eine Zwischenablage kopieren und in einen PowerPoint- oder andere Tools einfügen. Wählen Sie oben rechts im Dialogfeld &quot;Beschriftungen&quot;die Option ![Beschriftungen in die Zwischenablage kopieren](/help/assets/icons/Copy.svg) aus.

### Anzeige bearbeiten {#edit}

Sie können die Anzeige von Untertiteln bearbeiten, z. B. das Ausblenden oder Aufheben der Ausblendung einer bestimmten Kategorie von Einblicken.

1. Wählen Sie im Dialogfeld &quot;Intelligente Untertitel&quot;die Option ![Intelligente Untertitel bearbeiten..](/help/assets/icons/EditInLight.svg) .

1. Zwischen ![Sichtbarkeit](/help/assets/icons/Visibility.svg) wechseln, um einen bestimmten Einblick anzuzeigen (z. B. **[!UICONTROL Minimum]**), oder ![SichtbarkeitOff](/help/assets/icons/VisibilityOff.svg), um einen bestimmten Einblick auszublenden (z. B. **[!UICONTROL Spitze]**).

   ![Intelligente Beschriftungen bearbeiten](assets/edit-intelligent-captions.png)

1. Wählen Sie **[!UICONTROL Anwenden]** aus.


### Feedback geben

Sie können Feedback zu den generierten intelligenten Untertiteln geben.

1. Wählen Sie ![Mehr Aktionen](/help/assets/icons/More.svg) im Dialogfeld &quot;Intelligente Untertitel&quot;.

1. Wählen Sie ![Good response](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Good response]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Bad response]** oder ![Flag](/help/assets/icons/Flag.svg) **[!UICONTROL report]**.

1. Geben Sie im Dialogfeld **[!UICONTROL Vielen Dank für Ihr Feedback]** Ihr Feedback ein und wählen Sie **[!UICONTROL Senden]** aus, um das Feedback zu senden.

### Exportieren {#export}

Sie können intelligente Untertitel als Teil einer PDF exportieren, solange das Projekt mit den generierten intelligenten Untertiteln gespeichert wird.

### Deaktivieren {#toggle}

Wenn Sie keine intelligenten Beschriftungen anzeigen möchten, können Sie die Funktion deaktivieren.

1. Wechseln Sie zu [Voreinstellungen für Visualisierungen](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Deaktivieren Sie **[!UICONTROL Intelligente Beschriftungen anzeigen]**.

   ![Linienvisualisierungsoptionen mit der Option zum Deaktivieren der Option &quot;Intelligente Untertitel anzeigen&quot;](assets/toggle-captions.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Voreinstellung zu speichern.


## Intelligente Beschriftungen in mobilen Scorecards

Intelligente Untertitel sind auch in Customer Journey Analytics [mobile Scorecards](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) verfügbar.

## Funktionszugriff

Die folgenden Parameter steuern den Zugriff auf intelligente Untertitel:

* **Lösungszugriff**: Die Funktion &quot;Intelligente Untertitel&quot;ist unter Customer Journey Analytics verfügbar, jedoch nicht in Adobe Analytics.

* **Vertraglicher Zugriff**: Wenn Sie keine intelligenten Untertitel verwenden können, wenden Sie sich an den Administrator oder Adobe-Kundenbetreuer Ihres Unternehmens. Bevor Sie Intelligent in Ihrem Unternehmen verwenden können, müssen Sie bestimmten GenAI-bezogenen gesetzlichen Bestimmungen zustimmen.

* **Berechtigungen**: In der [!UICONTROL Adobe Admin Console] bestimmt die Berechtigung [!UICONTROL Berichterstellungs-Tools] **[!UICONTROL Intelligente Untertitel]** den Zugriff. Ein [Produktprofiladministrator](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) muss die folgenden Schritte in der [!UICONTROL Admin Console] ausführen:
   1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Dienste]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]**.
   1. Wählen Sie den Titel des Produktprofils aus, für das Sie Zugriff auf intelligente Beschriftungen gewähren möchten.
   1. Wählen Sie im jeweiligen Produktprofil **[!UICONTROL Berechtigungen]** aus.
   1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um die **[!UICONTROL Berichterstellungs-Tools]** zu bearbeiten.
   1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) aus, um **Intelligente Beschriftungen** zu **[!UICONTROL Einbezogene Berechtigungselemente]** hinzuzufügen.

      ![Berechtigung hinzufügen](./assets/intelligent-captions-permissions.png)

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

Weitere Informationen finden Sie unter [Zugriffskontrolle](/help/technotes/access-control.md#access-control) .
