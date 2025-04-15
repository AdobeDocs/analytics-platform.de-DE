---
description: Der Filtergenerator bietet eine Arbeitsfläche zum Drag-and-Drop von Metrikdimensionen, Filtern und Ereignissen, um Besuchende anhand von Container-Hierarchielogik, Regeln und Operatoren zu filtern. Mit diesem integrierten Entwicklungs-Tool können Sie einfache oder komplexe Filter erstellen und speichern, mit deren Hilfe Pesronenattribute und Aktionen bei Besuchen und Ereignissen identifiziert werden.
title: Erstellen von Filtern
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 91%

---

# Erstellen von Filtern {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Erstellen einer Zielgruppe"
>abstract="Zielgruppen können mithilfe eines Filters erstellt und zur Aktivierung für Adobe Experience Platform freigegeben werden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Datenvorschau"
>abstract="Vergleicht die Daten dieses Filters mit den Daten der Datenansicht. Der Prozentsatz der Vorschau basiert auf der Gesamtzahl der Daten in der Datenansicht aus den **letzten 90 Tagen**.<br><br/>Wenn die Vorschau nicht geladen wird, wird Ihre Verbindung möglicherweise noch aufgestockt."

<!-- markdownlint-enable MD034 -->



Das Dialogfeld **[!UICONTROL Generator filtern]** wird zum Erstellen neuer oder Bearbeiten vorhandener Filter verwendet. Das Dialogfeld heißt **[!UICONTROL Neuer Filter]** oder **[!UICONTROL Filter bearbeiten]** bei Filtern, die Sie über den [[!UICONTROL Filter]-Manager](/help/components/filters/manage-filters.md) erstellen oder verwalten.

>[!BEGINTABS]

>[!TAB Filtergenerator]

![Fenster Filterdetails mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/filter-builder.png)

>[!TAB Erstellen oder Bearbeiten von Filtern]

![Fenster Filterdetails mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) bedeutet erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für den Filter auswählen.  Der von Ihnen definierte Filter ist als Filter auf der Registerkarte [Einstellungen](/help/data-views/create-dataview.md#settings-filters) einer Datenansicht verfügbar. |
   | **[!UICONTROL Filter nur für das Projekt]** | Ein Informationsfeld, mit dem erklärt wird, dass der Filter nur in dem Projekt sichtbar ist, in dem er erstellt wurde, und dass der Filter nicht zu Ihrer Komponentenliste hinzugefügt wird. Aktivieren Sie **[!UICONTROL Diesen Filter für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]**, um diese Einstellung zu ändern. Dieses Infofeld wird nur angezeigt, wenn Sie einen [Schnellfilter](quick-filters.md) erstellen und diesen mithilfe von **[!UICONTROL Builder öffnen]** in der Oberfläche [!UICONTROL Schnellfilter] in einen regulären Filter umwandeln. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Benennen Sie den Filter, beispielsweise mit `Last month mobile customers`. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für den Filter ein, z. B. `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organisieren Sie den Filter, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um nach vorhandenen Tags zu suchen, die Sie auswählen können. Oder drücken Sie die **[!UICONTROL Eingabetaste]**, um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Definition]** ![Required](/help/assets/icons/Required.svg) | Definieren Sie Ihren Filter mit dem [Definition Builder](#definition-builder). |

   {style="table-layout:auto"}

1. Um zu überprüfen, ob Ihre Filterdefinition korrekt ist, verwenden Sie die ständig aktualisierte Vorschau der Ergebnisse des Filters oben rechts.
1. Um eine Zielgruppe aus dem Filter zu erstellen und die Zielgruppe für Experience Platform freizugeben, wählen Sie **[!UICONTROL Zielgruppe aus Filter erstellen]** aus. Weitere Informationen finden Sie unter [ Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md).
1. Wählen Sie Folgendes aus:
   * **[!UICONTROL Speichern]**: Speichert den Filter.
   * **[!UICONTROL Speichern unter]**: Speichert eine Kopie des Filters.
   * **[!UICONTROL Löschen]**: Löscht den Filter.
   * **[!UICONTROL Abbrechen]**: Verwirft alle Änderungen, die Sie an einem Filter vorgenommen haben, oder bricht die Erstellung eines neuen Filters ab.


## Definition Builder

Mit dem Definition Builder erstellen Sie Ihre Filterdefinition. Dabei verwenden Sie Komponenten, Container, Operatoren und Logik.

Sie können den Typ und den Umfang Ihrer Definition konfigurieren:

1. Um den Typ Ihrer Definition anzugeben, geben Sie an, ob Sie eine Ein- oder Ausschlussdefinition erstellen möchten. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** und über den Dropdown-Umschalter **[!UICONTROL Einbeziehen]** oder **[!UICONTROL Ausschließen]**.
1. Um den Umfang Ihrer Definition anzugeben, wählen Sie aus dem Dropdown-Menü **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]** aus, ob Sie den Umfang der Definition **[!UICONTROL Ereignis]**, **[!UICONTROL Sitzung]**, **[!UICONTROL Person]**, **[!UICONTROL Globales Konto]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Konto]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} oder **[!UICONTROL EinkaufsgruppeB2B edition [!BADGE ]** 24}]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} möchten

Sie können diese Einstellungen später jederzeit ändern.

### Komponenten

Ein wichtiger Teil beim Erstellen Ihrer Filterdefinition ist die Verwendung von Dimensionen, Metriken, vorhandenen Filtern und Datumsbereichen. Alle diese Komponenten sind über das Panel „Komponenten“ im Filteraufbau verfügbar.

![Erstellen einer Definition](assets/start-building-filter.gif){width=100%}

So fügen Sie eine Komponente hinzu:

1. Ziehen Sie eine Komponente aus dem Panel „Komponenten“ auf **[!UICONTROL Metrik(en), Filter und/oder Dimensionen per Drag-and-Drop hierher ziehen]**. Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.
1. Geben Sie Details für die Komponente an. Wählen Sie beispielsweise einen Wert über **[!UICONTROL Wert auswählen]** aus. Oder geben Sie einen Wert ein. Wie Sie einen oder mehrere Werte und welche Werte Sie angeben können, hängt von der Komponente und dem Operator ab.
1. Ändern Sie optional den Standardoperator. Beispiel: von **[!UICONTROL ist gleich]** zu **[!UICONTROL ist gleich eines von]**. Unter [Operatoren](operators.md) finden Sie einen detaillierten Überblick über die verfügbaren Operatoren.

So bearbeiten Sie eine Komponente:

* Wählen Sie im Dropdown-Menü „Operator“ einen neuen Operator für die Komponente aus.
* Wählen Sie ggf. einen anderen Wert für den Operator aus oder geben Sie ihn an.
* Wenn der Komponententyp eine Dimension ist, können Sie das Attributionsmodell definieren. Weitere Informationen finden Sie unter [Attributionsmodell](#attribution-models).

So löschen Sie eine Komponente:

* Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) in einer Komponente aus.

### Container

Sie können mehrere Komponenten in einem oder mehreren Containern gruppieren und Logik innerhalb und zwischen Containern definieren. Mit Containern können Sie komplexe Definitionen für Ihren Filter erstellen.

![Container hinzufügen](assets/add-container.gif){Width=100%}

* Wählen Sie zum Hinzufügen eines Containers über ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** die Option **[!UICONTROL Behälter hinzufügen]** aus.
* Um eine vorhandene Komponente zum Container hinzuzufügen, ziehen Sie die Komponente per Drag-and-Drop in den Container.
* Um dem Container eine weitere Komponente hinzuzufügen, ziehen Sie eine Komponente per Drag-and-Drop aus dem Panel „Komponente“ in den Container. Verwenden Sie die blaue Linie zum Einfügen als Orientierung.
* Um eine weitere Komponente außerhalb des Containers hinzuzufügen, ziehen Sie eine Komponente per Drag-and-Drop aus dem Panel „Komponente“ außerhalb des Containers, aber innerhalb des Containers für die Hauptdefinition. Verwenden Sie die blaue Linie zum Einfügen als Orientierung.
* Um die Logik zwischen Komponenten in einem Container, zwischen Containern oder zwischen einem Container und einer Komponente zu ändern, wählen Sie die entsprechende Option **[!UICONTROL Und]**, **[!UICONTROL Oder]**, **[!UICONTROL Dann]**. Wenn Sie „Dann“ auswählen, wandeln Sie den Filter in einen sequenziellen Filter um. Weitere Informationen finden Sie unter [Erstellen eines sequenziellen Filters](seg-sequential-build.md).
* Um die Container-Ebene zu wechseln, wählen Sie ![Globales ](/help/assets/icons/Globe.svg) **[!UICONTROL Globales Konto]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Konto](/help/assets/icons/Account.svg)**[!UICONTROL Konto]** [!BADGE B2B editionB2B edition B2B edition ]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Opportunity **(/help/assets/icons/Opportunity.svg)](/help/assets/icons/BuyingGroup.svg),]**]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}KaufGruppen![**[!UICONTROL Gruppen]** ]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} ![ ](/help/assets/icons/WebPage.svg) **** ![ ](/help/assets/icons/Visit.svg) **** ![ ](/help/assets/icons/User.svg) ****,[!BADGE [!BADGE 

Sie können ![Einstellung](/help/assets/icons/Setting.svg) in einem Container für die folgenden Aktionen verwenden:

| Container-Aktion | Beschreibung |
|---|---|
| **[!UICONTROL Behälter hinzufügen]** | Fügen Sie dem Container einen verschachtelten Container hinzu. |
| **[!UICONTROL Ausschließen]** | Schließen Sie das Ergebnis aus dem Container in der Filterdefinition aus. Ein dünner roter Balken auf der linken Seite kennzeichnet einen Container „Ausschließen.“ |
| **[!UICONTROL Einschließlich]** | Beziehen Sie das Ergebnis aus dem Container in die Filterdefinition ein. Die Standardeinstellung lautet „Einbeziehen“. Ein dünner grauer Balken auf der linken Seite kennzeichnet einen Container „Einbeziehen“. |
| **[!UICONTROL Container benennen]** | Benennen Sie den Container ausgehend von seiner Standardbeschreibung um. Geben Sie einen Namen in das Textfeld ein. Wenn Sie keine Eingabe vornehmen, wird die Standardbeschreibung verwendet. |
| **[!UICONTROL Container löschen]** | Löschen Sie den Container aus der Definition. |


## Datumsbereiche

Sie können Filter erstellen, die rollierende Datumsbereiche enthalten. Sie können also Fragen zu laufenden Kampagnen oder Ereignissen beantworten. Sie können beispielsweise einen Filter erstellen, der *alle, die in den vergangenen 60 Tagen Online-Käufe getätigt haben*, beinhaltet.

![Filter mit rollierendem Datumsbereich](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rollierende Datumsbereiche in Segmenten](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


## Stapeln von Filtern {#stack}

Sie können einen Filter mithilfe von Filtern erstellen. Wenn Sie Filter in einem Filter verwenden, können Sie Ihren Filter optimieren und die Komplexität reduzieren.

Angenommen, Sie möchten nach Gerätetyp (2) und US-Bundesstaaten (50) filtern. Die erste Möglichkeit: Sie erstellen 100 Filter, d. h. jeweils eine eindeutige Kombination aus Gerätetyp (Mobiltelefon oder Tablet) und US-Bundesstaat. Um die kalifornischen Tablet-Benutzenden abzurufen, würden Sie dann einen der 100 Filter verwenden:

![Einfacher Filter für Kalifornien und den Gerätetyp „Tablet“](assets/filter-ca-tablet-single.png)

Die zweite Möglichkeit: Sie definieren 52 Filter, d. h. 50 Filter für die US-Bundesstaaten sowie jeweils einen für den Gerätetyp „Mobiltelefon“ und „Tablet“. Stapeln Sie dann die Filter, um die gleichen Ergebnisse zu erhalten. Um die kalifornischen Tablet-Benutzenden abzurufen, würden Sie zwei Filter stapeln:

![Gestapelter Filter für Kalifornien und den Gerätetyp „Tablet“](assets/filter-ca-tablet-stacked.png)


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Wiederholend"
>abstract="Umfasst Instanzen und persistierte Werte für die Dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instanz"
>abstract="Umfasst Instanzen und persistierte Werte für die Dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Sich nicht wiederholende Instanz"
>abstract="Umfasst einzigartige (sich nicht wiederholende) Instanzen für die Dimension."

<!-- markdownlint-enable MD034 -->



Wenn Sie eine Dimension im Filtergenerator verwenden, können Sie das Attributionsmodell für diese Dimension angeben. Das von Ihnen ausgewählte Attributionsmodell bestimmt, ob Daten für die Bedingung qualifiziert sind, die Sie für die Dimensionskomponente angegeben haben.

Wählen Sie in der Dimensionskomponente das Symbol ![Setting](/help/assets/icons/Setting.svg) und dann eines der Attributionsmodelle aus dem Popup aus:

| Modelle | Beschreibung |
|---|---|
| **[!UICONTROL Sich wiederholendes Modell (Standard)]** | Schließen Sie die Instanz und persistierten Werte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Instanz]** | Schließen Sie nur Instanzwerte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Sich nicht wiederholende Instanz]** | Schließen Sie eindeutige (sich nicht wiederholende) Instanzwerte für die Dimension ein, um die Qualifizierung zu bestimmen. |


![Attributionsmodell für Dimension beim Erstellen eines Filters](assets/filter-dimension-attribution.png)

### Beispiel

Als Teil einer Filterdefinition haben Sie die folgende Bedingung angegeben: Seitenname ist gleich Frauen. Dies ist ähnlich wie im obigen Beispiel. Sie wiederholen diese Filterdefinition mit den beiden anderen Attributionsmodellen. Sie haben also drei Filter mit jeweils einem eigenen Attributionsmodell:

* „Frauen“-Seite – Attribution – Wiederholung (Standard)
* „Frauen“-Seite – Attribution – Instanz
* „Frauen“-Seite – Attribution – Sich nicht wiederholende Instanz


In der folgenden Tabelle wird für jedes Attributionsmodell angegeben, welche eingehenden Ereignisse für diese Bedingung qualifiziert ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) sind.


| „Frauen“-Seite – Attribution – <br/>*Attributionsmodell* | Ereignis 1:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 2:<br/>Seitenname ist gleich<br/>Männer | Ereignis 3:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 4:<br/>Seitenname ist gleich<br/>Frauen<br/>(persistiert) | Ereignis 5:<br/>Seitenname ist gleich<br/>Checkout | Ereignis 6:<br/>Seitenname ist gleich<br/>Frauen | Ereignis 7:<br/>Seitenname ist gleich<br/>Startseite |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Wiederholung (Standard) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Sich nicht wiederholende Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |

Ein Beispielbericht zu Ereignissen, die die drei Filter verwenden, sieht wie folgt aus:

![Filtern der Ergebnisse für ein Attributionsmodell](assets/filter-dimension-attribution-results.png)
