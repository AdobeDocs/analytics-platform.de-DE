---
description: Informationen zum Verwalten von Warnhinweisen.
title: Verwalten von Warnhinweisen
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
TQID: https://experienceleague.adobe.com/oKewVodxYwDlnsuqGclK6ZYEmN-pXNqbc5ud6OkIUK4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: de8f8e06f074fdcb0219ce7286785d870c2093b4
workflow-type: tm+mt
source-wordcount: 589
ht-degree: 22%

---

# Verwalten von Warnhinweisen


Sie können Warnhinweise über eine zentrale Verwaltungsoberfläche von [!UICONTROL Warnhinweise“ filtern, taggen, löschen, umbenennen, kopieren] aktivieren, deaktivieren, erneuern und exportieren. So verwalten Sie Warnhinweise:

* Wählen Sie **[!UICONTROL Hauptbenutzeroberfläche]** Komponenten“ und dann **[!UICONTROL Warnhinweise]** aus.

Der Warnhinweis-Manager ist wie der [Segment-Manager](/help/components/segments/seg-manage.md) und der [Manager für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-manager.md) strukturiert.


## Warnhinweis-Manager

Der Warnhinweis-Manager verfügt über die folgenden Elemente der Benutzeroberfläche:

![Benutzeroberfläche für Filter](assets/alerts-manager.png)

### Liste der Warnhinweise

Die Warnhinweisliste zeigt ➊ die von Ihnen erstellten Warnhinweise an. Als Administrator sehen Sie alle Warnhinweise.

Die Liste umfasst die folgenden Spalten:

| Spalte | Beschreibung |
|---|---|
| ![UnausgefüllterStern](/help/assets/icons/StarOutline.svg) | Wählen Sie aus![ um einen Warnhinweis ](/help/assets/icons/Star.svg)Star“ oder ![StarOutline](/help/assets/icons/StarOutline.svg) zu bevorzugen. |
| **[!UICONTROL Titel und Beschreibung]** | Um den Warnhinweis zu bearbeiten, klicken Sie auf den Titel-Link, über den der [Warnhinweiserstellung“ geöffnet ](alert-builder.md#alert-builder). |
| **[!UICONTROL Typ]** | Zeigt an, ob es sich bei dem Warnhinweis um einen Customer Journey Analytics-Datenwarnhinweis oder einen Warnhinweis zur Nutzung von Server-Aufrufen handelt. |
| **[!UICONTROL Aktiviert]** | Gibt an, ob der Warnhinweis aktiviert oder deaktiviert ist. |
| **[!UICONTROL Datenansicht]** | Die Datenansichten, für die dieser Warnhinweis gilt. |
| **[!UICONTROL Inhabende]** | Der Besitzer des Warnhinweises. Wenn Sie kein Administrator sind, sehen Sie nur Warnhinweise, deren Inhaber Sie sind. Ein Administrator kann alle Warnhinweise sehen. |
| **[!UICONTROL Tags]** | Die Tags für diesen Warnhinweis. |
| **[!UICONTROL Ablaufdatum]** | Datum und Uhrzeit, zu der der Warnhinweis ablaufen soll. |
| **[!UICONTROL Änderungsdatum]** | Datum und Uhrzeit der letzten Änderung des Warnhinweises. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Verwenden Sie ![Spalteneinstellung](/help/assets/icons/ColumnSetting.svg), um die anzuzeigenden Spalten anzugeben.

### Aktionsleiste

Sie können Aktionen für Warnhinweise mithilfe der Aktionsleiste ➋. Die Aktionsleiste ermöglicht die folgenden Aktionen:

| Symbol | Aktion | Beschreibung |
|:---:|---|---|
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Hinzufügen]** | Fügen Sie mithilfe der [Warnhinweiserstellung“ einen weiteren ](alert-builder.md#alert-builder) hinzu. |
| ![Durchsuchen](/help/assets/icons/Search.svg) | [!UICONTROL *Nach Titel suchen*] | Wenn kein Warnhinweis in der Liste ausgewählt ist, suchen Sie mithilfe dieses Suchfelds nach Warnhinweisen. |
| ![Beschriftung](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Markieren Sie die ausgewählten Warnhinweise. Wählen Sie im **[!UICONTROL Warnhinweis]**-Dialogfeld die Tags für die ausgewählten Warnhinweise aus bzw. heben Sie die Auswahl auf. Klicken Sie **[!UICONTROL Speichern]**, um die Tags für die ausgewählten Warnhinweise zu speichern. |
| ![Löschen](/help/assets/icons/Delete.svg) | **[!UICONTROL Löschen]** | Löscht die ausgewählten Warnhinweise. Sie werden zur Bestätigung aufgefordert. |
| ![Bearbeiten](/help/assets/icons/Edit.svg) | **[!UICONTROL Umbenennen]** | Umbenennen eines einzelnen ausgewählten Warnhinweises. Wenn ausgewählt, können Sie den Warnhinweis inline umbenennen. |
| ![Kopieren](/help/assets/icons/Copy.svg) | **[!UICONTROL Kopieren]** | Kopieren Sie den ausgewählten Warnhinweis. Neue Warnhinweise werden mit demselben Namen und derselben Suffix-`(Copy)` erstellt. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aktivieren]** oder **[!UICONTROL Deaktivieren]** | Aktivieren oder Deaktivieren der ausgewählten Warnhinweise. |
| ![Aktualisieren](/help/assets/icons/Refresh.svg) | **[!UICONTROL Verlängern]** | Verlängert das Ablaufdatum für einen Warnhinweis. Das Ablaufdatum liegt unabhängig vom ursprünglichen Ablaufdatum 1 Jahr ab dem Tag, an dem Sie diese Option auswählen. |
| ![CSV-Datei](/help/assets/icons/FileCSV.svg) | **[!UICONTROL In CSV exportieren]** | Exportieren Sie die Warnhinweise in eine `Alerts List.csv`. |


### Aktive Filterleiste

Die Filterleiste zeigt ➌ die aktiven Filter an, die vom Filterbereich auf die Liste der Warnhinweise (falls vorhanden) angewendet wurden. Mit ![XGröße75](/help/assets/icons/CrossSize75.svg) können Sie schnell einen Filter entfernen. Wenn mehr als ein Filter angegeben ist, können Sie alle Filter mit **[!UICONTROL Alle entfernen]** entfernen.


### Panel „Filter“

Sie können die Liste der Warnhinweise mithilfe der ➍ ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** im linken Bereich filtern. Das Bedienfeld „Filter“ zeigt den Filtertyp und die Anzahl der Warnhinweise an, die den spezifischen Filter berücksichtigen.


1. Wählen Sie ![Filter](/help/assets/icons/Filter.svg) aus, um das Bedienfeld „Filter“ zu öffnen. Wenn Sie mehr Platz für die Liste „Warnhinweise“ benötigen, können Sie erneut ![Filtern](/help/assets/icons/Filter.svg) auswählen, um das Bedienfeld zu schließen.
1. Wählen Sie Filter aus einem der verfügbaren Filterabschnitte aus.


#### Abschnitt zum Tags-Filter

{{tagfiltersection}}


#### Abschnitt zu Datenansichtsfiltern

{{dataviewfiltersection}}


#### Filterabschnitt Besitzer

{{ownerfiltersection}}


#### Abschnitt zu Filtern nach aktivierten Status

{{enabledstatusfiltersection}}


#### Abschnitt zu Typenfiltern

{{typefiltersection}}


#### Abschnitt zu Filtern von anderen Filtern

{{otherfiltersfiltersection}}



## Warnhinweise bearbeiten

Sie können einen Warnhinweis bearbeiten

* Wählen Sie in [[!UICONTROL  Liste ]Warnhinweis](#alerts-list) den Titel des Warnhinweises aus.

Verwenden Sie die [Warnhinweiserstellung](alert-builder.md#alert-builder), um den Warnhinweis zu bearbeiten.

## Fehlerbehebung bei einem Warnhinweis

Wenn Sie ein Problem mit einem Warnhinweis beheben, geben Sie die JID-Nummer (Job Instance ID) an den Adobe-Support an. Die JID-Nummer befindet sich am unteren Rand der E-Mail-Benachrichtigung, die Sie erhalten.

![Warninweis-E-Mail](assets/alerts-email.PNG)
