---
title: Konfigurieren von Einverständnisberichten und -filtern
description: Erfahren Sie, wie Sie die Reporting- und Filterkonfigurationen für Einverständnisse anzeigen, bearbeiten und löschen und wie der Lookup-Datensatz für Einverständnisrichtlinien in Customer Journey Analytics synchron bleibt.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# Konfigurieren von Einverständnisberichten und -filtern

Nachdem Sie [eine Reporting- und Filterkonfiguration für Einverständnisse erstellt haben](/help/connections/consent-reporting-filtering/consent-configure.md) können Sie sie anzeigen, bearbeiten oder löschen.

Nur Systemadministratoren können Einverständnisberichte und Filterkonfigurationen verwalten.

Übersichtsinformationen finden Sie unter [Übersicht über Einverständnisberichte und -filter](/help/connections/consent-reporting-filtering/consent-overview.md).

## Anzeigen vorhandener Konfigurationen

So zeigen Sie Ihre vorhandenen Konfigurationen an:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Einverständnisberichte und -filter]** aus.

   Die folgenden Informationsspalten sind zu jeder Konfiguration verfügbar:

   * **[!UICONTROL Erstellt von]**: Der Benutzer, der die Konfiguration erstellt hat.

   * **[!UICONTROL Sandbox]**: Die Experience Platform-Sandbox, die den Profildatensatz enthält.

   * **[!UICONTROL Connection]**: Die Verbindung, auf die die Konfiguration angewendet wird.

   * **[!UICONTROL Filtern]**: Die Marketing-Aktionen, für die die Filterung aktiviert ist, falls vorhanden.

   * **[!UICONTROL Erstellungsdatum]**: Das Datum, an dem die Konfiguration erstellt wurde.

   * **[!UICONTROL Zuletzt geändert]**: Das Datum, an dem die Konfiguration zuletzt geändert wurde.

   * **[!UICONTROL Status]**: Der Status der Konfiguration.

   Sie können alle Spalten ausblenden, indem Sie auf das Spaltensymbol ![Spaltensymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) klicken, die Auswahl der Spalten, die Sie ausblenden möchten, aufheben und dann auf **[!UICONTROL Anwenden]** klicken.

1. (Optional) Um die Liste der Konfigurationen zu filtern, wählen Sie **Filter** ![Filtersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) und filtern Sie dann nach einem der folgenden Kriterien:

   * **[!UICONTROL Verbindung]**

   * **[!UICONTROL Erstellt von]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Status]**

## Bearbeiten einer Konfiguration

>[!IMPORTANT]
>
>Änderungen an der Filterung wirken sich nur auf Daten aus, die aufgenommen werden, nachdem Sie Ihre Änderungen an der Konfiguration gespeichert haben. Durch Aktivierung der Filterung werden Daten von Besuchern, die vor der Änderung aufgenommen wurden und nicht mit Einverständnis aufgenommen wurden, nicht entfernt. Durch Deaktivieren der Filterung werden keine Daten wiederhergestellt, die während der Aktivierung der Filterung ausgeschlossen wurden.

So bearbeiten Sie eine vorhandene Konfiguration:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Einverständnisberichte und -filter]** aus.

1. Wählen Sie den Namen der Konfiguration aus, die Sie bearbeiten möchten.

   Oder

   Aktivieren Sie das Kontrollkästchen neben der Konfiguration, die Sie bearbeiten möchten, und klicken Sie dann auf **[!UICONTROL Bearbeiten]**.

1. Nehmen Sie die gewünschten Änderungen vor und klicken Sie auf **[!UICONTROL Speichern]**.

## Löschen einer Konfiguration

So löschen Sie eine vorhandene Konfiguration:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Daten-Management]** > **[!UICONTROL Einverständnisberichte und -filter]** aus.

1. Aktivieren Sie das Kontrollkästchen neben der Konfiguration, die Sie löschen möchten, und klicken Sie dann auf **[!UICONTROL Löschen]**.

## Wie der Einverständnisrichtlinien-Lookup-Datensatz synchron bleibt

Customer Journey Analytics synchronisiert den Einverständnisrichtlinien-Lookup-Datensatz automatisch mit Experience Platform. Wenn eine Einverständnisrichtlinie in Experience Platform erstellt, aktualisiert, umbenannt oder gelöscht wird, werden der entsprechende Richtlinienname und die entsprechende Beschreibung im Suchdatensatz aktualisiert.

Beachten Sie Folgendes:

* Pro Sandbox ist maximal ein Einverständnisrichtlinien-Lookup-Datensatz vorhanden. Mehrere Konfigurationen in derselben Sandbox teilen diesen Lookup-Datensatz.
* Da Richtliniennamen und -beschreibungen aus Experience Platform stammen, sollten Sie die Richtlinienmetadaten in Experience Platform aktualisieren, anstatt den Lookup-Datensatz direkt zu bearbeiten.
