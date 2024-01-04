---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Bereich Customer Journey Analytics-Experimentierung analysieren können.
title: Experimentier-Bedienfeld
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1892'
ht-degree: 58%

---

# Experimentier-Bedienfeld

Im Bedienfeld **[!UICONTROL Experimentieren]** können Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können den Anstieg und die Konfidenz eines jeden A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten – online, offline, aus Adobe-Lösungen, über Adobe Journey Optimizer und sogar aus eigenen BYO (bring-your-own)-Daten.

>[!IMPORTANT]
>
>An dieser Stelle [Adobe Analytics für Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=de) (A4T)-Daten *cannot* im Bereich Experimentierung analysiert werden.

## Zugriffssteuerung {#access}

Das Experimentierungsfenster steht allen Customer Journey Analytics-Benutzern zur Verfügung. Es sind keine Administratorrechte oder anderen Berechtigungen erforderlich. Die Einrichtung (Schritte 1 und 2 unten) erfordert jedoch Aktionen, die nur Administratoren durchführen können.

## Neue Funktionen in berechneten Metriken {#functions}

Zwei neue erweiterte Funktionen wurden hinzugefügt: [!UICONTROL Anstieg] und [!UICONTROL Konfidenz]. Weitere Informationen finden Sie unter [Referenz – Erweiterte Funktionen](/help/components/calc-metrics/cm-adv-functions.md).

## Schritt 1: Einrichten der Verbindung zu Experimentier-Datensätzen {#connection}

Laut dem empfohlenen Datenschema sollten die Experimentdaten in einem [Objekt-Array](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html?lang=de) gespeichert sein, in dem die Experiment- und Variantendaten in zwei separaten Dimensionen enthalten sind. Beide Dimensionen müssen in einer **single** Objekt-Array. Wenn sich Ihre Experimentdaten in einer einzigen Dimension und die Experiment- und Variantendaten in einer begrenzten Zeichenfolge befinden, können Sie die Einstellung der [Teilzeichenfolge](/help/data-views/component-settings/substring.md) in Datenansichten verwenden, um sie zur Verwendung im Bedienfeld aufzuteilen.

Nachdem Ihre Experimentdaten [erfasst](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) nach Adobe Experience Platform, [Erstellen einer Verbindung in Customer Journey Analytics](/help/connections/create-connection.md) zu einem oder mehreren Experimentdatensätzen hinzufügen.

## Schritt 2: Hinzufügen von Kontextbezeichnungen in Datenansichten {#contect-labels}

In den Einstellungen für Customer Journey Analytics-Datenansichten können Administratoren [Kontextbezeichnungen](/help/data-views/component-settings/overview.md) zu einer Dimension oder Metrik und Customer Journey Analytics-Diensten wie [!UICONTROL Experimentieren] -Bedienfeld können diese Beschriftungen für ihre Zwecke verwenden. Für das Bedienfeld „Experimentieren“ werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experimentierexperiment]
* [!UICONTROL Experimentiervariante]

Wählen Sie in Ihrer Datenansicht, die Experimentierdaten enthält, zwei Dimensionen aus: eine mit den Experimentierdaten und eine mit den Variantendaten. Geben Sie diesen Dimensionen dann die Beschriftungen **[!UICONTROL Experiment]** und **[!UICONTROL Variante]**.

![Kontextbeschriftungsoptionen für Experimentierungs- und Experimentierungsvarianten.](assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Bedienfeld „Experiment“ nicht, da keine Experimente vorhanden sind, mit denen gearbeitet werden kann.

## Schritt 3: Konfigurieren des Bedienfelds „Experiment“ {#configure}

1. Ziehen Sie in Customer Journey Analytics Workspace das Experimentierfeld in ein Projekt.

![Das Bedienfeld Erlebnis zog sich in ein Projekt.](assets/experiment.png)

>[!IMPORTANT]
>Wenn die erforderliche Einrichtung in Customer Journey Analytics-Datenansichten nicht abgeschlossen wurde, erhalten Sie diese Nachricht, bevor Sie fortfahren können: &quot;[!UICONTROL Konfigurieren Sie die Experiment- und Variantendimensionen in Datenansichten.]&quot;.

1. Konfigurieren Sie die Einstellungen für die Bedienfeldeingabe.

   | Einstellung | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | Eine Reihe von Varianten eines Erlebnisses, die Endbenutzern präsentiert wurden, um zu ermitteln, welche am besten dauerhaft beibehalten werden sollte. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante gilt. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in den Datenansichten mit der Beschriftung **[!UICONTROL Experiment]** gekennzeichnet wurden, sowie mit den Experimentdaten der letzten drei Monate. |
   | **[!UICONTROL Kontrollvariante]** | Eine von zwei oder mehr Änderungen im Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden und nur eine Variante kann als Kontrollvariante betrachtet werden. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in den Datenansichten mit der Beschriftung **[!UICONTROL Variante]** gekennzeichnet wurden. Mit dieser Einstellung werden die Variantendaten abgerufen, die mit diesem Experiment verknüpft sind. |
   | **[!UICONTROL Erfolgsmetriken]** | Die Metrik(en), die ein Anwender verwendet, um Varianten zu vergleichen. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zur „Variante mit der besten Performance“ eines Experiments erklärt. Sie können bis zu 5 Metriken hinzufügen. |
   | **[!UICONTROL Normalisierungsmetrik]** | Grundlage ([!UICONTROL Personen], [!UICONTROL Sitzungen] oder [!UICONTROL Ereignisse]) für die Ausführung eines Tests. Beispielsweise kann ein Test die Konversionsraten verschiedener Varianten vergleichen, bei denen die **[!UICONTROL Konversionsrate]** als **[!UICONTROL Konversionen pro Sitzung]** oder **[!UICONTROL Konversionen pro Person]** berechnet wird. |
   | **[!UICONTROL Datumsbereich]** | Der Datumsbereich wird automatisch festgelegt, basierend auf dem ersten Ereignis, das beim Customer Journey Analytics für das ausgewählte Experiment empfangen wurde. Sie können den Datumsbereich bei Bedarf auf einen spezifischeren Zeitraum beschränken oder erweitern. |

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

## Schritt 4: Anzeigen der Bedienfeldausgabe {#view}

Das Bedienfeld „Experimentieren“ liefert umfangreiche Daten und Visualisierungen, die Ihnen helfen, die Performance Ihrer Experimente besser zu verstehen. Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert. Sie können das Bedienfeld jederzeit bearbeiten, indem Sie oben rechts auf den Stift zum Bearbeiten klicken.

Sie erhalten auch eine Textzusammenfassung, die anzeigt, ob das Experiment schlüssig ist oder nicht, und die das Ergebnis zusammenfasst. Das Fazit beruht auf der statistischen Signifikanz. (Siehe unten unter „Statistische Methodik“.) Sie können Zusammenfassungszahlen für die Variante mit der besten Performance mit dem höchsten Anstieg und der höchsten Konfidenz anzeigen.

Für jede ausgewählte Erfolgsmetrik wird eine Freiformtabelle und ein Konversionsraten-Trend angezeigt.

![Die Experimentierungsausgabe, die eine Freiformtabelle und einen Konversionsraten-Trend anzeigt.](assets/exp-output1.png)

Das [!UICONTROL Liniendiagramm] zeigt Ihnen die Performance von [!UICONTROL Kontrolle] im Vergleich zur [!UICONTROL Kontrollvariante]:

![Die Liniendiagrammausgabe, die die Leistung von Control versus Control Variant anzeigt.](assets/exp-output2.png)

>[!NOTE]
>
>Die Analyse von A/A-Tests wird aktuell von diesem Bedienfeld nicht unterstützt.

## Schritt 5: Interpretieren der Ergebnisse {#interpret}

1. **Experiment ist abgeschlossen**: Jedes Mal, wenn Sie den Experimentbericht anzeigen, analysiert Adobe die Daten, die bis zu diesem Zeitpunkt im Experiment gesammelt wurden, und deklariert einen Versuch als &quot;Fazit&quot;, wenn das jederzeit gültige Vertrauen einen Schwellenwert von 95 % für *mindestens ein* der Varianten (mit einer Benjamini-Hochberg Korrektur, wenn mehr als zwei Arme vorhanden sind, zur Korrektur der Mehrfachhypothesen).

2. **Variante mit der besten Performance**: Wenn ein Experiment als endgültig deklariert wird, wird die Variante mit der höchsten Konversionsrate als „Variante mit der besten Performance“ gekennzeichnet. Beachten Sie, dass es sich bei dieser Variante entweder um die Kontroll- oder Grundvariante oder um eine der Varianten handeln muss, die die 95%-Schwelle jederzeit überschreiten (bei Anwendung von Benjamini-Hochberg-Korrekturen).

3. **Konversionsrate**: Die angezeigte Konversionsrate ist ein Verhältnis zwischen dem Wert der Erfolgsmetrik und dem Wert der Normalisierungsmetrik. Beachten Sie, dass dies manchmal größer als 1 sein kann, wenn die Metrik nicht binär ist (1 oder 0 für jede Einheit im Experiment)

4. **Anstieg**: Die Zusammenfassung des Experimentberichts zeigt den Anstieg im Vergleich zur Baseline und ist somit ein Messwert für die prozentuale Verbesserung der Konversionsrate einer bestimmten Variante gegenüber der Baseline. Genau bestimmt ist dies der Performance-Unterschied zwischen einer bestimmten Variante und der Baseline, geteilt durch die Performance der Baseline und ausgedrückt in Prozent.

5. **Konfidenz**: Die angezeigte „immer gültige Konfidenz“ ist ein wahrscheinlicher Messwert dafür, wie viele Nachweise dafür vorliegen, dass eine bestimmte Variante der Kontrollvariante entspricht. Eine höhere Konfidenz deutet auf weniger Nachweise hin, die die Annahme stützen, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen. Genauer gesagt ist die angezeigte Konfidenz eine Wahrscheinlichkeit (ausgedrückt als Prozentsatz), dass wir einen kleineren Unterschied bei den Konversionsraten zwischen einer bestimmten Variante und der Kontrollvariante beobachtet hätten, wenn in Wirklichkeit kein Unterschied bei den zugrunde liegenden tatsächlichen Konversionsraten besteht. Im Hinblick auf *p*-Werte ist die angezeigte Konfidenz 1 - *p*-Wert.

>[!NOTE]
>
>Beachten Sie jedoch, dass bei einer vollständigen Beschreibung der Ergebnisse alle verfügbaren Nachweise berücksichtigt werden sollten (d. h. Experimentaufbau, Stichprobengrößen, Konversionsraten, Konfidenz usw.) und nicht nur, ob das Experiment als schlüssig erachtet wird oder nicht. Selbst wenn ein Ergebnis noch nicht „schlüssig“ ist, können überzeugende Beweise dafür vorliegen, dass sich eine Variante von einer anderen unterscheidet (z. B. wenn sich Konfidenzintervalle kaum überlappen). Idealerweise sollte die Entscheidungsfindung unter Berücksichtigung aller statistischen Daten, die auf einem kontinuierlichen Spektrum interpretiert werden, erfolgen.

## Statistische Methodik von Adobe {#statistics}

Um leicht verständliche und sichere statistische Rückschlüsse zu ermöglichen, hat Adobe eine statistische Methodik eingeführt, die auf [Immer gültige Konfidenzsequenzen](https://doi.org/10.48550/arXiv.2103.06476) basiert.

Eine Konfidenzsequenz ist ein „sequenzielles“ Analogon eines Konfidenzintervalls. Um zu verstehen, was eine Konfidenzsequenz ist, stellen Sie sich Folgendes vor: Sie wiederholen Ihre Experimente hundertmal und für *jede(n) neue Benutzende(n)*, der/die zum Experiment hinzukommt, wird eine Schätzung der durchschnittlichen Geschäftskenngröße (z. B. Öffnungsrate einer E-Mail) und der zugehörigen 95-%-Konfidenzsequenz durchgeführt.

Eine Konfidenzsequenz von 95 % enthält in 95 der 100 Experimente, die Sie ausgeführt haben, den Wert „true“ der Geschäftsmetrik. (Ein Konfidenzintervall von 95 % kann nur einmal pro Experiment und nicht für jeden einzelnen neuen Anwender berechnet werden, um die gleiche 95-%-Garantie zu erhalten.) Konfidenzsequenzen ermöglichen es Ihnen daher, Experimente kontinuierlich zu überwachen, ohne die Falsch-Positiv-Fehlerrate zu erhöhen, d. h. sie ermöglichen einen Einblick in die Ergebnisse.

## Nicht randomisierte Dimensionen interpretieren {#non-randomized}

Mit Customer Journey Analytics können Analysten eine beliebige Dimension als &quot;Experiment&quot;auswählen. Aber wie interpretieren Sie eine Analyse, bei der die als Experiment gewählte Dimension nicht diejenige ist, für die Personen randomisiert werden?

Betrachten Sie beispielsweise eine Anzeige, die eine Person sieht. Sie können an der Messung der Veränderung in einer Metrik interessiert sein (z. B. der durchschnittliche Umsatz), wenn Sie Personen &quot;Anzeige B&quot;anstelle von &quot;Anzeige A&quot;anzeigen. Der kausale Effekt, dass anstelle von Anzeige A Anzeige B angezeigt wird, ist für die Marketing-Entscheidung von zentraler Bedeutung. Dieser kausale Effekt kann als durchschnittlicher Umsatz über die gesamte Population gemessen werden, wenn wir den Status quo der Anzeige von Anzeige A durch die alternative Strategie der Anzeige B ersetzen.

A/B-Tests sind der Goldstandard innerhalb der Branche zur objektiven Messung der Auswirkungen solcher Interventionen. Der entscheidende Grund, warum ein A/B-Test zu einer kausalen Schätzung führt, liegt in der Randomisierung der Personen, eine der möglichen Varianten zu erhalten.

Betrachten wir nun eine Dimension, die nicht durch Randomisierung erreicht wird, z. B. den US-Bundesstaat der Person. Nehmen wir an, unsere Personen kommen hauptsächlich aus zwei Staaten, New York und Kalifornien. Der durchschnittliche Umsatz der Verkäufe einer Winterbekleidungsmarke kann in den beiden Bundesstaaten aufgrund der unterschiedlichen regionalen Wetterbedingungen unterschiedlich sein. In einer solchen Situation kann das Wetter der wahre ursächliche Faktor für den Verkauf von Winterkleidung sein, und nicht die Tatsache, dass die geografischen Status der Personen unterschiedlich sind.

Im Experimentierbereich in Customer Journey Analytics können Sie Daten als durchschnittliche Umsatzdifferenz nach Personenstand analysieren. In einem solchen Fall hat die Ausgabe keine kausale Interpretation. Eine solche Analyse kann jedoch dennoch von Interesse sein. Er enthält eine Schätzung (zusammen mit Unsicherheitsmessungen) der Differenz der durchschnittlichen Einnahmen nach Staaten der Personen. Dies wird auch als &quot;Testen statistischer Hypothesen&quot;bezeichnet. Die Ergebnisse dieser Analyse sind vielleicht interessant, aber nicht unbedingt umsetzbar, da wir Personen nicht zufällig auf einen der möglichen Werte der Dimension verweisen und manchmal auch nicht zuordnen können.

Die folgende Abbildung widerspricht diesen Situationen:

![Ein Diagramm, das Beobachtungsdaten und das zufällige Experiment anzeigt.](assets/randomize.png)

Wenn Sie die Wirkung von Intervention X auf das Ergebnis Y messen möchten, ist es möglich, dass die wahre Ursache für beide der verwirrende Faktor C ist. Wenn die Daten nicht durch eine zufällige Personalisierung von X erreicht werden, ist die Auswirkung schwieriger zu messen, und die Analyse wird ausdrücklich für C verantwortlich sein. Die Randomisierung bricht die Abhängigkeit von X von C ab, sodass wir die Wirkung von X auf Y messen können, ohne sich um andere Variablen kümmern zu müssen.

## Berechnete Metriken im Experimentierungsbereich verwenden

Weitere Informationen finden Sie in diesem Blogpost . [Verwendung abgeleiteter Metriken im Experimentierungsbereich](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
