---
description: Der Generator für berechnete Metriken bietet eine Arbeitsfläche, in der Sie Dimensionen, Metriken, Filter und Funktionen per Drag-and-Drop verschieben können, um benutzerdefinierte Metriken basierend auf Container-Hierarchielogik, Regeln und Operatoren zu erstellen. Mit diesem integrierten Entwicklungstool können Sie einfache berechnete Metriken oder komplexe, erweiterte berechnete Metriken erstellen und speichern.
title: Bilden berechneter Metriken
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 11%

---

# Bilden berechneter Metriken {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Produktkompatibilität"
>abstract="Gibt an, wo in Customer Journey Analytics diese berechnete Metrik verwendet werden kann, z. B. in Analysis Workspace und Report Builder. Einige berechnete Metriken können nicht mit Experimenten verwendet werden."
>additional-url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Verwenden von berechneten Metriken in Experimenten"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="Externe ID"
>abstract="Eine Änderung der externen ID kann sich auf die Darstellung der berechneten Metrik in externen Quellen auswirken, z. B. auf Business Intelligence-Tools"

<!-- markdownlint-enable MD034 -->


Das Dialogfeld **[!UICONTROL Generator für berechnete]**&quot; wird verwendet, um neue berechnete Metriken zu erstellen oder vorhandene zu bearbeiten. Das Dialogfeld heißt **[!UICONTROL Neue berechnete Metrik]** oder **[!UICONTROL Berechnete Metrik bearbeiten]** für Metriken, die Sie über den Manager [[!UICONTROL Berechnete Metriken] erstellen oder verwalten](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Generator für berechnete Metriken]

![Fenster mit Details zur berechneten Metrik mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/calculated-metric-builder.png)

>[!TAB Berechnete Metrik erstellen oder bearbeiten]

![Fenster mit Details zur berechneten Metrik mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) bedeutet erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für die berechnete Metrik auswählen.  Die von Ihnen definierte berechnete Metrik ist in Workspace-Projekten verfügbar, die auf der ausgewählten Datenansicht basieren. |
   | **[!UICONTROL Metrik „Nur Projekt“]** | Ein Infofeld, in dem erläutert wird, dass die Metrik nur in dem Projekt sichtbar ist, in dem sie erstellt wurde, und dass sie nicht zur Komponentenliste hinzugefügt wird. Aktivieren Sie **[!UICONTROL Diese Metrik für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]** um diese Einstellung zu ändern. Dieses Infofeld wird nur angezeigt, wenn Sie eine Metrik in Workspace mit **[!UICONTROL Metrik aus Auswahl erstellen]** erstellen und eine Funktion (z. B. **[!UICONTROL Mittelwert]** oder **[!UICONTROL Median]**) ausgewählt haben. Verwenden Sie später die [Komponenteninformationen](/help/components/use-components-in-workspace.md#component-info) um diese erstellte Metrik zu bearbeiten. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Benennen Sie die berechnete Metrik, z. B. `Conversion Rate`. |
   | **[!UICONTROL Externe ID]** ![erforderlich](/help/assets/icons/Required.svg) | Der Name der berechneten Metrik bei Verwendung eines externen BI-Tools und der BI-Erweiterung. Der Wert wird automatisch als `undefined_xxx` definiert, es sei denn, Sie überschreiben den Wert. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für den Filter an, z. B. `Calculated metric to define the conversion rate.` Es ist nicht erforderlich, die Formel für die berechnete Metrik zu beschreiben, da die Formel bereits automatisch in [!UICONTROL Zusammenfassung“ ]. |
   | **[!UICONTROL Format]** | Wählen Sie ein Format für die berechnete Metrik aus: Sie können zwischen **[!UICONTROL Dezimal]**, **[!UICONTROL Zeit]**, **[!UICONTROL Prozent]** und **[!UICONTROL Währung]**. |
   | **[!UICONTROL Dezimalstellen]** | Geben Sie die Anzahl der Dezimalstellen für das ausgewählte Format an. Nur aktiviert, wenn das ausgewählte Format „Dezimal“, „Währung“ und „Prozent“ ist. |
   | **[!UICONTROL Aufwärts-Trend anzeigen als]** | Geben Sie an, ob ein Aufwärtstrend der berechneten Metrik als ▲ **[!UICONTROL Gut (Grün)]** oder als ▼ (**[!UICONTROL )]**. |
   | **[!UICONTROL Währung]** | Geben Sie die Währung der berechneten Metrik an. Nur aktiviert, wenn Format ausgewählt ist Währung. |
   | **[!UICONTROL Tags]** | Organisieren Sie die berechnete Metrik, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um nach vorhandenen Tags zu suchen, die Sie auswählen können. Oder drücken Sie **[!UICONTROL EINGABETASTE]**, um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Vorschau]** | Die Vorschau umfasst die letzten 90 Tage und ist eine Möglichkeit, abzuschätzen, ob Sie Ihre Metrik richtig definiert haben. |
   | **[!UICONTROL Zusammenfassung]** | Zeigt eine Zusammenfassung der Definition der berechneten Metrik an. <br/>Beispiel: ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen insgesamt]** ![Trennen](/help/assets/icons/Divide.svg)![ Ereignis](/help/assets/icons/Event.svg)**[!UICONTROL Sitzungen]**. |
   | **[!UICONTROL Definition]** ![erforderlich](/help/assets/icons/Required.svg) | Definieren Sie Ihren Filter mit dem [Definition Builder](#definition-builder). |

1. Um zu überprüfen, ob Ihre Definition der berechneten Metrik korrekt ist, verwenden Sie die ständig aktualisierte **[!UICONTROL Vorschau]** der Ergebnisse der berechneten Metrik. Der **[!UICONTROL Vorschau]** deckt die letzten 90 Tage ab und bewertet die Definition Ihrer berechneten Metrik kontinuierlich.

   Die **[!UICONTROL Produktkompatibilität]** gibt an, ob die berechnete Metrik beim Experimentieren verwendet werden kann. Mögliche Werte sind:
   * **[!UICONTROL Überall im Customer Journey Analytics]**: Die berechnete Metrik kann für das gesamte Customer Journey Analytics verwendet werden.
   * **[!UICONTROL Überall im Customer Journey Analytics (ohne Experimentieren)]**: Die berechnete Metrik kann auf allen Customer Journey Analytics-Instanzen verwendet werden, mit Ausnahme des Experimentier-Bedienfelds.

1. Auswählen:
   * **[!UICONTROL Speichern]**, um die berechnete Metrik zu speichern.
   * **[!UICONTROL Speichern unter]**, um eine Kopie der berechneten Metrik zu speichern.
   * **[!UICONTROL Abbrechen]**, um alle Änderungen an der berechneten Metrik abzubrechen oder die Erstellung einer neuen berechneten Metrik abzubrechen.


## Definition Builder

Mit dem Definition Builder können Sie per Drag-and-Drop Dimensionen, Metriken, Filter und Funktionen per Drag-and-Drop verschieben und benutzerdefinierte Metriken erstellen, die auf Container-Hierarchielogik, Regeln und Operatoren basieren. In dieser Konstruktion können Sie Standardmetriken, Adobe definierte Metriken, berechnete Metriken, Filter, Dimensionen und Funktionen verwenden. Alle diese Komponenten sind über das Bedienfeld „Komponenten“ im Generator für berechnete Metriken verfügbar. Darüber hinaus können Sie in der Definition Operatoren und Container verwenden.

![Berechnete Metrik erstellen](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Nur Metriken werden als einzelne Komponenten im Bereich &quot;**[!UICONTROL &quot;]**. Alle anderen Komponenten sind als Container, Umbruchmetriken oder andere Container definiert. Weitere Informationen finden [ unter ](#containers)Container“.

### Metriken

Hinzufügen einer Metrik:

* Ziehen Sie eine Komponente ![Ereignisse](/help/assets/icons/Event.svg) **[!UICONTROL Metriken]** aus dem Bedienfeld „Komponenten“ auf **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen per Drag-and-Drop hierher]**. Sie können den ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.

Wenn Sie eine berechnete Metrik als Teil Ihrer Definition verwenden, wird die berechnete Metrik erweitert.

So ändern Sie eine Metrik:

1. Wählen ![Einstellung](/help/assets/icons/Setting.svg) in einer Metrikkomponente im Bereich **[!UICONTROL Definition]** aus.
1. Im Popup-Dialogfeld können Sie den Typ der Metrik und ein Attributionsmodell definieren. Siehe [Metriktyp und Attribution](m-metric-type-alloc.md).

Löschen einer Metrik:

* Wählen ![ in ](/help/assets/icons/Close.svg) Metrik „Schließen“ aus.

### Operatoren

Mit Operatoren können Sie den Operator zwischen Komponenten oder Containern angeben. Operatoren werden automatisch angezeigt zwischen

* zwei oder mehr Metriken in einem Container,
* zwei oder mehr Behälter in einem Behälter,
* Eine oder mehrere Metriken und ein oder mehrere Container in einem Container.

Folgende Optionen stehen zur Auswahl:

| Symbol | Operator |
|:---:|---|
| ![Trennen](/help/assets/icons/Divide.svg) | Trennen (Standard) |
| ![Schließen](/help/assets/icons/Close.svg) | Multiplizieren |
| ![Entfernen](/help/assets/icons/Remove.svg) | Subtrahieren |
| ![Hinzufügen](/help/assets/icons/Add.svg) | Hinzufügen |

### Statische Zahl

Sie können Ihrer Definition für berechnete Metriken eine statische Zahl hinzufügen. So fügen Sie eine statische Zahl hinzu:

* Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** in einem Container aus.
* Wählen Sie **[!UICONTROL Statische Zahl]** aus. Ein statischer Zahlencontainer wird angezeigt.
* Wählen Sie [!UICONTROL *Klicken Sie, um einen Wert hinzuzufügen*] und geben Sie einen Wert ein.


### Container

Sie fügen Dimensionen, Filter und Funktionen als Container zu einer Definition für berechnete Metriken hinzu. Sie können auch einen generischen Container hinzufügen. Container funktionieren wie mathematische Ausdrücke und bestimmen die Reihenfolge der Vorgänge. Alles in einem Container wird vor der nächsten Komponente oder dem nächsten Container verarbeitet.


#### Filter-Container

Sie verwenden das Konzept eines Filter-Containers, um eine [gefilterte Metrik“ ](metrics-with-segments.md). Sie können einen Filter-Container mithilfe eines Filters oder mithilfe eines Filters erstellen, den Sie aus einer Dimension erstellen.

* So fügen Sie einen Filter-Container aus einer Dimension hinzu:

   1. Ziehen Sie eine ![Dimensionen ](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensionen]**-Komponente aus dem Komponentenbedienfeld auf **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen per Drag-and-Drop hierher]**. Sie können den ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.
   1. Definieren Sie **[!UICONTROL Popup Filter aus Dimension]** die Bedingung für den Filter. Wählen Sie in der Benutzerliste einen Wert aus, oder geben Sie einen Wert ein. Beispiel: **[!UICONTROL Monat]** **[!UICONTROL gleich]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Wählen Sie **[!UICONTROL Fertig]** aus. Ein Filter-Container wird der **[!UICONTROL Definition]** hinzugefügt.


* Um einen Filter-Container aus einem Filter hinzuzufügen, können Sie Folgendes verwenden:

   * Ziehen Sie eine Komponente ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** aus dem Bedienfeld „Komponenten“ auf **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen per Drag-and-Drop hierher]**. Sie können den ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Filtern zu suchen.
Der **[!UICONTROL Definition“ wird automatisch ein Filter]** Container mit dem Namen des Filters hinzugefügt.

   * Ziehen Sie eine Komponente ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** aus dem Bedienfeld „Komponenten“ in einen generischen Container. Der Container wird in einen Filter-Container geändert.

   * Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** in einem Container aus:

      1. Wählen Sie **[!UICONTROL Filter]** aus. Ein Filter-Container wird der **[!UICONTROL Definition]** hinzugefügt.
      1. Wählen Sie im neuen Filter-Container einen Filter aus dem Dropdown [!UICONTROL *Menü Auswählen…*].

  >[!TIP]
  >
  >Sie können mehr als einen Filter zu einem Container hinzufügen.

  Die Filter im Container werden nach der Filterkomponente benannt. Beispiel: ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web-]**. Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup mit Details zum Filter anzuzeigen. Wählen Sie im Popup die Option ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um die Filterdefinition zu bearbeiten.

So entfernen Sie einen Filter aus einem Container:

* Klicken Sie ![Schließen](/help/assets/icons/Close.svg) neben dem Filternamen.

Weitere [ und Beispiele finden ](metrics-with-segments.md) unter „Gefilterte Metriken“.

#### Funktions-Container

Um einen Funktions-Container hinzuzufügen, können Sie Folgendes verwenden:

* Drag &amp; Drop:

   1. Ziehen Sie eine Komponente ![Funktion](/help/assets/icons/Effect.svg) **[!UICONTROL Funktionen]** aus dem Bedienfeld „Komponenten“ auf **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen per Drag-and-Drop hierher]**. Sie können den ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Funktionen zu suchen.
   1. Der **[!UICONTROL Definition“ wird automatisch ein Funktions-Container mit]** Namen der Funktion hinzugefügt.

* Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** in einem Container aus:

   1. Wählen Sie **[!UICONTROL Funktion]**.
   1. Wählen Sie im Container eine Funktion aus dem Dropdown [!UICONTROL *Menü Auswählen…*] aus.

Der Funktions-Container ist nach der Funktionskomponente benannt. Beispiel: ![Funktion](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATWURZEL (Metrik)]**. Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup mit Details zur Funktion anzuzeigen. Wählen Sie **[!UICONTROL Weitere Informationen]** aus, um weitere Informationen zur Funktion zu erhalten.

Unter [Funktionen verwenden](cm-using-functions.md) finden Sie Details zur Verwendung von Funktionen und dazu, welche Funktionen zum Erstellen einer berechneten Metrik verfügbar sind.


#### Allgemeiner Container

So fügen Sie einen generischen Container hinzu:

* Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** in einem Container aus.
* Wählen Sie **[!UICONTROL Container]** aus. Ein neuer leerer generischer Container wird zur **[!UICONTROL Definition]** hinzugefügt. Sie können einen generischen Container verwenden, um eine Hierarchie in der Definition Ihrer berechneten Metrik zu verschachteln oder zu erstellen.


#### Löschen eines Containers

Um einen Container zu löschen, wählen ![ auf ](/help/assets/icons/Close.svg) Container-Ebene die Option „Schließen“ aus.

>[!MORELIKETHIS]
>
>[Funktionen verwenden](cm-using-functions.md)
>[Filter](/help/components/filters/filters-overview.md)
>

