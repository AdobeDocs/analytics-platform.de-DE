---
title: Analyse der Unterereignisse
description: Erfahren Sie, wie Sie mit der Analyse von Unterereignissen einzelne Produkte oder andere Container innerhalb eines Ereignisses in Customer Journey Analytics filtern können, wodurch Attributions-Anzapfungen in Produktberichten vermieden werden.
feature: Segmentation
hold: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: b4bec7c8e476bc2dbffce42bd52ff535b90dcb86
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 0%

---

# Analyse der Unterereignisse

{{release-limited-testing}}

Mit der Analyse von Unterereignissen können Sie Ereignisdaten auf einer Ebene analysieren, die detaillierter ist als die Ereignisebene. Anstatt das gesamte Ereignis zu filtern, können Sie innerhalb von Ereignissen einzelne Container segmentieren. Beispiel:

- Segmentierung nach einer bestimmten Produktkategorie ohne Einbeziehung aller anderen in derselben Bestellung gekauften Produkte
- Segmentieren Sie in Inhaltsanalysedaten nach einer bestimmten Asset-Kategorie?
- Segmentieren in einem bestimmten Medienkanal in Media Analytics-Daten.


In Customer Journey Analytics definieren Sie Container in einer Datenansicht, für die Sie die Analyse von Unterereignissen verwenden möchten. Ohne Analyse von Unterereignissen gibt die Segmentierung für ein Container-Elementattribut alle Ereignisse zurück, bei denen ein Element innerhalb eines Ereignisses mit dem Container-Elementattribut übereinstimmt. Das Ergebnis ist eine falsche Attribution und überhöhte Umsatzmetriken. Die Unterereignisanalyse berechnet den Filter auf einzelne Elementzeilen innerhalb eines Ereignisses und löst diese Probleme.

In der Analyse von Unterereignissen verhält sich die Ausschlusslogik anders als der standardmäßige Ausschluss auf Ereignisebene gegenüber dem Container. Wenn Sie Elementattribute innerhalb des Containers ausschließen, gibt das Segment Ereignisse zurück **die zwar Elemente** Container enthalten, aber nicht Ihren Ausschlusskriterien entsprechen. Das Segment gibt kein Ereignis ohne Elemente zurück.


## Beispiel

Sie möchten nur den Umsatz aus der Kategorie „Professional Suites“ messen. Ohne Unterereignisanalyse umfasst das Anwenden eines Segments für professionelle Anzüge den Umsatz aus jedem Produkt für jede Bestellung (Ereignis), das mindestens ein Produkt mit der Kategorie „professionelle Anzüge“ enthält. Mit der Analyse von Unterereignissen können Sie den Filter auf die Produktebene beschränken und nur den Umsatz für Produkte der Kategorie Profi-Anzüge zurückgeben.

Sie möchten auch den Online-Umsatz aller anderen Kategorien mit Ausnahme der Kategorie „Männer“ messen.

>[!BEGINTABS]

>[!TAB Ereignisanalyse]

Im Segmentierungs-Builder oder als Teil eines **[!UICONTROL Schnellsegments]** geben Sie an, **[!UICONTROL **&#x200B;**&#x200B;Dimension]&#x200B;**&#x200B;**&#x200B;[!UICONTROL product_category]&#x200B;**&#x200B;**&#x200B;[!UICONTROL gleich]&#x200B;**&#x200B;**&#x200B;[!UICONTROL Professional Suites] **&#x200B; im &#x200B;** [!UICONTROL Events]**-Container einzuschließen.

![Panel mit Segmentierung auf Ereignisebene für die Produktkategorie Professional Suites](./assets/product-category-segmentation-events.png)

Als Ergebnis werden alle Bestellungen berücksichtigt, die mindestens eine **[!UICONTROL Professional]**&#x200B;**[!UICONTROL product_category]** enthalten, und der Umsatz aus anderen Produkten in diesen Bestellungen wird in die Metrik **[!UICONTROL Umsatz]** einbezogen.Wenn Sie Berichte zu Kategorien erstellen, werden alle anderen Werte für **[!UICONTROL product_category]** gemeldet, die Teil einer Bestellung waren, die ein Produkt der **[!UICONTROL Professional Suites]**&#x200B;**[!UICONTROL product_category]**.

>[!TAB Analyse von Unterereignissen]

Im Segmentierungs-Builder oder als Teil eines **[!UICONTROL Schnellsegments]** geben Sie an, **[!UICONTROL &lbrace;4]** Dimension **&#x200B;**&#x200B;[!UICONTROL &#x200B; product_category &#x200B;]&#x200B;**&#x200B;**&#x200B;[!UICONTROL &#x200B; gleich &#x200B;]&#x200B;**&#x200B;**&#x200B;[!UICONTROL &#x200B; Professional Suites &#x200B;]&#x200B;**im**&#x200B;[!UICONTROL &#x200B; products &#x200B;]&#x200B;**-Container einzuschließen.**

![Panel, das die Segmentierung auf der Ebene der Unterveranstaltungen für die Produktkategorie Professional Suites anzeigt](./assets/product-category-segmentation-subevents.png)

Als Ergebnis werden alle Bestellungen berücksichtigt, die mindestens **[!UICONTROL Professional Suites]** **[!UICONTROL product_category]** enthalten, und nur der Umsatz von Produkten, die zur **[!UICONTROL Professional Suites]**&#x200B;**[!UICONTROL product_category]** gehören, wird in die Metrik **[!UICONTROL Revenue]** einbezogen.Wenn Sie Berichte zu Kategorien erstellen, wird nur die **[!UICONTROL Professional]**&#x200B;**[!UICONTROL Rproduct_category]** angezeigt.

>[!TAB Analyse von Unterereignissen (ausschließen)]

Im Segmentierungs-Builder oder als Teil eines **[!UICONTROL Schnellsegments]** geben Sie an, **[!UICONTROL &lbrace;4]** Dimension **&#x200B;**&#x200B;[!UICONTROL &#x200B; product_category &#x200B;]&#x200B;**&#x200B;**&#x200B;**gleich**&#x200B;**im**&#x200B;[!UICONTROL &#x200B; products &#x200B;]&#x200B;**-Container auszuschließen.**

![Bedienfeld, das die Segmentierung auf der Ebene untergeordneter Treffer anzeigt, um die Produktkategoriemänner auszuschließen](./assets/product-category-segmentation-subevents-exclude.png)

Um auf Produktebene Ereignisse auszuschließen, die mindestens ein Produkt enthalten, wird der Ausschluss auf der Ebene der Unterereignisse innerhalb dieses Bereichs angewendet. Dieser Ausschluss unterscheidet sich vom Ausschluss auf Ereignisebene, wodurch das gesamte Ereignis ausgeschlossen wird.

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
