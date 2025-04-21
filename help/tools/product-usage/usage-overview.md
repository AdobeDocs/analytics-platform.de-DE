---
title: Produktnutzungsübersicht
description: Zeigen Sie Erkenntnisse und Berichte dazu an, wie Ihre Organisation Customer Journey Analytics nutzt.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 100%

---

# Produktnutzungsübersicht

Die Produktnutzung bietet Ihrer Organisation die Möglichkeit, Analysedaten zur Verwendung von Customer Journey Analytics anzuzeigen. Sie steht allen Organisationen zur Verfügung, die Customer Journey Analytics nutzen. Nach der Aktivierung werden die folgenden Adobe Experience Platform-Komponenten automatisch erstellt und für Sie verbunden. Diese Komponenten sind alle im Besitz des Systems, schreibgeschützt und können nicht bearbeitet werden:

* ein Schema in Adobe Experience Platform
* ein Datensatz in Adobe Experience Platform
* eine Verbindung in Customer Journey Analytics
* eine Datenansicht in Customer Journey Analytics

Alle Datenerfassungs- und Einrichtungsoptionen werden nach der Aktivierung automatisch konfiguriert. Jede benutzerseitige Aktion in Analysis Workspace wird verfolgt und steht zum Reporting zur Verfügung.

>[!IMPORTANT]
>
>Diese Funktion zählt für Ihre vertraglichen Zeilenbeschränkungen in Adobe Experience Platform. Stellen Sie sicher, dass Ihre Organisation die von dieser Funktion generierten Daten verarbeiten kann, bevor Sie sie aktivieren.

## Produktnutzung aktivieren

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Produktnutzung]**

Wenn Sie zu diesem Abschnitt der Benutzeroberfläche in Customer Journey Analytics navigieren, gelangen Sie zu den [Dateneinstellungen](data-settings.md). Dort können Sie diese Funktion aktivieren.

## Verfügbare Dimensionen

Wenn Sie die Produktnutzung aktivieren, sind die folgenden Dimensionen verfügbar. Wenn Sie Dimensionseinstellungen ändern möchten, erstellen Sie eine Kopie der systemeigenen Datenansicht und verwenden Sie die kopierte Datenansicht in Analysis Workspace.

* **[!UICONTROL Aktionsname]**: Der Aktionstyp, den die Benutzerin bzw. der Benutzer ausgeführt hat. Sie können diese Dimension als beliebige Metrik verwenden, indem Sie in den Einstellungen für die Datenansicht eine Kopie erstellen. Zu den Dimensionselementen gehören:
   * [!UICONTROL Attribution hinzufügen]
   * [!UICONTROL Komponente hinzufügen]
   * [!UICONTROL Panel hinzufügen]
   * [!UICONTROL Visualisierung hinzufügen]
   * [!UICONTROL Neue geführte Analyse erstellen]
   * [!UICONTROL Neues Projekt erstellen]
   * [!UICONTROL Komponenten kuratieren]
   * [!UICONTROL CSV herunterladen]
   * [!UICONTROL PDF herunterladen]
   * [!UICONTROL Geführte Analyse laden]
   * [!UICONTROL Projekt laden]
   * [!UICONTROL Neue Scorecard geladen]
   * [!UICONTROL Datenwörterbuch öffnen]
   * [!UICONTROL Intelligente Beschriftungen öffnen]
   * [!UICONTROL Projektfreigabe]
   * [!UICONTROL Panel „Experiment durchführen“]
   * [!UICONTROL Projekt speichern]
   * [!UICONTROL Scorecard gespeichert]
   * [!UICONTROL Datei senden]
   * [!UICONTROL Datei planmäßig senden]
   * [!UICONTROL Projekt für alle freigeben]
   * [!UICONTROL Projekt für Workspace-Benutzende freigeben]
* **[!UICONTROL Verwendetes Attributionsmodell]**: Der Typ des Attributionsmodells, das von der Komponente verwendet wird. Zu den Dimensionselementen gehören:
   * [!UICONTROL Letztkontakt]
   * [!UICONTROL Erstkontakt]
   * [!UICONTROL Linear]
   * [!UICONTROL Beitrag]
   * [!UICONTROL Gleicher Kontaktpunkt]
   * [!UICONTROL U-Form]
   * [!UICONTROL J-Kurve]
   * [!UICONTROL Umgekehrtes J]
   * [!UICONTROL Zeitverfall]
   * [!UICONTROL Benutzerspezifisch]
   * [!UICONTROL Algorithmisch]
* **[!UICONTROL Name der Komponente]**: Der Name der Komponente, die hinzugefügt, entfernt oder geändert wurde.
* **[!UICONTROL Typ der Komponente]**: Der Typ der Komponente, die hinzugefügt, entfernt oder geändert wurde. Zu den Dimensionselementen gehören:
   * [!UICONTROL Dimension]
   * [!UICONTROL Metrik]
   * [!UICONTROL Segment]
   * [!UICONTROL Berechnete Kennzahl]
   * [!UICONTROL Datumsbereich]
   * [!UICONTROL Anmerkung]
   * [!UICONTROL Warnhinweis]
* **[!UICONTROL Anmeldebenutzerin bzw. Anmeldebenutzer]**: Die Benutzerin bzw. der Benutzer, die bzw. der die Aktion ausgeführt hat.
* **[!UICONTROL Verwendetes Bedienfeld]**: Das Panel, in dem die Komponente hinzugefügt, entfernt oder geändert wurde. Zu den Dimensionselementen gehören:
   * [!UICONTROL Attribution]
   * [!UICONTROL Leeres Bedienfeld]
   * [!UICONTROL Experimentieren]
   * [!UICONTROL Freiform]
   * [!UICONTROL Nächstes oder vorheriges Objekt]
   * [!UICONTROL Quick Insights]
   * [!UICONTROL Trends]
   * [!UICONTROL Trichter]
   * [!UICONTROL Benutzerwachstum]
   * [!UICONTROL Auswirkungen]
   * [!UICONTROL Benutzer-Stream]
   * [!UICONTROL Kundentreue]
   * [!UICONTROL Funktionsmatrix]
* **[!UICONTROL Projektname]**: Der Anzeigename des Projekts.
* **[!UICONTROL Projekttyp]**: Der Projekttyp. Zu den Dimensionselementen gehören:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Verwendete Visualisierung]**: Die Visualisierung, die hinzugefügt, entfernt oder geändert wurde. Zu den Dimensionselementen gehören:
   * [!UICONTROL Freiformtabelle]
   * [!UICONTROL Kohortentabelle]
   * [!UICONTROL Fallout]
   * [!UICONTROL Fluss]
   * [!UICONTROL Journey-Arbeitsflächen-Reportlet]
   * [!UICONTROL Bereich]
   * [!UICONTROL Bereiche gestapelt]
   * [!UICONTROL Balken]
   * [!UICONTROL Balken gestapelt]
   * [!UICONTROL Bullet]
   * [!UICONTROL Kombination]
   * [!UICONTROL Ringdiagramm]
   * [!UICONTROL Histogramm]
   * [!UICONTROL Horizontalbalken]
   * [!UICONTROL Horizontalbalken gestapelt]
   * [!UICONTROL Zusammenfassung der Schlüsselmetriken]
   * [!UICONTROL Linie]
   * [!UICONTROL Zuordnung]
   * [!UICONTROL Streuung]
   * [!UICONTROL Abschnittskopfzeile]
   * [!UICONTROL Zusammenfassungsänderung]
   * [!UICONTROL Zusammenfassungszahl]
   * [!UICONTROL Text]
   * [!UICONTROL Treemap]
   * [!UICONTROL Venn]

Die Produktnutzung verfolgt nicht einzelne Projektkomponenten, wenn ein Projekt lediglich geöffnet oder angezeigt wird. Die Benutzeraktion beim Öffnen eines Projekts wird jedoch verfolgt.
