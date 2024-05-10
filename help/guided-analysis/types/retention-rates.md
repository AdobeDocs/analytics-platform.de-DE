---
title: Bindungsrate
description: Messen Sie, wie viele Benutzer Ihr Produkt weiterhin verwenden.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 2%

---

# Bindungsrate

Die **[!UICONTROL Treuerate]** Die Ansicht zeigt Benutzern, die das Nutzungsverhalten in Ihrem Produkt im Laufe der Zeit wiederholen, was Ihnen dabei helfen kann, die Anpassungsfähigkeit Ihres Produktmarkts zu verstehen. In dieser Ansicht stellt die horizontale Achse die Anzahl der Tage seit der anfänglichen Interaktion eines Benutzers dar, und die vertikale Achse stellt den Prozentsatz der Benutzer dar, die sich erneut engagieren.

Diese Analyse zählt Benutzer anhand von zwei wichtigen Ereignissen:

* Startereignis: Das erste Mal, dass ein Benutzer innerhalb des Datumsbereichs mit dem Ereignis interagiert
* Rückkehrereignis: Das letzte Mal, dass ein Benutzer innerhalb des analysierten Datumsbereichs mit dem Ereignis interagiert hat

Der Behälter für die Dauer &quot;Tag 0&quot;stellt die Anfangszeit dar, zu der ein Benutzer mit dem Ereignis interagiert hat, und entspricht immer genau 100 %. Dieser Behälter ist der Nenner, mit dem der Prozentsatz der zurückbehaltenen Benutzer berechnet wird.

Die nachfolgenden Dauer-Behälter zählen die Anzahl der Benutzer, die nach dieser Dauer oder nach dieser Zeit zurückkehrten. Diese Anzahl ist der Zähler, der zur Berechnung des Prozentsatzes der einbehaltenen Benutzer verwendet wird.

* Wenn ein Benutzer innerhalb des gewünschten Datumsbereichs (die anfängliche Interaktion) nur einmal mit dem Ereignis interagiert, werden diese nur im Bereich &quot;Tag 0&quot;für die Dauer angezeigt.
* Wenn ein Benutzer mehrere Tage mit dem Ereignis interagiert, nachdem er sich erstmals für die Aufnahme in die Analyse qualifiziert hat, werden diese im Behälter für die neueste qualifizierende Dauer und in allen dazugehörigen Zeitspannen-Behältern angezeigt. Diese Art der Berechnung wird manchmal als &quot;unbegrenzte Beibehaltung&quot;bezeichnet. Sie können diese Berechnungseinstellung in der Abfrageleiste ändern.

Benutzer, die sich für die Dauer-Behälter qualifizieren, basieren auf der verstrichenen Zeit, nicht auf dem Kalendertag. Wenn ein Benutzer beispielsweise für ein Ereignis am 6. September um 23:55 Uhr qualifiziert ist und dann am 7. September um 12:05 Uhr für ein Rückkehrereignis qualifiziert ist, werden diese nicht im Bereich für die Dauer von 1 Tagen angezeigt. Eine volle Zeitdauer von 24 Stunden muss verstreichen, bevor der Benutzer für den Zeitraum von 1 Tagen qualifiziert ist.

![Screenshot der Treueraten](../assets/retention-rates.png){style="border:1px solid gray"}

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Kohortenanalyse**: Gruppieren Sie Benutzer basierend auf von ihnen durchgeführten Aktionen (wie z. B. Anmeldungen oder Käufe) in Kohorten. Sie können vergleichen, wie gut diese Gruppen erhalten bleiben, und bestimmen, wie das Benutzererlebnis der einzelnen Gruppen verbessert werden soll.
* **Produktmarktanpassung**: Messen Sie die regelmäßige Nutzung Ihres Produkts und visualisieren Sie es als Treuekurven. Eine höhere Kundenbindung bedeutet eine höhere Produktmarktanpassung, und wenn sich Ihre Kurve herausflacht, zeigt dies, wie lange es dauert, bis Sie Ihre Anpassung erreichen. Sehen Sie sich diese Analyse auf einer übergeordneten Ebene an oder unterteilen Sie sie nach einzelnen Produktfunktionen, um tiefere Einblicke zu erhalten.
* **Abonnement-Dienstanalyse**: Wenn Ihr Produkt ein Abonnement oder ein anderes Modell für den wiederkehrenden Umsatz verwendet, können Sie den Prozentsatz der Benutzer sehen, die Ihr Produkt optimal nutzen. Sie können bestimmte Eigenschaften und Verhaltensweisen identifizieren, die diese Benutzer aufweisen.
* **Benutzerinteraktion**: Evaluieren Sie, wie bestimmte Typen von Benutzern mit Ihrem Produkt interagieren, und vergleichen Sie, wie oft sie zurückkehren. Ein bestimmtes Segment mit geringerer Bindung als andere bietet Ihnen Einblicke in die Verbesserung potenzieller untergeordneter Erlebnisse, über die es möglicherweise verfügt.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Startereignis]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um sich für die Aufnahme in Ihre Analyse zu qualifizieren. Benutzer, die mit dem Startereignis interagieren, sind im anfänglichen Benutzerbehälter enthalten, der eine Gesamtanzahl von 100 % aufweist. Ein Ereignis wird unterstützt, Sie können jedoch Eigenschaftenfilter einbeziehen. Sie können die Start- und Rückkehrereignisse über das Menü mit drei Punkten verknüpfen. Die Verknüpfung von Start- und Rückkehrereignissen bedeutet, dass die Kriterien, die im Bereich &quot;Anfangsdauer&quot;und in den nachfolgenden Zeitspannen angezeigt werden, identisch sind.
* **[!UICONTROL Rückkehrereignisse]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um sich für die Aufnahme in aufeinander folgende Zeitspannen-Behälter zu qualifizieren. Sie können bis zu drei Rückkehrereignisse auswählen. Jedes Rückgabeereignis generiert eine parallele Analyse mit den anderen enthaltenen Rückgabeereignissen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die Sie auf einbehaltene Benutzer anwenden möchten. Zu den Optionen zählen: 
   * **[!UICONTROL Metrik]**: Zählt die Anzahl der [!UICONTROL Benutzer beibehalten] oder [!UICONTROL Prozentsatz der einbehaltenen Benutzer].
   * **[!UICONTROL Returning]**: Standardmäßig enthält diese Analyse Benutzer im zurückgegebenen Behälter und alle vorangehenden Behälter. Ändern Sie diese Einstellung in **[!UICONTROL Genau]** , um Benutzer nur in den exakten Behälter einzuschließen, für den sie sich qualifizieren.
   * **[!UICONTROL Jeder]**: Der Zeitraum, für den die einzelnen Zeiträume im Behälter &quot;Dauer&quot;festgelegt werden sollen. Diese Einstellung entspricht der **[!UICONTROL Intervall]** bei der Auswahl des Datumsbereichs fest.
   * **[!UICONTROL Einstellungen für die Dauer]**: Hiermit können Sie steuern, wie die Analyse Benutzer nach der Anzahl der verstrichenen Tage anzeigt. Die verfügbaren Zeitspannen-Behälter hängen vom festgelegten Datumsbereich ab. **[!UICONTROL Automatische Dauer]** legt die Dauer-Buckets automatisch auf Grundlage der Datumsbereichslänge und der Nähe zum aktuellen Tag fest, an dem sich der Datumsbereich befindet. **[!UICONTROL Benutzerdefinierte Dauer]** ermöglichen es Ihnen, in gewünschten Intervallen manuell vier Dauerbehälter festzulegen.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment fügt der Kohortentabelle eine Zeile hinzu. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Treuerate] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Balken] und [!UICONTROL Linie]. Die Linienvisualisierung zeigt Tag 0 visuell im Diagramm an.

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Aufbewahrungsdaten anzeigen möchten. Gültige Optionen sind &quot;Täglich&quot;, &quot;Wöchentlich&quot;und &quot;Monatlich&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Optionen für den Zeitraumbehälter auswirken.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

Wenn Sie einen Datumsbereich auswählen, der nahe am aktuellen Tag liegt, werden Benutzer, die sich anfangs zu nah am aktuellen Tag engagieren, nicht einbezogen. Diese Analyse gibt allen Benutzern immer die Möglichkeit, in alle Zeitspannen-Buckets aufgenommen zu werden. Eine Meldung unter der Kalenderauswahl enthält Informationen zum Datumsbereich, in dem Benutzer interagieren, und zum Intervall, das nur für wiederkehrende Benutzer reserviert ist:

* **[!UICONTROL Analysieren von Benutzern, die das Startereignis in [Datumsbereich]]**: Wenn ein Benutzer innerhalb dieses Datumsbereichs mit dem Ereignis interagiert, werden diese in die Analyse einbezogen. Dieser Datumsbereich garantiert allen Benutzern ausreichend Zeit, um sich für alle Zeitspannen-Behälter zu qualifizieren. Dieser Datumsbereich kann sich von Ihrer Auswahl unterscheiden, wenn er nahe dem aktuellen Tag liegt.
* **[!UICONTROL Daten aus [Datumsbereich] ist für den Abschluss der Analyse reserviert.]**: Wenn ein Benutzer innerhalb dieses Zeitraums zum ersten Mal eine Interaktion durchführt, erfolgt dies **not** in die Analyse einbezogen werden. Für die letzten Datumsbereiche hätten diese Benutzer keine Möglichkeit, sich für alle Zeitspannen-Behälter zu qualifizieren. Für frühere Datumsbereiche waren diese Benutzer außerhalb des ausgewählten Datumsbereichs aktiv.

## Kohortentabelle

Die Tabelle unter dem Diagramm bietet eine aggregierte Ansicht (ähnlich den Diagrammdaten) und eine vollständige Kohortentabelle. Die vollständige Kohortentabelle enthält Details zu den einzelnen Datumsintervallen und zur Interaktion der Benutzer.
