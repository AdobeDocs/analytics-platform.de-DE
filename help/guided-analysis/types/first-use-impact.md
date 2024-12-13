---
title: Wirkungsanalyse der ersten Verwendung
description: Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 9%

---

# Analyse [!UICONTROL Wirkung der ersten Verwendung] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="Wirkung der ersten Verwendung"
>abstract="Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren."

<!-- markdownlint-enable MD034 -->

Die Analyse ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL First use impact]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach der ersten Verwendung einer Produktfunktion durch einen Benutzer. Die horizontale Achse dieses Berichts ist ein relatives Zeitintervall vor und nach dem Ereignis, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms stellt den 0. Tag dar, an dem ein Feature zum ersten Mal von einem Benutzer verwendet wird. Da Benutzende nicht immer Funktionen am selben Tag übernehmen und Ihre Rollouts möglicherweise über mehrere Tage erfolgen, kann Tag 0 für jeden einzelnen Benutzenden etwas Anderes bedeuten.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)


## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Neue Funktionsanalyse**: Wenn Sie eine neue Funktion in Ihrem Produkt starten, können Sie vergleichen, wie wichtige Indikatoren vor und nach der ersten Anzeige dieser neuen Funktion durch Benutzende durchgeführt wurden.
* **Schrittweise Rollouts** Da bei der Analyse nach der ersten Verwendung der Funktion und nicht nach einem festen Datum gesucht wird, ist diese Analyse hilfreich, wenn Sie den Rollout Ihrer Funktionen im Laufe der Zeit planen.
* **Analyse der neuen Produktversion**: Wenn Sie eine neue Version Ihres Produkts starten, können Sie vergleichen, wie wichtige Indikatoren vor und nach dem erstmaligen Aufruf der Benutzenden an diese neue Version durchgeführt wurden. Wählen Sie als Erstereignis „Beliebiges Ereignis“ aus und filtern Sie es in Ihre Versionsnummer-Eigenschaft.
* **Vorhandene Funktionsverbesserungen**: Wenn Sie eine vorhandene Funktion in Ihrem Produkt verbessern, können Sie vergleichen, wie wichtige Indikatoren vor und nach dem ersten Kontakt mit diesen neuen Verbesserungen durchgeführt wurden. Sie können diese Analyse je nach Funktionsausstattung auf eine oder mehrere Arten durchführen.
   * Wählen Sie ein Ereignis aus, das die Verbesserung als Erstverwendungsereignis darstellt
   * Wählen Sie das Datum aus, an dem die Änderungen eingeführt wurden
   * Segmentieren Sie die Analyse auf die Personengruppe, die den Verbesserungen ausgesetzt sind.
* **Kampagnenwirksamkeit**: Wenn ein Benutzer von einer bestimmten Kampagne aus klickt, können Sie vergleichen, wie wichtige Indikatoren vor und nach der Benutzerinteraktion mit dieser Kampagne ausgeführt wurden.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Version](release-impact.md).
* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die pro Benutzer gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.  Die Optionen umfassen [!UICONTROL Ereignisse pro Benutzer], [!UICONTROL Ereignisse], [!UICONTROL Sitzungen] und [!UICONTROL Benutzer].
* **[!UICONTROL Faktoren]**: Diese Analyse beruht auf zwei Faktoren:
   * **[!UICONTROL Datum]**: Wie weit zurück Sie mit der Suche nach dem ersten aufgetretenen Anwendungsereignis beginnen möchten.
   * **[!UICONTROL Ereignis]**: Das Ereignis, nach dem Sie für die erste Verwendung von suchen möchten, um die Analyse zu zentrieren.
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass es sich nur auf die Personen konzentriert, die Ihren Segmentkriterien entsprechen. Für diese Analyse wird ein einzelnes Segment unterstützt.

### Diagrammeinstellungen

Die [!UICONTROL First Use Impact]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Zu den Optionen gehört „Line“.

### Datumsbereich

Die Datumsauswahl in der [!UICONTROL Erstverwendung von Auswirkungen]-Analyse funktioniert anders als andere Analysen, da sich die Analyse um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind [!UICONTROL täglich], [!UICONTROL wöchentlich], [!UICONTROL monatlich] und [!UICONTROL vierteljährlich]. Eine Änderung des Intervalls wirkt sich auf die Optionen aus, die für den Zeitraum vor und nach dem Zeitraum verfügbar sind.
* **[!UICONTROL Vor und nach dem Zeitraum]**: Der Zeitraum, der vor und nach dem ersten Anwendungsereignis analysiert werden soll, angegeben in der Abfrageleiste. Die verfügbaren Optionen hängen von der Auswahl [!UICONTROL Intervall] ab.

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
