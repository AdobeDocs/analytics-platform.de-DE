---
title: Timeline-Ansicht
description: Muster in der Sitzungsaktivität
feature: Guided Analysis
keywords: Produktanalyse
role: User
source-git-commit: ecdbe1b68aa0824bd9db4acefd3ef9059d9ac927
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# [!UICONTROL Timeline] Ansicht

Die **[!UICONTROL Timeline]** -Ansicht ermöglicht es Ihnen, einzelne Sitzungen zu analysieren, um Verhaltensmuster zu ermitteln. In der rechten Leiste können Sie die Personen-ID auswählen, die Sie analysieren möchten. Der mittlere Bereich zeigt die Zeit, den ausgewählten Eigenschaftswert und die Dauer für jedes Ereignis dieser Person.

Für diese Analyse müssen Sie die **[!UICONTROL Personen-ID]** Standardkomponente zu [Datenansicht](/help/data-views/component-reference.md#optional). Wenn Sie nicht über die [!UICONTROL Personen-ID] -Komponente, die der Datenansicht hinzugefügt wurde, wird die folgende Meldung angezeigt:

> Die PersonID-Eigenschaft ist für diese Analyse erforderlich. Fügen Sie der Datenansicht PersonID hinzu.

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Schmuckforschung**: Wenn Sie einen steilen Rückgang im [Friktion](friction.md) -Ansicht können Sie die potenziellen Ursachen dieses Rückgangs mithilfe dieser Ansicht untersuchen.
* **Fehlerverhalten**: Wenn Benutzer in Ihrem Produkt auf einen Fehler stoßen, können Sie prüfen, was Benutzer tun, bevor oder nachdem sie diesen Fehler sehen.
* **Datenerfassungsprüfung**: Datenadministratoren können diese Ansicht filtern, um sich selbst zu isolieren. Diese Ansicht bietet eine solide Möglichkeit, sicherzustellen, dass die Implementierung Ihres Unternehmens erwartungsgemäß funktioniert.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Eigenschaft]**: Die Eigenschaft, für die Sie Werte anzeigen möchten. Die Sitzungsanalyse in der Mitte zeigt Werte für die hier ausgewählte Eigenschaft an. Sie können Daten auch nach der ausgewählten Eigenschaft filtern. Gültige Operatoren für den Filter enthalten [!UICONTROL Gleich], [!UICONTROL Ist nicht gleich], [!UICONTROL Beginnt mit], [!UICONTROL Endet in], [!UICONTROL Enthält], [!UICONTROL Enthält nicht], [!UICONTROL Exists], und [!UICONTROL Nicht vorhanden].
* **[!UICONTROL Segmente]**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen. Für diese Ansicht wird ein Segment unterstützt.

## Diagrammeinstellungen

Die [!UICONTROL Timeline] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Anzeigen als]**: Zeigt die gewünschten Eigenschaftswerte an.
   * [!UICONTROL Alle anzeigen]
   * [!UICONTROL Hervorheben]
   * [!UICONTROL Nur anzeigen]

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Trenddaten angezeigt werden sollen. Diese Einstellung wirkt sich nicht auf Trend-Ansichten wie die Timeline aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
