---
description: In Analysis Workspace gibt es zwei Möglichkeiten zur Verwendung von Metriken.
title: Metriken
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 18%

---

# Metriken

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.

## Arten von Metriken

Adobe bietet verschiedene Arten von Metriken zur Verwendung in Analysis Workspace:

* **Standardmetriken**: Beispiel für Standardmetriken sind Personen, Sitzungen, Ereignisse.

* **Berechnete Metriken** ![Symbol für berechnete Metriken](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): Benutzerdefinierte Metriken, die auf Standardmetriken, statischen Zahlen oder algorithmischen Funktionen basieren.

* **Vorlagen für berechnete Metriken**  <img src="./assets/adobe-logo.svg" width="18"> : Adobe-definierte Metriken, die sich ähnlich wie berechnete Metriken verhalten. Sie können sie unverändert in Workspace-Projekten verwenden oder eine Kopie speichern, um ihre Logik anzupassen.


![Workspace-Bedienfeld, in dem Metriken im linken Bereich hervorgehoben werden.](assets/cja-metrics.png)

Sie können sehen, ob eine Metrik für ![Genehmigungssymbol](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) genehmigt wurde oder nicht. Wenn Sie weitere Details zu einer Metrik wünschen, bewegen Sie den Mauszeiger über die Metrik und wählen Sie ![Infosymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) aus.


Metriken sind in ihrer Verwendung in Analysis Workspace flexibel. Ziehen Sie eine Metrik in eine leere Freiformtabelle, um die Trendansicht dieser Metrik über den Datumsbereich des Projekts anzuzeigen. Sie können auch eine Metrik ziehen, wenn eine Dimension vorhanden ist, um diese Metrik im Vergleich zu jedem Dimensionselement anzuzeigen. Wenn Sie eine Metrik auf eine vorhandene Metrik-Kopfzeile ziehen, wird sie ersetzt und durch Ziehen einer Metrik neben eine Kopfzeile können Sie beide Metriken nebeneinander sehen.

## Verwenden von Metriken in Analysis Workspace

Metriken können in Analysis Workspace auf verschiedene Arten verwendet werden. Informationen zum Hinzufügen von Metriken und anderen Komponententypen zu Analysis Workspace finden Sie unter [Verwenden von Komponenten in Analysis Workspace](/help/components/use-components-in-workspace.md).

## Berechnete Metriken erstellen

Berechnete Metriken ermöglichen es Ihnen, mithilfe einfacher Operatoren oder statistischer Funktionen einfach zu erkennen, wie sich Metriken zueinander verhalten.

Es gibt mehrere Möglichkeiten, berechnete Metriken zu erstellen. Die gewählte Methode bestimmt, ob die berechnete Metrik in der Komponentenliste für alle Projekte oder nur in dem Projekt verfügbar ist, in dem sie erstellt wurde.

### Berechnete Metriken für alle Projekte erstellen

Mit dem Generator für berechnete Metriken können Sie berechnete Metriken erstellen. Auf diese Weise werden berechnete Metriken in der Komponentenliste verfügbar und können dann in Projekten in Ihrer gesamten Organisation verwendet werden.

Informationen zum Zugriff auf den Generator für berechnete Metriken finden Sie unter [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Berechnete Metriken für ein einzelnes Projekt erstellen

Sie können schnell berechnete Metriken erstellen, die nur für das Projekt verfügbar sind, in dem sie erstellt wurden.

So erstellen Sie eine berechnete Metrik für ein einzelnes Projekt:

1. Öffnen Sie in Analysis Workspace das Projekt, in dem Sie die berechnete Metrik erstellen möchten.

1. Klicken Sie in einer Freiformtabelle mit der rechten Maustaste auf eine oder mehrere Spaltenüberschriftszellen und wählen Sie dann **[!UICONTROL Metrik aus Auswahl erstellen]**

   ![Workspace-Bedienfeld, das die Option Aus Auswahl erstellen hervorhebt](assets/create-metric-from-selection.png)

1. Um nur eine berechnete Metrik für dieses Projekt zu erstellen, wählen Sie eine der folgenden Optionen aus:

   * [!UICONTROL **divide**]

   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Hinzufügen**]

   * [!UICONTROL **Multiply**]

   Alternativ können Sie den Generator für berechnete Metriken öffnen und die berechnete Metrik für alle Projekte erstellen, indem Sie [!UICONTROL **Im Generator für berechnete Metriken öffnen**] und dann mit [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) fortfahren.

[Berechnete Metriken: implementierungslose Metriken](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=de) (3:42)

## Vergleichen von Metriken mit verschiedenen Attributionsmodellen

Wenn Sie Attributionsmodelle schnell und einfach miteinander vergleichen möchten, klicken Sie mit der rechten Maustaste auf eine Metrik und wählen Sie **[!UICONTROL Attributionsmodelle vergleichen]**:

![Workspace-Bedienfeld zur Hervorhebung von Vergleichsattributionsmodellen](assets/compare-attribution.png)

Dadurch können Sie Attributionsmodelle schnell und einfach miteinander vergleichen, ohne eine Metrik hereinzuziehen und sie zweifach zu konfigurieren.
