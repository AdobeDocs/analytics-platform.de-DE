---
description: Erfahren Sie mehr über Metriktyp und Attribution
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 2d182004b12eb44f54ec9b4b5f63cb9072594aec
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 100%

---

# Metriktyp und Attribution

Sie können den Metriktyp und das [Attributionsmodell](#attribution-models) für eine Metrik in der Definition einer berechneten Metrik konfigurieren.

1. Wählen Sie in der Metrikkomponente ![Einstellung](/help/assets/icons/Setting.svg) aus.
1. Im Popup-Dialogfeld:

   ![Metriktyp und Attribution](assets/cm-type-alloc.png)

   * Geben Sie den **[!UICONTROL Metriktyp]** an:

     | Metriktyp | Definition |
     |---|---|
     | **[!UICONTROL Standard]** | Wenn eine Formel aus einer einzelnen Standardmetrik besteht, zeigt sie die gleichen Daten wie das nicht berechnete Metrikgegenstück an. Standardmetriken eignen sich zum Erstellen berechneter Metriken, die speziell für die einzelnen Zeileneinträge gelten. <p>Zum Beispiel teilt ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]** die Bestellungen für diesen spezifischen Zeileneintrag durch die Anzahl der Sitzungen für diesen Spezifischen Zeileneintrag. |
     | **[!UICONTROL Gesamtsumme]** | Verwenden Sie die **[!UICONTROL Gesamtsumme]** für den Berichtszeitraum in jedem Zeileneintrag. Wenn eine Formel aus einer einzelnen Gesamtsummenmetrik besteht, zeigt sie dieselbe Gesamtsummenzahl für jeden Zeileneintrag an. Gesamtsummenmetriken sind hilfreich, wenn Sie berechnete Metriken erstellen möchten, die mit den Gesamtdaten verglichen werden. <p>Zum Beispiel zeigt ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen insgesamt]** den Anteil der Bestellungen für alle Sitzungen und nicht nur die Sitzungen für den speziellen Zeileneintrag an. In diesem Beispiel geben Sie die **[!UICONTROL Gesamtsumme]** für die ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]**-Metrik in Ihrer berechneten Metrik an, die sie automatisch in ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen insgesamt]** umwandelt. |

   * Geben Sie die **[!UICONTROL Attribution]** an.

      1. Sie haben folgende Möglichkeiten:

         * Deaktivieren Sie **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden]**, um das standardmäßige Spalten-Attributionsmodell Letztkontakt mit einem Lookback-Fenster von 30 Tagen zu verwenden.
         * Aktivieren Sie **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden]**. Im Dialogfeld **[!UICONTROL Attributionsmodell mit Spalten]**

            * wählen Sie ein **[!UICONTROL Modell]** aus den Attributionsmodellen aus.
            * Wählen Sie ein **[!UICONTROL Lookback-Fenster]** aus. Wenn Sie **[!UICONTROL Benutzerdefinierte Zeit]** auswählen, können Sie den Zeitraum in **[!UICONTROL Minute(n)]** bis zu **[!UICONTROL Quartal(e)]** festlegen. Weitere Informationen finden Sie im Abschnitt [Lookback-Fenster](#lookback-window)

      1. Wählen Sie **[!UICONTROL Anwenden]**, um das nicht standardmäßige Attributionsmodell anzuwenden. Wählen Sie zum Abbrechen die Option „Abbrechen“ aus.

     Wenn Sie bereits ein nicht standardmäßiges Attributionsmodell definiert haben, wählen Sie **[!UICONTROL Bearbeiten]** aus, um die Auswahl zu ändern.

Unter [Beispiel](#example) finden Sie ein Beispiel für die Verwendung eines Attributionsmodells und Lookback-Fensters.


## Attribution {#attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Nicht standardmäßiges Attributionsmodell verwenden"
>abstract="Aktivieren Sie ein nicht standardmäßiges Attributionsmodell für die ausgewählte Metrik."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modell"
>abstract="Wählen Sie ein Attributionsmodell für die Metrik aus."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Letztkontakt"
>abstract="Die Credits gehen zu 100 % an den letzten Dimensionswert, den eine Besucherin bzw. ein Besucher gesehen hat."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Erstkontakt"
>abstract="Die Credits gehen zu 100 % an den ersten Dimensionswert, den eine Besucherin bzw. ein Besucher gesehen hat."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="Die Credits werden gleichmäßig auf alle Dimensionswerte verteilt."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Beitrag"
>abstract="Die Credits gehen zu 100 % an jeden Dimensionswert, der von einer Besucherin oder einem Besucher gesehen wird.<br/>Spaltensummen werden erhöht."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Selber Kontakt"
>abstract="Die Credits werden nur für Dimensionswerte erteilt, die bei demselben Ereignis wie die Konversion auftreten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Selber Kontakt"
>abstract="Die Credits werden nur für Dimensionswerte erteilt, die bei demselben Ereignis wie die Konversion auftreten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U-Form"
>abstract="Die Credits gehen zu zu 40 % an die erste Dimension, zu 40 % an die letzte und zu 20 % an die mittlere."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J-Kurve"
>abstract="Die Credits gehen zu zu 60 % an den letzten Dimensionswert, zu 20 % an den ersten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J-Kurve"
>abstract="Die Credits gehen zu zu 60 % an den letzten Dimensionswert, zu 20 % an den ersten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="Umgekehrtes J"
>abstract="Die Credits gehen zu 60 % an den ersten Dimensionswert, zu 20 % an den letzten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="Umgekehrtes J"
>abstract="Die Credits gehen zu 60 % an den ersten Dimensionswert, zu 20 % an den letzten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Zeitabfall"
>abstract="Die Dimensionswerte, die einer Konversion zeitlich am nächsten sind, erhalten die meisten Credits."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Anpassen"
>abstract="Definieren Sie Ihre eigene positionsbasierte Attributionsgewichtung."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Anpassen"
>abstract="Definieren Sie Ihre eigene positionsbasierte Attributionsgewichtung."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmisch"
>abstract="Die Credits werden anhand eines statistischen Algorithmus dynamisch bestimmt."



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

Sehen Sie sich folgendes Beispiel an:

1. Am 15. September gelangt eine Person über eine Paid Search-Anzeige zu Ihrer Site und verlässt sie dann.
1. Am 18. September gelangt die Person über einen Link in sozialen Medien, den er von einer Freundin oder einem Freund erhalten hat, erneut auf Ihre Site. Er fügt mehrere Artikel zum Warenkorb hinzu, erwirbt aber nichts.
1. Am 24. September sendet Ihr Marketing-Team eine E-Mail mit einem Coupon für einige der Artikel im Warenkorb. Der Coupon wird angewendet, der Besucher ruft aber mehrere andere Websites auf, um zu sehen, ob andere Coupons verfügbar sind. Er findet einen weiteren über eine Display-Anzeige und kauft dann letztendlich für 50 Euro ein.

Je nach Lookback-Fenster und Attributionsmodell erhalten Kanäle eine unterschiedliche Gewichtung. Im Folgenden finden Sie einige Beispiele:

* Bei Verwendung von **Erstkontakt** und einem **Sitzungs-Lookback-Fenster** betrachtet die Attribution nur den dritten Besuch. E-Mail kam vor Display-Anzeige, sodass E-Mail 100 % des Kaufs von 50 US-Dollar zugeschrieben werden.

* Mithilfe von **Erstkontakt** und einem **Personen-Lookback-Fenster** betrachtet die Attribution alle drei Besuche. Paid Search kam zuerst, sodass Paid Search 100 % des Kaufs von 50 $ zugeschrieben werden.

* Bei Verwendung eines **linearen** Fensters und eines **Sitzungs-Lookback-Fensters** wird die Gewichtung zwischen E-Mail und Display-Anzeige aufgeteilt. Beiden Kanälen werden jeweils 25 $ zugeschrieben. Die Gewichtung wird mithilfe eines **linearen** Fensters und eines **Personen-Lookback-Fensters** zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Jedem Kanal werden für diesen Kauf 12,50 $ zugeschrieben.

* Mithilfe des **J-förmigen** Fensters und eines **Personen-Lookback-Fensters** wird die Gewichtung zwischen Paid Search, Social Media und Display-Anzeige aufgeteilt.

   * Der Display-Anzeige werden 60 %, also 30 Euro, zugeschrieben.
   * Paid Search werden 20 %, also 10 Euro, zugeschrieben.
   * Die restlichen 20 % werden zwischen Social Media und E-Mail aufgeteilt (jeweils 5 Euro).

* Bei Verwendung von **Zeitverfall** und einem **Personen-Lookback-Fenster** wird die Gewichtung zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Verwendung der standardmäßigen 7-Tage-Halbwertszeit:

   * Abstand von null Tagen zwischen Display-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Abstand von null Tagen zwischen E-Mail-Touchpoint und Konversion. `2^(-0/7) = 1`
   * Abstand von sechs Tagen zwischen Social Media-Touchpoint und Konversion. `2^(-6/7) = 0.552`
   * Abstand von 9 Tagen zwischen Paid Search-Touchpoint und Konversion. `2^(-9/7) = 0.41`
   * Die Normalisierung dieser Werte führt zu Folgendem:

      * Display-Anzeige: 33,8 %, 16,88 Euro
      * E-Mail: 33,8 %, 16,88 Euro
      * Social Media: 18,6 %, 9,32 Euro
      * Paid Search: 13,8 %, 6,92 Euro

Konversionsereignisse, die in der Regel Ganzzahlen aufweisen, werden aufgeteilt, wenn die Gewichtung mehr als einem Kanal zugeschrieben wird. Wenn beispielsweise zwei Kanäle mit einem linearen Attributionsmodell zu einer Bestellung beitragen, erhalten beide Kanäle 0,5 dieser Bestellung. Diese Teilmetriken werden über alle Personen summiert und dann zur Berichterstellung auf die nächste Ganzzahl gerundet.


>[!MORELIKETHIS]
>
>[Attribution – Komponenteneinstellungen](/help/data-views/component-settings/attribution.md)
>[Beitragsmetrik](participation-metric.md)
>

