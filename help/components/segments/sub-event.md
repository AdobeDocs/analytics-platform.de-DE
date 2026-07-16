---
title: Analyse der Unterereignisse
description: Erfahren Sie, wie Sie mit der Analyse von Unterereignissen einzelne Produkte oder andere Container innerhalb eines Ereignisses in Customer Journey Analytics filtern können, wodurch Attributions-Anzapfungen in Produktberichten vermieden werden.
feature: Segmentation
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: babf5a87458103ca962113114d18b9dd8e1ab303
workflow-type: tm+mt
source-wordcount: 680
ht-degree: 8%

---

# Analyse der Unterereignisse

{{release-limited-testing}}

Mit der Analyse von Unterereignissen können Sie Ereignisdaten auf einer Ebene analysieren, die detaillierter ist als die Ereignisebene. Anstatt nach ganzen Ereignissen zu filtern, können Sie innerhalb von Ereignissen nach einzelnen Containern segmentieren. Beispiel:

* Segmentierung nach einer bestimmten Produktkategorie ohne Einbeziehung aller anderen in derselben Bestellung gekauften Produkte.
* Segmentieren nach einer bestimmten Asset-Kategorie in Inhaltsanalysedaten.
* Segmentierung in einem bestimmten Medienkanal in Media Analytics-Daten.

In Customer Journey Analytics definieren Sie Container in einer Datenansicht, für die Sie die Analyse von Unterereignissen verwenden möchten. Ohne Unterereignisanalyse gibt die Segmentierung nach einem Container-Elementattribut alle Ereignisse, Sitzungen, Personen, (globalen) Konten [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, Einkaufsgruppen [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, Opportunitys [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} oder andere [Container](/help/data-views/create-dataview.md#containers-1) zurück, die Sie definiert haben. Das Ergebnis ist eine falsche Attribution und überhöhte Umsatzmetriken. Die Unterereignisanalyse beschränkt den Filter auf einzelne Container-Zeilen innerhalb eines Ereignisses und löst diese Probleme.

In der Analyse von Unterereignissen verhält sich die Ausschlusslogik beim Container anders als der Ausschluss auf Standardereignisebene. Wenn Sie Elementattribute innerhalb des Containers ausschließen, gibt das Segment Ereignisse zurück **die zwar Elemente** Container enthalten, aber nicht Ihren Ausschlusskriterien entsprechen. Das Segment gibt keine Ereignisse ohne Elemente zurück.


## Beispiel

Sie möchten nur den Umsatz aus der Kategorie „Profi-Anzüge“ messen. Ohne Unterereignisanalyse umfasst das Anwenden eines Segments für professionelle Anzüge den Umsatz aus jedem Produkt für jede Bestellung (Ereignis), das mindestens ein Produkt mit der Kategorie „professionelle Anzüge“ enthält. Mit der Analyse von Unterereignissen können Sie den Filter auf die Produktebene beschränken und nur den Umsatz für Produkte der Kategorie Profi-Anzüge zurückgeben.

Sie möchten auch den Online-Umsatz aus allen anderen Kategorien mit Ausnahme der Kategorie „Profi-Anzüge“ messen.

>[!BEGINTABS]

>[!TAB Ereignisanalyse]

Im Segmentierungs-Builder oder als Teil eines **[!UICONTROL Schnellsegments]** geben Sie an, **[!UICONTROL **&#x200B;**&#x200B;Dimension]&#x200B;**&#x200B;**&#x200B;[!UICONTROL product_category]&#x200B;**&#x200B;**&#x200B;[!UICONTROL gleich]&#x200B;**&#x200B;**&#x200B;[!UICONTROL Professional Suites] **&#x200B; im &#x200B;** [!UICONTROL Events]**-Container einzuschließen.

![Panel mit Segmentierung auf Ereignisebene für die Produktkategorie Professional Suites](./assets/product-category-segmentation-events.png)

Als Ergebnis werden alle Bestellungen berücksichtigt, die mindestens eine **[!UICONTROL Professional]**&#x200B;**[!UICONTROL product_category]** enthalten, und der Umsatz aus anderen Produkten in diesen Bestellungen wird in die Metrik **[!UICONTROL Umsatz]** einbezogen.
Wenn Sie Berichte zu Kategorien erstellen, werden alle anderen Werte für **[!UICONTROL product_category]** gemeldet, die Teil einer Bestellung waren, die ein Produkt der **[!UICONTROL Professional Suites]**&#x200B;**[!UICONTROL product_category]**.

>[!TAB Analyse von Unterereignissen]

Sie haben einen **&#x200B;**&#x200B;[&#x200B; benutzerdefinierten Container](/help/data-views/create-dataview.md#containers) in Ihrer Datenansicht für die Analyse von Unterereignissen zu Produkten definiert.

![Container mit Produktdetails](assets/product-details-container.png)

Im Segmentierungs-Builder oder als Teil eines **[!UICONTROL Schnellsegments]** geben Sie **&#x200B;**&#x200B;**[!UICONTROL Dimension]** **&#x200B;**&#x200B;product_category **&#x200B;**&#x200B;equals **[!UICONTROL Professional Suites]** im **[!UICONTROL Product Details]**-Container an.

![Panel, das die Segmentierung auf der Ebene der Unterveranstaltungen für die Produktkategorie Professional Suites anzeigt](./assets/product-category-segmentation-subevents.png)

Als Ergebnis werden alle Bestellungen berücksichtigt, die mindestens **[!UICONTROL Professional Suites]** **[!UICONTROL product_category]** enthalten, und nur der Umsatz von Produkten, die zur **[!UICONTROL Professional Suites]**&#x200B;**[!UICONTROL product_category]** gehören, wird in die Metrik **[!UICONTROL Revenue]** einbezogen.
Wenn Sie Berichte zu Kategorien erstellen, wird nur die **[!UICONTROL Professional Suites]** **[!UICONTROL product_category]** angezeigt.

>[!TAB Analyse von Unterereignissen (ausschließen)]

Sie haben einen **&#x200B;**&#x200B;[&#x200B; benutzerdefinierten Container](/help/data-views/create-dataview.md#containers) in Ihrer Datenansicht für die Analyse von Unterereignissen zu Produkten definiert.

![Container mit Produktdetails](assets/product-details-container.png)

Im Segmentierungs-Builder oder als Teil eines **[!UICONTROL Schnellsegments]** geben Sie an, **[!UICONTROL &lbrace;4]** Dimension **&#x200B;**[!UICONTROL &#x200B; product_category &#x200B;]**&#x200B;gleich**[!UICONTROL **&#x200B;**&#x200B;Professional Suites &#x200B;]&#x200B;**im**&#x200B;[!UICONTROL &#x200B; Product Details &#x200B;]&#x200B;**-Container auszuschließen.**

![Bedienfeld, das die Segmentierung auf der Ebene untergeordneter Treffer anzeigt, um die Produktkategoriemänner auszuschließen](./assets/product-category-segmentation-subevents-exclude.png)

Um auf Produktebene Ereignisse auszuschließen, die mindestens ein Produkt enthalten, wird der Ausschluss auf der Ebene der Unterereignisse innerhalb dieses Bereichs angewendet. Dieser Ausschluss unterscheidet sich vom Ausschluss auf Ereignisebene, wodurch das gesamte Ereignis ausgeschlossen wird.

>[!ENDTABS]
