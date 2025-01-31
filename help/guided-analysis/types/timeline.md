---
title: Zeitleistenanalyse
description: Beobachten Sie Sitzungsereignisse auf Benutzerebene im Laufe der Zeit, um Erlebnismuster zu finden.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---

# Analyse [!UICONTROL Timeline] {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Timeline"
>abstract="Beobachten Sie Sitzungsereignisse auf Benutzerebene im Zeitverlauf."

<!-- markdownlint-enable MD034 -->

Die ![Timeline](/help/assets/icons/Timeline.svg)**[!UICONTROL Timeline]**-Analyse ermöglicht es Ihnen, Sitzungsereignisse auf Benutzerebene im Laufe der Zeit zu beobachten, um Erlebnismuster zu finden und bessere Benutzergeschichten zu erzählen. In der linken Leiste können Sie den Stream nach Eigenschaftswerten und Segmenten filtern. In der rechten Leiste können Sie aus einer zufälligen Liste von Benutzern auswählen, die den Filterkriterien entsprechen. Im mittleren Bereich wird der Stream für den ausgewählten Benutzer nach Sitzung angezeigt, bestehend aus Zeitstempel, Eigenschaftswerten und Dauer. Die Dauer ist für das letzte Ereignis in einer bestimmten Sitzung nicht verfügbar.


>[!NOTE]
>
>Für [!UICONTROL Zeitleisten]-Analyse muss die Standardkomponente **[!UICONTROL Personen-ID]** in der [Datenansicht“ verfügbar ](/help/data-views/component-reference.md#optional). Das Einschließen der Personen-ID in eine Datenansicht wird von Ihrem Customer Journey Analytics-Administrator verwaltet, sodass Ihr Unternehmen die volle Datenschutzkontrolle darüber hat, wer auf diese Daten zugreifen kann.
><br/>Wenn einer Datenansicht die Komponente [!UICONTROL Personen-ID] nicht hinzugefügt wurde, wird die folgende Meldung angezeigt:
>
>* **Administratoren**: *Die PersonID-Eigenschaft ist für diese Analyse erforderlich. Bitte Personen-ID zur Datenansicht hinzufügen.*
>* **Benutzer ohne Administratorrechte**: *Die PersonID-Eigenschaft ist für diese Analyse erforderlich. Wenden Sie sich an Ihren Customer Journey Analytics-Administrator, um die Personen-ID zur Datenansicht hinzuzufügen.*

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?quality=12&learn=on)



## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Reibungsanalyse**: Wenn Sie einen steilen Abfall in der [Trichteranalyse](funnel.md) feststellen, können Sie ein Segment dieser Benutzer erstellen und das Segment in dieser Analyse anwenden, um potenzielle Ursachen zu untersuchen.
* **Fehlerverhalten**: Wenn Benutzende auf einen Produktfehler stoßen, können Sie untersuchen, was Benutzende getan haben, bevor oder nachdem sie diesen Fehler gesehen haben.
* **Validierung der Datenerfassung**: Datenadministratoren können diese Analyse nach ihrer eigenen Personen-ID filtern, um zu überprüfen, ob die Implementierung ihrer Organisation erwartungsgemäß funktioniert.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Dimension]**: Die Dimension, für die Sie Streaming-Werte anzeigen möchten. Der Stream in der Mitte zeigt Werte für die ausgewählte Dimension an. Sie können auch Filter anwenden, um den Stream auf relevantere Daten einzugrenzen. Gültige Operatoren für den Filter sind [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Beginnt mit], [!UICONTROL Endet mit], [!UICONTROL Enthält], [!UICONTROL Enthält nicht], [!UICONTROL Existiert] und [!UICONTROL Ist nicht vorhanden].
* **[!UICONTROL Segmente]**: Das Segment, das Sie analysieren möchten. Das ausgewählte Segment filtert Ihre Daten so, dass es sich nur auf die Personen konzentriert, die Ihren Segmentkriterien entsprechen. Wenn Sie die Analyse auf eine bestimmte Personen-ID eingrenzen möchten, können Sie im rechten Bedienfeld nach dieser Personen-ID filtern. Für diese Analyse wird ein Segment unterstützt.

### Diagrammeinstellungen

Die [!UICONTROL Zeitleisten]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Anzeigen als]**: Zeigt die gewünschten Eigenschaftswerte an.
   * [!UICONTROL Alle anzeigen]: Alle Eigenschaftswerte in einer Sitzung anzeigen.
   * [!UICONTROL Hervorheben]: hebt Eigenschaftswerte in einer Sitzung, die mit den Abfragefiltern übereinstimmen, visuell hervor.
   * [!UICONTROL Nur Anzeigen]: Zeigen Sie nur Eigenschaftswerte in einer Sitzung an, die mit den Abfragefiltern übereinstimmen.

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Sie Trenddaten anzeigen möchten. Diese Einstellung hat keine Auswirkungen auf nicht-tendenzielle Analysen wie die Zeitleiste.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
