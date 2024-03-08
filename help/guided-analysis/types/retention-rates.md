---
title: Bindungsrate
description: Messen Sie, wie viele Benutzer Ihr Produkt weiterhin verwenden.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 77fbd2a9ad44affc62aa5e98728d3353d78d8c3c
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 2%

---

# Bindungsrate

Die **[!UICONTROL Treuerate]** Die Ansicht zeigt Benutzern, die das Nutzungsverhalten in Ihrem Produkt im Laufe der Zeit wiederholen, was Ihnen dabei hilft, Ihre Produktmarktanpassung zu verstehen. In dieser Ansicht stellt die horizontale Achse die Anzahl der Tage seit der anfänglichen Interaktion eines Benutzers dar, und die vertikale Achse stellt den Prozentsatz der Benutzer dar, die sich erneut engagieren.

Diese Analyse zählt Benutzer anhand von zwei wichtigen Ereignissen:

* Startereignis: Das erste Mal, dass ein Benutzer innerhalb des Datumsbereichs mit dem Ereignis interagiert
* Rückkehrereignis: Das letzte Mal, dass ein Benutzer innerhalb des analysierten Datumsbereichs mit dem Ereignis interagiert hat

Der Behälter für die Dauer &quot;Tag 0&quot;stellt die Anfangszeit dar, zu der ein Benutzer mit dem Ereignis interagiert hat, und entspricht immer genau 100 %. Dieser Behälter ist der Nenner, mit dem der Prozentsatz der zurückbehaltenen Benutzer berechnet wird.

Die nachfolgenden Dauer-Behälter zählen die Anzahl der Benutzer, die nach dieser Dauer oder nach dieser Zeit zurückkehrten. Diese Anzahl ist der Zähler, der zur Berechnung des Prozentsatzes der einbehaltenen Benutzer verwendet wird.

* Wenn ein Benutzer innerhalb des gewünschten Datumsbereichs (die anfängliche Interaktion) nur einmal mit dem Ereignis interagiert, werden diese nur im Bereich &quot;Tag 0&quot;für die Dauer angezeigt.
* Wenn ein Benutzer mehrere Tage mit dem Ereignis interagiert, nachdem er sich erstmals für die Aufnahme in die Analyse qualifiziert hat, werden diese im Behälter für die neueste qualifizierende Dauer und in allen dazugehörigen Zeitspannen-Behältern angezeigt. Diese Art der Berechnung wird manchmal als &quot;unbegrenzter Beibehalt&quot;bezeichnet.

![Screenshot der Treueraten](../assets/retention-rates.png){style="border:1px solid gray"}

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Kohortenanalyse**: Gruppieren Sie Benutzer basierend auf von ihnen durchgeführten Aktionen (wie z. B. Anmeldungen oder Käufe) in Kohorten. Sie können vergleichen, wie gut diese Gruppen erhalten bleiben, und bestimmen, wie das Benutzererlebnis der einzelnen Gruppen verbessert werden soll.
* **Produktmarktanpassung**: Messen Sie die regelmäßige Nutzung Ihres Produkts und visualisieren Sie es als Treuekurven. Eine höhere Kundenbindung bedeutet eine höhere Produktmarktanpassung, und wenn sich Ihre Kurve herausflacht, zeigt dies, wie lange es dauert, bis Sie Ihre Anpassung erreichen. Sehen Sie sich diese Analyse auf einer übergeordneten Ebene an oder unterteilen Sie sie nach einzelnen Produktfunktionen, um tiefere Einblicke zu erhalten.
* **Abonnement-Dienstanalyse**: Wenn Ihr Produkt ein Abonnement oder ein anderes Modell für den wiederkehrenden Umsatz verwendet, können Sie den Prozentsatz der Benutzer sehen, die Ihr Produkt optimal nutzen. Sie können bestimmte Eigenschaften und Verhaltensweisen identifizieren, die diese Benutzer aufweisen.
* **Benutzerinteraktion**: Evaluieren Sie, wie bestimmte Typen von Benutzern mit Ihrem Produkt interagieren, und vergleichen Sie, wie oft sie zurückkehren. Ein bestimmtes Segment mit geringerer Bindung als andere bietet Ihnen Einblicke in die Verbesserung potenzieller untergeordneter Erlebnisse, über die es möglicherweise verfügt.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Start- und Rückkehrereignis]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um sich für die Aufnahme und Beibehaltung in Ihre Analyse zu qualifizieren. Ein Ereignis wird unterstützt, Sie können jedoch Eigenschaftenfilter einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die Sie auf einbehaltene Benutzer anwenden möchten. Optionen umfassen [!UICONTROL Benutzer beibehalten] und [!UICONTROL Prozentsatz der einbehaltenen Benutzer].
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment fügt der Kohortentabelle eine Zeile hinzu. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Treuerate] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Balken] und [!UICONTROL Linie]. Die Linienvisualisierung zeigt Tag 0 visuell im Diagramm an.

## Einstellungen für Zeitrahmen

Damit können Sie steuern, wie die Analyse Benutzer nach der Anzahl der verstrichenen Tage anzeigt.

* **[!UICONTROL Automatische Dauer]**: Legen Sie automatisch Dauern basierend auf der Länge des Datumsbereichs und der Nähe zum aktuellen Tag fest, in dem sich der Datumsbereich befindet. Die Zeiträume werden für die häufigsten Anwendungsfälle kuratiert.
* **[!UICONTROL Benutzerdefinierte Dauer]**: Legen Sie die gewünschten verstrichenen Intervalle manuell fest. Sie können vier Zeiträume festlegen.

Die verfügbaren Zeitspannen-Behälter hängen vom festgelegten Datumsbereich ab.

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Aufbewahrungsdaten anzeigen möchten. Gültige Optionen sind &quot;Täglich&quot;, &quot;Wöchentlich&quot;und &quot;Monatlich&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Optionen für den Zeitraumbehälter auswirken.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

Wenn Sie einen Datumsbereich auswählen, der nahe am aktuellen Tag liegt, werden Benutzer, die sich anfangs zu nah am aktuellen Tag engagieren, nicht einbezogen. Diese Analyse gibt allen Benutzern immer die Möglichkeit, in alle Zeitspannen-Buckets aufgenommen zu werden. Eine Meldung unter der Kalenderauswahl enthält Informationen zum Datumsbereich, in dem Benutzer interagieren, und zum Intervall, das nur für wiederkehrende Benutzer reserviert ist:

* **Analysieren von Benutzern, die das Startereignis in [Datumsbereich]**: Wenn ein Benutzer innerhalb dieses Datumsbereichs mit dem Ereignis interagiert, werden diese in die Analyse einbezogen. Dieser Datumsbereich garantiert allen Benutzern ausreichend Zeit, um sich für alle Zeitspannen-Behälter zu qualifizieren. Dieser Datumsbereich kann sich von Ihrer Auswahl unterscheiden, wenn er nahe dem aktuellen Tag liegt.
* **Daten aus [Datumsbereich] ist für den Abschluss der Analyse reserviert.**: Wenn ein Benutzer innerhalb dieses Zeitraums zum ersten Mal eine Interaktion durchführt, erfolgt dies **not** in die Analyse einbezogen werden. Für die letzten Datumsbereiche hätten diese Benutzer keine Möglichkeit, sich für alle Zeitspannen-Behälter zu qualifizieren. Für frühere Datumsbereiche waren diese Benutzer außerhalb des ausgewählten Datumsbereichs aktiv.

## Kohortentabelle

Die Tabelle unter dem Diagramm bietet eine aggregierte Ansicht (ähnlich den Diagrammdaten) und eine vollständige Kohortentabelle. Die vollständige Kohortentabelle enthält Details zu den einzelnen Datumsintervallen und zur Interaktion der Benutzer.
