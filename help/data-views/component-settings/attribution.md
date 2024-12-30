---
title: Attributions-Komponenteneinstellungen
description: Hier können Sie die Standardattribution für eine Metrik festlegen.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 29%

---

# Attributions-Komponenteneinstellungen {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_attribution"
>title="Attribution"
>abstract="Konfigurieren Sie das standardmäßige Attributionsmodell, das auf eine Metrik in Berichten angewendet wird."

<!-- markdownlint-enable MD034 -->


Mit Attribution können Sie anpassen, wie Dimensionselemente für Erfolgsereignisse angerechnet werden.

![Datenansichtsfenster mit hervorgehobener Option „Attribution festlegen“](../assets/attribution-settings.png)

z. B.:

1. Eine Person auf Ihrer Site klickt auf einen Paid Search-Link, um eine Ihrer Produktseiten aufzurufen. Er fügt das Produkt zum Warenkorb hinzu, kauft es jedoch nicht.
2. Am nächsten Tag sehen sie einen Social-Media-Beitrag von einem ihrer Freunde. Er klickt auf den Link und schließt den Kauf ab.

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

1. Wechseln Sie zur Datenansicht, die die Komponente enthält, deren standardmäßiges Attributionsmodell Sie aktualisieren möchten.

1. Wählen Sie die Komponente aus und erweitern Sie dann den Abschnitt Attribution auf der rechten Seite des Bildschirms.

   ![Datenansichtsfenster mit hervorgehobener Option „Attribution festlegen“](../assets/attribution-settings.png)

1. Wählen [!UICONTROL **Attribution festlegen**] und wählen Sie dann das Attributionsmodell [!UICONTROL **Dropdown-Menü Attributionsmodell**] aus.

   Unter [Attributionsmodelle](#attribution-models) erfahren Sie mehr über die einzelnen Attributionsmodelle.

1. Wählen Sie [!UICONTROL **Speichern und fortfahren**] aus.

>[!TIP]
>
>Wenn Ihr Unternehmen verlangt, dass eine Metrik über mehrere Attributionseinstellungen verfügt, können Sie einen der folgenden Schritte ausführen:
>
> * Kopieren Sie die Metrik in die Datenansicht mit jeder gewünschten Attributionseinstellung. Sie können dieselbe Metrik mehrmals in eine Datenansicht einbeziehen, sodass jede Metrik eine andere Einstellung erhält. Achten Sie darauf, jede Metrik entsprechend zu kennzeichnen, damit Analysten bei der Berichterstellung den Unterschied zwischen diesen Metriken verstehen.
>
> * Überschreiben Sie die Metrik in Analysis Workspace. Wählen Sie in den [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) einer Metrik **[!UICONTROL Nicht-Standard-Attributionsmodell verwenden]** um das Attributionsmodell und das Lookback-Fenster der Metrik für diesen spezifischen Bericht zu ändern.

## Attributionsmodelle {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataviews_component_attribution_attributionmodels"
>title="Modell"
>abstract="Wählen Sie ein Attributionsmodell für die Metrik aus."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Lookback-Fenster

{{attribution-lookback-window}}



## Attributionsbeispiel {#attribution-example}

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


