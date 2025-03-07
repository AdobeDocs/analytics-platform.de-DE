---
title: Hinzufügen von Quantum Metric Friction-Ereignissen zu Customer Journey Analytics
description: Fügen Sie den Einblicken in Customer Journey Analytics mithilfe von Reibungsereignissen, die in Quantum Metric erfasst wurden, Tiefen hinzu.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: e6a77e75963fb43041c0533a28a9563a3849b8b0
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 0%

---

# Hinzufügen von Quantum Metric Friction-Ereignissen zu Customer Journey Analytics

Die Quantum-Metrik erfasst Friktionsereignisse wie Langsamkeit beim Laden der Seite, Seitenladefehler, Wutklicks und mehr. Diese Ereignisse können als komplementäre Ereignisse auf der Benutzer-Journey an Customer Journey Analytics übergeben werden. Mit diesen kombinierten Daten können Sie die Auswirkungen von Reibung auf nachgelagerte Metriken besser verstehen.

Dieser Anwendungsfall hat zwei Anforderungen:

* Sie müssen über eine Berechtigung für das **Dev Ops**-Paket von Quantum Metric verfügen.
* Sie müssen Tags in der Adobe Experience Platform-Datenerfassung verwenden.

## Schritt 1: Erfassen von Reibungsereignissen mit der Quantum Metric-Tag-Erweiterung

Das CSM-Team für Quantum Metric kann Ihnen dabei helfen, die richtigen Schemaelemente zu bestimmen, die hinzugefügt werden sollen, und Sie anweisen, Ihre Implementierung zu ändern, um die gewünschten Daten zur Verwendung in Customer Journey Analytics zu erfassen. Weitere Informationen erhalten Sie von Ihrem Quantum Metric Customer Success Manager.

Am Ende sollten Sie damit beginnen, den Namen des Friktionsereignisses in einem Feld zu verfolgen.

## Schritt 2: Bestätigen der eingeschlossenen Datensatzfelder

Vergewissern Sie sich, dass die Datensätze in Ihrer Verbindung jetzt die Quantum Metric-Sitzungs-ID im gewünschten Datensatz haben.

## Schritt 3: Hinzufügen einer oder mehrerer Dimensionen und Metriken zur Datenansicht in Customer Journey Analytics

Bearbeiten Sie die vorhandene Datenansicht, um die Sitzungs-ID als verfügbare Dimension in Customer Journey Analytics hinzuzufügen.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Datenansichten]** im oberen Menü aus.
1. Wählen Sie die gewünschte vorhandene Datenansicht aus.
1. Suchen Sie die Liste Quantum Metric Friction Event Field auf der linken Seite und ziehen Sie sie in den Bereich Metriken in der Mitte.
1. Legen Sie im rechten Bereich die Einstellung [Werte einschließen/ausschließen](/help/data-views/component-settings/include-exclude-values.md) auf die gewünschten Reibungsereignisse fest, die Sie verfolgen möchten. Sie können derselben Metrik mehrere Reibungsereignisse hinzufügen, um sie zu kombinieren. Sie können auch eine weitere Kopie des Felds Reibungsereignisse in den Bereich Metriken ziehen, um andere Reibungsereignisse als separate Metrik zu verfolgen.
1. Nachdem Sie alle gewünschten Dimensionen und Metriken erstellt haben, klicken Sie auf **[!UICONTROL Speichern]**.

## Schritt 4: Verwenden Sie die Dimension und Metriken für den Rest Ihrer Daten in Analysis Workspace.

Wenn Quantum Metric Friction-Ereignisdaten zusammen mit den anderen Besucherdaten erfasst werden, können Sie sie genau wie jede andere Dimension oder Metrik in Customer Journey Analytics verwenden.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Ziehen Sie die gewünschten Dimensionen und Metriken zur Analyse auf die Workspace-Arbeitsfläche.

Mögliche Ideen für Analysen sind:

* Trend von Reibungsereignisdaten im Zeitverlauf
* Fügen Sie in einer Fallout- oder Trichtervisualisierung Customer Journey Analytics-Ereignisse als einige Schritte und Quantenmetrik-Reibungsereignisse als andere hinzu. Dieser Bericht zeigt an, wo Besucherinnen und Besucher am häufigsten in Schwierigkeiten geraten.
* Erstellen und Anwenden eines Filters für Besucherinnen und Besucher, für die Reibungsereignisse auftreten, um eine tiefere Analyse zu ermöglichen
