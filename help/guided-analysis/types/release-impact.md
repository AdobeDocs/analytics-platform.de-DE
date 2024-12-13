---
title: Release-Wirkungsanalyse
description: Vergleichen Sie die Leistung in gleich langen Zeiträumen vor und nach der Veröffentlichung.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 10%

---

# Analyse [!UICONTROL Auswirkungen der Version] {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="Auswirkungen der Version"
>abstract="Vergleichen Sie die Leistung in gleich langen Zeiträumen vor und nach der Veröffentlichung."

<!-- markdownlint-enable MD034 -->

Die Analyse ![Release](/help/assets/icons/Release.svg) **[!UICONTROL Release Impact]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach einem bestimmten Datum. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms stellt das Datum dar, mit dem Sie vor und nach dem Vergleich beginnen möchten. Dieses Datum stellt in der Regel eine wesentliche Änderung am Produkt dar, an dem Sie messen möchten, z. B. eine Aktualisierung des Produkts oder einen Kampagnen-Launch.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Gesamtleistungsbewertung:** Vergleichen von allgemeinen Schlüsselindikatoren, wie z. B. Interaktionsmessungen, kann Ihnen dabei helfen festzustellen, ob eine bestimmte Version insgesamt erfolgreich war.
* **Monitoring**: Verfolgen Sie wichtige Metriken, von denen Sie erwarten würden, dass sie unverändert bleiben, wenn Änderungen vorgenommen werden, z. B. Ladezeit oder Anzahl der Anmeldungen. Verwenden Sie diese Analyse, um sie vor und nach einer Veröffentlichung zu vergleichen und sicherzustellen, dass dies keine unbeabsichtigten Folgen hat.
* **Funktionsübernahme**: Wenn ein Produkt-Update auf die Verbesserung einer bestimmten Funktion ausgerichtet ist, können Sie diese Analyse verwenden, um die Nutzung dieser Funktion vor und nach dem Produkt-Update direkt zu vergleichen.
* **Fehlererkennung**: Die Verfolgung der Fehleranzahl vor und nach einer Veröffentlichung kann einen frühen Indikator für Kundenprobleme bieten. Wenn Sie unmittelbar nach einer Veröffentlichung eine Zunahme von Fehlern bemerken, können Sie mit Technik- oder Entwicklungs-Teams zusammenarbeiten, um das Problem zu identifizieren und zu beheben und so weitere Auswirkungen auf Kunden zu verhindern.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Anzeigen]**: Wechseln zwischen dieser Analyse und [Auswirkung bei der ersten Verwendung](first-use-impact.md).
* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die pro Benutzer gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll.  Die Optionen umfassen [!UICONTROL Ereignisse pro ]), [!UICONTROL Prozentsatz der ][!UICONTROL  Ereignisse], [!UICONTROL Sitzungen] und [!UICONTROL Benutzer].
* **[!UICONTROL Faktoren]**: Das Datum, das Sie vor und nach dem vergleichen möchten.
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass es sich nur auf die Personen konzentriert, die Ihren Segmentkriterien entsprechen.

### Diagrammeinstellungen

Die [!UICONTROL Release Impact]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Die Optionen umfassen [!UICONTROL Line] und [!UICONTROL Bar].

### Datumsbereich

Die Datumsauswahl in der Auswirkungsanalyse funktioniert anders als andere Analysen, da sich der Bericht um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind [!UICONTROL täglich], [!UICONTROL wöchentlich], [!UICONTROL monatlich] und [!UICONTROL vierteljährlich]. Eine Änderung des Intervalls wirkt sich auf die Optionen aus, die für den Zeitraum vor und nach dem Zeitraum verfügbar sind.
* **[!UICONTROL Vor und nach dem Zeitraum]**: Der Zeitraum, der vor und nach dem in der Abfrageleiste angegebenen Datum analysiert werden muss. Die verfügbaren Optionen hängen von der Auswahl [!UICONTROL Intervall] ab.


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
