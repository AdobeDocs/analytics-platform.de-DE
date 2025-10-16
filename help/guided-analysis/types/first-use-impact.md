---
title: Wirkungsanalyse der ersten Verwendung
description: Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 100%

---

# Analyse [!UICONTROL Wirkung der ersten Verwendung] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="Wirkung der ersten Verwendung"
>abstract="Messen Sie die Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren."

<!-- markdownlint-enable MD034 -->

Die Analyse ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL Wirkung der ersten Verwendung]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach der ersten Verwendung einer Produktfunktion durch eine Benutzerin bzw. einen Benutzer. Die horizontale Achse dieses Berichts ist ein relatives Zeitintervall vor und nach dem Ereignis und die vertikale Achse ein Maß für die gewünschten Schlüsselindikatoren. Ein vertikaler Balken in der Mitte des Diagramms stellt Tag 0 für den Fall dar, wenn eine Funktion zum ersten Mal von einer bestimmten Person verwendet wird. Da Benutzende Funktionen nicht immer am selben Tag übernehmen und Ihre Rollouts möglicherweise über mehrere Tage erfolgen, kann Tag 0 für jede Benutzerin und jeden Benutzer etwas Anderes bedeuten.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Neue Funktionsanalyse**: Wenn Sie eine neue Funktion in Ihrem Produkt einführen, können Sie die Leistung der Schlüsselindikatoren vor und nach der erstmaligen Bereitstellung dieser Funktion für die Benutzenden vergleichen.
* **Stufenweise Rollouts**: Da bei der Analyse nach der ersten Verwendung der Funktion und nicht nach einem festen Datum gesucht wird, ist sie bei Rollouts Ihrer Funktionen über einen längeren Zeitraum nützlich.
* **Analyse einer neuen Produktversion**: Wenn Sie eine neue Version Ihres Produktes einführen, können Sie die Leistung der Schlüsselindikatoren vor und nach der erstmaligen Bereitstellung dieser neuen Version für die Benutzenden vergleichen. Wählen Sie als Ereignis der erstmaligen Verwendung „Beliebiges Ereignis“ aus und filtern Sie es auf Ihre Eigenschaft „Versionsnummer“.
* **Vorhandene Funktionsverbesserungen**: Wenn Sie eine vorhandene Funktion in Ihrem Produkt verbessern, können Sie die Leistung von Schlüsselindikatoren vor und nach der erstmaligen Bereitstellung dieser neuen Verbesserungen für die Benutzenden vergleichen. Sie können diese Analyse je nach Instrumentierung der Funktionen auf eine oder mehrere Arten durchführen.
   * Auswählen eines Ereignisses, das die Verbesserung als Ereignis der ersten Verwendung darstellt
   * Auswählen des Startdatums für das Rollout der Änderungen
   * Segmentieren der Analyse auf die Personengruppe, die den Verbesserungen ausgesetzt ist
* **Kampagneneffektivität**: Wenn sich Benutzende über eine bestimmte Kampagne durchklicken, können Sie die Leistung der Schlüsselindikatoren vor und nach der Benutzerinteraktion mit dieser Kampagne vergleichen.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Version](release-impact.md).
* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die pro Person gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Ereignisse pro nutzender Person], [!UICONTROL Ereignisse], [!UICONTROL Sitzungen] und [!UICONTROL Benutzende].
* **[!UICONTROL Faktoren]**: Diese Analyse beruht auf zwei Faktoren:
   * **[!UICONTROL Datum]**: Wie weit zurück Sie mit der Suche nach dem Ereignis der ersten Anwendung beginnen möchten.
   * **[!UICONTROL Ereignis]**: Das Ereignis, nach dessen erster Verwendung Sie suchen möchten, um die Analyse darauf zu zentrieren.
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Bei der Filterung Ihrer Daten fokussiert das ausgewählte Segment nur die Personen, die Ihren Segmentkriterien entsprechen. Für diese Analyse wird ein einzelnes Segment unterstützt.

### Diagrammeinstellungen

Die Analyse der [!UICONTROL Wirkung der ersten Verwendung] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Zu den Optionen gehört „Linie“.

### Datumsbereich

Die Datumsauswahl in der Analyse [!UICONTROL Wirkung der ersten Verwendung] funktioniert anders als bei anderen Analysen, da sich die Analyse um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich] und [!UICONTROL Quartalsweise]. Eine Änderung des Intervalls wirkt sich auf die Optionen aus, die für den Zeitraum „Vor und nach dem Zeitraum“ verfügbar sind.
* **[!UICONTROL Vor und nach dem Zeitraum]**: Der Zeitraum, der vor und nach dem in der Abfrageleiste angegebenen Ereignis der ersten Verwendung analysiert werden muss. Die verfügbaren Optionen hängen vom gewählten [!UICONTROL Intervall] ab.

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
