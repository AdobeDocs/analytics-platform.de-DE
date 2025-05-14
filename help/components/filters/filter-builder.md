---
description: Segment Builder bietet eine Arbeitsfläche, auf der Metrikdimensionen, Segmente und Ereignisse basierend auf Container-Hierarchielogik, Regeln und Operatoren per Drag-and-Drop an Personen segmentiert werden können. Mit diesem integrierten Entwicklungs-Tool können Sie einfache oder komplexe Segmente erstellen und speichern, die Personenattribute und Aktionen über Besuche und Ereignisse hinweg identifizieren.
title: Segmente erstellen
feature: Filters, Segments
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1572'
ht-degree: 49%

---

# Segmente erstellen {#build-segments}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Erstellen einer Zielgruppe"
>abstract="Zielgruppen können aus einem Segment erstellt und für die Adobe Experience Platform freigegeben werden, damit sie aktiviert werden können."

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Datenvorschau"
>abstract="Vergleicht die Daten dieses Segments mit den Daten der Datenansicht. Der Prozentsatz der Vorschau basiert auf der Gesamtzahl der Daten in der Datenansicht aus den **letzten 90 Tagen**.<br><br/>Wenn die Vorschau nicht geladen wird, wird Ihre Verbindung möglicherweise noch aufgestockt."


Das Dialogfeld **[!UICONTROL Segment Builder]** wird verwendet, um neue Segmente zu erstellen oder vorhandene Segmente zu bearbeiten. Das Dialogfeld heißt **[!UICONTROL Neues Segment]** oder **[!UICONTROL Segment bearbeiten]** für Segmente, die Sie über den [[!UICONTROL Segment]Manager erstellen oder verwalten](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Segment Builder]

![Fenster „Segmentdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/filter-builder.png)

>[!TAB Segment erstellen oder bearbeiten]

![Fenster „Segmentdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) bedeutet erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für das Segment auswählen.  Das von Ihnen definierte Segment ist als Segment in der Registerkarte [Einstellungen](/help/data-views/create-dataview.md#settings-filters) einer Datenansicht verfügbar. |
   | **[!UICONTROL Segment nur für Projekte]** | Ein Informationsfeld, in dem erläutert wird, dass das Segment nur in dem Projekt sichtbar ist, in dem es erstellt wurde, und nicht zur Komponentenliste hinzugefügt wird. Aktivieren Sie **[!UICONTROL Dieses Segment für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]** um diese Einstellung zu ändern. Dieses Infofeld wird nur angezeigt, wenn Sie ein [Schnellsegment](quick-filters.md) erstellen und das Schnellsegment mithilfe von **[!UICONTROL Open Builder]** in der [!UICONTROL Schnellsegment]-Oberfläche in ein reguläres Segment umwandeln. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Benennen Sie das Segment, z. B. `Last month mobile customers`. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für das Segment an, z. B. `Segment to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organisieren Sie das Segment, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um nach vorhandenen Tags zu suchen, die Sie auswählen können. Oder drücken Sie die **[!UICONTROL Eingabetaste]**, um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Definition]** ![Required](/help/assets/icons/Required.svg) | Definieren Sie Ihr Segment mit dem [Definition Builder](#definition-builder). |

   {style="table-layout:auto"}

1. Um sicherzustellen, dass Ihre Segmentdefinition korrekt ist, verwenden Sie die ständig aktualisierte Vorschau der Ergebnisse des Segments oben rechts.
1. Um eine Zielgruppe aus dem Segment zu erstellen und die Zielgruppe für Experience Platform freizugeben, wählen Sie **[!UICONTROL Zielgruppe aus Segment erstellen]** aus. Weitere Informationen finden Sie unter [ Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md).
1. Wählen Sie Folgendes aus:
   * **[!UICONTROL Speichern]**, um das Segment zu speichern.
   * **[!UICONTROL Speichern unter]**, um eine Kopie des Segments zu speichern.
   * **[!UICONTROL Löschen]**, um das Segment zu löschen.
   * **[!UICONTROL Abbrechen]**, um alle an dem Segment vorgenommenen Änderungen rückgängig zu machen oder die Erstellung eines neuen Segments abzubrechen.


## Definition Builder

Mit dem Definition Builder erstellen Sie eine Segmentdefinition. Dabei verwenden Sie Komponenten, Container, Operatoren und Logik.

Sie können den Typ und den Umfang Ihrer Definition konfigurieren:

1. Um den Typ Ihrer Definition anzugeben, geben Sie an, ob Sie eine Ein- oder Ausschlussdefinition erstellen möchten. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** und aus dem Dropdown-Menü **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]**.
1. Um den Umfang Ihrer Definition anzugeben, wählen Sie aus dem Dropdown-Menü **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]** aus, ob Sie den Umfang der Definition **[!UICONTROL Ereignis]**, **[!UICONTROL Sitzung]**, **[!UICONTROL Person]**, **[!UICONTROL Globales Konto]** [!BADGE B2B editionB2B edition B2B edition ]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} oder **** ]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Einkaufsgruppe]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}224}B2B edition **** ]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} **** möchten[!BADGE [!BADGE [!BADGE 

Sie können diese Einstellungen später jederzeit ändern.

### Komponenten

Ein wichtiger Teil beim Erstellen Ihrer Segmentdefinition ist die Verwendung von Dimensionen, Metriken, vorhandenen Segmenten und Datumsbereichen. Alle diese Komponenten sind über das Bedienfeld „Komponenten“ in Segment Builder verfügbar.

![Mit dem Erstellen einer Definition beginnen](assets/start-building-filter.gif){width=100%}

So fügen Sie eine Komponente hinzu:

1. Ziehen Sie eine Komponente aus dem Bedienfeld „Komponenten“ per Drag **[!UICONTROL and-Drop auf „Metrik(en), Segment(e) und/oder Dimensionen hierher ziehen und ablegen]**. Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.
1. Geben Sie Details für die Komponente an. Wählen Sie beispielsweise einen Wert über **[!UICONTROL Wert auswählen]** aus. Oder geben Sie einen Wert ein. Wie Sie einen oder mehrere Werte und welche Werte Sie angeben können, hängt von der Komponente und dem Operator ab.
1. Ändern Sie optional den Standardoperator. Beispiel: von **[!UICONTROL ist gleich]** zu **[!UICONTROL ist gleich eines von]**. Unter [Operatoren](operators.md) finden Sie einen detaillierten Überblick über die verfügbaren Operatoren.

So bearbeiten Sie eine Komponente:

* Wählen Sie im Dropdown-Menü Operator einen neuen Operator für die Komponente aus.
* Wählen Sie ggf. einen anderen Wert für den Operator aus oder geben Sie ihn an.
* Wenn der Komponententyp eine Dimension ist, können Sie das Attributionsmodell definieren. Weitere Informationen finden Sie unter [Attributionsmodell](#attribution-models).

So löschen Sie eine Komponente:

* Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) in einer Komponente aus.

### Container

Sie können mehrere Komponenten in einem oder mehreren Containern gruppieren und Logik innerhalb und zwischen Containern definieren. Mit Containern können Sie komplexe Definitionen für Ihr Segment erstellen.

![Container hinzufügen](assets/add-container.gif){Width=100%}

* Wählen Sie zum Hinzufügen eines Containers über ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** die Option **[!UICONTROL Behälter hinzufügen]** aus.
* Um eine vorhandene Komponente zum Container hinzuzufügen, ziehen Sie die Komponente per Drag-and-Drop in den Container.
* Um dem Container eine weitere Komponente hinzuzufügen, ziehen Sie eine Komponente per Drag-and-Drop aus dem Panel „Komponente“ in den Container. Verwenden Sie die blaue Linie zum Einfügen als Orientierung.
* Um eine weitere Komponente außerhalb des Containers hinzuzufügen, ziehen Sie eine Komponente per Drag-and-Drop aus dem Panel „Komponente“ außerhalb des Containers, aber innerhalb des Containers für die Hauptdefinition. Verwenden Sie die blaue Linie zum Einfügen als Orientierung.
* Um die Logik zwischen Komponenten in einem Container, zwischen Containern oder zwischen einem Container und einer Komponente zu ändern, wählen Sie die entsprechende Option **[!UICONTROL Und]**, **[!UICONTROL Oder]**, **[!UICONTROL Dann]**. Wenn Sie Dann auswählen, wandeln Sie das Segment in ein sequenzielles Segment um. Weitere Informationen [ Sie unter &quot;](seg-sequential-build.md) Segment erstellen“.
* Um die Container-Ebene zu wechseln, wählen Sie ![Globus](/help/assets/icons/Globe.svg) **[!UICONTROL Globales Konto]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Konto](/help/assets/icons/Account.svg) **[!UICONTROL Konto]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Opportunity](/help/assets/icons/Opportunity.svg) **[!UICONTROL Opportunity]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Käufergruppe](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Käufergruppe]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Web-Seite](/help/assets/icons/WebPage.svg) **[!UICONTROL Ereignis]**, ![Besuch](/help/assets/icons/Visit.svg) **[!UICONTROL Sitzung]** oder ![Benutzer](/help/assets/icons/User.svg) **[!UICONTROL Person]** aus.

Sie können ![Einstellung](/help/assets/icons/Setting.svg) in einem Container für die folgenden Aktionen verwenden:

| Container-Aktion | Beschreibung |
|---|---|
| **[!UICONTROL Behälter hinzufügen]** | Fügen Sie dem Container einen verschachtelten Container hinzu. |
| **[!UICONTROL Ausschließen]** | Schließen Sie das Ergebnis aus dem Container in der Segmentdefinition aus. Ein dünner roter Balken auf der linken Seite kennzeichnet einen Container „Ausschließen.“ |
| **[!UICONTROL Einschließlich]** | Fügen Sie das Ergebnis aus dem Container in die Segmentdefinition ein. Die Standardeinstellung lautet „Einbeziehen“. Ein dünner grauer Balken auf der linken Seite kennzeichnet einen Container „Einbeziehen“. |
| **[!UICONTROL Container benennen]** | Benennen Sie den Container ausgehend von seiner Standardbeschreibung um. Geben Sie einen Namen in das Textfeld ein. Wenn Sie keine Eingabe vornehmen, wird die Standardbeschreibung verwendet. |
| **[!UICONTROL Container löschen]** | Löschen Sie den Container aus der Definition. |


## Datumsbereiche

Sie können Segmente erstellen, die rollierende Datumsbereiche enthalten. Auf diese Weise können Sie Fragen zu laufenden Kampagnen oder Ereignissen beantworten. Sie können beispielsweise ein Segment erstellen, das Folgendes enthält *alle, die in den letzten 60 Tagen einen Online-Kauf getätigt haben*.

![Segment mit rollierendem Datumsbereich](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rollierende Datumsbereiche in Segmenten](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


## Stapelung von Segmenten {#stack}

Sie können ein Segment mithilfe von Segmenten erstellen. Wenn Sie Segmente in einem Segment verwenden, können Sie Ihr Segment optimieren und die Komplexität reduzieren.

Angenommen, Sie möchten eine Segmentierung anhand der Kombination aus Gerätetyp (2) und US-Status (50) vornehmen. Sie können entweder 100 Segmente erstellen, jedes für die eindeutige Kombination aus Gerätetyp (Mobiltelefon versus Tablet) und US-Bundesstaat. Um die Tablet-Benutzer in Kalifornien zu erhalten, verwenden Sie eines der 100 Segmente:

![Einfaches Segment für Kalifornien und Tablet](assets/filter-ca-tablet-single.png)

Oder Sie könnten 52 Segmente definieren: 50 Segmente für die US-Bundesstaaten, eines für Mobiltelefone und eines für Tablet-Computer. Stapeln Sie dann die Segmente, um die gleichen Ergebnisse zu erhalten. Um die kalifornischen Tablet-Benutzer zu erhalten, stapeln Sie zwei Segmente:

![Gestapeltes Segment für CA und Tablet](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Wiederholend"
>abstract="Umfasst Instanzen und persistierte Werte für die Dimension."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instanz"
>abstract="Umfasst Instanzen und persistierte Werte für die Dimension."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Sich nicht wiederholende Instanz"
>abstract="Umfasst einzigartige (sich nicht wiederholende) Instanzen für die Dimension."




Wenn Sie eine Dimension in Segment Builder verwenden, haben Sie die Möglichkeit, das Attributionsmodell für diese Dimension anzugeben. Das von Ihnen ausgewählte Attributionsmodell bestimmt, ob Daten für die Bedingung qualifiziert sind, die Sie für die Dimensionskomponente angegeben haben.

Wählen Sie in der Dimensionskomponente das Symbol ![Setting](/help/assets/icons/Setting.svg) und dann eines der Attributionsmodelle aus dem Popup aus:

| Modelle | Beschreibung |
|---|---|
| **[!UICONTROL Sich wiederholendes Modell (Standard)]** | Schließen Sie die Instanz und persistierten Werte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Instanz]** | Schließen Sie nur Instanzwerte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Sich nicht wiederholende Instanz]** | Schließen Sie eindeutige (sich nicht wiederholende) Instanzwerte für die Dimension ein, um die Qualifizierung zu bestimmen. |


![Attributionsmodell auf Dimension beim Erstellen eines Segments](assets/filter-dimension-attribution.png)

### Beispiel

Als Teil einer Segmentdefinition haben Sie die folgende Bedingung angegeben: Seitenname ist gleich Frauen. Ähnlich wie im obigen Beispiel. Sie wiederholen diese Segmentdefinition mithilfe der beiden anderen Attributionsmodelle. Sie haben also drei Segmente mit jeweils einem eigenen Attributionsmodell:

* „Frauen“-Seite – Attribution – Wiederholung (Standard)
* „Frauen“-Seite – Attribution – Instanz
* „Frauen“-Seite – Attribution – Sich nicht wiederholende Instanz


In der folgenden Tabelle wird für jedes Attributionsmodell angegeben, welche eingehenden Ereignisse für diese Bedingung qualifiziert ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) sind.


| „Frauen“-Seite – Attribution – <br/>*Attributionsmodell* | Ereignis 1:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 2:<br/>Seitenname ist gleich<br/>Männer | Ereignis 3:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 4:<br/>Seitenname ist gleich<br/>Frauen<br/>(persistiert) | Ereignis 5:<br/>Seitenname ist gleich<br/>Checkout | Ereignis 6:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 7:<br/>Seitenname ist gleich<br/>Startseite |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Wiederholung (Standard) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Sich nicht wiederholende Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |

Ein Beispielbericht zu Ereignissen, die die drei Segmente verwenden, sieht wie folgt aus:

![Ergebnisse des Segmentzuordnungsmodells](assets/filter-dimension-attribution-results.png)

<!-- markdownlint-enable MD034 -->