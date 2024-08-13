---
title: Anwendungsfälle für Datenansichten in Customer Journey Analytics
description: Mehrere Anwendungsfälle, die die Flexibilität und Leistungsfähigkeit von Datenansichten in Customer Journey Analytics zeigen
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 62779154e889158c62e4713a951fb3633c16d5e1
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 35%

---

# Anwendungsfälle von Datenansichten

Diese Anwendungsbeispiele veranschaulichen die Flexibilität und Leistungsfähigkeit von Datenansichten im Customer Journey Analytics.

## Bindungsdimensionsmetriken verwenden

Weitere Informationen finden Sie im Anwendungsbeispiel [Bindungsdimensionsmetriken verwenden](binding-dimensions-metrics.md) .

## Zusammenfassungsdaten verwenden

Weitere Informationen finden Sie im Anwendungsbeispiel [Zusammenfassungsdaten verwenden](summary-data.md) .

## Erstellen einer Metrik aus einem Zeichenfolgenschemafeld {#string}

Beim Erstellen einer Datenansicht können Sie beispielsweise eine Metrik vom Typ [!UICONTROL Bestellungen] aus einem Schemafeld vom Typ [!UICONTROL Seitentitel] erstellen, das eine Zeichenfolge ist.



1. Ziehen Sie auf der Registerkarte **[!UICONTROL Komponenten]** den **[!UICONTROL Seitentitel]** in den Abschnitt **[!UICONTROL Metriken]** unter [!UICONTROL Einbezogene Komponenten].
1. Markieren Sie die Metrik, die Sie gerade eingezogen haben, und benennen Sie sie in den **[!UICONTROL Komponenteneinstellungen]** in `Orders` um.
1. Öffnen Sie den Abschnitt **[!UICONTROL Werte einschließen/ausschließen]** und geben Sie Folgendes an:
   1. Aktivieren Sie **[!UICONTROL Setzen Sie die Werte zum Ausschließen von Elementen ein]**.
   1. Wählen Sie **[!UICONTROL Wenn alle Kriterien erfüllt sind]** aus **[!UICONTROL Übereinstimmung]**.
   1. Geben Sie `confirmation` an. Dieser Text für &quot;page_title&quot;zeigt an, dass diese Seite mit der Platzierung einer Bestellung verbunden ist. Nachdem Sie alle Seitentitel überprüft haben, bei denen diese Kriterien erfüllt sind, wird für jede Instanz ein `1` gezählt. Das Ergebnis ist eine neue Metrik (keine berechnete Metrik). Eine Metrik mit eingeschlossenen/ausgeschlossenen Werten kann überall dort verwendet werden, wo auch jede andere Metrik eingesetzt werden kann. Sie funktioniert mit Attribution IQ, Filtern und überall sonst, wo Sie Standardmetriken verwenden können.

   ![Dimension zu Metrik](../assets/string-to-metric.gif){width=100%}
1. Sie können darüber hinaus ein Zuordnungsmodell für diese Metrik angeben, beispielsweise [!UICONTROL Letztkontakt] mit einem [!UICONTROL Lookback-Fenster] von [!UICONTROL Sitzung].
Sie können auch eine weitere [!UICONTROL Bestellungen] -Metrik aus demselben Feld erstellen und ein anderes Attributionsmodell angeben. Beispiel: [!UICONTROL Erstkontakt] und ein anderes [!UICONTROL Lookback-Fenster], z. B. [!UICONTROL 30 Tage].

Ein weiteres Beispiel wäre die Verwendung der Personen-ID, einer Dimension, als Metrik zur Bestimmung der Anzahl der Personen-IDs, die Ihr Unternehmen hat.

## Verwenden von Ganzzahlen als Dimensionen {#integers}

Zuvor wurden Ganzzahlen in Customer Journey Analytics automatisch als Metriken behandelt. Jetzt können numerische Zeichen (einschließlich benutzerdefinierter Ereignisse aus Adobe Analytics) als Dimensionen behandelt werden. Siehe folgendes Beispiel:



1. Ziehen Sie die Ganzzahl **[!UICONTROL Dauer]** in den Abschnitt **[!UICONTROL Dimensionen]** unter [!UICONTROL Einbezogene Komponenten]:
1. Sie können jetzt **[!UICONTROL Wertgruppierung]** hinzufügen, um diese Dimension in Berichten in zusammengefasster Form darzustellen. Ohne Zusammenfassung würde jede Instanz dieser Dimension als Zeilenelement in der Workspace-Berichterstellung angezeigt.
   ![Integer zu Dimension](../assets/integer-to-dimension.gif){width=100%}


## Numerische Dimensionen als Metriken in Flussdiagrammen verwenden {#numeric}

Sie können eine numerische Dimension verwenden, um Metriken in Ihre [!UICONTROL  Fluss] -Visualisierung zu übertragen.

1. Ziehen Sie auf der Registerkarte [Komponenten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/create-dataview) der Datenansichten das Schemafeld [!UICONTROL Marketing-Kanäle] in den Bereich [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
2. In Arbeitsbereich-Berichten zeigt dieser Fluss [!UICONTROL Marketing-Kanäle], die in [!UICONTROL Bestellungen] fließen:

![Marketingkanal-Fluss von E-Mails zu Ausstiegen/Bestellungen.](../assets/flow.png)

## Unterereignisfilterung durchführen {#sub-event}

Diese Funktion gilt speziell für Array-basierte Felder. Mit der Ein-/Ausschlussfunktion können Sie auf der Ebene der Unterereignisse filtern, während im Filter-Builder erstellte Filter (Segmente) nur die Filterung auf der Ereignisebene ermöglichen. Sie können also die Filterung von Unterereignissen durchführen, indem Sie Einschließen/Ausschließen in Datenansichten verwenden und dann auf der Ereignisebene in einem Filter auf diese neue Metrik/Dimension verweisen.

Verwenden Sie beispielsweise die Ein-/Ausschlussfunktion in Datenansichten, um sich nur auf Produkte zu konzentrieren, die einen Umsatz von mehr als 50 US-Dollar generierten. Wenn Sie also eine Bestellung haben, die einen Produktkauf im Wert von 50 US-Dollar und einen Produktkauf im Wert von 25 US-Dollar enthält, wird durch die Einschluss-/Ausschlussfunktion der 25-Dollar-Produktkauf entfernt, nicht die gesamte Bestellung.

1. Ziehen Sie auf der Registerkarte [Komponenten](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/create-dataview) der Datenansichten das Schema **[!UICONTROL Umsatz]** in den Bereich **[!UICONTROL Metriken]** unter [!UICONTROL Eingeschlossene Komponenten].
1. Wählen Sie die Metrik aus und konfigurieren Sie rechts Folgendes:
a. Wählen Sie unter **[!UICONTROL Format]** die Option **[!UICONTROL Währung]** aus.
b. Wählen Sie unter **[!UICONTROL Währung]** **[!UICONTROL USD]** aus.
c. Aktivieren Sie unter **[!UICONTROL Werte einschließen/ausschließen]** das Kontrollkästchen neben **[!UICONTROL Ein-/Ausschlusswerte festlegen]**.
d. Wählen Sie unter **[!UICONTROL Match]** die Option **[!UICONTROL Wenn alle Kriterien erfüllt sind]**.
e. Wählen Sie unter **[!UICONTROL Kriterien]** die Option **[!UICONTROL ist größer oder gleich]** aus.
f. Geben Sie `50` als Wert an.

Mit diesen neuen Einstellungen können Sie nur Umsätze mit höheren Werten anzeigen und alles unter 50 Dollar herausfiltern.

## Verwenden Sie die Einstellung [!UICONTROL Keine Werteoptionen] . {#no-value}

Möglicherweise hat Ihr Unternehmen Zeit damit verbracht, Ihre Benutzer für Dimensionen in Berichten mit &quot;Nicht angegeben&quot;zu vertraut zu machen. Der Standardwert für Dimensionen in Datenansichten ist &quot;Kein Wert&quot;. Sie können jedoch pro Dimension angeben, wie Kein Wert in Berichten aufgeführt werden soll. Siehe No value options for a dimension component.

![Keine Wertoptionen](../assets/no-value-options.gif){width=100%}


## Mehrere Metriken mit unterschiedlichen Attributionseinstellungen erstellen {#attribution}

Verwenden Sie die Funktion **[!UICONTROL Duplizieren]** oben rechts, um eine Reihe von Gesamtumsatzmetriken mit verschiedenen Attributionseinstellungen wie **[!UICONTROL Erstkontakt]**, **[!UICONTROL Letztkontakt]** und **[!UICONTROL Algorithmus]** zu erstellen.

Vergessen Sie nicht, jede Metrik umzubenennen, um die Unterschiede widerzuspiegeln, z. B. `Total Revenue (Algorithmic)`

![Metrik für verschiedene Attributionseinstellungen duplizieren](../assets/duplicate-metric-for-attribution.gif){width=100%}

Weitere Informationen zu anderen Datenansicht-Einstellungen finden Sie unter [Erstellen von Datenansichten](/help/data-views/create-dataview.md).
Eine konzeptionelle Übersicht über die Datenansichten finden Sie unter [Übersicht über Datenansichten](/help/data-views/data-views.md).

## Neue Sitzungs- und Sitzungsberichte {#new-repeat}

Sie können bestimmen, ob eine Sitzung tatsächlich die erste Sitzung für einen Benutzer oder eine Rückkehrsitzung ist. Basierend auf dem Berichtsfenster, das Sie für diese Datenansicht definiert haben, und einem 13-monatigen Lookback-Fenster. Diese Reporting-Funktion ermöglicht Ihnen beispielsweise, Folgendes zu bestimmen:

* Welcher Prozentsatz von Bestellungen stammt aus neuen oder wiederkehrenden Sitzungen?

* Sprechen Sie auf einem bestimmten Marketing-Kanal oder bei einer bestimmten Kampagne Erstbenutzende an oder Personen, die wiedergekommen sind? Wie beeinflusst diese Auswahl die Konversionsraten?

Eine Dimension und zwei Metriken ermöglichen diese Berichte:

* [Sitzungstyp](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference) - Diese Dimension hat zwei Werte: [!UICONTROL Neu] und [!UICONTROL Zurückgeben]. Das Zeilenelement [!UICONTROL Neu] enthält das gesamte Verhalten (d. h. die Metriken für diese Dimension) einer Sitzung, bei der festgestellt wurde, dass es sich um eine erste Sitzung einer Person handelt. Alles andere ist im Zeileneintrag [!UICONTROL Wiederkehrend] enthalten (vorausgesetzt, dass alles zu einer Sitzung gehört). Wenn Metriken nicht Teil einer Sitzung sind, fallen sie in den Bereich „Nicht zutreffend“ für diese Dimension.

* [Erstmalige Sitzungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference). Die Metrik Erstmalige Sitzungen wird als die definierte erste Sitzung einer Person im Berichtsfenster definiert.

* [Rückkehrsitzungen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference) Die Metrik Rückkehrsitzungen ist die Anzahl der Sitzungen, die nicht die erste Sitzung einer Person waren.—>

So greifen Sie auf die Komponenten zu:

1. Wechseln Sie zum Datenansichts-Editor.
1. Wählen Sie die Registerkarte **[!UICONTROL Komponenten]** und dann in der linken Leiste die Option **[!UICONTROL Standardkomponenten]** aus.
1. Ziehen Sie die Komponenten **[!UICONTROL Sitzungstyp]**, **[!UICONTROL Erstmalige Sitzungen]** und **[!UICONTROL Wiederkehrende Sitzungen]** in Ihre Datenansicht.

Neue Sitzungen werden fast immer genau gemeldet. Die einzigen Ausnahmen sind:

* Wenn eine erste Sitzung vor dem 13-monatigen Lookback-Fenster stattgefunden hat. <br/>Diese Sitzung wird ignoriert.

* Wenn eine Sitzung sowohl das Lookback-Fenster als auch den Berichtszeitraum umfasst. <br/>Sie führen beispielsweise einen Bericht vom 1. Juni bis zum 15. Juni 2022 aus. Das Lookback-Fenster erstreckt sich vom 1. Mai 2021 bis zum 31. Mai 2022. Wenn eine Sitzung am 30. Mai 2022 beginnt und am 1. Juni 2022 endet, wird die Sitzung in das Lookback-Fenster aufgenommen. Und alle Sitzungen im Berichtsfenster werden als wiederkehrende Sitzungen gezählt.

## Verwenden der Datums- und Datumszeitfunktionen {#date}

Schemas in Adobe Experience Platform enthalten die Felder [!UICONTROL Datum] und [!UICONTROL Datum-Uhrzeit]. Customer Journey Analytics-Datenansichten unterstützen diese Felder jetzt. Wenn Sie diese Felder als Dimension in eine Datenansicht ziehen, können Sie ihr [Format](/help/data-views/component-settings/format.md) angeben. Diese Formateinstellung legt fest, wie die Felder im Berichtswesen angezeigt werden. Beispiel:

* Wenn Sie für das Datumsformat **[!UICONTROL Tag]** mit dem Format **[!UICONTROL Tag, Monat, Jahr]**, könnte eine Beispielausgabe in Berichten wie folgt aussehen: 23. August 2022.

* Wenn Sie für das Datum-Zeit-Format **[!UICONTROL Tagesminute]** mit dem Format **[!UICONTROL Stunde:Minute]** wählen, könnte Ihre Ausgabe wie folgt aussehen: 20:20.

Datumswerte nach dem 1. Januar 1900 (mit Ausnahme des 1. Januar 1970) und Datums-/Uhrzeitwerte nach dem 1. Januar 2000 00:00:00 werden unterstützt.

### Anwendungsfälle mit Datum und Datum/Uhrzeit

* Datum: Ein Reiseunternehmen erfasst das Abreisedatum für Reisen als Feld in seinen Daten. Das Unternehmen möchte einen Bericht haben, der den [!UICONTROL Wochentag] für alle erfassten Abreisedaten vergleicht, um zu verstehen, welcher am beliebtesten ist. Und das Unternehmen möchte dasselbe für den [!UICONTROL Monat des Jahres] tun.

* Datum/Uhrzeit: Ein Einzelhandelsunternehmen erfasst die Zeit für jeden seiner In-Store-Point-of-Sale-Käufe. Über einen bestimmten Monat hinweg möchte das Unternehmen die geschäftigsten Einkaufsphasen bis [!UICONTROL Stunde des Tages] verstehen.

>[!MORELIKETHIS]
>
>[Datum und Datum/Uhrzeit in der Einstellung der Komponente &quot;Format&quot;](/help/data-views/component-settings/format.md)
>

