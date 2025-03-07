---
title: Verwalten von Datenblöcken mithilfe von Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung der Verwaltungsfunktion in Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 57%

---

# Verwalten von Datenblöcken in Report Builder

Mit dem Datenblock-Manager können Sie alle Datenblöcke einer Arbeitsmappe anzeigen und verwalten. Der Datenblock-Manager bietet Such-, Filter- und Sortierfunktionen, mit denen Sie bestimmte Datenblöcke schnell finden können. Nach Auswahl eines oder mehrerer Datenblöcke können Sie diese bearbeiten, löschen oder aktualisieren.

![Der Bildschirm „Datenblock-Manager“.](./assets/image52.png)

## Anzeigen von Datenblöcken

Klicken Sie auf **Verwalten**, um eine Liste aller Datenblöcke in einer Arbeitsmappe anzuzeigen.


![Die Option „Verwalten“, um eine Liste aller Datenblöcke anzuzeigen.](./assets/image53.png)

Der Datenblock-Manager listet alle in einer Arbeitsmappe vorhandenen Datenblöcke auf. 

![Die Liste aller in einer Arbeitsmappe vorhandenen Datenblöcke.](./assets/image52.png)

## Sortieren der Datenblockliste

Sie können die Datenblockliste nach einer angezeigten Spalte sortieren. Sie können die Datenvariablen beispielsweise nach Datenansichten, Blockierungslisten, Datumsbereich und anderen Variablen sortieren.

Um die Datenblockliste zu sortieren, klicken Sie auf eine Spaltenüberschrift.

![Datenblöcke sortieren.](./assets/image54.png)

## Durchsuchen der Datenblockliste

Verwenden Sie das Suchfeld, um in der Datenblocktabelle eine Suche durchzuführen. Sie können beispielsweise nach Metriken suchen, die in den Datenblöcken oder in der Datenansicht enthalten sind. Sie können auch nach Datumsangaben suchen, die in den Spalten „Datumsbereich“, „Änderungsdatum“ oder „Datum des letzten Durchgang“ angezeigt werden.

![Verwenden des Suchfelds, um nach Elementen in der Datenblocktabelle zu suchen.](./assets/image55.png)

## Bearbeiten von Datenblöcken

Sie können die Datenansicht, den Datumsbereich oder die Segmente bearbeiten, die auf einen oder mehrere Datenblöcke angewendet wurden.

Sie können beispielsweise ein vorhandenes Segment in einem oder mehreren Datenblöcken durch ein neues Segment ersetzen.

1. Wählen Sie die zu aktualisierenden Datenblöcke aus. Sie können das Kontrollkästchen auf der obersten Ebene aktivieren, um alle Datenblöcke auszuwählen. Sie können aber auch einzelne Datenblöcke auswählen.

   ![Das Stiftsymbol „Bearbeiten“](./assets/image56.png)

1. Klicken Sie auf das Bearbeitungssymbol, um das Fenster „Schnellbearbeitung“ anzuzeigen.

   ![Das Fenster „Schnellbearbeitung“](./assets/image58.png)

1. Wählen Sie einen Segment-Link aus, um Datenansichten, Datumsbereiche oder Segmente zu aktualisieren.

   ![Das Feld Segment hinzufügen im Fenster „Schnellbearbeitung“](./assets/image59.png)

## Aktualisieren von Datenblöcken

Klicken Sie auf das Aktualisierungssymbol, um die Datenblöcke in der Liste zu aktualisieren.

<img src="./assets/refresh-icon.png" width="15%" alt="Aktualisierungssymbol"/>

Um zu überprüfen, ob ein Datenblock aktualisiert wurde, rufen Sie das Aktualisierungsstatus-Symbol auf.

Bei einem erfolgreich aktualisierten Datenblock wird ein Häkchen in einem grünen Kreis angezeigt: <img src="./assets/refresh-success.png" width="5%" alt="Grüner Kreis mit Häkchen"/>.

Bei einem Datenblock, der nicht aktualisiert werden konnte, wird das Warnsymbol angezeigt: <img src="./assets/refresh-failure.png" width="5%" alt="Rotes Dreieck mit Ausrufezeichen"/>. Auf diese Weise lässt sich leicht erkennen, ob Datenblöcke Fehler aufweisen.


![Datenblock-Manager, der den Aktualisierungsstatus für jeden aufgelisteten Datenblock anzeigt.](./assets/image512.png)

## Löschen von Datenblöcken

Klicken Sie auf das Papierkorbsymbol, um einen ausgewählten Datenblock zu löschen.

## Gruppieren von Datenblöcken

Sie können Datenblöcke mithilfe des Dropdown-Menüs **Gruppieren nach** gruppieren. Alternativ können Sie auch auf einen Spaltentitel klicken. Um Datenblöcke nach Spalten zu sortieren, klicken Sie auf den Spaltentitel. Um Datenblöcke nach Gruppen zu gruppieren, wählen Sie einen Gruppennamen aus dem Dropdown-Menü **Gruppieren nach** aus. Der folgende Screenshot zeigt ein Beispiel für nach Blatt gruppierte Datenblöcke. Darin sind Datenblöcke zu sehen, die nach Blatt 1 und Blatt 2 gruppiert sind.  Dies ist beispielsweise nützlich, wenn ein Anwendungsfall zum Ersetzen von Segmenten verwendet wird. Wenn auf jeden Datenblock mehrere Segmente angewendet werden, ist es hilfreich, eine Gruppe zu erstellen, die alle Datenblöcke enthält, die Sie ersetzen möchten. Dann können Sie sie einfach gemeinsam auswählen und alle gleichzeitig bearbeiten.

![Datenblock-Manager mit der Liste „Gruppieren nach Blatt“.](./assets/group-data-blocks.png)

## Ändern der Ansicht von Datenblock-Manager

Sie können auswählen, welche Spalten im Fenster „Datenblock-Manager“ angezeigt werden sollen.


Klicken Sie auf das <img src="./assets/image515.png" width="3%" alt="Symbol für Spaltenliste"/>-Symbol der Spaltenliste, um auszuwählen, welche Spalten im Datenblock-Manager aufgeführt werden. Wählen Sie einen Spaltennamen aus, um die entsprechende Spalte anzuzeigen. Heben Sie die Auswahl des Spaltennamens auf, um die Spalte aus der Ansicht zu entfernen.

![Datenblock-Manager mit der Spaltenliste](./assets/image516.png)
