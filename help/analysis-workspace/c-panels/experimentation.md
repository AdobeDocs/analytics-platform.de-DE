---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Panel „Experimentieren“ von Customer Journey Analytics analysieren können.
title: Experimentier-Bedienfeld
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 7e32ae7aa757a8ca47732416f0f883033611ea94
workflow-type: tm+mt
source-wordcount: '2179'
ht-degree: 96%

---

# Experimentier-Bedienfeld {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="Experimentieren"
>abstract="Erstellen Sie ein Bedienfeld, um verschiedene Anwendererlebnisse bzw. Marketing- oder Messaging-Varianten zu vergleichen. Außerdem können Sie dadurch feststellen, welche Variante die beste Lösung für ein bestimmtes Ergebnis ist."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="Experimentieren"
>abstract="Vergleichen Sie verschiedene Anwendererlebnisse bzw. Marketing- oder Messaging-Varianten miteinander, um zu ermitteln, was für ein bestimmtes Ergebnis die beste Lösung ist. Geben Sie das Experiment, die damit zu vergleichende Kontrollvariante, die Erfolgsmetrik und die Normalisierungsmetrik an. Legen Sie optional Ober- und Untergrenzen für die Konfidenz fest."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_In diesem Artikel wird das Panel Experimentieren in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** beschrieben._<br/>_Unter [Panel Analytics for Target](https://experienceleague.adobe.com/de/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) finden Sie Informationen zum Analysieren von Adobe Target-Aktivitäten und -Erlebnissen in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._

>[!ENDSHADEBOX]


Im Panel **[!UICONTROL Experimentieren]** können Analystinnen und Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können den Anstieg und die Konfidenz eines jeden A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten – online, offline, aus Adobe-Lösungen wie Target oder Journey Optimizer und sogar aus eigenen, selbst eingebrachten Daten.

Lesen Sie mehr über die [Integration zwischen Adobe Customer Journey Analytics und Adobe Target](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja).

## Zugangssteuerung {#access}

Das Panel „Experimentieren“ kann von allen Anwendern von Customer Journey Analytics genutzt werden. Es sind keine Administratorrechte oder anderen Berechtigungen erforderlich. Die Voraussetzungen erfordern jedoch Aktionen, die nur Admins ausführen können.

## Funktionen in berechneten Metriken

Zwei erweiterte Funktionen sind verfügbar: Anstieg und Konfidenz. Weitere Informationen finden Sie unter [Referenz – Erweiterte Funktionen](/help/components/calc-metrics/cm-adv-functions.md).

## Voraussetzungen

Um das Panel „Experimentieren“ zu verwenden, müssen Sie die folgenden Voraussetzungen erfüllen:

### Einrichten der Verbindung zu Experimentier-Datensätzen

Laut dem empfohlenen Datenschema sollten die Experimentdaten in einem [Objekt-Array](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/array) gespeichert sein, in dem die Experiment- und Variantendaten in zwei separaten Dimensionen enthalten sind. Beide Dimensionen müssen sich in einem **einzelnen** Objekt-Array befinden. Wenn sich Ihre Experimentdaten in einer einzigen Dimension (und die Experiment- und Variantendaten in einer begrenzten Zeichenfolge) befinden, können Sie die Einstellung der [Unterzeichenfolge](/help/data-views/component-settings/substring.md) in Datenansichten verwenden, um die Dimension zur Verwendung im Panel aufzuteilen.


Wenn Ihre Experimentierdaten in Adobe Experience Platform [erfasst](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/home) sind, können Sie zu einem oder mehreren Testdatensätzen [in Customer Journey Analytics eine Verbindung einrichten](/help/connections/create-connection.md).

### Hinzufügen von Kontextbezeichnungen in Datenansichten

In den Einstellungen für Datenansichten in Customer Journey Analytics können Admins [Kontextbeschriftungen](/help/data-views/component-settings/overview.md) zu einer Dimension oder Metrik hinzufügen, und Customer Journey Analytics-Services wie das Panel [!UICONTROL Experimentieren] können diese Beschriftungen für ihre Zwecke verwenden. Für das Bedienfeld „Experimentieren“ werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experimentierexperiment]
* [!UICONTROL Experimentiervariante]

Wählen Sie in Ihrer Datenansicht, die Experimentierdaten enthält, zwei Dimensionen aus: eine mit den Experimentierdaten und eine mit den Variantendaten. Geben Sie diesen Dimensionen dann die Beschriftungen **[!UICONTROL Experimentierexperiment]** und **[!UICONTROL Variante]**.

![Kontextbeschriftungsoptionen für Experimentieren und Experimentiervariante.](assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Bedienfeld „Experiment“ nicht, da keine Experimente vorhanden sind, mit denen gearbeitet werden kann.

## Verwenden

So verwenden Sie das Panel **[!UICONTROL Experimentieren]**:

1. Erstellen Sie das Panel **[!UICONTROL Experimentieren]**. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).


1. Legen Sie die [Eingabe](#panel-input) für das Bedienfeld fest.

1. Sehen Sie sich die [Ausgabe](#panel-output) für das Bedienfeld an.

   >[!IMPORTANT]
   >
   >Wenn die erforderliche Einrichtung in Customer Journey Analytics-Datenansichten nicht abgeschlossen wurde, erhalten Sie diese Nachricht, bevor Sie fortfahren können: [!UICONTROL Konfigurieren Sie die Experiment- und Variantendimensionen in Datenansichten.].
   >

### Panel-Eingabe

So verwenden Sie das Panel „Experimentieren“:

1. Konfigurieren Sie die Einstellungen für die Panel-Eingabe:

   ![Das Panel Experimentieren, das in ein Projekt gezogen wurde.](assets/experiment-input.png)

   | Einstellung | Definition |
   | --- | --- |
   | **[!UICONTROL Datumsbereich]** | Der Datumsbereich für das Panel „Experimentieren“ wird basierend auf dem ersten Ereignis, das in Customer Journey Analytics für das ausgewählte Experiment empfangen wurde, automatisch festgelegt. Sie können den Datumsbereich bei Bedarf auf einen spezifischeren Zeitraum beschränken oder erweitern. |
   | **[!UICONTROL Experiment]** | Eine Reihe von Varianten eines Erlebnisses, die Endbenutzenden präsentiert wurden, um zu ermitteln, welche am besten dauerhaft beibehalten werden sollte. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante gilt. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in den Datenansichten mit der Beschriftung **[!UICONTROL Experiment]** gekennzeichnet wurden, sowie mit den Experimentdaten der letzten drei Monate. |
   | **[!UICONTROL Kontrollvariante]** | Eine von zwei oder mehr Änderungen im Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden und nur eine Variante kann als Kontrollvariante betrachtet werden. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in den Datenansichten mit der Beschriftung **[!UICONTROL Variante]** gekennzeichnet wurden. Mit dieser Einstellung werden die Variantendaten abgerufen, die mit diesem Experiment verknüpft sind. |
   | **[!UICONTROL Erfolgsmetriken]** ➊ | Die Metrik oder Metriken, die eine Benutzerin bzw. ein Benutzer verwendet. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zur *Variante mit der besten Performance* eines Experiments erklärt. Sie können bis zu 5 Metriken hinzufügen. |
   | **[!UICONTROL Normalisierungsmetrik]** ➋ | Die Basis (**[!UICONTROL Globales Konto &#x200B;** B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Konto]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunity &#x200B;** B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Kauf Gruppe &#x200B;** B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Personen]**, **[!UICONTROL Sitzungen]** oder **[!UICONTROL Ereignis]**), auf der ein Test ausgeführt wird. Ein Test kann z. B. die Konversion Raten verschiedener Varianten vergleichen, wobei **[!UICONTROL die Konversionsrate]** als Seite Ansicht berechnet wird. |
   | **[!UICONTROL Obere/untere Konfidenzgrenzen einbeziehen]** | Aktivieren Sie diese Option, um die oberen und unteren Grenzen für Konfidenzniveaus anzuzeigen. |


1. Wählen Sie **[!UICONTROL Erstellen]** aus.

### Panel-Ausgabe

Das Bedienfeld „Experimentieren“ liefert umfangreiche Daten und Visualisierungen, die Ihnen helfen, die Performance Ihrer Experimente besser zu verstehen. Oben im Panel werden Visualisierungen der [Zusammenfassungsänderung](../visualizations/summary-number-change.md) angezeigt, Sie können das Panel jederzeit bearbeiten, indem Sie oben rechts den Stift zum Bearbeiten auswählen.

Sie erhalten auch eine Textzusammenfassung, die anzeigt, ob das Experiment schlüssig ist oder nicht, und die das Ergebnis zusammenfasst. Das Fazit beruht auf der statistischen Signifikanz (siehe [Statistische Methodik](#adobes-statistical-methodology).) Sie können Zusammenfassungszahlen für die Variante mit der besten Performance mit dem höchsten Anstieg und der höchsten Konfidenz anzeigen.

Für jede ausgewählte Erfolgsmetrik werden eine Visualisierung [Freiformtabelle](../visualizations/freeform-table/freeform-table.md) und eine Visualisierung [Linie](../visualizations/line.md) der Konversionsrate anzeigt:

![Die Ausgabe des Experiments, die eine Freiformtabelle und einen Konversionsraten-Trend zeigt.](assets/experiment-output.png)


>[!NOTE]
>
>Die Analyse von A/A-Tests wird aktuell von diesem Bedienfeld nicht unterstützt.

#### Interpretation der Ergebnisse

1. **Experiment ist endgültig**: Jedes Mal, wenn Sie den Experimentbericht anzeigen, werden die Daten analysiert, die bis zu diesem Zeitpunkt im Experiment gesammelt wurden. Die Analyse erklärt ein Experiment als endgültig, wenn die *jederzeit* gültige Konfidenz einen Schwellenwert von 95 % für *mindestens eine* der Varianten überschreitet. Bei mehr als zwei Armen wird eine Benjamini-Hochberg-Korrektur angewendet, um Mehrfach-Hypothesentests zu korrigieren.

2. **Variante mit der besten Performance**: Wenn ein Experiment als endgültig deklariert wird, wird die Variante mit der höchsten Konversionsrate als Variante mit der besten Performance gekennzeichnet. Beachten Sie, dass diese Variante entweder die Kontroll- bzw. Baseline-Variante sein muss oder eine der Varianten, die die 95-%-ige, *jedrzeit* gültige Konfidenzschwelle überschreiten (mit Benjamini-Hochberg-Korrekturen).

3. **Konversionsrate**: Die angezeigte Konversionsrate ist ein Verhältnis zwischen dem Wert der Erfolgsmetrik ➊ und dem Wert der Normalisierungsmetrik ➋. Beachten Sie, dass dieser Wert manchmal größer als 1 sein kann, wenn die Metrik nicht binär ist (1 oder 0 für jede Einheit im Experiment)

4. **Anstieg**: Die Zusammenfassung des Experimentberichts zeigt den Anstieg im Vergleich zur Baseline und ist somit ein Messwert für die prozentuale Verbesserung der Konversionsrate einer bestimmten Variante gegenüber der Baseline. Genau bestimmt ist dies der Performance-Unterschied zwischen einer bestimmten Variante und der Baseline, geteilt durch die Performance der Baseline und ausgedrückt in Prozent.

5. **Konfidenz**: Die angezeigte jederzeit gültige Konfidenz ist ein wahrscheinlicher Messwert dafür, wie viele Nachweise dafür vorliegen, dass eine bestimmte Variante der Kontrollvariante entspricht. Eine höhere Konfidenz deutet auf weniger Nachweise hin, die die Annahme stützen, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen. Die Konfidenz ist eine Wahrscheinlichkeit (ausgedrückt als Prozentsatz) dafür, dass wir einen kleineren Unterschied bei den Konversionsraten zwischen einer bestimmten Variante und der Kontrollvariante beobachtet hätten. Dabei besteht in Wirklichkeit kein Unterschied bei den zugrunde liegenden tatsächlichen Konversionsraten. Im Hinblick auf *p*-Werte ist die angezeigte Konfidenz 1 - *p*-Wert.

>[!NOTE]
>
>Beachten Sie jedoch, dass bei einer vollständigen Beschreibung der Ergebnisse alle verfügbaren Nachweise berücksichtigt werden sollten (d. h. Experimentaufbau, Stichprobengrößen, Konversionsraten, Konfidenz und andere) und nicht nur, ob das Experiment als endgültig erachtet wird oder nicht. Selbst wenn ein Ergebnis noch nicht „endgültig“ ist, können überzeugende Beweise dafür vorliegen, dass sich eine Variante von einer anderen unterscheidet (z. B. wenn sich Konfidenzintervalle kaum überlappen). Idealerweise sollten alle statistischen Nachweise, die auf einem kontinuierlichen Spektrum interpretiert werden, in die Entscheidungsfindung einfließen.

## Statistische Methodik von Adobe {#statistics}

Um leicht verständliche und sichere statistische Rückschlüsse zu ermöglichen, hat Adobe eine statistische Methodik eingeführt, die auf [Immer gültige Konfidenzsequenzen](https://arxiv.org/abs/2103.06476) basiert.

Eine Konfidenzsequenz ist ein *sequenzielles* Analogon eines Konfidenzintervalls. Um zu verstehen, was eine Konfidenzsequenz ist, stellen Sie sich vor, Ihre Experimente hundertmal zu wiederholen, für *jeden neue Anwender*, der zum Experiment hinzukommt, eine Schätzung der durchschnittlichen Geschäftsmetrik (z. B. Öffnungsrate einer E-Mail) und der zugehörigen 95-%-Konfidenzsequenz durchzuführen.

Eine Konfidenzsequenz von 95 % enthält in 95 der 100 Experimente, die Sie ausgeführt haben, den Wert „true“ der Geschäftsmetrik. (Ein Konfidenzintervall von 95 % kann nur einmal pro Experiment und nicht für jeden einzelnen neuen Anwender berechnet werden, um die gleiche 95-%-Garantie zu erhalten). Konfidenzsequenzen ermöglichen es Ihnen daher, Experimente kontinuierlich zu überwachen, ohne die Falsch-Positiv-Fehlerrate zu erhöhen, d. h. sie ermöglichen einen Einblick in die Ergebnisse.

## Interpretieren nicht-randomisierter Dimensionen {#non-randomized}

Mit Customer Journey Analytics können Analystinnen und Analysten eine beliebige Dimension als Experiment auswählen. Aber wie wird eine Analyse interpretiert, bei der die als Experiment gewählte Dimension nicht diejenige ist, für die die Personen randomisiert werden?

Betrachten Sie beispielsweise eine Anzeige, die eine Person sieht. Es könnte für Sie interessant sein, die Änderung an einer Metrik zu messen (z. B. durchschnittlicher Umsatz), wenn Sie Personen *Anzeige B* anstelle von *Anzeige A* anzeigen. Die Kausalwirkung durch Anzeige B anstelle von Anzeige A ist für die Marketing-Entscheidung von zentraler Bedeutung. Dieser kausale Effekt kann als durchschnittlicher Umsatz über die gesamte Population gemessen werden, wenn Sie den Status quo von Anzeige A durch die alternative Strategie von Anzeige B ersetzt haben.

A/B-Tests sind in der Branche der Goldstandard für die objektive Messung der Auswirkungen solcher Interventionen. Der entscheidende Grund, aus dem ein A/B-Test zu einer kausalen Schätzung führt, liegt in der Randomisierung der Personen, die eine der möglichen Varianten erhalten sollen.

Betrachten wir nun eine Dimension, die nicht durch Randomisierung erreicht wird, zum Beispiel den US-Bundesstaat der Person. Die Personen kommen hauptsächlich aus zwei Bundesstaaten, New York und Kalifornien. Der durchschnittliche Umsatz mit dem Verkauf einer Winterbekleidungsmarke kann in den beiden Bundesstaaten aufgrund der Unterschiede im regionalen Wetter unterschiedlich sein. In einer solchen Situation kann das Wetter der wahre Kausalfaktor für den Verkauf von Winterkleidung sein und nicht die Tatsache, dass die geografischen Staaten von Personen unterschiedlich sind.

Im Panel „Experimentieren“ in Customer Journey Analytics können Sie Daten als durchschnittliche Umsatzdifferenz nach Staaten der Personen analysieren. In einer solchen Situation hat die Ausgabe keine kausale Interpretation. Eine solche Analyse kann jedoch weiterhin von Interesse sein. Sie bietet eine Schätzung (zusammen mit Messgrößen für die Unsicherheit) der Differenz des durchschnittlichen Umsatzes der Staaten der Personen.  Dieser Wert wird auch als *Statistischer Hypothesentest* bezeichnet. Die Ergebnisse dieser Analyse können interessant sein, müssen aber nicht unbedingt umsetzbar sein. Einfach deshalb, weil Sie Personen nicht randomisiert haben und manchmal auch nicht für einen der möglichen Werte der Dimension randomisieren können.

Die folgende Abbildung stellt diese Situationen gegenüber:

![Ein Diagramm mit Beobachtungsdaten und dem randomisierten Experiment.](assets/randomize.png)

Wenn Sie die Auswirkung von Intervention X auf Ergebnis Y messen möchten, kann die wahre Ursache für beide Faktoren der Störfaktor C sein. Wenn die Daten nicht durch die Randomisierung von Personen für X erhalten werden, ist die Auswirkung schwieriger zu messen, und die Analyse berücksichtigt explizit C. Die Randomisierung beseitigt die Abhängigkeit von X auf C, sodass wir die Wirkung von X auf Y messen können, ohne uns über andere Variablen Gedanken machen zu müssen.

## Verwenden von berechneten Metriken in Experimenten {#use-in-experimentation}

>[!NOTE]
>
>Für Organisationen, die sowohl Customer Journey Analytics als auch Adobe Journey Optimizer verwenden, gelten die Informationen in diesem Abschnitt auch für Experimentierfunktionen in Journey Optimizer.

Nicht alle berechneten Metriken sind mit dem Panel „Experimentieren“ kompatibel.

Berechnete Metriken, die eine der folgenden Metriken oder Konstanten enthalten, sind nicht mit dem Panel „Experimentieren“ kompatibel:

* Basismetriken aus einem [Zusammenfassungsdatensatz](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/summary-data)
* Basismetriken, die untereinander aufgeteilt oder miteinander multipliziert werden (z. B. `Revenue`/`Orders`)
* Konstanten, die zu einer Basismetrik hinzugefügt oder von ihr subtrahiert werden (z. B. `Revenue+50`)
* Eine der folgenden Basismetriken:
   * Personen

Beim Erstellen der berechneten Metrik haben berechnete Metriken, die nicht mit dem Panel Experimentieren kompatibel sind, den Wert: [!UICONTROL **Überall in Customer Journey Analytics (außer beim Experimentieren)**] im Feld [!UICONTROL **Produktkompatibilität**]. Informationen zum Erstellen einer berechneten Metrik finden Sie unter [Erstellen von Metriken](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Verwenden von berechneten Metriken im Panel Experimentieren

In diesem Blogpost finden Sie Informationen zur [Verwendung berechneter Metriken im Panel Experimentieren](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).

>[!MORELIKETHIS]
>[Meistern von Experimentenen in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
