---
description: Unterstützende Funktionen für die Barrierefreiheit in Analysis Workspace
title: Barrierefreiheit in Analysis Workspace
feature: FAQ
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 42%

---

# Barrierefreiheit in Analysis Workspace

Erfahren Sie mehr über die Unterstützung der Barrierefreiheit in [!UICONTROL Analysis Workspace], dem führenden Analyse-Tool für Customer Journey Analytics.

Barrierefreiheit bezieht sich darauf, Produkte für Menschen mit visuellen, akustischen, kognitiven, motorischen und anderen Behinderungen nutzbar zu machen. Beispiele für Barrierefreiheitsfunktionen für Software-Produkte:

* Bildschirmlesehilfen,
* Textäquivalente für Grafiken,
* Tastaturbefehle,
* Änderung der Anzeigefarben auf hohen Kontrast,
* und mehr.

[!UICONTROL Analysis Workspace] bietet einige Tools, um die Verwendung zu ermöglichen, darunter:

## Tastaturnavigation

Die Navigation in [!UICONTROL Analysis Workspace] funktioniert von links nach rechts von oben. Die folgenden Navigationselemente erleichtern die Zugänglichkeit:

* Die Taste **[!UICONTROL Tab]** ermöglicht richtungsweisende Verknüpfungen, die innerhalb von Workspace zwischen größeren Abschnitten wechseln. Im linken Bereich können Sie mit **[!UICONTROL Tab]** auch von einer ziehbaren Option zur nächsten wechseln.
* Die ◀︎ und ▶︎ wechseln zwischen einzelnen Elementen, nachdem die Taste **[!UICONTROL Tab]** ein Element hervorgehoben hat.
* Die Taste **[!UICONTROL F6]** navigiert zum ersten Bereich im Projekt und wechselt zwischen den Visualisierungen in diesem Bereich. Anschließend wird zum nächsten Bedienfeld im Projekt gewechselt und es wird wiederholt.
* Fokusindikatoren werden angewendet, sodass sehende Tastaturbenutzer einen klaren Hinweis darauf haben, welches UI-Element derzeit den Fokus hat. Der Indikator ist ein blauer Rahmen für das Bedienfeld, das den Fokus hat. Grauer Hintergrund für die kürzlich ausgewählte Funktion und die Auswahl innerhalb der Funktion. In diesem Beispiel wurden kürzlich die Dimension [!UICONTROL Komponenten] und die Dimension &quot;Seite&quot;ausgewählt.

  ![Freiformtabelle mit einem Fokusindikator eines blauen Rands um die Freiformtabelle.](assets/focus-indicator.png)

### Tastaturnavigation zur Menüleiste

1. Drücken Sie die Tabulatortaste, bis Sie die Menüleiste erreicht haben.
1. Verwenden Sie die Pfeiltasten, um zwischen Menüs und Menüelementen zu navigieren.
1. Drücken Sie **[!UICONTROL die Eingabetaste]** , um ein Menü zu öffnen oder ein Menüelement auszuwählen.
1. Verwenden Sie **[!UICONTROL Esc]** , um ein Menü zu schließen.

### Tastaturnavigation für Drag-and-Drop-Interaktionen

[!UICONTROL Analysis Workspace] ist eine Drag-and-Drop-Benutzeroberfläche. Benutzer können jedoch stattdessen Komponenten über die Tastatur hinzufügen:

1. Registerkarte zu einer Komponente im linken Bereich.
1. Drücken Sie **[!UICONTROL die Eingabetaste]**, um auszuwählen.
1. Verwenden Sie die Pfeiltasten, um zu dem Bereich zu navigieren, in dem Sie die Komponente ablegen möchten.
1. Drücken Sie **[!UICONTROL Enter]** , um die Komponente zu platzieren.

### Tastaturbefehle (Hotkeys)

[!UICONTROL Analysis Workspace] bietet einen umfangreichen Satz von [Tastaturbefehlen](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys) für einen nahtloseren Workflow.

## Unterstützung für Bildschirmlesehilfen und Vergrößerungs-Software

Eine Bildschirmlesehilfe liest Text, der auf dem Computer-Bildschirm angezeigt wird. Es werden auch nicht textuelle Informationen wie Schaltflächenbeschriftungen oder Bildbeschreibungen in der Anwendung gelesen.

## Farbpaletten und Kontrast

[!UICONTROL Analysis Workspace] strebt die Konformität mit WCAG 2.1 AA an, einschließlich der Anforderungen an den Farbkontrast.

Darüber hinaus können Benutzer ihre eigene bevorzugte Farbpalette für ein Projekt unter **[!UICONTROL Projekt]** > **[!UICONTROL Projekteinstellungen]** > [Farbpalette](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) festlegen.

## Erforderliche Validierung

Beim Erstellen einer Komponente, einer Visualisierung oder eines Bedienfelds werden die erforderlichen Felder beim Speichern validiert. Wenn ein erforderliches Feld die Validierung nicht besteht, wird es rot und mit einem Fehlersymbol gekennzeichnet. Eine schriftliche Beschreibung erklärt, was behoben werden muss.

![Segment Builder und Indikator zur Fehlervalidierung.](assets/error-validation.png)

## Unterstützung für Barrierefreiheitsfunktionen des Betriebssystems

Analysis Workspace unterstützt integrierte Windows- und macOS-Funktionen zur Barrierefreiheit wie kontrastreichen Modus, fixierbare Schlüssel und langsame Schlüssel/Filterschlüssel. Es werden auch Informationen über die Benutzeroberfläche des Betriebssystems bereitgestellt, um die Interaktion mit Hilfstechnologien zu ermöglichen, einschließlich Bildschirmlesehilfen wie VoiceOver für macOS und NVDA unter Windows.
