---
description: Überblick über die Journey-Arbeitsfläche
title: Journey-Arbeitsfläche
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 27c76e5090e4dfcfc00fd11c7a67574dc6af1c63
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 1%

---

# Überblick über die Journey-Arbeitsfläche

{{release-limited-testing}}

Mit der Journey-Arbeitsflächenvisualisierung können Sie tief greifende Einblicke in die Journey erhalten, die Sie Ihren Benutzern und Kunden zur Verfügung stellen. Es ermöglicht Ihnen, eine Journey von Grund auf zu definieren oder eine von Journey Optimizer anzuzeigen, dann sehen Sie, wie die Menschen verlassen (fiel aus) oder weiter durch (fiel durch) die Journey.

Sie können [ Analysen von Journey erstellen, indem Sie eine beliebige Kombination aus Ereignissen, Dimensionselementen, Filtern und Datumsbereichen verwenden, um Journey-Knoten zu erstellen. ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) Verbinden Sie die Knoten, um den Journey zu erstellen, und schließen Sie mehrere Pfade und Entscheidungspunkte ein. Ziehen Sie Knoten auf die Arbeitsfläche, um die Ereignisse und Bedingungen der Journey neu anzuordnen. Daten werden bei Änderungen in Echtzeit aktualisiert.

[Knoten sind mit ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) als &quot;letztendlichen Pfad&quot;verbunden. Das bedeutet, dass Besucher gezählt werden, solange sie sich schließlich von einem Knoten zum anderen bewegen, unabhängig von Ereignissen, die zwischen den beiden Knoten auftreten. Die Zeit, die Benutzern für das Verschieben entlang des Pfads zugewiesen wird, wird durch die Containereinstellung bestimmt.

![Journey canvas](assets/journey-canvas.png)

## Wichtigste Funktionen

Zu den wichtigsten Funktionen der Visualisierung der Journey-Arbeitsfläche gehören:

* Tief greifende Analyse von Fallout und Fallthrough, die die komplexesten Journey-Benutzererlebnisse abdeckt.

* Eine Arbeitsfläche zum Zuordnen und Visualisieren der verschiedenen Einstiegspunkte, Knoten und Pfade eines Journey-Benutzers.

* Drag &amp; Drop von Interaktionen zum Hinzufügen von Komponenten zur Arbeitsfläche und zum Neupositionieren vorhandener Knoten.

* Die Option zum Erstellen von Analysen von Journey-Benutzern auf der Journey-Arbeitsfläche oder zum automatischen Erstellen dieser Analysen auf der Grundlage von Journey Optimizer-Journey.

## Potenzielle Erkenntnisse

Journey-Arbeitsfläche bietet umsetzbare Einblicke für die komplexesten Journey.

### Pfad mit der höchsten Konversionsrate {#conversion-rate-caption}

Der auffälligste Einblick in die Journey-Arbeitsfläche wird als Beschriftung oben auf der Arbeitsfläche angezeigt.

Diese Beschriftung fasst zusammen, welche von allen Pfaden im Journey die höchste Konversionsrate aufwies.

Wenn die Journey mehrere Startknoten enthält, sieht die Beschriftung wie folgt aus:

![Journey canvas insight caption](assets/journey-canvas-caption.png)

Wenn die Journey einen einzelnen Startknoten enthält, sieht die Beschriftung wie folgt aus:

![Journey canvas insight caption single start node](assets/journey-canvas-caption-singlestart.png)

Beachten Sie bei der Interpretation dieser Beschriftung Folgendes:

* Ein _path_ wird als ein Startknoten definiert, der durch Pfeile mit einem Endknoten verbunden ist, wobei eine beliebige Anzahl von Knoten zwischen ihnen verbunden ist.

* Die Berechnung der Konversionsrate hängt vom Typ der Journey ab (die Anzahl der Start- und Endknoten im Journey sowie davon, ob sich die Pfade zwischen ihnen überschneiden).

  In der folgenden Tabelle wird beschrieben, wie Konversionsraten basierend auf dem Journey-Typ berechnet werden:

  | Journey-Typ | Berechnung der Konversionsrate | Beispiel |
  |---------|----------|---------|
  | **Ein einzelner Startknoten und ein einzelner Endknoten** | Die Konversionsrate wird berechnet, indem die Zahl des Endknotens durch die des Anfangsknotens geteilt wird. | ![Journey mit mehreren Beginns, die in einen gemeinsamen Knoten konvertieren](assets/journey-canvas-single-path.png) |
  | **Ein einzelner Startknoten und mehrere Endknoten** | Die Konversionsrate wird berechnet, indem der Endknoten mit der höchsten Zahl ermittelt und durch den Anfangsknoten geteilt wird. | ![Journey mit mehreren Beginns, die in einen gemeinsamen Knoten konvertieren](assets/journey-canvas-singlestart-multiend.png) |
  | **Mehrere eigenständige Pfade mit jedem Pfad, der einen einzelnen Startknoten und einen einzelnen Endknoten enthält** | Die Konversionsrate wird berechnet, indem die Zahl des Endknotens durch die des Anfangsknotens geteilt wird. Der Pfad mit der höchsten Konversionsrate wird in der Beschriftung beschrieben. | ![Journey mit mehreren Beginns, die in einen gemeinsamen Knoten konvertieren](assets/journey-canvas-multi-start-separate.png) |
  | **Mehrere Startknoten, die an einem beliebigen Punkt im Journey in einen gemeinsamen Knoten konvertieren** | Die Konversionsrate wird berechnet, indem der Endknoten mit der höchsten Nummer ermittelt und durch die Division der Nummer durch die des Anfangsknotens mit der niedrigsten Nummer geteilt wird. | ![Journey mit mehreren Beginns, die in einen gemeinsamen Knoten konvertieren](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, Fallout und mehr

Im Folgenden finden Sie einige Beispiele für weitere Einblicke, die Journey-Arbeitsfläche bieten kann. Sie können auswählen, ob diese Einblicke auf allen Personen in der Datenansicht, allen Personen, die die Journey gestartet haben, oder allen Personen aus dem vorherigen Knoten der Journey basieren.

#### Fall-through (Verbleib)

* Anzahl und Prozentsatz der Personen, die die Journey abgeschlossen haben (am Endknoten angekommen)

* Anzahl und Prozentsatz der Personen, die zu einem bestimmten Knoten der Journey gelangt sind

* Der häufigste Schritt, der nach oder vor einem bestimmten Knoten der Journey erfolgte

#### Fallout

* Die Knoten der Journey, wo die Leute am häufigsten aus der Journey herausgefallen sind (sie kamen nie an einem der unmittelbar nächsten Knoten an)

#### Zusätzliche Daten für jeden Knoten

* Fügen Sie auf einem beliebigen Knoten der Journey eine Aufschlüsselungsdimension hinzu, um zusätzliche Daten für diesen Knoten anzuzeigen

## Wählen Sie zwischen Journey-Arbeitsfläche, Fallout- oder Fluss-Visualisierungen

Die Visualisierung der Journey-Arbeitsfläche weist Ähnlichkeiten mit der [Fallout-Visualisierung](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) und der [Flussvisualisierung](/help/analysis-workspace/visualizations/c-flow/flow.md) auf, allerdings mit wichtigen Unterschieden.

### Unterschiede verstehen

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Verwendung der Journey-Arbeitsfläche

Journey-Arbeitsfläche ist für Folgendes unerlässlich:

* Fallout-Analyse mit Journey mit mehreren Einstiegspunkten und Pfaden.

* Nicht lineare Journey mit mehreren Einstiegspunkten und Pfaden mit einer vordefinierten Seitensequenz.

* Sondierende Ad-hoc-Analysen, die auf einer vordefinierten Journey basieren.

* Analyse, für die eine andere primäre Metrik als Sitzung, Person oder Ereignisse erforderlich ist.

* Detaillierte Analyse der Journey aus Adobe Journey Optimizer.

Verwenden Sie [die obige Tabelle](#understand-the-differences), um die Unterschiede zwischen Journey-Arbeitsfläche, Trichteranalyse und Flussvisualisierungen zu verstehen.

## Journey Optimizer-Journey analysieren

>[!NOTE]
>
>Wenn Ihr Unternehmen keinen Zugriff auf Journey Optimizer hat, können Sie weiterhin [Analysen in der Journey-Arbeitsfläche](#build-analyses-in-customer-journey-analytics) erstellen.

Die Analyse von Journey Optimizer-Journey in der Journey-Arbeitsfläche bietet tiefe, umsetzbare Einblicke in die Interaktion der Menschen mit einer Journey.

Wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche analysieren, wird die Journey mit der gleichen Reihenfolge, Sequenz und Struktur angezeigt wie in Journey Optimizer. Wenn Sie Änderungen an einer Journey in der Journey-Arbeitsfläche vornehmen können, werden [Änderungen nicht mehr von Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas) synchronisiert.

### Vorteile der Analyse von Journey Optimizer-Journey mit Journey-Arbeitsfläche

Journey-Arbeitsfläche bietet eine tiefgründige Analyse, die in Journey Optimizer nicht möglich ist.

Die Verwendung der Journey-Arbeitsfläche zur Analyse von Journey, die in Journey Optimizer erstellt wurden, bietet verschiedene Vorteile:

* Erstellen Sie Customer Journey Analytics-Ereignisse mit beliebigen Dimensionen, Metriken, Filtern oder Datumsbereichen.

  In Journey Optimizer muss ein technischer Anwender ein Ereignis erstellen, bevor es zu einer Journey hinzugefügt werden kann.

* Erstellen Sie Zielgruppen basierend auf einem benutzerdefinierten Knoten, den Sie erstellen (startet den Customer Journey Analytics-Audience-Builder).

  In Journey Optimizer können Sie Zielgruppen nur für vordefinierte Aktivitäten erstellen.

* Fallthrough und Fallout analysieren

* Aufschlüsseln von Ereignissen mit einer beliebigen Dimension

* Ereignisse kombinieren

* Ereignisse verbinden

* Ereignisse umbenennen und löschen

* Mehr

### Synchronisation zwischen Journey Optimizer und Journey-Arbeitsfläche

Nachdem Sie eine Analyse einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche erstellt haben, werden die Daten nur in eine Richtung synchronisiert, von Journey Optimizer auf die Journey-Arbeitsfläche. Das bedeutet, dass Änderungen an einer Journey in der Journey-Arbeitsfläche nie in Journey Optimizer übernommen werden.

Darüber hinaus werden Änderungen an einer Journey in Journey Optimizer nur dann mit der Journey-Arbeitsfläche synchronisiert, wenn die Journey in der Journey-Arbeitsfläche unverändert bleibt. Nachdem Sie eine Journey in der Journey-Arbeitsfläche geändert haben, werden alle Änderungen, die Sie an der Journey in Journey Optimizer vornehmen, nicht in der Journey-Arbeitsfläche angezeigt. Um die Änderungen auf der Journey-Arbeitsfläche zu sehen, können Sie die Journey in der Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) löschen und [neu erstellen.

### Unterschiede nach der Änderung einer Journey in der Journey-Arbeitsfläche {#differences-after-modifying}

Nachdem Sie eine Journey Optimizer-Journey in der Journey-Arbeitsfläche geändert haben, können Änderungen an der Datenverarbeitung, den verfügbaren Funktionen und dem Synchronisierungsverhalten auftreten.

Wenn Sie eine wesentliche Änderung an einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche vornehmen, können Änderungen an der Datenverarbeitung, den verfügbaren Funktionen und dem Synchronisierungsverhalten auftreten. Eine wesentliche Änderung umfasst eine der folgenden Aspekte:

* Knoten hinzufügen oder entfernen

* Hinzufügen oder Entfernen eines Pfeils zwischen Knoten

* Komponenten auf einem Knoten ändern

Wenn Sie andere Änderungen an einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche vornehmen, z. B. das Ziehen eines Knotens oder das Hinzufügen einer Aufschlüsselung, gelten die in den folgenden Abschnitten beschriebenen Unterschiede nicht.

>[!NOTE]
>
>Um den Originalzustand der Journey wiederherzustellen, können Sie Strg+Z drücken, nachdem Sie Ihre erste Änderung in der Journey-Arbeitsfläche vorgenommen haben. Oder Sie können die Journey in der Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) löschen und [neu erstellen

#### Datenverarbeitungsunterschiede

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, werden Sie möglicherweise Änderungen an Ihren Daten bemerken, wenn Ihre Journey Metriken enthält, die nicht standardmäßige Attributionsmodelle aufweisen.

Dies liegt daran, dass Sie im Gegensatz zu Journey Optimizer mit der Journey-Arbeitsfläche mehrere Dimensionen innerhalb einer Journey anwenden können. Diese Funktion bedeutet, dass die [Metrikzuordnung](/help/data-views/component-settings/attribution.md) nicht unterstützt wird.

#### Funktionsunterschiede

Nachdem Sie eine Journey Optimizer-Journey auf der Arbeitsfläche &quot;Journey&quot;geändert haben, ändern sich die Optionen, die im Dropdown-Feld [!UICONTROL **Pfeileinstellungen**] verfügbar sind, je nach Ihren Änderungen. Weitere Informationen finden Sie unter [Einstellungen konfigurieren](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

Das Feld [!UICONTROL **Knotentyp**] ist nur in Journey Optimizer verfügbar. Sie ist nicht verfügbar, wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche anzeigen, unabhängig davon, ob Sie Änderungen an der Journey auf der Journey-Arbeitsfläche vornehmen.

#### Unterschiede bei der Synchronisierung

Änderungen, die an einer Journey in der Journey Optimizer-Arbeitsfläche vorgenommen wurden, werden nur dann mit der Journey-Arbeitsfläche synchronisiert, wenn die Journey in der Journey-Arbeitsfläche unverändert bleibt.

Nachdem Sie eine Journey Optimizer-Journey in der Journey-Arbeitsfläche geändert haben, werden alle Änderungen, die Sie an der Journey in Journey Optimizer vornehmen, nicht in der Arbeitsfläche zum Journey dargestellt. Um die Änderungen auf der Journey-Arbeitsfläche zu sehen, können Sie die Journey in der Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) löschen und [neu erstellen.

### Terminologieunterschiede zwischen Journey Optimizer und Customer Journey Analytics

Bestimmte Begriffe, die eine Sache in Journey Optimizer bedeuten, bedeuten etwas Anderes im Customer Journey Analytics. Bei Verwendung der Journey-Arbeitsfläche werden die Customer Journey Analytics-Begriffe verwendet.

| Begriff | Journey-Arbeitsfläche | Journey Optimizer |
|---------|----------|---------|
| **Ereignis** | Eine von mehreren Standardmetriken, die in Customer Journey Analytics verfügbar sind. Diese Metrik zählt Dinge wie Umsatz, Abonnements oder generierte Leads. | Die Aktivitätskategorie, die eine personalisierte Journey Trigger, z. B. einen Online-Kauf. |

### Analysieren einer Journey Optimizer-Journey in der Journey-Arbeitsfläche

Informationen zum Analysieren einer Journey Optimizer-Journey in der Journey-Arbeitsfläche finden Sie unter [Konfigurieren einer Visualisierung der Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Erstellen von Analysen in der Journey-Arbeitsfläche

Sie können Analysen in der Journey-Arbeitsfläche erstellen, die auf beliebigen Dimensionen oder Metriken basieren, die in Analysis Workspace verfügbar sind. Sie können auch Journey analysieren, die in Journey Optimizer erstellt wurden. Weitere Informationen finden Sie unter [Konfigurieren einer Journey-Arbeitsflächenvisualisierung](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
