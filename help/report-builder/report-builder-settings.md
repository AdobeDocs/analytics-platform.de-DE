---
title: Konfigurieren von Einstellungen für Report Builder in Customer Journey Analytics
description: Beschreibt, wie Einstellungen für Offline-Modus, Sprache, Datum und Fehlerbehebung festgelegt werden.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 31%

---

# Report Builder-Einstellungen

Verwenden Sie den Bereich **Einstellungen**, um Einstellungen auf Anwendungsebene zu konfigurieren, z. B. die von der UI angezeigte Sprache oder ob das Arbeiten im Offline-Modus möglich sein soll oder nicht. Die Einstellungen gelten sofort und sind für alle zukünftigen Sitzungen festgelegt, bis sie geändert werden.

So ändern Sie die Report Builder-Einstellungen

1. Wählen Sie das Symbol **Einstellungen** aus.

1. Nehmen Sie Änderungen an [Aktivieren oder Deaktivieren des Offline-](#off-line-mode), [Sprache auswählen](#language) oder [Fehlerbehebung aktivieren](#troubleshooting) vor.

1. Wählen Sie **[!UICONTROL Anwenden]** aus.

   ![Datumsbereich von Report Builder mit den Schaltflächen „Abbrechen“ und „Anwenden“.](./assets/report-builder-settings.png){zoomable="yes"}

## Offline-Modus

Wenn Sie einen Datenblock im Offline-Modus erstellen und bearbeiten, werden keine Daten abgerufen. Stattdessen werden Simulationsdaten verwendet, damit Sie schnell arbeiten können, ohne auf die Ausführung der Anfrage zu warten. Wenn Sie wieder online sind, wählen Sie ![Aktualisieren](/help/assets/icons/Refresh.svg) **[!UICONTROL Datenblock aktualisieren]** oder ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Alle Datenblöcke aktualisieren]**, um die Datenblöcke mit den tatsächlichen Daten zu aktualisieren.

So aktivieren Sie den Offline-Modus

1. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) aus.

1. Schalten Sie **[!UICONTROL Offline-Modus aktivieren]** ein.

1. Geben Sie eine positive Ganzzahl in das Feld **[!UICONTROL Metrikdaten anzeigen]** als ein.

1. Wählen Sie **[!UICONTROL Anwenden]** aus.


## Sprache

Sie können die Sprache für die Benutzeroberfläche von Report Builder auswählen. Alle unterstützten Customer Journey Analytics-Sprachen sind verfügbar.

So wählen Sie die in der Benutzeroberfläche von Report Builder verwendete Sprache aus:

1. Wählen Sie eine Sprache aus **[!UICONTROL Dropdown-Menü]** Sprache“ aus.

1. Wählen Sie **Apply.**

## Fehlerbehebung

Die Einstellung **[!UICONTROL Fehlerbehebungsprotokolle]** protokolliert alle Client/Server-Daten in einer lokalen Datei. Verwenden Sie diese Option, um Support-Tickets zu klären.

Um die Fehlerbehebungsprotokolle zu aktivieren, aktivieren Sie **[!UICONTROL Report Builder-Anfrage in lokaler Datei protokollieren]**.
