---
title: Treueanalyse
description: Messen Sie, wie viele Benutzende weiterhin Ihr Produkt nutzen.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 2%

---

# Treueanalyse

Die Analyse ![Bindung](/help/assets/icons/Retention.svg) **[!UICONTROL Bindung]** misst, wie Benutzer Ihr Produkt im Laufe der Zeit weiterhin verwenden. Dies kann Ihnen dabei helfen, die Anpassungsfähigkeit Ihres Produktmarktes zu verstehen. Die Analyse zählt Benutzer anhand von zwei wichtigen Ereignissen:

* Startereignis: Das Ereignis, mit dem Benutzer für die Aufnahme in Ihre Analyse qualifiziert werden.
* Rückkehrereignis: Ein oder mehrere Ereignisse, mit denen ein Benutzer interagieren muss, um in Ihrer Analyse als wiederkehrender Benutzer zu zählen.

In dieser Analyse stellt die x-Achse des Diagramms die Zeit seit dem ersten Startereignis eines Benutzers und die y-Achse den Prozentsatz der Benutzer dar, die mit einem oder mehreren Rückkehrereignissen interagieren. Sie können die Beibehaltung und Abwanderung über mehrere Zeiträume hinweg anzeigen und die angezeigten Zeiträume können über die Abfrageeinstellungen angepasst werden. Unter dem Diagramm bietet eine Tabelle aggregierte Daten mit der Möglichkeit, einzelne Kohorten anzuzeigen. Dabei handelt es sich um eine Gruppe von Personen, die am selben Datum das Startereignis durchgeführt haben.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?learn=on)


## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Kohortenanalyse**: Gruppieren Sie Benutzer anhand von Aktionen, die sie ausführen, z. B. Anmeldungen oder Käufe, in Kohorten. Sie können vergleichen, wie gut diese Gruppen erhalten bleiben, und bestimmen, wie das Benutzererlebnis der einzelnen Gruppen verbessert werden soll.
* **Produktmarktanpassung**: Messen Sie die regelmäßige Nutzung Ihres Produkts und visualisieren Sie es als Treuekurven. Eine höhere Kundenbindung bedeutet eine höhere Produktmarktanpassung, und wenn sich Ihre Kurve herausflacht, zeigt dies, wie lange es dauert, bis Sie Ihre Anpassung erreichen. Sehen Sie sich diese Analyse auf einer übergeordneten Ebene an oder unterteilen Sie sie nach einzelnen Produktfunktionen, um tiefere Einblicke zu erhalten.
* **Analyse des Anmeldedienstes**: Wenn Ihr Produkt ein Abonnement oder ein anderes Modell für wiederkehrenden Umsatz verwendet, können Sie den Prozentsatz der Benutzer sehen, die das meiste aus Ihrem Produkt machen. Sie können bestimmte Eigenschaften und Verhaltensweisen identifizieren, die diese Benutzer aufweisen.
* **Benutzerinteraktion**: Evaluieren Sie, wie bestimmte Typen von Benutzern mit Ihrem Produkt interagieren, und vergleichen Sie nebeneinander, wie oft sie zurückkehren. Ein bestimmtes Segment mit geringerer Bindung als andere bietet Ihnen Einblicke in die Verbesserung potenzieller untergeordneter Erlebnisse, über die es möglicherweise verfügt.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ereignis starten]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um sich für die Aufnahme in Ihre Analyse zu qualifizieren. Benutzer, die mit dem Startereignis interagieren, werden in der Spalte &quot;Benutzer&quot;der Tabelle gezählt. Dieses Ereignis dient als Nenner für angezeigte Treueraten. Ein Ereignis wird unterstützt und Eigenschaftsfilter können nach Bedarf angewendet werden. Standardmäßig sind das Start- und das Rückkehrereignis verknüpft. Das bedeutet, dass ein Benutzer das ausgewählte Ereignis einmal ausführen muss, um in die Kohorte aufgenommen zu werden, und dann erneut als wiederkehrender Benutzer gezählt werden muss. Im Menü &quot;Mehr&quot;können Sie die Verknüpfung zwischen den Start- und den Rückgabeereignissen aufheben, wenn Sie möchten, dass sich die Rückkehraktion von der Einschlussaktion unterscheidet.
* **[!UICONTROL Rückkehrereignisse]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um in den Zeitspannen-Behältern als wiederkehrende Benutzer zu zählen. Sie können bis zu drei Rückkehrereignisse auswählen, um die Beibehaltung zu vergleichen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die Sie auf die gespeicherten Benutzer anwenden möchten. Zu den Optionen zählen: 
   * **[!UICONTROL Metrik]**: Zeigt die Anzahl der [!UICONTROL Benutzer] oder den [!UICONTROL Prozentsatz der Benutzer] an, die beibehalten wurden. Der Nenner für die berücksichtigten prozentualen Benutzer ist der eingeschlossene Benutzer für die Kohorte und ist für alle Dauer-Behälter gleich.
   * **[!UICONTROL Zurückgeben]**: Ermöglicht Ihnen, zu steuern, wie wiederkehrende Benutzer gezählt werden. Zu den Optionen zählen: 
      * **[!UICONTROL An oder nach]**: Diese Option wird häufig als &quot;ungebundene&quot;Bindung bezeichnet und zählt einen Benutzer, wenn er nach oder nach der angegebenen Dauer zurückkehrt. Beispiel: an Tag 7 oder jederzeit nach Tag 7. Diese Option ist hilfreich, um zu zeigen, wie Benutzer weiter interagieren, und dadurch eine reibungslosere Aufbewahrungskurve zu erzeugen.
      * **[!UICONTROL Bei genau]**: Diese Option wird häufig als &quot;eingegrenzte&quot;Bindung bezeichnet und zählt einen Benutzer, wenn er genau zur angegebenen Dauer zurückkehrt. Zum Beispiel genau an Tag 7. Diese Option ist hilfreich, um anzuzeigen, wie Benutzer innerhalb bestimmter Zeitrahmen zurückkehren, und generiert eine Treuekurve mit mehr Abschwächung. Hinweis: Die Kohortenanalyse in Analysis Workspace verwendet die Zählung &quot;genau&quot;als Grundlage für die Analyse.
   * **[!UICONTROL Jeder]**: Der Zeitraum, für den die einzelnen Zeitspannen-Behälter erstellt werden sollen. Zu den Optionen zählen: 
      * **[!UICONTROL Tag/Woche/Monat]**: Die verfügbaren Optionen hängen vom ausgewählten Datumsbereich ab. Diese Optionen sind mit der Einstellung **[!UICONTROL Intervall]** identisch, wenn Sie den Datumsbereich auswählen und diese Einstellung automatisch aktualisieren.
      * **[!UICONTROL Benutzerdefinierte Klammern]**: Diese Option ist nur für die Einstellung &quot;Bei jedem&quot;verfügbar. Damit können Sie Benutzer über einen größeren Zeitraum hinweg zählen, z. B. Tag 7-10 anstelle von nur Tag 7.
   * **[!UICONTROL Dauer-Einstellungen]**: Ermöglicht die Steuerung der Dauer-Behälter, die in der Grafik und Tabelle angezeigt werden. Eine Dauer ist der Zeitraum nach dem Startereignis, in dem das Rückgabeereignis eingetreten ist. Hinweis: Benutzer, die sich für Dauer-Behälter qualifizieren, basieren auf der verstrichenen Zeit, nicht auf Kalendertagen. Wenn ein Benutzer beispielsweise für ein Ereignis am 6. September um 23:55 Uhr qualifiziert ist und dann am 7. September um 12:05 Uhr für ein Rückkehrereignis qualifiziert ist, werden diese nicht im Bereich für die Dauer von 1 Tagen angezeigt. Eine volle Zeitdauer von 24 Stunden muss verstreichen, bevor der Benutzer für den Zeitraum von 1 Tagen qualifiziert ist. Die verfügbaren Zeitspannen-Behälter hängen vom festgelegten Datumsbereich ab.
      * **[!UICONTROL Automatische Dauer]** definiert automatisch die Dauer der Behälter basierend auf der Datumsbereichslänge und der Nähe zum aktuellen Tag, in dem sich der Datumsbereich befindet.
      * **[!UICONTROL Benutzerdefinierte Dauern]** ermöglichen es Ihnen, die vier im Diagramm und in der Tabelle angezeigten Zeitspannen anzupassen.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment fügt der Kohortentabelle eine Zeile hinzu. Sie können bis zu drei Segmente einbeziehen.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Bindung] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören [!UICONTROL Balken] und [!UICONTROL Linie].

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Aufbewahrungsdaten anzeigen möchten. Gültige Optionen sind &quot;Täglich&quot;, &quot;Wöchentlich&quot;und &quot;Monatlich&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Optionen für den Zeitraumbehälter auswirken.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

Wenn Sie einen Datumsbereich auswählen, der nahe am aktuellen Tag liegt, werden Benutzer, die sich anfangs zu nah am aktuellen Tag engagieren, nicht einbezogen. Diese Analyse gibt allen Benutzern immer die Möglichkeit, in alle Zeitspannen-Buckets aufgenommen zu werden. Eine Meldung unter der Kalenderauswahl enthält Informationen zum Datumsbereich, in dem Benutzer interagieren, und zum Intervall, das nur für wiederkehrende Benutzer reserviert ist:

* **[!UICONTROL Analysieren von Benutzern, die das Startereignis in [Datumsintervall]]** durchgeführt haben: Wenn ein Benutzer innerhalb dieses Datumsbereichs mit dem Ereignis interagiert, werden diese in die Analyse einbezogen. Dieser Datumsbereich garantiert allen Benutzern ausreichend Zeit, um sich für alle Zeitspannen-Behälter zu qualifizieren. Dieser Datumsbereich kann sich von Ihrer Auswahl unterscheiden, wenn er nahe dem aktuellen Tag liegt.
* **[!UICONTROL Daten aus dem [Datumsintervall] sind für den Abschluss der Analyse reserviert]**: Wenn ein Benutzer innerhalb dieses Zeitraums zum ersten Mal interagiert, sind sie **nicht** in der Analyse enthalten. Für die letzten Datumsbereiche hätten diese Benutzer keine Möglichkeit, sich für alle Zeitspannen-Behälter zu qualifizieren. Für frühere Datumsbereiche waren diese Benutzer außerhalb des ausgewählten Datumsbereichs aktiv.

## Beispiel

Unten finden Sie ein Beispiel für die Analyse.

![Treue](../assets/retention.png)
