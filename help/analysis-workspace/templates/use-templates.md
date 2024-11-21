---
description: Eine Übersicht über die Verwendung von Standardvorlagen in Analysis Workspace.
title: Verwenden von Vorlagen
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: 1345981ac78272935ffa8bfc50de8c41223a132f
workflow-type: tm+mt
source-wordcount: '15295'
ht-degree: 58%

---

# Verwenden von Vorlagen

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
>title="Identifizieren Sie die beliebtesten und unbeliebtesten Seiten."
>abstract="**Dies kann Ihnen helfen**, Ihre Zielgruppe und die Art von Informationen, die sie am meisten interessiert, besser zu verstehen.<br/>**Basierend auf dem, was Sie erfahren, können Sie** eine Reihe von Schritten ausführen, z. B. Seitenmetadaten anpassen, um die Sichtbarkeit auf seltener angezeigten Seiten zu erhöhen, oder Zeit in die Verbesserung des Inhalts Ihrer am häufigsten angezeigten Seiten investieren.<br/>Diese Vorlage verwendet die Dimension „Seite“ und die Metrik „Seitenansichten“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pageViewsOvertimeReport"
>title="Zeigen Sie die Gesamtanzahl der Seitenansichten an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. "
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit möglicherweise zu- oder abnimmt.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Sitetraffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Feiertags-Traffic.<br/>Diese Vorlage verwendet die Dimension „Tag“ und die Metrik „Seitenansichten“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitsOvertimeReport"
>title="Zeigen Sie die Gesamtanzahl der Besuche an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit möglicherweise zu- oder abnimmt.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Sitetraffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Feiertags-Traffic.<br/>Diese Vorlage verwendet die Dimension „Tag“ und die Metrik „Besuche“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitorsOvertimeReport"
>title="Zeigen Sie die Gesamtanzahl der Unique Visitors an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. "
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wie die Reichweite und die Zielgruppengröße Ihrer Site im Laufe der Zeit oder im Vergleich mit einem früheren Zeitraum zu- oder abnimmt.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob eine kürzlich gestartete Marketing-Kampagne erfolgreich darin war, neue Personen auf die Site zu locken, indem Sie Unique Visitors vor und nach dem Start der Kampagne vergleichen. Oder Sie können die Anzahl der Personen vergleichen, die die Site jedes Jahr während der Feiertage besuchen.<br/>Diese Vorlage verwendet die Dimension „Tag“ und die Metrik „Unique Visitors“. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--keyMetricsReport"
>title="Zeigen Sie einen Bericht an, der die Metriken „Seitenansichten“, „Besuche“ und „Unique Visitors“ nebeneinander anzeigt. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen helfen**, diese wichtigen Metriken zu vergleichen, um ein vollständigeres Bild über die Anzahl der Unique Visitors auf der Site, die Anzahl der Seitenbesuche und die Anzahl der Sitzungen zu erhalten.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die durchschnittliche Anzahl der Seiten bewerten, die jede Person während eines Besuchs auf der Site in einer bestimmten Woche oder in einem bestimmten Monat angesehen hat, und ermitteln, wie sich dies während bestimmter Zeiten des Jahres oder vor und nach der Durchführung von Marketing-Kampagnen verändert hat. <br/>Diese Vorlage verwendet die Dimension „Tag“, die Metrik „Seitenansichten“, die Metrik „Besuche“ und die Metrik „Unique Visitors“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--siteSectionRankedReport"
>title="Zeigen Sie die beliebtesten oder leistungsstärksten Bereiche Ihrer Site an."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Bereiche Ihrer Site am häufigsten besucht werden.<br>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, welche Ihrer Produkte oder Services das meiste Interesse generieren.<br/>Diese Vorlage verwendet die Dimension „Site-Bereich“ und die Metrik „Besuche“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--next-page-report"
>title="Sehen Sie sich die Bereiche an, die Personen am häufigsten direkt nach einem Besuch oder unmittelbar vor dem Besuch eines bestimmten Bereichs aufrufen."
>abstract="**Dies kann Ihnen dabei helfen**, zu verstehen, wie sich der Traffic von einer bestimmten Seite zu anderen Teilen Ihrer Site bewegt. Außerdem können Sie die Pfade verstehen, die Personen nehmen, um zu einer bestimmten Seite zu gelangen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob das Seiten-Design oder -Layout optimiert werden kann, um Personen zu wünschenswerteren Seiten zu leiten, z. B. zu einer Seite, auf der sie einen Kauf tätigen oder eine Rezension abgeben. Oder bewerten Sie, ob die Informationen auf der aktuellen Seite wahrscheinlich die Richtung oder die Aktionen angeben, nach denen Personen suchen, wenn sie von vorherigen Seiten kommen. Sie könnten auch bewerten, ob Seiten, die nicht als vorherige Seiten angezeigt werden, markantere Links zur aktuellen Seite benötigen.<br/>Diese Vorlage verwendet das Panel „Nächstes oder vorheriges Objekt“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignRankedReport"
>title="Zeigen Sie die Links an, die am erfolgreichsten Traffic auf Ihre Site geleitet haben."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Trackingcodes (und Links, mit denen sie verknüpft sind) am häufigsten beim Zugriff auf Ihre Site verwendet wurden.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Strategie anpassen, wo Sie Links zu Ihrer Site hinzufügen.<br/>Diese Vorlage verwendet die Dimension „Trackingcode“ und die Metrik „Besuche“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productsRankedReport"
>title="Zeigen Sie die Anzahl der Bestellungen nach Produkt an. Daten werden für einen bestimmten Zeitraum angezeigt."
>abstract="**Dies kann Ihnen helfen**, zu verstehen, welche Produkte die höchste oder die geringste Nachfrage aufweisen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Marketing-Strategien so anpassen, dass sie leistungsstarke Produkte bewerben oder Produkte mit schlechter Leistung verbessern oder einstellen. Sie könnten auch Ihren Produktbestand auf Grundlage Ihrer Datenanalyse anpassen.<br/>Diese Vorlage verwendet die Dimension „Produkt“ und die Metrik „Bestellungen“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelRankedReport"
>title="Zeigen Sie die neuesten Marketing-Kanäle an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen."
>abstract="**Dies kann Ihnen dabei helfen**, zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu leiten und um Konversionen zu erreichen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.<br/>Diese Vorlage verwendet die Dimension „Letztkontaktkanal“ und die Metrik „Unique Visitors“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelDetailRankedReport"
>title="Zeigen Sie Details zu den neuesten Marketing-Kanälen an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen."
>abstract="**Dies kann Ihnen dabei helfen**, nicht nur zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu leiten und Konversionen zu erreichen, sondern Sie erhalten auch Details zu diesen Marketing-Kanälen. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.<br/>Diese Vorlage verwendet die Dimension „Details des Letztkontaktkanals“ und die Metrik „Unique Visitors“. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--revenueOvertimeReport"
>title="Zeigen Sie den Geldbetrag der bei allen Bestellungen gekauften Produkte an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen helfen**, zu verstehen, wie der Umsatz im Laufe der Zeit zu- oder abnimmt. Sie können diese Metrik mit einer beliebigen Dimension kombinieren, um zu erfahren, welche Dimensionselemente zum Umsatz beigetragen haben. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. zukünftige Umsätze basierend auf früheren Trends planen. Sie können auch eine weitere Dimension hinzufügen, z. B. die Dimension „Trackingcode“, um zu erfahren, welche Kampagnen den meisten Umsatz generieren.<br/>Diese Vorlage verwendet die Dimension „Tag“ und die Metrik „Umsatz“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ordersOvertimeReport"
>title="Zeigen Sie die Gesamtanzahl der Kaufereignisse an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wie das Interesse an Ihren Produkten und Services im Laufe der Zeit zu- oder abnimmt. Sie können ein Segment anwenden, um zu erfahren, welche Kundinnen und Kunden oder Regionen die meisten Bestellungen aufgeben und wie der Trend bei diesen Bestellungen im Laufe der Zeit aussieht.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne durch den Vergleich der Bestellungen vor und nach dem Start der Kampagne bewerten. Oder Sie vergleichen die jährlichen Bestellungen zu Feiertagen.<br/>Diese Vorlage verwendet die Dimension „Tag“ und die Metrik „Bestellungen“."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Tutorial für Schulungen**] | Erfahren Sie mehr über die gängige Terminologie und die Schritte zur Erstellung Ihrer ersten Analyse in Analysis Workspace. |
| [!UICONTROL **Seiten**] | <!--duplicated in Engagement section--> Identifizieren Sie die beliebtesten und unbeliebtesten Seiten. <p>**Dies kann Ihnen helfen**, Ihre Zielgruppe und die Art von Informationen, die sie am meisten interessiert, besser zu verstehen.</p><p>**Basierend auf dem, was Sie erfahren, können Sie** eine Reihe von Schritten ausführen, z. B. Seitenmetadaten anpassen, um die Sichtbarkeit auf seltener angezeigten Seiten zu erhöhen, oder Zeit in die Verbesserung des Inhalts Ihrer am häufigsten angezeigten Seiten investieren.</p><p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Seitenansichten**] | <!--duplicated in Engagement section--> Zeigen Sie die Gesamtanzahl der Seitenansichten an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit möglicherweise zu- oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Sitetraffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Feiertags-Traffic.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Webbesuche**] | <!--duplicated in Engagement section--> Zeigen Sie die Gesamtanzahl der Besuche an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit möglicherweise zu- oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Sitetraffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Feiertags-Traffic.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Besuche .</p> |
| [!UICONTROL **Webbesucher**] | <!--duplicated in Engagement section--> Zeigen Sie die Gesamtanzahl der Unique Visitors an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie die Reichweite und die Zielgruppengröße Ihrer Site im Laufe der Zeit oder im Vergleich mit einem früheren Zeitraum zu- oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob eine kürzlich gestartete Marketing-Kampagne erfolgreich darin war, neue Personen auf die Site zu locken, indem Sie Unique Visitors vor und nach dem Start der Kampagne vergleichen. Oder Sie können die Anzahl der Personen vergleichen, die die Site jedes Jahr während der Feiertage besuchen.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Schlüsselmetriken**] | <!--duplicated in Engagement section--> Zeigen Sie einen Bericht an, der die Metriken „Seitenansichten“, „Besuche“ und „Unique Visitors“ nebeneinander anzeigt. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, diese wichtigen Metriken zu vergleichen, um ein vollständigeres Bild über die Anzahl der Unique Visitors auf der Site, die Anzahl der Seitenbesuche und die Anzahl der Sitzungen zu erhalten.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die durchschnittliche Anzahl der Seiten, die jeder Besucher während eines Besuchs auf der Site in einer bestimmten Woche oder in einem bestimmten Monat angesehen hat, und wie sich dies während bestimmter Zeiten des Jahres oder vor und nach der Ausführung von Marketingkampagnen verändert hat. </p><p>Diese Vorlage verwendet die Dimension Tag , die Metrik Seitenansichten , die Metrik Besuche und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Sitebereiche**] | Zeigen Sie die beliebtesten oder leistungsstärksten Bereiche Ihrer Site an. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Bereiche Ihrer Site am häufigsten besucht werden.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, welche Ihrer Produkte oder Services das meiste Interesse generieren.</p> <p>Diese Vorlage verwendet die Dimension Sitebereich und die Metrik Besuche .</p> |
| [!UICONTROL **Nächste und vorherige Seite**] | Sehen Sie sich die Bereiche an, die Personen am häufigsten direkt nach einem Besuch oder unmittelbar vor dem Besuch eines bestimmten Bereichs aufrufen. <p>**Dies kann Ihnen dabei helfen**, zu verstehen, wie sich der Traffic von einer bestimmten Seite zu anderen Teilen Ihrer Site bewegt. Außerdem können Sie die Pfade verstehen, die Personen nehmen, um zu einer bestimmten Seite zu gelangen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob das Seiten-Design oder -Layout optimiert werden kann, um Personen zu wünschenswerteren Seiten zu leiten, z. B. zu einer Seite, auf der sie einen Kauf tätigen oder eine Rezension abgeben. Oder bewerten Sie, ob die Informationen auf der aktuellen Seite wahrscheinlich die Richtung oder die Aktionen angeben, nach denen Personen suchen, wenn sie von vorherigen Seiten kommen. Sie könnten auch bewerten, ob Seiten, die nicht als vorherige Seiten angezeigt werden, markantere Links zur aktuellen Seite benötigen.</p><p>Diese Vorlage verwendet das Bedienfeld Nächstes oder vorheriges Element .</p> |
| [!UICONTROL **Kampagnen (Trackingcode)**] | Zeigen Sie die Links an, die am erfolgreichsten Traffic auf Ihre Site geleitet haben. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Trackingcodes (und Links, mit denen sie verknüpft sind) am häufigsten beim Zugriff auf Ihre Site verwendet wurden.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Strategie anpassen, wo Sie Links zu Ihrer Site hinzufügen.</p><p>Diese Vorlage verwendet die Dimension Trackingcode und die Metrik Besuche .</p> |
| [!UICONTROL **Produkte**] | Zeigen Sie die Anzahl der Bestellungen nach Produkt an. Daten werden für einen bestimmten Zeitraum angezeigt. <p>**Dies kann Ihnen helfen**, zu verstehen, welche Produkte die höchste oder die geringste Nachfrage aufweisen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Marketing-Strategien so anpassen, dass sie leistungsstarke Produkte bewerben oder Produkte mit schlechter Leistung verbessern oder einstellen. Sie könnten auch Ihren Produktbestand auf Grundlage Ihrer Datenanalyse anpassen.</p><p>Diese Vorlage verwendet die Dimension Produkt und die Metrik Bestellungen .</p> |
| [!UICONTROL **Letztkontakt Marketingkanal**] | Zeigen Sie die neuesten Marketing-Kanäle an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen.<p>**Dies kann Ihnen dabei helfen**, zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu leiten und um Konversionen zu erreichen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.</p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanal und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Letztkontakt Marketingkanaldetail**] | Zeigen Sie Details zu den neuesten Marketing-Kanälen an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen.<p>**Dies kann Ihnen dabei helfen**, nicht nur zu verstehen, welche Marketing-Kanäle am effektivsten waren, um Personen zu Ihrer Site zu leiten und Konversionen zu erreichen, sondern Sie erhalten auch Details zu diesen Marketing-Kanälen. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. mehr Ressourcen für leistungsstarke Kanäle oder weniger Ressourcen für leistungsschwache Kanäle zuweisen.</p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanaldetail und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Umsatz**] | <!--duplicated in Web Conversion section-->Zeigen Sie den Geldbetrag der bei allen Bestellungen gekauften Produkte an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen.<p>**Dies kann Ihnen helfen**, zu verstehen, wie der Umsatz im Laufe der Zeit zu- oder abnimmt. Sie können diese Metrik mit einer beliebigen Dimension kombinieren, um zu erfahren, welche Dimensionselemente zum Umsatz beigetragen haben. </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. zukünftige Umsätze basierend auf früheren Trends planen. Sie können auch eine weitere Dimension hinzufügen, z. B. die Dimension „Trackingcode“, um zu erfahren, welche Kampagnen den meisten Umsatz generieren.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Umsatz .</p> |
| [!UICONTROL **Bestellungen**] | <!--duplicated in Web Conversion section-->Zeigen Sie die Gesamtanzahl der Kaufereignisse an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie das Interesse an Ihren Produkten und Services im Laufe der Zeit zu- oder abnimmt. Sie können ein Segment anwenden, um zu erfahren, welche Kundinnen und Kunden oder Regionen die meisten Bestellungen aufgeben und wie der Trend bei diesen Bestellungen im Laufe der Zeit aussieht.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne durch den Vergleich der Bestellungen vor und nach dem Start der Kampagne bewerten. Oder Sie vergleichen die jährlichen Bestellungen zu Feiertagen.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Bestellungen .</p> |

### Web: Interaktion {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Zeigen Sie die durchschnittliche Besuchszeit auf Ihrer Site während jedes Besuchs sowie die durchschnittliche Besuchszeit vor einem Erfolgsereignis an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen."
>abstract="**Dies kann Ihnen helfen**, die Interaktionsstufen der Besuchenden besser zu verstehen und herauszufinden, wie viel Zeit Besuchende benötigen, um eine gewünschte Aktion durchzuführen, z. B. einen Kauf.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob Änderungen an Ihrer Site es den Besuchenden erleichtert, schnell ein Erfolgsereignis zu erreichen.<br/>Diese Vorlage verwendet die Dimension „Tag“, die Metrik „Pro Besuch aufgewendete Zeit (Sekunden)“, die Dimension „Tag“ und die Metrik „Pro Besuch aufgewendete Zeit (Sekunden)“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-content-consumption"
>title="Zeigen Sie an, welche Web-Inhalte am häufigsten genutzt werden und für Benutzende interessant sind."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wo Personen beim ersten Aufrufen der Site hingehen, welche Bereiche der Site von Personen am häufigsten besucht werden und welche Seiten Personen am wahrscheinlichsten von der Site wegführen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, welche Pfade auf der Site Personen zu den wichtigsten Seiten führen und welche Seiten Personen wahrscheinlicher von der Site wegführen.<br/>Diese Vorlage verwendet die Dimension „Seite“ und die Metrik „Seitenansichten“, die Metrik „Besuche“, die Metrik „Unique Visitors“, die Metrik „Eintrittsrate“, die Metrik „Bounce-Rate“, die Metrik „Ausstiegsrate“ und die Metrik „Contentgeschwindigkeit“. Außerdem werden Flussvisualisierungen für Eintritts-, Ausstiegs- und Top-Abschnitte verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--media-content-consumption"
>title="Zeigen Sie an, welche Medieninhalte am häufigsten genutzt werden und für Benutzende interessant sind."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wo Personen beim ersten Aufrufen der Site hingehen, welche Bereiche der Site von Personen am häufigsten besucht werden und welche Seiten Personen am wahrscheinlichsten von der Site wegführen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, welche Pfade auf der Site Personen zu den wichtigsten Seiten führen und welche Seiten Personen wahrscheinlicher von der Site wegführen.<br/>Diese Vorlage verwendet die Dimension „Seite“ und die Metrik „Seitenansichten“, die Metrik „Besuche“, die Metrik „Unique Visitors“, die Metrik „Eintrittsrate“, die Metrik „Bounce-Rate“, die Metrik „Ausstiegsrate“ und die Metrik „Contentgeschwindigkeit“. Darüber hinaus werden Flussvisualisierungen für Eintritt-, Ausstiegs- und Top-Abschnitte verwendet. Eine Scatterplot-Visualisierung zeigt die Seitenansichten für die gängigsten Seiten an. Eine Balkenvisualisierung zeigt die Seitenansichten nach zusammengefasster Zeit an. Eine Linienvisualisierung stellt eine Trend-Ansicht der durchschnittlichen Besuchszeit auf der Site dar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--page-summary-report"
>title="Zeigen Sie wichtige Informationen zu einer Seite in Ihren Eigenschaften an. Zeigt Seitenansichten, eine Trend-Linie, eine Flussvisualisierung und mehr an."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, wie Personen mit einer bestimmten Seite interagieren.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Leistung der Seite über einen bestimmten Zeitraum analysieren oder besser verstehen, was den Traffic zur Seite bringt.<br/>Diese Vorlage verwendet die Metrik „Seitenansichten“. Außerdem werden die Linienvisualisierung und die Flussvisualisierung verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--entryPageRankedReport"
>title="Zeigen Sie die wichtigsten Seiten an, auf die Personen beim ersten Besuch Ihrer Site zugreifen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Seiten den meisten Traffic zu Ihrer Site leiten, oder mehr über die ersten Eindrücke zu erfahren, die Besuchende auf Ihrer Site haben.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. das erste Erlebnis optimieren, das Personen auf der Site haben, oder sicherstellen, dass die Seiten, die Personen beim Eintritt in Ihre Site zuerst sehen, einladend sind und die erforderlichen Links zu anderen Bereichen Ihrer Site bereitstellen.<br/>Diese Vorlage verwendet die Metrik „Sitzungen“. Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--exitPageRankedReport"
>title="Zeigen Sie die wichtigsten Seiten an, auf die Personen unmittelbar vor dem Verlassen Ihrer Site zugreifen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Seiten Personen von der Site wegführen. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. gängige Exitpages aktualisieren, um das Erlebnis zu optimieren, das Personen vor dem Verlassen haben, oder Inhalte oder Links aufnehmen, um Personen dazu aufzufordern, auf Ihrer Site zu bleiben.<br/>Diese Vorlage verwendet die Metrik „Sitzungen“. Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Schlüsselmetriken**] | <!--duplicated in Most popular section--> Zeigen Sie einen Bericht an, der die Metriken „Seitenansichten“, „Besuche“ und „Unique Visitors“ nebeneinander anzeigt. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, diese wichtigen Metriken zu vergleichen, um ein vollständigeres Bild über die Anzahl der Unique Visitors auf der Site, die Anzahl der Seitenbesuche und die Anzahl der Sitzungen zu erhalten.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die durchschnittliche Anzahl der Seiten, die jeder Besucher während eines Besuchs auf der Site in einer bestimmten Woche oder in einem bestimmten Monat angesehen hat, und wie sich dies während bestimmter Zeiten des Jahres oder vor und nach der Ausführung von Marketingkampagnen verändert hat. </p><p>Diese Vorlage verwendet die Dimension Tag , die Metrik Seitenansichten , die Metrik Besuche und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Seitenansichten**] | <!--duplicated in Most popular section-->Zeigen Sie die Gesamtanzahl der Seitenansichten an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit möglicherweise zu- oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Sitetraffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Feiertags-Traffic.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Seiten**] | <!--duplicated in Most popular section-->Identifizieren Sie die beliebtesten und unbeliebtesten Seiten. <p>**Dies kann Ihnen helfen**, Ihre Zielgruppe und die Art von Informationen, die sie am meisten interessiert, besser zu verstehen.</p><p>**Basierend auf dem, was Sie erfahren, können Sie** eine Reihe von Schritten ausführen, z. B. Seitenmetadaten anpassen, um die Sichtbarkeit auf seltener angezeigten Seiten zu erhöhen, oder Zeit in die Verbesserung des Inhalts Ihrer am häufigsten angezeigten Seiten investieren.</p><p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten .</p> |
| [!UICONTROL **Besuche**] | <!--duplicated in Most popular section-->Zeigen Sie die Gesamtanzahl der Besuche an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie der Traffic auf Ihrer Site im Laufe der Zeit möglicherweise zu- oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität einer kürzlich gestarteten Marketing-Kampagne bewerten, indem Sie den Sitetraffic vor und nach dem Start der Kampagne vergleichen. Oder Sie vergleichen den jährlichen Feiertags-Traffic.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Besuche .</p> |
| [!UICONTROL **Besucher**] | <!--duplicated in Most popular section-->Zeigen Sie die Gesamtanzahl der Unique Visitors an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie die Reichweite und die Zielgruppengröße Ihrer Site im Laufe der Zeit oder im Vergleich mit einem früheren Zeitraum zu- oder abnimmt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob eine kürzlich gestartete Marketing-Kampagne erfolgreich darin war, neue Personen auf die Site zu locken, indem Sie Unique Visitors vor und nach dem Start der Kampagne vergleichen. Oder Sie können die Anzahl der Personen vergleichen, die die Site jedes Jahr während der Feiertage besuchen.</p><p>Diese Vorlage verwendet die Dimension Tag und die Metrik Unique Visitors .</p> |
| [!UICONTROL **Besuchszeit**] | Zeigen Sie die durchschnittliche Besuchszeit auf Ihrer Site während jedes Besuchs sowie die durchschnittliche Besuchszeit vor einem Erfolgsereignis an. Die Daten werden für einen bestimmten Zeitraum angezeigt und mit früheren Zeiträumen verglichen. <p>**Dies kann Ihnen helfen**, die Interaktionsstufen der Besuchenden besser zu verstehen und herauszufinden, wie viel Zeit Besuchende benötigen, um eine gewünschte Aktion durchzuführen, z. B. einen Kauf.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, ob Änderungen an Ihrer Site es den Besuchenden erleichtert, schnell ein Erfolgsereignis zu erreichen.</p><p>Diese Vorlage verwendet die Dimension Tag , die Metrik Zeit pro Besuch (Sekunden) , die Dimension Tag und die Metrik Zeit pro Besuch (Sekunden) .</p> |
| [!UICONTROL **Sitebereiche**] | <!--duplicated in Most popular section-->Zeigen Sie die beliebtesten oder leistungsstärksten Bereiche Ihrer Site an. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Bereiche Ihrer Site am häufigsten besucht werden.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. bewerten, welche Ihrer Produkte oder Services das meiste Interesse generieren.</p> <p>Diese Vorlage verwendet die Dimension Sitebereich und die Metrik Besuche .</p> |
| [!UICONTROL **Nutzung von Webinhalten**] | Zeigen Sie an, welche Web-Inhalte am häufigsten genutzt werden und für Benutzende interessant sind.<p>**Dies kann Ihnen helfen**, besser zu verstehen, wo Personen beim ersten Aufrufen der Site hingehen, welche Bereiche der Site von Personen am häufigsten besucht werden und welche Seiten Personen am wahrscheinlichsten von der Site wegführen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. feststellen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site wegführen <!-- not sure about these takeaways... -->.</p> <p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Außerdem werden Flussvisualisierungen für Eintritts-, Ausstiegs- und Top-Abschnitte verwendet.</p> |
| [!UICONTROL **Verbrauch von Medieninhalten**] | Zeigen Sie an, welche Medieninhalte am häufigsten genutzt werden und für Benutzende interessant sind.<p>**Dies kann Ihnen helfen**, besser zu verstehen, wo Personen beim ersten Aufrufen der Site hingehen, welche Bereiche der Site von Personen am häufigsten besucht werden und welche Seiten Personen am wahrscheinlichsten von der Site wegführen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. feststellen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site wegführen <!-- not sure about these takeaways... -->.</p> <p>Diese Vorlage verwendet die Dimension Seite und die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Darüber hinaus werden Flussvisualisierungen für Eintritt-, Ausstiegs- und Top-Abschnitte verwendet. Eine Scatterplot-Visualisierung zeigt die Seitenansichten für die gängigsten Seiten an. Eine Balkenvisualisierung zeigt die Seitenansichten nach zusammengefasster Zeit an. Eine Linienvisualisierung stellt eine Trend-Ansicht der durchschnittlichen Besuchszeit auf der Site dar.</p> |
| [!UICONTROL **Nächste und vorherige Seite**] | <!--duplicated in Most popular section-->Sehen Sie sich die häufigsten Orte an, an denen Besucher vor oder nach dem Besuch eines bestimmten Ortes reisen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wo Personen beim ersten Einstieg in die Site hineinnavigieren, welche Bereiche der Site von den Besuchern am häufigsten besucht werden und welche Seiten am ehesten besucht werden, bevor sie die Site verlassen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. feststellen, welche Pfade auf der Site Menschen zu den wichtigsten Seiten führen und welche Seiten die Besucher wahrscheinlicher von der Site weg führen.<!-- not sure about these takeaways... --></p> <p>Diese Vorlage verwendet die Dimension Seite , die Metrik Seitenansichten , die Metrik Besuche , die Metrik Unique Visitors , die Metrik Einstiegsrate , die Metrik Absprungrate , die Metrik Ausstiegsrate und die Metrik Content-Geschwindigkeit . Darüber hinaus werden Flussvisualisierungen für Einstiegs-, Ausstiegs- und oberste Abschnitte, eine Streudiagrammdarstellung mit Seitenansichten für die häufigsten Seiten, eine Balkenvisualisierung, die Seitenansichten nach Zusammenfassungszeit anzeigt, und eine Linienvisualisierung verwendet, die eine Trendansicht der durchschnittlichen Besuchszeit auf der Site anzeigt.</p> |
| **Seitenzusammenfassung** | Zeigen Sie wichtige Informationen zu einer Seite in Ihren Eigenschaften an. Zeigt Seitenansichten, eine Trend-Linie, eine Flussvisualisierung und mehr an.  <p>**Dies kann Ihnen helfen**, besser zu verstehen, wie Personen mit einer bestimmten Seite interagieren.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Leistung der Seite über einen bestimmten Zeitraum analysieren oder besser verstehen, was den Traffic zur Seite bringt.</p><p>Diese Vorlage verwendet die Metrik Seitenansichten . Außerdem werden die Linienvisualisierung und die Flussvisualisierung verwendet.</p> |
| **Entrypages** | Zeigen Sie die wichtigsten Seiten an, auf die Personen beim ersten Besuch Ihrer Site zugreifen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Seiten den meisten Traffic zu Ihrer Site leiten, oder mehr über die ersten Eindrücke zu erfahren, die Besuchende auf Ihrer Site haben.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. das erste Erlebnis optimieren, das Personen auf der Site haben, oder sicherstellen, dass die Seiten, die Personen beim Eintritt in Ihre Site zuerst sehen, einladend sind und die erforderlichen Links zu anderen Bereichen Ihrer Site bereitstellen.</p><p>Diese Vorlage verwendet die Metrik Sitzungen . Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet.</p> |
| **Exitpages** | Zeigen Sie die wichtigsten Seiten an, auf die Personen unmittelbar vor dem Verlassen Ihrer Site zugreifen.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Seiten Personen von der Site wegführen. </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. gängige Exitpages aktualisieren, um das Erlebnis zu optimieren, das Personen vor dem Verlassen haben, oder Inhalte oder Links aufnehmen, um Personen dazu aufzufordern, auf Ihrer Site zu bleiben.</p><p>Diese Vorlage verwendet die Metrik Sitzungen . Außerdem werden die Balkenvisualisierung und die Freiformtabellen-Visualisierung verwendet.</p> |

### Web: Konversion {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productConversionReport"
>title="Vorlage für Produkt-Konversionstrichter"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-products-template"
>title="Zeigen Sie die Produkte mit der höchsten Leistung."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Produkte am erfolgreichsten sind.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Finanzierung für erfolgreiche Produkte erhöhen und für weniger erfolgreiche Produkte verringern.<br/>Diese Vorlage verwendet die Metriken „Produktansichten“, „Zusatz zum Warenkorb“, „Bestellungen“, „Umsatz“ und „Einheiten“. Außerdem wird die Dimension „Produkt“ verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartConversionReport"
>title="Sehen Sie sich an, wie oft Personen wichtige Checkout-Ereignisse ausgeführt haben, z. B. Hinzufügen von Artikeln zum Warenkorb, Anzeigen des Warenkorbs, Entfernen von Artikeln aus dem Warenkorb und Checkout-Vorgänge."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Teile des Checkout-Prozess-Trichters zu einer Konversion führen und welche eher zum Warenkorbabbruch führen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Reibung bei bestimmten Schritten des Checkout-Prozesses reduzieren.<br/>Diese Vorlage verwendet die"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartsOvertimeReport"
>title="Zeigen Sie die Anzahl der Personen an, die ein Produkt zum Warenkorb hinzugefügt haben."
>abstract="**Dies kann Ihnen dabei helfen**, die Anzahl der Personen besser zu verstehen, die ein Produkt zum Warenkorb hinzufügen, im Gegensatz zur Gesamtzahl der Produkte, die zum Warenkorb hinzugefügt werden.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität Ihrer Produktseiten messen.<br/>Diese Vorlage verwendet die Metrik „Warenkörbe“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartViewsOvertimeReport"
>title="Zeigen Sie an, wie oft Personen ihren Warenkorb angezeigt haben."
>abstract="**Dies kann Ihnen dabei helfen**, das Checkout-Erlebnis besser zu verstehen, um die Warenkorbabbruch-Raten zu reduzieren oder die Zeit zwischen Warenkorbergänzungen und Checkouts für verschiedene Produkte zu analysieren.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Aktionen für Produkte anbieten, die am längsten im Warenkorb bleiben und das größte Risiko für einen Abbruch aufweisen.<br/>Diese Vorlage verwendet die Metrik „Warenkorbansichten“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartAdditionsOvertimeReport"
>title="Zeigen Sie an, wie häufig Personen etwas zum Warenkorb hinzugefügt haben."
>abstract="**Dies kann Ihnen helfen**, den Teil des Konversionstrichters besser zu verstehen, in dem das Kundeninteresse an einem Produkt so hoch ist, dass es zum Warenkorb hinzugefügt wird.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Produktempfehlungen für alle Kundinnen und Kunden verbessern. Dazu können Sie analysieren, welche Produkte häufig demselben Warenkorb hinzugefügt werden, und ähnliche Produkte auf der Grundlage von Artikeln vorschlagen, die bereits im Warenkorb enthalten sind."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartRemovalsOvertimeReport"
>title="Zeigen Sie an, wie oft Personen etwas aus dem Warenkorb entfernt haben."
>abstract="**Dies kann Ihnen dabei helfen**, den Teil des Konversionstrichters besser zu verstehen, in dem Kundschaft kein Interesse mehr an einem Produkt hat, oder zu verstehen, wo im Checkout-Prozess möglicherweise Probleme auftreten.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. potenzielle Barrieren beseitigen, die im Checkout-Prozess bestehen könnten, wie ein kompliziertes Kundenerlebnis.<br/>Diese Vorlage verwendet die Metrik „Entnahmen aus Warenkorb“."

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
| **Produkte** | Zeigen Sie an, auf welche Produkte Schlüsselmetriken wie Topverkäufe oder am häufigsten angezeigte Produkte verweisen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Produkte am erfolgreichsten sind.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Finanzierung für erfolgreiche Produkte erhöhen und für weniger erfolgreiche Produkte verringern.</p><p>Diese Vorlage verwendet die Metrik Bestellungen und die Dimension Produkt . |
| **Produktleistung** | Zeigen Sie die Produkte mit der höchsten Leistung.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Produkte am erfolgreichsten sind.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Finanzierung für erfolgreiche Produkte erhöhen und für weniger erfolgreiche Produkte verringern.</p><p>Diese Vorlage verwendet die Metriken Produktansichten, Zusatz zum Warenkorb, Bestellungen, Umsatz und Einheiten . Außerdem wird die Dimension „Produkt“ verwendet. |
| **Umrechnungstrichter für Warenkorb** | Sehen Sie sich an, wie oft Personen wichtige Checkout-Ereignisse ausgeführt haben, z. B. Hinzufügen von Artikeln zum Warenkorb, Anzeigen des Warenkorbs, Entfernen von Artikeln aus dem Warenkorb und Checkout-Vorgänge. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Teile des Checkout-Prozess-Trichters zu einer Konversion führen und welche eher zum Warenkorbabbruch führen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Reibung bei bestimmten Schritten des Checkout-Prozesses reduzieren.</p><p>Diese Vorlage verwendet die |
| **Warenkorb** | Zeigen Sie die Anzahl der Personen an, die ein Produkt zum Warenkorb hinzugefügt haben.<p>**Dies kann Ihnen dabei helfen**, die Anzahl der Personen besser zu verstehen, die ein Produkt zum Warenkorb hinzufügen, im Gegensatz zur Gesamtzahl der Produkte, die zum Warenkorb hinzugefügt werden.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Effektivität Ihrer Produktseiten messen.</p><p>Diese Vorlage verwendet die Metrik Warenkorb . |
| **Warenkorbansicht** | Zeigen Sie an, wie oft Personen ihren Warenkorb angezeigt haben. <p>**Dies kann Ihnen dabei helfen**, das Checkout-Erlebnis besser zu verstehen, um die Warenkorbabbruch-Raten zu reduzieren oder die Zeit zwischen Warenkorbergänzungen und Checkouts für verschiedene Produkte zu analysieren.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Aktionen für Produkte anbieten, die am längsten im Warenkorb bleiben und das größte Risiko für einen Abbruch aufweisen.</p><p>Diese Vorlage verwendet die Metrik Warenkorbansichten . |
| **Zusatz zum Warenkorb** | Zeigen Sie an, wie häufig Personen etwas zum Warenkorb hinzugefügt haben. <p>**Dies kann Ihnen helfen**, den Teil des Konversionstrichters besser zu verstehen, in dem das Kundeninteresse an einem Produkt so hoch ist, dass es zum Warenkorb hinzugefügt wird.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Produktempfehlungen für alle Kundinnen und Kunden verbessern. Dazu können Sie analysieren, welche Produkte häufig demselben Warenkorb hinzugefügt werden, und ähnliche Produkte auf der Grundlage von Artikeln vorschlagen, die bereits im Warenkorb enthalten sind. |
| **Entnahme aus Warenkorb** | Zeigen Sie an, wie oft Personen etwas aus dem Warenkorb entfernt haben.<p>**Dies kann Ihnen dabei helfen**, den Teil des Konversionstrichters besser zu verstehen, in dem Kundschaft kein Interesse mehr an einem Produkt hat, oder zu verstehen, wo im Checkout-Prozess möglicherweise Probleme auftreten.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. potenzielle Barrieren beseitigen, die im Checkout-Prozess bestehen könnten, wie ein kompliziertes Kundenerlebnis.</p><p>Diese Vorlage verwendet die Metrik Entnahme aus Warenkorb . |
| **Einkaufskonversionstrichter** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Umsatz** | <!--duplicated in Most popular section-->Zeigen Sie den Geldbetrag der bei allen Bestellungen gekauften Produkte an.<p>**Dies kann Ihnen** dabei helfen, besser zu verstehen, welche Dimensionselemente zum Umsatz beigetragen haben, indem die Umsatzmetrik mit einer beliebigen Dimension kombiniert wird. Sie könnten beispielsweise die Top-Kampagnen (unter Verwendung der Dimension Trackingcode ) sehen, die zum Umsatz beigetragen haben. </p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Kampagnen anpassen, die nicht den erwarteten Umsatzzielen entsprechen.</p><p>Diese Vorlage verwendet die Umsatzmetrik. |
| **Bestellungen** | <!--duplicated in Most popular section-->Anzeigen der Gesamtzahl der Kaufereignisse auf Ihrer Site. <p>**Dies kann Ihnen** dabei helfen, besser zu verstehen, welche Dimensionselemente zu einer Bestellung beigetragen haben, indem die Metrik &quot;Bestellungen&quot;mit einer beliebigen Dimension kombiniert wird. Sie könnten beispielsweise die Top-Kampagnen (unter Verwendung der Dimension Trackingcode ) sehen, die zu Käufen beigetragen haben.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Kampagnen anpassen, die nicht den erwarteten Einkaufszielen entsprechen. </p><p>Diese Vorlage verwendet die Metrik Bestellungen . |

### Web: Zielgruppe {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Zeigen Sie das Land an, aus dem die Personen stammen, die Ihre Site besuchen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Ländern die meisten Personen stammen, die Ihre Site besuchen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Daten nutzen, um sich auf Marketing-Maßnahmen in diesen Ländern zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Ländern mit unterschiedlichen Hauptsprachen optimal ist.<br/>Diese Vorlage verwendet die Dimension „Länder“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Zeigen Sie den Bundesstaat (in den USA) an, aus dem die Personen stammen, die Ihre Site besuchen. Diese Vorlage ähnelt der Vorlage für geografische Regionen, allerdings ist sie spezifisch für die USA. "
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen US-Bundesstaaten die meisten Personen stammen, die Ihre Site besuchen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Bundesstaaten zu konzentrieren.<br/>Diese Vorlage verwendet die Dimension „USA“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Zeigen Sie die geografische Region an, aus der die Personen stammen, die Ihre Site besuchen. Eine Region ist ein geografischer Bereich, der kleiner als ein Land, jedoch größer als eine Stadt ist. In einigen Ländern ist eine Region ein Bundesland, eine Provinz oder eine Präfektur. In anderen Gebieten handelt es sich um einen Landesteil, ein Departement oder eine großstädtische Region. "
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Regionen die meisten Personen stammen, die Ihre Site besuchen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Daten nutzen, um sich auf Marketing-Maßnahmen in diesen Regionen zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Regionen mit unterschiedlichen Hauptsprachen optimal ist. <br/>Diese Vorlage verwendet die Dimensionen „ID(variables/geocountry)“ und „Regionen“. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Zeigen Sie die Stadt an, aus der die Personen stammen, die Ihre Site besuchen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Städten die meisten Personen stammen, die Ihre Site besuchen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Städten zu konzentrieren. <br/>Diese Vorlage verwendet die Dimension „Städte“"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Zeigen Sie die designierten Marketing-Gebiete (DMAs) in den USA an, aus denen die Personen stammen, die Ihre Site besuchen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Regionen die meisten Personen stammen, die Ihre Site besuchen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in der erfolgreichsten Regionen zu konzentrieren. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Zeigen Sie die häufigsten Sprachen an, in denen die Besuchenden den Inhalt anzeigen."
>abstract="**Dies kann Ihnen dabei helfen**, die am häufigsten bevorzugten Sprachen der Besuchenden besser zu verstehen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Lokalisierungs- oder Marketing-Maßnahmen auf die beliebtesten Sprachen konzentrieren.<br/>Diese Vorlage verwendet die Dimension „Sprache“."

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
>abstract="**Dies kann Ihnen dabei helfen**, die gängigsten Browser, die beim Besuch verwendet werden, besser zu verstehen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Site-Qualität durch Testen neuer Versionen Ihrer Site mit den wichtigsten Browsern verbessern. Auf diese Weise können die Maßnahmen zur Qualitätssicherung maximiert werden.<br/>Diese Vorlage verwendet die Dimension „Browser“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Zeigen Sie die Namen der Organisationen an, die die wichtigsten Browser erstellt haben, mit denen Personen auf Ihre Site zugreifen. Diese Vorlage unterscheidet sich insofern von der Vorlage „Browser“, als sie verschiedene Versionen desselben Browsers nicht als separate Dimensionselemente auflistet."
>abstract="**Dies kann Ihnen dabei helfen**, die gängigsten Browser, die Besuchende verwenden, besser zu verstehen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Site-Qualität verbessern, indem Sie neue Versionen Ihrer Site mit den wichtigsten Browsern testen. Auf diese Weise können die Maßnahmen zur Qualitätssicherung maximiert werden. <br/>Diese Vorlage verwendet die Dimension „Browsertyp“. "

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Erste und Wiederholte Benutzer**] | Vergleich von erstmaligen Besuchern mit wiederkehrenden Besuchern anzeigen. <p>**Dies kann Ihnen** helfen, die Effektivität Ihrer Site bei der Aufrechterhaltung der Kundenloyalität oder die Rate, mit der Sie neue Kunden gewinnen, besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Anreize für zukünftige Käufe an erstmalige Besucher, um sie zur Rückkehr zu bewegen.</p><!-- This template uses the --> |
| **Personen-ID/Namespace** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><!-- This template uses the --> |
| **Standortübersicht** | Zeigen Sie eine Übersicht über die Besucherposition in einer Zuordnungsvisualisierung an.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wo sich Besucher befinden, die Ihre Site besuchen. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Ressourcen an den Orten konzentrieren, an denen Sie das größte Interesse und die beste Gelegenheit sehen.</p><!-- This template uses the --> |
| **Geo Countries** | Zeigen Sie das Land an, aus dem die Personen stammen, die Ihre Site besuchen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Ländern die meisten Personen stammen, die Ihre Site besuchen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Daten nutzen, um sich auf Marketing-Maßnahmen in diesen Ländern zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Ländern mit unterschiedlichen Hauptsprachen optimal ist.</p><p>Diese Vorlage verwendet die Dimension Länder . </p> |
| **US-Bundesstaaten** | Zeigen Sie den Bundesstaat (in den USA) an, aus dem die Personen stammen, die Ihre Site besuchen. Diese Vorlage ähnelt der Vorlage für geografische Regionen, allerdings ist sie spezifisch für die USA. <p>**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen US-Bundesstaaten die meisten Personen stammen, die Ihre Site besuchen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Bundesstaaten zu konzentrieren.</p><p>Diese Vorlage verwendet die Dimension US-Bundesstaaten . </p> |
| **Geo-Regionen** | Zeigen Sie die geografische Region an, aus der die Personen stammen, die Ihre Site besuchen. Eine Region ist ein geografischer Bereich, der kleiner als ein Land, jedoch größer als eine Stadt ist. In einigen Ländern ist eine Region ein Bundesland, eine Provinz oder eine Präfektur. In anderen Gebieten handelt es sich um einen Landesteil, ein Departement oder eine großstädtische Region. <p>**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Regionen die meisten Personen stammen, die Ihre Site besuchen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Regionen zu konzentrieren, oder sicherstellen, dass Ihr Site-Erlebnis in Regionen mit unterschiedlichen Hauptsprachen optimal ist. </p><p>Diese Vorlage verwendet die Dimensionen ID (Variablen/Land) und Regionen . </p> |
| **Geo-Städte** | Zeigen Sie die Stadt an, aus der die Personen stammen, die Ihre Site besuchen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Städten die meisten Personen stammen, die Ihre Site besuchen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in diesen Städten zu konzentrieren. </p><p>Diese Vorlage verwendet die Dimension Städte . </p> |
| **Geo US DMA** | Zeigen Sie die designierten Marketing-Gebiete (DMAs) in den USA an, aus denen die Personen stammen, die Ihre Site besuchen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, aus welchen Regionen die meisten Personen stammen, die Ihre Site besuchen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Daten verwenden, um sich auf Marketing-Maßnahmen in der erfolgreichsten Regionen zu konzentrieren. </p><!-- This template uses the --> |
| **Sprachen** | Zeigen Sie die häufigsten Sprachen an, in denen die Besuchenden den Inhalt anzeigen. <p>**Dies kann Ihnen dabei helfen**, die am häufigsten bevorzugten Sprachen der Besuchenden besser zu verstehen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Lokalisierungs- oder Marketing-Maßnahmen auf die beliebtesten Sprachen konzentrieren.</p><p>Diese Vorlage verwendet die Dimension Sprache .</p> |
| **Technologieübersicht** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die </p> |
| **Browser** | Zeigen Sie den Namen und die Version der wichtigsten Browser an, die für den Zugriff auf Ihre Site verwendet werden.<p>**Dies kann Ihnen dabei helfen**, die gängigsten Browser, die beim Besuch verwendet werden, besser zu verstehen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Site-Qualität durch Testen neuer Versionen Ihrer Site mit den wichtigsten Browsern verbessern. Auf diese Weise können die Maßnahmen zur Qualitätssicherung maximiert werden.</p><p>Diese Vorlage verwendet die Dimension Browser . </p> |
| **Browsertypen** | Zeigen Sie die Namen der Organisationen an, die die wichtigsten Browser erstellt haben, mit denen Personen auf Ihre Site zugreifen. Diese Vorlage unterscheidet sich insofern von der Vorlage „Browser“, als sie verschiedene Versionen desselben Browsers nicht als separate Dimensionselemente auflistet.<p>**Dies kann Ihnen** helfen, die gängigsten Browser, die Besucher verwenden, besser zu verstehen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. die Site-Qualität durch Testen neuer Versionen Ihrer Site mit den wichtigsten Browsern verbessern. Auf diese Weise können die Maßnahmen zur Qualitätssicherung maximiert werden. </p><p>Diese Vorlage verwendet die Dimension Browsertyp . </p> |

### Web: Akquise {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Bei Verwendung der benutzerdefinierten Attribution zeigt diese Vorlage, wie Besuchende auf Ihre Site gelangen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Ihrer Marketing-Kanäle am effektivsten sind.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. intensiver in effektive Marketing-Kanäle investieren und weniger effektive Marketing-Kanäle aufgeben.<br/>Diese Vorlage verwendet die Dimension „ID(variables/marketingchannel)“ und die Metrik „Umsatz“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Zeigen Sie die ersten Marketing-Kanäle an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Marketing-Kanäle den anfänglichen Traffic zu Ihrer Site leiten.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.<br/>Diese Vorlage verwendet die Dimension „Erstkontaktkanal“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Zeigen Sie Details zu den ersten Marketing-Kanälen an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, was dazu beigetragen hat, dass der Treffer zu einem Marketing-Kanal passte. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.<br/>Diese Vorlage verwendet die Dimension „Detail des Erstkontaktkanals“."

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
>abstract="**Dies kann Ihnen helfen**, mehr über die verschiedenen Erfolgsindikatoren zu erfahren, die mit Kampagnen verbunden sind, wie Umsatz, Produktansichten, Bestellungen usw.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf die Kampagnen konzentrieren, die den meisten Umsatz bringen. <br/>Diese Vorlage verwendet die Metrik „Umsatz“, die Metrik „Produktansichten“, die Metrik „Zusatz zum Warenkorb“, die Metrik „Bestellungen“ und die Metrik „Einheiten“. Außerdem werden die Dimension „Trackingcode“ und die Dimension „Verweisende Domain“ verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-acquisition-template"
>title="Sehen Sie sich an, wie Ihre Website Besuchende erhält."
>abstract="**Dies kann Ihnen helfen**, die verschiedenen Faktoren besser zu verstehen, die zur Akquise führen, wie Suchbegriffe, verweisende Domain usw.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf die effektivsten Kanäle konzentrieren.<br/>Diese Vorlage verwendet die Metrik „Bounce-Rate“ und die Metrik „Bounces“. Außerdem werden die Dimension „Suchmaschine“, die Dimension „Suchbegriff“, die Dimension „Einstiegsseite“, die Dimension „Verweisende Domain“, die Dimension „Trackingcode“ und die Dimension „Verweisende Stelle“ verwendet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Zeigen Sie die Keywords an, die Besuchende zum Erreichen Ihrer Site verwenden, unabhängig davon, ob es sich um Paid Search oder organische Suche handelt."
>abstract="**Dies kann Ihnen helfen**, die Keywords besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Keywords, die den Sitetraffic fördern, identifizieren und füllen.<br/>Diese Vorlage verwendet die Dimension „Suchbegriff“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besuchende zum Erreichen Ihrer Site verwenden und die mit der Paid-Search-Erkennung übereinstimmen."
>abstract="**Dies kann Ihnen helfen**, die Keywords besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Keywords, die den Sitetraffic fördern, identifizieren und füllen. <br/>Diese Vorlage verwendet die Dimension „Suchbegriff – Paid“. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besuchende zum Erreichen Ihrer Site verwenden und die nicht mit der Paid-Search-Erkennung übereinstimmen."
>abstract="**Dies kann Ihnen helfen**, die Keywords besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Keywords, die den Sitetraffic fördern, identifizieren und füllen.<br/>Diese Vorlage verwendet die Dimension „Suchbegriff – Organisch“. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Zeigen Sie die Suchmaschinen an, die Besuchende zum Erreichen Ihrer Site verwenden, unabhängig davon, ob dafür bezahlt wurde oder sie natürlich sind."
>abstract="**Dies kann Ihnen helfen**, die Suchmaschinen besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.<br/>Diese Vorlage verwendet die Dimension „Suchmaschine“. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Zeigen Sie die Suchmaschinen an, die Besuchende zum Erreichen Ihrer Site verwenden und die mit der Paid-Search-Erkennung übereinstimmen."
>abstract="**Dies kann Ihnen helfen**, die Suchmaschinen besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten. <br/>Diese Vorlage verwendet die Dimension „Suchmaschine – Paid“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Zeigen Sie die Suchbegriffe an, die Besuchende zum Erreichen Ihrer Site verwenden und die nicht mit der Paid-Search-Erkennung übereinstimmen."
>abstract="**Dies kann Ihnen helfen**, die Suchmaschinen besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.<br/>Diese Vorlage verwendet die Dimension „Suchmaschine – Organisch“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Zeigen Sie an, durch welche Domains Besuchende sich klicken, um Ihre Site zu erreichen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Sites von Drittanbietern den meisten Traffic zu Ihrer Site leiten. (Auf der externen Site muss ein Link vorhanden sein und Besuchende müssen darauf klicken, damit das Dimensionselement angezeigt wird.)<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besuchenden von den verweisenden Top-Domains anzupassen. <br/>Diese Vorlage verwendet die Dimension „Verweisende Domain“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Zeigen Sie die erste verweisende Domain an, durch die sich Personen zum Erreichen Ihrer Site geklickt haben. (Sobald sie festgelegt wurde, enthält sie denselben Wert für die gesamte Lebensdauer dieser Besucher-ID.)"
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Drittanbieter-Sites den Traffic ursprünglich zu Ihrer Site leiten.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besuchenden von den ursprünglichen verweisenden Top-Domains anzupassen. <br/>Diese Vorlage verwendet die Dimension „Ursprünglich verweisende Domain“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Zeigen Sie an, auf welchen URLs sich die Besuchenden befanden, als sie sich zu Ihrer Site durchklickten. (Auf der externen URL muss ein Link vorhanden sein, und Besuchende müssen darauf klicken, damit das Dimensionselement angezeigt wird.)"
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche spezifischen URLs den meisten Traffic zu Ihrer Site leiten. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besuchenden von den Top-URLs anzupassen. <br/>Diese Vorlage verwendet die Dimension „Verweisende Domain“.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Zeigen Sie an, durch welche generischen Kanäle Besuchende sich geklickt haben, um zu Ihrer Site zu gelangen. Adobe verwaltet die Regeln für jeden Kanal. Mögliche Kanäle sind Suchmaschinen, soziale Netzwerke, andere Websites, die Festplatte oder E-Mails."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Referrer-Typen den meisten Traffic zu Ihrer Site leiten. <br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besuchenden von einem bestimmten Kanal anzupassen. <br/>Diese Vorlage verwendet die Dimension „Referrer-Typ“."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Marketingkanal-Übersichtsbericht**] | Bei Verwendung der benutzerdefinierten Attribution zeigt diese Vorlage, wie Besuchende auf Ihre Site gelangen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Ihrer Marketing-Kanäle am effektivsten sind.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. intensiver in effektive Marketing-Kanäle investieren und weniger effektive Marketing-Kanäle aufgeben.</p><p>Diese Vorlage verwendet die Dimension ID (Variablen/Marketing-Kanal) und die Metrik Umsatz .</p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Erstkontakt Marketingkanal**] | Zeigen Sie die ersten Marketing-Kanäle an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen. <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Marketing-Kanäle den anfänglichen Traffic zu Ihrer Site leiten.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.</p><p>Diese Vorlage verwendet die Dimension Erstkontakt Kanal .</p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Erstkontakt Marketingkanaldetail**] | Zeigen Sie Details zu den ersten Marketing-Kanälen an, zu denen Besuchende während ihres Interaktionszeitraums (standardmäßig 30 Tage) passen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, was dazu beigetragen hat, dass der Treffer zu einem Marketing-Kanal passte. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.</p><p>Diese Vorlage verwendet die Dimension Erstkontakt Kanaldetail .</p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Letztkontakt Marketingkanal**] | Zeigen Sie den neuesten Marketing-Kanal an, mit dem ein Besucher während des Interaktionszeitraums des Besuchers übereinstimmt (standardmäßig 30 Tage).<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Marketing-Kanäle Traffic zu Ihrer Site leiten, der zu Konversionen führt.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind.</p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanal .  </p> |
| [!UICONTROL **Marketingkanäle**] > [!UICONTROL **Letztkontakt Marketingkanaldetail**] | Details zum neuesten Marketing-Kanal anzeigen, mit dem ein Besucher während des Interaktionszeitraums des Besuchers (standardmäßig 30 Tage) übereinstimmt<p>**Dies kann Ihnen helfen**, besser zu verstehen, was dazu beigetragen hat, dass der Treffer zu einem Marketing-Kanal passte. Wenn beispielsweise ein Besucher zu Ihrer Site gelangt ist und mit dem Marketing-Kanal „Paid Search“ übereinstimmt, können Sie anhand des Kanaldetails sehen, welche Suchmaschine verwendet wurde oder nach welchem Schlüsselwort er gesucht hat.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf Bereiche konzentrieren, die am effektivsten sind. </p><p>Diese Vorlage verwendet die Dimension Letztkontakt Kanaldetail . </p> |
| [!UICONTROL **Kampagnen**] > [!UICONTROL **Kampagnen (Trackingcode)**] | Zeigen Sie die Namen der Trackingcodes auf Ihrer Site an. Sie können Links mit unterschiedlichen Abfragezeichenfolgenparameterwerten an verschiedenen Stellen im Internet platzieren.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Links am erfolgreichsten zur Erhöhung des Traffics auf Ihre Site beigetragen haben. Abfragezeichenfolgen für Trackingcodes werden häufig in E-Mails, Anzeigen, Social-Media-Beiträgen und anderen Marketing-Maßnahmen verwendet, die Ihr Unternehmen verwendet</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Marketing-Maßnahmen auf die Kampagnen zu konzentrieren, die den meisten Umsatz bringen.</p><p>Diese Vorlage verwendet die Dimension Trackingcode . </p> |
| [!UICONTROL **Kampagnen**] > [!UICONTROL **Kampagnenkonversionstrichter**] | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die  </p> |
| [!UICONTROL **Kampagnen**] > [!UICONTROL **Kampagnenleistung**] | Zeigen Sie Details zur Leistung Ihrer Marketing-Kampagnen an.<p>**Dies kann Ihnen helfen**, mehr über die verschiedenen Erfolgsindikatoren zu erfahren, die mit Kampagnen verbunden sind, wie Umsatz, Produktansichten, Bestellungen usw.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Marketing-Maßnahmen auf die Kampagnen zu konzentrieren, die den meisten Umsatz bringen. </p><p>Diese Vorlage verwendet die Metrik Umsatz , die Metrik Produktansichten , die Metrik Zusatz zum Warenkorb , die Metrik Bestellungen und Einheiten . Außerdem werden die Dimension „Trackingcode“ und die Dimension „Verweisende Domain“ verwendet. </p> |
| **Web-Akquise** | Sehen Sie sich an, wie Ihre Website Besuchende erhält.<p>**Dies kann Ihnen helfen**, die verschiedenen Faktoren besser zu verstehen, die zur Akquise führen, wie Suchbegriffe, verweisende Domain usw.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Marketing-Maßnahmen auf die effektivsten Kanäle konzentrieren.</p><p>Diese Vorlage verwendet die Metrik Absprungrate und die Metrik Absprünge . Außerdem werden die Dimension „Suchmaschine“, die Dimension „Suchbegriff“, die Dimension „Einstiegsseite“, die Dimension „Verweisende Domain“, die Dimension „Trackingcode“ und die Dimension „Verweisende Stelle“ verwendet.  </p> |
| **Suchkeywords-all** | Zeigen Sie die Keywords an, die Besuchende zum Erreichen Ihrer Site verwenden, unabhängig davon, ob es sich um Paid Search oder organische Suche handelt. <p>**Dies kann Ihnen helfen**, die Keywords besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen.  </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Keywords, die den Sitetraffic fördern, identifizieren und füllen.</p><p>Diese Vorlage verwendet die Dimension Suchbegriff . </p> |
| **Suchkeywords-paid** | Zeigen Sie die Suchbegriffe an, die Besuchende zum Erreichen Ihrer Site verwenden und die mit der Paid-Search-Erkennung übereinstimmen.<p>**Dies kann Ihnen helfen**, die Keywords besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Keywords, die den Sitetraffic fördern, identifizieren und füllen. </p><p>Diese Vorlage verwendet die Dimension Suchbegriff - Gebührenpflichtig . </p> |
| **Suchkeywords-kostenlos** | Zeigen Sie die Suchbegriffe an, die Besuchende zum Erreichen Ihrer Site verwenden und die nicht mit der Paid-Search-Erkennung übereinstimmen.<p>**Dies kann Ihnen helfen**, die Keywords besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. SEO-Lücken zwischen den verwendeten Keywords und den Keywords, die den Sitetraffic fördern, identifizieren und füllen.</p><p>Diese Vorlage verwendet die Dimension Suchbegriff - Kostenlos . </p> |
| **Suchmaschinen-Alle** | Zeigen Sie die Suchmaschinen an, die Besuchende zum Erreichen Ihrer Site verwenden, unabhängig davon, ob dafür bezahlt wurde oder sie natürlich sind. <p>**Dies kann Ihnen helfen**, die Suchmaschinen besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen. </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.</p><p>Diese Vorlage verwendet die Dimension Suchmaschine . </p> |
| **Suchmaschinen-bezahlt** | Zeigen Sie die Suchmaschinen an, die Besuchende zum Erreichen Ihrer Site verwenden und die mit der Paid-Search-Erkennung übereinstimmen.<p>**Dies kann Ihnen helfen**, die Suchmaschinen besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten. </p><p>Diese Vorlage verwendet die Dimension Suchmaschine - Gebührenpflichtig . </p> |
| **Suchmaschinen-kostenlos** | Zeigen Sie die Suchbegriffe an, die Besuchende zum Erreichen Ihrer Site verwenden und die nicht mit der Paid-Search-Erkennung übereinstimmen.<p>**Dies kann Ihnen helfen**, die Suchmaschinen besser zu verstehen, die bei Suchvorgängen verwendet werden, die zu Sitetraffic führen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre SEO-Bemühungen auf die Suchmaschinen konzentrieren, die den meisten Traffic zur Site leiten.</p><p>Diese Vorlage verwendet die Dimension Suchmaschine - Kostenlos . </p> |
| **Referrerdomänen** | Zeigen Sie an, durch welche Domains Besuchende sich klicken, um Ihre Site zu erreichen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Sites von Drittanbietern den meisten Traffic zu Ihrer Site leiten. (Auf der externen Site muss ein Link vorhanden sein und Besuchende müssen darauf klicken, damit das Dimensionselement angezeigt wird.)</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus den Top-Referrer-Domänen anzupassen. </p><p>Diese Vorlage verwendet die Dimension Referrer-Domäne . </p> |
| **Ursprünglich Referrerdomänen** | Zeigen Sie die erste verweisende Domain an, durch die sich Personen zum Erreichen Ihrer Site geklickt haben. (Sobald sie festgelegt wurde, enthält sie denselben Wert für die gesamte Lebensdauer dieser Besucher-ID.)<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Drittanbieter-Sites den Traffic ursprünglich zu Ihrer Site leiten.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher aus den ursprünglichen Referrerdomänen anzupassen. </p><p>Diese Vorlage verwendet die Dimension &quot;Ursprünglich verweisende Domäne&quot;. </p> |
| **Verweisende Stellen** | Zeigen Sie an, auf welchen URLs sich die Besuchenden befanden, als sie sich zu Ihrer Site durchklickten. (Auf der externen URL muss ein Link vorhanden sein, und Besuchende müssen darauf klicken, damit das Dimensionselement angezeigt wird.)  <p>**Dies kann Ihnen helfen**, besser zu verstehen, welche spezifischen URLs den meisten Traffic zu Ihrer Site leiten. </p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besucher anzupassen, die von Top-URLs kommen. </p><p>Diese Vorlage verwendet die Dimension Referrerdomäne . </p><p>Diese Vorlage verwendet die Dimension Referrer . </p> |
| **Typen der verweisenden Stellen** | Zeigen Sie an, durch welche generischen Kanäle Besuchende sich geklickt haben, um zu Ihrer Site zu gelangen. Adobe verwaltet die Regeln für jeden Kanal. Mögliche Kanäle sind Suchmaschinen, soziale Netzwerke, andere Websites, die Festplatte oder E-Mails.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Referrer-Typen den meisten Traffic zu Ihrer Site leiten. </p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Inhalte erstellen oder anpassen, um sie besser an die Interessen der Besuchenden von einem bestimmten Kanal anzupassen. </p><p>Diese Vorlage verwendet die Dimension Referrer-Typ .</p> |

### Mobile: Mobile App {#mobile-app}

<!-- add contextual help for Mobile app screens and mobile app actions -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-lifecycle-metrics-app-usage-template"
>title="Zeigen Sie die Anzahl der Benutzer, Starts und ersten Starts in Ihrer App sowie die durchschnittliche Sitzungslänge an."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie viel Ihre App verwendet wird. <br/>**Je nachdem, was Sie lernen, können Sie** beliebig viele Dinge tun, z. B. die App-Leistung verbessern, damit sie auf die Nutzungsmenge skaliert werden kann."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-journeys"
>title="Zeigen Sie die markanten Nutzungsmuster für Ihre App an."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer Ihre App verwenden. <br/>**Basierend auf dem, was Sie lernen, können Sie** beliebig viele Dinge tun, z. B. die Verbesserung, wie Benutzer von einem Bildschirm zum anderen gelangen können, um die häufigsten Workflows auszuwählen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-key-metrics"
>title="Zeigen Sie einige der häufigsten Mobile-App-Metriken an."
>abstract="**Dies kann Ihnen** dabei helfen, die grundlegende Leistung Ihrer App besser zu verstehen.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die allgemeine Gesundheit und Leistung Ihrer App bewerten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-messaging"
>title="Zeigen Sie Leistungsdaten für In-App-Nachrichten und Push-Nachrichten für Ihre App an."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer In-App-Messaging-Funktionen verwenden und wie effektiv Push-Benachrichtigungen Traffic zu Ihrer App leiten.<br/>**Je nach Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die Verbesserung des Erlebnisses von In-App-Nachrichten-Push-Benachrichtigungen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-performance-template"
>title="Sehen Sie sich die Leistung Ihrer App an und erfahren Sie, wo Probleme bei Benutzern auftreten."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, ob Benutzer Ihrer App auf Langsamkeit oder eine beeinträchtigte Leistung stoßen. <br/>**Je nachdem, was Sie erfahren, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. vorhandene Probleme beheben oder die App-Leistung verbessern, bevor Probleme auftreten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-retention"
>title="Zeigen Sie an, welche Benutzer die treuesten Benutzer Ihrer App sind und was sie in der App tun."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie Ihre treusten Benutzer Ihre App verwenden.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Ihre Marketing-Bemühungen für die Funktionen verbessern, die Ihre treusten Benutzer verwenden."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Mobile App Screens**] | Zeigen Sie die Anzahl der Ereignisse, Sitzungen und Personen an, die mit den einzelnen Bildschirmen der App verknüpft sind.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Bildschirme auf Ihrer Site am beliebtesten sind.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Inhalte auf den beliebtesten Bildschirmen verbessern.</p><p>Diese Vorlage verwendet die Metriken für die Änderungen &quot;Ereignisse&quot;, &quot;Sitzungen&quot;, &quot;Personen&quot;und &quot;Prozent&quot;. Außerdem wird die Dimension &quot;Seitentitel&quot;verwendet.</p> |
| **Mobile App-Aktionen** | Sehen Sie sich die Aktionen an, die Benutzer Ihrer mobilen App ausführen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer Ihre App verwenden, und welchen Wert sie daraus erhalten.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Entwicklung von Funktionen verbessern, die die beliebtesten ergänzen oder verbessern.</p><p>Diese Vorlage verwendet die Metriken für die Änderungen &quot;Ereignisse&quot;, &quot;Sitzungen&quot;, &quot;Personen&quot;und &quot;Prozent&quot;. |
| **Mobile App Usage** | Zeigen Sie die Anzahl der Benutzer, Starts und ersten Starts in Ihrer App sowie die durchschnittliche Sitzungslänge an.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wie viel Ihre App verwendet wird. </p><p>**Je nachdem, was Sie lernen, können Sie** beliebig viele Dinge tun, z. B. die App-Leistung verbessern, damit sie auf die Nutzungsmenge skaliert werden kann.</p><!-- This template uses the --> |
| **Journey der mobilen App** | Zeigen Sie die markanten Nutzungsmuster für Ihre App an. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer Ihre App verwenden. </p><p>**Basierend auf dem, was Sie lernen, können Sie** beliebig viele Dinge tun, z. B. die Verbesserung, wie Benutzer von einem Bildschirm zum anderen gelangen können, um die häufigsten Workflows auszuwählen. </p><!-- This template uses the --> |
| **Mobile-App-Metriken** | Zeigen Sie einige der häufigsten Mobile-App-Metriken an. <p>**Dies kann Ihnen** dabei helfen, die grundlegende Leistung Ihrer App besser zu verstehen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die allgemeine Gesundheit und Leistung Ihrer App bewerten.</p><!-- This template uses the --> |
| **Mobile App Messaging** | Zeigen Sie Leistungsdaten für In-App-Nachrichten und Push-Nachrichten für Ihre App an.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wie Benutzer In-App-Messaging-Funktionen verwenden und wie effektiv Push-Benachrichtigungen Traffic zu Ihrer App leiten.</p><p>**Je nach Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. die Verbesserung des Erlebnisses von In-App-Nachrichten-Push-Benachrichtigungen.</p><!-- This template uses the --> |
| **Leistung der mobilen App** | Sehen Sie sich die Leistung Ihrer App an und erfahren Sie, wo Probleme bei Benutzern auftreten. <p>**Dies kann Ihnen** helfen, besser zu verstehen, ob Benutzer Ihrer App auf Langsamkeit oder eine beeinträchtigte Leistung stoßen. </p><p>**Je nachdem, was Sie erfahren, können Sie** eine beliebige Anzahl von Maßnahmen ergreifen, z. B. vorhandene Probleme beheben oder die App-Leistung verbessern, bevor Probleme auftreten.</p><!-- This template uses the --> |
| **Beibehaltung mobiler Apps** | Zeigen Sie an, welche Benutzer die treuesten Benutzer Ihrer App sind und was sie in der App tun. <p>**Dies kann Ihnen** helfen, besser zu verstehen, wie Ihre treusten Benutzer Ihre App verwenden.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Maßnahmen durchführen, z. B. Ihre Marketing-Bemühungen für die Funktionen verbessern, die Ihre treusten Benutzer verwenden.</p><!-- This template uses the --> |

### Mobile: Informationen zu Mobilgeräten {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileCarrierRankedReport"
>title="Zeigen Sie das Telekommunikationsunternehmen an, das Mobilfunkverbindungen mit den Mobilgeräten bereitstellt, mit denen Benutzende auf Ihre Site zugreifen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Mobilnetzbetreiber bei Ihrer Benutzerbasis am beliebtesten sind.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Netzwerkfunktionen verschiedener Betreiber anpassen, um ein reibungsloses Anwendererlebnis zu gewährleisten.<br/>Diese Vorlage verwendet die Dimension „Mobilnetzbetreiber“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceNameRankedReport"
>title="Zeigen Sie die Marke und das Modell von Mobilgeräten an, mit denen Benutzende auf Ihre Site zugreifen."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Mobilgeräte bei Ihrer Benutzerbasis am beliebtesten sind.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. das Rendering Ihrer Site für die gängigsten Mobilgeräte optimieren.<br/>Diese Vorlage verwendet die Dimension „Mobilgerätename“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceTypeRankedReport"
>title="Zeigen Sie die Mobilgerätetypen an, mit denen Benutzende auf Ihre Site zugreifen, z. B. Smartphones und Tablets."
>abstract="**Dies kann Ihnen dabei helfen**, die verschiedenen Arten von Mobilgeräten besser zu verstehen, die für den Zugriff auf Ihre Site verwendet werden.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Site für die Mobilgerätetypen optimieren, die am häufigsten verwendet werden.<br/>Diese Vorlage verwendet die Dimension „Mobilgerätetyp“."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileManufacturerRankedReport"
>title="Zeigen Sie an, welche Hersteller die Mobilgeräte herstellen, mit denen Benutzende auf Ihre Site zugreifen, z. B. Apple und Samsung."
>abstract="**Dies kann Ihnen helfen**, besser zu verstehen, welche Hersteller bei Ihrer Benutzerbasis am beliebtesten sind.<br/>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Fähigkeiten verschiedener Hersteller anpassen, um ein reibungsloses Anwendererlebnis zu gewährleisten.<br/>Diese Vorlage verwendet die Dimension „Mobilgerätehersteller“."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Mobilnetzbetreiber**] | Zeigen Sie das Telekommunikationsunternehmen an, das Mobilfunkverbindungen mit den Mobilgeräten bereitstellt, mit denen Benutzende auf Ihre Site zugreifen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Mobilnetzbetreiber bei Ihrer Benutzerbasis am beliebtesten sind.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Netzwerkfunktionen verschiedener Betreiber anpassen, um ein reibungsloses Anwendererlebnis zu gewährleisten.</p><p>Diese Vorlage verwendet die Dimension Mobilnetzbetreiber .</p> |
| **Mobilgeräte** | Zeigen Sie die Marke und das Modell von Mobilgeräten an, mit denen Benutzende auf Ihre Site zugreifen.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Mobilgeräte bei Ihrer Benutzerbasis am beliebtesten sind.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. das Rendering Ihrer Site für die gängigsten Mobilgeräte optimieren.</p><p>Diese Vorlage verwendet die Dimension Mobilgerätename .</p> |
| **Mobilgerätetyp** | Zeigen Sie die Mobilgerätetypen an, mit denen Benutzende auf Ihre Site zugreifen, z. B. Smartphones und Tablets.<p>**Dies kann Ihnen dabei helfen**, die verschiedenen Arten von Mobilgeräten besser zu verstehen, die für den Zugriff auf Ihre Site verwendet werden.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Site für die Mobilgerätetypen optimieren, die am häufigsten verwendet werden.</p><p>Diese Vorlage verwendet die Dimension Mobilgerätetyp .</p> |
| **Hersteller** | Zeigen Sie an, welche Hersteller die Mobilgeräte herstellen, mit denen Benutzende auf Ihre Site zugreifen, z. B. Apple und Samsung.<p>**Dies kann Ihnen helfen**, besser zu verstehen, welche Hersteller bei Ihrer Benutzerbasis am beliebtesten sind.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** eine Reihe von Schritten ausführen, z. B. Ihre Inhaltsbereitstellung auf Grundlage der Fähigkeiten verschiedener Hersteller anpassen, um ein reibungsloses Anwendererlebnis zu gewährleisten.</p><p>Diese Vorlage verwendet die Dimension Mobilgerätehersteller .</p> |

### Zeitunterteilung {#time-parting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Anzeigen der Anzahl der Ereignisse, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Minuten. Wenn Sie beispielsweise einen Bericht mit einem Berichtszeitrahmen von einem einzelnen Tag haben, wird die erste Minute jeder Stunde des Tages in dasselbe Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, Trends auf granularer Ebene besser zu verstehen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ressourcen für Spitzenzeiten optimieren, bis auf die Minute.<br/>Diese Vorlage verwendet die Dimension Minute der Stunde ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Stunden des Tages. Wenn Sie beispielsweise einen Bericht haben, der sich vom 1. Januar bis zum 7. Januar erstreckt, wird die erste Stunde jedes Tages in dasselbe Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, die Tageszeit besser zu verstehen, zu der Ihre Site am häufigsten und am wenigsten häufig besucht wird.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihrer Site während hoher Traffic-Zeiten mehr Rechenressourcen zuweisen.<br/>Diese Vorlage verwendet die Dimension Stunde des Tages."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach AM und PM. Wenn Sie beispielsweise einen Bericht haben, der sich vom 1. Januar bis zum 7. Januar erstreckt, werden die AM-Stunden jedes Tages in dasselbe Dimensionselement gruppiert."
>abstract="***Dies kann Ihnen** helfen, die Tageszeit besser zu verstehen, zu der Ihre Site am häufigsten und am wenigsten häufig besucht wird.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihrer Site während hoher Traffic-Zeiten mehr Rechenressourcen zuweisen.<br/>Diese Vorlage verwendet die AM/PM-Dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Wochentagen. Wenn Sie beispielsweise einen Bericht haben, der sich auf den Monat Januar erstreckt, wird jeder Wochentag in dasselbe Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Wochentage Ihre Site am häufigsten und am seltensten besucht.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.<br/>Diese Vorlage verwendet die Dimension Wochentag ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Tag des Monats. Wenn Sie beispielsweise einen Bericht haben, der sich auf ein ganzes Jahr erstreckt, wird jeder Tag des Monats in ein und dasselbe Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Tage eines jeden Monats Ihre Site am häufigsten und am wenigsten häufig besucht.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.<br/>Diese Vorlage verwendet die Dimension Tag des Monats ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Zeigen Sie Ereignisse, Sitzungen und Personen auf Ihrer Site an, aufgeschlüsselt nach Tag des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jeder Tag des Jahres in ein und dasselbe Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Tage eines jeden Jahres Ihre Site am häufigsten und am wenigsten häufig besucht.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.<br/>Diese Vorlage verwendet die Dimension Tag des Jahres ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Zeigen Sie Ereignisse, Sitzungen und Personen auf Ihrer Site an, aufgeschlüsselt nach Wochentagen und Wochenenden. Wenn Sie beispielsweise einen Bericht haben, der sich auf den Januar erstreckt, werden Wochentage und Wochenenden in separate Dimensionselemente gruppiert."
>abstract="**Dies kann Ihnen** helfen, die Unterschiede im Site-Traffic für Wochentage und Wochenenden besser zu verstehen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter stärker an den Wochenenden zu beschäftigen, wenn der Bericht darauf hinweist, dass Wochenenden schlechter sind als Wochentage.<br/>Diese Vorlage verwendet die Dimension Wochentag/Wochenende ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Woche des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jede Woche in demselben Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Wochen des Jahres Ihre Site am häufigsten und am wenigsten häufig besucht wird.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter für Wochen mit hohem Traffic besser betreuen, z. B. während der Feiertage.<br/>Diese Vorlage verwendet die Dimension Woche des Jahres ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Monat des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jeder Monat in demselben Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, in welchen Monaten Ihre Site am häufigsten und am seltensten besucht wird.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter für Monate mit hohem Traffic-Aufkommen besser betreuen, z. B. während der Feiertage.<br/>Diese Vorlage verwendet die Dimension &quot;Monat des Jahres&quot;."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Quartal des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jedes Quartal in demselben Dimensionselement gruppiert."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Quartale Ihre Site am häufigsten und am seltensten besucht.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Zeit des Produktstarts, um historisch wenig Traffic-Viertel zu steigern.<br/>Diese Vorlage verwendet die Dimension &quot;Quartal des Jahres&quot;."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Minute der Stunde**] | Anzeigen der Anzahl der Ereignisse, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Minuten. Wenn Sie beispielsweise einen Bericht mit einem Berichtszeitrahmen von einem einzelnen Tag haben, wird die erste Minute jeder Stunde des Tages in dasselbe Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, Trends auf granularer Ebene besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ressourcen für Spitzenzeiten optimieren, bis auf die Minute.</p><p>Diese Vorlage verwendet die Dimension Minute der Stunde .</p> |
| **Stunde des Tages** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Stunden des Tages. Wenn Sie beispielsweise einen Bericht haben, der sich vom 1. Januar bis zum 7. Januar erstreckt, wird die erste Stunde jedes Tages in dasselbe Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, die Tageszeit besser zu verstehen, zu der Ihre Site am häufigsten und am wenigsten häufig besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihrer Site während hoher Traffic-Zeiten mehr Rechenressourcen zuweisen.</p><p>Diese Vorlage verwendet die Dimension Stunde des Tages.</p> |
| **Vormittag/Nachmittag** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach AM und PM. Wenn Sie beispielsweise einen Bericht haben, der sich vom 1. Januar bis zum 7. Januar erstreckt, werden die AM-Stunden jedes Tages in dasselbe Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, die Tageszeit besser zu verstehen, zu der Ihre Site am häufigsten und am wenigsten häufig besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihrer Site während hoher Traffic-Zeiten mehr Rechenressourcen zuweisen.</p><p>Diese Vorlage verwendet die AM/PM-Dimension.</p> |
| **Wochentag** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Wochentagen. Wenn Sie beispielsweise einen Bericht haben, der sich auf den Monat Januar erstreckt, wird jeder Wochentag in dasselbe Dimensionselement gruppiert. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Wochentage Ihre Site am häufigsten und am seltensten besucht.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.</p><p>Diese Vorlage verwendet die Dimension Wochentag .</p> |
| **Tag des Monats** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Tag des Monats. Wenn Sie beispielsweise einen Bericht haben, der sich auf ein ganzes Jahr erstreckt, wird jeder Tag des Monats in ein und dasselbe Dimensionselement gruppiert. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Tage eines jeden Monats Ihre Site am häufigsten und am wenigsten häufig besucht.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.</p><p>Diese Vorlage verwendet die Dimension Tag des Monats .</p> |
| **Tag des Jahres** | Zeigen Sie Ereignisse, Sitzungen und Personen auf Ihrer Site an, aufgeschlüsselt nach Tag des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jeder Tag des Jahres in ein und dasselbe Dimensionselement gruppiert. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Tage eines jeden Jahres Ihre Site am häufigsten und am wenigsten häufig besucht.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter besser für Tage mit hohem Traffic-Aufkommen gestalten.</p><p>Diese Vorlage verwendet die Dimension Tag des Jahres .&lt;/> |
| **Wochentag/Wochenende** | Zeigen Sie Ereignisse, Sitzungen und Personen auf Ihrer Site an, aufgeschlüsselt nach Wochentagen und Wochenenden. Wenn Sie beispielsweise einen Bericht haben, der sich auf den Januar erstreckt, werden Wochentage und Wochenenden in separate Dimensionselemente gruppiert. <p>**Dies kann Ihnen** helfen, die Unterschiede im Site-Traffic für Wochentage und Wochenenden besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter stärker an den Wochenenden zu beschäftigen, wenn der Bericht darauf hinweist, dass Wochenenden schlechter sind als Wochentage.</p><p>Diese Vorlage verwendet die Dimension Wochentag/Wochenende .</p> |
| **Woche des Jahres** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Woche des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jede Woche in demselben Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Wochen des Jahres Ihre Site am häufigsten und am wenigsten häufig besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter für Wochen mit hohem Traffic besser betreuen, z. B. während der Feiertage.</p><p>Diese Vorlage verwendet die Dimension Woche des Jahres .</p> |
| **Monat des Jahres** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Monat des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jeder Monat in demselben Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, besser zu verstehen, in welchen Monaten Ihre Site am häufigsten und am seltensten besucht wird.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihr Callcenter für Monate mit hohem Traffic-Aufkommen besser betreuen, z. B. während der Feiertage.</p><p>Diese Vorlage verwendet die Dimension Monat des Jahres .</p> |
| **Quartal des Jahres** | Anzeigen von Ereignissen, Sitzungen und Personen auf Ihrer Site, aufgeschlüsselt nach Quartal des Jahres. Wenn Sie beispielsweise einen Bericht haben, der sich über mehrere Jahre erstreckt, wird jedes Quartal in demselben Dimensionselement gruppiert.<p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Quartale Ihre Site am häufigsten und am seltensten besucht.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Zeit des Produktstarts, um historisch wenig Traffic-Viertel zu steigern.</p><p>Diese Vorlage verwendet die Dimension &quot;Quartal des Jahres&quot;.</p> |

### Kanalübergreifend {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Anzeigen der Traffic-Verteilung über mehrere Kanäle."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, welche Kanäle Traffic und Interaktion erfolgreicher fördern. <br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf die Kanäle konzentrieren, die die höchste ROI erzielen.<br/>Diese Vorlage verwendet die Benutzer-, Sitzungs- und Ereignismetriken."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Sehen Sie sich an, wie der Web-Traffic den Callcenter-Traffic beeinflusst."
>abstract="**Dies kann Ihnen** helfen, besser zu verstehen, wie erfolgreich der Self-Service-Inhalt auf Ihrer Website den Traffic zu Ihrem Callcenter lenkt.<br/>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. den Self-Service-Inhalt verbessern, um den Traffic zu Ihrem Callcenter zu reduzieren, oder den ROI Ihres Self-Service-Inhalts messen, indem Sie den durch weniger Support-Aufrufe eingesparten Betrag berechnen.<br/>Diese Vorlage verwendet die Metriken Web-Sitzungen, Mobile-App-Sitzungen und Web+App-Sitzungen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Anzeigen von Web-Traffic und mobilem Traffic"
>abstract="**Dies kann Ihnen** dabei helfen, die Verteilung des Web- und mobilen Traffics auf Ihre Site besser zu verstehen.<br/>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. mehr Ressourcen für Ihr App-Erlebnis zuweisen, wenn es ein bestimmtes Traffic-Niveau erreicht.<br/>Diese Vorlage verwendet die Metriken Web-Sitzungen, Mobile-App-Sitzungen und Web+App-Sitzungen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Anzeigen von Online- und Offline-Traffic gemeinsam."
>abstract="**Dies kann Ihnen** helfen, die Verteilung des Online- und Offline-Traffics auf Ihre Site besser zu verstehen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für Ihr Online-Erlebnis bereitstellen, wenn es ein bestimmtes Traffic-Niveau erreicht."

<!-- markdownlint-enable MD034 -->

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Überblick über mehrere Kanäle**] | Anzeigen der Traffic-Verteilung über mehrere Kanäle. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Kanäle Traffic und Interaktion erfolgreicher fördern. </p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Marketing-Maßnahmen auf die Kanäle konzentrieren, die die höchste ROI erzielen.</p><p>Diese Vorlage verwendet die Benutzer-, Sitzungs- und Ereignismetriken.</p> |
| **Callcenter-Erkennung (Web+Call Center)** | Sehen Sie sich an, wie der Web-Traffic den Callcenter-Traffic beeinflusst.<p>**Dies kann Ihnen** helfen, besser zu verstehen, wie erfolgreich der Self-Service-Inhalt auf Ihrer Website den Traffic zu Ihrem Callcenter lenkt.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. den Self-Service-Inhalt verbessern, um den Traffic zu Ihrem Callcenter zu reduzieren, oder den ROI Ihres Self-Service-Inhalts messen, indem Sie den durch weniger Support-Aufrufe eingesparten Betrag berechnen.</p><p>Diese Vorlage verwendet die Metriken Web-Sitzungen, Mobile-App-Sitzungen und Web+App-Sitzungen.</p> |
| **Web+App** | Anzeigen von Web-Traffic und mobilem Traffic<p>**Dies kann Ihnen** dabei helfen, die Verteilung des Web- und mobilen Traffics auf Ihre Site besser zu verstehen.</p><p>**Basierend auf Ihren Erkenntnissen können Sie** beliebig viele Dinge tun, z. B. mehr Ressourcen für Ihr App-Erlebnis zuweisen, wenn es ein bestimmtes Traffic-Niveau erreicht.</p><p>Diese Vorlage verwendet die Metriken Web-Sitzungen, Mobile-App-Sitzungen und Web+App-Sitzungen.</p> |
| **Online/Offline** | Anzeigen von Online- und Offline-Traffic gemeinsam.<p>**Dies kann Ihnen** helfen, die Verteilung des Online- und Offline-Traffics auf Ihre Site besser zu verstehen.</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Ressourcen für Ihr Online-Erlebnis bereitstellen, wenn es ein bestimmtes Traffic-Niveau erreicht.</p><!-- This template uses the ... --> |

### Andere Kanäle {#other-channels}

Die folgenden Vorlagen sind verfügbar:

| Vorlagenname | Warum diese Vorlage <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> verwenden |
| --- | --- | 
| [!UICONTROL **Callcenter-Dashboard**] | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **POS/Offline** | Zeigen Sie POS-Transaktionsdaten (Point-of-Sale) an, einschließlich Umsatz, getätigten Bestellungen und verkauften Einheiten. Diese Vorlage enthält auch Visualisierungen, die Informationen über Top-Stores, Top-Produkte und Top-Produktkategorien sowie Online- und Offline-Verkäufe anzeigen. <p>**Dies kann Ihnen** helfen, besser zu verstehen, welche Produkte Sie am häufigsten verkaufen, und zwar über den Store und online.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. mehr Marketing-Ressourcen zu Ihren Produkten und Kanälen mit der höchsten Leistung zuweisen.</p><p>Diese Vorlage verwendet die Metriken Benutzer, Umsatz und Bestellungen .</p> |
| **E-Mail/AJO** | <p>**Dies hilft Ihnen**, besser zu verstehen</p><p>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. </p><p>Diese Vorlage verwendet die |
| **Umfrage** | Anzeigen der Benutzerinteraktion für Ihre Umfragen. Sehen Sie sich die Anzahl der Starts und Beendigungen, die wichtigsten Fragen und Antworten sowie die Anzahl der ersten und wiederholten Teilnehmer an.<p>**Dies kann Ihnen** dabei helfen, die Interaktionsstufen und die Erfolgsrate Ihrer Umfragen besser zu verstehen.</p><p>**Basierend auf dem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. zukünftige Umfragen so anpassen, dass eine bessere Beteiligung erreicht wird.</p><p>Diese Vorlage verwendet die Metriken Benutzer, Ereignisse, Umfragestarts, Umfragebeendigungen und Umfrageabschlussrate .</p> |

### AJO {#AJO-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Zeigen Sie wichtige Metriken für Ihre Journey Optimizer-Kampagnen an, darunter E-Mail-Kampagnen, Experimente, In-App-Nachrichten, SMS usw."
>abstract="**Dies kann Ihnen** dabei helfen, Details wie die Anzahl der Klicks und die Anzahl der zugestellten Nachrichten besser zu verstehen. So erhalten Sie einen umfassenden Einblick in die Effektivität und den Grad der Interaktion Ihrer Kampagne.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Kampagnen auf der Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Zeigen Sie wichtige Metriken für Ihre Journey Optimizer-Journey an, darunter E-Mail-Journey, Experimente, In-App-Nachrichten, SMS und mehr."
>abstract="**Dies kann Ihnen** dabei helfen, Details wie die Anzahl der Klicks und die Anzahl der zugestellten Nachrichten besser zu verstehen. So erhalten Sie einen umfassenden Einblick in die Effektivität Ihrer Journey und den Grad der Interaktion.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Kampagnen auf der Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Anzeigen von Benutzerverhalten, Interaktionsmustern, Konversionsraten und anderen Schlüsselmetriken."
>abstract="**Dies kann Ihnen** helfen, die Effektivität Ihrer Landingpage besser zu verstehen. <br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. die Leistung Ihrer Landingpage optimieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Zeigen Sie eine ausführliche Zusammenfassung der Traffic- und Interaktionsmetriken für alle Kampagnen und Journey in Ihrer Umgebung an."
>abstract="**Dies kann Ihnen** helfen, die Effektivität Ihrer Kampagnen und Journey besser zu verstehen. <br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Kampagnen und Journey auf Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Anzeigen von Anmeldungen und Abmeldungen von Profilen, die bestimmten Listen zugeordnet sind."
>abstract="**Dies kann Ihnen** helfen, die Effektivität verschiedener Abonnementkampagnen und -initiativen bei der Förderung von Interaktion und Konversionen besser zu verstehen.<br/>**Je nachdem, was Sie lernen, können Sie** eine beliebige Anzahl von Dingen ausführen, z. B. Ihre Abonnementkampagnen auf der Grundlage der Interaktionsstufen Ihrer Zielgruppe anpassen."

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
