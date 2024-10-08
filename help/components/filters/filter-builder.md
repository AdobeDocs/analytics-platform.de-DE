---
description: Der Filter-Builder bietet eine Arbeitsfläche zum Ziehen und Ablegen von metrischen Dimensionen, Filtern und Ereignissen, um Personen basierend auf der Behälterhierarchielogik, den Regeln und Operatoren zu filtern. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit denen Personenattribute und Aktionen bei Besuchen und Ereignissen identifiziert werden.
title: Erstellen von Filtern
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 6%

---

# Erstellen von Filtern {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_createaudience"
>title="Erstellen einer Zielgruppe"
>abstract="Zielgruppen können mithilfe eines Filters erstellt und zur Aktivierung für Adobe Experience Platform freigegeben werden."

<!-- markdownlint-enable MD034 -->


Das Dialogfeld **[!UICONTROL Filter-Builder]** wird verwendet, um neue Filter zu erstellen oder vorhandene Filter zu bearbeiten. Das Dialogfeld trägt den Titel **[!UICONTROL Neuer Filter]** oder **[!UICONTROL Filter bearbeiten]** für Filter, die Sie aus dem [[!UICONTROL Filter]-Manager](/help/components/filters/manage-filters.md) erstellen oder verwalten.

>[!BEGINTABS]

>[!TAB Filter-Builder]

![Fenster &quot;Filterdetails&quot;mit den im nächsten Abschnitt beschriebenen Feldern und Optionen.](assets/filter-builder.png)

>[!TAB Filter erstellen oder bearbeiten]

![Fenster &quot;Filterdetails&quot;mit den im nächsten Abschnitt beschriebenen Feldern und Optionen.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) ist erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für den Filter auswählen.  Der von Ihnen definierte Filter ist als Filter auf der Registerkarte [Einstellungen](/help/data-views/create-dataview.md#settings-filters) einer Datenansicht verfügbar. |
   | **[!UICONTROL Nur-Projekt-Filter]** | Ein Informationsfeld, das erklärt, dass der Filter nur in dem Projekt sichtbar ist, in dem er erstellt wird, und dass der Filter nicht zu Ihrer Komponentenliste hinzugefügt wird. Aktivieren Sie **[!UICONTROL Stellen Sie diesen Filter für alle Ihre Projekte zur Verfügung und fügen Sie ihn Ihrer Komponentenliste hinzu]**, um diese Einstellung zu ändern. Dieses Informationsfeld ist nur sichtbar, wenn Sie einen [Schnellfilter](quick-filters.md) erstellen und die Schnellfilterinformationen mithilfe von **[!UICONTROL Builder öffnen]** aus der Benutzeroberfläche [!UICONTROL Schnellfilter] in einen regulären Filter umwandeln. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Benennen Sie den Filter, z. B. &quot;`Last month mobile customers`&quot;. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für den Filter ein, z. B. `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organisieren Sie den Filter, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um vorhandene Tags zu finden, die Sie auswählen können. Oder drücken Sie **[!UICONTROL EINGABETASTE]** , um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Definition]** ![Erforderlich](/help/assets/icons/Required.svg) | Definieren Sie Ihren Filter mit dem [Definition-Builder](#definition-builder). |

   {style="table-layout:auto"}

1. Um zu überprüfen, ob Ihre Filterdefinition korrekt ist, verwenden Sie die ständig aktualisierte Vorschau der Ergebnisse des Filters oben rechts.
1. Um eine Audience aus dem Filter zu erstellen und die Audience mit Experience Platform freizugeben, wählen Sie **[!UICONTROL Erstellen einer Audience aus Filter]** aus. Weitere Informationen finden Sie unter [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md) .
1. Wählen Sie:
   * **[!UICONTROL Speichern]** zum Speichern des Filters.
   * **[!UICONTROL Speichern unter]** , um eine Kopie des Filters zu speichern.
   * **[!UICONTROL Löschen]** , um den Filter zu löschen.
   * **[!UICONTROL Abbrechen]** , um alle Änderungen abzubrechen, die Sie am Filter vorgenommen haben, oder um die Erstellung eines neuen Filters abzubrechen.


## Definition-Builder

Sie verwenden den Definition-Builder, um Ihre Filterdefinition zu erstellen. In dieser Konstruktion verwenden Sie Komponenten, Container, Operatoren und Logik.

Sie können den Typ und den Umfang Ihrer Definition konfigurieren:

1. Um den Typ Ihrer Definition anzugeben, geben Sie an, ob der Build eine Ein- oder Ausschlussdefinition enthalten soll. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** und aus dem Dropdown-Umschalter **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]** aus.
1. Um den Umfang Ihrer Definition anzugeben, wählen Sie aus dem Dropdown-Menü **[!UICONTROL Einschließen]** oder **[!UICONTROL Ausschließen]** aus, ob der Umfang der Definition **[!UICONTROL Ereignis]**, **[!UICONTROL Sitzung]** oder **[!UICONTROL Person]** lauten soll.

Sie können diese Einstellungen jederzeit zu einem späteren Zeitpunkt ändern.

### Komponenten

Ein wichtiger Teil der Erstellung Ihrer Filterdefinition ist die Verwendung von Dimensionen, Metriken, vorhandenen Filtern und Datumsbereichen. Alle diese Komponenten sind im Komponentenbereich des Filter-Builders verfügbar.

![Erstellen einer Definition ](assets/start-building-filter.gif){width=100%}

So fügen Sie eine Komponente hinzu:

1. Ziehen Sie eine Komponente aus dem Komponentenbereich auf **[!UICONTROL Metrik(en), Filter(n) und/oder Dimensionen hierher ziehen und ablegen]**. Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.
1. Geben Sie Details für die Komponente an. Wählen Sie beispielsweise einen Wert aus &quot;**[!UICONTROL Wert auswählen]**&quot;. Oder geben Sie einen Wert ein. Was und wie Sie einen oder mehrere Werte angeben können, hängt von der Komponente und dem Operator ab.
1. Ändern Sie optional den Standardoperator. Beispielsweise entspricht **[!UICONTROL gleich]** bis **[!UICONTROL einem der]**. Eine detaillierte Übersicht der verfügbaren Operatoren finden Sie unter [Operatoren](operators.md) .

Bearbeiten einer Komponente:

* Wählen Sie im Dropdown-Menü für den Operator einen neuen Operator für die Komponente aus.
* Wählen Sie ggf. einen anderen Wert für den Operator aus oder geben Sie einen anderen an.
* Wenn der Komponententyp eine Dimension ist, können Sie das Attributionsmodell definieren. Weitere Informationen finden Sie unter [Attributionsmodell](#attribution-models) .

Löschen einer Komponente:

* Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) in einer Komponente aus.

### Container

Sie können mehrere Komponenten in einem oder mehreren Containern gruppieren und eine Logik innerhalb und zwischen Behältern definieren. Mit Containern können Sie komplexe Definitionen für Ihren Filter erstellen.

![Container hinzufügen](assets/add-container.gif){width=100%}

* Um einen Container hinzuzufügen, wählen Sie **[!UICONTROL Container hinzufügen]** aus ![Einstellung](/help/assets/icons/Setting.svg) **[!UICONTROL Optionen]** aus.
* Um eine vorhandene Komponente zum Container hinzuzufügen, ziehen Sie die Komponente in den Container.
* Um dem Container eine weitere Komponente hinzuzufügen, ziehen Sie eine Komponente aus dem Komponentenbereich in den Container. Verwenden Sie die blaue Einfügemarke als Anleitung.
* Um eine weitere Komponente außerhalb des Containers hinzuzufügen, ziehen Sie eine Komponente aus dem Komponentenbereich außerhalb des Containers, aber innerhalb des Hauptdefinitionsbehälters. Verwenden Sie die blaue Einfügezeile als Anleitung.
* Um die Logik zwischen Komponenten in einem Container, zwischen Behältern oder zwischen einem Container und einer Komponente zu ändern, wählen Sie die entsprechenden **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]** aus. Wenn Sie Dann auswählen, wandeln Sie den Filter in einen sequenziellen Filter um. Weitere Informationen finden Sie unter [Sequenziellen Filter erstellen](seg-sequential-build.md) .
* Um die Behälterebene zu wechseln, wählen Sie ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Event]**, ![Visit](/help/assets/icons/Visit.svg) **[!UICONTROL Session]** oder ![User](/help/assets/icons/User.svg) **[!UICONTROL Person]** aus.

Sie können ![Einstellung](/help/assets/icons/Setting.svg) in einem Container für die folgenden Aktionen verwenden:

| Container-Aktion | Beschreibung |
|---|---|
| **[!UICONTROL Container hinzufügen]** | Fügen Sie dem Container einen verschachtelten Container hinzu. |
| **[!UICONTROL Ausschließen]** | Schließen Sie das Ergebnis aus dem Container in der Filterdefinition aus. Ein dünner roter linker Balken identifiziert einen Container zum Ausschließen. |
| **[!UICONTROL Einschließlich]** | Schließen Sie das Ergebnis aus dem Container in die Filterdefinition ein. &quot;Einschließen&quot;ist die Standardeinstellung. Ein dünner grauer linker Balken identifiziert einen Include-Container. |
| **[!UICONTROL Name container]** | Benennen Sie den Container in der Standardbeschreibung um. Geben Sie einen Namen in das Textfeld ein. Wenn Sie keine Eingabe angeben, wird die Standardbeschreibung verwendet. |
| **[!UICONTROL Container löschen]** | Löschen Sie den Container aus der Definition. |


## Datumsbereiche

Sie können Filter erstellen, die rollierende Datumsbereiche enthalten. So können Sie Fragen zu laufenden Kampagnen oder Ereignissen beantworten. Sie können beispielsweise einen Filter erstellen, der *alle Personen enthält, die in den letzten 60 Tagen online eingekauft haben*.

![Filtern mit dem rollierenden Datumsbereich](assets/filter-rolling-date-range.gif)

+++ Im Folgenden finden Sie ein Video zur Verwendung rollierender Datumsbereiche in Filtern

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## Stapeln von Filtern {#stack}

Sie können Filter mithilfe von Filtern erstellen. Wenn Sie Filter in einem Filter verwenden, können Sie Ihren Filter optimieren und die Komplexität verringern.

Angenommen, Sie möchten nach der Kombination aus Gerätetyp (2) und US-Status (50) filtern. Sie können entweder 100 Filter erstellen, die jeweils für die eindeutige Kombination aus Gerätetyp (Mobiltelefon versus Tablet) und US-Status ausgelegt sind. Um die kalifornischen Tablet-Benutzer zu erhalten, würden Sie einen der 100 Filter verwenden:

![Einfacher Filter für CA und Tablet](assets/filter-ca-tablet-single.png)

Oder Sie können 52 Filter definieren: 50 Filter für die US-Bundesstaaten, eine für Mobiltelefone und eine für Tablets. Und stapeln Sie dann die Filter, um dieselben Ergebnisse zu erhalten. Um die kalifornischen Tablet-Benutzer zu erhalten, stapeln Sie zwei Filter:

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



Wenn Sie eine Dimension im Filter-Builder verwenden, haben Sie die Optionen, das Attributionsmodell für diese Dimension anzugeben. Das von Ihnen ausgewählte Attributionsmodell bestimmt, ob die Daten für die Bedingung qualifiziert sind, die Sie für die Dimensionskomponente angegeben haben.

Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) innerhalb der Dimensionskomponente und wählen Sie eines der Attributionsmodelle aus dem Popup-Fenster aus:

| Modelle | Beschreibung |
|---|---|
| **[!UICONTROL Wiederholungsmodell (Standard)]** | Schließen Sie Instanz und beibehaltene Werte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Instanz]** | Schließen Sie nur Instanzwerte für die Dimension ein, um die Qualifizierung zu bestimmen. |
| **[!UICONTROL Nicht wiederholende Instanz]** | Einbeziehen von eindeutigen Instanzwerten (nicht wiederholend) für die Dimension, um die Qualifizierung zu bestimmen. |


![Attributionsmodell für Dimension beim Erstellen eines Filters](assets/filter-dimension-attribution.png)

### Beispiel

Im Rahmen einer Filterdefinition haben Sie die folgende Bedingung angegeben: Seitenname ist Frauen. Ähnlich wie im obigen Beispiel. Sie wiederholen diese Filterdefinition anhand der beiden anderen Attributionsmodelle. Sie haben also drei Filter mit jeweils einem eigenen Attributionsmodell:

* Frauen-Seite - Attribution - Wiederholend (Standard)
* Frauen-Seite - Attribution - Instanz
* Frauen-Seite - Attribution - Nicht wiederholende Instanz


In der folgenden Tabelle wird für jedes Attributionsmodell erläutert, welche eingehenden Ereignisse für diese Bedingung ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) qualifiziert sind.


| Frauen-Seite - Attribution - <br/>*Attributionsmodell* | Ereignis 1:<br/>Seitenname gleich<br/>Women | Ereignis 2:<br/>Seitenname gleich<br/>Männer | Ereignis 3:<br/>Seitenname gleich<br/>Women | Ereignis 4:<br/>Seitenname ist gleich<br/>Women<br/> (persistent) | Ereignis 5:<br/>Seitenname gleich<br/>Checkout | Ereignis 6:<br/>Seitenname gleich<br/>Women | Ereignis 7:<br/>Seitenname gleich<br/>Home |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Wiederholen (Standard) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |
| Nicht wiederholende Instanz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![Entfernen](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Entfernen](/help/assets/icons/Remove.svg) |

Ein Beispielbericht zu Ereignissen mit den drei Filtern sieht wie folgt aus:

![Ergebnisse des Attributionsmodells filtern](assets/filter-dimension-attribution-results.png)
