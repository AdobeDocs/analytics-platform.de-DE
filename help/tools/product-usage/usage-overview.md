---
title: Übersicht über die Produktnutzung
description: Insights und Berichte zur Verwendung von Customer Journey Analytics in Ihrem Unternehmen anzeigen.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---

# Übersicht über die Produktnutzung

Die Produktnutzung bietet Ihrem Unternehmen die Möglichkeit, Analysedaten darüber anzuzeigen, wie Ihr Unternehmen Customer Journey Analytics verwendet. Es ist für alle Organisationen verfügbar, die Customer Journey Analytics verwenden. Nach der Aktivierung werden die folgenden Adobe Experience Platform-Komponenten automatisch erstellt und für Sie verbunden. Diese Komponenten sind alle im Besitz des Systems, schreibgeschützt und können nicht bearbeitet werden.

* Ein Schema in Adobe Experience Platform
* Ein Datensatz in Adobe Experience Platform
* Eine Verbindung in Customer Journey Analytics
* Eine Datenansicht auf Customer Journey Analytics

Alle Datenerfassungs- und -einstellungen werden automatisch konfiguriert, sobald sie aktiviert sind. Jedes Mal, wenn ein Benutzer eine Aktion in Analysis Workspace vornimmt, wird diese Aktion verfolgt und steht für das Reporting zur Verfügung.

>[!IMPORTANT]
>
>Diese Funktion zählt für Ihre vertraglichen Zeilenbeschränkungen in Adobe Experience Platform. Stellen Sie sicher, dass Ihr Unternehmen die von dieser Funktion generierten Daten verarbeiten kann, bevor Sie sie aktivieren.

## Produktnutzung aktivieren

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Produktnutzung]**

Wenn Sie in Customer Journey Analytics zu diesem Abschnitt der Benutzeroberfläche navigieren, gelangen Sie zu [Dateneinstellungen](data-settings.md) wo Sie diese Funktion aktivieren können.

## Verfügbare Dimensionen

Wenn Sie die Produktnutzung aktivieren, sind die folgenden Dimensionen verfügbar. Wenn Sie Dimensionseinstellungen ändern möchten, erstellen Sie eine Kopie der systemeigenen Datenansicht und verwenden Sie die kopierte Datenansicht in Analysis Workspace.

* **[!UICONTROL Aktionsname]**: Der Aktionstyp, den der Benutzer ausgeführt hat. Sie können diese Dimension als beliebige Metrik verwenden, indem Sie in den Einstellungen für die Datenansicht eine Kopie erstellen. Zu den Dimensionen gehören:
   * [!UICONTROL Attribution hinzufügen]
   * [!UICONTROL Komponente hinzufügen]
   * [!UICONTROL Bedienfeld hinzufügen]
   * [!UICONTROL Visualisierung hinzufügen]
   * [!UICONTROL Erstellen einer neuen geführten Analyse]
   * [!UICONTROL Neues Projekt erstellen]
   * [!UICONTROL Komponenten kuratieren]
   * [!UICONTROL CSV herunterladen]
   * [!UICONTROL PDF herunterladen]
   * [!UICONTROL Geführte Analyse laden]
   * [!UICONTROL Projekt laden]
   * [!UICONTROL Neue Scorecard geladen]
   * [!UICONTROL Datenwörterbuch öffnen]
   * [!UICONTROL Intelligente Untertitel öffnen]
   * [!UICONTROL Projektfreigabe]
   * [!UICONTROL Experimentier-Bedienfeld ausführen]
   * [!UICONTROL Projekt speichern]
   * [!UICONTROL Scorecard gespeichert]
   * [!UICONTROL Datei senden]
   * [!UICONTROL Datei planmäßig senden]
   * [!UICONTROL Projekt für alle freigeben]
   * [!UICONTROL Projekt für Workspace-Benutzer freigeben]
* **[!UICONTROL Attributionsmodell verwendet]**: Der Typ des Attributionsmodells, das die Komponente verwendet. Zu den Dimensionen gehören:
   * [!UICONTROL Letztkontakt]
   * [!UICONTROL Erstkontakt]
   * [!UICONTROL Linear]
   * [!UICONTROL Beitrag]
   * [!UICONTROL Selber Kontakt]
   * [!UICONTROL U-förmig]
   * [!UICONTROL J-Kurve]
   * [!UICONTROL Umgekehrt J]
   * [!UICONTROL Zeitverfall]
   * [!UICONTROL Benutzerspezifisch]
   * [!UICONTROL Algorithmisch]
* **[!UICONTROL Komponentenname]**: Der Name der Komponente, die hinzugefügt, entfernt oder geändert wurde.
* **[!UICONTROL Komponententyp]**: Der Typ der Komponente, die hinzugefügt, entfernt oder geändert wurde. Zu den Dimensionen gehören:
   * [!UICONTROL Dimension]
   * [!UICONTROL Metrik]
   * [!UICONTROL Filter]
   * [!UICONTROL Berechnete Kennzahl]
   * [!UICONTROL Datumsbereich]
   * [!UICONTROL Anmerkung]
   * [!UICONTROL Warnhinweis]
* **[!UICONTROL Benutzer anmelden]**: Der Benutzer, der die Aktion ausgeführt hat.
* **[!UICONTROL Bedienfeld verwendet]**: Das Bedienfeld, in dem die Komponente hinzugefügt, entfernt oder geändert wurde. Zu den Dimensionen gehören:
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
* **[!UICONTROL Projekttyp]** Der Projekttyp. Zu den Dimensionen gehören:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Verwendete Visualisierung]**: Die Visualisierung, die hinzugefügt, entfernt oder geändert wurde. Zu den Dimensionen gehören:
   * [!UICONTROL Freiformtabelle]
   * [!UICONTROL Kohortentabelle]
   * [!UICONTROL Fallout]
   * [!UICONTROL Fluss]
   * [!UICONTROL Journey Canvas-Reportlet]
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
   * [!UICONTROL Zusammenfassung einer Schlüsselmetrik]
   * [!UICONTROL Linie]
   * [!UICONTROL Zuordnung]
   * [!UICONTROL Streuung]
   * [!UICONTROL Bereichs-Kopfzeile]
   * [!UICONTROL Zusammenfassungsänderung]
   * [!UICONTROL Zusammenfassungszahl]
   * [!UICONTROL Text]
   * [!UICONTROL Treemap]
   * [!UICONTROL Venn]

Die Produktnutzung verfolgt nicht einzelne Projektkomponenten, wenn ein Projekt lediglich geöffnet oder angezeigt wird. Die Benutzeraktion beim Öffnen eines Projekts wird jedoch verfolgt.
