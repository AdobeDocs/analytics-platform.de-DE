---
title: Freigegebener Komponenten-Editor
description: Erstellen oder bearbeiten Sie freigegebene Dimensionen und Metriken.
exl-id: 3f6a808a-d6ac-4a47-a5e2-63b9f17952e8
TQID: https://experienceleague.adobe.com/vHmMlOpgjLAVzEg9t-MORtrHKsbqBABVcDFkuMlo5FM
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 0%

---

# Freigegebener Komponenten-Editor

Mit dem Editor für freigegebene Komponenten können Sie freigegebene Dimensionen und Metriken erstellen und bearbeiten. Sie verwendet beim [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md) viele Benutzeroberflächenelemente, aber diese Schnittstellen haben einen anderen Zweck:

* Mit dem Komponenteneditor für die Datenansicht können Sie für diese Datenansicht spezifische Komponenten erstellen und bearbeiten. Freigegebene Dimensionen oder Metriken können im Komponenteneditor für die Datenansicht nicht bearbeitet werden. In dieser Benutzeroberfläche können freigegebene Dimensionen und Metriken durch ein Symbol ![Freigegebene Komponente](/help/assets/icons/CCLibrary.svg) neben dem Komponentennamen identifiziert werden.
* Mit dem Editor für freigegebene Komponenten können Sie freigegebene Dimensionen und Metriken erstellen und bearbeiten. Sie können keine Komponenten bearbeiten, die zu einer einzelnen Datenansicht im freigegebenen Komponenten-Editor gehören.

![Screenshot des Komponenten-Editors](assets/component-editor.png)

Oben rechts befinden sich drei Schaltflächen:

* **[!UICONTROL Schließen]** oder **[!UICONTROL Abbrechen]**: Wenn alle Änderungen gespeichert wurden, wird der Editor durch Klicken auf **[!UICONTROL Schließen]** geschlossen. Wenn es ungespeicherte Änderungen gibt, wird mit der Schaltfläche **[!UICONTROL Abbrechen]** der Editor geschlossen, ohne dass diese Änderungen gespeichert werden.
* **[!UICONTROL Speichern]**: Speichert alle Komponenten und lässt den Editor geöffnet.
* **[!UICONTROL Speichern und beenden]**: Speichert alle Komponenten und schließt den Editor.

Die Benutzeroberfläche umfasst drei Hauptspalten/Abschnitte:

* **Schemafeldauswahl**: Suchen Sie die gewünschten Schemafelder und ziehen Sie sie in den Bereich Enthaltene Komponenten .
   * **Verbindung**: Die aktive Verbindung. Ändern Sie die aktive Verbindung im [Manager für freigegebene Metriken und Dimensionen](smd-overview.md).
   * **Komponentenliste**: Sie können zwischen der Auswahl [!UICONTROL Schemafelder] (neue freigegebene Dimensionen und Metriken) oder [!UICONTROL Metriken und Dimensionen] (vorhandene freigegebene Komponenten) aus dem Dropdown-Menü wählen.
   * **Suche**: Verwenden Sie das ![Suchsymbol](/help/assets/icons/Search.svg) Textsuche, um das gewünschte Schemafeld oder die freigegebene Komponente nach Namen zu suchen. Sie können auch Filter ![Filtersymbol](/help/assets/icons/Filter.svg) verwenden, um die Liste der Komponenten einzugrenzen. Der `Is not deprecated` ist standardmäßig aktiv.
   * **Abgeleitetes Feld erstellen**: Ermöglicht das [Erstellen eines abgeleiteten Felds](/help/data-views/derived-fields/derived-fields.md).
* **Enthaltene Komponenten**: Die Komponenten, die Sie für die Freigabe konfigurieren. Beim Erstellen gemeinsam genutzter Komponenten können Sie mehrere Schemafelder in diesen Bereich ziehen, um mehrere Komponenten gleichzeitig zu erstellen. Beim Bearbeiten freigegebener Komponenten können Sie mehrere zu bearbeitende Komponenten auswählen. Daraufhin werden alle in diesem Bereich ausgewählten Komponenten aufgelistet.
* **Komponenteneinstellungen**: Wenn Sie eine Komponente im Bereich Enthaltene Komponenten auswählen, können alle verfügbaren Einstellungen in dieser Spalte konfiguriert werden. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) für alle verfügbaren Optionen für Dimensionen und Metriken. Umschalt+Klicken auf mehrere Elemente im Bereich Enthaltene Komponenten ermöglicht es Ihnen, alle gängigen Felder gleichzeitig zu bearbeiten.
