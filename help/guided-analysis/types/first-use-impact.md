---
title: Wirkungsanalyse der ersten Verwendung
description: Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 6%

---

# Analyse [!UICONTROL Wirkung der ersten Verwendung] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_firstuseimpact_button"
>title="Wirkung der ersten Verwendung"
>abstract="Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren."

<!-- markdownlint-enable MD034 -->

Die Analyse ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL First Use Impact]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren, bevor und nachdem ein Benutzer zum ersten Mal eine Produktfunktion verwendet hat. Die horizontale Achse dieses Berichts ist ein relatives Zeitintervall vor und nach dem Ereignis, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms stellt den Tag 0 für den Zeitpunkt dar, zu dem eine Funktion von einem bestimmten Benutzer zum ersten Mal verwendet wird. Da Benutzer nicht immer Funktionen am selben Tag übernehmen und Ihre Rollouts möglicherweise über mehrere Tage erfolgen können, kann Tag 0 für jeden einzelnen Benutzer etwas Anderes bedeuten.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)


## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Analyse neuer Funktionen**: Wenn Sie eine neue Funktion in Ihrem Produkt starten, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der erstmaligen Anzeige der neuen Funktion durch die Benutzer abgeschnitten wurden.
* **Schrittweise Rollouts**: Da die Analyse nach der ersten Verwendung der Funktion und nicht nach einem festen Datum sucht, ist diese Analyse hilfreich, wenn Sie die Einführung Ihrer Funktionen im Laufe der Zeit schrittweise planen.
* **Neue Analyse der Produktversion**: Wenn Sie eine neue Version Ihres Produkts starten, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der erstmaligen Anzeige der neuen Version durch die Benutzer abliefen. Wählen Sie &quot;Beliebiges Ereignis&quot;als Erstes aus und filtern Sie es nach der Eigenschaft Versionsnummer .
* **Verbesserungen vorhandener Funktionen**: Wenn Sie Verbesserungen an einer vorhandenen Funktion in Ihrem Produkt vornehmen, können Sie vergleichen, wie wichtige Indikatoren vor und nach der erstmaligen Anzeige der Benutzer für diese neuen Verbesserungen durchgeführt wurden. Sie können diese Analyse auf eine oder mehrere Arten durchführen, je nach Funktionsinstrumentierung.
   * Wählen Sie ein Ereignis aus, das die Verbesserung als Ihr Erstverwendungsereignis darstellt
   * Wählen Sie das Datum aus, an dem die Änderungen eingeführt wurden
   * Segmentieren Sie die Analyse der Gruppe von Personen, die den Verbesserungen ausgesetzt sind.
* **Kampagneneffizienz**: Wenn ein Benutzer von einer bestimmten Kampagne durchklickt, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der Interaktion des Benutzers mit dieser Kampagne abgeschnitten haben.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Freigabe](release-impact.md).
* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die Sie pro Benutzer messen möchten. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Ereignisse pro Benutzer], [!UICONTROL Ereignisse], [!UICONTROL Sitzungen] und [!UICONTROL Benutzer].
* **[!UICONTROL Faktoren]**: Für diese Analyse gibt es zwei Faktoren:
   * **[!UICONTROL Datum]**: Wie weit zurück Sie nach dem ersten aufgetretenen Nutzungsereignis suchen möchten.
   * **[!UICONTROL Ereignis]**: Das Ereignis, für das Sie die Analyse zentrieren möchten.
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen. Für diese Analyse wird ein einzelnes Segment unterstützt.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Erste Verwendung der Auswirkung] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Typ der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;.

### Datumsbereich

Die Datumsauswahl in der Analyse [!UICONTROL Auswirkungen der ersten Verwendung] funktioniert anders als bei anderen Analysen, da sich die Analyse um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Trenddaten angezeigt werden sollen. Gültige Optionen sind [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich] und [!UICONTROL Vierteljährlich]. Eine Änderung des Intervalls wirkt sich auf die für den Zeitraum vor und nach verfügbaren Optionen aus.
* **[!UICONTROL Vor und nach dem Zeitraum]**: Die Zeit, die vor und nach dem in der Abfrageleiste angegebenen ersten Anwendungsereignis analysiert werden soll. Die verfügbaren Optionen hängen von der Auswahl [!UICONTROL Intervall] ab.

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
