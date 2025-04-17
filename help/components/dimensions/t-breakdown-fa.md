---
description: Schlüsseln Sie Dimensionen und Dimensionselemente in Analysis Workspace auf.
keywords: Analysis Workspace
title: Dimensionen aufschlüsseln
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 60%

---

# Aufschlüsseln von Dimensionen in Workspace

Sie können Ihre Daten für Ihre spezifischen Anforderungen unbegrenzt aufschlüsseln. Erstellen Sie Abfragen mithilfe relevanter Metriken, Dimensionen, Segmente, Zeitachsen und anderer Aufschlüsselungswerte für die Analyse.

1. Wählen [ in einer ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) aus dem Kontextmenü einer oder mehrerer ausgewählter Zeilen **[!UICONTROL Aufschlüsselung]** ![ChevronRight](/help/assets/icons/ChevronRight.svg).

   ![Schrittergebnis, das die Option Warnhinweis aus Auswahl erstellen anzeigt.](assets/breakdown.png)

1. Wählen Sie aus dem Untermenü **[!UICONTROL Dimensionen]**, **[!UICONTROL Metriken]**, **[!UICONTROL Filter]** oder **[!UICONTROL Datumsbereiche]** und wählen Sie dann ein Element aus.

Sie können Metriken nach Dimensionselementen oder Zielgruppensegmenten über ausgewählte Zeiträume aufschlüsseln. Sie können auch noch granularer aufschlüsseln.

>[!NOTE]
>
>Die Anzahl der in der Tabelle angezeigten Aufschlüsselungen ist auf 200 beschränkt. Dieses Limit erhöht sich beim Exportieren von Aufschlüsselungen.

## Aufschlüsselung nach Position

Standardmäßig sind Aufschlüsselungen an statische Zeilenelemente gebunden. Angenommen, Sie schlüsseln die drei oberen Elemente der Dimension „Seite“ (Startseite, Suchergebnisse, Checkout) nach Marketing-Kanälen auf. Dann verlassen Sie das Projekt und kehren zwei Wochen später zurück. Beim erneuten Öffnen des Projekts haben sich die drei oberen Seiten geändert, und jetzt sind Startseite, Suchergebnisse und Checkout stattdessen die oberen Seiten vier bis sechs. Standardmäßig werden Ihre Aufschlüsselungen des Marketing-Kanals weiterhin unter Startseite, Suchergebnisse und Checkout angezeigt, auch wenn sie sich jetzt in den Zeilen 4-6 befinden.

Im Gegensatz dazu werden **Aufschlüsselung nach Position** immer die drei obersten Elemente aufgeschlüsselt, unabhängig davon, was diese Elemente sind. Wenn Sie auf das Beispiel zurückgreifen, werden die Aufschlüsselungen des Marketing-Kanals beim erneuten Öffnen des Projekts an die drei obersten Seiten der Tabelle gebunden. Und nicht zu Homepage, Suchergebnissen und Checkout, die sich jetzt in den Zeilen 4-6 befinden. Siehe [Zeileneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) wie Sie diese Einstellung konfigurieren.



## Attributionsmodelle auf Aufschlüsselungen anwenden

Auf jede Aufschlüsselung innerhalb einer Tabelle kann auch ein beliebiges Attributionsmodell angewandt werden. Dieses Attributionsmodell kann mit der übergeordneten Spalte identisch sein oder sich von ihr unterscheiden. Sie können beispielsweise lineare Bestellungen in Ihrer Dimension „Marketing-Kanäle“ analysieren, jedoch U-förmige Bestellungen auf spezifische Trackingcodes in einem Kanal anwenden. Um das auf eine Aufschlüsselung angewendete Attributionsmodell zu bearbeiten, bewegen Sie die Maus über das Aufschlüsselungsmodell und wählen Sie **[!UICONTROL Bearbeiten]** aus.

![Vergleich der Reihenfolgenzuordnung mit den Aufschlüsselungseinstellungen](assets/breakdown-attribution.png)

Dies ist das erwartete Verhalten, wenn Attributionsmodelle auf Aufschlüsselungen angewendet oder bearbeitet werden:

* Wenn Sie eine Attribution anwenden und keine anderen Attributionen vorhanden sind, gilt die Attribution für die gesamte Spaltenstruktur.

* Wenn Sie eine Aufschlüsselung hinzufügen, nachdem eine Attribution angewendet wurde, wird für die hinzugefügte Aufschlüsselung der Standardwert verwendet (wenn diese Dimension einen Standardwert hat). Andernfalls wird die Aufschlüsselung aus der übergeordneten Spalte verwendet. Einige Dimensionen haben eine Standardzuordnung. Beispielsweise verwenden Zeitdimensionen und Referrer „Same Touch“. Die Dimension „Produkt“ verwendet „Last Touch“. Andere Dimensionen haben keinen Standardwert und verwenden die Zuordnung der übergeordneten Spalte.

* Wenn im Spaltenbaum bereits Zuordnungen vorhanden sind, wirkt sich eine Änderung der Zuordnung nur auf diejenige aus, die Sie gerade bearbeiten.

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension in Analysis Workspace](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Aufschlüsselungen nach Dimension](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Hinzufügen von Dimensionen und ](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"}) für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Arbeiten mit Dimensionen in einer Freiformtabelle](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Aufschlüsselung der Dimension nach Position](https://video.tv.adobe.com/v/24033){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]



