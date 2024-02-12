---
title: Timeline-Ansicht
description: Lernen Sie Erlebnismuster kennen und erzählen Sie bessere Benutzergeschichten.
feature: Guided Analysis
keywords: Produktanalyse
role: User
source-git-commit: fef60995e9241eaad99f6f536b1f329757ea0830
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 1%

---

# [!UICONTROL Timeline] Ansicht

Die **[!UICONTROL Timeline]** Mit dieser Ansicht können Sie Sitzungsereignisse auf Benutzerebene im Zeitverlauf beobachten, um Erlebnismuster zu finden und bessere Benutzergeschichten zu erzählen. In der linken Leiste können Sie nach Eigenschaftswerten filtern, die Sie streamen möchten. In der rechten Leiste können Sie die Personen-ID auswählen, die Sie analysieren möchten. Der mittlere Bereich zeigt den Stream nach Sitzung an, bestehend aus Zeitstempel, Eigenschaftswerten und Dauer. Die Dauer ist für das letzte Ereignis in einer bestimmten Sitzung nicht verfügbar.

>[!NOTE]
>
>In der Timeline-Ansicht muss die **[!UICONTROL Personen-ID]** Standardkomponente ist im [Datenansicht](/help/data-views/component-reference.md#optional). Die Aufnahme der Personen-ID in eine Datenansicht wird von Ihrem Adobe Analytics-Datenadministrator verwaltet, sodass Unternehmen die volle Datenschutzkontrolle darüber erhalten, wer auf diese Daten zugreifen kann.

Wenn eine Datenansicht nicht über die [!UICONTROL Personen-ID] -Komponente hinzugefügt wurde, wird die folgende Meldung angezeigt:

* **Administratoren**: *Die PersonID-Eigenschaft ist für diese Analyse erforderlich. Fügen Sie der Datenansicht die Personen-ID hinzu.*
* **Benutzer ohne Administratorrechte**: *Die PersonID-Eigenschaft ist für diese Analyse erforderlich. Wenden Sie sich an Ihren Customer Journey Analytics-Administrator, um die Personen-ID zur Datenansicht hinzuzufügen.*

![Timeline-Screenshot](../assets/timeline.png)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Schmuckforschung**: Wenn Sie einen steilen Rückgang im [Friktion](friction.md) -Ansicht können Sie ein Segment dieser Benutzer erstellen und das Segment in dieser Ansicht anwenden, um potenzielle Ursachen zu untersuchen.
* **Fehlerverhalten**: Wenn bei Benutzern ein Produktfehler auftritt, können Sie untersuchen, was Benutzer vor oder nach diesem Fehler getan haben.
* **Datenerfassungsprüfung**: Datenadministratoren können diese Ansicht nach ihrer eigenen Personen-ID filtern, um zu überprüfen, ob die Implementierung ihres Unternehmens erwartungsgemäß funktioniert.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Eigenschaft]**: Die Eigenschaft, für die Sie Streaming-Werte anzeigen möchten. Der Stream in der Mitte zeigt Werte für die ausgewählte Eigenschaft an. Sie können auch Filter anwenden, um den Stream auf relevantere Daten einzugrenzen. Gültige Operatoren für den Filter enthalten [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Beginnt mit], [!UICONTROL Endet in], [!UICONTROL Enthält], [!UICONTROL Enthält nicht], [!UICONTROL Exists], und [!UICONTROL Nicht vorhanden].
* **[!UICONTROL Segmente]**: Das Segment, das Sie analysieren möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen. Wenn Sie die Ansicht auf eine bestimmte Personen-ID einschränken möchten, können Sie hier nach dieser Personen-ID filtern. Für diese Ansicht wird ein Segment unterstützt.

## Diagrammeinstellungen

Die [!UICONTROL Timeline] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Anzeigen als]**: Zeigt die gewünschten Eigenschaftswerte an.
   * [!UICONTROL Alle anzeigen]: Zeigt alle Eigenschaftswerte in einer Sitzung an.
   * [!UICONTROL Hervorheben]: Bildet visuell Eigenschaftswerte in einer Sitzung, die mit den Abfragefiltern übereinstimmen.
   * [!UICONTROL Nur anzeigen]: Zeigt nur Eigenschaftswerte in einer Sitzung an, die mit den Abfragefiltern übereinstimmen.

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Diese Einstellung wirkt sich nicht auf Trend-Ansichten wie die Timeline aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
