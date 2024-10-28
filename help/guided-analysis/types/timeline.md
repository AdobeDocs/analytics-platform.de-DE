---
title: Timeline-Analyse
description: Beobachten Sie Sitzungsereignisse auf Benutzerebene im Zeitverlauf, um Erlebnismuster zu finden.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Analyse [!UICONTROL Timeline] {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_timeline_button"
>title="Timeline"
>abstract="Beobachten Sie Sitzungsereignisse auf Benutzerebene im Zeitverlauf."

<!-- markdownlint-enable MD034 -->

Die Analyse ![Timeline](/help/assets/icons/Timeline.svg) **[!UICONTROL Timeline]** ermöglicht es Ihnen, Sitzungsereignisse auf Benutzerebene im Laufe der Zeit zu beobachten, um Erlebnismuster zu finden und bessere Benutzermeldungen zu erzählen. In der linken Leiste können Sie den Stream nach Eigenschaftswerten und Segmenten filtern. In der rechten Leiste können Sie aus einer zufälligen Liste von Benutzern auswählen, die den Filterkriterien entsprechen. Der mittlere Bereich zeigt den Stream für den ausgewählten Benutzer nach Sitzung an, der aus Zeitstempel, Eigenschaftswerten und Dauer besteht. Die Dauer ist für das letzte Ereignis in einer bestimmten Sitzung nicht verfügbar.


>[!NOTE]
>
>Für die Analyse [!UICONTROL Timeline] muss die Standardkomponente **[!UICONTROL Personen-ID]** in der [Datenansicht](/help/data-views/component-reference.md#optional) verfügbar sein. Die Aufnahme der Personen-ID in eine Datenansicht wird von Ihrem Customer Journey Analytics-Administrator verwaltet, sodass Ihr Unternehmen die volle Datenschutzkontrolle darüber hat, wer auf diese Daten zugreifen kann.
><br/>Wenn in einer Datenansicht die Komponente [!UICONTROL Personen-ID] nicht hinzugefügt wurde, wird die folgende Meldung angezeigt:
>
>* **Admins**: *Für diese Analyse ist die PersonID-Eigenschaft erforderlich. Fügen Sie der Datenansicht die Personen-ID hinzu.*
>* **Nicht-Administratoren**: *Für diese Analyse ist die PersonID-Eigenschaft erforderlich. Wenden Sie sich an Ihren Customer Journey Analytics-Administrator, um die Personen-ID zur Datenansicht hinzuzufügen.*

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)



## Anwendungsbeispiele

Anwendungsbeispiele für diese Analyse sind:

* **Friction exploration**: Wenn Sie einen steilen Rückgang in der Analyse [Trichteranalyse](funnel.md) feststellen, können Sie ein Segment dieser Benutzer erstellen und das Segment in dieser Analyse anwenden, um potenzielle Ursachen zu untersuchen.
* **Fehlerverhalten**: Wenn Benutzer auf einen Produktfehler stoßen, können Sie untersuchen, was Benutzer vor oder nach diesem Fehler getan haben.
* **Validierung der Datenerfassung**: Datenadministratoren können diese Analyse nach ihrer eigenen Personen-ID filtern, um zu überprüfen, ob die Implementierung ihrer Organisation erwartungsgemäß funktioniert.

## Benutzeroberfläche

Eine Übersicht über die Benutzeroberfläche der geführten Analyse finden Sie unter [Schnittstelle](../overview.md#interface) . Die folgenden Einstellungen beziehen sich auf diese Analyse:

### Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Dimension]**: Die Dimension, für die Sie Streaming-Werte anzeigen möchten. Der Stream in der Mitte zeigt Werte für die ausgewählte Dimension an. Sie können auch Filter anwenden, um den Stream auf relevantere Daten einzugrenzen. Gültige Operatoren für den Filter sind [!UICONTROL Entspricht], [!UICONTROL Entspricht nicht], [!UICONTROL Beginnt mit], [!UICONTROL Endet mit], [!UICONTROL Enthält], [!UICONTROL enthält nicht], [!UICONTROL Vorhanden] und [!UICONTROL Existiert nicht].
* **[!UICONTROL Segmente]**: Das Segment, das Sie analysieren möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen. Wenn Sie die Analyse auf eine bestimmte Personen-ID einschränken möchten, können Sie im rechten Bereich nach dieser Personen-ID filtern. Für diese Analyse wird ein Segment unterstützt.

### Diagrammeinstellungen

Die Analyse [!UICONTROL Timeline] bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Als]** anzeigen: Zeigt die gewünschten Eigenschaftswerte an.
   * [!UICONTROL Alle anzeigen]: Zeigt alle Eigenschaftswerte in einer Sitzung an.
   * [!UICONTROL Hervorheben]: Hervorheben visuell die Eigenschaftswerte in einer Sitzung, die mit den Abfragefiltern übereinstimmen.
   * [!UICONTROL Nur Ansicht]: Zeigt nur Eigenschaftswerte in einer Sitzung an, die mit den Abfragefiltern übereinstimmen.

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Diese Einstellung wirkt sich nicht auf Trendanalysen wie die Timeline aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
