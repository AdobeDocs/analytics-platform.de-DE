---
description: Journey-Arbeitsflächenvisualisierung konfigurieren
title: Journey-Arbeitsfläche
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: 2f42c64443cc5798388287e6f84b125fb8694812
workflow-type: tm+mt
source-wordcount: '4526'
ht-degree: 1%

---

# Journey-Arbeitsflächenvisualisierung konfigurieren

{{release-limited-testing}}

Mit der Journey-Arbeitsflächenvisualisierung können Sie tief greifende Einblicke in die Journey erhalten, die Sie Ihren Benutzern und Kunden zur Verfügung stellen.

## Übersicht über die Journey-Arbeitsfläche

Weitere Informationen zu Journey-Arbeitsflächen finden Sie unter [Journey-Arbeitsfläche - Übersicht](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) , einschließlich:

* Wichtigste Funktionen

* Potenzielle Erkenntnisse

* Unterschiede zwischen Journey-Arbeitsfläche und Fallout

* Details zur Analyse der Journey Optimizer-Journey

* Und mehr

## Erstellen einer Journey-Arbeitsflächenvisualisierung

1. Fügen Sie ein leeres Bedienfeld zu Ihrem Projekt hinzu, wählen Sie in der linken Leiste das Symbol [!UICONTROL **Visualisierungen**] aus und ziehen Sie dann die Visualisierung [!UICONTROL **Journey-Arbeitsfläche**] in das Bedienfeld.

   Oder

   Fügen Sie die Visualisierung der Journey-Arbeitsfläche auf eine der im Abschnitt [Visualisierungen zu einem Bereich hinzufügen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in der Übersicht über die [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) beschriebenen Arten hinzu.

1. Geben Sie die folgenden grundlegenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Primäre Metrik**] | Die primäre Metrik wirkt sich auf die folgenden Aspekte der Visualisierung der Journey-Arbeitsfläche aus:  <ul><li>Definiert, wie Benutzer durch die Journey navigieren.</li><li>Die Gesamtzahl, die auf jedem Knoten angezeigt wird.<p>Wenn beispielsweise People die primäre Metrik ist, zeigt jeder Knoten die Anzahl der Personen an, die diesen Knoten im Journey erreicht haben.</p></li><li>Der auf jedem Knoten angezeigte Prozentsatz. (Nachdem die Visualisierung erstellt wurde, können Sie festlegen, dass entweder der Prozentsatz des Gesamtwerts oder des Anfangsknotens angezeigt werden soll.)</li><p>Wenn beispielsweise People die primäre Metrik ist, zeigt jeder Knoten den Prozentsatz der Personen an, die diesen Knoten im Journey erreicht haben (entweder den Prozentsatz des Gesamtwerts oder des Anfangsknotens).</p></li><li>Wenn der Visualisierung eine Dimension hinzugefügt wird, werden die drei wichtigsten Knoten der Visualisierung hinzugefügt, basierend auf der primären Metrik.</li></ul> |
   | [!UICONTROL **Sekundäre Metrik**] | Die sekundäre Metrik ist optional. Wenn eine ausgewählt ist, werden die folgenden Informationen für jeden Knoten unter der primären Metrik angezeigt: <ul><li>Die Gesamtzahl<p>Wenn Sitzungen beispielsweise die sekundäre Metrik sind, zeigt jeder Knoten die Anzahl der Sitzungen an, die diesen Knoten im Journey erreicht haben.</p></li><li>Der Prozentsatz (nach Erstellung der Visualisierung können Sie entweder den Prozentsatz des Gesamtwerts oder des Anfangsknotens anzeigen.)</li><p>Wenn Sitzungen beispielsweise die sekundäre Metrik sind, zeigt jeder Knoten den Prozentsatz der Sitzungen an, die diesen Knoten im Journey erreicht haben (entweder den Prozentsatz des Gesamtwerts oder des Anfangsknotens).</p></li></ul> |
   | [!UICONTROL **Journey Optimizer Journey**]<!-- name? --> | Wählen Sie die Journey Optimizer-Journey aus, die Sie als Grundlage für Ihre Analyse in der Journey-Arbeitsfläche verwenden möchten. (Alternativ können Sie diese Option leer lassen, wenn Sie eine leere Arbeitsfläche zum Erstellen Ihrer Analyse in Analysis Workspace verwenden möchten.)</p> <p>Wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche analysieren, wird die Journey mit der gleichen Reihenfolge, Sequenz und Struktur angezeigt wie in Journey Optimizer. Weitere Informationen finden Sie unter [Journey Optimizer-Journey analysieren](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in der [Journey-Arbeitsfläche - Übersicht](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Hinweis**: Diese Option wird nur angezeigt, wenn Journey Optimizer-Daten in derselben Datenansicht erkannt werden, die im Bedienfeld &quot;Analysis Workspace&quot;ausgewählt ist, in dem Sie die Visualisierung hinzufügen. Informationen zum Ändern der Datenansicht in einem Bedienfeld in Analysis Workspace finden Sie unter [Analysis Workspace - Übersicht](/help/analysis-workspace/home.md).</p> |

1. (Optional) Wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Journey canvas container**] | Wählen Sie den Container aus, auf den Sie sich auf der gesamten Journey konzentrieren möchten. Der ausgewählte Container bestimmt die Statistiken, die in der Visualisierung angezeigt werden. (Wenn sich Ihre Containernamen von den unten gezeigten Standardnamen unterscheiden, wurden sie in Ihrer Datenansicht angepasst.)<ul><li>**Sitzungen:** Beschränkt die Statistiken der Visualisierung so, dass sie für eine bestimmte Person in eine einzelne definierte Sitzung fallen. Das bedeutet, dass die Zahlen und Prozentsätze, die auf jedem Knoten angezeigt werden (die auf den primären und sekundären Metriken basieren), innerhalb einer einzelnen Sitzung für jede Person auftreten müssen.</li><li>**Personen:** Ermöglicht es, dass die Statistiken der Visualisierung mehrere Sitzungen für eine bestimmte Person umfassen. Das bedeutet, dass die Zahlen und Prozentsätze, die auf jedem Knoten angezeigt werden (die auf den primären und sekundären Metriken basieren), über eine beliebige Anzahl von Sitzungen hinweg auftreten können, sofern die Sitzungen zur selben Person gehören. Dies ist die Standardeinstellung.</li></ul> |

1. Wählen Sie [!UICONTROL **Erstellen**] aus.

   Wenn Sie Journey Optimizer ausgewählt haben und eine Journey Optimizer-Journey ausgewählt haben, wird die Journey mit derselben Reihenfolge, Sequenz und Struktur angezeigt wie in Journey Optimizer.

   <!-- add screen shot -->

   Wenn Sie nicht über Journey Optimizer verfügen oder keine Journey Optimizer-Journey ausgewählt haben, wird eine leere Arbeitsfläche angezeigt, auf der Sie mit dem Ausfüllen der Journey beginnen können.

   <!-- add screen shot -->

1. Unabhängig davon, ob Sie eine neue Analyse auf einer leeren Arbeitsfläche erstellen oder eine Journey Optimizer-Journey analysieren, können Sie die Journey wie in [Visualisierungseinstellungen konfigurieren](#configure-visualization-settings) beschrieben konfigurieren.


## Visualisierungseinstellungen konfigurieren

In der Kopfzeile der Journey-Arbeitsfläche stehen verschiedene Konfigurationsoptionen zur Verfügung.

So konfigurieren Sie Einstellungen für die Visualisierung der Journey-Arbeitsfläche:

1. Öffnen Sie in Analysis Workspace eine bestehende Visualisierung der Journey-Arbeitsfläche oder beginnen Sie mit der Erstellung einer neuen Visualisierung.[](#begin-building-a-journey-canvas-visualization)

   Optionen, mit denen Sie die Visualisierung der Journey-Arbeitsfläche konfigurieren können, sind in der Kopfzeile verfügbar:

   ![Journey canvas-Kopfzeilenoptionen](assets/journey-canvas-header.png)

1. Konfigurieren Sie eine der folgenden Einstellungen, die oben in der Visualisierung angezeigt werden:

   | Einstellung | Funktion |
   |---------|----------|
   | [!UICONTROL **Knotentyp**] | Ermöglicht die Konfiguration der in der Visualisierung angezeigten Knotentypen. Um einen Knotentyp aus der Visualisierung auszublenden, wählen Sie (x) neben dem Knotentyp aus oder deaktivieren Sie ihn im Dropdown-Menü. Um einen ausgeblendeten Knotentyp anzuzeigen, wählen Sie ihn aus dem Dropdownmenü aus. <p>Je nach Inhalt Ihrer Visualisierung sind folgende Knotentypen möglich:</p><ul><li>[!UICONTROL **Segment lesen**]</li><li>[!UICONTROL **Ende**]</li><li>[!UICONTROL **Dimension**]</li><li>[!UICONTROL **Metrik**]</li></ul><p>**Hinweis**: Beachten Sie bei Verwendung dieses Felds Folgendes:</p><ul><li>Diese Option wird nur angezeigt, wenn Journey Optimizer-Daten in derselben Datenansicht erkannt werden, die im Bedienfeld Analysis Workspace ausgewählt ist, in dem Sie die Visualisierung hinzufügen. Informationen zum Ändern der Datenansicht in einem Bedienfeld in Analysis Workspace finden Sie unter [Analysis Workspace - Übersicht](/help/analysis-workspace/home.md).</li><li>Nachdem Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche geändert haben, ist diese Option nicht mehr verfügbar. Weitere Informationen finden Sie unter [Visuelle Unterschiede nach dem Ändern einer Journey in der Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p> |
   | [!UICONTROL **Prozentwert**] | Wählen Sie aus den folgenden Optionen: <ul><li>[!UICONTROL **Prozent der Gesamtsumme**]: Der Prozentsatz aller Personen, die in der Datenansicht im Datumsbereich des Bedienfelds enthalten sind.</li><li>[!UICONTROL **Prozent des Startknotens**]: Der Prozentsatz aller Personen, die in der Datenansicht im Datumsbereich des Bedienfelds enthalten sind und die Kriterien des Journey-Startknotens erfüllen. (Diese Option ist nur in Journey mit einem einzelnen Startknoten verfügbar. Sie ist in Journey mit mehreren Startknoten deaktiviert. Ein Startknoten ist definiert als jeder Knoten, der keine Verbindung hat.)</li></ul> |
   | [!UICONTROL **Pfeileinstellungen**] | Wählen Sie aus den folgenden Optionen:<ul><li>[!UICONTROL **None**]: </li><li>[!UICONTROL **Bedingung**]: </li><li>[!UICONTROL **Alle Beschriftungen**]: </li></ul><p>**Hinweis**: Diese Option wird nur angezeigt, wenn Journey Optimizer-Daten in derselben Datenansicht erkannt werden, die im Bedienfeld &quot;Analysis Workspace&quot;ausgewählt ist, in dem Sie die Visualisierung hinzufügen. Informationen zum Ändern der Datenansicht in einem Bedienfeld in Analysis Workspace finden Sie unter [Analysis Workspace - Übersicht](/help/analysis-workspace/home.md).</p> |
   | [!UICONTROL **Fallout anzeigen**] | Anzeigen von Fallout-Daten für jeden Knoten. Zeigt die Anzahl und den Prozentsatz der Personen an, die die Journey nach einem bestimmten Knoten verlassen haben. <p>Personen, die aus der Journey herausgefallen sind, haben möglicherweise andere Aktionen auf der Site durchgeführt, aber sie haben die vom nächsten Knoten im Journey definierten Kriterien nie erfüllt.</p> |
   | **Zoom-Steuerelemente** | Die folgenden Zoom-Steuerelemente sind oben rechts auf der Arbeitsfläche verfügbar:<ul><li>**Zoom in** ![Einzoomsymbol](assets/zoom-in-icon.png): Vergrößert bestimmte Bereiche der Visualisierung.<p>Sie können auch Maussteuerungen verwenden, wie z. B. das Pinzen auf einem Trackpad.</p></li><li>**Auszoomen** ![ Symbol &quot;Auszoomen&quot;](assets/zoom-out-icon.png): Verkleinert die Visualisierung, um mehr Platz auf der Arbeitsfläche zu gewähren.<p>Sie können auch Maussteuerungen verwenden, wie z. B. das Pinzen auf einem Trackpad.</p></li><li>**Bildschirmgröße** ![Bildschirmsymbol](assets/fill-screen-icon.png): Passt die aktuellen Zoom- und Bildeinstellungen an, um den Bildschirm mit der vollständigen Visualisierung zu füllen.</li></ul><p>Um nach dem Vergrößern oder Verkleinern über die Arbeitsfläche zu schwenken, klicken Sie auf die Maus und ziehen Sie sie an die gewünschte Position.</p> |

1. Fahren Sie mit [Knoten hinzufügen](#add-nodes) fort.

## Knoten hinzufügen

Knoten in einer Journey-Arbeitsflächenvisualisierung stellen die Ereignisse oder Aktionen eines Journey dar.

Sie erstellen Knoten, indem Sie Workspace-Komponenten aus der linken Leiste auf die Arbeitsfläche ziehen, indem Sie Journey-Arbeitsfläche die Auswahl der obersten nächsten oder vorherigen Knoten auf der Grundlage vorhandener Knoten ermöglichen oder indem Sie vorhandene Knoten duplizieren.

### Komponenten aus der linken Leiste ziehen

1. Öffnen Sie in Analysis Workspace eine bestehende Visualisierung der Journey-Arbeitsfläche oder beginnen Sie mit der Erstellung einer neuen Visualisierung.[](#begin-building-a-journey-canvas-visualization)

1. Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter oder Datumsbereiche aus der linken Leiste auf die Arbeitsfläche. Metriken, die auf einem [abgeleiteten Feld](/help/data-views/derived-fields/derived-fields.md) basieren, werden unterstützt. Berechnete Metriken sowie Metriken oder Dimensionen, die auf einem [Zusammenfassungsdatensatz](/help/data-views/summary-data.md) basieren, werden jedoch nicht unterstützt.

   Sie können mehrere Komponenten in der linken Leiste auswählen, indem Sie die Umschalttaste gedrückt halten oder die Befehlstaste (Mac) oder die Strg-Taste (Windows) gedrückt halten.

   Die Visualisierung wird entsprechend dem Komponententyp und dem Bereich der Arbeitsfläche, in dem Sie sie platzieren, wie folgt aktualisiert:

   | Typ der Komponente | Platzierung der Komponente | Aktualisierungen der Visualisierung nach dem Hinzufügen des Knotens |
   |---------|----------|----------|
   | Metrik | Leerer Bereich der Arbeitsfläche | Der Knoten zeigt an, wo die Komponente abgelegt wurde, ohne dass die Verbindung zu vorhandenen Knoten hergestellt wurde. |
   | Metrik | Ein vorhandener Knoten | Die Komponente wird automatisch mit dem vorhandenen Knoten kombiniert. (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p> |
   | Metrik | Ein Pfeil zwischen zwei vorhandenen Knoten | Der Knoten wird zwischen den beiden vorhandenen Knoten angezeigt, auf denen die Komponente abgelegt wurde, und ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p> |
   | Dimension | Leerer Bereich der Arbeitsfläche | Für die drei wichtigsten Dimensionselemente, in denen die Komponente abgelegt wurde, werden 3 Knoten erstellt, die nicht mit vorhandenen Knoten verbunden sind. (**Hinweis:** Wenn nur 1 oder 2 Knoten angezeigt werden, bedeutet dies, dass Daten nur für 1 oder 2 der Dimensionselemente verfügbar sind. Wenn keine Knoten angezeigt werden, bedeutet dies, dass für keines der Dimensionselemente Daten verfügbar sind. Versuchen Sie in diesem Fall, sie einem anderen Punkt der Journey hinzuzufügen, passen Sie den Datumsbereich der Visualisierung an oder wählen Sie eine andere Dimension aus.)<p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Dimension auf der Arbeitsfläche ablegen, um sie als einen einzelnen Knoten mit 3 Dimensionselementen hinzuzufügen.</p><p></p> |
   | Dimension | Ein vorhandener Knoten | Eine Aufschlüsselung wird automatisch auf den Knoten angewendet, wobei die fünf wichtigsten Dimensionselemente angezeigt werden.<!--what happens if you hold Shift?--> |
   | Dimension | Ein Pfeil, der zwei vorhandene Knoten verbindet | 3 Knoten werden für die drei wichtigsten Dimensionselemente erstellt, die auf das erste Ereignis nach dem ersten Knoten folgen (Personen/Sitzungen, die schließlich den zweiten Knoten erreichen). Die Knoten werden zwischen den beiden vorhandenen Knoten angezeigt, auf denen die Komponente abgelegt wurde, und jeder Knoten ist mit beiden vorhandenen Knoten verbunden. (**Hinweis:** Wenn nur 1 oder 2 Knoten angezeigt werden, bedeutet dies, dass Daten nur für 1 oder 2 der Dimensionselemente verfügbar sind. Wenn keine Knoten angezeigt werden, bedeutet dies, dass für keines der Dimensionselemente Daten verfügbar sind. Versuchen Sie in diesem Fall, sie einem anderen Punkt der Journey hinzuzufügen, passen Sie den Datumsbereich der Visualisierung an oder wählen Sie eine andere Dimension aus.)<p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Dimension auf der Arbeitsfläche ablegen, um sie als einen einzelnen Knoten mit 3 Dimensionselementen hinzuzufügen. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p> |
   | Dimensionselement | Leerer Bereich der Arbeitsfläche | Der Knoten zeigt an, wo die Komponente abgelegt wurde, ohne dass die Verbindung zu vorhandenen Knoten hergestellt wurde. |
   | Dimensionselement | Ein vorhandener Knoten | Die Komponente wird automatisch mit dem vorhandenen Knoten kombiniert. |
   | Dimensionselement | Ein Pfeil, der zwei vorhandene Knoten verbindet | Der Knoten wird zwischen den beiden vorhandenen Knoten angezeigt, auf denen die Komponente abgelegt wurde, und ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p> |
   | Filter | Leerer Bereich der Arbeitsfläche | Der Knoten zeigt an, wo die Komponente ohne Verbindung zu anderen Knoten abgelegt wurde.<p>Die Zahl und der Prozentsatz, die auf dem Knoten angezeigt werden, beinhalten die Gesamtsumme der primären Metrik, gefiltert nach dem ausgewählten Filter.</p> <p>Wenn beispielsweise &quot;Personen&quot;als primäre Metrik für die Journey ausgewählt ist, werden durch Hinzufügen des Filters &quot;Heute&quot;zu einem leeren Bereich der Arbeitsfläche alle Personen angezeigt, die heute ein Ereignis hatten.</p> |
   | Filter | Ein vorhandener Knoten | Wendet den Filter auf den vorhandenen Knoten an. |
   | Filter | Ein Pfeil, der zwei Knoten verbindet | Der Knoten wird zwischen den beiden vorhandenen Knoten angezeigt, auf denen die Komponente abgelegt wurde, und ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p><p>Wendet den Filter auf den Punkt auf den Pfad an, an dem die Komponente abgelegt wurde.</p> |
   | Datumsbereich | Leerer Bereich der Arbeitsfläche | Der Knoten zeigt an, wo die Komponente abgelegt wurde, ohne dass die Verbindung zu anderen Knoten hergestellt wurde.<p>Die Zahl und der Prozentsatz, die auf dem Knoten angezeigt werden, enthalten die Gesamtsumme der primären Metrik, gefiltert nach dem ausgewählten Datumsbereich.</p> <p>Wenn beispielsweise Personen als primäre Metrik für die Journey ausgewählt ist, werden durch Hinzufügen des Datumsbereichs Diesen Monat zu einem leeren Bereich der Arbeitsfläche alle Personen angezeigt, die im aktuellen Monat ein Ereignis hatten.</p> |
   | Datumsbereich | Ein vorhandener Knoten | Wendet den Datumsbereich auf den vorhandenen Knoten an. |
   | Datumsbereich | Ein Pfeil, der zwei Knoten verbindet | Der Knoten wird zwischen den beiden vorhandenen Knoten angezeigt, auf denen die Komponente abgelegt wurde, und ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p><p>Wendet den Datumsbereich auf den Punkt auf dem Pfad an, an dem die Komponente abgelegt wurde.</p> |
   | Mehrere Komponenten | Ein leerer Bereich der Arbeitsfläche | **Wenn keine der Komponenten Dimensionen ist:**<p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden, ohne dass die Verbindung zu vorhandenen Knoten besteht.</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. </p><p>**Wenn eine der Komponenten, die Sie hinzufügen, Dimensionen ist:**</p><p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden, ohne dass die Verbindung zu vorhandenen Knoten besteht.</p><p>Es kann immer nur eine Dimension hinzugefügt werden und für die drei wichtigsten Dimensionselemente, in denen die Komponente abgelegt wurde, werden drei Knoten erstellt.</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. Die drei wichtigsten Dimensionselemente werden mit jedem Knoten kombiniert. (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p> |
   | Mehrere Komponenten | Ein vorhandener Knoten | Alle Komponenten werden mit dem vorhandenen Knoten kombiniert.<p>Wenn es sich bei einer der Komponenten, die Sie hinzufügen, um Dimensionen handelt, werden die drei obersten Dimensionselemente mit dem Knoten kombiniert.</p> <p>Es kann immer nur eine Dimension hinzugefügt werden.</p> |
   | Mehrere Komponenten | Ein Pfeil, der zwei vorhandene Knoten verbindet | **Wenn keine der Komponenten Dimensionen ist:**<p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden und jeder Knoten mit beiden vorhandenen Knoten verbunden ist. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. (Komponenten müssen vom gleichen Typ sein, damit sie zu einem einzelnen Knoten kombiniert werden können.) (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p><p>**Wenn eine der Komponenten, die Sie hinzufügen, Dimensionen ist:**</p><p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden und jeder Knoten mit beiden vorhandenen Knoten verbunden ist.</p><p>Es kann immer nur eine Dimension hinzugefügt werden und drei Knoten werden für die drei wichtigsten Elemente der Dimension erstellt, die auf das erste Ereignis nach dem ersten Knoten folgen (Personen/Sitzungen, die schließlich den zweiten Knoten erreichen). Jeder Knoten ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. Die drei wichtigsten Dimensionselemente werden mit jedem Knoten kombiniert und jeder Knoten ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p> |

   Knoten werden als rechteckige Kästchen mit den folgenden Informationen angezeigt:

   * Name der Komponente

   * Der Komponententyp (z. B. Metrik oder Dimension)

   * Primäre Metrikstatistiken (insgesamt und in Prozent)

   * Sekundäre Metrikstatistiken (insgesamt und in Prozent)

1. Wiederholen Sie diesen Vorgang, um mit dem Hinzufügen von Knoten fortzufahren und Ihre Journey zu erstellen.

1. Nehmen Sie die Anpassung der Journey wie in den folgenden Abschnitten beschrieben vor. Sie können Knoten verbinden, Knoten umbenennen, Aufschlüsselungen anwenden, Zielgruppen erstellen, Zeitbeschränkungen hinzufügen und vieles mehr.

### Hinzufügen der obersten Knoten basierend auf vorhandenen Knoten

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Sie können die obersten Knoten automatisch hinzufügen, basierend auf den Knoten, die sich bereits auf der Arbeitsfläche befinden.

Diese Option ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Der Pfeil zwischen Knoten

#### Hinzufügen von Top-Knoten nach einem vorhandenen Knoten

Sie können einen Knoten auswählen und die drei obersten Knoten, die darauf folgen, im Journey hinzufügen.

1. Klicken Sie mit der rechten Maustaste auf den Knoten, in den Sie die drei obersten Knoten einfügen möchten, die auf der Journey folgen.

   Dieser Knoten kann keine vorhandenen Knoten in der Journey enthalten.

1. Wählen Sie [!UICONTROL **Top-Knoten nach diesem Knoten hinzufügen**] aus.

   Die drei wichtigsten Knoten, die auf dem Journey nach diesem Knoten kommen, werden hinzugefügt und sind jeweils mit dem Knoten verbunden, den Sie als separaten Zweig ausgewählt haben.

#### Hinzufügen der obersten Knoten vor einem vorhandenen Knoten

Sie können die drei wichtigsten Knoten hinzufügen, die vor einem vorhandenen Knoten im Journey auftreten.

1. Klicken Sie mit der rechten Maustaste auf den Knoten, in den Sie die drei wichtigsten Knoten einfügen möchten, die auf der Journey davor stehen.

   Dieser Knoten kann keine vorhandenen Knoten in der Journey enthalten.

1. Wählen Sie [!UICONTROL **Top-Knoten vor diesem Knoten hinzufügen**] aus.

   Die drei wichtigsten Knoten, die vor diesem Knoten im Journey kommen, werden hinzugefügt und sind jeweils mit dem Knoten verbunden, den Sie als separaten Zweig ausgewählt haben.

#### Hinzufügen von Top-Knoten zwischen vorhandenen Knoten

Sie können die drei wichtigsten Knoten hinzufügen, die zwischen zwei vorhandenen Knoten liegen:

1. Klicken Sie mit der rechten Maustaste auf den Pfeil zwischen den 2 Knoten, von denen Sie die drei oberen Knoten im Journey hinzufügen möchten.

1. Wählen Sie [!UICONTROL **Top-Knoten hinzufügen**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   Die drei wichtigsten Knoten werden zwischen den beiden vorhandenen Knoten hinzugefügt und sind jeweils als separater Zweig verbunden.

### Duplizieren von Knoten

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Die Option zum Duplizieren ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Mehrere Knoten

So duplizieren Sie Knoten:

1. Wählen Sie mehrere Knoten aus, die Sie duplizieren möchten.

1. Klicken Sie mit der rechten Maustaste auf einen der ausgewählten Knoten und wählen Sie dann [!UICONTROL **Duplizieren**] aus.

## Entwerfen der Journey

Die Reihenfolge der Knoten und die Verbindungen zwischen ihnen wirken sich auf die Daten der Journey-Arbeitsfläche aus. Journey sollten die Ereignisabfolge, über die Sie Berichte erstellen möchten, visuell und präzise widerspiegeln.

Nachdem Knoten zur Arbeitsfläche hinzugefügt wurden, können Sie sie neu anordnen, kombinieren, verbinden und Zeitbeschränkungen zwischen ihnen hinzufügen.

### Knoten neu anordnen

Journey in der Journey-Arbeitsfläche bestehen aus einem flexiblen Diagramm von Knoten und Pfeilen, die eine beliebige Kombination aus Ereignissen, Dimensionselementen und Filtern darstellen.

Sie können Knoten auf die Arbeitsfläche ziehen, um die Ereignisse und Bedingungen der Journey neu anzuordnen. Sie können mehrere Knoten auswählen, indem Sie die Befehlstaste (unter Mac) oder die Strg-Taste (unter Windows) gedrückt halten.

Wenn Sie die Reihenfolge der Knoten im Journey neu anordnen, werden die Daten entsprechend aktualisiert.

### Knoten kombinieren

Ein kombinierter Knoten in der Journey-Arbeitsfläche ist ein Einzelpunkt im Benutzer-Journey (Knoten), der 2 oder mehr Komponenten enthält, die durch Logik verbunden werden.

#### Erstellen kombinierter Knoten

Sie können einen der folgenden Schritte ausführen, um eine kombinierte Node in der Journey-Arbeitsfläche zu erstellen:

* Ziehen Sie aus der linken Leiste eine einzelne Komponente auf einen Knoten auf der Arbeitsfläche.

* Ziehen Sie aus der linken Leiste mehrere Komponenten gleichzeitig auf einen Knoten auf der Arbeitsfläche.

* Ziehen Sie aus der linken Leiste mehrere Komponenten gleichzeitig auf einen leeren Bereich der Arbeitsfläche, während Sie die Umschalttaste gedrückt halten.

* Wählen Sie auf der Arbeitsfläche die Knoten aus, die Sie kombinieren möchten, klicken Sie mit der rechten Maustaste auf einen der ausgewählten Knoten und wählen Sie dann **Kombinieren**<!--Is there a limit on how many you can combine? -->.

#### Logik beim Kombinieren von Knoten

Die Logik, die beim Kombinieren auf Knoten angewendet wird, hängt davon ab, welche Komponententypen Sie wie folgt kombinieren:

>[!TIP]
>
>Sie können die Logik eines kombinierten Knotens anzeigen, indem Sie mit der rechten Maustaste auf den Knoten klicken und dann [!UICONTROL **Filter aus Knoten erstellen**] auswählen. Die Logik wird im Abschnitt [!UICONTROL **Definition**] angezeigt.


| Komponententypen, die kombiniert werden | Verwendete Logik (Operator) |
|---------|----------|
| Metrik + Metrik | Verbunden mit ODER |
| DIMENSION + DIMENSION | Verbunden mit ODER |
| Filter + Filter | Verbunden mit AND |
| Dimension + Metrik, Datumsbereich oder Filter | Verbunden mit AND |
| Datumsbereich + Metrik, Filter oder Dimension | Verbunden mit AND |
| Filter + Metrik, Datumsbereich oder Dimension | Verbunden mit AND |

### Verbinden von Knoten

Sie können Knoten verbinden, die sich bereits auf der Arbeitsfläche befinden, oder Sie können einen Knoten verbinden, wenn Sie ihn zur Arbeitsfläche hinzufügen.

#### Pfeile zwischen Knoten

Knoten sind durch einen Pfeil verbunden. Sowohl die Pfeilrichtung als auch die Pfeilbreite haben Bedeutung:

* **Richtung**: Gibt die Ereignisabfolge der Journey an

* **Breite**: Gibt die prozentuale Lautstärke von einem Knoten zum anderen an

#### Logik beim Verbinden von Knoten

Wenn Sie Knoten in der Journey-Arbeitsfläche verbinden, werden diese über den THEN-Operator verbunden. Dies wird auch als [sequenzielle Filterung](/help/components/filters/seg-sequential-build.md) bezeichnet.

Knoten sind als &quot;letztendlicher Pfad&quot;verbunden. Das bedeutet, dass Besucher gezählt werden, solange sie sich schließlich von einem Knoten zum anderen bewegen, unabhängig von Ereignissen, die zwischen den beiden Knoten auftreten.

Sie können die Logik der verbundenen Knoten anzeigen, indem Sie mit der rechten Maustaste auf den Knoten klicken und dann [!UICONTROL **Filter von Knoten erstellen**] auswählen. Die Logik wird im Abschnitt [!UICONTROL **Definition**] angezeigt.

#### Vorhandene Knoten verbinden

Journey können nicht zirkulär sein und an zuvor verbundene Knoten zurückschleifen.

So verbinden Sie Knoten auf der Journey-Arbeitsfläche:

1. Bewegen Sie auf der Arbeitsfläche den Mauszeiger über den Knoten, der zuerst in der Journey-Sequenz erscheint, die Sie mit einem anderen Knoten verbinden möchten.

   Auf jeder Seite des ausgewählten Knotens werden vier blaue Punkte angezeigt.

1. Ziehen Sie einen der vier blauen Punkte auf eine der vier Seiten des Knotens, mit dem Sie eine Verbindung herstellen möchten.

   Es wird ein Pfeil angezeigt, der die beiden Knoten verbindet. Weitere Informationen finden Sie unter [Pfeile zwischen Knoten](#arrows-between-nodes) .

#### Knoten beim Hinzufügen eines Knotens verbinden

Beim Hinzufügen eines Knotens zur Arbeitsfläche können Sie ihn zwischen zwei verbundenen Knoten platzieren. Der Knoten wird dem Journey zwischen den beiden vorhandenen Knoten hinzugefügt.

Weitere Informationen finden Sie unter [Knoten hinzufügen](#add-nodes).

### Zeitliche Beschränkung zwischen Knoten hinzufügen

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Sie können eine Zeitbegrenzung zwischen Knoten festlegen. Wenn eine Zeitbeschränkung vorhanden ist und eine Person der definierten Journey folgt, aber länger dauert, als der zugewiesene Zeitraum für die Bewegung zwischen den Knoten ist, gilt sie als aus der Journey herausgefallen.

Die Option zum Hinzufügen einer Zeitbegrenzung ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Der Pfeil zwischen Knoten

So fügen Sie eine Zeitbegrenzung hinzu:

1. Klicken Sie mit der rechten Maustaste auf den Pfeil zwischen 2 Knoten und wählen Sie dann [!UICONTROL **Zeitliche Beschränkung hinzufügen**] aus.

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Knoten oder Pfeile verwalten

### Ändern der Farbe eines Knotens oder Pfeils

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Sie können eine Journey visuell anpassen, indem Sie die Farbe eines beliebigen Knotens oder Pfeils auf der Arbeitsfläche ändern. Sie können beispielsweise Farben anpassen, um ein wünschenswertes oder unerwünschtes Ereignis anzuzeigen.

Die Option zum Ändern der Farbe ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Der Pfeil zwischen Knoten

So ändern Sie die Farbe eines Knotens oder Pfeils:

1. Klicken Sie mit der rechten Maustaste auf den Knoten oder Pfeil, dessen Farbe Sie ändern möchten.

1. Wählen Sie [!UICONTROL **Farbe ändern**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Wählen Sie die gewünschte Farbe aus.

   Die folgenden Farben sind verfügbar: <!--look into this interaction and color list-->

### Umbenennen eines Knotens oder Pfeils

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Wenn Sie eine Komponente in eine Journey-Arbeitsflächenvisualisierung ziehen, wird ein Knoten mit demselben Namen wie der Komponentenname erstellt. Sie können den Knoten so umbenennen, dass er besser mit dem Schritt der Journey übereinstimmt, den der Knoten darstellt.

Die Option zum Umbenennen ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Der Pfeil zwischen Knoten

So benennen Sie einen Knoten um:

1. Klicken Sie mit der rechten Maustaste auf den Knoten, den Sie umbenennen möchten.

1. Wählen Sie [!UICONTROL **Umbenennen**] aus.

1. Geben Sie einen neuen Namen ein und drücken Sie dann die Eingabetaste.<!--is that right?-->

### Aufschlüsselung anwenden

Die Option, eine Aufschlüsselung auf Ihre Daten anzuwenden, ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Mehrere Knoten

* Der Pfeil zwischen Knoten

* Mehrere Pfeile zwischen Knoten

#### Aufschlüsselung auf einen oder mehrere Knoten oder Pfeile anwenden

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

1. Wählen Sie mindestens einen Knoten aus, auf den Sie eine Aufschlüsselung anwenden möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

   Oder

   Wählen Sie einen oder mehrere Pfeile zwischen 2 Knoten aus, auf die Sie die Aufschlüsselung anwenden möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Aufschlüsselung**] aus.

#### Aufschlüsselung auf einzelne Knoten anwenden

Sie können eine Dimension aus der linken Leiste auf den Knoten auf der Arbeitsfläche ziehen, auf den Sie die Aufschlüsselung anwenden möchten.

Weitere Informationen finden Sie unter [Knoten hinzufügen](#add-nodes).

### Erstellen einer Zielgruppe

Die Option zum Erstellen einer Zielgruppe ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Mehrere Knoten

* Der Pfeil zwischen Knoten

* Mehrere Pfeile zwischen Knoten

So erstellen Sie eine Zielgruppe:

1. Wählen Sie mindestens einen Knoten aus, für den Sie eine Zielgruppe erstellen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

   Oder

   Wählen Sie einen oder mehrere Pfeile zwischen 2 Knoten, in denen Sie eine Zielgruppe erstellen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Zielgruppe erstellen**] aus.

1. Fahren Sie mit dem Erstellen und Veröffentlichen der Zielgruppe fort, wie unter [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md) beschrieben.

### Trenddaten anzeigen

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Sie können die Trenddaten in einem Liniendiagramm für Objekte auf der Journey-Arbeitsfläche anzeigen. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

Die Option zum Trend ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Mehrere Knoten

* Die Pfeile zwischen Knoten

* Mehrere Pfeile zwischen Knoten

Anzeigen von Trenddaten:

1. Wählen Sie mindestens einen Knoten aus, für den Sie Trenddaten anzeigen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

   Oder

   Wählen Sie einen oder mehrere Pfeile zwischen 2 Knoten aus, für die Sie Trenddaten anzeigen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Trend**] aus.

### Erstellen eines auf einem Knoten oder Pfeil basierenden Filters

Sie können einen neuen Filter basierend auf einem Knoten oder Pfeil innerhalb einer Journey erstellen. Nachdem der Filter erstellt wurde, können Sie ihn überall in Analysis Workspace verwenden.

Auf der Arbeitsfläche von Journey erstellte Filter verwenden [sequenzielle Filterung](/help/components/filters/seg-sequential-build.md). Das bedeutet, dass der Filter den THEN -Operator verwendet, um die Ereignisabfolge (d. h. die Journey), durch die die Besucher flogen, miteinander zu verknüpfen und zum ausgewählten Knoten bzw. Pfeil zu gelangen. Alle Ereignisse, die mit der ausgewählten Node oder dem ausgewählten Pfeil übereinstimmen, sind im Filter enthalten.

Wenn Sie einen Filter erstellen, der auf einem Knoten basiert, in den mehrere Pfade fließen, werden alle Pfade in den Filter einbezogen. Separate Pfade werden mit dem Operator ODER verbunden.

Erstellen eines Filters:

1. Klicken Sie auf der Arbeitsfläche mit der rechten Maustaste auf den Knoten oder Pfeil, den Sie zum Erstellen des Filters verwenden möchten.

1. Wählen Sie [!UICONTROL **Filter aus Knoten erstellen**] oder [!UICONTROL **Filter aus Pfeil erstellen**].

   Der Filter-Builder wird angezeigt. Im Abschnitt [!UICONTROL **Definition**] wird die Filterdefinition basierend auf dem von Ihnen ausgewählten Knoten oder Pfeil und seinem Kontext innerhalb der Journey erstellt.

1. Geben Sie einen Titel für den Filter an und nehmen Sie alle anderen Änderungen vor. Weitere Informationen zum Erstellen eines Filters finden Sie unter [Filter-Builder](/help/components/filters/filter-builder.md).

1. Wählen Sie [!UICONTROL **Speichern**] aus, um den Filter zu speichern.

### Knoten löschen

Sie können einen oder mehrere Knoten gleichzeitig innerhalb einer Journey löschen. Wenn Sie einen Knoten löschen, der zwischen zwei Knoten innerhalb des Journey verbunden ist, werden die beiden verbleibenden Knoten direkt verbunden.

So löschen Sie Knoten in der Journey-Arbeitsfläche:

1. Wählen Sie mindestens einen Knoten aus, den Sie löschen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

1. Wählen Sie [!UICONTROL **Löschen**] aus.

### Pfeile zwischen Knoten löschen

Sie können einen oder mehrere Pfeile gleichzeitig innerhalb einer Journey löschen. Wenn Sie einen Pfeil zwischen zwei Knoten löschen, sind die Knoten nicht mehr verbunden. Wenn der Pfeil Teil eines längeren Pfads war, wird der Pfad getrennt.

So löschen Sie Pfeile zwischen Knoten in der Journey-Arbeitsfläche:

1. Wählen Sie einen oder mehrere Pfeile zwischen zwei Knoten aus, die Sie löschen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Löschen**] aus.


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## Öffnen einer Journey über Journey Optimizer


Öffnen Sie in Journey Optimizer die Journey, die Sie analysieren möchten, in der Arbeitsfläche des Journey.

1. Wählen Sie [!UICONTROL **Analysieren in CJA**] aus. <!-- ?? -->
