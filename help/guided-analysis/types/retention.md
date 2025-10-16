---
title: Analyse der Kundentreue
description: Messen Sie, wie viele Benutzende weiterhin Ihr Produkt nutzen.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 97%

---

# Analyse der Kundentreue {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Kundentreue"
>abstract="Messen Sie, wie viele Benutzende weiterhin Ihr Produkt nutzen."

<!-- markdownlint-enable MD034 -->

Die ![Retention](/help/assets/icons/Retention.svg) **[!UICONTROL Analyse der Kundentreue]** misst, wie Benutzende Ihr Produkt im Laufe der Zeit weiterhin verwenden. Dies kann Ihnen helfen, die Markttauglichkeit Ihres Produkts nachzuvollziehen. Die Analyse zählt Benutzende auf der Grundlage von zwei wichtigen Ereignissen:

* Startereignis: Das Ereignis, mit dem Benutzende für die Aufnahme in Ihre Analyse qualifiziert werden.
* Rückkehrereignis: Ein oder mehrere Ereignisse, mit denen eine Benutzerin bzw. ein Benutzer interagieren muss, um in Ihrer Analyse als wiederkehrende Benutzerin bzw. wiederkehrender Benutzer gezählt zu werden.

Bei dieser Analyse stellt die X-Achse des Diagramms die Zeit seit dem ersten Startereignis einer Benutzerin oder eines Benutzers dar und die Y-Achse stellt den Prozentsatz der Benutzenden dar, die mit einem oder mehreren Rückkehrereignisse interagieren. Sie können sowohl die Bindung als auch die Abwanderung über verschiedene Zeiträume hinweg anzeigen. Die angezeigten Zeiträume können zudem über die Abfrageeinstellungen angepasst werden. Eine Tabelle unterhalb des Diagramms enthält aggregierte Daten mit der Option, einzelne Kohorten anzuzeigen, bei denen es sich um eine Gruppe von Personen handelt, deren Startereignis dasselbe Datum hat.

>[!VIDEO](https://video.tv.adobe.com/v/3435787/?captions=ger&quality=12&learn=on)


## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Kohortenanalyse**: Gruppieren Sie Benutzende basierend auf von ihnen durchgeführten Aktionen wie Anmeldungen oder Käufe in Kohorten. Sie können vergleichen, wie gut diese Gruppen beibehalten werden, und festlegen, wie das Benutzererlebnis jeder Gruppe verbessert werden soll.
* **Markttauglichkeit des Produkts**: Messen Sie die regelmäßige Nutzung Ihres Produkts und visualisieren Sie sie als Bindungskurven. Eine höhere Bindung bedeutet eine höhere Markttauglichkeit des Produkts und dort, wo Ihre Kurve abflacht, wird die Dauer bis zum Erreichen der Tauglichkeit angezeigt. Sehen Sie sich diese Analyse auf einer allgemeinen Ebene an oder schlüsseln Sie sie nach den einzelnen Produktfunktionen auf, um tiefere Einblicke zu erhalten.
* **Abonnementdienstanalyse**: Wenn Ihr Produkt ein Abonnement oder ein anderes Modell für wiederkehrenden Umsatz verwendet, können Sie den Prozentsatz der Benutzenden sehen, die Ihr Produkt optimal nutzen. Sie können bestimmte Qualitäten und Verhaltensweisen dieser Benutzenden identifizieren.
* **Benutzerinteraktion**: Bewerten Sie, wie bestimmte Benutzertypen mit Ihrem Produkt interagieren, und vergleichen Sie nebeneinander, wie oft sie zurückkehren. Ein bestimmtes Segment mit einer geringeren Bindung als andere kann Ihnen Einblicke in die Verbesserung potenzieller unterdurchschnittlicher Erlebnisse bieten, die es möglicherweise aufweist.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Startereignis]**: Die Ereigniskriterien, mit denen eine Benutzerin oder ein Benutzer interagieren muss, um sich für die Aufnahme in Ihre Analyse zu qualifizieren. Benutzende, die mit dem Startereignis interagieren, werden in der Spalte „Benutzende“ der Tabelle gezählt. Dieses Ereignis dient als Nenner für die angezeigten Bindungsraten. Es wird ein Ereignis unterstützt und bei Bedarf können Eigenschaftsfilter angewendet werden. Das Start- und das Rückkehrereignis sind standardmäßig verknüpft. Das bedeutet, dass eine Benutzerin bzw. ein Benutzer das ausgewählte Ereignis nur einmal ausführen muss, um in die Kohorte aufgenommen zu werden. Sie bzw. er muss es anschließend erneut ausführen, um als wiederkehrende Benutzerin bzw. wiederkehrender Benutzer gezählt zu werden. Unter dem Menü „Mehr“ können Sie die Verknüpfung zwischen Start- und Rückkehrereignis aufheben, wenn sich die Rückkehraktion von der Einschlussaktion unterscheiden soll.
* **[!UICONTROL Rückkehrereignisse]**: Die Ereigniskriterien, mit denen eine Benutzerin bzw. ein Benutzer interagieren muss, um als wiederkehrende Benutzerin bzw. wiederkehrender Benutzer in den Dauer-Buckets gezählt zu werden. Sie können bis zu drei Rückkehrereignisse auswählen, um die Bindung übergreifend zu vergleichen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die gehaltenen Benutzenden angewendet werden soll.  Zu den Optionen zählen:
   * **[!UICONTROL Metrik]**: Zeigt die Anzahl der [!UICONTROL Benutzenden] oder den [!UICONTROL Prozentualer Anteil der Benutzenden], die gehalten wurden. Der Nenner für den prozentualen Anteil der Benutzenden, die gehalten wurden, sind die eingeschlossenen Benutzenden für die Kohorte. Sie sind für alle Dauer-Buckets gleich.
   * **[!UICONTROL Wiederkehrend]**: Hiermit können Sie steuern, wie wiederkehrende Benutzende gezählt werden. Zu den Optionen zählen:
      * **[!UICONTROL Am oder nach]**: Wird oft als „ungebundene“ Bindung bezeichnet. Diese Option zählt eine Benutzerin oder einen Benutzer, wenn sie bzw. er am oder nach der angegebenen Dauer zurückkehrt. Zum Beispiel an Tag 7 oder jederzeit nach Tag 7. Mit dieser Option lässt sich zeigen, wie Benutzende weiterhin interagieren. Sie erzeugt dadurch eine glattere Bindungskurve.
      * **[!UICONTROL Genau am]**: Wird oft als „gebundene“ Bindung bezeichnet. Diese Option zählt eine Benutzerin oder einen Benutzer, wenn sie bzw. er genau zur angegebenen Dauer zurückkehrt. Zum Beispiel genau an Tag 7. Mit dieser Option lässt sich zeigen, wie Benutzende innerhalb bestimmter Zeitrahmen zurückkehren. Sie erzeugt eine Bindungskurve mit mehr Wellenformen. Hinweis: Die Kohortenanalyse in Analysis Workspace verwendet die Zählung „Genau am“ als Grundlage für ihre Analyse.
   * **[!UICONTROL Jede]**: Der Zeitraum, in dem sich jeder Duration-Bucket befinden soll. Zu den Optionen zählen:
      * **[!UICONTROL Tag/Woche/Monat]**: Die verfügbaren Optionen hängen vom ausgewählten Datumsbereich ab. Diese Optionen sind identisch mit der Einstellung **[!UICONTROL Intervall]** bei Auswahl des Datumsbereichs und aktualisiert diese Einstellung automatisch.
      * **[!UICONTROL Benutzerdefinierter Zeitraum]**: Diese Option ist nur für die Einstellung „Bei jedem“ verfügbar. Damit können Sie Benutzende über einen größeren Zeitraum hinweg zählen, z. B. Tag 7 bis 10 anstelle von nur Tag 7.
   * **[!UICONTROL Einstellungen für Zeitrahmen]**: Ermöglicht die Steuerung der im Diagramm und in der Tabelle angezeigten Dauer-Buckets. Eine Dauer ist der Zeitraum nach dem Startereignis, in dem das Rückkehrereignis aufgetreten ist. Hinweis: Benutzende, die für Dauer-Buckets infrage kommen, basieren auf verstrichener Zeit und nicht auf Kalendertagen. Wenn sich ein(e) Benutzende(r) beispielsweise für ein Ereignis am 6. September um 11 :55 Uhr und dann für ein Rückgabeereignis am 7. September um 12 :05 Uhr qualifiziert, würden sie nicht im Zeitraum von 1 Tag angezeigt. Es müssen volle 24 Stunden verstreichen, bevor die Benutzerin oder der Benutzer sich für den Dauer-Bucket „1 Tag“ qualifiziert. Die verfügbaren Dauer-Buckets hängen vom festgelegten Datumsbereich ab.
      * **[!UICONTROL Automatische Zeitrahmen]** definiert automatisch die Dauer-Buckets basierend auf der Länge des Datumsbereichs und der Nähe zum aktuellen Tag des Datumsbereichs.
      * **[!UICONTROL Benutzerdefinierte Zeitrahmen]** ermöglicht es Ihnen, die vier Dauer-Buckets anzupassen, die auf dem Diagramm und der Tabelle angezeigt werden.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment fügt der Kohortentabelle eine Zeile hinzu. Sie können bis zu drei Segmente einschließen.

### Diagrammeinstellungen

Die [!UICONTROL Analyse der Kundentreue] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Die Optionen umfassen [!UICONTROL Balken] und [!UICONTROL Zeile].

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Kundenbindungsdaten angezeigt werden sollen. Gültige Optionen sind „Täglich“, „Wöchentlich“ und „Monatlich“. Derselbe Datumsbereich kann unterschiedliche Intervalle aufweisen, die sich auf die Optionen für Dauer-Buckets auswirken.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.

Bei Auswahl eines Datumsbereichs, der nahe am aktuellen Tag liegt, werden Benutzende, die ursprünglich zu nahe am aktuellen Tag interagieren, nicht eingeschlossen. Bei dieser Analyse besteht stets für alle Benutzenden die Chance, in alle Dauer-Buckets aufgenommen zu werden. Eine Nachricht unter der Kalenderauswahl enthält Informationen zum Datumsbereich, in dem Benutzende interagieren, und zum Intervall, das nur wiederkehrenden Benutzenden vorbehalten ist:

* **[!UICONTROL Analysieren von Benutzenden, die das Startereignis im [Datumsintervall]]** durchgeführt haben: Wenn eine Benutzerin oder ein Benutzer innerhalb dieses Datumsbereichs mit dem Ereignis interagiert, wird sie bzw. er in die Analyse einbezogen. Dieser Datumsbereich garantiert allen Benutzenden genügend Zeit, um sich für alle Dauer-Buckets zu qualifizieren. Dieser Datumsbereich kann sich von Ihrer Auswahl unterscheiden, wenn er nahe am aktuellen Tag liegt.
* **[!UICONTROL Daten aus dem [Datumsintervall] sind für das Abschließen der Analyse reserviert]**: Wenn eine Benutzerin oder ein Benutzer zum ersten Mal innerhalb dieses Zeitraums interagiert, wird sie bzw. er **nicht** in die Analyse einbezogen. Für aktuelle Datumsbereiche hätten diese Benutzenden keine Möglichkeit, sich für alle Dauer-Buckets zu qualifizieren. Für vergangene Datumsbereiche waren diese Benutzenden außerhalb des ausgewählten Datumsbereichs aktiv.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->