---
description: In Analysis Workspace gibt es zwei Möglichkeiten zur Verwendung von Metriken.
title: Metriken
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: ec2fc88372814b01a04d4cc824181222ee55a83d
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 7%

---

# Metriken

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.

## Verwenden von Metriken in Analysis Workspace

Metriken können in Analysis Workspace flexibel verwendet werden. Ziehen Sie eine Metrik in eine leere Freiformtabelle, um die Entwicklung dieser Metrik über den Datumsbereich des Projekts anzuzeigen. Sie können auch eine Metrik ziehen, wenn eine Dimension vorhanden ist, um diese Metrik mit jedem Dimensionselement zu vergleichen. Wenn Sie eine Metrik über eine vorhandene Metrik-Kopfzeile ziehen, wird sie ersetzt, und wenn Sie eine Metrik neben einer Kopfzeile ziehen, können Sie beide Metriken nebeneinander sehen.

Informationen zum Hinzufügen von Metriken und anderen Komponententypen zu Analysis Workspace finden Sie unter [Verwenden von Komponenten in Analysis Workspace](/help/components/use-components-in-workspace.md).


## Arten von Metriken

Adobe bietet verschiedene Arten von Metriken zur Verwendung in Analysis Workspace:


* **Standardmetriken**: Beispiel für Standardmetriken sind „Personen“, „Sitzungen“ und „Ereignisse“.

  Im Gegensatz zu Adobe Analytics können Sie mit Customer Journey Analytics Standardmetriken im Rahmen einer Verbindung und einer Datenansicht flexibel definieren.

   * **Personen**: Die Metrik „Personen“ in Customer Journey Analytics entspricht der Anzahl der eindeutigen Personen-IDs. Je nachdem, was Sie bei der Konfiguration von Datensätzen in Ihrer Verbindung als Personen-ID auswählen, kann die Personen -Metrik unterschiedliche Bedeutungen haben.
   * **Sitzungen**: Die Sitzungsmetrik in Customer Journey Analytics wird von Ihnen als Teil der Konfiguration der Sitzungseinstellungen in Ihrer Datenansicht definiert. Siehe [Sitzungseinstellungen](/help/data-views/session-settings.md).
   * **Ereignisse**: Die Ereignismetrik in Customer Journey Analytics besteht aus den Ereignissen, die Teil eines Ereignisdatensatzes sind, den Sie als Teil Ihrer Verbindung konfiguriert haben.

  Siehe [Standardmetriken](#standard-metrics) für die vollständige Liste der Standardmetriken.

* **Berechnete Metriken** ![Rechner](/help/assets/icons/Calculator.svg): Benutzerdefinierte Metriken, die auf Standardmetriken, statischen Zahlen oder algorithmischen Funktionen basieren.

* **Vorlagen für berechnete Metriken** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Von Adobe definierte Metriken, die sich ähnlich wie berechnete Metriken verhalten. Sie können sie unverändert in Workspace-Projekten verwenden oder eine Kopie speichern, um die Logik anzupassen. Siehe [Standardberechnete Metriken](calc-metrics/cm-workflow/../default-calcmetrics.md).

Sie können sehen, ob eine Metrik genehmigt wurde ![Symbol „Genehmigt](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) oder nicht. Wenn Sie weitere Details zu einer Metrik wünschen, bewegen Sie den Mauszeiger über die Metrik und wählen Sie ![Infosymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) aus. Siehe [Komponenteninformationen](use-components-in-workspace.md#component-info) für weitere Informationen.


## Standardmetriken

Vollständige Liste der Standardmetriken in Customer Journey Analytics:
{{standard-metrics}}


## Erstellen von berechneten Metriken

Mit berechneten Metriken können Sie einfach konfigurieren, wie sich Metriken zueinander verhalten, indem Sie einfache Operatoren oder statistische Funktionen verwenden. Weitere Informationen finden [ unter ](/help/components/calc-metrics/calc-metr-overview.md) Metriken - Übersicht .

Es gibt mehrere Möglichkeiten, berechnete Metriken zu erstellen. Die gewählte Methode bestimmt, ob die berechnete Metrik in der Komponentenliste für alle Projekte verfügbar ist oder nur in dem Projekt, in dem sie erstellt wurde.

### Berechnete Metriken für alle Projekte erstellen

Sie können den [Generator für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) verwenden, um [berechnete Metriken zu erstellen](/help/components/calc-metrics/cm-workflow/cm-workflow.md). Wenn sie auf diese Weise erstellt werden, sind berechnete Metriken in der Komponentenliste verfügbar und können dann in Projekten in Ihrer gesamten Organisation verwendet werden.

### Erstellen von berechneten Metriken für ein einzelnes Projekt

Sie können schnell eine berechnete Metrik erstellen, die nur für das Projekt verfügbar ist, in dem sie erstellt wurde.

Erstellen einer berechneten Metrik für ein einzelnes Projekt:

1. Öffnen Sie in Analysis Workspace das Projekt, in dem Sie die berechnete Metrik erstellen möchten.

1. Klicken Sie in einer Freiformtabelle mit der rechten Maustaste auf die Spaltenüberschrift einer einzelnen Spalte.

   Oder

   Wählen Sie zwei Spalten aus, während Sie die Umschalttaste gedrückt halten, und klicken Sie dann mit der rechten Maustaste auf eine der ausgewählten Spalten.

1. Wählen Sie **[!UICONTROL Metrik aus Auswahl erstellen]**

   ![Workspace-Bedienfeld mit hervorgehobener Option „Aus Auswahl erstellen“](assets/create-metric-from-selection.png)

1. Um nur für dieses Projekt eine berechnete Metrik zu erstellen, wählen Sie eine der verfügbaren Optionen aus.

   Wenn eine einzelne Spalte ausgewählt ist, stehen die folgenden Optionen zur Verfügung:

   * [!UICONTROL **Mittel**]: Erstellt eine neue Spalte, die den Mittelwert im Satz der Dimensionselemente für die Spalte anzeigt. Dabei wird die Funktion [Mittelwert](/help/components/calc-metrics/cm-functions.md#mean) verwendet.

   * [!UICONTROL **Median**]: Erstellt eine neue Spalte, die den Medianwert im Satz der Dimensionselemente für die Spalte anzeigt. Dabei wird die [Median](/help/components/calc-metrics/cm-functions.md#median)-Funktion verwendet.

   * [!UICONTROL **Spalte max**]: Erstellt eine neue Spalte, die den größten Wert im Satz von Dimensionselementen für die Spalte anzeigt. Dabei wird die [Spaltenmaximum](/help/components/calc-metrics/cm-functions.md#column-maximum)-Funktion verwendet.

   * [!UICONTROL **Spalte min**]: Erstellt eine neue Spalte, die den kleinsten Wert im Satz der Dimensionselemente für die Spalte anzeigt. Dabei wird die Funktion [Spalten-Minimum](/help/components/calc-metrics/cm-functions.md#column-minimum) verwendet.

   * [!UICONTROL **Spaltensumme**]: Erstellt eine neue Spalte, die alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg) hinzufügt. Dabei wird die Funktion [Spaltensumme](/help/components/calc-metrics/cm-functions.md#column-sum) verwendet.

   Wenn zwei Spalten ausgewählt sind, sind die folgenden Optionen verfügbar:

   * [!UICONTROL **Trennen**]: Erstellt eine neue Spalte, die die Werte der beiden ausgewählten Spalten teilt.

   * [!UICONTROL **Abziehen**]: Erstellt eine neue Spalte, die die Werte der beiden ausgewählten Spalten abzieht.

   * [!UICONTROL **Hinzufügen**]: Erstellt eine neue Spalte, die die Werte der beiden ausgewählten Spalten hinzufügt.

   * [!UICONTROL **Multiplizieren**]: Erstellt eine neue Spalte, die die Werte der beiden ausgewählten Spalten multipliziert.

   * [!UICONTROL **prozentuale Änderung**]: Erstellt eine neue Spalte, die die prozentuale Änderung zwischen den beiden ausgewählten Spalten anzeigt.


## Vergleichen von Metriken mit verschiedenen Attributionsmodellen

Um ein Attributionsmodell für eine Metrik schnell mit einem anderen zu vergleichen, wählen Sie **[!UICONTROL Attributionsmodelle vergleichen]** aus dem Kontextmenü für eine Metrik aus.

![Workspace-Bedienfeld mit hervorgehobenen Attributionsmodellen vergleichen](assets/compare-attribution.png)

Mithilfe dieser Tastenkombination können Sie ein Attributionsmodell mit einem anderen vergleichen, ohne eine Metrik per Drag-and-Drop verschieben und zweimal konfigurieren zu müssen.


