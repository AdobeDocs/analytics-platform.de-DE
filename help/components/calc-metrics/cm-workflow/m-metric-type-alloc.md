---
description: Erfahren Sie mehr über Metriktyp und Attribution
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 40%

---

# Metriktyp und Attribution

Sie können den Metriktyp und [Attributionsmodell) für ](#attribution-models) Metrik in einer Definition einer berechneten Metrik konfigurieren.

1. Wählen ![Einstellung](/help/assets/icons/Setting.svg) in der Metrikkomponente aus.
1. Im Popup-Dialogfeld:

   ![Metriktyp und Attribution](assets/cm-type-alloc.png)

   * Geben Sie den **[!UICONTROL Metriktyp]** an:

     | Metriktyp | Definition |
     |---|---|
     | **[!UICONTROL Standard]** | Wenn eine Formel aus einer einzelnen Standardmetrik besteht, zeigt sie identische Daten für das nicht berechnete Metrik-Gegenstück an. Standardmetriken sind nützlich, um für jeden einzelnen Zeileneintrag spezifische berechnete Metriken zu erstellen. <p>Beispielsweise nimmt ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Teilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg)**[!UICONTROL Sitzungen]** die Bestellungen für diesen bestimmten Zeileneintrag und teilt ihn durch die Anzahl der Sitzungen für diesen bestimmten Zeileneintrag. |
     | **[!UICONTROL Gesamtsumme]** | Verwenden Sie **[!UICONTROL Gesamtsumme]** für den Berichtszeitraum in jedem Zeileneintrag. Wenn eine Formel aus einer einzelnen Gesamtsummenmetrik besteht, zeigt die berechnete Metrik dieselbe Gesamtsummenzahl für jeden Zeileneintrag an. Gesamtmetriken sind nützlich, wenn Sie berechnete Metriken erstellen möchten, die mit den Gesamtdaten verglichen werden. <p>Zum Beispiel zeigt ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Teilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg)**[!UICONTROL Total Sessions]** den Anteil der Bestellungen an allen Sitzungen, nicht nur an den Sitzungen für den bestimmten Zeileneintrag. In diesem Beispiel geben Sie **[!UICONTROL Gesamtsumme]** für die Metrik ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]** in Ihrer berechneten Metrik an, wodurch sie automatisch in ![](/help/assets/icons/Event.svg) Ereignis **[!UICONTROL Gesamtsitzungen]** umgewandelt wird. |

   * Geben Sie **[!UICONTROL Attribution]** an.

      1. Sie haben folgende Möglichkeiten:

         * Deaktivieren Sie **[!UICONTROL Nicht-standardmäßiges Attributionsmodell verwenden]**, um das standardmäßige Spalten-Attributionsmodell „Letztkontakt“ mit einem Lookback-Fenster von 30 Tagen zu verwenden.
         * Aktivieren **[!UICONTROL Nicht-standardmäßiges Attributionsmodell verwenden]**. Im Dialogfeld **[!UICONTROL Spalten-Attributionsmodell]**

            * Wählen Sie **[!UICONTROL Attributionsmodelle]** Modell“ aus.
            * Wählen Sie ein **[!UICONTROL Lookback-Fenster]** aus. Wenn Sie **[!UICONTROL Benutzerdefinierte Zeit]** auswählen, können Sie den Zeitraum in **[!UICONTROL Minute(n)]** bis zu **[!UICONTROL Quartal(en)]** definieren. Weitere Informationen finden [ unter ](#lookback-window)Lookback-Fenster)

      1. Wählen **[!UICONTROL Anwenden]**, um das nicht standardmäßige Attributionsmodell anzuwenden. Wählen Sie Abbrechen aus, um abzubrechen.

     Wenn Sie bereits ein nicht standardmäßiges Attributionsmodell definiert haben, wählen Sie **[!UICONTROL Bearbeiten]** aus, um die Auswahl zu ändern.

Ein [ für ](#example) Verwendung eines Attributionsmodells und eines Lookback-Fensters finden Sie unter „Beispiel“.


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Nicht standardmäßiges Attributionsmodell verwenden"
>abstract="Aktivieren Sie ein nicht standardmäßiges Attributionsmodell für die ausgewählte Metrik."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modell"
>abstract="Wählen Sie ein Attributionsmodell für die Metrik aus."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Letztkontakt"
>abstract="Die Credits gehen zu 100 % an den letzten Dimensionswert, den eine Besucherin bzw. ein Besucher gesehen hat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Erstkontakt"
>abstract="Die Credits gehen zu 100 % an den ersten Dimensionswert, den eine Besucherin bzw. ein Besucher gesehen hat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="Die Credits werden gleichmäßig auf alle Dimensionswerte verteilt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Beitrag"
>abstract="Die Credits gehen zu 100 % an jeden Dimensionswert, der von einer Besucherin oder einem Besucher gesehen wird.<br/>Spaltensummen werden erhöht."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Selber Kontakt"
>abstract="Die Credits werden nur für Dimensionswerte erteilt, die bei demselben Ereignis wie die Konversion auftreten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U-Form"
>abstract="Die Credits gehen zu zu 40 % an die erste Dimension, zu 40 % an die letzte und zu 20 % an die mittlere."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J-Kurve"
>abstract="Die Credits gehen zu zu 60 % an den letzten Dimensionswert, zu 20 % an den ersten und zu 20 % an den mittleren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="Umgekehrtes J"
>abstract="Die Credits gehen zu 60 % an den ersten Dimensionswert, zu 20 % an den letzten und zu 20 % an den mittleren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Zeitabfall"
>abstract="Die Dimensionswerte, die einer Konversion zeitlich am nächsten sind, erhalten die meisten Credits."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Anpassen"
>abstract="Definieren Sie Ihre eigene positionsbasierte Attributionsgewichtung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmisch"
>abstract="Die Credits werden anhand eines statistischen Algorithmus dynamisch bestimmt."

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### Lookback-Fenster {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Lookback-Fenster"
>abstract="Diese Einstellung bestimmt das Fenster der Datenattribution, das für jede Konversion angewendet wird."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### Attributionsbeispiel {#attribution-example}

Siehe folgendes Beispiel:

1. Am 15. September kommt eine Person über eine Paid-Search-Anzeige auf Ihre Website und verlässt sie.
1. Am 18. September kommt die Person über einen Social-Media-Link, den sie von einem Freund erhalten hat, wieder auf Ihre Website. Er fügt mehrere Artikel zum Warenkorb hinzu, erwirbt aber nichts.
1. Am 24. September sendet Ihr Marketing-Team eine E-Mail mit einem Coupon für einige der Artikel im Warenkorb. Der Coupon wird angewendet, der Besucher ruft aber mehrere andere Websites auf, um zu sehen, ob andere Coupons verfügbar sind. Er findet einen weiteren über eine Display-Anzeige und kauft dann letztendlich für 50 Euro ein.

Je nach Lookback-Fenster und Attributionsmodell erhalten Kanäle eine unterschiedliche Gewichtung. Im Folgenden finden Sie einige Beispiele:

* Mit **Erstkontakt** und einem **Sitzungs-Lookback-Fenster** betrachtet die Attribution nur den dritten Besuch. E-Mail kam vor Display-Anzeige, sodass E-Mail 100 % des Kaufs von 50 Euro zugeschrieben werden.

* Mit **Erstkontakt** und einem **Personen-Lookback-Fenster** untersucht die Attribution alle drei Besuche. Paid Search kam zuerst, sodass Paid Search 100 % des Kaufs von 50 Euro zugeschrieben werden.

* Mit **linear** und einem **Sitzungs-Lookback-Fenster** wird die Gutschrift auf E-Mail und Anzeige aufgeteilt. Beide Kanäle erhalten jeweils einen Kredit von 25 Dollar.
Bei Verwendung **linear** und eines **Personen-Lookback-Fensters** wird die Gutschrift auf Paid Search, Social, E-Mail und Display aufgeteilt. Jedem Kanal werden für diesen Kauf 12,50 Euro zugeschrieben.

* Mithilfe **J-förmigen** und eines **Personen-Lookback-Fensters** wird die Gutschrift auf Paid Search, Social, E-Mail und Display aufgeteilt.

   * Der Display-Anzeige werden 60 %, also 30 Euro, zugeschrieben.
   * Paid Search werden 20 %, also 10 Euro, zugeschrieben.
   * Die restlichen 20 % werden zwischen Social Media und E-Mail aufgeteilt (jeweils 5 Euro).

* Mithilfe **Zeitverfalls** und eines **Personen-Lookback-Fensters** wird die Gutschrift auf Paid Search, Social, E-Mail und Display aufgeteilt. Verwendung der standardmäßigen 7-Tage-Halbwertszeit:

   * Intervall von null Tagen zwischen Touchpoint-Display und Konversion. `2^(-0/7) = 1`
   * Lücke von null Tagen zwischen E-Mail-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Lücke von sechs Tagen zwischen Social Touchpoint und Konversion. `2^(-6/7) = 0.552`
   * Intervall von neun Tagen zwischen Paid Search-Touchpoint und Konversion. `2^(-9/7) = 0.41`
   * Die Normalisierung dieser Werte führt zu Folgendem:

      * Display-Anzeige: 33,8 %, 16,88 Euro
      * E-Mail: 33,8 %, 16,88 Euro
      * Social Media: 18,6 %, 9,32 Euro
      * Paid Search: 13,8 %, 6,92 Euro

Konversionsereignisse, die in der Regel Ganzzahlen aufweisen, werden aufgeteilt, wenn das Guthaben zu mehr als einem Kanal gehört. Wenn beispielsweise zwei Kanäle zu einer Reihenfolge beitragen, die ein lineares Attributionsmodell verwendet, erhalten beide Kanäle 0,5 dieser Reihenfolge. Diese partiellen Metriken werden für alle Personen summiert und dann zur Berichterstellung auf die nächste Ganzzahl gerundet.


>[!MORELIKETHIS]
>
>[Attribution - Komponenteneinstellungen](/help/data-views/component-settings/attribution.md)
>[Teilnahmemetrik](participation-metric.md)
>

