---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Bereich Customer Journey Analytics-Experimentierung analysieren können.
title: Experimentier-Bedienfeld
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '2167'
ht-degree: 23%

---

# Experimentier-Bedienfeld {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_experimentation_button"
>title="Experimentieren"
>abstract="Erstellen Sie ein Bedienfeld, um verschiedene Varianten von Benutzererlebnissen, Marketing- oder Messaging zu vergleichen. Und um festzustellen, welche Variante am besten zu einem bestimmten Ergebnis führt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_experimentation_panel"
>title="Experimentieren"
>abstract="Vergleichen Sie verschiedene Benutzererfahrungen, Marketing- oder Messaging-Variationen, um zu bestimmen, welche am besten geeignet ist, um ein bestimmtes Ergebnis zu erzielen.<br/><br/>**Parameter **<br/>**Experiment**: Das zu analysierende Experiment.<br>**Kontrollvariante**: Kontrollvariante für das ausgewählte Experiment.<br/>**Erfolgsmetrik**: Bis zu 5 standardmäßige (nicht berechnete) Erfolgsmetriken zur Analyse des Experiments.<br/>**Normalisierungsmetrik**: Personen, Sitzungen oder Ereignisse. Diese Metrik (auch als Zählmethodik bezeichnet) wird zum Nenner der Steigerungsberechnung. Diese Metrik wirkt sich auch darauf aus, wie die Daten aggregiert werden, bevor die Konfidenzberechnung angewendet wird."

<!-- markdownlint-enable MD034 -->



Im Bedienfeld **[!UICONTROL Experimentieren]** können Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können die Steigerung und Konfidenz jedes A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten: online, offline, von Adobe-Lösungen wie Target oder Journey Optimizer und sogar von BYO-Daten (eigene Daten).

Erfahren Sie mehr über die [Integration zwischen Adobe Customer Journey Analytics und Adobe Target](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja).

## Zugangssteuerung {#access}

Das Experimentierungsfenster steht allen Customer Journey Analytics-Benutzern zur Verfügung. Es sind keine Administratorrechte oder anderen Berechtigungen erforderlich. Für die [Voraussetzungen](#prerequisites) sind jedoch Aktionen erforderlich, die nur Administratoren ausführen können.

## Neue Funktionen in berechneten Metriken

Zwei neue erweiterte Funktionen wurden hinzugefügt: Steigerung und Konfidenz. Weitere Informationen finden Sie unter [Referenz – Erweiterte Funktionen](/help/components/calc-metrics/cm-adv-functions.md).

## Voraussetzungen

Um das Experimentierfeld zu verwenden, müssen Sie die folgenden Voraussetzungen erfüllen:

### Verbindung zu Experimentdatensätzen erstellen

Laut dem empfohlenen Datenschema sollten die Experimentdaten in einem [Objekt-Array](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) gespeichert sein, in dem die Experiment- und Variantendaten in zwei separaten Dimensionen enthalten sind. Beide Dimensionen müssen sich in einem **einzelnen** -Objektarray befinden. Wenn sich Ihre Experimentdaten in einer einzigen Dimension befinden (mit Experiment- und Variantendaten in einer getrennten Zeichenfolge), können Sie die Einstellung [substring](/help/data-views/component-settings/substring.md) in Datenansichten verwenden, um die Dimension zur Verwendung im Bedienfeld in zwei aufzuteilen.

Nachdem Ihre Experimentdaten [ in Adobe Experience Platform aufgenommen wurden, erstellen [in Customer Journey Analytics](/help/connections/create-connection.md) eine Verbindung zu einem oder mehreren Experimentdatensätzen.](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)

### Hinzufügen von Kontextbezeichnungen in Datenansichten

In den Einstellungen für Customer Journey Analytics-Datenansichten können Administratoren einer Dimension oder Metrik [Kontextbezeichnungen](/help/data-views/component-settings/overview.md) hinzufügen und Customer Journey Analytics-Dienste wie das Bedienfeld [!UICONTROL Experimentation] können diese Bezeichnungen für ihre Zwecke verwenden. Für das Bedienfeld „Experimentieren“ werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experimentierexperiment]
* [!UICONTROL Experimentiervariante]

Wählen Sie in Ihrer Datenansicht, die Experimentierdaten enthält, zwei Dimensionen aus: eine mit den Experimentierdaten und eine mit den Variantendaten. Benennen Sie diese Dimensionen dann mit den Beschriftungen **[!UICONTROL Experimentierexperiment]** und **[!UICONTROL Experimentvariante]** .

![Optionen für die Kontextbeschriftung für die Experimentierungs- und Experimentierungsvariante.](assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Bedienfeld „Experiment“ nicht, da keine Experimente vorhanden sind, mit denen gearbeitet werden kann.

## Verwenden Sie stattdessen 

So verwenden Sie ein Bedienfeld **[!UICONTROL Experimentation]** :

1. Erstellen Sie ein Bedienfeld &quot;**[!UICONTROL Experimentation]**&quot;. Informationen zum Erstellen eines Bedienfelds finden Sie unter [Erstellen eines Bedienfelds](panels.md#create-a-panel).


1. Geben Sie die [Eingabe](#panel-input) für das Bedienfeld an.

1. Beobachten Sie die [Ausgabe](#panel-output) für das Bedienfeld.

   ![Das Bedienfeld &quot;Erlebnis&quot;wurde in ein Projekt gezogen.](assets/experiment.png)

   >[!IMPORTANT]
   >
   >Wenn die erforderliche Einrichtung in Customer Journey Analytics-Datenansichten nicht abgeschlossen wurde, erhalten Sie diese Nachricht, bevor Sie fortfahren können: [!UICONTROL Konfigurieren Sie die Dimensionen für Experiment und Variante in Datenansichten].
   >

### Bedienfeldeingabe

So verwenden Sie das Experimentierfeld:

1. Konfigurieren Sie die Bedienfeldeingabeeinstellungen:

   | Einstellung | Definition |
   | --- | --- |
   | **[!UICONTROL Datumsbereich]** | Der Datumsbereich für das Experimentierungsfenster wird automatisch festgelegt, basierend auf dem ersten Ereignis, das beim Customer Journey Analytics für das ausgewählte Experiment empfangen wurde. Sie können den Datumsbereich bei Bedarf auf einen spezifischeren Zeitraum beschränken oder erweitern. |
   | **[!UICONTROL Experiment]** | Eine Reihe von Varianten eines Erlebnisses, die Endbenutzern bereitgestellt wurden, um zu ermitteln, welche Erlebnisse am besten dauerhaft beibehalten werden sollten. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante gilt. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in Datenansichten mit der Beschriftung **[!UICONTROL Experiment]** und den Experimentdaten der letzten drei Monate gekennzeichnet wurden. |
   | **[!UICONTROL Kontrollvariante]** | Eine von zwei oder mehr Änderungen im Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden und nur eine Variante kann als Kontrollvariante betrachtet werden. Diese Einstellung enthält vorab die Dimensionen, die in Datenansichten mit der Bezeichnung **[!UICONTROL Variante]** gekennzeichnet wurden. Mit dieser Einstellung werden die Variantendaten abgerufen, die mit diesem Experiment verknüpft sind. |
   | **[!UICONTROL Erfolgsmetriken]** | Die Metrik(en), die ein Anwender verwendet, um Varianten zu vergleichen. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zur „Variante mit der besten Performance“ eines Experiments erklärt. Sie können bis zu 5 Metriken hinzufügen. |
   | **[!UICONTROL Normalisierungsmetrik]** | Die Grundlage ([!UICONTROL Personen], [!UICONTROL Sitzungen] oder [!UICONTROL Ereignisse]), auf der ein Test ausgeführt wird. Beispielsweise kann ein Test die Konversionsraten verschiedener Varianten vergleichen, bei denen die **[!UICONTROL Konversionsrate]** als **[!UICONTROL Konversionen pro Sitzung]** oder **[!UICONTROL Konversionen pro Person]** berechnet wird. |
   | **[!UICONTROL Obere/untere Konfidenzgrenzen einschließen]** | Aktivieren Sie diese Option, um Obergrenzen und Untergrenzen für Konfidenzniveaus anzuzeigen. |


1. Wählen Sie **[!UICONTROL Erstellen]** aus.

### Bedienfeldausgabe

Das Bedienfeld „Experimentieren“ liefert umfangreiche Daten und Visualisierungen, die Ihnen helfen, die Performance Ihrer Experimente besser zu verstehen. Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert. Sie können das Bedienfeld jederzeit bearbeiten, indem Sie oben rechts den Stift zum Bearbeiten auswählen.

Sie erhalten auch eine Textzusammenfassung, die anzeigt, ob das Experiment schlüssig ist oder nicht, und die das Ergebnis zusammenfasst. Die Zusammenfassung basiert auf der statistischen Bedeutung (siehe [Statistische Methode](#adobes-statistical-methodology)). Sie können Zusammenfassungszahlen für die Variante mit der besten Performance mit dem höchsten Anstieg und der höchsten Konfidenz anzeigen.

Für jede ausgewählte Erfolgsmetrik wird eine Freiformtabelle und ein Konversionsraten-Trend angezeigt.

![Die Experimentierungsausgabe, die eine Freiformtabelle und einen Konversionsratentrend anzeigt.](assets/exp-output1.png)

Das [!UICONTROL Liniendiagramm] zeigt Ihnen die Performance von [!UICONTROL Kontrolle] im Vergleich zur [!UICONTROL Kontrollvariante]:

![Die Liniendiagrammausgabe, die die Leistung von Kontroll- und Kontrollvarianten anzeigt.](assets/exp-output2.png)

>[!NOTE]
>
>Die Analyse von A/A-Tests wird aktuell von diesem Bedienfeld nicht unterstützt.

#### Interpretieren der Ergebnisse

1. **Experiment ist abgeschlossen**: Jedes Mal, wenn Sie den Experimentbericht anzeigen, werden die bis zu diesem Zeitpunkt im Experiment angesammelten Daten analysiert. Die Analyse deklariert einen Versuch als abgeschlossen, wenn die jederzeit gültige Konfidenz für mindestens eine der Varianten einen Schwellenwert von 95 % für *1} überschreitet.* Mit mehr als zwei Armen wird eine Benjamini-Hochberg Korrektur vorgenommen, um die Mehrfachhypothesentests zu korrigieren.

2. **Variante mit der besten Leistung**: Wenn ein Experiment für schlüssig erklärt wird, wird die Variante mit der höchsten Konversionsrate als die Variante mit der besten Performance gekennzeichnet. Beachten Sie, dass es sich bei dieser Variante entweder um die Kontroll- oder Grundvariante oder um eine der Varianten handeln muss, die die 95%-Schwelle jederzeit überschreiten (bei Anwendung von Benjamini-Hochberg-Korrekturen).

3. **Konversionsrate**: Die angezeigte Konversionsrate ist ein Verhältnis zwischen dem Erfolgsmetrikwert und dem normalisierenden Metrikwert. Beachten Sie, dass dieser Wert manchmal größer als 1 sein kann, wenn die Metrik nicht binär ist (1 oder 0 für jede Einheit im Experiment)

4. **Steigerung**: Die Zusammenfassung des Experimentberichts zeigt die Steigerung gegenüber der Grundlinie, die eine Messung der prozentualen Verbesserung der Konversionsrate einer bestimmten Variante gegenüber der Grundlinie darstellt. Genau bestimmt ist dies der Performance-Unterschied zwischen einer bestimmten Variante und der Baseline, geteilt durch die Performance der Baseline und ausgedrückt in Prozent.

5. **Konfidenz**: Die jederzeit gültige Konfidenz, die angezeigt wird, ist ein probabilistischer Messwert dafür, wie viele Beweise dafür vorliegen, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Eine höhere Konfidenz deutet auf weniger Nachweise hin, die die Annahme stützen, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen. Die Konfidenz ist eine Wahrscheinlichkeit (ausgedrückt als Prozentsatz), die Sie in Bezug auf die Konversionsraten zwischen einer bestimmten Variante und der Kontrollgruppe gesehen hätten. Während in Wirklichkeit gibt es keinen Unterschied in den zugrunde liegenden tatsächlichen Konversionsraten. Im Hinblick auf *p*-Werte ist die angezeigte Konfidenz 1 - *p*-Wert.

>[!NOTE]
>
>Bei einer vollständigen Beschreibung der Ergebnisse sollten alle verfügbaren Beweise berücksichtigt werden (z. B. Versuchsdesign, Stichprobengrößen, Konversionsraten, Konfidenz und andere), und nicht nur die endgültige Erklärung. Selbst wenn ein Ergebnis noch nicht schlüssig ist, kann es dennoch überzeugende Beweise dafür geben, dass sich eine Variante von einer anderen unterscheidet (Konfidenzintervalle sind beispielsweise nahezu nicht überlappend). Idealerweise sollten alle statistischen Nachweise, die auf einem kontinuierlichen Spektrum interpretiert werden, die Entscheidungsfindung beeinflussen.

## Statistische Methodik von Adobe {#statistics}

Um leicht verständliche und sichere statistische Rückschlüsse zu ermöglichen, hat Adobe eine statistische Methodik eingeführt, die auf [Immer gültige Konfidenzsequenzen](https://arxiv.org/abs/2103.06476) basiert.

Eine Konfidenzsequenz ist ein *sequenzielles* Analogon eines Konfidenzintervalls. Um zu verstehen, was eine Konfidenzsequenz ist, stellen Sie sich vor, Sie wiederholen Ihre Experimente hundertmal. Und berechnen Sie eine Schätzung der durchschnittlichen Geschäftsmetrik (z. B. die Öffnungsrate einer E-Mail) und der zugehörigen 95-%-Konfidenzsequenz für *jeden neuen Benutzer*, der in das Experiment eintritt.

Eine Konfidenzsequenz von 95 % umfasst den &quot;true&quot;-Wert der Geschäftsmetrik in 95 der 100 Experimente, die Sie ausgeführt haben. (Ein Konfidenzintervall von 95 % kann nur einmal pro Experiment berechnet werden, um die gleiche 95-%-Garantie zu erhalten, nicht bei jedem neuen Benutzer.) Konfidenzsequenzen ermöglichen es Ihnen daher, Experimente kontinuierlich zu überwachen, ohne die Falsch-Positiv-Fehlerrate zu erhöhen, d. h. sie ermöglichen einen &quot;Peeking&quot; bei den Ergebnissen.

## Nicht randomisierte Dimensionen interpretieren {#non-randomized}

Mit Customer Journey Analytics können Analysten eine beliebige Dimension als Experiment auswählen. Aber wie interpretieren Sie eine Analyse, bei der die als Experiment gewählte Dimension nicht diejenige ist, für die Personen randomisiert werden?

Betrachten Sie beispielsweise eine Anzeige, die eine Person sieht. Sie können an der Messung der Änderung in einer Metrik interessiert sein (z. B. Durchschnittsumsatz), wenn Sie Personen *und B* anstelle von *und A* anzeigen. Der kausale Effekt der Anzeige von Anzeige B anstelle von Anzeige A ist für die Marketing-Entscheidung von zentraler Bedeutung. Dieser kausale Effekt kann als durchschnittlicher Umsatz über die gesamte Population gemessen werden, wenn Sie den Status quo der Anzeige von Anzeige A durch die alternative Strategie der Anzeige B ersetzen.

A/B-Tests sind der Goldstandard innerhalb der Branche zur objektiven Messung der Auswirkungen solcher Interventionen. Der entscheidende Grund, warum ein A/B-Test zu einer kausalen Schätzung führt, liegt in der Randomisierung der Personen, eine der möglichen Varianten zu erhalten.

Betrachten wir nun eine Dimension, die nicht durch Randomisierung erreicht wird, z. B. den US-Bundesstaat der Person. Personen kommen hauptsächlich aus zwei Staaten, New York und Kalifornien. Der durchschnittliche Umsatz der Verkäufe einer Winterbekleidungsmarke kann in den beiden Bundesstaaten aufgrund der unterschiedlichen regionalen Wetterbedingungen unterschiedlich sein. In einer solchen Situation kann das Wetter der wahre ursächliche Faktor für den Verkauf von Winterkleidung sein, und nicht die Tatsache, dass die geografischen Status der Personen unterschiedlich sind.

Im Experimentierbereich in Customer Journey Analytics können Sie Daten als durchschnittliche Umsatzdifferenz nach Personenstand analysieren. In einem solchen Fall hat die Ausgabe keine kausale Interpretation. Eine solche Analyse kann jedoch dennoch von Interesse sein. Er enthält eine Schätzung (zusammen mit Unsicherheitsmessungen) der Differenz der durchschnittlichen Einnahmen nach Staaten der Personen.  Dieser Wert wird auch als *Testen statistischer Hypothesen* bezeichnet. Das Ergebnis dieser Analyse mag interessant sein, aber nicht unbedingt umsetzbar. Einfach, weil Sie keine zufällige Auswahl getroffen haben und Personen manchmal nicht nach einem der möglichen Werte der Dimension zuordnen können.

Die folgende Abbildung widerspricht diesen Situationen:

![Ein Diagramm, das Beobachtungsdaten und das randomisierte Experiment anzeigt.](assets/randomize.png)

Wenn Sie die Wirkung von Intervention X auf das Ergebnis Y messen möchten, ist es möglich, dass die wahre Ursache für beide der verwirrende Faktor C ist. Wenn die Daten nicht durch eine zufällige Personalisierung auf X erreicht werden, ist die Auswirkung schwieriger zu messen, und die Analyse berücksichtigt explizit C. Randomisierung unterbricht die Abhängigkeit von X auf C, sodass wir die Wirkung von X auf Y messen können, ohne sich um andere Variablen kümmern zu müssen.

## Verwenden von berechneten Metriken in Experimenten {#use-in-experimentation}

>[!NOTE]
>
>Für Unternehmen, die sowohl Customer Journey Analytics als auch Adobe Journey Optimizer verwenden, gelten die Informationen in diesem Abschnitt auch für Experimentierungsfunktionen in Journey Optimizer.


Nicht alle berechneten Metriken sind mit dem Experimentierungsbereich kompatibel.

Berechnete Metriken, die eine der folgenden Metriken oder Konstanten enthalten, sind nicht mit dem Experimentierungsbereich kompatibel:

* Basismetriken aus einem Zusammenfassungsdatensatz<!--add link to Rob's "Summary data" doc when it's published -->
* Basismetriken, die untereinander aufgeteilt oder miteinander multipliziert werden (z. B. `Revenue`/`Orders`)
* Konstanten, die zu einer Basismetrik hinzugefügt oder von dieser abgezogen werden (z. B. `Revenue+50`)
* Eine der folgenden Basismetriken:
   * Personen

Berechnete Metriken, die nicht mit dem Experimentierungsbereich kompatibel sind, haben beim Erstellen der berechneten Metrik den Wert [!UICONTROL **Überall auf Customer Journey Analytics (außer Experimentierung)**] im Feld [!UICONTROL **Produktkompatibilität**] . Informationen zum Erstellen einer berechneten Metrik finden Sie unter [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Berechnete Metriken im Experimentierungsbereich verwenden

In diesem Blogpost finden Sie Informationen zu [Verwendung berechneter Metriken im Experimentierungsbereich](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
