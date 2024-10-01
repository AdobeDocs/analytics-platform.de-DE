---
description: Erfahren Sie mehr über Metriktyp und Attribution
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 26%

---

# Metriktyp und Attribution

Sie können den Metriktyp und das [Attributionsmodell](#attribution-models) für eine Metrik in einer Definition für berechnete Metriken konfigurieren.

1. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) in der Metrikkomponente aus.
1. Im Popup-Dialogfeld:

   ![Metriktyp und Attribution](assets/cm-type-alloc.png)

   * Geben Sie den **[!UICONTROL Metriktyp]** an:

     | Metriktyp | Definition |
     |---|---|
     | **[!UICONTROL Standard]** | Wenn eine Formel aus einer einzelnen Standardmetrik besteht, werden identische Daten mit dem nicht berechneten Metrik-Gegenstück angezeigt. Standardmetriken sind nützlich, um berechnete Metriken zu erstellen, die für jeden einzelnen Zeileneintrag spezifisch sind. <p>Beispiel: ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Aufteilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]** gibt die Bestellungen für diesen Zeileneintrag aus und teilt ihn durch die Anzahl Sitzungen für diesen Zeileneintrag. |
     | **[!UICONTROL Gesamtsumme]** | Verwenden Sie in jedem Zeileneintrag **[!UICONTROL Gesamtsumme]** für den Berichtszeitraum. Wenn eine Formel aus einer einzelnen Gesamtsumme-Metrik besteht, zeigt die berechnete Metrik für jeden Zeileneintrag dieselbe Gesamtsumme an. Gesamtmetriken sind nützlich, wenn Sie berechnete Metriken erstellen möchten, die mit Gesamtdaten vergleichen. <p>Beispielsweise zeigt ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Aufteilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Gesamtsitzungen]** den Anteil der Bestellungen für alle Sitzungen, nicht nur die Sitzungen für den jeweiligen Zeileneintrag. In diesem Beispiel geben Sie **[!UICONTROL Gesamtsumme]** für die Metrik ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]** in Ihrer berechneten Metrik an, wodurch sie automatisch in ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Gesamtsitzungen]** umgewandelt wird. |

   * Geben Sie **[!UICONTROL Attribution]** an.

      1. Sie haben die Möglichkeit zum:

         * Deaktivieren Sie **[!UICONTROL Verwenden Sie nicht standardmäßiges Attributionsmodell]**, um das standardmäßige Spaltenattributionsmodell &quot;Letztkontakt&quot;mit einem Lookback-Fenster von 30 Tagen zu verwenden.
         * Aktivieren Sie **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]**. Im Dialogfeld **[!UICONTROL Spaltenattributionsmodell]**

            * Wählen Sie ein **[!UICONTROL Modell]** aus den Attributionsmodellen aus.
            * Wählen Sie ein **[!UICONTROL Lookback-Fenster]** aus. Wenn Sie **[!UICONTROL Benutzerdefinierte Zeit]** auswählen, können Sie den Zeitraum in **[!UICONTROL Minute(n)]** bis zu **[!UICONTROL Quartal(en)]** definieren. Weitere Informationen finden Sie unter [Lookback-Fenster](#lookback-window) .

      1. Wählen Sie **[!UICONTROL Anwenden]** aus, um das nicht standardmäßige Attributionsmodell anzuwenden. Wählen Sie Abbrechen aus, um abzubrechen.

     Wenn Sie bereits ein nicht standardmäßiges Attributionsmodell definiert haben, wählen Sie **[!UICONTROL Bearbeiten]** aus, um die Auswahl zu ändern.

Ein Beispiel für die Verwendung eines Attributionsmodells und Lookback-Fensters finden Sie unter [Beispiel](#example) .


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_nondefaultattributionmodel"
>title="Nicht standardmäßiges Attributionsmodell verwenden"
>abstract="Aktivieren eines nicht standardmäßigen Attributionsmodells für die ausgewählte Metrik."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attributionmodel"
>title="Modell"
>abstract="Wählen Sie ein Attributionsmodell für die Metrik."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lasttouch"
>title="Letztkontakt"
>abstract="100 % der Gutschrift geht an den letzten Dimensionswert, den ein Besucher gesehen hat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_firsttouch"
>title="Erstkontakt"
>abstract="100 % der Gutschrift geht an den ersten Dimensionswert, den ein Besucher gesehen hat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="Die Gewichtung wird gleichmäßig über alle Dimensionswerte verteilt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_participation"
>title="Beitrag"
>abstract="100 % Gewichtung für jeden Dimensionswert, der von einem Besucher gesehen wird.<br/>Spaltensummen werden überschrieben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_sametouch"
>title="Selber Kontakt"
>abstract="Die Gewichtung wird nur Dimensionswerten zugeschrieben, die bei demselben Ereignis wie die Konversion auftreten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_ushaped"
>title="U-Form"
>abstract="Der ersten Dimension werden 40 % zugeschrieben, dem letzten 40 %, dem mittleren 20 %."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_jcurve"
>title="J-Kurve"
>abstract="60 % werden dem letzten Dimensionswert zugeschrieben, 20 % dem ersten, 20 % von der Mitte."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_inversej"
>title="Umgekehrtes J"
>abstract="Der ersten Dimension werden 60 %, der letzten 20 % und der mittleren 20 % zugeschrieben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_timedecay"
>title="Zeitverlauf"
>abstract="Die zeitlich am nächsten zu einer Konversion liegenden Dimensionswerte erhalten die höchste Anrechnung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_custom"
>title="Zeitverlauf"
>abstract="Die zeitlich am nächsten zu einer Konversion liegenden Dimensionswerte erhalten die höchste Anrechnung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmisch"
>abstract="Die Gewichtung wird anhand eines statistischen Algorithmus dynamisch bestimmt."

<!-- markdownlint-enable MD034 -->



{{attribution-models-details}}


### Lookback-Fenster {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lookbackwindow"
>title="Lookback-Fenster"
>abstract="Diese Einstellung bestimmt das Fenster der Datenzuordnung, das für jede Konversion angewendet wird."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### Beispiel für Attribution {#attribution-example}

Siehe folgendes Beispiel:

1. Am 15. September gelangt eine Person über eine gebührenpflichtige Suchanzeige zu Ihrer Site und verlässt sie dann.
1. Am 18. September gelangt die Person erneut über einen Link in sozialen Medien zu Ihrer Site, den sie von einem Freund erhalten hat. Er fügt mehrere Artikel zum Warenkorb hinzu, erwirbt aber nichts.
1. Am 24. September sendet Ihr Marketing-Team eine E-Mail mit einem Coupon für einige der Artikel im Warenkorb. Der Coupon wird angewendet, der Besucher ruft aber mehrere andere Websites auf, um zu sehen, ob andere Coupons verfügbar sind. Er findet einen weiteren über eine Display-Anzeige und kauft dann letztendlich für 50 Euro ein.

Je nach Lookback-Fenster und Attributionsmodell erhalten Kanäle eine unterschiedliche Gewichtung. Im Folgenden finden Sie einige Beispiele:

* Bei Verwendung von **Erstkontakt** und einem **Sitzungs-Lookback-Fenster** betrachtet die Attribution nur den dritten Besuch. E-Mail kam vor Display-Anzeige, sodass E-Mail 100 % des Kaufs von 50 Euro zugeschrieben werden.

* Mithilfe von **Erstkontakt** und einem **Personen-Lookback-Fenster** betrachtet die Attribution alle drei Besuche. Paid Search kam zuerst, sodass Paid Search 100 % des Kaufs von 50 Euro zugeschrieben werden.

* Bei Verwendung von **linear** und einem **Sitzungs-Lookback-Fenster** wird die Gewichtung zwischen E-Mail und Anzeige aufgeteilt. Beiden Kanälen werden jeweils 25 USD gutgeschrieben.
Bei Verwendung von **linear** und einem **Personen-Lookback-Fenster** wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Jedem Kanal werden für diesen Kauf 12,50 Euro zugeschrieben.

* Bei Verwendung von **J-förmig** und einem **Personen-Lookback-Fenster** wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt.

   * Der Display-Anzeige werden 60 %, also 30 Euro, zugeschrieben.
   * Paid Search werden 20 %, also 10 Euro, zugeschrieben.
   * Die restlichen 20 % werden zwischen Social Media und E-Mail aufgeteilt (jeweils 5 Euro).

* Bei Verwendung von **Zeitverfall** und einem **Personen-Lookback-Fenster** wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Verwendung der standardmäßigen 7-Tage-Halbwertszeit:

   * Abstand von null Tagen zwischen Display-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Abstand von null Tagen zwischen E-Mail-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Abstand von sechs Tagen zwischen Social Touch-Point und Konversion. `2^(-6/7) = 0.552`
   * Abstand von neun Tagen zwischen Paid-Search-Touchpoint und Konversion. `2^(-9/7) = 0.41`
   * Die Normalisierung dieser Werte führt zu Folgendem:

      * Display-Anzeige: 33,8 %, 16,88 Euro
      * E-Mail: 33,8 %, 16,88 Euro
      * Social Media: 18,6 %, 9,32 Euro
      * Paid Search: 13,8 %, 6,92 Euro

Konversionsereignisse, die normalerweise ganze Zahlen aufweisen, werden aufgeteilt, wenn die Gewichtung für mehrere Kanäle erfolgt. Wenn beispielsweise zwei Kanäle mit einem linearen Attributionsmodell zu einer Bestellung beitragen, erhalten beide Kanäle 0,5 dieser Reihenfolge. Diese partiellen Metriken werden über alle Personen summiert und dann zur Berichterstellung auf die nächste Ganzzahl gerundet.


>[!MORELIKETHIS]
>
>[Einstellungen der Zuordnungskomponente](/help/data-views/component-settings/attribution.md)
>[Beitragsmetrik](participation-metric.md)
>

