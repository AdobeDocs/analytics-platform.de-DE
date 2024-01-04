---
title: Anwendungsfälle für Datenansichten in Customer Journey Analytics
description: Mehrere Anwendungsfälle, die die Flexibilität und Leistungsfähigkeit von Datenansichten in Customer Journey Analytics zeigen
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1360'
ht-degree: 90%

---

# Anwendungsfälle von Datenansichten

Diese Anwendungsfälle zeigen die Flexibilität und Leistungsfähigkeit von Datenansichten in Customer Journey Analytics.

## 1. Erstellen Sie eine Metrik aus einem Zeichenfolgen-Schemafeld {#string}

Wenn Sie beispielsweise eine Datenansicht erstellen, können Sie eine Metrik [!UICONTROL Bestellungen] aus einem Schemafeld [!UICONTROL pageTitle] erstellen, das eine Zeichenfolge ist. Hierzu sind folgende Schritte notwendig:

1. Ziehen Sie auf der Registerkarte „Komponenten“ den Abschnitt [!UICONTROL pageTitle] in den Abschnitt [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
   ![Schemafelder mit dem Pfeil, der in der Liste &quot;Komponentenname&quot;auf &quot;pageTitle&quot;verweist.](../assets/use-case1a.png)
1. Markieren Sie nun die Metrik, die Sie gerade in den Bereich gezogen haben, und benennen Sie sie unter [!UICONTROL Komponenteneinstellungen] auf der rechten Seite um:
   ![Schemafelder, die Bestellungen unter den Komponenteneinstellungen hervorheben.](../assets/orders.png)
1. Öffnen Sie das Dialogfeld [!UICONTROL Werte einschließen/ausschließen] auf der rechten Seite und geben Sie Folgendes an:
   ![Ein-/Ausschließen von Werten mit Festlegen von Ein-/Ausschlusswerten und Auswahl der Option Groß-/Kleinschreibung beachten.](../assets/orders2.png)

   Der Zusatz „Bestätigung“ gibt an, dass es sich um eine Bestellung handelt. Nach Überprüfung aller Seitentitel, bei denen diese Kriterien erfüllt sind, wird für jede Instanz „1“ gezählt. Das Ergebnis ist eine neue Metrik (keine berechnete Metrik). Eine Metrik mit eingeschlossenen/ausgeschlossenen Werten kann überall dort verwendet werden, wo auch jede andere Metrik eingesetzt werden kann. Sie funktioniert mit Attribution IQ, Filtern und überall sonst, wo Sie Standardmetriken verwenden können.
1. Sie können darüber hinaus ein Zuordnungsmodell für diese Metrik angeben, beispielsweise [!UICONTROL Letztkontakt] mit einem [!UICONTROL Lookback-Fenster] von [!UICONTROL Sitzung].
Sie können auch eine weitere Metrik [!UICONTROL Bestellungen] aus demselben Feld erstellen und dafür ein anderes Zuordnungsmodell festlegen, beispielsweise [!UICONTROL Erstkontakt], und ein anderes [!UICONTROL Lookback-Fenster], beispielsweise [!UICONTROL 30 Tage].

Ein weiteres Beispiel wäre die Verwendung der Besucher-ID, also einer Dimension, als Metrik zur Bestimmung der Anzahl der Besucher-IDs in Ihrem Unternehmen.

## 2. Verwenden Sie Ganzzahlen als Dimensionen {#integers}

Zuvor wurden Ganzzahlen in Customer Journey Analytics automatisch als Metriken behandelt. Jetzt können numerische Zeichen (einschließlich benutzerdefinierter Ereignisse aus Adobe Analytics) als Dimensionen behandelt werden. Siehe folgendes Beispiel:

1. Ziehen Sie die Ganzzahl [!UICONTROL call_length_min] in den Abschnitt [!UICONTROL Dimensionen] unter [!UICONTROL Eingeschlossene Komponenten]:

   ![Pfeil, der auf call_length_mins in der Liste der Dimensionen verweist.](../assets/integers.png)

1. Sie können jetzt [!UICONTROL Wertgruppierung] hinzufügen, um diese Dimension in Berichten in zusammengefasster Form darzustellen. (Ohne Gruppierung würde jede Instanz dieser Dimension als Zeilenelement im Arbeitsbereich-Reporting angezeigt.)

   ![Wert-Zusammenstellung mit ausgewähltem Behälterwert.](../assets/bucketing.png)

## 3. Verwenden Sie numerische Dimensionen als „Metriken“ in Flussdiagrammen {#numeric}

Eine numerische Dimension kann verwendet werden, um „Metriken“ in Ihre [!UICONTROL Flussvisualisierung] zu übertragen.

1. Ziehen Sie auf der Registerkarte [Komponenten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de#configure-component-settings) der Datenansichten das Schemafeld [!UICONTROL Marketing-Kanäle] in den Bereich [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
2. In Arbeitsbereich-Berichten zeigt dieser Fluss [!UICONTROL Marketing-Kanäle], die in [!UICONTROL Bestellungen] fließen:

![Marketing-Kanal-Fluss von E-Mails zu Ausstieg/Bestellungen.](../assets/flow.png)

## 4. Unterereignisfilterung durchführen {#sub-event}

Diese Funktion gilt speziell für Array-basierte Felder. Die Einschluss-/Ausschlussfunktion ermöglicht das Filtern auf Ebene der Unterereignisse, während im Filter Builder erstellte Filter (Segmente) nur die Filterung auf Ereignisebene erlauben. So können Sie die Filterung von Unterereignissen durchführen, indem Sie Einschließen/Ausschließen in Datenansichten verwenden und dann auf der Ereignisebene in einem Filter auf diese neue Metrik/Dimension verweisen.

Verwenden Sie beispielsweise die Ein-/Ausschlussfunktion in Datenansichten, um sich nur auf Produkte zu konzentrieren, die einen Umsatz von mehr als 50 Dollar generiert haben. Wenn Sie also eine Bestellung haben, die einen 50-Dollar-Produktkauf und einen 25-Dollar-Produktkauf beinhaltet, würden wir nur den 25-Dollar-Produktkauf entfernen, nicht die gesamte Bestellung.

1. Ziehen Sie auf der Registerkarte [Komponenten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de#configure-component-settings) der Datenansichten das Schema [!UICONTROL Umsatz] in den Bereich [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
1. Wählen Sie die Metrik aus und konfigurieren Sie rechts Folgendes:
a. Wählen Sie unter [!UICONTROL Format] die Option [!UICONTROL Währung] aus.
b. Wählen Sie unter [!UICONTROL Währung] die Option „USD“ aus.
c. Aktivieren Sie unter [!UICONTROL Werte einschließen/ausschließen] das Kontrollkästchen neben [!UICONTROL Ein-/Ausschlusswerte festlegen].
d. Wählen Sie unter [!UICONTROL Match] die Option [!UICONTROL Wenn alle Kriterien erfüllt sind].
e. Wählen Sie unter [!UICONTROL Kriterien] die Option [!UICONTROL ist größer oder gleich] aus.
f. Geben Sie als Wert „50“ an.

Mit diesen neuen Einstellungen können Sie nur Umsätze mit höheren Werten anzeigen und alles unter 50 Dollar herausfiltern.

## 5. Verwenden Sie die Einstellung [!UICONTROL Keine Wertoptionen] {#no-value}

Ihr Unternehmen hat vielleicht Zeit damit verbracht, Ihre Benutzer dahingehend zu schulen, dass sie in Berichten „Nicht angegeben“ erwarten. Der Standardwert in Datenansichten ist „Kein Wert“. Sie können in der Benutzeroberfläche für Datenansichten jetzt [„Kein Wert“ in „Nicht angegeben“ umbenennen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de#configure-no-value-options-settings).

Ein weiteres Beispiel wäre eine Dimension für die Registrierung eines Abonnementprogramms. In diesem Fall können Sie „Kein Wert“ in „Keine Registrierung für ein Abonnementprogramm“ umbenennen.

## 6. Erstellen Sie mehrere Metriken mit unterschiedlichen Einstellungen für die [!UICONTROL Attribution] {#attribution}

Erstellen Sie dazu mithilfe der Funktion [!UICONTROL Duplizieren] oben rechts eine Reihe von Umsatzmetriken mit verschiedenen Attributionseinstellungen wie [!UICONTROL Erstkontakt], [!UICONTROL Letztkontakt] und [!UICONTROL Algorithmisch].

Vergessen Sie nicht, jeder Metrik einen neuen Namen zu geben, um die Unterschiede widerzuspiegeln, z. B. „Algorithmischer Umsatz“:

![Algorithmischer Umsatz mit Zählerwerten, die unter &quot;Verhaltensliste&quot;ausgewählt sind.](../assets/algo-revenue.png)

Weitere Informationen zu anderen Datenansicht-Einstellungen finden Sie unter [Erstellen von Datenansichten](/help/data-views/create-dataview.md).
Eine konzeptionelle Übersicht über die Datenansichten finden Sie unter [Übersicht über Datenansichten](/help/data-views/data-views.md).

## 7. Berichte zu neuen und wiederkehrenden Sitzungen {#new-repeat}

Sie können anhand des Berichtszeitraums, den Sie für diese Datenansicht definiert haben, und eines 13-monatigen Lookback-Fensters bestimmen, ob eine Sitzung tatsächlich die erste Sitzung einer Person ist oder eine wiederkehrende Sitzung. Diese Reporting-Funktion ermöglicht Ihnen beispielsweise, Folgendes zu bestimmen:

* Welcher Prozentsatz von Bestellungen stammt aus neuen oder wiederkehrenden Sitzungen?

* Sprechen Sie auf einem bestimmten Marketing-Kanal oder bei einer bestimmten Kampagne Erstbenutzende an oder Personen, die wiedergekommen sind? Wie beeinflusst diese Auswahl die Konversionsraten?

Eine Dimension und zwei Metriken ermöglichen diese Berichte:

* [Sitzungstyp](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=de#optional) – Diese Dimension hat zwei Werte: 1) [!UICONTROL Neu] und 2) [!UICONTROL Wiederkehrend]. Der Zeileneintrag [!UICONTROL Neu] enthält das gesamte Verhalten (d. h. die Metriken für diese Dimension) einer Sitzung, die als erste Sitzung einer Person definiert wurde. Alles andere ist im Zeileneintrag [!UICONTROL Wiederkehrend] enthalten (vorausgesetzt, dass alles zu einer Sitzung gehört). Wenn Metriken nicht Teil einer Sitzung sind, fallen sie in den Bereich „Nicht zutreffend“ für diese Dimension.

* [Erstmalige Sitzungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=de#optional). Die Metrik Erstmalige Sitzungen wird als die definierte erste Sitzung einer Person im Berichtsfenster definiert.

* [Rückkehrsitzungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=de#optional) Die Metrik &quot;Rückkehrsitzungen&quot;ist die Anzahl der Sitzungen, die keine Erstsitzung einer Person waren.—>

So greifen Sie auf diese Komponente zu:

1. Wechseln Sie zum Datenansichts-Editor.
1. Klicken Sie in der linken Leiste auf **[!UICONTROL Komponenten]** > **[!UICONTROL Optionale Standardkomponenten]**.
1. Ziehen Sie diese Komponenten in Ihre Datenansicht.

In 95-99 % der Fälle werden neue Sitzungen korrekt gemeldet. Die einzigen Ausnahmen sind:

* Wenn eine erste Sitzung vor dem 13-monatigen Lookback-Fenster stattgefunden hat. Diese Sitzung wird ignoriert.

* Wenn eine Sitzung sowohl das Lookback-Fenster als auch den Berichtszeitraum umfasst. Nehmen wir an, ein Bericht wird vom 1. Juni bis zum 15. Juni 2022 erstellt. Das Lookback-Fenster würde die Zeit vom 1. Mai 2021 bis zum 31. Mai 2022 umfassen. Wenn eine Sitzung am 30. Mai 2022 beginnen und am 1. Juni 2022 endet, werden alle Sitzungen im Berichtszeitraum als wiederkehrende Sitzungen gezählt, da die Sitzung im Rückschaufenster enthalten ist.

## 8. Verwenden der Funktionen „Datum“ und „Datum-Uhrzeit“ {#date}

Schemas in Adobe Experience Platform enthalten die Felder [!UICONTROL Datum] und [!UICONTROL Datum-Uhrzeit]. Customer Journey Analytics-Datenansichten unterstützen diese Felder jetzt. Wenn Sie diese Felder als Dimension in eine Datenansicht ziehen, können Sie ihr [Format](/help/data-views/component-settings/format.md) angeben. Diese Formateinstellung legt fest, wie die Felder im Berichtswesen angezeigt werden. Beispiel:

* Wenn Sie für das Datumsformat **[!UICONTROL Tag]** mit dem Format **[!UICONTROL Tag, Monat, Jahr]**, könnte eine Beispielausgabe in Berichten wie folgt aussehen: 23. August 2022.

* Wenn Sie für das Datum-Zeit-Format **[!UICONTROL Tagesminute]** mit dem Format **[!UICONTROL Stunde:Minute]** wählen, könnte Ihre Ausgabe wie folgt aussehen: 20:20.

Wir unterstützen derzeit Datumsangaben nach dem 1. Januar 1900 (mit Ausnahme des 1. Januar 1970) und Datums-/Uhrzeitwerte nach dem 1. Januar 2000 00:00:00.

### Anwendungsfälle mit Datum und Datum/Uhrzeit

* Datum: Ein Reiseunternehmen erfasst in seinen Daten das Abreisedatum für Reisen als Feld. Sie möchten einen Bericht, der den [!UICONTROL Wochentag] für alle gesammelten Abreisedaten vergleicht, um zu verstehen, welche am beliebtesten sind. Sie möchten dasselbe für [!UICONTROL Monat des Jahres] tun.

* Datum-Uhrzeit: Ein Einzelhandelsunternehmen erfasst die Uhrzeit für jeden seiner Einkäufe am Verkaufsort (POS Point-Of-Sale) im Geschäft. Sie möchten wissen, zu welchen Zeiten in einem bestimmten Monat am meisten eingekauft wird, und zwar nach [!UICONTROL Tageszeit].

>[!MORELIKETHIS]
>[Datum und Uhrzeit in der Komponenteneinstellung &quot;Format&quot;](/help/data-views/component-settings/format.md)

