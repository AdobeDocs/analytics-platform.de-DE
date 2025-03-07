---
title: Was ist der Report Builder-Hub in Customer Journey Analytics?
description: Beschreibt die Report Builder-Hub-Komponenten
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 88%

---

# Report Builder-Hub

Verwenden Sie den Report Builder-Hub, um Datenblöcke zu erstellen, zu aktualisieren, zu löschen und zu verwalten.

Der Report Builder-Hub enthält die Schaltflächen „Erstellen“ und „Verwalten“ sowie die Liste BEFEHLE und die Bedienfelder zur SCHNELLBEARBEITUNG.

<img src="./assets/hub51.png" width="50%" alt="Report Builder-Hub"/>


## Die Schaltflächen „Erstellen“ und „Verwalten“

Verwenden Sie die Schaltflächen „Erstellen“ oder „Verwalten“, um neue Datenblöcke zu erstellen oder vorhandene Datenblöcke zu verwalten.

## Bedienfeld „Befehle“

Verwenden Sie das Bedienfeld „Befehle“, um auf Befehle zuzugreifen, die mit den ausgewählten Zellen oder einer vorherigen Aktion kompatibel sind.

![Bedienfeld „Befehle“ im Report Builder-Hub](./assets/hub1.png)

### Befehle

| Angezeigte Befehle | Verfügbar wenn… | Zweck |
|------|------------------|--------|
| Datenblock erstellen | Eine oder mehrere Zellen sind in der Arbeitsmappe ausgewählt. | Dient zum Erstellen eines Datenblocks |
| Datenblock bearbeiten | Die ausgewählte Zelle bzw. der ausgewählte Zellenbereich ist nur Teil eines Datenblocks. | Dient zum Bearbeiten eines Datenblocks |
| Datenblock aktualisieren | Die Auswahl enthält mindestens einen Datenblock. Mit dem Befehl werden nur die Datenblöcke in der Auswahl aktualisiert. | Wird zum Aktualisieren eines oder mehrerer Datenblöcke verwendet |
| Alle Datenblöcke aktualisieren | Die Arbeitsmappe enthält einen oder mehrere Datenblöcke. | Wird zum Aktualisieren aller Datenblöcke in der Arbeitsmappe verwendet |
| Datenblock kopieren | Die ausgewählte Zelle oder der ausgewählte Zellbereich ist Teil eines oder mehrerer Datenblöcke. | Dient zum Kopieren eines Datenblocks |
| Datenblock löschen | Die ausgewählte Zelle bzw. der ausgewählte Zellenbereich ist nur Teil eines Datenblocks. | Dient zum Löschen eines Datenblocks |

## Bedienfeld „Schnellbearbeitung“

Wenn Sie einen oder mehrere Datenblöcke in einem Arbeitsblatt auswählen, zeigt Report Builder das Bedienfeld „Schnellbearbeitung“ an. Sie können das Bedienfeld „Schnellbearbeitung“ verwenden, um Parameter in einem Datenblock zu ändern oder Parameter in mehreren Datenblöcken gleichzeitig zu ändern.

![Das Bedienfeld „Schnellbearbeitung“ in Report Builder](./assets/hub2.png)

Die mithilfe der Schnellbearbeitungs-Bereiche vorgenommenen Änderungen gelten für alle ausgewählten Datenblöcke.

### Datenansichten

Datenblöcke rufen Daten aus einer ausgewählten Datenansicht ab. Wenn mehrere Datenblöcke in einem Arbeitsblatt ausgewählt sind und sie keine Daten aus derselben Datenansicht abrufen, zeigt der Link für **Datenansichten** *Mehrere* an.

Wenn Sie die Datenansicht ändern, übernehmen alle Datenblöcke in der Auswahl die neue Datenansicht. Komponenten im Datenblock werden mit der neuen Datenansicht abgeglichen, die beispielsweise auf einer ID basiert, die mit ```evars``` übereinstimmt). Wenn eine Komponente nicht in einem Datenblock gefunden wird, wird eine Warnmeldung angezeigt und die Komponente wird aus dem Datenblock entfernt.

Um die Datenansicht zu ändern, wählen Sie eine neue Datenansicht aus dem Dropdown-Menü aus.

![Der Report Builder-Hub mit dem Dropdown-Menü „Datenansicht“.](./assets/image16.png)

### Datumsbereich

**Datumsbereich** zeigt den Datumsbereich für die ausgewählten Datenblöcke an. Wenn mehrere Datenblöcke mit mehreren Datumsbereichen ausgewählt sind, zeigt der Link für **Datumsbereich** *Mehrere* an.

### Segmente 

Der **Segmente**-Link zeigt eine zusammenfassende Liste der Segmente an, die von den ausgewählten Datenblöcken verwendet werden. Wenn mehrere Datenblöcke mit mehreren angewendeten Segmenten ausgewählt sind, wird der Link **Segmente** angezeigt *Mehrere*.
