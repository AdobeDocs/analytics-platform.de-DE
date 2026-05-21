---
title: Release-Wirkungsanalyse
description: Vergleichen Sie die Leistung in gleich langen Zeiträumen vor und nach der Veröffentlichung.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
TQID: https://experienceleague.adobe.com/2PKIwvFwCv5FiL7WgeJPksm74c8m5B4L33RZouD-t1o
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 545
ht-degree: 97%

---

# Analyse [!UICONTROL Auswirkungen der Version] {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="Auswirkungen der Version"
>abstract="Vergleichen Sie die Leistung in gleich langen Zeiträumen vor und nach der Veröffentlichung."

<!-- markdownlint-enable MD034 -->

Die Analyse der ![Release](/help/assets/icons/Release.svg) **[!UICONTROL Auswirkungen der Version]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach einem bestimmten Datum. Die horizontale Achse dieses Berichts ist ein Zeitintervall, die vertikale Achse ein Maß für die gewünschten Schlüsselindikatoren. Ein vertikaler Balken in der Mitte des Diagramms stellt das Datum dar, mit dem Sie die Leistung davor und danach vergleichen möchten. Dieses Datum stellt in der Regel eine wesentliche Änderung am Produkt dar, für die Sie die Messung durchführen möchten, z. B. eine Aktualisierung des Produkts oder ein Kampagnen-Launch.

>[!VIDEO](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/guided-analysis/release-impact)

## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Bewertung der Gesamtleistung:** Durch den Vergleich von allgemeinen Schlüsselindikatoren, z. B. Interaktionsmessungen, können Sie ermitteln, ob eine bestimmte Version insgesamt erfolgreich war.
* **Monitoring**: Verfolgen Sie wichtige Metriken, von denen Sie erwarten würden, dass sie nach Änderungen unverändert bleiben, z. B. die Ladezeit oder Anzahl der Anmeldungen. Verwenden Sie diese Analyse, um Metriken vor und nach einer Version zu vergleichen und sicherzustellen, dass sie keine unbeabsichtigten Folgen hat.
* **Funktionsübernahme**: Wenn eine Produktaktualisierung auf die Verbesserung einer bestimmten Funktion ausgerichtet ist, können Sie die Nutzung dieser Funktion vor und nach der Produktaktualisierung mithilfe dieser Analyse vergleichen.
* **Fehlererkennung**: Die Verfolgung der Fehleranzahl vor und nach einer Version kann einen frühen Indikator für Kundenprobleme bereitstellen. Wenn Sie unmittelbar nach einer Version eine Zunahme von Fehlern bemerken, können Sie das Problem zusammen mit Engineering- oder Entwicklungs-Teams identifizieren und beheben und so weitere Auswirkungen auf die Kundschaft verhindern.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ansicht]**: Wechseln Sie zwischen dieser Analyse und [Wirkung der ersten Verwendung](first-use-impact.md).
* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die pro Person gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Zählt als]**: Die Zählmethode, die auf die ausgewählten Ereignisse angewendet werden soll. Zu den Optionen gehören [!UICONTROL Ereignisse pro nutzender Person], [!UICONTROL Prozentualer Anteil der Benutzenden], [!UICONTROL Ereignisse], [!UICONTROL Sitzungen] und [!UICONTROL Benutzende].
* **[!UICONTROL Faktoren]**: Das Datum, vor. bzw. nach dem Sie den Vergleich durchführen möchten.
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Bei der Filterung Ihrer Daten fokussiert das ausgewählte Segment nur die Personen, die Ihren Segmentkriterien entsprechen.

### Diagrammeinstellungen

Die Analyse der [!UICONTROL Auswirkungen der Version] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, der verwendet werden soll. Die Optionen umfassen [!UICONTROL Linie] und [!UICONTROL Balken].

### Datumsbereich

Die Datumsauswahl in der Wirkungsanalyse funktioniert anders als bei anderen Analysen, da sich der Bericht um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Gültige Optionen sind [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich] und [!UICONTROL Quartalsweise]. Eine Änderung des Intervalls wirkt sich auf die Optionen aus, die für den Zeitraum „Vor und nach dem Zeitraum“ verfügbar sind.
* **[!UICONTROL Vor und nach dem Zeitraum]**: Der Zeitraum, der vor und nach dem in der Abfrageleiste angegebenen Datum analysiert werden muss. Die verfügbaren Optionen hängen vom gewählten [!UICONTROL Intervall] ab.


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
