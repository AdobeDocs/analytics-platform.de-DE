---
description: Übersicht über die Journey-Arbeitsfläche
title: Journey-Arbeitsfläche
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: fb2a24d6f7a93e941a76db0d10c515381c476c31
workflow-type: tm+mt
source-wordcount: '1215'
ht-degree: 3%

---

# Übersicht über die Journey-Arbeitsfläche

Mit der Journey-Arbeitsflächenvisualisierung können Sie tief greifende Einblicke in die Journey erhalten, die Sie Ihren Benutzern und Kunden zur Verfügung stellen. Es ermöglicht Ihnen, eine Journey von Grund auf zu definieren oder eine von Journey Optimizer anzuzeigen, dann sehen Sie, wie die Menschen verlassen (fiel aus) oder weiter durch (fiel durch) die Journey.

Sie können Analysen von Journey erstellen, indem Sie eine beliebige Kombination aus Ereignissen, Dimensionselementen, Filtern und Datumsbereichen verwenden, um Journey-Knoten zu erstellen. Verbinden Sie die Knoten, um den Journey zu erstellen, und schließen Sie mehrere Pfade und Entscheidungspunkte ein. Ziehen Sie Knoten auf die Arbeitsfläche, um die Ereignisse und Bedingungen der Journey neu anzuordnen. Daten werden in Echtzeit aktualisiert, wenn Sie Änderungen vornehmen.

## Wichtigste Funktionen

Zu den wichtigsten Funktionen der Visualisierung der Journey-Arbeitsfläche gehören:

* Tief greifende Analyse von Fallout und Fallthrough, die die komplexesten Journey-Benutzererlebnisse abdeckt.

* Eine Arbeitsfläche zum Zuordnen und Visualisieren der verschiedenen Einstiegspunkte, Knoten und Pfade eines Journey-Benutzers.

* Drag &amp; Drop von Interaktionen zum Hinzufügen von Komponenten zur Arbeitsfläche und zum Neupositionieren vorhandener Knoten.

* Die Option zum Erstellen von Analysen von Journey-Benutzern auf der Journey-Arbeitsfläche oder zum automatischen Erstellen dieser Analysen auf Grundlage von Journey Optimizer-Journey.

## Potenzielle Erkenntnisse

Im Folgenden finden Sie einige Beispiele für die Arten von Einblicken, die Journey-Arbeitsfläche bieten kann. Sie können auswählen, ob diese Einblicke auf allen Personen in der Datenansicht oder auf allen Personen basieren, die die Journey gestartet haben.

**Fallthrough**

* Anzahl und Prozentsatz der Personen, die die Journey abgeschlossen haben (am Endknoten angekommen)

* Anzahl und Prozentsatz der Personen, die zu einem bestimmten Punkt (Knoten) der Journey gelangt sind

* Der häufigste Schritt, der nach oder vor einem bestimmten Punkt (Knoten) der Journey erfolgte

**Fallout**

* Die Punkte (Knoten) des Journey, an denen die meisten Menschen am häufigsten aus dem Journey herausgefallen sind

**Sonstige**

* Zusätzliche Daten für jeden Knoten im Journey (durch Hinzufügen einer Aufschlüsselungsdimension für den Knoten)


## Wählen Sie zwischen Journey-Arbeitsfläche und Fallout-Visualisierungen

Journey-Arbeitsflächenvisualisierungen ähneln den [Fallout-Visualisierungen](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), da beide Visualisierungen zeigen, wo Personen eine vordefinierte Seitensequenz verlassen (ausgefallen) und weitergemacht (durchgeraten) haben.

Es gibt jedoch wichtige Unterschiede.

### Unterschiede verstehen

Die folgende Tabelle zeigt die in der Visualisierung der Journey-Arbeitsfläche und der Fallout-Visualisierung unterstützten Analysetypen:

| Funktion | Visualisierung der Journey-Arbeitsfläche | Fallout-Visualisierung |
|---------|----------|---------|
| Lineare Journey | Ja | Ja |
| Nicht lineare Journey mit mehreren Einstiegspunkten und Pfaden | Ja | Nein |
| Adobe Journey Optimizer Journey | Ja | Nein |
| Primäre Metrik | Jede Metrik, einschließlich berechneter Metriken | Kann nur die Metriken Sitzung oder Benutzer verwenden |
| Sekundäre Metrik | Ja<p>Jede Metrik, einschließlich berechneter Metriken</p> | Nein |
| Filter vergleichen | Nein | Ja<p>Vergleichen einer [unbegrenzten Anzahl von Filtern](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Auswählen der zu verwendenden Visualisierung

Bevor Sie sich für die Verwendung von Journey-Arbeitsfläche oder Trichteranalyse entscheiden, sollten Sie [die Unterschiede zwischen den beiden](#understand-the-differences) verstehen.

Wenn Ihre Fallout-Analyse nur eine lineare Journey mit einem einzigen bekannten Anfang und Ende umfasst, sollten Sie eine [Fallout-Visualisierung](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) als einfachere Option für diese benutzerfreundlicheren Journey verwenden.

Journey-Arbeitsfläche ist für die Fallout-Analyse von Journey mit mehreren Einstiegspunkten und Pfaden oder für die Analyse von Journey, die in Journey Optimizer erstellt wurden, unerlässlich.

## Journey Optimizer-Journey analysieren

>[!NOTE]
>
>Wenn Ihr Unternehmen keinen Zugriff auf Journey Optimizer hat, können Sie weiterhin [Analysen in der Journey-Arbeitsfläche](#build-analyses-in-customer-journey-analytics) erstellen.

Die Analyse von Journey Optimizer-Journey in der Journey-Arbeitsfläche bietet tiefe, umsetzbare Einblicke in die Interaktion der Menschen mit einer Journey.

Wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche analysieren, wird die Journey mit der gleichen Reihenfolge, Sequenz und Struktur angezeigt wie in Journey Optimizer. Wenn Sie Änderungen an einer Journey in der Journey-Arbeitsfläche vornehmen können, werden [Änderungen nicht mehr von Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas) synchronisiert.

### Vorteile der Analyse von Journey Optimizer-Journey mit Journey-Arbeitsfläche

Journey-Arbeitsfläche bietet eine tiefgründige Analyse, die in Journey Optimizer nicht möglich ist.

Die Verwendung der Journey-Arbeitsfläche zur Analyse von Journey, die in Journey Optimizer erstellt wurden, bietet verschiedene Vorteile:

| Funktion | Vorteil |
|---------|----------|
| **Ereignisse erstellen** | Einfaches Erstellen von Ereignissen mithilfe von Customer Journey Analytics-Dimensionen, Metriken oder Filtern. <p>In Journey Optimizer muss ein technischer Anwender ein Ereignis erstellen, bevor es zu einer Journey hinzugefügt werden kann.</p> |
| **Erstellen von Zielgruppen aus benutzerdefinierten Knoten** | Erstellen Sie Zielgruppen basierend auf einem benutzerdefinierten Knoten, den Sie in der Journey in der Visualisierung der Journey-Arbeitsfläche erstellen. (Startet den Customer Journey Analytics Audience Builder.) <p>In Journey Optimizer können Sie Zielgruppen nur für vordefinierte Aktivitäten erstellen.</p> |
| **Fallthrough und Fallout** | B3 |
| **Aufschlüsseln von Ereignissen** | B3 |
| **Ereignisse umbenennen** | B3 |
| **Löschereignisse** | B3 |
| **Ereignisse kombinieren** | B3 |
| **Ereignisse verbinden** | B3 |

### Synchronisation zwischen Journey Optimizer und Journey-Arbeitsfläche

Nachdem Sie eine Analyse einer Journey Optimizer-Journey auf der Journey-Arbeitsfläche erstellt haben, werden die Daten nur in eine Richtung synchronisiert, von Journey Optimizer auf die Journey-Arbeitsfläche. Das bedeutet, dass Änderungen an einer Journey in der Journey-Arbeitsfläche nie in Journey Optimizer übernommen werden.

Darüber hinaus werden Änderungen an einer Journey in Journey Optimizer nur dann mit der Journey-Arbeitsfläche synchronisiert, wenn die Journey in der Journey-Arbeitsfläche unverändert bleibt. Nachdem Sie eine Journey in der Journey-Arbeitsfläche geändert haben, werden alle Änderungen, die Sie an der Journey in Journey Optimizer vornehmen, nicht in der Journey-Arbeitsfläche angezeigt. Um die Änderungen auf der Journey-Arbeitsfläche zu sehen, können Sie die Journey in der Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) löschen und [neu erstellen.

### Unterschiede nach der Änderung einer Journey in der Journey-Arbeitsfläche {#differences-after-modifying}

Nachdem Sie eine Journey Optimizer-Journey in der Journey-Arbeitsfläche geändert haben, können Änderungen an der Datenverarbeitung, den verfügbaren Funktionen und dem Synchronisierungsverhalten auftreten.

>[!NOTE]
>
>Um den Originalzustand der Journey wiederherzustellen, können Sie Strg+Z drücken, nachdem Sie Ihre erste Änderung in der Journey-Arbeitsfläche vorgenommen haben. Oder Sie können die Journey in der Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) löschen und [neu erstellen

#### Datenverarbeitungsunterschiede

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, werden Sie möglicherweise Änderungen an Ihren Daten bemerken, wenn Ihre Journey Metriken enthält, die nicht standardmäßige Attributionsmodelle aufweisen.

Dies liegt daran, dass Sie im Gegensatz zu Journey Optimizer mit der Journey-Arbeitsfläche mehrere Dimensionen innerhalb einer Journey anwenden können. Diese Funktion bedeutet, dass die [Metrikzuordnung](/help/data-views/component-settings/attribution.md) nicht unterstützt wird.

#### Funktionsunterschiede

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, ist das Dropdown-Feld [!UICONTROL **Knotentyp**] nicht mehr verfügbar.

Weitere Informationen zu diesem Feld finden Sie unter [Einstellungen konfigurieren](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

#### Unterschiede bei der Synchronisierung

Änderungen, die an einer Journey in der Journey Optimizer-Arbeitsfläche vorgenommen wurden, werden nur dann mit der Journey-Arbeitsfläche synchronisiert, wenn die Journey in der Journey-Arbeitsfläche unverändert bleibt.

Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, werden alle Änderungen, die Sie an der Journey in Journey Optimizer vornehmen, nicht in der Arbeitsfläche zum Journey dargestellt. Um die Änderungen auf der Journey-Arbeitsfläche zu sehen, können Sie die Journey in der Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) löschen und [neu erstellen.

### Terminologieunterschiede zwischen Journey Optimizer und Customer Journey Analytics

Bestimmte Begriffe, die eine Sache in Journey Optimizer bedeuten, bedeuten etwas Anderes im Customer Journey Analytics. Bei Verwendung der Journey-Arbeitsfläche werden die Customer Journey Analytics-Begriffe verwendet.

| Begriff | Journey-Arbeitsfläche | Journey Optimizer |
|---------|----------|---------|
| **Ereignis** | Eine von mehreren Standardmetriken, die in Customer Journey Analytics verfügbar sind. Diese Metrik zählt Dinge wie Umsatz, Abonnements oder generierte Leads. | Die Aktivitätskategorie, die eine personalisierte Journey Trigger, z. B. einen Online-Kauf. |
| A2 | B2 | C2 |
| A3 | B3 | C3 |

### Analysieren einer Journey Optimizer-Journey in der Journey-Arbeitsfläche

Informationen zum Analysieren einer Journey Optimizer-Journey in der Journey-Arbeitsfläche finden Sie unter [Konfigurieren einer Visualisierung der Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Erstellen von Analysen in der Journey-Arbeitsfläche

Sie können Analysen in der Journey-Arbeitsfläche erstellen, die auf beliebigen Dimensionen oder Metriken basieren, die in Analysis Workspace verfügbar sind. Sie können auch Journey analysieren, die in Journey Optimizer erstellt wurden. Weitere Informationen finden Sie unter [Konfigurieren einer Journey-Arbeitsflächenvisualisierung](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


