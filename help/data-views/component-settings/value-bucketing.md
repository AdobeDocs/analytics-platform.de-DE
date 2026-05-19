---
title: Komponenteneinstellungen für Wert-Bucketing
description: Kombinieren Sie numerische Werte in einer Dimension.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:00.872Z'
TQID: 'https://experienceleague.adobe.com/LHEk3h9utGW73kSo2-SgY5NgKi11uktKR0ucPxw9IcY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# Komponenteneinstellungen für [!UICONTROL Wert-Bucketing] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="Bucketing von Werten"
>abstract="Verteilen Sie Werte in bestimmte Bucket-Bereiche. Diese Bereiche werden in Berichten als Dimensionselemente angezeigt."

<!-- markdownlint-enable MD034 -->


Beim Erstellen oder Bearbeiten einer Datenansicht können Sie mit Wert-Bucketing numerische Werte basierend auf einem Bereich kombinieren. Sie ist nur für Dimensionen verfügbar, die Schemadatentypen vom Typ „Ganzzahl“ oder „Doppelt“ verwenden.

![Wert-Bucketing](../assets/value-bucketing.png)

Wert-Bucketing ist nützlich, wenn Sie Bereiche gruppieren möchten, anstatt jede eindeutige Zahl als ein separates Dimensionselement zu behandeln. Ein Behälter von „zwischen 5 und 10“ wird beispielsweise in Analysis Workspace als ein Zeilenelement „5 bis 10“ angezeigt.

Wenn Sie die Flexibilität beim Reporting für eine Dimension mit und ohne Behälter Dimension wünschen, ziehen Sie zwei Kopien der Komponente in die Liste der verfügbaren Dimensionen. Aktivieren Sie Bucketing für eine Dimension und deaktivieren Sie es für die andere.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Bucket-Wert] | Ein Kontrollkästchen, mit dem Sie Bucketing aktivieren können. |
| [!UICONTROL Kleiner als] | Die obere Grenze des ersten Dimensionsbehälters. |
| [!UICONTROL Einschließlich] [!UICONTROL und weniger als] | Grenzen der nachfolgenden Behälter. |
| [!UICONTROL Größer oder gleich] | Die untere Grenze des letzten Dimensionsbehälters. |
| [!UICONTROL Bucket hinzufügen] | Ermöglicht das Hinzufügen eines weiteren Behälters zu numerischen Dimensionsbehältern. Sie können bis zu 20 Behälter in einer Dimension hinzufügen. |

{style="table-layout:auto"}
