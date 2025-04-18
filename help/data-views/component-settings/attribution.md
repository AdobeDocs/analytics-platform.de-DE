---
title: Attributions-Komponenteneinstellungen
description: Hier können Sie die Standardattribution für eine Metrik festlegen.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: ht
source-wordcount: '847'
ht-degree: 100%

---

# Attributions-Komponenteneinstellungen {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Attribution"
>abstract="Konfigurieren Sie das standardmäßige Attributionsmodell, das auf eine Metrik in Berichten angewendet wird."

<!-- markdownlint-enable MD034 -->


Attribution ermöglicht die Anpassung der Anrechnung von Dimensionselementen für Erfolgsereignisse.

![Datenansichtsfenster mit hervorgehobener Option Attribution festlegen](../assets/attribution-settings.png)

Zum Beispiel:

1. Eine Person au Ihrer Site klickt auf einen Paid Search-Link zu einer Ihrer Produktseiten. Sie fügt das Produkt zum Warenkorb hinzu, kauft es jedoch nicht.
2. Am nächsten Tag sieht sie einen Social Media-Beitrag von einer Freundin bzw. einem Freund. Sie klickt auf den Link und schließt den Kauf ab.

In einigen Berichten möchten Sie die Bestellung eventuell Paid Search zuordnen. In anderen Berichten möchten Sie die Bestellung eventuell Social Media zuordnen. Mithilfe von Attribution können Sie diesen Aspekt der Berichterstattung steuern.

## Festlegen des standardmäßigen Attributionsmodells einer Komponente

Sie können ein standardmäßiges Attributionsmodell für eine bestimmte Metrik festlegen, indem Sie die Einstellung der Metrik in der Datenansicht aktualisieren. Dadurch wird das Attributionsmodell der Metrik bei jeder Verwendung in Analysis Workspace überschrieben.

>[!NOTE]
>
>Beachten Sie beim Aktivieren der Attribution für eine Metrik Folgendes:
>
>* **Bei Verwendung der Komponente in einem Bericht mit *einer einzelnen Dimension*:** Die Attribution der Komponente ignoriert das Zuordnungsmodell, wenn ein nicht standardmäßiges Attributionsmodell verwendet wird.
>
>* **Bei Verwendung der Komponente in einem Bericht mit *mehreren Dimensionen*:** Die Attribution der Komponente behält das Zuordnungsmodell bei, wenn ein nicht standardmäßiges Attributionsmodell verwendet wird.
>
>   Mehrere Dimensionen sind nur beim [Exportieren von Daten in die Cloud](/help/analysis-workspace/export/export-cloud.md) verfügbar.
>
> Weitere Informationen zur Zuordnung finden Sie unter [Persistenz - Komponenteneinstellungen](/help/data-views/component-settings/persistence.md).

So aktualisieren Sie das standardmäßige Attributionsmodell einer Komponente:

1. Wechseln Sie zu zur Datenansicht mit der Komponente, deren standardmäßiges Attributionsmodell Sie aktualisieren möchten.

1. Wählen Sie die Komponente aus und erweitern Sie dann den Abschnitt Attribution auf der rechten Seite des Bildschirms.

   ![Datenansichtsfenster mit hervorgehobener Option Attribution festlegen](../assets/attribution-settings.png)

1. Wählen Sie [!UICONTROL **Attribution festlegen**] und wählen Sie dann das Attributionsmodell im Dropdown-Menü [!UICONTROL **Attributionsmodell**] aus.

   Unter [Attributionsmodelle](#attribution-models) erfahren Sie mehr über die einzelnen Attributionsmodelle.

1. Wählen Sie [!UICONTROL **Speichern und fortfahren**] aus.

>[!TIP]
>
>Wenn Ihre Organisation verlangt, dass eine Metrik über mehrere Attributionseinstellungen verfügt, können Sie einen der folgenden Schritte ausführen:
>
> * Kopieren Sie die Metrik in die Datenansicht mit jeder gewünschten Attributionseinstellung. Sie können dieselbe Metrik mehrmals in eine Datenansicht einschließen, sodass jede Metrik eine andere Einstellung erhält. Achten Sie darauf, jede Metrik entsprechend zu kennzeichnen, damit Analystinnen und Analysten bei der Berichterstellung den Unterschied zwischen diesen Metriken erkennen.
>
> * Überschreiben Sie die Metrik in Analysis Workspace. Wählen Sie in den [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) einer Metrik **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden]** aus, um das Attributionsmodell und das Lookback-Fenster der Metrik für diesen spezifischen Bericht zu ändern.

## Attributionsmodelle {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modell"
>abstract="Wählen Sie ein Attributionsmodell für die Metrik aus."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Lookback-Fenster

{{attribution-lookback-window}}



## Attributionsbeispiel {#attribution-example}

Sehen Sie sich folgendes Beispiel an:

1. Am 15. September gelangt eine Person über eine Paid Search-Anzeige zu Ihrer Site und verlässt sie dann.
1. Am 18. September gelangt die Person über einen Link in sozialen Medien, den er von einer Freundin oder einem Freund erhalten hat, erneut auf Ihre Site. Er fügt mehrere Artikel zum Warenkorb hinzu, erwirbt aber nichts.
1. Am 24. September sendet Ihr Marketing-Team eine E-Mail mit einem Coupon für einige der Artikel im Warenkorb. Der Coupon wird angewendet, der Besucher ruft aber mehrere andere Websites auf, um zu sehen, ob andere Coupons verfügbar sind. Er findet einen weiteren über eine Display-Anzeige und kauft dann letztendlich für 50 Euro ein.

Je nach Lookback-Fenster und Attributionsmodell erhalten Kanäle eine unterschiedliche Gewichtung. Im Folgenden finden Sie einige Beispiele:

* Bei Verwendung von **Erstkontakt** und einem **Sitzungs-Lookback-Fenster** betrachtet die Attribution nur den dritten Besuch. E-Mail kam vor Display-Anzeige, sodass E-Mail 100 % des Kaufs von 50 US-Dollar zugeschrieben werden.

* Mithilfe von **Erstkontakt** und einem **Personen-Lookback-Fenster** betrachtet die Attribution alle drei Besuche. Paid Search kam zuerst, sodass Paid Search 100 % des Kaufs von 50 $ zugeschrieben werden.

* Bei Verwendung eines **linearen** Fensters und eines **Sitzungs-Lookback-Fensters** wird die Gewichtung zwischen E-Mail und Display-Anzeige aufgeteilt. Beiden Kanälen werden jeweils 25 $ zugeschrieben.
Die Gewichtung wird mithilfe eines **linearen** Fensters und eines **Personen-Lookback-Fensters** zwischen Paid Search, Social Media, E-Mail und Display-Anzeige aufgeteilt. Jedem Kanal werden für diesen Kauf 12,50 $ zugeschrieben.

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


