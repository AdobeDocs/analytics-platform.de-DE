---
title: Übersicht über die Produktnutzung
description: Insights und Berichte zur Verwendung von Customer Journey Analytics in Ihrem Unternehmen anzeigen.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# Übersicht über die Produktnutzung

{{release-limited-testing}}

Die Produktnutzung bietet Ihrem Unternehmen die Möglichkeit, Analysedaten darüber anzuzeigen, wie Ihr Unternehmen Customer Journey Analytics verwendet. Es ist für alle Organisationen verfügbar, die Customer Journey Analytics verwenden. Nach der Aktivierung werden die folgenden Adobe Experience Platform-Komponenten automatisch erstellt und für Sie verbunden. Diese Komponenten sind alle im Besitz des Systems, schreibgeschützt und können nicht bearbeitet werden.

* Ein Schema in Adobe Experience Platform
* Ein Datensatz in Adobe Experience Platform
* Eine Verbindung in Customer Journey Analytics
* Eine Datenansicht auf Customer Journey Analytics

Alle Datenerfassungs- und -einstellungen werden automatisch konfiguriert, sobald sie aktiviert sind. Jedes Mal, wenn ein Benutzer eine Aktion in Analysis Workspace vornimmt, wird diese Aktion verfolgt und steht für das Reporting zur Verfügung.

>[!IMPORTANT]
>
>Diese Funktion zählt für Ihre vertraglichen Zeilenbeschränkungen in Adobe Experience Platform. Stellen Sie sicher, dass Ihr Unternehmen die von dieser Funktion generierten Daten verarbeiten kann, bevor Sie sie aktivieren.

## Verfügbare Dimensionen

Wenn Sie die Produktnutzung aktivieren, sind die folgenden Dimensionen verfügbar. Wenn Sie Dimensionseinstellungen ändern möchten, erstellen Sie eine Kopie der systemeigenen Datenansicht und verwenden Sie die kopierte Datenansicht in Analysis Workspace.

| Dimension | Beschreibung |
| --- | --- |
| Aktionsname | Die Art der Aktion, die der Benutzer ausgeführt hat. Sie können diese Dimension als beliebige Metrik verwenden, indem Sie in den Einstellungen für die Datenansicht eine Kopie erstellen. |
| Verwendetes Attributionsmodell | Der Typ des Attributionsmodells, das die Komponente verwendet. |
| Komponente | Ein abgeleitetes Feld, das den Komponententyp und den Komponentennamen enthält. |
| Typ der Komponente | Der Typ der hinzugefügten, entfernten oder geänderten Komponente. |
| Anmeldebenutzerin bzw. Anmeldebenutzer | Der Benutzer, der die Aktion durchgeführt hat. |
| Verwendetes Bedienfeld | Das Bedienfeld, in dem die Komponente hinzugefügt, entfernt oder geändert wurde. |
| Projektname | Der Anzeigename des Projekts. |
| Projekttyp | Der Projekttyp. |
| Benutzer-ID | Die Benutzer-ID, die das Ereignis ausgelöst hat. |
| Verwendete Visualisierung | Die Visualisierung, die hinzugefügt, entfernt oder geändert wurde. |

Die Produktnutzung verfolgt nicht einzelne Projektkomponenten, wenn ein Projekt lediglich geöffnet oder angezeigt wird. Die Benutzeraktion beim Öffnen eines Projekts wird jedoch verfolgt.
