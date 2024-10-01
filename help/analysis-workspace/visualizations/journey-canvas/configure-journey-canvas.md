---
description: Konfigurieren einer Journey-Arbeitsflächenvisualisierung
title: Journey-Arbeitsfläche
feature: Visualizations
role: User
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: c42858908aa8e73c5f3b622b9911ff9e9724f2dc
workflow-type: tm+mt
source-wordcount: '6520'
ht-degree: 1%

---

# Konfigurieren einer Journey-Arbeitsflächenvisualisierung

{{release-limited-testing}}

Mit der Journey-Arbeitsflächenvisualisierung können Sie tief greifende Einblicke in die Journey erhalten, die Sie Ihren Benutzern und Kunden zur Verfügung stellen.

## Überblick über die Journey-Arbeitsfläche

Weitere Informationen zu Journey-Arbeitsflächen finden Sie unter [Journey-Arbeitsfläche - Übersicht](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) , einschließlich:

* Wichtigste Funktionen

* Potenzielle Erkenntnisse

* Unterschiede zwischen Journey-Arbeitsfläche und Fallout

* Details zur Analyse der Journey Optimizer-Journey

* Und mehr

## Erstellen einer Journey-Arbeitsflächenvisualisierung

1. Fügen Sie ein leeres Bedienfeld zu Ihrem Projekt hinzu, wählen Sie in der linken Leiste das Symbol [!UICONTROL **Visualisierungen**] aus und ziehen Sie dann die Visualisierung [!UICONTROL **Journey-Arbeitsfläche**] in das Bedienfeld.

   Oder

   Fügen Sie eine Visualisierung der Journey-Arbeitsfläche auf eine der im Abschnitt [Visualisierungen zu einem Bereich hinzufügen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) in der Übersicht über die [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) beschriebenen Arten hinzu.

1. Geben Sie die folgenden grundlegenden Informationen zum Konfigurieren der Journey-Arbeitsfläche an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Primäre Metrik**] | Bestimmt die Metrik, die zur Berechnung der Prozentwert- und Zahlenwerte für jeden Knoten im Journey verwendet wird. <p>**Hinweis**: Der Umfang der in den einzelnen Prozentwerten und Zahlenwerten enthaltenen Daten wird durch die Metrik bestimmt, die Sie im Feld **[!UICONTROL Journey-Arbeitsflächencontainer]** auswählen. Wenn beispielsweise **[!UICONTROL Person]** als Container festgelegt ist, erstrecken sich die auf der Journey angezeigten Statistiken über mehrere Sitzungen für eine bestimmte Person. Wenn **[!UICONTROL Sitzung]** als Container festgelegt ist, sind die auf der Journey angezeigten Statistiken auf eine einzelne definierte Sitzung für eine bestimmte Person beschränkt.</p><p>Sehen Sie sich folgende Beispiele an:</p><ul><li>Wenn _Personen_ die primäre Metrik ist und _Person_ der Container ist, werden nur die Personen, die ein Ereignis haben, das den Kriterien jedes nachfolgenden Knotens im Journey entspricht, durch die Journey bewegt. Fallout tritt auf einem Knoten auf, wenn eine Person nie an einem der unmittelbar nächsten Knoten im Journey angekommen ist. Möglicherweise haben sie andere Aktionen auf der Site durchgeführt, die Kriterien, die von einem der unmittelbar folgenden Knoten definiert wurden, jedoch nicht erfüllt.</li><li>Wenn _Personen_ die primäre Metrik und _Sitzung_ der Container ist, werden nur Personen, die ein Ereignis haben, das den Kriterien der einzelnen Knoten im Journey innerhalb einer einzelnen Sitzung entspricht, durch die Journey bewegt. Fallout tritt auf einem Knoten auf, wenn eine Person innerhalb einer einzigen Sitzung nie an einem der unmittelbar nächsten Knoten im Journey angekommen ist. Möglicherweise haben sie innerhalb der Sitzung andere Aktionen auf der Site ausgeführt, die Kriterien, die von einem der unmittelbar folgenden Knoten definiert wurden, jedoch nicht erfüllt.</li></ul> <p>Die primäre Metrik wirkt sich auf die folgenden Aspekte der Visualisierung der Journey-Arbeitsfläche aus:</p><ul><li>Die Gesamtzahl, die auf jedem Knoten angezeigt wird.  <p>Wenn beispielsweise &quot;Ereignisse&quot;die primäre Metrik ist, zeigt jeder Knoten die Anzahl der Personen an, die ein Ereignis hatten, das den Kriterien dieses Knotens entspricht (und jeden vorherigen Knoten, der zu ihm in der Journey führte).</p></li><li>Der auf jedem Knoten angezeigte Prozentsatz. (Nachdem die Visualisierung erstellt wurde, können Sie über das Dropdown-Menü **[!UICONTROL Prozentwert]** auswählen, ob der Prozentsatz des Gesamtwerts, der Prozentsatz des vorherigen Knotens oder der Prozentsatz des Anfangsknotens angezeigt werden soll.)</li><p>Wenn beispielsweise &quot;Ereignisse&quot;die primäre Metrik ist, zeigt jeder Knoten den Prozentsatz der Personen an, die ein Ereignis hatten, das den Kriterien dieses Knotens entspricht (und jeden vorherigen Knoten, der zu ihm in der Journey führte).</p></li><li>Wenn der Visualisierung eine Dimension hinzugefügt wird, werden die drei wichtigsten Knoten der Visualisierung hinzugefügt, basierend auf der primären Metrik.</li></ul> |
   | [!UICONTROL **Sekundäre Metrik**] | Bestimmt die sekundäre Metrik, die zur Berechnung der Prozentwerte und Zahlenwerte für jeden Knoten im Journey verwendet wird. Die sekundäre Metrik ist optional. <p>**Hinweis**: Der Umfang der in den einzelnen Prozentwerten und Zahlenwerten enthaltenen Daten wird durch die Metrik bestimmt, die Sie im Feld **[!UICONTROL Journey-Arbeitsflächencontainer]** auswählen. Wenn beispielsweise **[!UICONTROL Person]** als Container festgelegt ist, erstrecken sich die auf der Journey angezeigten Statistiken über mehrere Sitzungen für eine bestimmte Person. Wenn **[!UICONTROL Sitzung]** als Container festgelegt ist, sind die auf der Journey angezeigten Statistiken auf eine einzelne definierte Sitzung für eine bestimmte Person beschränkt.</p><p>Wenn eine sekundäre Metrik ausgewählt wird, wirkt sich dies auf die folgenden Aspekte der Visualisierung der Journey-Arbeitsfläche aus:</p><ul><li>Die Gesamtzahl, die auf jedem Knoten unter der primären Metrik angezeigt wird. <p>Wenn beispielsweise Konten die sekundäre Metrik sind, wird die Anzahl der Konten auf dem Knoten für alle Personen angezeigt, die diesen Knoten erreicht haben, wobei nur der Knoten der Personen die Anzahl der Sitzungen anzeigt, die diesen Knoten im Journey erreicht haben.</p></li><li>Der auf jedem Knoten unter der primären Metrik angezeigte Prozentsatz. (Nachdem die Visualisierung erstellt wurde, können Sie festlegen, dass entweder der Prozentsatz des Gesamtwerts oder des Anfangsknotens angezeigt werden soll.)</li><p>Wenn Sitzungen beispielsweise die sekundäre Metrik sind, zeigt jeder Knoten den Prozentsatz der Sitzungen an, die diesen Knoten im Journey erreicht haben (entweder den Prozentsatz des Gesamtwerts oder des Anfangsknotens).</p></li></ul> |
   | [!UICONTROL **Journey Optimizer Journey**]<!-- name? --> | Wählen Sie die Journey Optimizer-Journey aus, die Sie als Grundlage für Ihre Analyse in der Journey-Arbeitsfläche verwenden möchten. Journey mit einem der folgenden Status sind verfügbar: &quot;Live&quot;, &quot;Angehalten&quot;oder &quot;Abgeschlossen&quot; <p>Alternativ können Sie diese Option leer lassen, wenn Sie eine leere Arbeitsfläche zum Erstellen Ihrer Analyse in Analysis Workspace verwenden möchten.</p> <p>Wenn Sie eine Journey Optimizer-Journey auf der Journey-Arbeitsfläche analysieren, wird die Journey mit der gleichen Reihenfolge, Sequenz und Struktur angezeigt wie in Journey Optimizer. Weitere Informationen finden Sie unter [Journey Optimizer-Journey analysieren](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in der [Journey-Arbeitsfläche - Übersicht](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Hinweis**: Diese Option wird nur angezeigt, wenn Journey Optimizer-Daten in derselben Datenansicht erkannt werden, die im Bedienfeld &quot;Analysis Workspace&quot;ausgewählt ist, in dem Sie die Visualisierung hinzufügen. Informationen zum Ändern der Datenansicht in einem Bedienfeld in Analysis Workspace finden Sie unter [Analysis Workspace - Übersicht](/help/analysis-workspace/home.md).</p> |

1. (Optional) Wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**] und geben Sie dann die folgenden Informationen an:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Journey canvas container**] | Wählen Sie den Container aus, auf den Sie sich auf der gesamten Journey konzentrieren möchten. Der ausgewählte Container bestimmt den Umfang der in der Journey erfassten Daten. Dies wirkt sich auf die in der Visualisierung angezeigten Statistiken aus. (Wenn sich Ihre Containernamen von den unten gezeigten Standardnamen unterscheiden, wurden sie in Ihrer Datenansicht angepasst.)<ul><li>**Sitzung:** Beschränkt die Statistiken der Visualisierung so, dass sie für eine bestimmte Person in eine einzelne definierte Sitzung fallen. Das bedeutet, dass die Zahlen und Prozentsätze, die auf jedem Knoten angezeigt werden (die auf den primären und sekundären Metriken basieren), innerhalb einer einzelnen Sitzung für jede Person auftreten müssen. Mit anderen Worten, eine Person kann mehrmals in einer Journey dargestellt werden.<p>Dieser Container verwendet die Metrik Sitzungen .</p></li><li>**Person:** (Standard) Ermöglicht es, dass die Statistiken der Visualisierung mehrere Sitzungen für eine bestimmte Person umfassen. Das bedeutet, dass die Zahlen und Prozentsätze, die auf jedem Knoten angezeigt werden (die auf den primären und sekundären Metriken basieren), über eine beliebige Anzahl von Sitzungen hinweg auftreten können, sofern die Sitzungen zur selben Person gehören. Mit anderen Worten, eine Person kann nur einmal in einer Journey vertreten sein.<p>Dieser Container verwendet die Metrik für Personen .</p></li></ul> |

1. Wählen Sie [!UICONTROL **Erstellen**] aus.

   Wenn Sie Journey Optimizer ausgewählt haben und eine Journey Optimizer-Journey ausgewählt haben, wird die Journey mit derselben Reihenfolge, Sequenz und Struktur angezeigt wie in Journey Optimizer.

   <!-- add screen shot -->

   Wenn Sie nicht über Journey Optimizer verfügen oder keine Journey Optimizer-Journey ausgewählt haben, wird eine leere Arbeitsfläche angezeigt, auf der Sie Knoten zum Journey hinzufügen können.

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
   | [!UICONTROL **Knotentyp**] | Ermöglicht die Konfiguration der in der Visualisierung angezeigten Knotentypen.<p>Um einen Knotentyp aus der Visualisierung auszublenden, wählen Sie (x) neben dem Knotentyp aus oder deaktivieren Sie ihn im Dropdown-Menü. Um einen ausgeblendeten Knotentyp anzuzeigen, wählen Sie ihn aus dem Dropdownmenü aus. (Knoten werden nicht aus dem Journey gelöscht, wenn Sie sie ausblenden. Informationen zum Löschen eines Knotens finden Sie unter [Knoten löschen](#delete-nodes).)</p><p>Dieses Feld kann wie folgt Journey Optimizer-Knotentypen ([!UICONTROL **Segment lesen**], [!UICONTROL **Ende**] usw.) und Komponentenknotentypen ([!UICONTROL **Dimension**], [!UICONTROL **Metrik**], [!UICONTROL **Filter**] und [!UICONTROL **Datumsbereich**]) enthalten: </p><ul><li>**Es werden nur Journey Optimizer-Knotentypen angezeigt**, wenn die Journey eine Journey Optimizer-Journey ist, die nicht auf der Journey-Arbeitsfläche mit einer der folgenden Änderungen geändert wurde:<ul><li>Knoten hinzugefügt oder entfernt</li><li>Pfeile hinzugefügt oder entfernt</li><li>Komponenten auf einem Knoten geändert</li></ul></li><li>**Sowohl Journey Optimizer-Knotentypen als auch Komponentenknotentypen werden angezeigt**, wenn die Journey eine Journey Optimizer-Journey ist, die auf der Journey-Arbeitsfläche mit einer der folgenden Änderungen geändert wurde:<ul><li>Knoten hinzugefügt oder entfernt</li><li>Pfeile hinzugefügt oder entfernt</li><li>Komponenten auf einem Knoten geändert</li></ul></li><li>**Es werden nur Komponentenknotentypen angezeigt**, wenn die Journey keine Journey Optimizer-Journey ist.</li></ul></p> |
   | [!UICONTROL **Prozentwert**] | Der auf jedem Knoten im Journey angezeigte Prozentwert. <p>Beachten Sie Folgendes bei der Konfiguration der auf Knoten in der Journey angezeigten Prozentwerte:</p><ul><li>Ein Prozentsatz wird auf jedem Knoten für die primäre Metrik angezeigt. Ein Prozentsatz wird auch für die sekundäre Metrik angezeigt, wenn eine konfiguriert ist. (Weitere Informationen zu den primären und sekundären Metrikeinstellungen finden Sie unter [Erstellen einer Journey-Arbeitsflächenvisualisierung beginnen](#begin-building-a-journey-canvas-visualization).)</li><li>Prozentsätze umfassen alle Personen oder Sitzungen, die in der Datenansicht innerhalb des Datumsbereichs des Bedienfelds enthalten sind. Ob _Personen_ oder _Sitzungen_ verwendet werden, hängt von der Behältereinstellung ab. (Weitere Informationen zur Behältereinstellung finden Sie unter [Erstellen einer Journey-Arbeitsflächenvisualisierung beginnen](#begin-building-a-journey-canvas-visualization).)</li></ul> <p>Wählen Sie aus den folgenden Optionen:</p> <ul><li>[!UICONTROL **Prozent des Startknotens**]: Berechnet die auf jedem Knoten angezeigten Prozentsätze im Verhältnis zum Startknoten. Prozentsätze basieren auf der von Ihnen ausgewählten primären und sekundären Metrik. <p>Ein _Startknoten_ ist ein Knoten, der keine verbundenen Knoten davor hat.</p><p>Eine Journey kann mehrere Startknoten enthalten. Allerdings wird [!UICONTROL **Prozent des Gesamtwerts**] verwendet, wenn die Journey 2 oder mehr Startknoten enthält, die zu einem gemeinsamen Knoten führen. Wenn Sie [!UICONTROL **Prozent des Startknotens**] verwenden möchten, aktualisieren Sie die Journey, sodass jeder Knoten im Journey auf einen einzelnen Startknoten zurückverfolgt werden kann.</p></li><li>[!UICONTROL **Prozentsatz des vorherigen Knotens**]: Berechnet die auf jedem Knoten angezeigten Prozentsätze im Verhältnis zum vorherigen Knoten. Prozentsätze basieren auf der von Ihnen ausgewählten primären und sekundären Metrik.</li><li>[!UICONTROL **Prozent des Gesamtwerts**]: Berechnet die auf jedem Knoten angezeigten Prozentsätze in Bezug auf alle Daten in der Datenansicht. Prozentsätze basieren auf der von Ihnen ausgewählten primären und sekundären Metrik.</li></ul> |
   | [!UICONTROL **Pfeileinstellungen**] | Die Pfeile, die zwischen Knoten auf der Journey-Arbeitsfläche angezeigt werden, können so konfiguriert werden, dass benutzerdefinierte Beschriftungen und Werte angezeigt werden. <p>_Beschriftungen_ sind benutzerdefinierte Namen, die auf den Pfeilen angezeigt werden. Auf einem Pfeil wird nur eine einzige Bezeichnung angezeigt. Bezeichnungen können eine der folgenden sein und werden in der folgenden Reihenfolge angezeigt:</p><ol><li>Ein benutzerdefinierter Name, der von der Journey-Arbeitsfläche hinzugefügt wurde (wie unter [Hinzufügen oder Aktualisieren einer Bezeichnung auf einem Pfeil](#add-or-update-a-label-on-an-arrow) beschrieben)</li><li>Eine Journey Optimizer-Bezeichnung</li><li>Eine Journey Optimizer-Bedingung</li></ol><p>_Werte_ sind die Zahlen und Prozentwerte, die auf den Pfeilen angezeigt werden, und sie geben die Personen oder Sitzungen an, die von einem Knoten zum nächsten im Journey verschoben wurden. (Mit anderen Worten, diejenigen, die bei einem bestimmten Schritt nicht aus dem Journey herausgefallen sind.) </p><p>Die folgenden Optionen sind für Journey verfügbar, die nicht aus Journey Optimizer stammen, und für Journey Optimizer-Journey, die nicht wesentlich auf der Journey-Arbeitsfläche geändert wurden: (Wesentliche Änderungen sind das Hinzufügen oder Entfernen von Knoten, das Hinzufügen oder Entfernen von Pfeilen oder das Ändern der Knotenkomponenten.)</p><ul><li>[!UICONTROL **Keine Beschriftungen**]: Auf den Pfeilen im Journey werden keine Beschriftungen angezeigt. </br> Diese Option ist nur verfügbar, wenn die Journey in </li><li>[!UICONTROL **Nur Beschriftungen**]: Beschriftungen werden auf den Pfeilen im Journey angezeigt.</li></ul><p>Die folgenden Optionen stehen für Journey Optimizer-Journey zur Verfügung, die in der Journey-Arbeitsfläche erheblich geändert wurden: (Wesentliche Änderungen sind das Hinzufügen oder Entfernen von Knoten, das Hinzufügen oder Entfernen von Pfeilen oder das Ändern der Komponenten eines Knotens.)(**Hinweis**: Diese Optionen werden nur angezeigt, wenn Journey Optimizer-Daten in derselben Datenansicht erkannt werden, die im Bedienfeld &quot;Analysis Workspace&quot;ausgewählt ist, in dem Sie die Visualisierung hinzufügen. Informationen zum Ändern der Datenansicht in einem Bedienfeld in Analysis Workspace finden Sie unter [Analysis Workspace - Übersicht](/help/analysis-workspace/home.md).)</p><ul><li>[!UICONTROL **Keine Beschriftungen oder Werte**]: Auf den Pfeilen des Journey werden keine Beschriftungen oder Werte angezeigt.</li><li>[!UICONTROL **Nur Beschriftungen**]: Auf den Pfeilen im Journey werden nur Beschriftungen angezeigt. Werte werden nicht angezeigt.</li><li>[!UICONTROL **Nur Werte**]: Nur Werte werden auf den Pfeilen im Journey angezeigt. Beschriftungen werden nicht angezeigt.</li><li>[!UICONTROL **Werte und Beschriftungen**]: Sowohl Beschriftungen als auch Werte werden auf den Pfeilen im Journey angezeigt.</li></ul> |
   | [!UICONTROL **Fallout anzeigen**] | Fallout-Daten zeigen einen Prozentsatz und eine Zahl, die von jedem Knoten der Journey fallen. Fallout-Daten basieren auf der Metrik, die mit den Einstellungen des Journey-Containers verknüpft ist. Sie basieren nicht auf der primären oder sekundären Metrik.<p>Standardmäßig ist der Container _Person_, daher ist die für Fallout-Daten verwendete Metrik _Personen_. Wenn der Container in _Sitzung_ geändert wird, lautet die für Fallout-Daten verwendete Metrik _Sitzungen_ usw.</p><p>Wenn beispielsweise _Person_ als Containereinstellung verwendet wird, zeigt Fallout den Prozentsatz und die Anzahl der Personen auf jedem Knoten des Journey an, die nie an einem der nächsten Knoten gelangt sind. Möglicherweise haben sie andere Aktionen auf der Site durchgeführt, die Kriterien, die von einem der unmittelbar folgenden Knoten definiert wurden, jedoch nicht erfüllt.</p> <p>Weitere Informationen zur Journey-Arbeitsflächencontainer-Einstellung finden Sie unter [Erstellen einer Journey-Arbeitsflächenvisualisierung beginnen](#begin-building-a-journey-canvas-visualization). |
   | **Zoom-Steuerelemente** | Die folgenden Zoom-Steuerelemente sind oben rechts auf der Arbeitsfläche verfügbar:<ul><li>**Zoom in** ![Einzoomsymbol](assets/zoom-in-icon.png): Vergrößert bestimmte Bereiche der Visualisierung.<p>Sie können auch Maussteuerungen verwenden, wie z. B. das Pinzen auf einem Trackpad.</p></li><li>**Auszoomen** ![ Symbol &quot;Auszoomen&quot;](assets/zoom-out-icon.png): Verkleinert die Visualisierung, um mehr Platz auf der Arbeitsfläche zu gewähren.<p>Sie können auch Maussteuerungen verwenden, wie z. B. das Pinzen auf einem Trackpad.</p></li><li>**Bildschirmgröße** ![Bildschirmsymbol](assets/fill-screen-icon.png): Passt die aktuellen Zoom- und Bildeinstellungen an, um den Bildschirm mit der vollständigen Visualisierung zu füllen.</li></ul><p>Um nach dem Vergrößern oder Verkleinern über die Arbeitsfläche zu schwenken, klicken Sie auf die Maus und ziehen Sie sie an die gewünschte Position.</p> |

1. Fahren Sie mit [Knoten hinzufügen](#add-nodes) fort.

## Knoten hinzufügen

Knoten in einer Journey-Arbeitsflächenvisualisierung stellen die Ereignisse oder Aktionen eines Journey dar.

Sie können Knoten wie folgt erstellen: indem Sie Workspace-Komponenten aus der linken Leiste auf die Arbeitsfläche ziehen, indem Sie Journey-Arbeitsfläche die Auswahl der obersten nächsten oder vorherigen Knoten auf der Grundlage vorhandener Knoten ermöglichen oder indem Sie vorhandene Knoten duplizieren.

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
   | Dimension | Ein vorhandener Knoten | Eine Aufschlüsselung wird automatisch auf den Knoten angewendet, wobei die fünf wichtigsten Dimensionselemente angezeigt werden.<!--what happens if you hold Shift?--><p>Um die Aufschlüsselung in einer neuen Freiformtabellenvisualisierung anzuzeigen, wählen Sie den Link [!UICONTROL **In einer Freiformtabelle öffnen**] auf dem Knoten aus.</p> |
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
   | Mehrere Komponenten | Ein leerer Bereich der Arbeitsfläche | **Wenn keine der Komponenten Dimensionen ist:**<p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden, ohne dass die Verbindung zu vorhandenen Knoten besteht.</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. </p><p>**Wenn eine der Komponenten, die Sie hinzufügen, Dimensionen ist:**</p><p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden, ohne dass die Verbindung zu vorhandenen Knoten besteht.</p><p>Es kann immer nur eine Dimension hinzugefügt werden. Wenn die Dimension hinzugefügt wird, werden 3 Knoten für die drei wichtigsten Dimensionselemente erstellt, in denen die Komponente abgelegt wurde.</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. Die drei wichtigsten Dimensionselemente werden mit jedem Knoten kombiniert. (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p> |
   | Mehrere Komponenten | Ein vorhandener Knoten | Alle Komponenten werden mit dem vorhandenen Knoten kombiniert.<p>Wenn es sich bei einer der Komponenten, die Sie hinzufügen, um Dimensionen handelt, werden die drei obersten Dimensionselemente mit dem Knoten kombiniert.</p> <p>Es kann immer nur eine Dimension hinzugefügt werden.</p> |
   | Mehrere Komponenten | Ein Pfeil, der zwei vorhandene Knoten verbindet | **Wenn keine der Komponenten Dimensionen ist:**<p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden und jeder Knoten mit beiden vorhandenen Knoten verbunden ist. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. (Komponenten müssen vom gleichen Typ sein, damit sie zu einem einzelnen Knoten kombiniert werden können.) (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p><p>**Wenn eine der Komponenten, die Sie hinzufügen, Dimensionen ist:**</p><p>Jede Komponente wird als separater Knoten angezeigt, in dem die Komponenten abgelegt wurden und jeder Knoten mit beiden vorhandenen Knoten verbunden ist.</p><p>Es kann immer nur eine Dimension hinzugefügt werden. Wenn die Dimension hinzugefügt wird, werden 3 Knoten für die drei wichtigsten Elemente der Dimension erstellt, die auf das erste Ereignis nach dem ersten Knoten folgen (Personen/Sitzungen, die schließlich den zweiten Knoten erreichen). Jeder Knoten ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Verbinden von Knoten](#connect-nodes) .)</p><p>Halten Sie die Umschalttaste gedrückt, wenn Sie die Komponenten auf der Arbeitsfläche ablegen, um sie als einen kombinierten Knoten hinzuzufügen. Die drei wichtigsten Dimensionselemente werden mit jedem Knoten kombiniert und jeder Knoten ist mit beiden vorhandenen Knoten verbunden. (Weitere Informationen finden Sie unter [Kombinieren von Knoten](#combine-nodes) .)</p> |

   Knoten werden als rechteckige Kästchen mit den folgenden Informationen angezeigt:

   * Name der Komponente

   * Der Komponententyp (z. B. Metrik oder Dimension)

   * Primäre Metrikstatistiken (insgesamt und in Prozent)

   * Sekundäre Metrikstatistiken (insgesamt und in Prozent)

   Ein pulsierender oder leuchtender Knoten zeigt an, dass Daten für diesen Knoten geladen werden.

1. Wiederholen Sie diesen Vorgang, um mit dem Hinzufügen von Knoten fortzufahren und Ihre Journey zu erstellen.

1. Nehmen Sie die Anpassung der Journey wie in den folgenden Abschnitten beschrieben vor. Sie können Knoten verbinden, Knoten umbenennen, Aufschlüsselungen anwenden, Zielgruppen erstellen, Zeitbeschränkungen hinzufügen und vieles mehr.

### Anzeigen der obersten Knoten basierend auf vorhandenen Knoten

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Sie können die obersten Knoten automatisch anhand der Knoten anzeigen, die sich bereits auf der Arbeitsfläche befinden. Sie können die obersten Knoten zur Journey-Arbeitsfläche hinzufügen oder sie in einer Freiformtabelle anzeigen.

Diese Option ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Der Pfeil zwischen Knoten

#### Anzeigen der obersten Knoten nach einem vorhandenen Knoten

Sie können einen Knoten auswählen und die obersten Dimensionselemente anzeigen, die nach ihm im Journey folgen. Sie können die drei wichtigsten Dimensionselemente zur Journey-Arbeitsfläche als separate Knoten hinzufügen oder Sie können alle obersten Dimensionselemente in einer Freiformtabelle anzeigen.

1. Klicken Sie mit der rechten Maustaste auf den Knoten, unter dem die obersten Dimensionselemente angezeigt werden sollen, die auf der Journey folgen.

   Der Knoten kann keine vorhandenen Knoten in der Journey enthalten.

1. Wählen Sie [!UICONTROL **Oberste Knoten nach diesem Knoten anzeigen**] aus.

1. Wählen Sie aus, wo die Dimensionselemente angezeigt werden sollen:

   * [!UICONTROL **In Journey canvas**]: Fügt die drei obersten Knoten der Arbeitsfläche hinzu, die hinter diesem Knoten im Journey liegen. Jeder Knoten ist mit dem Knoten verbunden, den Sie als separaten Zweig auf der Arbeitsfläche ausgewählt haben.

   * [!UICONTROL **In einer Freiformtabelle**]: Erstellt eine Freiformtabellen-Visualisierung, die alle obersten Dimensionselemente anzeigt, die nach diesem Knoten im Journey kommen.

1. Wählen Sie die gewünschte Dimension aus der Liste der Dimensionen aus.

   Je nachdem, was Sie im vorherigen Schritt ausgewählt haben, werden die drei wichtigsten Dimensionselemente der Arbeitsfläche als 3 separate Knoten hinzugefügt oder alle obersten Dimensionselemente werden in einer Freiformtabelle angezeigt.

#### Anzeigen der obersten Knoten vor einem vorhandenen Knoten

Sie können einen Knoten auswählen und die obersten Dimensionselemente anzeigen, die ihm im Journey vorstehen. Sie können die drei wichtigsten Dimensionselemente zur Journey-Arbeitsfläche als separate Knoten hinzufügen oder Sie können alle obersten Dimensionselemente in einer Freiformtabelle anzeigen.

1. Klicken Sie mit der rechten Maustaste auf den Knoten, unter dem die obersten Dimensionselemente angezeigt werden sollen, die auf der Journey davor stehen.

   Dieser Knoten kann keine vorhandenen Knoten in der Journey enthalten.

1. Wählen Sie [!UICONTROL **Oberste Knoten vor diesem Knoten anzeigen**] aus.

1. Wählen Sie aus, wo die Dimensionselemente angezeigt werden sollen:

   * [!UICONTROL **In Journey canvas**]: Fügt die drei obersten Knoten der Arbeitsfläche hinzu, die vor diesem Knoten im Journey liegen. Jeder Knoten ist mit dem Knoten verbunden, den Sie als separaten Zweig auf der Arbeitsfläche ausgewählt haben.

   * [!UICONTROL **In einer Freiformtabelle**]: Erstellt eine Freiformtabellen-Visualisierung, die alle obersten Dimensionselemente anzeigt, die vor diesem Knoten im Journey auftreten.

1. Wählen Sie die gewünschte Dimension aus der Liste der Dimensionen aus.

   Je nachdem, was Sie im vorherigen Schritt ausgewählt haben, werden die drei wichtigsten Dimensionselemente der Arbeitsfläche als 3 separate Knoten hinzugefügt oder alle obersten Dimensionselemente werden in einer Freiformtabelle angezeigt.

#### Oberste Knoten zwischen vorhandenen Knoten anzeigen

Sie können einen Pfeil auswählen und die obersten Dimensionselemente anzeigen, die zwischen zwei vorhandenen Knoten im Journey liegen. Sie können die drei wichtigsten Dimensionselemente zur Journey-Arbeitsfläche als separate Knoten hinzufügen oder Sie können alle obersten Dimensionselemente in einer Freiformtabelle anzeigen.

1. Klicken Sie mit der rechten Maustaste auf den Pfeil zwischen den beiden Knoten, an denen die obersten Dimensionselemente angezeigt werden sollen.

1. Wählen Sie [!UICONTROL **Oberste Knoten zwischen diesen Knoten anzeigen**] aus.

1. Wählen Sie aus, wo die Dimensionselemente angezeigt werden sollen:

   * [!UICONTROL **In Journey canvas**]: Fügt die drei obersten Knoten der Arbeitsfläche hinzu, die zwischen den beiden vorhandenen Knoten liegen. Jeder Knoten ist mit den umgebenden Knoten als separater Zweig auf der Arbeitsfläche verbunden.

   * [!UICONTROL **In einer Freiformtabelle**]: Erstellt eine Freiformtabellen-Visualisierung, die alle obersten Dimensionselemente enthält, die zwischen den beiden vorhandenen Knoten liegen.

1. Wählen Sie die gewünschte Dimension aus der Liste der Dimensionen aus.

   Je nachdem, was Sie im vorherigen Schritt ausgewählt haben, werden die drei wichtigsten Dimensionselemente der Arbeitsfläche als 3 separate Knoten hinzugefügt oder alle obersten Dimensionselemente werden in einer Freiformtabelle angezeigt.

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

Sie können Knoten auf die Arbeitsfläche ziehen, um die Ereignisse und Bedingungen der Journey neu anzuordnen.

Wenn Sie die Reihenfolge der Knoten im Journey neu anordnen, werden die Daten entsprechend aktualisiert.

### Knoten kombinieren

Ein kombinierter Knoten in der Journey-Arbeitsfläche ist ein Einzelpunkt im Benutzer-Journey (Knoten), der 2 oder mehr Komponenten enthält, die durch Logik verbunden werden.

#### Erstellen kombinierter Knoten

Sie können Folgendes tun, um Knoten in der Journey-Arbeitsfläche zu kombinieren:

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
| Dimension Element + Dimension Element (aus derselben übergeordneten Dimension) | Verbunden mit ODER |
| Dimension Element + Dimension Element (aus verschiedenen übergeordneten Dimensionen) | Verbunden mit AND |
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

1. Bewegen Sie in einer Journey-Arbeitsflächenvisualisierung den Mauszeiger über den Knoten, der zuerst in der Journey-Sequenz erscheint, die Sie mit einem anderen Knoten verbinden möchten.

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

Sie können eine Zeitbegrenzung zwischen Knoten festlegen. Wenn eine Zeitbegrenzung vorhanden ist, gelten die Personen als aus dem Journey herausgefallen, wenn sie der definierten Journey folgen, aber länger als den zugewiesenen Zeitraum benötigen, um zwischen den Knoten zu wechseln.

Die Option zum Hinzufügen einer Zeitbegrenzung ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Der Pfeil zwischen Knoten

So fügen Sie eine Zeitbegrenzung hinzu:

1. Klicken Sie in einer Journey-Arbeitsflächenvisualisierung mit der rechten Maustaste auf den Pfeil zwischen zwei Knoten und wählen Sie dann [!UICONTROL **Zeitliche Beschränkung hinzufügen**] aus.

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

1. Klicken Sie in einer Journey-Arbeitsflächenvisualisierung mit der rechten Maustaste auf den Knoten oder Pfeil, dessen Farbe Sie ändern möchten.

1. Wählen Sie [!UICONTROL **Farbe ändern**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Wählen Sie die gewünschte Farbe aus.

   Die folgenden Farben sind verfügbar: <!--look into this interaction and color list-->

### Umbenennen eines Knotens

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

Wenn Sie eine Komponente in eine Journey-Arbeitsflächenvisualisierung ziehen, wird ein Knoten mit demselben Namen wie der Komponentenname erstellt. Sie können den Knoten so umbenennen, dass er besser mit dem Schritt der Journey übereinstimmt, den der Knoten darstellt.

Die Option zum Umbenennen ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

So benennen Sie einen Knoten um:

1. Klicken Sie in einer Journey-Arbeitsflächenvisualisierung mit der rechten Maustaste auf den Knoten, den Sie umbenennen möchten.

1. Wählen Sie [!UICONTROL **Umbenennen**] aus.

1. Geben Sie einen neuen Namen ein und drücken Sie dann die Eingabetaste.<!--is that right?-->

### Hinzufügen oder Aktualisieren einer Bezeichnung auf einem Pfeil

Die Pfeile, die zwischen Knoten auf der Journey-Arbeitsfläche angezeigt werden, können so konfiguriert werden, dass benutzerdefinierte Beschriftungen und Werte angezeigt werden.

Beschriftungen sind benutzerdefinierte Namen, die auf Pfeilen angezeigt werden. Auf einem Pfeil wird nur eine einzige Bezeichnung angezeigt.

Weitere Informationen zu den Beschriftungen und Werten, die auf den Pfeilen angezeigt werden, finden Sie unter &quot;Pfeileinstellungen&quot;in [Visualisierungseinstellungen konfigurieren](#configure-visualization-settings).

Die Option zum Hinzufügen oder Aktualisieren einer Bezeichnung ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Der Pfeil zwischen Knoten

So fügen Sie einem Pfeil eine Bezeichnung hinzu:

1. Klicken Sie in einer Visualisierung der Journey-Arbeitsfläche mit der rechten Maustaste auf den Pfeil, in dem Sie eine Beschriftung hinzufügen möchten.

1. Wählen Sie **[!UICONTROL Titel hinzufügen]** aus.

1. Geben Sie einen Namen für die Beschriftung ein und drücken Sie dann die Eingabetaste.

   Wenn die Pfeileinstellungen derzeit so konfiguriert sind, dass Beschriftungen ausgeblendet werden, wird eine Meldung angezeigt, in der Sie aufgefordert werden, Beschriftungen anzuzeigen.

So aktualisieren Sie eine vorhandene Bezeichnung für einen Pfeil:

1. Klicken Sie in einer Visualisierung der Journey-Arbeitsfläche mit der rechten Maustaste auf den Pfeil, in dem Sie eine Beschriftung hinzufügen möchten.

1. Wählen Sie **[!UICONTROL Titel aktualisieren]** aus.

1. Geben Sie einen Namen für die Beschriftung ein und drücken Sie dann die Eingabetaste.

   Wenn die Pfeileinstellungen derzeit so konfiguriert sind, dass Beschriftungen ausgeblendet werden, wird eine Meldung angezeigt, in der Sie aufgefordert werden, Beschriftungen anzuzeigen.

### Aufschlüsselung anwenden

Die Option, eine Aufschlüsselung auf Ihre Daten anzuwenden, ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Mehrere Knoten

* Der Pfeil zwischen Knoten

* Mehrere Pfeile zwischen Knoten

Beachten Sie beim Anwenden einer Aufschlüsselung Folgendes:

* Aufschlüsselungen werden auf die primäre Metrik angewendet. Die sekundäre Metrik ist nicht betroffen.

* Die Anwendung einer Aufschlüsselung ändert die Journey nicht. Stattdessen wird lediglich eine Aufschlüsselung der Daten für den Knoten angezeigt, auf den sie angewendet werden.

* Wenn ein Knoten bereits eine Aufschlüsselung aufweist, wird die vorhandene Aufschlüsselung durch die Anwendung einer neuen Aufschlüsselung ersetzt.

* Die Aufschlüsselungsdaten werden aktualisiert, wenn Änderungen zu einem früheren Zeitpunkt im Journey vorgenommen werden.

#### Aufschlüsselung auf einen oder mehrere Knoten oder Pfeile anwenden

>[!AVAILABILITY]
>
>Diese Funktion ist noch nicht verfügbar.

1. Wählen Sie in einer Journey-Arbeitsflächenvisualisierung mindestens einen Knoten aus, auf den Sie eine Aufschlüsselung anwenden möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

   Oder

   Wählen Sie in einer Journey-Arbeitsflächenvisualisierung einen oder mehrere Pfeile zwischen 2 Knoten aus, auf die Sie die Aufschlüsselung anwenden möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Aufschlüsselung**] aus.

1. Wählen Sie aus, wo die Aufschlüsselung angezeigt werden soll:

   * [!UICONTROL **In Journey canvas**]

   * [!UICONTROL **In einer Freiformtabelle**]

1. Wählen Sie die Dimension aus, die Sie für die Aufschlüsselung verwenden möchten.

   Wenn Sie die Aufschlüsselung auf der Journey-Arbeitsfläche anzeigen möchten, werden die obersten 5 Dimensionselemente auf dem Knoten angezeigt. Auf dem Knoten ist eine Option verfügbar, um die Aufschlüsselung in einer Freiformtabelle zu öffnen.

   Wenn Sie die Aufschlüsselung in einer Freiformtabelle anzeigen möchten, werden die obersten Dimensionselemente in einer neuen Freiformtabelle direkt über der Journey-Arbeitsflächenvisualisierung angezeigt.

#### Aufschlüsselung auf einzelne Knoten anwenden

Sie können eine Dimension aus der linken Leiste auf den Knoten auf der Arbeitsfläche ziehen, auf den Sie die Aufschlüsselung anwenden möchten.

Weitere Informationen finden Sie unter [Knoten hinzufügen](#add-nodes).

### Erstellen einer Zielgruppe

Die Option zum Erstellen einer Zielgruppe ist für die folgenden Objekte auf der Arbeitsfläche verfügbar:

* Einzelne Knoten

* Mehrere Knoten

* Der Pfeil zwischen Knoten

* Mehrere Pfeile zwischen Knoten

Wenn Sie eine Zielgruppe aus mehreren Knoten oder Pfeilen erstellen, werden diese mit dem ODER-Operator verknüpft.

So erstellen Sie eine Zielgruppe:

1. Wählen Sie in einer Journey-Arbeitsflächenvisualisierung mindestens einen Knoten aus, für den Sie eine Zielgruppe erstellen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

   Oder

   Wählen Sie in einer Journey-Arbeitsflächenvisualisierung einen oder mehrere Pfeile zwischen 2 Knoten, an denen Sie eine Zielgruppe erstellen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

   >[!NOTE]
   >
   >Zielgruppen können keine berechneten Metriken oder Metriken enthalten, die auf einem [Zusammenfassungsdatensatz](/help/data-views/summary-data.md) basieren. Wenn Sie versuchen, eine Zielgruppe aus einem Bereich der Journey-Arbeitsfläche zu erstellen, der eine berechnete Metrik oder eine Metrik enthält, die auf einem Zusammenfassungsdatensatz basiert, wird die berechnete Metrik nicht in die Zielgruppendefinition aufgenommen.

1. Wählen Sie [!UICONTROL **Erstellen einer Zielgruppe aus dem Knoten**] oder [!UICONTROL **Erstellen einer Zielgruppe aus Pfeil**] aus.

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

1. Wählen Sie in einer Journey-Arbeitsflächenvisualisierung mindestens einen Knoten aus, für den Sie Trenddaten anzeigen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

   Oder

   Wählen Sie in einer Journey-Arbeitsflächenvisualisierung einen oder mehrere Pfeile zwischen 2 Knoten aus, für die Sie Trenddaten anzeigen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Trend**] aus.

### Erstellen eines auf einem Knoten oder Pfeil basierenden Filters

Sie können einen neuen Filter basierend auf einem Knoten oder Pfeil innerhalb einer Journey erstellen. Nachdem der Filter erstellt wurde, können Sie ihn überall in Analysis Workspace verwenden.

Auf der Arbeitsfläche von Journey erstellte Filter verwenden [sequenzielle Filterung](/help/components/filters/seg-sequential-build.md). Das bedeutet, dass der Filter den THEN -Operator verwendet, um die Ereignissequenz (die Journey) zu verknüpfen, durch die die Besucher den Fluss geleitet haben, und zum ausgewählten Knoten bzw. Pfeil führt. Alle Ereignisse, die mit der ausgewählten Node oder dem ausgewählten Pfeil übereinstimmen, sind im Filter enthalten.

Wenn Sie einen Filter erstellen, der auf einem Knoten basiert, in den mehrere Pfade fließen, werden alle Pfade in den Filter einbezogen. Separate Pfade werden mit dem Operator ODER verbunden.

Erstellen eines Filters:

1. Klicken Sie in einer Journey-Arbeitsflächenvisualisierung mit der rechten Maustaste auf den Knoten oder Pfeil, den Sie zum Erstellen des Filters verwenden möchten.

1. Wählen Sie [!UICONTROL **Filter aus Knoten erstellen**] oder [!UICONTROL **Filter aus Pfeil erstellen**].

   Der Filter-Builder wird angezeigt. Im Abschnitt [!UICONTROL **Definition**] wird die Filterdefinition basierend auf dem von Ihnen ausgewählten Knoten oder Pfeil und seinem Kontext innerhalb der Journey erstellt.

1. Geben Sie einen Titel für den Filter an und nehmen Sie alle anderen Änderungen vor. Weitere Informationen zum Erstellen eines Filters finden Sie unter [Filter-Builder](/help/components/filters/filter-builder.md).

1. Wählen Sie [!UICONTROL **Speichern**] aus, um den Filter zu speichern.

### Knoten löschen

Sie können einen oder mehrere Knoten gleichzeitig innerhalb einer Journey löschen. Wenn Sie einen Knoten löschen, der zwischen zwei Knoten innerhalb des Journey verbunden ist, werden die beiden verbleibenden Knoten direkt verbunden.

So löschen Sie Knoten in der Journey-Arbeitsfläche:

1. Wählen Sie in einer Journey-Arbeitsflächenvisualisierung mindestens einen Knoten aus, den Sie löschen möchten, und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Knoten.

1. Wählen Sie [!UICONTROL **Löschen**] aus.

### Pfeile zwischen Knoten löschen

Sie können einen oder mehrere Pfeile gleichzeitig innerhalb einer Journey löschen. Wenn Sie einen Pfeil zwischen zwei Knoten löschen, sind die Knoten nicht mehr verbunden. Wenn der Pfeil Teil eines längeren Pfads war, wird der Pfad getrennt.

So löschen Sie Pfeile zwischen Knoten in der Journey-Arbeitsfläche:

1. Wählen Sie in einer Journey-Arbeitsflächenvisualisierung einen oder mehrere Pfeile zwischen zwei zu löschenden Nodes aus und klicken Sie dann mit der rechten Maustaste auf einen der ausgewählten Pfeile.

1. Wählen Sie [!UICONTROL **Löschen**] aus.

## Öffnen einer Journey über Journey Optimizer

Wenn Sie eine Journey in Journey Optimizer anzeigen, können Sie sie auf der Journey-Arbeitsfläche anzeigen.

1. Öffnen Sie in Journey Optimizer die Journey, die Sie analysieren möchten, in der Arbeitsfläche des Journey.

1. Wählen Sie [!UICONTROL **Analysieren in CJA**] aus. <!-- ?? -->
