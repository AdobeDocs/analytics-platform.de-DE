---
description: Warnhinweise erstellen, bearbeiten oder löschen.
title: Änderungen verwalten
feature: Workspace Basics
role: User, Admin
source-git-commit: bd58af0680fc9524453e072ecb60e3ada72ce634
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 4%

---

# Verwalten von Warnhinweisen


Sie können Warnhinweise über eine zentrale Verwaltungsoberfläche von [!UICONTROL Warnhinweise] filtern, taggen, löschen, umbenennen, kopieren, aktivieren, deaktivieren, verlängern und exportieren. Warnhinweise verwalten:

* Wählen Sie **[!UICONTROL Komponenten]** in der Hauptbenutzeroberfläche und dann **[!UICONTROL Warnhinweise]** aus.

Der Warnhinweis-Manager ähnelt sehr dem [Filter-Manager](/help/components/filters/manage-filters.md) und dem [Manager für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-manager.md).


## Warnhinweis-Manager

Der Warnhinweis-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![Filterschnittstelle](assets/alerts-manager.png)

### Liste der Warnhinweise

In der Liste der Warnhinweise werden alle Warnhinweise, die Ihnen gehören, sowie alle Warnhinweise, die für alle Ihre Projekte verfügbar sind, und die Warnhinweise angezeigt, die für Sie freigegeben wurden. Die Liste enthält die folgenden Spalten:

| Spalte | Beschreibung |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Wählen Sie diese Option aus, um ![Star](/help/assets/icons/Star.svg) oder den Warnhinweis für ![StarOutline](/help/assets/icons/StarOutline.svg) zu favorisieren. |
| **[!UICONTROL Titel und Beschreibung]** | Um den Warnhinweis zu bearbeiten, wählen Sie den Titel-Link aus, der den [Warnhinweiserstellung](alert-builder.md#alert-builder) öffnet. |
| **[!UICONTROL Typ]** | Zeigt an, ob es sich bei dem Warnhinweis um einen Customer Journey Analytics-Datenwarnungen oder einen Warnhinweis zur Nutzung von Server-Aufrufen handelt. |
| **[!UICONTROL Aktiviert]** | Gibt an, ob der Warnhinweis aktiviert oder deaktiviert ist. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieser Warnhinweis gilt. |
| **[!UICONTROL Inhabende]** | Der Eigentümer der Warnung. Als Nicht-Administrator werden nur Warnhinweise angezeigt, die Ihnen gehören oder für Sie freigegeben wurden. |
| **[!UICONTROL Tags]** | Die Tags für diese Warnung. |
| **[!UICONTROL Ablaufdatum]** | Datum und Uhrzeit des Ablaufs der Warnung. |
| **[!UICONTROL Datum geändert]** | Datum und Uhrzeit der letzten Änderung der Warnung. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Verwenden Sie ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) , um anzugeben, welche Spalten angezeigt werden sollen.

### Symbolleiste

Sie können Warnhinweise über die Aktionsleiste bearbeiten. Die Aktionsleiste enthält die folgenden Aktionen:

| Aktion | Beschreibung |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Fügen Sie mit dem [Alert Builder](alert-builder.md#alert-builder) einen weiteren Warnhinweis hinzu. |
| ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *Suche nach Titel*] | Wenn in der Liste kein Warnhinweis ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Warnhinweisen. |
| ![Beschriftung](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Taggen Sie die ausgewählten Warnhinweise. Wählen Sie im Dialogfeld **[!UICONTROL Warnhinweis taggen]** die Tags für die ausgewählten Warnhinweise aus oder deaktivieren Sie sie. Wählen Sie **[!UICONTROL Speichern]** aus, um die Tags für die ausgewählten Warnhinweise zu speichern. |
| ![Löschen](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]** | Löschen Sie die ausgewählten Warnhinweise. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Umbenennen]** | Benennen Sie eine einzelne ausgewählte Warnung um. Wenn diese Option aktiviert ist, können Sie den Warnhinweis inline umbenennen. |
| ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Kopieren]** | Kopieren Sie den ausgewählten Warnhinweis. Neue Warnhinweise werden mit demselben Namen und Suffix `(Copy)` erstellt. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Enable]** or **[!UICONTROL disable]** | Aktivieren oder deaktivieren Sie die ausgewählten Warnhinweise. |
| ![Aktualisieren](/help/assets/icons/Refresh.svg) **[!UICONTROL Verlängern]** | Verlängern Sie das Ablaufdatum des Warnhinweises. Das Ablaufdatum erstreckt sich ab dem Tag, an dem Sie diese Option auswählen, unabhängig vom ursprünglichen Ablaufdatum um 1 Jahr. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export in CSV]** | Exportieren Sie die Warnungen in eine `Alerts List.csv` -Datei. |


### Aktive Filterleiste

Die Filterleiste zeigt die aktiven Filter an, die aus dem Filterbereich auf die Liste der Warnhinweise angewendet werden (sofern vorhanden). Mit ![CrossSize75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.


### Filterbereich

Sie können die Liste der Warnhinweise mit dem linken Fensterbereich ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** filtern. Im Filterbereich werden der Filtertyp und die Anzahl der Warnhinweise angezeigt, die den jeweiligen Filter berücksichtigen.

{{filterspanel}}


#### Abschnitt &quot;Tags-Filter&quot;

{{tagfiltersection}}


#### Datenansichtsfilterabschnitt

{{dataviewfiltersection}}


#### Filterabschnitt für Inhaber

{{ownerfiltersection}}


#### Abschnitt für aktivierte Statusfilter

{{enabledstatusfiltersection}}


#### Filtertyp

{{typefiltersection}}


#### Abschnitt &quot;Sonstige Filter&quot;

{{otherfiltersfiltersection}}



## Warnhinweise bearbeiten

Sie können eine Warnung bearbeiten

* Wählen Sie in der Liste [[!UICONTROL Alert]](#alerts-list) den Titel des Warnhinweises aus.

Sie verwenden die [Warnhinweiserstellung](alert-builder.md#alert-builder), um den Warnhinweis zu bearbeiten.

## Fehlerbehebung bei einem Warnhinweis

Stellen Sie beim Beheben eines Problems mit einem Warnhinweis die JID-Nummer (Job Instance ID) für den Adobe-Support bereit. Die JID-Nummer befindet sich unten in der Benachrichtigungs-E-Mail mit dem Warnhinweis, die Sie erhalten.

![Warnhinweis-E-Mail](assets/alerts-email.PNG)
