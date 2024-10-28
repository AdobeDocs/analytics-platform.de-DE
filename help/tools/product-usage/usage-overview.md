---
title: Produktnutzung - Übersicht
description: Zeigen Sie Einblicke und Berichte dazu an, wie Ihr Unternehmen Customer Journey Analytics verwendet.
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# Produktnutzung - Übersicht

{{release-limited-testing}}

Die Produktnutzung bietet Ihrem Unternehmen die Möglichkeit, Analysedaten zur Verwendung von Customer Journey Analytics anzuzeigen. Es ist für alle Unternehmen verfügbar, die Customer Journey Analytics verwenden. Nach der Aktivierung werden die folgenden Adobe Experience Platform-Komponenten automatisch erstellt und für Sie bereitgestellt. Diese Komponenten sind alle im Besitz des Systems, schreibgeschützt und können nicht bearbeitet werden.

* Ein Schema in Adobe Experience Platform
* Ein Datensatz in Adobe Experience Platform
* Eine Verbindung in Customer Journey Analytics
* Eine Datenansicht im Customer Journey Analytics

Die Datenerfassung und -einrichtung wird automatisch für Sie konfiguriert, sobald sie aktiviert sind. Jedes Mal, wenn ein Benutzer eine Aktion in Analysis Workspace ausführt, wird diese Aktion verfolgt und steht für Berichte zur Verfügung.

>[!IMPORTANT]
>
>Diese Funktion zählt zu Ihren vertraglichen Zeilenbeschränkungen in Adobe Experience Platform. Stellen Sie sicher, dass Ihre Organisation die durch diese Funktion erzeugten Daten berücksichtigen kann, bevor Sie sie aktivieren.

## Verfügbare Dimensionen

Wenn Sie die Produktnutzung aktivieren, sind die folgenden Dimensionen verfügbar. Wenn Sie Dimensionseinstellungen ändern möchten, erstellen Sie eine Kopie der systemeigenen Datenansicht und verwenden Sie die kopierte Datenansicht in Analysis Workspace.

| Dimension | Beschreibung |
| --- | --- |
| Aktionsname | Die Art der Aktion, die der Benutzer ausgeführt hat. Sie können diese Dimension wie eine beliebige Metrik verwenden, indem Sie eine Kopie in den Datenansichtseinstellungen erstellen. |
| Verwendetes Attributionsmodell | Der Typ des Attributionsmodells, das die Komponente verwendet. |
| Komponente | Ein abgeleitetes Feld, das den Komponententyp und den Komponentennamen enthält. |
| Typ der Komponente | Der Typ der hinzugefügten, entfernten oder geänderten Komponente. |
| Anmeldebenutzerin bzw. Anmeldebenutzer | Der Benutzer, der die Aktion ausgeführt hat. |
| Verwendetes Bedienfeld | Das Bedienfeld, in dem die Komponente hinzugefügt, entfernt oder geändert wurde. |
| Projektname | Der Anzeigename des Projekts. |
| Projekttyp | Der Projekttyp. |
| Benutzer-ID | Die Benutzer-ID, die das Ereignis ausgelöst hat. |
| Verwendete Visualisierung | Die Visualisierung, die hinzugefügt, entfernt oder geändert wurde. |

Die Produktnutzung verfolgt keine einzelnen Projektkomponenten, wenn ein Projekt nur geöffnet oder angezeigt wird. Die Benutzeraktion beim Öffnen eines Projekts wird jedoch verfolgt.
