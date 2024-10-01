---
title: Produktnutzung - Übersicht
description: Zeigen Sie Einblicke und Berichte dazu an, wie Ihr Unternehmen Customer Journey Analytics verwendet.
hide: true
hidefromtoc: true
source-git-commit: dcd3ee5f3db5af434b87bfded0e360c66643793e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 6%

---

# Produktnutzung - Übersicht

{{release-limited-testing}}

Die Produktnutzung bietet Ihrem Unternehmen die Möglichkeit, Analysedaten zur Verwendung von Customer Journey Analytics anzuzeigen. Es ist für alle Unternehmen verfügbar, die Customer Journey Analytics verwenden. Nach der Aktivierung werden die folgenden Adobe Experience Platform-Komponenten automatisch erstellt und für Sie bereitgestellt:

* Ein Schema in Adobe Experience Platform. Dieses Schema ist schreibgeschützt und kann nicht bearbeitet werden.
* Ein Datensatz in Adobe Experience Platform. Die Einstellungen für diesen Datensatz sind schreibgeschützt und können nicht bearbeitet werden.
* Eine Verbindung im Customer Journey Analytics. Die Einstellungen für diese Verbindung sind schreibgeschützt und können nicht bearbeitet werden.
* Eine Datenansicht im Customer Journey Analytics. Sie können diese Datenansicht bearbeiten oder weitere Datenansichten mit derselben Verbindung erstellen.

Die Datenerfassung und -einrichtung wird automatisch für Sie konfiguriert, sobald sie aktiviert sind. Jedes Mal, wenn ein Benutzer eine Aktion in Analysis Workspace ausführt, wird diese Aktion verfolgt und steht für Berichte zur Verfügung.

>[!IMPORTANT]
>
>Diese Funktion zählt zu Ihren vertraglichen Zeilenbeschränkungen in Adobe Experience Platform. Stellen Sie sicher, dass Ihre Organisation die durch diese Funktion erzeugten Daten berücksichtigen kann, bevor Sie sie aktivieren.

## Verfügbare Dimensionen

Wenn Sie die Produktnutzung aktivieren, sind die folgenden Dimensionen verfügbar:

| Dimension | Beschreibung |
| --- | --- |
| Aktionsname | Die Art der Aktion, die der Benutzer ausgeführt hat. Sie können diese Dimension wie eine beliebige Metrik verwenden, indem Sie eine Kopie in den Datenansichtseinstellungen erstellen. |
| Verwendetes Attributionsmodell | Der Typ des Attributionsmodells, das die aktuelle Komponente verwendet. |
| Komponente | Ein abgeleitetes Feld. |
| Typ der Komponente | Der Typ der hinzugefügten, entfernten oder geänderten Komponente. |
| Verbindung | Die Verbindung, die das Projekt verwendet. |
| Datenansicht | Die Datenansicht, die vom Projekt verwendet wird. |
| Funktion | Die Funktion, die das Projekt verwendet. |
| Kennung | Die eindeutige Kennung für das Ereignis. |
| Anmeldebenutzerin bzw. Anmeldebenutzer | Der Benutzer, der die Aktion ausgeführt hat. |
| Bedienfeld verwendet | Das Bedienfeld, in dem die Komponente hinzugefügt, entfernt oder geändert wurde. |
| Projekt   | Ein abgeleitetes Feld. |
| Projektname | Der Anzeigename des Projekts. |
| Projekttyp | Der Projekttyp. |
| Benutzer-ID | Die Benutzer-ID, die das Ereignis ausgelöst hat. |
| Verwendete Visualisierung | Die Visualisierung, die hinzugefügt, entfernt oder geändert wurde. |

Die Produktnutzung verfolgt keine einzelnen Projektkomponenten, wenn ein Projekt nur geöffnet oder angezeigt wird. Die Benutzeraktion beim Öffnen eines Projekts wird jedoch verfolgt.
