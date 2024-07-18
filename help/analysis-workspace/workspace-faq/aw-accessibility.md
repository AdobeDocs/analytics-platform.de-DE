---
description: Unterstützende Funktionen für die Barrierefreiheit in Analysis Workspace
title: Barrierefreiheit in Analysis Workspace
feature: FAQ
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 100%

---

# Barrierefreiheit in Analysis Workspace

Erfahren Sie mehr über die Unterstützung der Barrierefreiheit in [!UICONTROL Analysis Workspace], dem führenden Analyse-Tool für Customer Journey Analytics.

Barrierefreiheit bezieht sich darauf, Produkte für Menschen mit visuellen, akustischen, kognitiven, motorischen und anderen Behinderungen nutzbar zu machen. Beispiele für Barrierefreiheitsfunktionen für Software-Produkte sind die Bildschirmleserunterstützung, Textäquivalente für Grafiken, Tastaturkürzel, Änderung der Anzeigefarben auf hohen Kontrast usw.

[!UICONTROL Analysis Workspace] bietet einige Tools, um die Verwendung zu ermöglichen, darunter:

## Navigieren in [!UICONTROL Workspace] mithilfe der Tastatur

Die Navigation in [!UICONTROL Analysis Workspace] funktioniert von oben nach unten und von links nach rechts. Die folgenden Navigationselemente erleichtern die Zugänglichkeit:

* Die Taste `Tab` ermöglicht Markierungskurzbefehle, mit denen Sie zwischen größeren Abschnitten in Workspace wechseln können. In der linken Leiste können Sie mit `Tab` auch von einer ziehbaren Option zur nächsten wechseln.
* Mit den `left/right arrows` können Sie zwischen einzelnen Elementen wechseln, nachdem Sie sie mit `Tab` markiert haben.
* Mit `F6` navigieren Sie zum ersten Bedienfeld im Projekt und können zwischen den Visualisierungen in diesem Bedienfeld wechseln. Anschließend wird zum nächsten Bedienfeld im Projekt gewechselt und es wird wiederholt.
* Wir wenden Fokusindikatoren an, sodass sehende Tastaturbenutzer einen klaren Hinweis darauf haben, welches Element der Benutzeroberfläche derzeit im Fokus ist. Der Indikator ist ein blauer Rand um das ausgewählte Element herum.

  ![Freiformtabelle mit einem Fokusindikator eines blauen Rands um die Freiformtabelle.](assets/focus-indicator.png)

### Tastaturnavigation zur Menüleiste

1. Drücken Sie die Tabulatortaste, bis Sie die Menüleiste erreicht haben.
1. Verwenden Sie die Pfeiltasten nach links/rechts, um zum gewünschten Menü zu navigieren.
1. Drücken Sie die Taste `Enter`, um das Menü auszuwählen und seine Optionen anzuzeigen.
1. Verwenden Sie die Pfeiltasten nach oben/unten, um zu der gewünschten Menüoption zu navigieren.
1. Drücken Sie `Enter`, um die Option auszuwählen.

### Tastaturnavigation für Drag-and-Drop-Interaktionen

[!UICONTROL Analysis Workspace] ist eine Drag-and-Drop-Benutzeroberfläche. Benutzer können jedoch stattdessen Komponenten über die Tastatur hinzufügen:

1. Tippen Sie auf eine Komponente in der linken Leiste.
1. Drücken Sie zum Auswählen `Enter`.
1. Verwenden Sie die Pfeiltasten, um zu dem Bereich zu navigieren, in dem Sie die Komponente ablegen möchten.
1. Drücken Sie `Enter`, um die Komponente zu platzieren.

### Tastaturbefehle (Hotkeys)

[!UICONTROL Analysis Workspace] bietet eine umfangreiche Auswahl an [Tastaturbefehlen](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=de) für einen nahtlosen Workflow. Nachfolgend sind einige allgemeine Kurzbefehle für die Navigation, die Erstellung von Analysen und die Demokratisierung von Erkenntnissen aufgeführt.

#### Navigation

| Tastaturbefehl | Aktion |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Zu verschiedenen Leisten wechseln: [!UICONTROL Bedienfelder], [!UICONTROL Visualisierungen] oder [!UICONTROL Komponenten] |
| `[Alt + Left / Right]` | Zwischen Bedienfeldern navigieren |
| `[Alt + M]` | Alle Bedienfelder reduzieren/erweitern |
| `[Alt + Ctrl + M]` | Aktives Bedienfeld reduzieren/erweitern |
| `[Ctrl + /]` | Linke Leiste durchsuchen |

#### Erstellung von Analysen

| Tastaturbefehl | Aktion |
| --- | --- |
| `[Alt + 1]` | Neue Freiformtabelle |
| `[Ctrl + Shift + C]` | Neue berechnete Metrik |
| `[Ctrl + Shift + D]` | Neuer Datumsbereich |
| `[Ctrl + Shift + E]` | Neuer Filter |
| `[Ctrl + Z]` | Rückgängig machen |
| `[Component drag + Shift]` | Einen Dropdown-Filter erstellen |

#### Demokratisierung

| Tastaturbefehl | Aktion |
| --- | --- |
| `[Ctrl + S]` | Speichern |
| `[Ctrl + Shift + G]` | Kuratieren |
| `[Ctrl + G]` | Freigeben |
| `[Alt + Shift + S]` | Zeitplan |
| `[Alt + L]` | Link zum Projekt abrufen |
| `[Ctrl + Shift + B]` | PDF herunterladen |

## Unterstützung für Bildschirmlesehilfen und Vergrößerungs-Software

Eine Bildschirmlesehilfe liest Text, der auf dem Computer-Bildschirm angezeigt wird. Es werden auch nicht textuelle Informationen wie Schaltflächenbeschriftungen oder Bildbeschreibungen in der Anwendung gelesen, die in Barrierefreiheits-Tags oder Attributen bereitgestellt werden.

## Farbpaletten und Kontrast

[!UICONTROL Analysis Workspace] strebt die Konformität mit WCAG 2.1 AA an, einschließlich der Anforderungen an den Farbkontrast.

Darüber hinaus können Benutzer ihre eigene bevorzugte Farbpalette für ein Projekt unter **[!UICONTROL Projekt]** > **[!UICONTROL Projekteinstellungen]** > [Farbpalette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=de) festlegen.

## Erforderliche Feldvalidierung in Komponenten-Buildern

Beim Erstellen einer Komponente werden die erforderlichen Felder beim Speichern validiert. Wenn ein erforderliches Feld die Validierung nicht erfolgreich durchläuft, wird es rot und mit einem Fehlersymbol gekennzeichnet. Es wird eine schriftliche Beschreibung des Problems angezeigt, das behoben werden muss.

Sobald eine Komponente vollständig validiert ist, wird der Builder durch Klicken auf `Save` geschlossen.

![Segment Builder und Indikator zur Fehlervalidierung.](assets/error-validation.png)

## Unterstützung für Barrierefreiheitsfunktionen des Betriebssystems

Analysis Workspace unterstützt integrierte MS Windows- und macOS-Eingabehilfen wie den Modus für hohen Kontrast, Einrastfunktionen und Anschlaggeschwindigkeit/Anschlagverzögerung. Es werden auch Informationen über die Benutzeroberfläche des Betriebssystems bereitgestellt, um die Interaktion mit Hilfstechnologien zu ermöglichen, einschließlich Bildschirmlesehilfen wie VoiceOver für macOS und NVDA unter Windows.
