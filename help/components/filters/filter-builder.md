---
description: Der Filtergenerator bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metrik -Dimensionen, -Filtern und -Ereignissen, um Personen basierend auf Container-Hierarchielogik, Regeln und Operatoren zu filtern. Mit diesem integrierten Entwicklungs-Tool können Sie einfache oder komplexe Filter erstellen und speichern, mit denen Personenattribute und Aktionen über Besuche und Ereignisse hinweg identifiziert werden.
title: Erstellen von Filtern
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 388708526204f0854b486643fa58d1f8504575aa
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 10%

---

# Erstellen von Filtern {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_createaudience"
>title="Erstellen einer Zielgruppe"
>abstract="Zielgruppen können mithilfe eines Filters erstellt und zur Aktivierung für Adobe Experience Platform freigegeben werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_datapreview"
>title="Datenvorschau"
>abstract="Vergleicht die Daten dieses Filters mit den Daten der Datenansicht. Der Prozentsatz der Vorschau basiert auf der Gesamtzahl der Daten in der Datenansicht aus den **letzten 90 Tagen**.<br><br/>Wenn die Vorschau nicht geladen wird, wird Ihre Verbindung möglicherweise noch aufgestockt."

<!-- markdownlint-enable MD034 -->



Das **[!UICONTROL Filter-Builder]**-Dialogfeld wird verwendet, um neue Filter zu erstellen oder vorhandene Filter zu bearbeiten. Das Dialogfeld heißt **[!UICONTROL Neuer Filter]** oder **[!UICONTROL Filter bearbeiten]** für Filter, die Sie über den [[!UICONTROL Filter]Manager erstellen oder verwalten](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Filter-Builder]

![Fenster „Filterdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/filter-builder.png)

>[!TAB Filter erstellen oder bearbeiten]

![Fenster „Filterdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) bedeutet erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für den Filter auswählen.  Der von Ihnen definierte Filter ist als Filter auf der Registerkarte [Einstellungen](/help/data-views/create-dataview.md#settings-filters) einer Datenansicht verfügbar. |
   | **[!UICONTROL Nur-Projekt-Filter]** | Ein Informationsfeld, in dem erläutert wird, dass der Filter nur in dem Projekt sichtbar ist, in dem er erstellt wurde, und nicht zur Komponentenliste hinzugefügt wird. Aktivieren Sie **[!UICONTROL Diesen Filter für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]** um diese Einstellung zu ändern. Dieses Infofeld wird nur angezeigt, wenn Sie einen [Schnellfilter](quick-filters.md) erstellen und den Schnellfilter mithilfe von **[!UICONTROL Open Builder]** in der [!UICONTROL Schnellfilter]-Oberfläche in einen regulären Filter umwandeln. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Benennen Sie den Filter, z. B. `Last month mobile customers`. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für den Filter an, z. B. `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organisieren Sie den Filter, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um nach vorhandenen Tags zu suchen, die Sie auswählen können. Oder drücken Sie **[!UICONTROL EINGABETASTE]**, um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Definition]** ![erforderlich](/help/assets/icons/Required.svg) | Definieren Sie Ihren Filter mit dem [Definition Builder](#definition-builder). |

   {style="table-layout:auto"}

1. Um sicherzustellen, dass Ihre Filterdefinition korrekt ist, verwenden Sie die ständig aktualisierte Vorschau der Ergebnisse des Filters oben rechts.
1. Um eine Zielgruppe aus dem Filter zu erstellen und die Zielgruppe für Experience Platform freizugeben, wählen Sie **[!UICONTROL Zielgruppe aus Filter erstellen]** aus. Weitere Informationen [ Sie unter ](/help/components/audiences/publish.md) und Veröffentlichen von Zielgruppen .
1. Auswählen:
   * **[!UICONTROL Speichern]**, um den Filter zu speichern.
   * **[!UICONTROL Speichern unter]**, um eine Kopie des Filters zu speichern.
   * **[!UICONTROL Löschen]**, um den Filter zu löschen.
   * **[!UICONTROL Abbrechen]**, um alle am Filter vorgenommenen Änderungen rückgängig zu machen oder die Erstellung eines neuen Filters abzubrechen.


## Definition Builder

Mit dem Definition Builder erstellen Sie Ihre Filterdefinition. In dieser Konstruktion verwenden Sie Komponenten, Container, Operatoren und Logik.

Sie können den Typ und den Umfang Ihrer Definition konfigurieren:

1. Um den Typ Ihrer Definition anzugeben, geben Sie an, ob Sie eine Ein- oder Ausschlussdefinition erstellen möchten. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** und aus dem Dropdown-Umschalter **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]**.
1. Um den Umfang Ihrer Definition anzugeben, wählen Sie aus dem Dropdown-Menü **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]** aus, ob der Umfang der Definition **[!UICONTROL Ereignis]**, **[!UICONTROL Sitzung]** oder **[!UICONTROL Person]** sein soll.

Sie können diese Einstellungen später jederzeit ändern.

### Komponenten

Ein wichtiger Teil beim Erstellen Ihrer Filterdefinition ist die Verwendung von Dimensionen, Metriken, vorhandenen Filtern und Datumsbereichen. Alle diese Komponenten sind über das Bedienfeld „Komponenten“ im Filter-Builder verfügbar.

![Mit dem Erstellen einer Definition beginnen](assets/start-building-filter.gif){width=100%}

So fügen Sie eine Komponente hinzu:

1. Ziehen Sie eine Komponente aus dem Bedienfeld „Komponenten“ auf **[!UICONTROL Ziehen Sie Metrik(en), Filter und/oder Dimensionen per Drag-and-Drop hierher]**. Sie können den ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.
1. Geben Sie Details für die Komponente an. Wählen Sie beispielsweise einen Wert unter **[!UICONTROL Wert auswählen]** aus. Oder geben Sie einen Wert ein. Was und wie Sie einen oder mehrere Werte angeben können, hängt von der Komponente und dem Operator ab.
1. Ändern Sie optional den Standardoperator. Beispiel: von **[!UICONTROL gleich]** bis **[!UICONTROL gleich einem von]**. Unter [Benutzer](operators.md) finden Sie einen detaillierten Überblick über die verfügbaren Benutzer.

So bearbeiten Sie eine Komponente:

* Wählen Sie im Dropdown-Menü Operator einen neuen Operator für die Komponente aus.
* Wählen Sie ggf. einen anderen Wert für den -Operator aus oder geben Sie ihn an.
* Wenn der Komponententyp eine Dimension ist, können Sie das Attributionsmodell definieren. Weitere Informationen finden [ unter ](#attribution-models)Attributionsmodell“.

So löschen Sie eine Komponente:

* Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) in einer Komponente aus.

### Container

Sie können mehrere Komponenten in einem oder mehreren Containern gruppieren und Logiken innerhalb und zwischen Containern definieren. Mit Containern können Sie komplexe Definitionen für Ihren Filter erstellen.

![Container hinzufügen](assets/add-container.gif){width=100%}

* Um einen Container hinzuzufügen, wählen Sie **[!UICONTROL Container hinzufügen]** unter ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** aus.
* Um eine vorhandene Komponente zum Container hinzuzufügen, ziehen Sie die Komponente per Drag-and-Drop in den Container.
* Um dem Container eine weitere Komponente hinzuzufügen, ziehen Sie eine Komponente aus dem Komponentenbedienfeld in den Container. Verwenden Sie die blaue Einfügezeile als Anleitung.
* Um eine weitere Komponente außerhalb des Containers hinzuzufügen, ziehen Sie eine Komponente aus dem Komponentenbereich außerhalb des Containers, aber innerhalb des Containers für die Hauptdefinition. Verwenden Sie die blaue Einfügezeile als Anleitung.
* Um die Logik zwischen Komponenten in einem Container, zwischen Containern oder zwischen einem Container und einer Komponente zu ändern, wählen Sie die entsprechenden **[!UICONTROL Und]**, **[!UICONTROL Oder]**, **[!UICONTROL Dann]**. Wenn Sie Dann auswählen, wandeln Sie den Filter in einen sequenziellen Filter um. Siehe [Erstellen sequenzieller Filter](seg-sequential-build.md) für weitere Informationen.
* Um die Container-Ebene zu wechseln, wählen ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Event]**, ![Visit](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** oder ![User](/help/assets/icons/User.svg)**[!UICONTROL Person]**.

Sie können ![Einstellung](/help/assets/icons/Setting.svg) in einem Container für die folgenden Aktionen verwenden:

| Container-Aktion | Beschreibung |
|---|---|
| **[!UICONTROL Container hinzufügen]** | Fügen Sie dem Container einen verschachtelten Container hinzu. |
| **[!UICONTROL Ausschließen]** | Schließen Sie das Ergebnis aus dem Container in der Filterdefinition aus. Ein dünner roter linker Balken kennzeichnet einen Ausschluss-Container. |
| **[!UICONTROL Einschließlich]** | Fügen Sie das Ergebnis aus dem Container in die Filterdefinition ein. Einschließen ist der Standard. Ein dünner, grauer linker Balken kennzeichnet einen Include-Container. |
| **[!UICONTROL Container benennen]** | Benennen Sie den Container ausgehend von seiner Standardbeschreibung um. Geben Sie einen Namen in das Textfeld ein. Wenn Sie keine Eingabe vornehmen, wird die Standardbeschreibung verwendet. |
| **[!UICONTROL Container löschen]** | Löschen Sie den Container aus der Definition. |


## Datumsbereiche

Sie können Filter erstellen, die rollierende Datumsbereiche enthalten. Sie können also Fragen zu laufenden Kampagnen oder Veranstaltungen beantworten. Sie können beispielsweise einen Filter erstellen, der Folgendes enthält *alle Personen, die in den letzten 60 Tagen einen Online-Kauf getätigt haben*.

![Filtern mit rollierendem Datumsbereich](assets/filter-rolling-date-range.gif)

+++ Im Folgenden finden Sie ein Video zur Verwendung rollierender Datumsbereiche in Filtern

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## Stapeln von Filtern {#stack}

Sie können einen Filter mithilfe von Filtern erstellen. Wenn Sie Filter in einem Filter verwenden, können Sie Ihren Filter optimieren und die Komplexität reduzieren.

Angenommen, Sie möchten nach der Kombination aus Gerätetyp (2) und US-Status (50) filtern. Sie können entweder 100 Filter erstellen, jeder für die eindeutige Kombination aus Gerätetyp (Mobiltelefon versus Tablet) und US-Bundesstaat. Um die kalifornischen Tablet-Benutzer zu erhalten, würden Sie einen der 100 Filter verwenden:

![Einfacher Filter für CA und Tablet](assets/filter-ca-tablet-single.png)

Oder Sie könnten 52 Filter definieren: 50 Filter für die US-Bundesstaaten, einer für Mobiltelefone und einer für Tablet. Stapeln Sie dann die Filter, um die gleichen Ergebnisse zu erhalten. Um die kalifornischen Tablet-Benutzer zu erhalten, würden Sie zwei Filter stapeln:

![Gestapelter Filter für CA und Tablet](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_repeating"
>title="Wiederholend"
>abstract="Umfasst Instanzen und persistierte Werte für die Dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_instance"
>title="Instanz"
>abstract="Umfasst Instanzen und persistierte Werte für die Dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_nonrepeatinginstance"
>title="Nicht wiederholende Instanz"
>abstract="Umfasst einzigartige (sich nicht wiederholende) Instanzen für die Dimension."

<!-- markdownlint-enable MD034 -->



Wenn Sie eine Dimension im Filter Builder verwenden, haben Sie die Möglichkeit, das Attributionsmodell für diese Dimension anzugeben. Das von Ihnen ausgewählte Attributionsmodell bestimmt, ob Daten für die Bedingung qualifiziert sind, die Sie für die Dimensionskomponente angegeben haben.

Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) in der Dimensionskomponente aus und wählen Sie eines der Attributionsmodelle aus dem Popup:

| Modelle | Beschreibung |
|---|---|
| **[!UICONTROL Wiederholungsmodell (Standard)]** | Schließen Sie die Instanz und persistierten Werte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Instanz]** | Schließen Sie nur Instanzwerte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Nicht wiederholende Instanz]** | Eindeutige Instanzwerte (sich nicht wiederholende Werte) für die Dimension einschließen, um die Qualifizierung zu bestimmen. |


![Attributionsmodell auf Dimension beim Erstellen eines Filters](assets/filter-dimension-attribution.png)

### Beispiel

Als Teil einer Filterdefinition haben Sie die folgende Bedingung angegeben: Seitenname ist gleich Frauen. Ähnlich wie im obigen Beispiel. Sie wiederholen diese Filterdefinition mit den beiden anderen Attributionsmodellen. Sie haben also drei Filter mit jeweils einem eigenen Attributionsmodell:

* Frauenseite - Attribution - Wiederholung (Standard)
* Damenabteilung - Attribution - Instanz
* Damenabteilung - Attribution - Nicht wiederholende Instanz


In der folgenden Tabelle wird für jedes Attributionsmodell erläutert, welche eingehenden Ereignisse ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) für diese Bedingung qualifiziert sind.


| Damenseite - Attribution - <br/>*Attributionsmodell* | Ereignis 1:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 2:<br/>Seitenname ist gleich<br/>Männer | Ereignis 3:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 4:<br/>Seitenname ist gleich<br/>Frauen<br/>(Beständig) | Ereignis 5:<br/>Seitenname ist gleich<br/>Checkout | Ereignis 6:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 7:<br/>Seitenname ist gleich<br/>Home |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Wiederholung (Standard) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Nicht wiederholende Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |

Ein Beispielbericht zu Ereignissen, die die drei Filter verwenden, sieht wie folgt aus:

![Attributionsmodellergebnisse filtern](assets/filter-dimension-attribution-results.png)
