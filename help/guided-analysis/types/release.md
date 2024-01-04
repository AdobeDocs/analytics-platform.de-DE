---
title: Versionsansicht
description: Vergleichen Sie die Leistung über gleiche Zeiträume vor und nach der Veröffentlichung.
feature: Guided Analysis
keywords: Produktanalyse
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 2%

---

# [!UICONTROL Version] Ansicht

Die **[!UICONTROL Version]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach einem bestimmten Datum. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms stellt das Datum dar, das Sie vor und nach dem vergleichen möchten. Dieses Datum stellt in der Regel eine erhebliche Änderung am Produkt dar, mit dem Sie messen möchten, z. B. eine Aktualisierung des Produkts oder einen Kampagnen-Start.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Allgemeine Leistungsbewertung:** Der Vergleich der wichtigsten Indikatoren insgesamt, wie z. B. Interaktionsmaßnahmen, kann Ihnen dabei helfen festzustellen, ob eine bestimmte Version insgesamt erfolgreich war.
* **Überwachung**: Verfolgen Sie wichtige Metriken, von denen Sie erwarten würden, dass sie bei Änderungen flach bleiben, z. B. Ladezeit oder Anzahl der Anmeldungen. Verwenden Sie diesen Analysetyp, um sie vor und nach einer Veröffentlichung zu vergleichen, um sicherzustellen, dass er keine unbeabsichtigten Folgen hat.
* **Funktionsbereitstellung**: Wenn sich eine Produktaktualisierung auf die Verbesserung einer bestimmten Funktion konzentriert, können Sie diese Ansicht verwenden, um die Nutzung dieser Funktion vor und nach der Produktaktualisierung direkt zu vergleichen.
* **Fehlererkennung**: Das Tracking der Anzahl der Fehler vor und nach einer Version kann einen frühzeitigen Indikator für Kundenprobleme liefern. Wenn Sie unmittelbar nach einer Veröffentlichung einen Anstieg der Fehler feststellen, können Sie mit Entwicklungs- oder Entwicklungsteams zusammenarbeiten, um das Problem zu identifizieren und zu beheben, wodurch weitere Auswirkungen für Kunden vermieden werden.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die Sie pro Benutzer messen möchten. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Faktoren]**: Das Datum, das Sie vor und nach dem vergleichen möchten.
* **[!UICONTROL Personen]**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen.

## Diagrammeinstellungen

Die Freigabeansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die zu messende Metrik. Optionen umfassen [!UICONTROL Ereignisse pro Benutzer], [!UICONTROL Prozentsatz der Benutzer], [!UICONTROL Veranstaltungen], [!UICONTROL Sitzungen], und [!UICONTROL Benutzer].
* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Linie] und [!UICONTROL Balken].

## Datumsbereich

Die Datumsauswahl in der Impact-Analyse funktioniert anders als bei anderen Analysetypen, da sich der Bericht um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Zu den gültigen Optionen gehören [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich], und [!UICONTROL Vierteljährlich]. Eine Änderung des Intervalls wirkt sich auf die für den Zeitraum vor und nach verfügbaren Optionen aus.
* **[!UICONTROL Vor- und Nach-Zeitraum]**: Die Zeitdauer, die vor und nach dem in der Abfrageleiste angegebenen Datum analysiert werden soll. Die verfügbaren Optionen hängen von der [!UICONTROL Intervall] auswählen.
