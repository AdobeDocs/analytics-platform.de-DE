---
title: Verhaltens-Komponenteneinstellungen
description: Geben Sie an, wie sich eine Dimension oder Metrik beim Reporting verhält.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/ra-O8TGxS6ByFEClZR7FtOnJ70YwclBiVMh9vubmGxk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 341
ht-degree: 100%

---

# Verhaltens-Komponenteneinstellungen {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="Verhalten"
>abstract="Gilt für Dimensions- und Metrikkomponenten. Bestimmen Sie, wie Zeileneinträge für diese Metrik aggregiert werden. Geben Sie an, ob Zeichenfolgenwerte für diese Dimension in Kleinbuchstaben sein sollen."

<!-- markdownlint-enable MD034 -->


Verhaltenseinstellungen sind sowohl für Dimensionen als auch für Metriken verfügbar. Die verfügbaren Einstellungen hängen vom Komponententyp und Schemadatentyp ab.

![Verhaltenseinstellungen](../assets/behavior-settings.png)

## Verhaltenseinstellungen für Dimensionen

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Kleinbuchstaben] | Dedupliziert Zeilen mit demselben Wert, aber unterschiedlicher Groß-/Kleinschreibung. Wenn diese Option aktiviert ist, werden alle Instanzen einer Dimension mit demselben Wert als Kleinbuchstaben gemeldet. Ihre Daten enthalten beispielsweise die Werte `"liverpool"`, `"Liverpool"` und `"LIVERPOOL"` in einer Zeichenfolgendimension. Wenn [!UICONTROL Kleinbuchstaben] aktiviert ist, werden alle drei Werte zu `"liverpool"` kombiniert. Wenn diese Option deaktiviert ist, werden alle drei Werte als unterschiedlich behandelt. |

{style="table-layout:auto"}

>[!NOTE]
>
>Wenn Sie [!UICONTROL Kleinbuchstaben] für eine Such-Datensatzdimension aktivieren, können für dieselbe Kennung mehrere Suchwerte vorhanden sein. In diesem Fall verwendet Customer Journey Analytics den ersten gesammelten ASCII-Wert (Werte in Großbuchstaben vor Kleinbuchstaben). Adobe rät davon ab, Such-Datensätze zu verwenden, die denselben Wert enthalten, wenn [!UICONTROL Kleinbuchstaben] aktiviert ist.

![Dimension mit Berücksichtigung von Groß-/Kleinschreibung](../assets/case-sens-workspace.png)

## Einstellungen für das Metrikverhalten

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Werte zählen] | Sichtbar bei Schemadatentypen vom Typ „Ganzzahl“ und „Doppelt“. Erhöhen Sie die Metrik um den angegebenen Betrag. Erhöht beispielsweise eine Metrik um 50, wenn der Wert der Spalte `50` lautet. |
| [!UICONTROL Instanzen zählen] | Sichtbar bei Schemadatentypen vom Typ „Ganzzahl“ und „Doppelt“. Erhöhen Sie die Metrik um eins, unabhängig vom Wert. Das Vorhandensein von Werten erhöht die Metrik. Erhöht beispielsweise eine Metrik um 1, wenn der Wert der Spalte `50` lautet. |
| [!UICONTROL Zu zählende Werte] | Sichtbar für boolesche Schemadatentypen. Ermöglicht es Ihnen, zu bestimmen, ob die Metrik durch die Zählung von `true`, `false` oder beiden zunimmt. |

{style="table-layout:auto"}

Sie können in Analysis Workspace sowohl die Metrik „Bestellungen“ als auch die Metrik „Umsatz“ generieren, indem Sie dieselbe Ereignis-Datensatzspalte mit unterschiedlichem Verhalten verwenden. Ziehen Sie die Datensatzspalte „Umsatz“ zweimal in die Datenansicht und legen Sie eine auf „Zählerwerte“ und die andere auf „Instanzen zählen“ fest. Die Metrik „Bestellungen“ zählt Instanzen, während die Metrik „Umsatz“ Werte zählt.
