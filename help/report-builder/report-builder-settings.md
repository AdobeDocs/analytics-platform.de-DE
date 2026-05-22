---
title: Einstellungen für Report Builder konfigurieren
description: Erfahren Sie, wie Sie Einstellungen für Report Builder konfigurieren.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/voTu-CKMtY-0dWvxQd2RzGF8bU9xcuc7J1206kB-3Ao
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 257
ht-degree: 29%

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
