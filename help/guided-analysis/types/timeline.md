---
title: Zeitleistenanalyse
description: Beobachten Sie Sitzungsereignisse auf Benutzerebene im Zeitverlauf, um Erlebnismuster zu erkennen.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---

# Analyse [!UICONTROL Timeline] {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Zeitleiste"
>abstract="Beobachten Sie Sitzungsereignisse auf Benutzerebene im Zeitverlauf."

<!-- markdownlint-enable MD034 -->

Die ![Timeline](/help/assets/icons/Timeline.svg)**[!UICONTROL Zeitleistenanalyse]** ermöglicht es Ihnen, Sitzungsereignisse auf Benutzerebene im Laufe der Zeit zu beobachten, um Erlebnismuster zu erkennen und bessere Benutzergeschichten zu erzählen. In der linken Leiste können Sie den Stream nach Eigenschaftswerten und Segmenten filtern. In der rechten Leiste können Sie aus einer zufälligen Liste von Benutzenden auswählen, die den Filterkriterien entsprechen. Im mittleren Bereich wird der Stream für die ausgewählte Benutzerin oder den ausgewählten Benutzer nach Sitzung angezeigt, bestehend aus Zeitstempel, Eigenschaftswerten und Dauer. Die Dauer ist für das letzte Ereignis in einer bestimmten Sitzung nicht verfügbar.


>[!NOTE]
>
>Für die [!UICONTROL Zeitleistenanalyse] muss die Standardkomponente **[!UICONTROL Personen-ID]** in der [Datenansicht](/help/data-views/component-reference.md#optional) verfügbar sein. Das Einschließen der Personen-ID in eine Datenansicht wird von Ihrer oder Ihrem Customer Journey Analytics-Admin verwaltet, sodass Ihre Organisation die volle Datenschutzkontrolle darüber hat, wer auf diese Daten zugreifen kann.
>><br/>Wenn einer Datenansicht die Komponente [!UICONTROL Personen-ID] nicht hinzugefügt wurde, wird die folgende Meldung angezeigt:
>
>* **Admins**: *Die Eigenschaft PersonID ist für diese Analyse erforderlich. Bitte fügen Sie die Personen-ID zur Datenansicht hinzu.*
>* **Benutzende ohne Administratorrechte**: *Die Eigenschaft PersonID ist für diese Analyse erforderlich. Bitte arbeiten Sie mit Ihren Customer Journey Analytics-Admins zusammen, um die Personen-ID zur Datenansicht hinzuzufügen.*

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?quality=12&learn=on)



## Anwendungsfälle

Zu den Anwendungsfällen für diese Analyse gehören:

* **Reibungsuntersuchung**: Wenn Sie einen steilen Abfall in der [Trichteranalyse](funnel.md) feststellen, können Sie ein Segment dieser Benutzenden erstellen und das Segment in dieser Analyse anwenden, um potenzielle Ursachen zu prüfen.
* **Fehlerverhalten**: Wenn Benutzende auf einen Produktfehler stoßen, können Sie untersuchen, was Benutzende getan haben, bevor oder nachdem sie diesen Fehler gesehen haben.
* **Validierung der Datenerfassung**: Datenadmins können diese Analyse nach ihrer eigenen Personen-ID filtern, um zu überprüfen, ob die Implementierung ihrer Organisation wie erwartet funktioniert.

## Benutzeroberfläche

Einen Überblick über die Benutzeroberfläche für die geführte Analyse erhalten Sie unter [Benutzeroberfläche](../overview.md#interface). Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Dimension]**: Die Dimension, für die Sie Streaming-Werte anzeigen möchten. Der Stream in der Mitte zeigt Werte für die ausgewählte Dimension an. Sie können auch Filter anwenden, um den Stream auf relevantere Daten einzugrenzen. Gültige Operatoren für den Filter sind [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Beginnt mit], [!UICONTROL Endet mit], [!UICONTROL Enthält], [!UICONTROL Enthält nicht], [!UICONTROL Vorhanden] und [!UICONTROL Ist nicht vorhanden].
* **[!UICONTROL Segmente]**: Das Segment, das Sie analysieren möchten. Bei der Filterung Ihrer Daten fokussiert das ausgewählte Segment nur die Personen, die Ihren Segmentkriterien entsprechen. Wenn Sie die Analyse auf eine bestimmte Personen-ID eingrenzen möchten, können Sie im rechten Panel nach dieser Personen-ID filtern. Für diese Analyse wird ein Segment unterstützt.

### Diagrammeinstellungen

Die [!UICONTROL Zeitleistenanalyse] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Anzeigen als]**: Zeigt die gewünschten Eigenschaftswerte an.
   * [!UICONTROL Alle anzeigen]: Zeigt alle Eigenschaftswerte in einer Sitzung an.
   * [!UICONTROL Markieren]: Hebt Eigenschaftswerte in einer Sitzung, die mit den Abfragefiltern übereinstimmen, visuell hervor.
   * [!UICONTROL Nur Ansicht]: Zeigt nur Eigenschaftswerte in einer Sitzung an, die mit den Abfragefiltern übereinstimmen.

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trend-Daten angezeigt werden sollen. Diese Einstellung hat keine Auswirkungen auf Analysen ohne Trend, wie die Zeitleiste.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Ihnen stehen rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche zur Verfügung. Sie können auch die Kalenderauswahl verwenden, um einen festen Datumsbereich zu definieren.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
