---
title: Analyse „Treue“
description: Messen Sie, wie viele Benutzende Ihr Produkt weiterhin verwenden.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 3%

---

# Analyse „Treue“ {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Kundentreue"
>abstract="Messen Sie, wie viele Benutzende Ihr Produkt weiterhin verwenden."

<!-- markdownlint-enable MD034 -->

Die Analyse ![Bindung](/help/assets/icons/Retention.svg) **[!UICONTROL Bindung]** misst, wie Benutzer Ihr Produkt im Laufe der Zeit weiterhin verwenden. Dies kann Ihnen helfen, Ihre Produktmarktanpassung zu verstehen. Die Analyse zählt Benutzende auf der Grundlage von zwei wichtigen Ereignissen:

* Startereignis: Das Ereignis, mit dem Benutzer für die Aufnahme in Ihre Analyse qualifiziert werden.
* Rückkehrereignis : Ein oder mehrere Ereignisse, mit denen ein Benutzer interagieren muss, damit sie in Ihrer Analyse als wiederkehrender Benutzer gezählt werden.

Bei dieser Analyse stellt die X-Achse des Diagramms die Zeit seit dem ersten Startereignis einer Benutzerin oder eines Benutzers dar und die Y-Achse stellt den Prozentsatz der Benutzerinnen oder Benutzer dar, die mit einem oder mehreren Rückgabeereignissen interagieren. Sie können sowohl die Kundenbindung als auch die Abwanderung über verschiedene Zeiträume hinweg anzeigen. Die angezeigten Zeiträume können zudem über die Abfrageeinstellungen angepasst werden. Unterhalb des Diagramms enthält eine Tabelle aggregierte Daten mit der Option, einzelne Kohorten anzuzeigen, bei denen es sich um eine Gruppe von Personen handelt, die das Startereignis am selben Datum durchgeführt haben.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?learn=on)


## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Kohortenanalyse**: Gruppieren Sie Benutzer basierend auf von ihnen durchgeführten Aktionen wie Anmeldungen oder Käufe in Kohorten. Sie können vergleichen, wie gut diese Gruppen beibehalten, und festlegen, wie das Benutzererlebnis jeder Gruppe verbessert werden soll.
* **Produktmarktanpassung**: Messen Sie die regelmäßige Nutzung Ihres Produkts und visualisieren Sie sie als Aufbewahrungskurven. Eine höhere Kundenbindung bedeutet eine bessere Anpassung an den Produktmarkt und an der flacheren Kurve wird angezeigt, wie lange es dauert, bis die Anpassung erreicht ist. Sehen Sie sich diese Analyse auf einer allgemeinen Ebene an oder schlüsseln Sie sie nach den einzelnen Produktfunktionen auf, um tiefere Einblicke zu erhalten.
* **Abonnement-**: Wenn Ihr Produkt ein Abonnement oder ein anderes Modell für den wiederkehrenden Umsatz verwendet, können Sie den Prozentsatz der Benutzer sehen, die das Beste aus Ihrem Produkt machen. Sie können bestimmte Qualitäten und Verhaltensweisen dieser Benutzenden identifizieren.
* **Benutzerinteraktion**: Bewerten Sie, wie bestimmte Benutzertypen mit Ihrem Produkt interagieren, und vergleichen Sie nebeneinander, wie oft sie zurückkehren. Ein bestimmtes Segment mit einer geringeren Bindung als andere kann Ihnen Einblicke in die Verbesserung potenzieller unterdurchschnittlicher Erlebnisse bieten, die sie möglicherweise haben.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Startereignis]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um in Ihre Analyse aufgenommen zu werden. Benutzer, die mit dem Startereignis interagieren, werden in der Spalte „Benutzer“ der Tabelle gezählt. Dieses Ereignis dient als Nenner für die angezeigten Bindungsraten. Ein Ereignis wird unterstützt, und bei Bedarf können Eigenschaftsfilter angewendet werden. Standardmäßig sind das Start- und das Rückgabeereignis verknüpft. Das bedeutet, dass ein Benutzer das ausgewählte Ereignis nur einmal ausführen muss, um in die Kohorte aufgenommen zu werden, und anschließend erneut als wiederkehrender Benutzer gezählt werden muss. Im Menü Mehr können Sie die Verknüpfung zwischen Start- und Rückgabeereignissen aufheben, wenn sich die Rückgabeaktion von der Einschlussaktion unterscheiden soll.
* **[!UICONTROL Ereignisse zurückgeben]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, damit sie als wiederkehrende Benutzer in den Gültigkeitsbereichen gezählt werden. Sie können bis zu drei Rückgabeereignisse auswählen, um die Kundenbindung zu vergleichen.
* **[!UICONTROL Gezählt als]**: Die Zählmethode, die Sie auf die gespeicherten Benutzer anwenden möchten. Zu den Optionen zählen: 
   * **[!UICONTROL Metrik]**: Zeigt die Anzahl [!UICONTROL Benutzer] oder den [!UICONTROL Prozentsatz der Benutzer] an. Der Nenner für die einbehaltenen prozentualen Benutzer sind die eingeschlossenen Benutzer für die Kohorte und sind für alle Dauer-Buckets gleich.
   * **[!UICONTROL Wiederkehrend]**: Hiermit können Sie steuern, wie wiederkehrende Benutzende gezählt werden. Zu den Optionen zählen: 
      * **[!UICONTROL On or After]**: Wird oft als „ungebundene“ Aufbewahrung bezeichnet. Diese Option zählt einen Benutzer, wenn er am oder nach der angegebenen Dauer zurückkehrt. Zum Beispiel an Tag 7 oder jederzeit nach Tag 7. Diese Option ist hilfreich, um zu zeigen, wie Benutzende weiterhin interagieren, und erzeugt dadurch eine glattere Bindungskurve.
      * **[!UICONTROL Genau]**: Diese Option wird häufig als „begrenzte Aufbewahrung“ bezeichnet und zählt einen Benutzer, wenn er genau zur angegebenen Dauer zurückkehrt. Zum Beispiel genau an Tag 7. Diese Option ist hilfreich, um zu zeigen, wie Benutzer innerhalb bestimmter Zeitrahmen zurückkehren, und erzeugt eine Bindungskurve mit mehr Wellengang. Hinweis: Die Kohortenanalyse in Analysis Workspace verwendet eine „exakte“ Zählung als Grundlage für ihre Analyse.
   * **[!UICONTROL Each]**: Der Zeitraum, in dem jeder Duration-Bucket definiert sein soll. Zu den Optionen zählen: 
      * **[!UICONTROL Tag/Woche/Monat]**: Die verfügbaren Optionen hängen vom ausgewählten Datumsbereich ab. Diese Optionen sind identisch mit der Einstellung **[!UICONTROL Intervall]** bei Auswahl des Datumsbereichs und aktualisiert diese Einstellung automatisch.
      * **[!UICONTROL Benutzerdefinierte Klammern]**: Diese Option ist nur für die Einstellung „Bei jedem“ verfügbar. Damit können Sie Benutzer über einen größeren Zeitraum hinweg zählen, z. B. Tag 7 bis 10 anstelle von Tag 7.
   * **[!UICONTROL Dauereinstellungen]**: Ermöglicht die Steuerung der im Diagramm und in der Tabelle angezeigten Dauer-Buckets. Eine Dauer ist der Zeitraum nach dem Startereignis, in dem das Rückgabeereignis aufgetreten ist. Hinweis: Benutzende, die für einen Zeitraum-Bucket infrage kommen, basieren auf verstrichener Zeit und nicht auf Kalendertagen. Wenn sich ein(e) Benutzende(r) beispielsweise am 6. September um 23:55 Uhr für ein Ereignis qualifiziert und dann am 7. September um 12:05 Uhr für ein Rückgabeereignis qualifiziert, würden sie nicht im 1-Tages-Dauerbereich angezeigt. Es müssen volle 24 Stunden verstreichen, bevor der Benutzer sich für den 1-Tage-Dauerbereich qualifiziert. Die verfügbaren Dauer-Buckets hängen vom festgelegten Datumsbereich ab.
      * **[!UICONTROL Automatische Dauer]** definiert automatisch die Dauer-Buckets basierend auf der Länge des Datumsbereichs und der Nähe zum aktuellen Tag, an dem der Datumsbereich liegt.
      * **[!UICONTROL Benutzerdefinierte Dauer]** ermöglicht es Ihnen, die vier Dauer-Buckets anzupassen, die auf dem Diagramm und der Tabelle angezeigt werden.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment fügt der Kohortentabelle eine Zeile hinzu. Sie können bis zu drei Segmente einschließen.

### Diagrammeinstellungen

Die [!UICONTROL Beibehaltung]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Die Optionen umfassen [!UICONTROL Bar] und [!UICONTROL Line].

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie die Aufbewahrungsdaten anzeigen möchten. Gültige Optionen sind „Täglich“, „Wöchentlich“ und „Monatlich“. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Optionen für Dauer-Buckets auswirken.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.

Wenn Sie einen Datumsbereich auswählen, der nahe am aktuellen Tag liegt, werden Benutzende, die ursprünglich zu nahe am aktuellen Tag interagieren, nicht einbezogen. Diese Analyse gibt allen Nutzern immer die Chance, in alle Duration Buckets aufgenommen zu werden. Eine Nachricht unter der Kalenderauswahl enthält Informationen zum Datumsbereich, in dem Benutzende interagieren, und zum Intervall, das nur wiederkehrenden Benutzenden vorbehalten ist:

* **[!UICONTROL Analysieren von Benutzenden, die das Startereignis im [Datumsintervall“ durchgeführt haben]]**: Wenn ein(e) Benutzende(r) innerhalb dieses Datumsbereichs mit dem Ereignis interagiert, werden sie in die Analyse einbezogen. Dieser Datumsbereich garantiert allen Benutzern genügend Zeit, um sich für alle Zeiträume zu qualifizieren. Dieser Datumsbereich kann sich von Ihrer Auswahl unterscheiden, wenn er nahe am aktuellen Tag liegt.
* **[!UICONTROL Daten aus [Datumsintervall] sind reserviert, um die Analyse abzuschließen]**: Wenn ein(e) Benutzende(r) innerhalb dieses Zeitraums zum ersten Mal interagiert, werden sie **in die Analyse**. Für aktuelle Datumsbereiche hätten diese Benutzenden keine Möglichkeit, sich für alle Zeiträume zu qualifizieren. Für vergangene Datumsbereiche waren diese Benutzenden außerhalb des ausgewählten Datumsbereichs aktiv.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->