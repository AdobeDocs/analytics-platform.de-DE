---
description: Überblick über die Journey-Arbeitsfläche
title: Journey-Arbeitsfläche
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 25969de61f23cf0690a130127fcc1442b9806a35
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 1%

---

# Überblick über die Journey-Arbeitsfläche

Die Journey-Arbeitsflächen-Visualisierung ermöglicht es Ihnen, die Journey zu analysieren und detaillierte Einblicke zu erhalten, die Sie Ihren Benutzenden und Kunden bieten. Damit können Sie eine Journey von Grund auf neu definieren oder eine von Journey Optimizer anzeigen und dann sehen, wie Personen die Journey verlassen (ausgefallen) oder weiter durchlaufen (durchgefallen) haben.

Sie können [Analysen von Benutzerereignissen erstellen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) indem Sie eine beliebige Kombination aus Journey, Dimensionselementen, Filtern und Datumsbereichen verwenden, um Journey-Knoten zu erstellen. Verbinden Sie die -Knoten, um den Journey-Fluss zu erstellen, und schließen Sie mehrere Pfade und Entscheidungspunkte ein. Ziehen Sie Knoten auf die Arbeitsfläche, um die Ereignisse und Bedingungen des Journey neu anzuordnen. Daten werden bei Änderungen in Echtzeit aktualisiert.

[Knoten sind ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) „Eventueller Pfad“ verbunden, d. h. Besucher werden gezählt, solange sie letztendlich von einem Knoten zum anderen wechseln, unabhängig von Ereignissen, die zwischen den beiden Knoten auftreten. Die Zeit, die Benutzenden zum Verschieben auf dem Pfad zugewiesen wird, wird durch die Container-Einstellung bestimmt.

![Journey-Arbeitsfläche](assets/journey-canvas.png)

## Wichtigste Funktionen

Zu den wichtigsten Funktionen der Journey-Arbeitsflächen-Visualisierung gehören:

* Detaillierte Analyse der Fallout- und Fallthrough-Analyse, die auch die komplexesten Journey-Benutzerinnen und -Benutzer berücksichtigt.

* Eine Arbeitsfläche zum Zuordnen und Visualisieren der verschiedenen Einstiegspunkte, Knoten und Pfade einer Journey.

* Drag-and-Drop-Interaktionen zum Hinzufügen von Komponenten zur Arbeitsfläche und zum Neupositionieren vorhandener Knoten.

* Die Option, innerhalb der Journey-Arbeitsfläche Journey-Analysen zu erstellen oder diese automatisch auf der Grundlage von Journey Optimizer-Journey zu erstellen.

## Potenzielle Erkenntnisse

Journey Canvas bietet umsetzbare Einblicke für die komplexesten Journey.

### Pfad mit der höchsten Konversionsrate {#conversion-rate-caption}

Der markanteste Einblick in die Journey-Leinwand wird oben auf der Leinwand selbst als Bildunterschrift angezeigt.

Diese Beschriftung fasst zusammen, welcher der Pfade auf der Journey die höchste Konversionsrate aufwies.

Wenn die Journey mehrere Startknoten enthält, sieht die Beschriftung wie folgt aus:

![Journey Canvas Insight-Beschriftung](assets/journey-canvas-caption.png)

Wenn die Journey einen einzelnen Startknoten enthält, sieht die Beschriftung wie folgt aus:

![Journey Canvas Insight-Beschriftung, einzelner Startknoten](assets/journey-canvas-caption-singlestart.png)

Beachten Sie beim Interpretieren dieser Beschriftung Folgendes:

* Ein _path_ wird als ein Startknoten definiert, der über Pfeile mit einem Endknoten verbunden ist, wobei eine beliebige Anzahl von Knoten zwischen ihnen verbunden ist.

* Die Berechnung der Konversionsrate hängt vom Typ des Journey ab (die Anzahl der Start- und Endknoten in der Journey und ob sich die Pfade zwischen ihnen schneiden).

  Die folgende Tabelle beschreibt, wie die Konversionsraten anhand des Journey-Typs berechnet werden:

  | Journey-Typ | Berechnung des Umrechnungskurses | Beispiel |
  |---------|----------|---------|
  | **Ein einzelner Start- und ein einzelner Endknoten** | Die Konversionsrate wird berechnet, indem die Zahl des Endknotens durch die Zahl des Startknotens dividiert wird. | ![Journey mit mehreren Starts, die zu einem gemeinsamen Knoten konvergieren](assets/journey-canvas-single-path.png) |
  | **Ein einzelner Start- und mehrere Endknoten** | Die Konversionsrate wird berechnet, indem der Endknoten mit der höchsten Zahl gefunden und durch die Zahl des Startknotens dividiert wird. | ![Journey mit mehreren Starts, die zu einem gemeinsamen Knoten konvergieren](assets/journey-canvas-singlestart-multiend.png) |
  | **Mehrere eigenständige Pfade, wobei jeder Pfad einen einzelnen Start- und einen einzelnen Endknoten enthält** | Die Konversionsrate wird berechnet, indem die Zahl des Endknotens durch die Zahl des Startknotens dividiert wird. Der Pfad mit der höchsten Konversionsrate wird in der Beschriftung beschrieben. | ![Journey mit mehreren Starts, die zu einem gemeinsamen Knoten konvergieren](assets/journey-canvas-multi-start-separate.png) |
  | **Mehrere Startknoten, die zu einem beliebigen Zeitpunkt im Journey zu einem gemeinsamen Knoten zusammenlaufen** | Die Konversionsrate wird berechnet, indem der Endknoten mit der höchsten Zahl gefunden und durch die Zahl des Startknotens mit der niedrigsten Zahl dividiert wird. | ![Journey mit mehreren Starts, die zu einem gemeinsamen Knoten konvergieren](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, Fallout und mehr

Im Folgenden finden Sie einige Beispiele für weitere Einblicke, die Journey-Arbeitsfläche bieten kann. Sie können auswählen, ob diese Einblicke auf allen Personen in der Datenansicht, allen Personen, die den Journey gestartet haben, oder allen Personen aus dem vorherigen Knoten des Journey basieren.

#### Fall-through (Verbleib)

* Die Anzahl und der Prozentsatz der Personen, die die Journey abgeschlossen haben (am Endknoten angekommen)

* Die Anzahl und der Prozentsatz der Personen, die an einem bestimmten Knoten des Journey angekommen sind

* Der häufigste Schritt, der nach oder vor einem bestimmten Knoten des Journey erfolgte

#### Fallout

* Die Knoten des Journey, an denen die Personen am häufigsten aus dem Journey gefallen sind (kamen nie an einem der unmittelbar nächsten Knoten an)

#### Zusätzliche Daten für jeden Knoten

* Fügen Sie für jeden Knoten des Journey eine Aufschlüsselungsdimension hinzu, um zusätzliche Daten für diesen bestimmten Knoten anzuzeigen

## Wählen Sie zwischen Journey-Arbeitsfläche, Fallout oder Fluss -Visualisierungen

Die Journey-Arbeitsflächen-Visualisierung weist Ähnlichkeiten mit der [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) und der [Flow-Visualisierung](/help/analysis-workspace/visualizations/c-flow/flow.md) auf, jedoch mit wichtigen Unterschieden.

### Unterschiede verstehen

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Verwendung der Journey-Arbeitsfläche

Journey Canvas ist wichtig für:

* Fallout-Analyse mit Journey mit mehreren Einstiegspunkten und Pfaden.

* Nichtlineare Journey mit mehreren Einstiegspunkten und Pfaden mit einer vordefinierten Seitensequenz.

* Explorative Ad-hoc-Analyse, die auf einem vordefinierten Journey basiert.

* Analyse, für die eine andere primäre Metrik als Sitzung, Person oder Vorfälle erforderlich ist.

* Detaillierte Analyse der Journey, die ihren Ursprung in Adobe Journey Optimizer haben.

Verwenden Sie [die obige ](#understand-the-differences)), um die Unterschiede zwischen Journey-Arbeitsfläche-, Fallout- und Fluss -Visualisierungen zu verstehen.

## Analysieren von Journey Optimizer Journey

>[!NOTE]
>
>Wenn Ihr Unternehmen keinen Zugriff auf Journey Optimizer hat, können Sie weiterhin [Analysen auf der Journey-Arbeitsfläche erstellen](#build-analyses-in-customer-journey-analytics).

Das Analysieren von Journey Optimizer-Journey auf der Journey-Arbeitsfläche bietet vertiefte, umsetzbare Einblicke in die Interaktion von Personen mit einer Journey.

Wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche analysieren, wird die Journey in der gleichen Reihenfolge, Reihenfolge und Struktur angezeigt wie in Journey Optimizer. Wenn Sie wesentliche Änderungen an einer Journey auf der Journey-Arbeitsfläche vornehmen, [werden Änderungen nicht mehr von Journey Optimizer synchronisiert](#synchronization-between-journey-optimizer-and-journey-canvas).

### Vorteile der Analyse von Journey Optimizer Journey mit Journey Canvas

Journey Canvas bietet eine gründliche Analyse, die in Journey Optimizer nicht möglich ist.

Die Verwendung der Journey-Arbeitsfläche zur Analyse von Journey , die in Journey Optimizer erstellt wurden, bietet verschiedene Vorteile:

* Erstellen Sie Ereignisse mithilfe von Customer Journey Analytics-Dimensionen, -Metriken, -Filtern oder -Datumsbereichen.

  In Journey Optimizer muss ein technischer Anwender ein Ereignis erstellen, bevor es zu einer Journey hinzugefügt werden kann.

* Erstellen Sie Zielgruppen basierend auf einem benutzerdefinierten Knoten, den Sie erstellen (startet den Customer Journey Analytics-Zielgruppen-Builder).

  In Journey Optimizer können Sie Zielgruppen nur für vordefinierte Aktivitäten erstellen.

* Analyse von Fallthrough und Fallout

* Aufschlüsseln von Ereignissen mit einer beliebigen Dimension

* Kombinieren von Ereignissen

* Ereignisse verbinden

* Ereignisse umbenennen und löschen

* Viel mehr

### Synchronisation zwischen Journey Optimizer und Journey-Arbeitsfläche

Nachdem Sie eine Analyse einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche erstellt haben, werden die Daten nur in eine Richtung synchronisiert, von Journey Optimizer zur Journey-Arbeitsfläche. Das bedeutet, dass Änderungen, die an einer Journey auf der Journey-Arbeitsfläche vorgenommen werden, nie in Journey Optimizer übernommen werden.

Darüber hinaus werden Änderungen an einer Journey in Journey Optimizer mit der Journey-Arbeitsfläche synchronisiert [nur wenn die Journey auf der Journey-Arbeitsfläche nicht wesentlich geändert wurde](#differences-after-modifying-a-journey-in-journey-canvas). Nachdem Sie eine Journey auf der Journey-Arbeitsfläche geändert haben, werden alle Änderungen, die Sie an der Journey in Journey Optimizer vornehmen, nicht auf der Journey-Arbeitsfläche angezeigt. Um die Änderungen auf der Journey-Arbeitsfläche anzuzeigen, können Sie die Journey löschen und [in der Journey-Arbeitsfläche neu erstellen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Unterschiede nach dem Ändern einer Journey auf der Journey-Arbeitsfläche {#differences-after-modifying}

Nachdem Sie eine Journey Optimizer-Journey in der Journey-Arbeitsfläche geändert haben, können Änderungen an der Datenverarbeitung, den verfügbaren Funktionen und dem Synchronisierungsverhalten auftreten.

Wenn Sie eine wesentliche Änderung an einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche vornehmen, können Änderungen an der Datenverarbeitung, den verfügbaren Funktionen und dem Synchronisierungsverhalten auftreten. Eine wesentliche Änderung umfasst eine der folgenden:

* Knoten hinzufügen oder entfernen

* Hinzufügen oder Entfernen eines Pfeils zwischen Knoten

* Ändern von Komponenten auf einem Knoten

Wenn Sie andere Änderungen an einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche vornehmen, z. B. einen Knoten ziehen oder eine Aufschlüsselung hinzufügen, gelten die in den folgenden Abschnitten beschriebenen Unterschiede nicht.

>[!NOTE]
>
>Um die Journey in den Originalzustand zurückzuversetzen, drücken Sie Strg+Z, nachdem Sie Ihre erste Änderung auf der Journey-Arbeitsfläche vorgenommen haben. Alternativ können Sie die Journey löschen und [auf der Journey-Arbeitsfläche neu erstellen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Unterschiede bei der Datenverarbeitung

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, werden Sie möglicherweise Änderungen an Ihren Daten feststellen, wenn Ihre Journey Metriken enthält, die nicht standardmäßige Attributionsmodelle aufweisen.

Dies liegt daran, dass Sie im Gegensatz zu Journey Optimizer mit der Journey-Arbeitsfläche mehrere Dimensionen auf eine Journey anwenden können. Diese Funktion bedeutet, dass [Metrikattribution](/help/data-views/component-settings/attribution.md) nicht unterstützt wird.

#### Funktionsunterschiede

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, ändern sich je nach Ihren Änderungen die Optionen, [!UICONTROL **in der**] „Pfeileinstellungen“ verfügbar sind. Weitere Informationen finden Sie unter [Konfigurieren von Einstellungen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Das [!UICONTROL **Knotentyp**]-Feld ist nur in Journey Optimizer verfügbar. Sie ist nicht verfügbar, wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche anzeigen, unabhängig davon, ob Sie Änderungen an der Journey auf der Journey-Arbeitsfläche vornehmen oder nicht.

#### Synchronisationsunterschiede

Änderungen an einer Journey in Journey Optimizer werden nur dann mit der Journey-Arbeitsfläche synchronisiert, wenn die Journey auf der Journey-Arbeitsfläche unverändert bleibt.

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, werden alle Änderungen, die Sie an der Journey in Journey Optimizer vornehmen, nicht auf der Journey-Arbeitsfläche angezeigt. Um die Änderungen auf der Journey-Arbeitsfläche anzuzeigen, können Sie die Journey löschen und [in der Journey-Arbeitsfläche neu erstellen](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Terminologische Unterschiede zwischen Journey Optimizer und Customer Journey Analytics

Bestimmte Begriffe, die in Journey Optimizer etwas bedeuten, bedeuten etwas Anderes im Customer Journey Analytics. Bei Verwendung der Journey-Arbeitsfläche werden die Customer Journey Analytics-Begriffe verwendet.

| Begriff | Journey-Arbeitsfläche | Journey Optimizer |
|---------|----------|---------|
| **Ereignis** | Eine von mehreren Standardmetriken, die im Customer Journey Analytics verfügbar sind. Diese Metrik zählt Dinge wie Umsatz, Abonnements oder generierte Leads. | Die Aktivitätskategorie, in der ein personalisierter Journey Trigger wird, z. B. ein Online-Kauf. |

### Analysieren einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche

Informationen zum Analysieren einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche finden Sie unter [Konfigurieren einer Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Erstellen von Analysen auf der Journey-Arbeitsfläche

Sie können Analysen auf der Journey-Arbeitsfläche erstellen, die auf allen in Analysis Workspace verfügbaren Dimensionen oder Metriken basieren. Sie können auch Journey analysieren, die in Journey Optimizer erstellt wurden. Weitere Informationen finden Sie unter [Konfigurieren einer Journey-Arbeitsflächen-](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
