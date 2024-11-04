---
description: Eine Übersicht über die Verwendung von Standardvorlagen in Analysis Workspace.
title: Vorlagen verwenden
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 9f2f79e264d9cdd460751c50fe252bb7237682fd
workflow-type: tm+mt
source-wordcount: '13206'
ht-degree: 3%

---

# Vorlagen verwenden

Vorlagen (oder Unternehmensvorlagen) in Analysis Workspace bieten schnelle Einblicke in die gängigsten Berichtsszenarien. Im Folgenden finden Sie einige Beispiele für Fragen, die Sie mit Vorlagen beantworten können:

* Wie viele Personen Ihre Website besuchen
* Wie viele dieser Besucher Unique Visitors darstellen (d. h. nur ein Mal gezählt werden)
* Wie diese zu Ihrer Site gelangten (ob sie einem Link folgen oder Ihre Site direkt aufrufen)
* Welche Keywords die Besucher zum Browsen des Site-Inhalts einsetzen
* Wie lange sie auf einer bestimmten Seite oder der gesamten Website verweilen
* Welche Links von Besuchern angeklickt wurden und wann diese die Seite verlassen haben
* Welche Marketingkanäle am wirksamsten zu Umsatz oder Konversion-Ereignissen führen
* Wie viel Zeit sie mit dem Anschauen eines Videos verbracht haben
* Welche Browser und Geräte zum Besuch der Seite genutzt wurden

Im Folgenden wird beschrieben, wie Sie Vorlagen auf der Registerkarte [!UICONTROL Vorlagen] in Analysis Workspace aufrufen und verwenden.

## Zugreifen auf und Ausführen einer Vorlage

1. Wählen Sie in Analysis Workspace die Registerkarte [!UICONTROL **Workspace**].

1. Wählen Sie [!UICONTROL **Vorlagen**] aus.

   ![Registerkarte „Berichte“](assets/view-prebuilt-reports.png)

1. Geben Sie im Suchfeld den Namen der Vorlage ein, die Sie finden möchten, und wählen Sie sie dann aus der Vorlagenliste aus.

   Oder

   Wählen Sie die Vorlagenkategorie aus, die Sie anzeigen möchten, und wählen Sie dann die Vorlage aus der Vorlagenliste aus.

   >[!TIP]
   >
   >Um mithilfe der Pfeiltasten durch das Menü zu navigieren, drücken Sie die Schrägstrich-Taste (/) und dann die Nach-unten-Taste. Drücken Sie die Eingabetaste , um die ausgewählte Vorlage zu laden.

   Eine Liste der verfügbaren Vorlagen finden Sie unten im Abschnitt [Verfügbare Vorlagen](#available-templates) .

1. (Optional) Zeigen Sie Vorlagen an und verwenden Sie Vorlagen, die Komponenten enthalten, die in Ihrer Datenansicht nicht verfügbar sind. (Standardmäßig werden nur Vorlagen angezeigt, die Komponenten verwenden, die in Ihrer Datenansicht verfügbar sind.)

   1. Auswählen (Name der Filteroption?) , um Vorlagen anzuzeigen, die zusätzliche Komponenten erfordern.

      <!-- add screenshot -->

   1. Wählen Sie die Vorlage aus, die Sie verwenden möchten.

   1. Wenn die Vorlage Komponenten enthält, die in Ihrer Datenansicht nicht verfügbar sind, wird eine Meldung angezeigt, die angibt, welche Komponenten fehlen. Klicken (Schaltfläche?) , um zur Datenansicht zu gelangen, wo Sie sie automatisch erstellen können. <!--how do you do this? Walk through the process -->

1. Wählen Sie die Vorlage aus, um einen Bericht auf der Basis der von Ihnen ausgewählten Vorlage zu erstellen.

## Vorlagen anpassen und speichern {#use-reports}

Eine Vorlage passt möglicherweise nicht genau zu Ihren Anforderungen, kann Sie jedoch schließen. In diesen Fällen können Sie die Vorlage als Ausgangspunkt verwenden und sie dann an Ihre spezifischen Zwecke anpassen.

Wenn Sie nach den Änderungen von einer Vorlage weg navigieren, werden Sie aufgefordert, Ihre Änderungen zu speichern oder zu verwerfen. Durch das Speichern von Änderungen an einer Vorlage wird die Vorlage als neues Projekt gespeichert.

So passen Sie eine Vorlage an und speichern sie:

1. Wählen Sie in Adobe Analytics die Registerkarte [!UICONTROL **Workspace**] aus.

1. Wählen Sie die Registerkarte [!UICONTROL **Vorlagen**] aus.

1. Wählen Sie die Vorlage aus, die Sie anzeigen möchten. Wählen Sie zum Beispiel unter [!UICONTROL **Am beliebtesten**] den Bericht zu [!UICONTROL **Seiten**].

   Die Seitenvorlage, wie in Analysis Workspace angezeigt, zeigt zwei [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Balkendiagramm](/help/analysis-workspace/visualizations/bar.md) und [Zusammenfassungsnummer](/help/analysis-workspace/visualizations/summary-number-change.md)) und eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) an. Die verwendete Metrik ist „Vorkommen“.

   ![Seitenvorlage](assets/pages-report.png)

1. Führen Sie einen der folgenden Schritte aus:

   * Zeigen Sie die Vorlage an.
   * Sie können ein oder mehrere Segmente oben in den Ablagebereich ziehen. Ziehen Sie beispielsweise das Segment [!UICONTROL **Mobile-Kunden**] und sehen Sie sich die Ergebnisse an.
   * Ändern Sie den Datumsbereich, indem Sie zum Kalender oben rechts gehen.
   * Fügen Sie Dimensionsaufschlüsselungen hinzu, ziehen Sie andere Metriken hinzu und passen Sie die Vorlage im Allgemeinen an Ihre Anforderungen an.

1. (Optional) Speichern Sie die Vorlage als Projekt, indem Sie [!UICONTROL **Projekt**] > [!UICONTROL **Speichern**] auswählen.

   Die Vorlage wird als neues Projekt gespeichert. Der vorhandene Bericht wird dadurch nicht geändert. Weitere Informationen zum Speichern eines Berichts als Projekt finden Sie unter [Projekte speichern](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Verfügbare Vorlagen

So greifen Sie auf alle verfügbaren vordefinierten Vorlagen zu:

1. Wählen Sie in Adobe Analytics die Registerkarte [!UICONTROL **Workspace**] und dann die Registerkarte [!UICONTROL **Vorlagen**] aus.

   Vordefinierte Vorlagen sind nach Kategorie geordnet.

   <!--add screenshot-->

1. Wählen Sie eine Kategorie aus, um die darin enthaltenen Vorlagen anzuzeigen.

   Die folgenden Abschnitte entsprechen den verfügbaren Kategorien und enthalten Informationen zu den einzelnen Vorlagen.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

   * [[!UICONTROL ](#web-conversion)

   * [[!UICONTROL ](#web-audience)

   * [[!UICONTROL ](#web-acquisition)

   * [[!UICONTROL ](#mobile-mobile-app)

   * [[!UICONTROL ](#mobile-mobile-device-information)

   * [[!UICONTROL ](#time-parting)

   * [[!UICONTROL ](#cross-channel)

   * [[!UICONTROL ](#other-channels)

   * [[!UICONTROL ](#ajo)

### Am beliebtesten {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--training"
>title="Schulungsanleitung"
>abstract="Erfahren Sie mehr über die gängige Terminologie und die Schritte zum Erstellen Ihrer ersten Analyse in Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pagesRankedReport"
>title="Identifizieren Sie die beliebtesten und am wenigsten beliebten Seiten."
>abstract="**Dies kann Ihnen** helfen, Ihre Zielgruppe und die Art von Informationen, die sie am meisten interessiert, besser zu verstehen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Seitenmetadaten anpassen, um die Sichtbarkeit auf weniger angezeigten Seiten zu erhöhen, oder Sie verbringen Zeit mit der Verbesserung des Inhalts Ihrer am häufigsten angezeigten Seiten.<br/>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pageViewsOvertimeReport"
>title="Anzeigen der Gesamtanzahl der Seitenansichten. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. "
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit zunehmen oder abnehmen kann.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Site-Traffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Urlaubsverkehr.<br/>Diese Vorlage verwendet die Dimension Tag und die Metrik Seitenansichten ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitsOvertimeReport"
>title="Anzeigen der Gesamtzahl der Besuche Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit zunehmen oder abnehmen kann.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Site-Traffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Urlaubsverkehr.<br/>Diese Vorlage verwendet die Dimension Tag und die Metrik Besuche ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitorsOvertimeReport"
>title="die Gesamtzahl der Unique Visitors anzeigen. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. "
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie die Reichweite und die Zielgruppengröße Ihrer Site im Laufe der Zeit oder im Vergleich zu einem früheren Zeitraum zunimmt oder abnimmt.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. um zu bewerten, ob eine kürzlich gestartete Marketing-Kampagne erfolgreich darin bestand, neue Besucher auf die Site zu locken, indem Sie Unique Visitors vor und nach dem Start der Kampagne vergleichen. Oder Sie können die Anzahl der Personen vergleichen, die die Website während der Ferien im Jahr besuchen.<br/>Diese Vorlage verwendet die Dimension Tag und die Metrik Unique Visitors . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--keyMetricsReport"
>title="Zeigen Sie einen Bericht an, der die Metriken zu Seitenansichten, Besuchen und Unique Visitors nebeneinander anzeigt. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen helfen, diese wichtigen Metriken zu vergleichen, um ein vollständigeres Bild über die Anzahl der Unique Visitors auf der Site, die Anzahl der Seitenbesuche und die Anzahl der Sitzungen zu erhalten.**<br/>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die durchschnittliche Anzahl der Seiten, die jeder Besucher während eines Besuchs auf der Site in einer bestimmten Woche oder in einem bestimmten Monat angesehen hat, und wie sich dies während bestimmter Zeiten des Jahres oder vor und nach der Ausführung von Marketingkampagnen verändert hat. <br/>Diese Vorlage verwendet die Dimension Tag , die Metrik Seitenansichten , die Metrik Besuche und die Metrik Unique Visitors ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--siteSectionRankedReport"
>title="Zeigen Sie die beliebtesten oder leistungsstärksten Abschnitte Ihrer Site an."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Bereiche Ihrer Site am häufigsten besucht werden.<br>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, welche Produkte oder Services Sie bereitstellen, die das meiste Interesse generieren.<br/>Diese Vorlage verwendet die Dimension Sitebereich und die Metrik Besuche ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--next-page-report"
>title="Sehen Sie sich die häufigsten Orte an, die Besucher direkt nach einem Besuch oder unmittelbar vor dem Besuch eines bestimmten Ortes aufrufen."
>abstract="**Dies kann Ihnen** dabei helfen, zu verstehen, wie sich der Traffic von einer bestimmten Seite zu anderen Teilen Ihrer Site bewegt, und die Pfade zu verstehen, die Besucher nehmen, um zu einer bestimmten Seite zu gelangen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, ob das Seitendesign oder das Layout optimiert werden kann, um Personen zu wünschenswerteren Seiten zu leiten, z. B. zu einer Seite, um einen Kauf zu tätigen oder einen Review zu verlassen. Oder bewerten Sie, ob die Informationen auf der aktuellen Seite wahrscheinlich die Richtung oder die Aktionen bieten, nach denen Benutzer suchen, wenn sie von vorherigen Seiten kommen. Oder Sie können bewerten, ob Seiten, die nicht als vorherige Seiten angezeigt werden, auffälliger Links zur aktuellen Seite benötigen.<br/>Diese Vorlage verwendet das Bedienfeld &quot;Nächstes oder vorheriges Element&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignRankedReport"
>title="Zeigen Sie die Links an, die am erfolgreichsten zur Erhöhung des Traffics auf Ihre Site beigetragen haben."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Trackingcodes (und die Links, mit denen sie verknüpft sind) am häufigsten beim Zugriff auf Ihre Site verwendet wurden.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Strategie anpassen, wo Sie Links zu Ihrer Site hinzufügen.<br/>Diese Vorlage verwendet die Dimension Trackingcode und die Metrik Besuche ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productsRankedReport"
>title="Anzeigen der Anzahl der Bestellungen nach Produkt. Daten werden über einen bestimmten Zeitraum angezeigt."
>abstract="**Dies hilft Ihnen** zu verstehen, welche Produkte die höchste oder die niedrigste Nachfrage aufweisen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Marketing-Strategien so anpassen, dass sie leistungsstarke Produkte bewerben oder Produkte mit schlechter Leistung verbessern oder einstellen. Sie können Ihren Produktbestand auch auf Grundlage Ihrer Datenanalyse anpassen.<br/>Diese Vorlage verwendet die Dimension Produkt und die Metrik Bestellungen ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelRankedReport"
>title="Zeigen Sie die neuesten Marketing-Kanäle an, mit denen Besucher während ihres Interaktionszeitraums (standardmäßig 30 Tage) übereinstimmen."
>abstract="**Dies kann Ihnen** dabei helfen zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu bringen, die zu Konversionen führten.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle zuweisen oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.<br/>Diese Vorlage verwendet die Dimension Letztkontakt Kanal und die Metrik Unique Visitors ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelDetailRankedReport"
>title="Zeigen Sie Details zu den neuesten Marketing-Kanälen an, mit denen Besucher während ihres Interaktionszeitraums (standardmäßig 30 Tage) übereinstimmen."
>abstract="**Dies kann Ihnen** helfen, nicht nur zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu bringen, die zu Konversionen führten, sondern auch Details zu diesen Marketing-Kanälen. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle zuweisen oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.<br/>Diese Vorlage verwendet die Dimension Letztkontakt Kanaldetail und die Metrik Unique Visitors . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--revenueOvertimeReport"
>title="Zeigen Sie den Geldbetrag der bei allen Bestellungen gekauften Produkte an. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies hilft Ihnen** zu verstehen, wie der Umsatz im Laufe der Zeit steigt oder abnimmt. Sie können diese Metrik mit einer beliebigen Dimension kombinieren, um zu erfahren, welche Dimensionselemente zum Umsatz beigetragen haben.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. zukünftige Projekterlöse basierend auf früheren Trends. Sie können auch eine weitere Dimension hinzufügen, z. B. die Dimension Trackingcode , um zu erfahren, welche Kampagnen den meisten Umsatz generieren.<br/>Diese Vorlage verwendet die Dimension Tag und die Metrik Umsatz ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ordersOvertimeReport"
>title="Anzeigen der Gesamtanzahl der Kaufereignisse. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie das Interesse an Ihren Produkten und Services im Laufe der Zeit steigt oder abnimmt. Sie können ein Segment anwenden, um zu erfahren, welche Kunden oder Regionen die meisten Bestellungen aufgeben und wie diese Bestellungen im Laufe der Zeit im Trend liegen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne durch Vergleich der Bestellungen vor und nach dem Start der Kampagne. Oder Sie vergleichen Jahresvergleiche mit Urlaubsaufträgen.<br/>Diese Vorlage verwendet die Dimension Tag und die Metrik Bestellungen ."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Tutorial für Schulungen**] | Erfahren Sie mehr über die gängige Terminologie und die Schritte zur Erstellung Ihrer ersten Analyse in Analysis Workspace. |
| [!UICONTROL **Seiten**] | <!--duplicated in Engagement section--> Identifizieren Sie die beliebtesten und am wenigsten beliebten Seiten. <p>**Dies kann Ihnen** helfen, Ihre Zielgruppe und die Art von Informationen, die sie am meisten interessiert, besser zu verstehen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Seitenmetadaten anpassen, um die Sichtbarkeit auf weniger angezeigten Seiten zu erhöhen, oder Sie verbringen Zeit mit der Verbesserung des Inhalts Ihrer am häufigsten angezeigten Seiten.</p><p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Seitenansichten**] | <!--duplicated in Engagement section--> Anzeigen der Gesamtanzahl der Seitenansichten. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit zunehmen oder abnehmen kann.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Site-Traffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Urlaubsverkehr.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Webbesuche**] | <!--duplicated in Engagement section--> Anzeigen der Gesamtzahl der Besuche Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit zunehmen oder abnehmen kann.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Site-Traffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Urlaubsverkehr.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Besuche .</p> |
| [!UICONTROL **Webbesucher**] | <!--duplicated in Engagement section--> die Gesamtzahl der Unique Visitors anzeigen. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie die Reichweite und die Zielgruppengröße Ihrer Site im Laufe der Zeit oder im Vergleich zu einem früheren Zeitraum zunimmt oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. um zu bewerten, ob eine kürzlich gestartete Marketing-Kampagne erfolgreich darin bestand, neue Besucher auf die Site zu locken, indem Sie Unique Visitors vor und nach dem Start der Kampagne vergleichen. Oder Sie können die Anzahl der Personen vergleichen, die die Website während der Ferien im Jahr besuchen.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Schlüsselmetriken**] | <!--duplicated in Engagement section--> Zeigen Sie einen Bericht an, der die Metriken zu Seitenansichten, Besuchen und Unique Visitors nebeneinander anzeigt. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen, diese wichtigen Metriken zu vergleichen, um ein vollständigeres Bild über die Anzahl der Unique Visitors auf der Site, die Anzahl der Seitenbesuche und die Anzahl der Sitzungen zu erhalten.**</p><p>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die durchschnittliche Anzahl der Seiten, die jeder Besucher während eines Besuchs auf der Site in einer bestimmten Woche oder in einem bestimmten Monat angesehen hat, und wie sich dies während bestimmter Zeiten des Jahres oder vor und nach der Ausführung von Marketingkampagnen verändert hat. </p><p>Diese Vorlage verwendet die Dimension Tag , die Metrik Seitenansichten , die Metrik Besuche und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Sitebereiche**] | Zeigen Sie die beliebtesten oder leistungsstärksten Abschnitte Ihrer Site an. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Bereiche Ihrer Site am häufigsten besucht werden.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, welche Produkte oder Services Sie bereitstellen, die das meiste Interesse generieren.</p> <p>Diese Vorlage verwendet die Dimension Sitebereich und die Metrik Besuche .</p> |
| [!UICONTROL **Nächste und vorherige Seite**] | Sehen Sie sich die häufigsten Orte an, die Besucher direkt nach einem Besuch oder unmittelbar vor dem Besuch eines bestimmten Ortes aufrufen. <p>**Dies kann Ihnen** dabei helfen, zu verstehen, wie sich der Traffic von einer bestimmten Seite zu anderen Teilen Ihrer Site bewegt, und die Pfade zu verstehen, die Besucher nehmen, um zu einer bestimmten Seite zu gelangen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, ob das Seitendesign oder das Layout optimiert werden kann, um Personen zu wünschenswerteren Seiten zu leiten, z. B. zu einer Seite, um einen Kauf zu tätigen oder einen Review zu verlassen. Oder bewerten Sie, ob die Informationen auf der aktuellen Seite wahrscheinlich die Richtung oder die Aktionen bieten, nach denen Benutzer suchen, wenn sie von vorherigen Seiten kommen. Oder Sie können bewerten, ob Seiten, die nicht als vorherige Seiten angezeigt werden, auffälliger Links zur aktuellen Seite benötigen.</p><p>Diese Vorlage verwendet das Bedienfeld Nächstes oder vorheriges Element .</p> |
| [!UICONTROL **Kampagnen (Trackingcode)**] | Zeigen Sie die Links an, die am erfolgreichsten zur Erhöhung des Traffics auf Ihre Site beigetragen haben. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Trackingcodes (und die Links, mit denen sie verknüpft sind) am häufigsten beim Zugriff auf Ihre Site verwendet wurden.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Strategie anpassen, wo Sie Links zu Ihrer Site hinzufügen.</p><p>Diese Vorlage verwendet die Dimension Trackingcode und die Metrik Besuche .</p> |
| [!UICONTROL **Produkte**] | Anzeigen der Anzahl der Bestellungen nach Produkt. Daten werden über einen bestimmten Zeitraum angezeigt. <p>**Dies hilft Ihnen** zu verstehen, welche Produkte die höchste oder die niedrigste Nachfrage aufweisen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Marketing-Strategien so anpassen, dass sie leistungsstarke Produkte bewerben oder Produkte mit schlechter Leistung verbessern oder einstellen. Sie können Ihren Produktbestand auch auf Grundlage Ihrer Datenanalyse anpassen.</p><p>Diese Vorlage verwendet die Dimension Produkt und die Metrik Bestellungen .</p> |
| [!UICONTROL **Letztkontakt Marketingkanal**] | Zeigen Sie die neuesten Marketing-Kanäle an, mit denen Besucher während ihres Interaktionszeitraums (standardmäßig 30 Tage) übereinstimmen.<p>**Dies kann Ihnen** dabei helfen zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu bringen, die zu Konversionen führten.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle zuweisen oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.</p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanal und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Letztkontakt Marketingkanaldetail**] | Zeigen Sie Details zu den neuesten Marketing-Kanälen an, mit denen Besucher während ihres Interaktionszeitraums (standardmäßig 30 Tage) übereinstimmen.<p>**Dies kann Ihnen** helfen, nicht nur zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu bringen, die zu Konversionen führten, sondern auch Details zu diesen Marketing-Kanälen. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle zuweisen oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.</p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanaldetail und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Umsatz**] | <!--duplicated in Web Conversion section-->Zeigen Sie den Geldbetrag der bei allen Bestellungen gekauften Produkte an. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen.<p>**Dies hilft Ihnen** zu verstehen, wie der Umsatz im Laufe der Zeit steigt oder abnimmt. Sie können diese Metrik mit einer beliebigen Dimension kombinieren, um zu erfahren, welche Dimensionselemente zum Umsatz beigetragen haben.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. zukünftige Projekterlöse basierend auf früheren Trends. Sie können auch eine weitere Dimension hinzufügen, z. B. die Dimension Trackingcode , um zu erfahren, welche Kampagnen den meisten Umsatz generieren.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Umsatz .</p> |
| [!UICONTROL **Bestellungen**] | <!--duplicated in Web Conversion section-->Anzeigen der Gesamtanzahl der Kaufereignisse. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie das Interesse an Ihren Produkten und Services im Laufe der Zeit steigt oder abnimmt. Sie können ein Segment anwenden, um zu erfahren, welche Kunden oder Regionen die meisten Bestellungen aufgeben und wie diese Bestellungen im Laufe der Zeit im Trend liegen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne durch Vergleich der Bestellungen vor und nach dem Start der Kampagne. Oder Sie vergleichen Jahresvergleiche mit Urlaubsaufträgen.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Bestellungen .</p> |

### Web: Interaktion {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Sehen Sie sich die durchschnittliche Besuchszeit auf Ihrer Site während jedes Besuchs sowie die durchschnittliche Besuchszeit vor einem Erfolgsereignis an. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen** helfen, die Interaktionsstufen der Besucher besser zu verstehen und zu verstehen, wie viel Zeit Besucher benötigen, um eine gewünschte Aktion durchzuführen, z. B. einen Kauf.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. um zu bewerten, ob Änderungen an Ihrer Site die Fähigkeit der Besucher verbessern, schnell ein Erfolgsereignis zu erreichen.<br/>Diese Vorlage verwendet die Dimension Tag , die Metrik Zeit pro Besuch (Sekunden) , die Dimension Tag und die Metrik Zeit pro Besuch (Sekunden) ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-content-consumption"
>title="Sehen Sie sich an, welche Webinhalte am häufigsten verwendet werden und wie Benutzer angesprochen werden."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wo Personen beim ersten Einstieg in die Site hineingehen, welche Bereiche der Site von den Besuchern am häufigsten besucht werden und welche Seiten die Besucher am wahrscheinlichsten von der Site wegführen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site weg führen.<br/>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Außerdem werden Flussvisualisierungen für Einstiegs-, Ausstiegs- und Top-Abschnitte verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--media-content-consumption"
>title="Sehen Sie sich an, welche Medieninhalte am häufigsten verwendet werden und Benutzer anregen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wo Personen beim ersten Einstieg in die Site hineingehen, welche Bereiche der Site von den Besuchern am häufigsten besucht werden und welche Seiten die Besucher am wahrscheinlichsten von der Site wegführen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site weg führen.<br/>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Darüber hinaus werden Flussvisualisierungen für Einstiegs-, Ausstiegs- und oberste Abschnitte verwendet, eine Starterplotvisualisierung, die Seitenansichten für die häufigsten Seiten anzeigt, eine Balkenvisualisierung, die Seitenansichten nach zusammengefasster Zeit anzeigt, und eine Linienvisualisierung, die eine Trendansicht der durchschnittlichen Besuchszeit auf der Site anzeigt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--page-summary-report"
>title="Zeigen Sie wichtige Informationen zu beliebigen Seiten in Ihren Eigenschaften an. Zeigt Seitenansichten, eine Trendlinie, eine Flussvisualisierung und mehr an."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer mit einer bestimmten Seite interagieren.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Leistung der Seite über einen bestimmten Zeitraum analysieren oder besser verstehen, was den Traffic zur Seite bringt.<br/>Diese Vorlage verwendet die Metrik &quot;Seitenansichten&quot;. Außerdem werden die Linienvisualisierung und die Flussvisualisierung verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--entryPageRankedReport"
>title="Zeigen Sie die wichtigsten Seiten an, auf die Benutzer beim ersten Besuch Ihrer Site zugreifen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Seiten den meisten Traffic zu Ihrer Site leiten, oder mehr über die ersten Impressionen zu verstehen, die Besucher auf Ihrer Site haben.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die ersten Erlebnisse optimieren, die Besucher auf der Site erhalten, oder sicherstellen, dass die Seiten, die Besucher beim Einstieg auf Ihre Site zuerst sehen, willkommen heißen und die erforderlichen Links zu anderen Bereichen Ihrer Site bereitstellen.<br/>Diese Vorlage verwendet die Sitzungsmetrik. Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--exitPageRankedReport"
>title="Zeigen Sie die wichtigsten Seiten an, auf die Benutzer unmittelbar vor dem Verlassen Ihrer Site zugreifen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Seiten Personen von der Site wegführen. <br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. gängige Exitpages aktualisieren, um das Erlebnis zu optimieren, das Besucher vor dem Verlassen erhalten, oder Inhalte oder Links einschließen, um Menschen dazu zu ermutigen, auf Ihrer Site zu bleiben.<br/>Diese Vorlage verwendet die Sitzungsmetrik. Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Schlüsselmetriken**] | <!--duplicated in Most popular section--> Zeigen Sie einen Bericht an, der die Metriken zu Seitenansichten, Besuchen und Unique Visitors nebeneinander anzeigt. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen, diese wichtigen Metriken zu vergleichen, um ein vollständigeres Bild über die Anzahl der Unique Visitors auf der Site, die Anzahl der Seitenbesuche und die Anzahl der Sitzungen zu erhalten.**</p><p>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die durchschnittliche Anzahl der Seiten, die jeder Besucher während eines Besuchs auf der Site in einer bestimmten Woche oder in einem bestimmten Monat angesehen hat, und wie sich dies während bestimmter Zeiten des Jahres oder vor und nach der Ausführung von Marketingkampagnen verändert hat. </p><p>Diese Vorlage verwendet die Dimension Tag , die Metrik Seitenansichten , die Metrik Besuche und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Seitenansichten**] | <!--duplicated in Most popular section-->Anzeigen der Gesamtanzahl der Seitenansichten. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit zunehmen oder abnehmen kann.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Site-Traffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Urlaubsverkehr.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Seiten**] | <!--duplicated in Most popular section-->Identifizieren Sie die beliebtesten und am wenigsten beliebten Seiten. <p>**Dies kann Ihnen** helfen, Ihre Zielgruppe und die Art von Informationen, die sie am meisten interessiert, besser zu verstehen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Seitenmetadaten anpassen, um die Sichtbarkeit auf weniger angezeigten Seiten zu erhöhen, oder Sie verbringen Zeit mit der Verbesserung des Inhalts Ihrer am häufigsten angezeigten Seiten.</p><p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Besuche**] | <!--duplicated in Most popular section-->Anzeigen der Gesamtzahl der Besuche Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit zunehmen oder abnehmen kann.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Site-Traffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Urlaubsverkehr.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Besuche .</p> |
| [!UICONTROL **Besucher**] | <!--duplicated in Most popular section-->die Gesamtzahl der Unique Visitors anzeigen. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie die Reichweite und die Zielgruppengröße Ihrer Site im Laufe der Zeit oder im Vergleich zu einem früheren Zeitraum zunimmt oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. um zu bewerten, ob eine kürzlich gestartete Marketing-Kampagne erfolgreich darin bestand, neue Besucher auf die Site zu locken, indem Sie Unique Visitors vor und nach dem Start der Kampagne vergleichen. Oder Sie können die Anzahl der Personen vergleichen, die die Website während der Ferien im Jahr besuchen.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Besuchszeit**] | Sehen Sie sich die durchschnittliche Besuchszeit auf Ihrer Site während jedes Besuchs sowie die durchschnittliche Besuchszeit vor einem Erfolgsereignis an. Die Daten werden über einen bestimmten Zeitraum hinweg angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen** helfen, die Interaktionsstufen der Besucher besser zu verstehen und zu verstehen, wie viel Zeit Besucher benötigen, um eine gewünschte Aktion durchzuführen, z. B. einen Kauf.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. um zu bewerten, ob Änderungen an Ihrer Site die Fähigkeit der Besucher verbessern, schnell ein Erfolgsereignis zu erreichen.</p><p>Diese Vorlage verwendet die Dimension Tag , die Metrik Zeit pro Besuch (Sekunden) , die Dimension Tag und die Metrik Zeit pro Besuch (Sekunden) .</p> |
| [!UICONTROL **Sitebereiche**] | <!--duplicated in Most popular section-->Zeigen Sie die beliebtesten oder leistungsstärksten Abschnitte Ihrer Site an. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Bereiche Ihrer Site am häufigsten besucht werden.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. um zu beurteilen, welche Produkte oder Services Sie bereitstellen, die das meiste Interesse generieren.</p> <p>Diese Vorlage verwendet die Dimension Sitebereich und die Metrik Besuche .</p> |
| [!UICONTROL **Nutzung von Webinhalten**] | Sehen Sie sich an, welche Webinhalte am häufigsten verwendet werden und wie Benutzer angesprochen werden.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wo Personen beim ersten Einstieg in die Site hineingehen, welche Bereiche der Site von den Besuchern am häufigsten besucht werden und welche Seiten die Besucher am wahrscheinlichsten von der Site wegführen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. feststellen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site wegführen <!-- not sure about these takeaways... -->.</p> <p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Außerdem werden Flussvisualisierungen für Einstiegs-, Ausstiegs- und Top-Abschnitte verwendet.</p> |
| [!UICONTROL **Verbrauch von Medieninhalten**] | Sehen Sie sich an, welche Medieninhalte am häufigsten verwendet werden und Benutzer anregen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wo Personen beim ersten Einstieg in die Site hineingehen, welche Bereiche der Site von den Besuchern am häufigsten besucht werden und welche Seiten die Besucher am wahrscheinlichsten von der Site wegführen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. feststellen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site wegführen <!-- not sure about these takeaways... -->.</p> <p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Darüber hinaus werden Flussvisualisierungen für Einstiegs-, Ausstiegs- und oberste Abschnitte verwendet, eine Starterplotvisualisierung, die Seitenansichten für die häufigsten Seiten anzeigt, eine Balkenvisualisierung, die Seitenansichten nach zusammengefasster Zeit anzeigt, und eine Linienvisualisierung, die eine Trendansicht der durchschnittlichen Besuchszeit auf der Site anzeigt.</p> |
| [!UICONTROL **Nächste und vorherige Seite**] | <!--duplicated in Most popular section-->Sehen Sie sich die häufigsten Orte an, an denen Besucher vor oder nach dem Besuch eines bestimmten Ortes reisen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wo Personen beim ersten Einstieg in die Site hineinnavigieren, welche Bereiche der Site von den Besuchern am häufigsten besucht werden und welche Seiten am ehesten besucht werden, bevor sie die Site verlassen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. feststellen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site weg führen.<!-- not sure about these takeaways... --></p> <p>Diese Vorlage verwendet die Dimension Seite , die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Darüber hinaus werden Flussvisualisierungen für Einstiegs-, Ausstiegs- und oberste Abschnitte, eine Streudiagrammdarstellung mit Seitenansichten für die häufigsten Seiten, eine Balkenvisualisierung, die Seitenansichten nach Zusammenfassungszeit anzeigt, und eine Linienvisualisierung verwendet, die eine Trendansicht der durchschnittlichen Besuchszeit auf der Site anzeigt.</p> |
| **Seitenzusammenfassung** | Zeigen Sie wichtige Informationen zu beliebigen Seiten in Ihren Eigenschaften an. Zeigt Seitenansichten, eine Trendlinie, eine Flussvisualisierung und mehr an.  <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer mit einer bestimmten Seite interagieren.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Leistung der Seite über einen bestimmten Zeitraum analysieren oder besser verstehen, was den Traffic zur Seite bringt.</p><p>Diese Vorlage verwendet die Metrik Seitenansichten . Außerdem werden die Linienvisualisierung und die Flussvisualisierung verwendet.</p> |
| **Entrypages** | Zeigen Sie die wichtigsten Seiten an, auf die Benutzer beim ersten Besuch Ihrer Site zugreifen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Seiten den meisten Traffic zu Ihrer Site leiten, oder mehr über die ersten Impressionen zu verstehen, die Besucher auf Ihrer Site haben.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die ersten Erlebnisse optimieren, die Besucher auf der Site erhalten, oder sicherstellen, dass die Seiten, die Besucher beim Einstieg auf Ihre Site zuerst sehen, willkommen heißen und die erforderlichen Links zu anderen Bereichen Ihrer Site bereitstellen.</p><p>Diese Vorlage verwendet die Metrik Sitzungen . Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet.</p> |
| **Exitpages** | Zeigen Sie die wichtigsten Seiten an, auf die Benutzer unmittelbar vor dem Verlassen Ihrer Site zugreifen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Seiten Personen von der Site wegführen. </p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. gängige Exitpages aktualisieren, um das Erlebnis zu optimieren, das Besucher vor dem Verlassen erhalten, oder Inhalte oder Links einschließen, um Menschen dazu zu ermutigen, auf Ihrer Site zu bleiben.</p><p>Diese Vorlage verwendet die Metrik Sitzungen . Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet.</p> |

### Web: Conversion {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productConversionReport"
>title="Produktkonversionstrichter-Vorlage"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-products-template"
>title="Anzeigen der Produkte mit der höchsten Leistung."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Produkte am erfolgreichsten sind.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Erhöhung der Finanzierung für erfolgreiche Produkte und die Verringerung der Finanzierung für weniger erfolgreiche Produkte.<br/>Diese Vorlage verwendet die Metriken &quot;Produktansichten&quot;, &quot;Zusatz zum Warenkorb&quot;, &quot;Bestellungen&quot;, &quot;Umsatz&quot;und &quot;Einheiten&quot;. Außerdem wird die Dimension Produkt verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartConversionReport"
>title="Sehen Sie sich an, wie oft Personen wichtige Checkout-Ereignisse ausgeführt haben, z. B. das Hinzufügen von Artikeln zum Warenkorb, das Anzeigen des Warenkorbs, das Entfernen von Artikeln aus dem Warenkorb und das Auschecken."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Teile des Checkout-Prozess-Trichters zu einer Konversion führen und welche eher zum Warenkorbabbruch neigen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Reibung bei bestimmten Schritten des Checkout-Prozesses reduzieren.<br/>Diese Vorlage verwendet die"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartsOvertimeReport"
>title="Zeigen Sie die Anzahl der Personen an, die ein Produkt zum Warenkorb hinzugefügt haben."
>abstract="**Dies kann Ihnen** dabei helfen, die Anzahl der Personen, die ein Produkt zum Warenkorb hinzufügen, besser zu verstehen als die Gesamtzahl der Produkte, die zum Warenkorb hinzugefügt werden.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität Ihrer Produktseiten messen.<br/>Diese Vorlage verwendet die Metrik Warenkorb ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartViewsOvertimeReport"
>title="Zeigt an, wie oft Personen ihren Warenkorb angezeigt haben."
>abstract="**Dies kann Ihnen** dabei helfen, das Kassengang-Erlebnis besser zu verstehen, um die Warenkorbabbruchsraten zu reduzieren oder die Zeit zwischen Warenkorbabbrüchen und Checkouts zwischen verschiedenen Produkten zu analysieren.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Angebotsaktionen für Produkte, die am längsten im Warenkorb bleiben und das größte Risiko für einen Abbruch aufweisen.<br/>Diese Vorlage verwendet die Metrik Warenkorbansichten ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartAdditionsOvertimeReport"
>title="Sehen Sie sich an, wie oft Personen etwas zum Warenkorb hinzugefügt haben."
>abstract="**Dies kann Ihnen** helfen, den Teil des Konversionstrichter besser zu verstehen, in dem das Kundeninteresse an einem Produkt so hoch ist, dass es zum Warenkorb hinzugefügt wird.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. die Verbesserung der Produktempfehlungen für alle Kunden. Dazu können Sie analysieren, welche Produkte häufig demselben Warenkorb hinzugefügt werden, und verwandte Produkte auf der Grundlage von Artikeln vorschlagen, die bereits im Warenkorb enthalten sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartRemovalsOvertimeReport"
>title="Sehen Sie sich an, wie oft Personen etwas aus dem Warenkorb entfernt haben."
>abstract="**Dies kann Ihnen** dabei helfen, den Teil des Konversionstrichter besser zu verstehen, in dem Kunden kein Interesse mehr an einem Produkt haben, oder Ihnen dabei helfen, zu verstehen, wo im Checkout-Prozess möglicherweise Probleme auftreten.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. potenzielle Barrieren beseitigen, die im Checkout-Prozess bestehen könnten, wie z. B. ein kompliziertes Benutzererlebnis.<br/>Diese Vorlage verwendet die Metrik Entnahme aus Warenkorb ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--purchaseConversionReport"
>title="Vorlage für Einkaufskonversionstrichter"
>abstract=""

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Produktkonversionstrichter**] | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Produkte** | Zeigen Sie an, auf welche Produkte Schlüsselmetriken wie Topverkäufe oder am häufigsten angezeigte Produkte verweisen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Produkte am erfolgreichsten sind.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Erhöhung der Finanzierung für erfolgreiche Produkte und die Verringerung der Finanzierung für weniger erfolgreiche Produkte.</p><p>Diese Vorlage verwendet die Metrik Bestellungen und die Dimension Produkt . |
| **Produktleistung** | Anzeigen der Produkte mit der höchsten Leistung.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Produkte am erfolgreichsten sind.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Erhöhung der Finanzierung für erfolgreiche Produkte und die Verringerung der Finanzierung für weniger erfolgreiche Produkte.</p><p>Diese Vorlage verwendet die Metriken Produktansichten, Zusatz zum Warenkorb, Bestellungen, Umsatz und Einheiten . Außerdem wird die Dimension Produkt verwendet. |
| **Umrechnungstrichter für Warenkorb** | Sehen Sie sich an, wie oft Personen wichtige Checkout-Ereignisse ausgeführt haben, z. B. das Hinzufügen von Artikeln zum Warenkorb, das Anzeigen des Warenkorbs, das Entfernen von Artikeln aus dem Warenkorb und das Auschecken. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Teile des Checkout-Prozess-Trichters zu einer Konversion führen und welche eher zum Warenkorbabbruch neigen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Reibung bei bestimmten Schritten des Checkout-Prozesses reduzieren.</p><p>Diese Vorlage verwendet die |
| **Warenkorb** | Zeigen Sie die Anzahl der Personen an, die ein Produkt zum Warenkorb hinzugefügt haben.<p>**Dies kann Ihnen** dabei helfen, die Anzahl der Personen, die ein Produkt zum Warenkorb hinzufügen, besser zu verstehen als die Gesamtzahl der Produkte, die zum Warenkorb hinzugefügt werden.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Effektivität Ihrer Produktseiten messen.</p><p>Diese Vorlage verwendet die Metrik Warenkorb . |
| **Warenkorbansicht** | Zeigt an, wie oft Personen ihren Warenkorb angezeigt haben. <p>**Dies kann Ihnen** dabei helfen, das Kassengang-Erlebnis besser zu verstehen, um die Warenkorbabbruchsraten zu reduzieren oder die Zeit zwischen Warenkorbabbrüchen und Checkouts zwischen verschiedenen Produkten zu analysieren.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Angebotsaktionen für Produkte, die am längsten im Warenkorb bleiben und das größte Risiko für einen Abbruch aufweisen.</p><p>Diese Vorlage verwendet die Metrik Warenkorbansichten . |
| **Zusatz zum Warenkorb** | Sehen Sie sich an, wie oft Personen etwas zum Warenkorb hinzugefügt haben. <p>**Dies kann Ihnen** helfen, den Teil des Konversionstrichter besser zu verstehen, in dem das Kundeninteresse an einem Produkt so hoch ist, dass es zum Warenkorb hinzugefügt wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. die Verbesserung der Produktempfehlungen für alle Kunden. Dazu können Sie analysieren, welche Produkte häufig demselben Warenkorb hinzugefügt werden, und verwandte Produkte auf der Grundlage von Artikeln vorschlagen, die bereits im Warenkorb enthalten sind. |
| **Entnahme aus Warenkorb** | Sehen Sie sich an, wie oft Personen etwas aus dem Warenkorb entfernt haben.<p>**Dies kann Ihnen** dabei helfen, den Teil des Konversionstrichter besser zu verstehen, in dem Kunden kein Interesse mehr an einem Produkt haben, oder Ihnen dabei helfen, zu verstehen, wo im Checkout-Prozess möglicherweise Probleme auftreten.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. potenzielle Barrieren beseitigen, die im Checkout-Prozess bestehen könnten, wie z. B. ein kompliziertes Benutzererlebnis.</p><p>Diese Vorlage verwendet die Metrik Entnahme aus Warenkorb . |
| **Einkaufskonversionstrichter** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Umsatz** | <!--duplicated in Most popular section-->Zeigen Sie den Geldbetrag der bei allen Bestellungen gekauften Produkte an.<p>**Dies kann Ihnen** dabei helfen, besser zu verstehen, welche Dimensionselemente zum Umsatz beigetragen haben, indem die Umsatzmetrik mit einer beliebigen Dimension kombiniert wird. Sie könnten beispielsweise die Top-Kampagnen (unter Verwendung der Dimension Trackingcode ) sehen, die zum Umsatz beigetragen haben. </p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Kampagnen anpassen, die nicht den erwarteten Umsatzzielen entsprechen.</p><p>Diese Vorlage verwendet die Umsatzmetrik. |
| **Bestellungen** | <!--duplicated in Most popular section-->Anzeigen der Gesamtzahl der Kaufereignisse auf Ihrer Site. <p>**Dies kann Ihnen** dabei helfen, besser zu verstehen, welche Dimensionselemente zu einer Bestellung beigetragen haben, indem die Metrik &quot;Bestellungen&quot;mit einer beliebigen Dimension kombiniert wird. Sie könnten beispielsweise die Top-Kampagnen (unter Verwendung der Dimension Trackingcode ) sehen, die zu Käufen beigetragen haben.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Kampagnen anpassen, die nicht den erwarteten Einkaufszielen entsprechen. </p><p>Diese Vorlage verwendet die Metrik Bestellungen . |

### Web: Audience {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Sehen Sie sich das Land an, aus dem die Besucher der Site stammen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, was die beliebtesten Länder sind, aus denen Besucher Ihre Site besuchen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen treffen, z. B. die Verwendung der Daten, um sich auf die Marketing-Maßnahmen in diesen Ländern zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Ländern mit unterschiedlichen Hauptsprachen optimal ist.<br/>Diese Vorlage verwendet die Dimension &quot;Länder&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Sehen Sie sich den Staat (in den USA) an, aus dem die Besucher der Site stammen. Dies ähnelt der Vorlage Geo-Regionen , allerdings ist sie spezifisch für die USA."
>abstract="**Dies kann Ihnen** helfen, die beliebtesten US-Bundesstaaten besser zu verstehen, von denen die Besucher Ihrer Site stammen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. die Verwendung der Daten, um sich auf Marketing-Maßnahmen in diesen Status zu konzentrieren.<br/>Diese Vorlage verwendet die Dimension &quot;US-Staaten&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Sehen Sie sich die geografische Region an, aus der die Besucher der Site stammen. Eine Region ist ein geografisches Gebiet, das kleiner als ein Land, aber größer als eine Stadt ist. In einigen Ländern ist unter einer Region ein Bundesstaat, eine Provinz oder eine Präfektur zu verstehen. In anderen Gebieten handelt es sich um ein konstituierendes Land, ein Departement oder eine großstädtische Region. "
>abstract="**Dies kann Ihnen** helfen, die beliebtesten Regionen besser zu verstehen, aus denen die Besucher Ihre Site besuchen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Regionen zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Regionen mit unterschiedlichen Hauptsprachen optimal ist. <br/>Diese Vorlage verwendet die Dimensionen ID (Variablen/Land) und Regionen . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Zeigen Sie die Stadt an, aus der die Besucher der Site stammen."
>abstract="**Dies kann Ihnen** helfen, die beliebtesten Städte besser zu verstehen, von denen die Besucher Ihre Site besuchen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Städten zu konzentrieren. <br/>Diese Vorlage verwendet die Dimension &quot;Städte&quot;"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Zeigen Sie die vorgesehenen Marketing-Gebiete (DMAs) in den USA an, aus denen die Besucher der Site stammen."
>abstract="**Dies kann Ihnen** helfen, die beliebtesten Regionen besser zu verstehen, aus denen die Besucher Ihre Site besuchen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in den erfolgreichsten Regionen zu konzentrieren. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Zeigen Sie die wichtigsten Sprachen an, in denen Besucher Inhalte am liebsten sehen."
>abstract="**Dies kann Ihnen** dabei helfen, die am häufigsten bevorzugten Sprachen der Besucher besser zu verstehen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Lokalisierungs- oder Marketingbemühungen für die beliebtesten Sprachen.<br/>Diese Vorlage verwendet die Dimension Sprache ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Technologieübersicht"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Zeigen Sie den Namen und die Version der wichtigsten Browser an, die für den Zugriff auf Ihre Site verwendet werden."
>abstract="**Dies kann Ihnen** dabei helfen, die gängigsten Browser, die Besucher verwenden, besser zu verstehen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. die Verbesserung der Site-Qualität durch Testen neuer Versionen Ihrer Site mit den wichtigsten Browsern. Auf diese Weise können die Qualitätssicherungsbemühungen maximiert werden.<br/>Diese Vorlage verwendet die Dimension Browser ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Zeigen Sie die Namen der Organisationen an, die die wichtigsten Browser erstellt haben, mit denen Benutzer auf Ihre Site zugreifen. Dies unterscheidet sich von der Browser-Vorlage insofern, als sie nicht verschiedene Versionen desselben Browsers als separate Dimensionselemente auflistet."
>abstract="**Dies kann Ihnen** dabei helfen, die gängigsten Browser, die Besucher verwenden, besser zu verstehen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** verschiedene Dinge tun, z. B. die Site-Qualität verbessern, indem Sie neue Versionen Ihrer Site mit den wichtigsten Browsern testen. Auf diese Weise können die Qualitätssicherungsbemühungen maximiert werden. <br/>Diese Vorlage verwendet die Dimension Browsertyp . "

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Erste und Wiederholte Benutzer**] | Vergleich von erstmaligen Besuchern mit wiederkehrenden Besuchern anzeigen. <p>**Dies kann Ihnen** helfen, die Effektivität Ihrer Site bei der Aufrechterhaltung der Kundenloyalität oder die Rate, mit der Sie neue Kunden gewinnen, besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Anreize für zukünftige Käufe an erstmalige Besucher, um sie zur Rückkehr zu bewegen.</p><p>Diese Vorlage verwendet die </p> |
| **Personen-ID/Namespace** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die  </p> |
| **Standortübersicht** | Zeigen Sie eine Übersicht über die Besucherposition in einer Zuordnungsvisualisierung an.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wo sich Besucher befinden, die Ihre Site besuchen. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Ressourcen an den Orten konzentrieren, an denen Sie das größte Interesse und die beste Gelegenheit sehen.</p><p>Diese Vorlage verwendet die  </p> |
| **Geo Countries** | Sehen Sie sich das Land an, aus dem die Besucher der Site stammen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, was die beliebtesten Länder sind, aus denen Besucher Ihre Site besuchen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen treffen, z. B. die Verwendung der Daten, um sich auf die Marketing-Maßnahmen in diesen Ländern zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Ländern mit unterschiedlichen Hauptsprachen optimal ist.</p><p>Diese Vorlage verwendet die Dimension Länder . </p> |
| **US-Bundesstaaten** | Sehen Sie sich den Staat (in den USA) an, aus dem die Besucher der Site stammen. Dies ähnelt der Vorlage Geo-Regionen , allerdings ist sie spezifisch für die USA.<p>**Dies kann Ihnen** helfen, die beliebtesten US-Bundesstaaten besser zu verstehen, von denen die Besucher Ihrer Site stammen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. die Verwendung der Daten, um sich auf Marketing-Maßnahmen in diesen Status zu konzentrieren.</p><p>Diese Vorlage verwendet die Dimension US-Bundesstaaten . </p> |
| **Geo-Regionen** | Sehen Sie sich die geografische Region an, aus der die Besucher der Site stammen. Eine Region ist ein geografisches Gebiet, das kleiner als ein Land, aber größer als eine Stadt ist. In einigen Ländern ist unter einer Region ein Bundesstaat, eine Provinz oder eine Präfektur zu verstehen. In anderen Gebieten handelt es sich um ein konstituierendes Land, ein Departement oder eine großstädtische Region. <p>**Dies kann Ihnen** helfen, die beliebtesten Regionen besser zu verstehen, aus denen die Besucher Ihre Site besuchen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Regionen zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Regionen mit unterschiedlichen Hauptsprachen optimal ist. </p><p>Diese Vorlage verwendet die Dimensionen ID (Variablen/Land) und Regionen . </p> |
| **Geo-Städte** | Zeigen Sie die Stadt an, aus der die Besucher der Site stammen. <p>**Dies kann Ihnen** helfen, die beliebtesten Städte besser zu verstehen, von denen die Besucher Ihre Site besuchen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Städten zu konzentrieren. </p><p>Diese Vorlage verwendet die Dimension &quot;Städte&quot; </p> |
| **Geo US DMA** | Zeigen Sie die vorgesehenen Marketing-Gebiete (DMAs) in den USA an, aus denen die Besucher der Site stammen.<p>**Dies kann Ihnen** helfen, die beliebtesten Regionen besser zu verstehen, aus denen die Besucher Ihre Site besuchen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in den erfolgreichsten Regionen zu konzentrieren. </p><p>Diese Vorlage verwendet die </p> |
| **Sprachen** | Zeigen Sie die wichtigsten Sprachen an, in denen Besucher Inhalte am liebsten sehen. <p>**Dies kann Ihnen** dabei helfen, die am häufigsten bevorzugten Sprachen der Besucher besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Lokalisierungs- oder Marketingbemühungen für die beliebtesten Sprachen.</p><p>Diese Vorlage verwendet die Dimension Sprache .</p> |
| **Technologieübersicht** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die </p> |
| **Browser** | Zeigen Sie den Namen und die Version der wichtigsten Browser an, die für den Zugriff auf Ihre Site verwendet werden.<p>**Dies kann Ihnen** dabei helfen, die gängigsten Browser, die Besucher verwenden, besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. die Verbesserung der Site-Qualität durch Testen neuer Versionen Ihrer Site mit den wichtigsten Browsern. Auf diese Weise können die Qualitätssicherungsbemühungen maximiert werden.</p><p>Diese Vorlage verwendet die Dimension Browser . </p> |
| **Browsertypen** | Zeigen Sie die Namen der Organisationen an, die die wichtigsten Browser erstellt haben, mit denen Benutzer auf Ihre Site zugreifen. Dies unterscheidet sich von der Browser-Vorlage insofern, als sie nicht verschiedene Versionen desselben Browsers als separate Dimensionselemente auflistet.<p>**Dies kann Ihnen** helfen, die gängigsten Browser, die Besucher verwenden, besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. die Verbesserung der Site-Qualität durch Testen neuer Versionen Ihrer Site mit den wichtigsten Browsern. Auf diese Weise können die Qualitätssicherungsbemühungen maximiert werden. </p><p>Diese Vorlage verwendet die Dimension Browsertyp . </p> |

### Web: Akquise {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Bei Verwendung der benutzerdefinierten Attribution zeigt diese Vorlage, wie Besucher auf Ihre Site gelangen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Ihrer Marketing-Kanäle am effektivsten sind.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. intensiver in effektive Marketing-Kanäle investieren und weniger effektive Marketing-Kanäle veräußern.<br/>Diese Vorlage verwendet die Dimension ID(variables/marketingchannel) und die Umsatzmetrik."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Zeigen Sie den ersten Marketing-Kanal an, mit dem ein Besucher während des Interaktionszeitraums des Besuchers übereinstimmt (standardmäßig 30 Tage)."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Marketing-Kanäle den anfänglichen Traffic zu Ihrer Site leiten.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.<br/>Diese Vorlage verwendet die Dimension Erstkontaktkanal ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Zeigen Sie Details zum ersten Marketing-Kanal an, mit dem ein Besucher während des Interaktionszeitraums des Besuchers (standardmäßig 30 Tage) übereinstimmt."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, was dazu beigetragen hat, dass der Treffer einem Marketing-Kanal entsprach. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.<br/>Diese Vorlage verwendet die Dimension &quot;Erstkontakt Kanaldetail&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Kampagnenkonversionstrichter"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Zeigen Sie Details zur Leistung Ihrer Marketing-Kampagnen an."
>abstract="**Dies kann Ihnen** helfen, mehr über die verschiedenen Erfolgsindikatoren zu verstehen, die mit Kampagnen verbunden sind, wie Umsatz, Produktansichten, Bestellungen usw.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Marketing-Maßnahmen auf die Kampagnen zu konzentrieren, die den meisten Umsatz bringen. <br/>Diese Vorlage verwendet die Metrik Umsatz , die Metrik Produktansichten , die Metrik Zusatz zum Warenkorb , die Metrik Bestellungen und Einheiten . Außerdem werden die Dimension &quot;Trackingcode&quot;und die Dimension &quot;Referrer-Domäne&quot;verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-acquisition-template"
>title="Sehen Sie sich an, wie Ihre Website Besucher erhält."
>abstract="**Dies kann Ihnen** helfen, mehr über die verschiedenen Faktoren zu verstehen, die zur Akquise führen, wie Suchbegriffe, Referrer-Domäne usw.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Bemühungen auf die effektivsten Kanäle konzentrieren.<br/>Diese Vorlage verwendet die Metrik Absprungrate und die Metrik Absprünge . Außerdem werden die Dimension Suchmaschine , die Dimension Suchbegriff , die Dimension Entrypage , die Dimension Referrer-Domäne , die Dimension Trackingcode und die Dimension Referrer verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden, unabhängig davon, ob diese gebührenpflichtig oder kostenlos ist."
>abstract="**Dies kann Ihnen** helfen, die Suchbegriffe besser zu verstehen, die bei Suchvorgängen verwendet werden, die zum Site-Traffic führen. <br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Suchbegriffen, die den Site-Traffic fördern, identifizieren und füllen.<br/>Diese Vorlage verwendet die Dimension Suchbegriff ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden und die mit der gebührenpflichtigen Sucherkennung übereinstimmen."
>abstract="**Dies kann Ihnen** helfen, die Suchbegriffe besser zu verstehen, die bei Suchvorgängen verwendet werden, die zum Site-Traffic führen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Suchbegriffen, die den Site-Traffic fördern, identifizieren und füllen. <br/>Diese Vorlage verwendet die Dimension Suchbegriff - Gebührenpflichtig . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden und die nicht mit der gebührenpflichtigen Sucherkennung übereinstimmen."
>abstract="**Dies kann Ihnen** helfen, die Suchbegriffe besser zu verstehen, die bei Suchvorgängen verwendet werden, die zum Site-Traffic führen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Suchbegriffen, die den Site-Traffic fördern, identifizieren und füllen.<br/>Diese Vorlage verwendet die Dimension Suchbegriff - Kostenlos . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Zeigen Sie die Suchmaschinen an, die Besucher verwenden, um Ihre Site zu erreichen, unabhängig davon, ob die Suche gebührenpflichtig oder kostenlos ist."
>abstract="**Dies kann Ihnen** helfen, die Suchmaschinen besser zu verstehen, die Benutzer verwenden, die zu Site-Traffic führen. <br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.<br/>Diese Vorlage verwendet die Dimension Suchmaschine . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Zeigen Sie die Suchmaschinen an, die Besucher zum Erreichen Ihrer Site verwenden und die mit der gebührenpflichtigen Sucherkennung übereinstimmen."
>abstract="**Dies kann Ihnen** helfen, die Suchmaschinen besser zu verstehen, die Benutzer verwenden, die zu Site-Traffic führen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten. <br/>Diese Vorlage verwendet die Dimension Suchmaschine - Gebührenpflichtig ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden und die nicht mit der gebührenpflichtigen Sucherkennung übereinstimmen."
>abstract="**Dies kann Ihnen** helfen, die Suchmaschinen besser zu verstehen, die Benutzer verwenden, die zu Site-Traffic führen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.<br/>Diese Vorlage verwendet die Dimension Suchmaschine - Kostenlos ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Zeigen Sie an, durch welche Domänen Besucher klicken, um Ihre Site zu erreichen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Drittanbieter-Sites den meisten Traffic zu Ihnen leiten. (Auf der externen Site muss ein Link vorhanden sein und ein Besucher muss darauf klicken, damit das Dimensionselement angezeigt wird.)<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus den Top-Referrer-Domänen anzupassen. <br/>Diese Vorlage verwendet die Dimension Referrer-Domäne ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Zeigen Sie die erste Referrer-Domäne an, durch die Benutzer zum Erreichen Ihrer Site geklickt haben. (Sobald sie festgelegt ist, enthält sie denselben Wert für die gesamte Lebensdauer dieser Besucher-ID.)"
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Drittanbieter-Sites den Traffic ursprünglich zu Ihrer Site leiten.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus den ursprünglichen Referrerdomänen anzupassen. <br/>Diese Vorlage verwendet die Dimension &quot;Ursprünglich verweisende Domäne&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Zeigen Sie an, auf welchen URLs sich Besucher befanden, als sie sich durchklickten, um zu Ihrer Site zu gelangen. (Auf der externen URL muss ein Link vorhanden sein und ein Besucher muss darauf klicken, damit das Dimensionselement angezeigt wird.)"
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche spezifischen URLs den meisten Traffic zu Ihrer Site leiten.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher anzupassen, die von Top-URLs kommen. <br/>Diese Vorlage verwendet die Dimension Referrer-Domäne .</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Zeigen Sie an, durch welche generischen Kanäle Besucher geklickt haben, um zu Ihrer Site zu gelangen. Adobe verwaltet die Regeln für jeden Kanal. Mögliche Kanäle sind Suchmaschinen, soziale Netzwerke, andere Websites, Festplatte oder E-Mail."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welcher Typ von Referrern den meisten Traffic zu Ihrer Site bringt.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus einem bestimmten Kanal anzupassen.<br/>Diese Vorlage verwendet die Dimension Referrer-Typ ."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Marketingkanal-Übersichtsbericht**] | Bei Verwendung der benutzerdefinierten Attribution zeigt diese Vorlage, wie Besucher auf Ihre Site gelangen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Ihrer Marketing-Kanäle am effektivsten sind.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. intensiver in effektive Marketing-Kanäle investieren und weniger effektive Marketing-Kanäle veräußern.</p><p>Diese Vorlage verwendet die Dimension ID (Variablen/Marketing-Kanal) und die Metrik Umsatz .</p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Erstkontakt Marketingkanal**] | Zeigen Sie den ersten Marketing-Kanal an, mit dem ein Besucher während des Interaktionszeitraums des Besuchers übereinstimmt (standardmäßig 30 Tage). <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Marketing-Kanäle den anfänglichen Traffic zu Ihrer Site leiten.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.</p><p>Diese Vorlage verwendet die Dimension Erstkontakt Kanal .</p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Erstkontakt Marketingkanaldetail**] | Zeigen Sie Details zum ersten Marketing-Kanal an, mit dem ein Besucher während des Interaktionszeitraums des Besuchers (standardmäßig 30 Tage) übereinstimmt.<p>**Dies kann Ihnen** helfen, besser zu verstehen, was dazu beigetragen hat, dass der Treffer einem Marketing-Kanal entsprach. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.</p><p>Diese Vorlage verwendet die Dimension Erstkontakt Kanaldetail .</p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Letztkontakt Marketingkanal**] | Zeigen Sie den neuesten Marketing-Kanal an, mit dem ein Besucher während des Interaktionszeitraums des Besuchers übereinstimmt (standardmäßig 30 Tage).<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Marketing-Kanäle Traffic zu Ihrer Site leiten, der zu Konversionen führt.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.</p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanal .  </p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Letztkontakt Marketingkanaldetail**] | Details zum neuesten Marketing-Kanal anzeigen, mit dem ein Besucher während des Interaktionszeitraums des Besuchers (standardmäßig 30 Tage) übereinstimmt<p>**Dies kann Ihnen** helfen, besser zu verstehen, was dazu beigetragen hat, dass der Treffer einem Marketing-Kanal entsprach. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind. </p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanaldetail . </p> |
| [!UICONTROL **Kampagnen**] > [!UICONTROL **Kampagnen (Trackingcode)**] | Zeigen Sie die Namen der Trackingcodes auf Ihrer Site an. Sie können Links mit unterschiedlichen Abfragezeichenfolgenparameterwerten an verschiedenen Stellen im Internet platzieren.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Links am erfolgreichsten zur Erhöhung des Traffics auf Ihre Site beigetragen haben. Abfragezeichenfolgen für Trackingcodes werden häufig in E-Mails, Anzeigen, Social-Media-Beiträgen und anderen Marketing-Maßnahmen verwendet, die Ihr Unternehmen verwendet</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Marketing-Maßnahmen auf die Kampagnen zu konzentrieren, die den meisten Umsatz bringen.</p><p>Diese Vorlage verwendet die Dimension Trackingcode . </p> |
| [!UICONTROL **Kampagnen**] > [!UICONTROL **Kampagnenkonversionstrichter**] | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die  </p> |
| [!UICONTROL **Kampagnen**] > [!UICONTROL **Kampagnenleistung**] | Zeigen Sie Details zur Leistung Ihrer Marketing-Kampagnen an.<p>**Dies kann Ihnen** helfen, mehr über die verschiedenen Erfolgsindikatoren zu verstehen, die mit Kampagnen verbunden sind, wie Umsatz, Produktansichten, Bestellungen usw.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Marketing-Maßnahmen auf die Kampagnen zu konzentrieren, die den meisten Umsatz bringen. </p><p>Diese Vorlage verwendet die Metrik Umsatz , die Metrik Produktansichten , die Metrik Zusatz zum Warenkorb , die Metrik Bestellungen und Einheiten . Außerdem werden die Dimension &quot;Trackingcode&quot;und die Dimension &quot;Referrer-Domäne&quot;verwendet. </p> |
| **Web-Akquise** | Sehen Sie sich an, wie Ihre Website Besucher erhält.<p>**Dies kann Ihnen** helfen, mehr über die verschiedenen Faktoren zu verstehen, die zur Akquise führen, wie Suchbegriffe, Referrer-Domäne usw.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Bemühungen auf die effektivsten Kanäle konzentrieren.</p><p>Diese Vorlage verwendet die Metrik Absprungrate und die Metrik Absprünge . Außerdem werden die Dimension Suchmaschine , die Dimension Suchbegriff , die Dimension Entrypage , die Dimension Referrer-Domäne , die Dimension Trackingcode und die Dimension Referrer verwendet.  </p> |
| **Suchkeywords-all** | Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden, unabhängig davon, ob diese gebührenpflichtig oder kostenlos ist. <p>**Dies kann Ihnen** helfen, die Suchbegriffe besser zu verstehen, die bei Suchvorgängen verwendet werden, die zum Site-Traffic führen. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Suchbegriffen, die den Site-Traffic fördern, identifizieren und füllen.</p><p>Diese Vorlage verwendet die Dimension Suchbegriff . </p> |
| **Suchkeywords-paid** | Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden und die mit der gebührenpflichtigen Sucherkennung übereinstimmen.<p>**Dies kann Ihnen** helfen, die Suchbegriffe besser zu verstehen, die bei Suchvorgängen verwendet werden, die zum Site-Traffic führen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Suchbegriffen, die den Site-Traffic fördern, identifizieren und füllen. </p><p>Diese Vorlage verwendet die Dimension Suchbegriff - Gebührenpflichtig . </p> |
| **Suchkeywords-kostenlos** | Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden und die nicht mit der gebührenpflichtigen Sucherkennung übereinstimmen.<p>**Dies kann Ihnen** helfen, die Suchbegriffe besser zu verstehen, die bei Suchvorgängen verwendet werden, die zum Site-Traffic führen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Suchbegriffen, die den Site-Traffic fördern, identifizieren und füllen.</p><p>Diese Vorlage verwendet die Dimension Suchbegriff - Kostenlos . </p> |
| **Suchmaschinen-Alle** | Zeigen Sie die Suchmaschinen an, die Besucher verwenden, um Ihre Site zu erreichen, unabhängig davon, ob die Suche gebührenpflichtig oder kostenlos ist. <p>**Dies kann Ihnen** helfen, die Suchmaschinen besser zu verstehen, die Benutzer verwenden, die zu Site-Traffic führen. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.</p><p>Diese Vorlage verwendet die Dimension Suchmaschine . </p> |
| **Suchmaschinen-bezahlt** | Zeigen Sie die Suchmaschinen an, die Besucher zum Erreichen Ihrer Site verwenden und die mit der gebührenpflichtigen Sucherkennung übereinstimmen.<p>**Dies kann Ihnen** helfen, die Suchmaschinen besser zu verstehen, die Benutzer verwenden, die zu Site-Traffic führen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten. </p><p>Diese Vorlage verwendet die Dimension Suchmaschine - Gebührenpflichtig . </p> |
| **Suchmaschinen-kostenlos** | Zeigen Sie die Suchbegriffe an, die Besucher zum Erreichen Ihrer Site verwenden und die nicht mit der gebührenpflichtigen Sucherkennung übereinstimmen.<p>**Dies kann Ihnen** helfen, die Suchmaschinen besser zu verstehen, die Benutzer verwenden, die zu Site-Traffic führen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.</p><p>Diese Vorlage verwendet die Dimension Suchmaschine - Kostenlos . </p> |
| **Referrerdomänen** | Zeigen Sie an, durch welche Domänen Besucher klicken, um Ihre Site zu erreichen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Drittanbieter-Sites den meisten Traffic zu Ihnen leiten. (Auf der externen Site muss ein Link vorhanden sein und ein Besucher muss darauf klicken, damit das Dimensionselement angezeigt wird.)</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus den Top-Referrer-Domänen anzupassen. </p><p>Diese Vorlage verwendet die Dimension Referrer-Domäne . </p> |
| **Ursprünglich Referrerdomänen** | Zeigen Sie die erste Referrer-Domäne an, durch die Benutzer zum Erreichen Ihrer Site geklickt haben. (Sobald sie festgelegt ist, enthält sie denselben Wert für die gesamte Lebensdauer dieser Besucher-ID.)<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Drittanbieter-Sites den Traffic ursprünglich zu Ihrer Site leiten.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus den ursprünglichen Referrerdomänen anzupassen. </p><p>Diese Vorlage verwendet die Dimension &quot;Ursprünglich verweisende Domäne&quot;. </p> |
| **Verweisende Stellen** | Zeigen Sie an, auf welchen URLs sich Besucher befanden, als sie sich durchklickten, um zu Ihrer Site zu gelangen. (Auf der externen URL muss ein Link vorhanden sein und ein Besucher muss darauf klicken, damit das Dimensionselement angezeigt wird.)  <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche spezifischen URLs den meisten Traffic zu Ihrer Site leiten.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher anzupassen, die von Top-URLs kommen. </p><p>Diese Vorlage verwendet die Dimension Referrerdomäne . </p><p>Diese Vorlage verwendet die Dimension Referrer . </p> |
| **Typen der verweisenden Stellen** | Zeigen Sie an, durch welche generischen Kanäle Besucher geklickt haben, um zu Ihrer Site zu gelangen. Adobe verwaltet die Regeln für jeden Kanal. Mögliche Kanäle sind Suchmaschinen, soziale Netzwerke, andere Websites, Festplatte oder E-Mail.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welcher Typ von Referrern den meisten Traffic zu Ihrer Site bringt.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus einem bestimmten Kanal anzupassen.</p><p>Diese Vorlage verwendet die Dimension Referrer-Typ .</p> |

### Mobile: Mobile App {#mobile-app}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-lifecycle-metrics-app-usage-template"
>title="Nutzung mobiler Apps"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-journeys"
>title="Journey für mobile Apps"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-key-metrics"
>title="Mobile-App-Metriken"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-messaging"
>title="Mobile-App-Nachrichten"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-performance-template"
>title="Leistung mobiler Apps"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-retention"
>title="Beibehaltung mobiler Apps"
>abstract=""

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Mobile App Screens**] | Zeigen Sie Informationen zu den Mobilgeräten an, die Benutzer beim Zugriff auf Ihre Site verwenden, z. B. Bildschirmgröße, Bildschirmbreite und Bildschirmhöhe. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie Personen Ihre Site erleben.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. das Rendering Ihrer Site für die häufigsten Bildschirmgrößen optimieren.</p><p>Diese Vorlage verwendet die |
| **Mobile App-Aktionen** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Mobile App Usage** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Journey der mobilen App** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Mobile-App-Metriken** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Mobile App Messaging** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Leistung der mobilen App** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Beibehaltung mobiler Apps** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |

### Mobile: Informationen zu Mobilgeräten {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileCarrierRankedReport"
>title="Zeigen Sie das Telekommunikationsunternehmen an, das Mobilfunknetzverbindungen zu den Mobilgeräten bereitstellt, mit denen Benutzer auf Ihre Website zugreifen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Mobilnetzbetreiber bei Ihrer Benutzerbasis am beliebtesten sind.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Netzwerkfunktionen verschiedener Anbieter anpassen, um ein reibungsloses Benutzererlebnis zu gewährleisten.<br/>Diese Vorlage verwendet die Dimension Mobilnetzbetreiber ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceNameRankedReport"
>title="Zeigen Sie die Marke und das Modell von Mobilgeräten an, mit denen Benutzer auf Ihre Site zugreifen."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Mobilgeräte bei Ihrer Benutzerbasis am beliebtesten sind.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. das Rendering Ihrer Site für die gängigsten Mobilgeräte optimieren.<br/>Diese Vorlage verwendet die Dimension Mobilgerätename ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceTypeRankedReport"
>title="Zeigen Sie die Mobilgerätetypen an, mit denen Benutzer auf Ihre Site zugreifen, z. B. Smartphones und Tablets."
>abstract="**Dies kann Ihnen** dabei helfen, die verschiedenen Arten von Mobilgeräten besser zu verstehen, die für den Zugriff auf Ihre Site verwendet werden.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Site für die Mobilgerätetypen optimieren, die am häufigsten verwendet werden.<br/>Diese Vorlage verwendet die Dimension Mobilgerätetyp ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileManufacturerRankedReport"
>title="Ermitteln Sie, welche Hersteller die Mobilgeräte herstellen, mit denen Benutzer auf Ihre Site zugreifen, z. B. Apple und Samsung."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Hersteller bei Ihrer Benutzerbasis am beliebtesten sind.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Fähigkeiten verschiedener Hersteller anpassen, um ein reibungsloses Benutzererlebnis zu gewährleisten.<br/>Diese Vorlage verwendet die Dimension Mobilgerätehersteller ."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Mobilnetzbetreiber**] | Zeigen Sie das Telekommunikationsunternehmen an, das Mobilfunknetzverbindungen zu den Mobilgeräten bereitstellt, mit denen Benutzer auf Ihre Website zugreifen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Mobilnetzbetreiber bei Ihrer Benutzerbasis am beliebtesten sind.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Netzwerkfunktionen verschiedener Anbieter anpassen, um ein reibungsloses Benutzererlebnis zu gewährleisten.</p><p>Diese Vorlage verwendet die Dimension Mobilnetzbetreiber .</p> |
| **Mobilgeräte** | Zeigen Sie die Marke und das Modell von Mobilgeräten an, mit denen Benutzer auf Ihre Site zugreifen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Mobilgeräte bei Ihrer Benutzerbasis am beliebtesten sind.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. das Rendering Ihrer Site für die gängigsten Mobilgeräte optimieren.</p><p>Diese Vorlage verwendet die Dimension Mobilgerätename .</p> |
| **Mobilgerätetyp** | Zeigen Sie die Mobilgerätetypen an, mit denen Benutzer auf Ihre Site zugreifen, z. B. Smartphones und Tablets.<p>**Dies kann Ihnen** dabei helfen, die verschiedenen Arten von Mobilgeräten besser zu verstehen, die für den Zugriff auf Ihre Site verwendet werden.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Site für die Mobilgerätetypen optimieren, die am häufigsten verwendet werden.</p><p>Diese Vorlage verwendet die Dimension Mobilgerätetyp .</p> |
| **Hersteller** | Ermitteln Sie, welche Hersteller die Mobilgeräte herstellen, mit denen Benutzer auf Ihre Site zugreifen, z. B. Apple und Samsung.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Hersteller bei Ihrer Benutzerbasis am beliebtesten sind.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Fähigkeiten verschiedener Hersteller anpassen, um ein reibungsloses Benutzererlebnis zu gewährleisten.</p><p>Diese Vorlage verwendet die Dimension Mobilgerätehersteller .</p> |

### Zeitunterteilung

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Minute der Stunde**] | Anzeigen der Anzahl der Ereignisse, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Minuten. Wenn Sie beispielsweise einen Bericht mit einem Berichtszeitrahmen von einem einzelnen Tag haben, wird die erste Minute jeder Stunde des Tages in dasselbe Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, Trends auf granularer Ebene besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die Dimension Minute der Stunde . |
| **Stunde des Tages** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Stunden des Tages. Wenn Sie beispielsweise einen Bericht haben, der sich vom 1. Januar bis zum 7. Januar erstreckt, wird die erste Stunde jedes Tages in dasselbe Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, die Tageszeit besser zu verstehen, zu der Ihre Site am häufigsten und am wenigsten häufig besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihrer Site während hoher Traffic-Zeiten mehr Rechenressourcen zuweisen.</p><p>Diese Vorlage verwendet die Dimension Stunde des Tages. |
| **Vormittag/Nachmittag** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach AM und PM. Wenn Sie beispielsweise einen Bericht haben, der sich vom 1. Januar bis zum 7. Januar erstreckt, werden die AM-Stunden jedes Tages in dasselbe Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, die Tageszeit besser zu verstehen, zu der Ihre Site am häufigsten und am wenigsten häufig besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihrer Site während hoher Traffic-Zeiten mehr Rechenressourcen zuweisen.</p><p>Diese Vorlage verwendet die AM/PM-Dimension. |
| **Wochentag** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Wochentagen. Wenn Sie beispielsweise einen Bericht haben, der sich auf den Monat Januar erstreckt, wird jeder Wochentag in dasselbe Dimensionselement gruppiert. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Wochentage Ihre Site am häufigsten und am seltensten besucht.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.</p><p>Diese Vorlage verwendet die Dimension Wochentag . |
| **Tag des Monats** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Tag des Monats. Wenn Sie beispielsweise einen Bericht haben, der sich auf ein ganzes Jahr erstreckt, wird jeder Tag des Monats in ein und dasselbe Dimensionselement gruppiert. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Tage eines jeden Monats Ihre Site am häufigsten und am wenigsten häufig besucht.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.</p><p>Diese Vorlage verwendet die Dimension Tag des Monats . |
| **Tag des Jahres** | Zeigen Sie Ereignisse, Sitzungen und Personen auf Ihrer Site an, aufgeschlüsselt nach Tag des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jeder Tag des Jahres in ein und dasselbe Dimensionselement gruppiert. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Tage eines jeden Jahres Ihre Site am häufigsten und am wenigsten häufig besucht.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.</p><p>Diese Vorlage verwendet die Dimension Tag des Jahres . |
| **Wochentag/Wochenende** | Zeigen Sie Ereignisse, Sitzungen und Personen auf Ihrer Site an, aufgeschlüsselt nach Wochentagen und Wochenenden. Wenn Sie beispielsweise einen Bericht haben, der sich auf den Januar erstreckt, werden Wochentage und Wochenenden in separate Dimensionselemente gruppiert. <p>**Dies kann Ihnen** helfen, die Unterschiede im Site-Traffic für Wochentage und Wochenenden besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter stärker an den Wochenenden zu beschäftigen, wenn der Bericht darauf hinweist, dass Wochenenden schlechter sind als Wochentage.</p><p>Diese Vorlage verwendet die Dimension Wochentag/Wochenende . |
| **Woche des Jahres** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Woche des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jede Woche in demselben Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Wochen des Jahres Ihre Site am häufigsten und am wenigsten häufig besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter für Wochen mit hohem Traffic besser betreuen, z. B. während der Feiertage.</p><p>Diese Vorlage verwendet die Dimension Woche des Jahres . |
| **Monat des Jahres** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Monat des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jeder Monat in demselben Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, besser zu verstehen, in welchen Monaten Ihre Site am häufigsten und am seltensten besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter für Monate mit hohem Traffic-Aufkommen besser betreuen, z. B. während der Feiertage.</p><p>Diese Vorlage verwendet die Dimension Monat des Jahres . |
| **Quartal des Jahres** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Quartal des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jedes Quartal in demselben Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Quartale Ihre Site am häufigsten und am seltensten besucht.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Zeit des Produktstarts, um historisch wenig Traffic-Viertel zu steigern.</p><p>Diese Vorlage verwendet die Dimension &quot;Quartal des Jahres&quot;. |

### Kanalübergreifend

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Überblick über mehrere Kanäle**] | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Kanalübergreifender Vergleich** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Callcenter-Erkennung (Web+Call Center)** | Sehen Sie sich an, wie der Web-Traffic den Callcenter-Traffic beeinflusst.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wie erfolgreich der Self-Service-Inhalt auf Ihrer Website den Traffic zu Ihrem Callcenter lenkt.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. den Self-Service-Inhalt verbessern, um den Traffic zu Ihrem Callcenter zu reduzieren, oder den ROI Ihres Self-Service-Inhalts messen, indem Sie den durch weniger Support-Aufrufe eingesparten Betrag berechnen.</p><p>Diese Vorlage verwendet die |
| **Web+App** | Anzeigen von Web-Traffic und mobilem Traffic<p>**Dies kann Ihnen** dabei helfen, die Verteilung des Web- und mobilen Traffics auf Ihre Site besser zu verstehen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. mehr Ressourcen für Ihr App-Erlebnis zuweisen, wenn es ein bestimmtes Traffic-Niveau erreicht.</p><p>Diese Vorlage verwendet die |
| **Online/Offline** | Anzeigen von Online- und Offline-Traffic gemeinsam.<p>**Dies kann Ihnen** helfen, die Verteilung des Online- und Offline-Traffics auf Ihre Site besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für Ihr Online-Erlebnis bereitstellen, wenn es ein bestimmtes Traffic-Niveau erreicht.</p><p>Diese Vorlage verwendet die |

### Andere Kanäle

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Callcenter-Dashboard**] | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **POS/Offline** | Zeigen Sie POS- und Offline-Transaktionsdaten an.<p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **E-Mail/AJO** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Umfrage** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |

### AJO {#AJO-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="AJO-Kampagnen"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="AJO-Journeys"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="AJO-Landingpages"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="AJO-Übersichtsbericht"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="AJO-Abonnements"
>abstract=""

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **AJO-Kampagnen**] | Zeigen Sie wichtige Metriken für Ihre Journey Optimizer-Kampagnen an, darunter E-Mail-Kampagnen, Experimente, In-App-Nachrichten, SMS usw.<p>**Dies kann Ihnen** dabei helfen, Details wie die Anzahl der Klicks und die Anzahl der zugestellten Nachrichten besser zu verstehen. So erhalten Sie einen umfassenden Einblick in die Effektivität und den Grad der Interaktion Ihrer Kampagne.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Kampagnen auf der Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen.</p> |
| **AJO Journey** | Zeigen Sie wichtige Metriken für Ihre Journey Optimizer-Journey an, darunter E-Mail-Journey, Experimente, In-App-Nachrichten, SMS und mehr.<p>**Dies kann Ihnen** dabei helfen, Details wie die Anzahl der Klicks und die Anzahl der zugestellten Nachrichten besser zu verstehen. So erhalten Sie einen umfassenden Einblick in die Effektivität Ihrer Journey und den Grad der Interaktion.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Kampagnen auf der Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen.</p> |
| **AJO-Einstiegsseiten** | Anzeigen von Benutzerverhalten, Interaktionsmustern, Konversionsraten und anderen Schlüsselmetriken.<p>**Dies kann Ihnen** helfen, die Effektivität Ihrer Landingpage besser zu verstehen. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Leistung Ihrer Landingpage optimieren.</p> |
| **AJO-Übersichtsbericht** | Zeigen Sie eine ausführliche Zusammenfassung der Traffic- und Interaktionsmetriken für alle Kampagnen und Journey in Ihrer Umgebung an.<p>**Dies kann Ihnen** helfen, die Effektivität Ihrer Kampagnen und Journey besser zu verstehen. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Kampagnen und Journey auf Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen.</p> |
| **AJO-Abonnements** | Anzeigen von Anmeldungen und Abmeldungen von Profilen, die bestimmten Listen zugeordnet sind.<p>**Dies kann Ihnen** helfen, die Effektivität verschiedener Abonnementkampagnen und -initiativen bei der Förderung von Interaktion und Konversionen besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Abonnementkampagnen auf der Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen.</p> |


<!-- deleted: 

| [!UICONTROL **Real-Time**] | View the dimensions and metrics that are currently being collected on your site. <p>**This can help you** better understand what is trending on your site.</p><p>**Based on what you learn, you might** respond to and actively manage the performance of your current marketing content and campaigns.</p> <p>This template uses the [Real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> | 
| [!UICONTROL **Fallout**] | View where people leave or continue through a predefined sequence of pages.<p>**This can help you** better understand where people are falling out of the user journey.</p><p>**Based on what you learn, you might** do any number of things, like analyze conversion rates through specific processes on your site (such as a purchase or registration process), or analyze correlations between events on your site. (For example, what percentage of people who looked at your privacy policy went on to purchase a product.) You can also use this template to perform side-by-side comparisons of two different segments in the same report.</p> <p>This template uses the [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> | 
| [!UICONTROL **Cross-device analysis**] | View which devices people used across all points of the journey.<p>**This can help you** better understand how many people interact with your brand, the types of devices they use, and how their use of multiple devices affects their experience. For example, how often do people begin a task on a mobile device and then later move to a desktop to complete a task? What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed? And so forth.</p><p>**Based on what you learn, you might** do any number of things, like optimize certain parts of the user journey for a mobile experience.</p> <p>This template uses the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Cohort analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [the People metric](/help/components/metrics/people.md), and [the Unique devices metric](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Web retention**] | View who your loyal users are and what they are doing on your site.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 
| [!UICONTROL **Streaming Media Consumption**] | View  trends and top metrics of media consumption across all digital devices.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 

-->

<!--

Ignore below this 

| Menu item | Reports under this menu item |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Training Tutorial (Pre-existing Workspace template)</li><li>Pages (What are my top pages?)</li><li>Page views (How many page views am I generating?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Key metrics (How are my most important metrics performing?)</li><li>Site sections (Which sections of my site generated the most page views?)</li><li>Real-Time (What is trending on my site, and why?)</li><li>Next page (What are the next pages my visitors go to?)</li><li>Previous page (What are the previous pages my visitors went to?)</li><li>Campaigns (What campaigns are driving my key metrics?)</li><li>Products (What products are driving my key metrics?)</li><li>Last touch channel (Which last touch channel is performing best?</li><li>Last touch channel detail (Which specific last touch channel is outperforming others?)</li><li>Revenue (How is my revenue performing?)</li><li>Orders (How are my orders performing?)</li><li>Units (How many units am I selling?)</li></ul> | 
| **[!UICONTROL Engagement]** | <ul><li>Key metrics (How are my most important metrics performing?)</li><li>Page views (How many page views am I generating?)</li><li>Pages (What are my top pages?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Time spent per visit (How much time do my users spend per visit?)</li><li>Time prior to event (How much time do my users spend prior to a success event?)</li><li>Site sections (Which sections of my site generated the most page views?</li><li>Web content consumption (Which content is consumed most and is engaging users?)</li><li>Media content consumption (Which content is consumed most and is engaging users?)</li><li>Next and previous page flow (What are/were the next/previous paths my visitors take/took?)</li><li>Fallout (Where am I seeing fallout through my digital properties?)</li><li>Cross-device analysis (Using cross-device analysis in Analysis Workspace)</li><li>Web retention (Who are my loyal users and what do they do?)</li><li>Media audio consumption (What are trends and top metrics of audio consumption?)</li><li>Media recency, frequency, loyalty (Who are my loyal readers?)</li><li>Page analysis > Reloads (Which pages generate the most reloads?)</li><li>Page analysis > Time spent on page (How much time do my users spend on my pages?)</li><li>Entries & exits > Entry pages (What are my top entry pages?)</li><li>Entries & exits > Original entry pages (What page did my visitor originally enter from?)</li><li>Entries & exits > Single-page visits (Which pages generated the most single-page visits?)</li><li>Entries & exits > Exit pages (What are my top exit pages?)</li><li>Page Analysis > Page summary</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Products > Products (Which products are driving my key metrics?)</li><li>Products > Product performance (Which products are performing best?)</li><li>Products > Categories (What are my best performing product categories?</li><li>Shopping cart > Carts (How many users added a product to cart?</li><li>Shopping cart > Cart views (How many times did my visitors view their carts?)</li><li>Shopping cart > Cart additions (How often are users adding a product to their cart?)</li><li>Shopping cart > Cart removals (How often are users removing a product from their cart?)</li><li>Purchases > Revenue (How is my revenue performing?)</li><li>Purchases > Orders (How are my orders performing?)</li><li>Purchases > Units (How many units am I selling?)</li><li>[Magento: marketing and commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** |<ul><li>People metric (How many people are interacting with my brand?)</li><li>Visitor profile > Location overview (Which locations are driving the most usage among users)</li><li>Visitor profile > Geosegmentation > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Which geographies are my users visiting from?)</li><li>Visitor profile > Languages (Which language do my users prefer?)</li><li>Visitor profile > Time zones (Which time zones are my users visiting from?)</li><li>Visitor profile > Domains (Which ISPs are my visitors using to access my site?)</li><li>Visitor profile > Top level domains (Which domains are driving traffic to my site?)</li><li>Visitor profile > Technology > Technology overview (What technologies are people using to access my site?)</li><li>Visitor profile > Technology > Browsers, Browser type, Browser width, Browser height (Which company's browser, browser version, and its width and height, are people using to access my site?)</li><li>Visitor profile > Technology > Operating system, Operating system types (Which OS and which version of it do my visitors use?)</li><li>Visitor profile > Technology > Mobile carrier (Which mobile carriers do my visitors use to access my site?)</li><li>Visitor retention > Return frequency (How much time passes between my user's current visit and previous visits?)</li><li>Visitor retention > Return visits (How many of my visits are returning users?)</li><li>Visitor retention > Visit number (Which visit number bucket drives most of my key metrics)</li><li>Visitor retention > Sales cycle > Customer loyalty (Which loyalty segment do my users belong to?)</li><li>Visitor retention > Sales cycle > Days before first purchase (How many days passed between my users' first visit and their first purchase?)</li><li>Visitor retention > Sales cycle > Days since last purchase (How many days have passed between my users' current visit and their last purchase? )</li><li>Visitor retention > Mobile > Devices and Device types (Which devices and device types are my visitors using?)</li><li>Visitor retention > Mobile > Manufacturer (Which mobile device manufacturer do my visitors use?)</li><li>Visitor retention > Mobile > Screen size, Screen height, Screen width (Which mobile screen size/height/width do my visitors have?)</li><li>Visitor retention > Mobile > [Mobile app usage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app journeys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app metrics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app messaging](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app performance](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app retention](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** |<ul><li>Marketing channels > First touch channel, First touch channel detail (Which first touch channel, and which specific first touch channel is performing best?)</li><li>Marketing channels > First last channel, First last channel detail (Which last touch channel, and which specific last touch channel is performing best?)</li><li>Campaigns > Campaigns (Which campaigns are driving my key metrics?)</li><li>Campaigns > Campaign performance (What campaigns are driving the most revenue?)</li><li>Campaigns > Tracking code (Which campaign tracking codes perform the best?)</li><li>[Web acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobile acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: paid search](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Search keywords - all, paid, natural (Which search keywords and paid/natural search keywords drive my key metrics the best?)</li><li>Search engines - all, paid, natural (Which search engines and paid/natural search engines drive my key metrics the best?)</li><li>All search page ranking (Which search page are my users visiting from?)</li><li>Referring domains (Which domains are driving traffic to my site?)</li><li>Original referring domains (What was the first domain users were on before visiting my site?)</li><li>Referrers (Which URLs were my users on before clicking through to my site?)</li><li>Referrer types (Which category do my referring URLs belong to?)</li></ul> |

-->
