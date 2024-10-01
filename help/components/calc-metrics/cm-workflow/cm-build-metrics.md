---
description: Der Generator für berechnete Metriken bietet eine Arbeitsfläche, in der Sie Dimensionen, Metriken, Filter und Funktionen per Drag-and-Drop verschieben können, um benutzerdefinierte Metriken basierend auf Container-Hierarchielogik, Regeln und Operatoren zu erstellen. Mit diesem integrierten Entwicklungstool können Sie einfache berechnete Metriken oder komplexe, erweiterte berechnete Metriken erstellen und speichern.
title: Berechnete Metriken erstellen
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 6%

---

# Berechnete Metriken erstellen {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_productcompatibility"
>title="Produktkompatibilität"
>abstract="Gibt an, wo auf der Customer Journey Analytics diese berechnete Metrik verwendet werden kann, z. B. in Analysis Workspace, Report Builder usw. Einige berechnete Metriken können nicht mit Experimenten verwendet werden."
>additional-url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Verwenden von berechneten Metriken in Experimenten"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_externalid"
>title="Externe ID"
>abstract="Eine Änderung der externen ID kann sich auf die Darstellung der berechneten Metrik in externen Quellen auswirken, z. B. auf Business Intelligence-Tools"

<!-- markdownlint-enable MD034 -->


Das Dialogfeld **[!UICONTROL Generator für berechnete Metriken]** wird verwendet, um neue berechnete Metriken zu erstellen oder vorhandene zu bearbeiten. Das Dialogfeld trägt den Titel **[!UICONTROL Neue berechnete Metrik]** oder **[!UICONTROL Berechnete Metrik bearbeiten]** für Metriken, die Sie über den Manager [[!UICONTROL Berechnete Metriken] erstellen oder verwalten](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Generator für berechnete Metriken]

![Detailfenster für berechnete Metriken mit den im nächsten Abschnitt beschriebenen Feldern und Optionen.](assets/calculated-metric-builder.png)

>[!TAB Berechnete Metrik erstellen oder bearbeiten]

![Detailfenster für berechnete Metriken mit den im nächsten Abschnitt beschriebenen Feldern und Optionen.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) ist erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für die berechnete Metrik auswählen.  Die von Ihnen definierte berechnete Metrik ist in Workspace-Projekten auf der Basis der ausgewählten Datenansicht verfügbar. |
   | **[!UICONTROL Nur Projekt-Metrik]** | Ein Informationsfeld, das erklärt, dass die Metrik nur in dem Projekt sichtbar ist, in dem sie erstellt wird, und dass die Metrik nicht zu Ihrer Komponentenliste hinzugefügt wird. Aktivieren Sie **[!UICONTROL Stellen Sie diese Metrik für alle Ihre Projekte zur Verfügung und fügen Sie sie Ihrer Komponentenliste hinzu]**, um diese Einstellung zu ändern. Dieses Informationsfeld ist nur sichtbar, wenn Sie eine Metrik in Workspace mit &quot;**[!UICONTROL Metrik aus Auswahl erstellen]**&quot;erstellen und eine Funktion ausgewählt haben (z. B. **[!UICONTROL Mittelwert]** oder **[!UICONTROL Median]**). Verwenden Sie später die [Komponenteninfo](/help/components/use-components-in-workspace.md#component-info) , um die erstellte Metrik zu bearbeiten. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Nennen Sie die berechnete Metrik, z. B. &quot;`Conversion Rate`&quot;. |
   | **[!UICONTROL Externe ID]** ![Erforderlich](/help/assets/icons/Required.svg) | Der Name der berechneten Metrik bei Verwendung eines externen BI-Tools und der BI-Erweiterung. Der Wert wird automatisch als `undefined_xxx` definiert, es sei denn, Sie überschreiben den Wert. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für den Filter ein, z. B. `Calculated metric to define the conversion rate.` Es ist nicht erforderlich, die Formel für die berechnete Metrik zu beschreiben, da die Formel bereits automatisch in [!UICONTROL Zusammenfassung] verfügbar ist. |
   | **[!UICONTROL Format]** | Wählen Sie ein Format für die berechnete Metrik aus: Sie können zwischen **[!UICONTROL Dezimal]**, **[!UICONTROL Zeit]**, **[!UICONTROL Prozent]** und **[!UICONTROL Währung]** auswählen. |
   | **[!UICONTROL Dezimalstellen]** | Geben Sie die Anzahl der Dezimalstellen für das ausgewählte Format an. Nur aktiviert, wenn das ausgewählte Format Dezimal, Währung und Prozent ist. |
   | **[!UICONTROL Aufwärts-Trend anzeigen als]** | Geben Sie an, ob ein Aufwärtstrend der berechneten Metrik als **[!UICONTROL Gutes (Grün)]** oder als BS **[!UICONTROL Schlecht (Rot)]** angezeigt wird. |
   | **[!UICONTROL Währung]** | Geben Sie die Währung der berechneten Metrik an. Nur aktiviert, wenn das ausgewählte Format &quot;Währung&quot;ist. |
   | **[!UICONTROL Tags]** | Organisieren Sie die berechnete Metrik, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um vorhandene Tags zu finden, die Sie auswählen können. Oder drücken Sie **[!UICONTROL EINGABETASTE]** , um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Vorschau]** | Die Vorschau deckt die letzten 90 Tage ab und bietet eine Möglichkeit zu messen, ob Sie Ihre Metrik richtig definiert haben. |
   | **[!UICONTROL Zusammenfassung]** | Zeigt eine Zusammenfassung der Definition der berechneten Metrik an. <br/>Beispiel: ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen insgesamt]** ![teilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]**. |
   | **[!UICONTROL Definition]** ![Erforderlich](/help/assets/icons/Required.svg) | Definieren Sie Ihren Filter mit dem [Definition-Builder](#definition-builder). |

1. Um zu überprüfen, ob Ihre berechnete Metrikdefinition korrekt ist, verwenden Sie die ständig aktualisierte **[!UICONTROL Vorschau]** der Ergebnisse der berechneten Metrik. Die **[!UICONTROL Vorschau]** umfasst die letzten 90 Tage und wertet die Definition Ihrer berechneten Metrik kontinuierlich aus.

   Die **[!UICONTROL Produktkompatibilität]** gibt an, ob die berechnete Metrik für Experimente verwendet werden kann. Mögliche Werte sind:
   * **[!UICONTROL Überall auf Customer Journey Analytics]**: Die berechnete Metrik kann während des gesamten Customer Journey Analytics verwendet werden, mit Ausnahme des Experimentierungsbereichs.
   * **[!UICONTROL Überall auf Customer Journey Analytics (ohne Experimentiervorgänge)]**: Die berechnete Metrik kann für alle Customer Journey Analytics verwendet werden.

1. Wählen Sie:
   * **[!UICONTROL Speichern]** , um die berechnete Metrik zu speichern.
   * **[!UICONTROL Speichern unter]** , um eine Kopie der berechneten Metrik zu speichern.
   * **[!UICONTROL Abbrechen]** , um alle Änderungen abzubrechen, die Sie an der berechneten Metrik vorgenommen haben, oder um die Erstellung einer neuen berechneten Metrik abzubrechen.


## Definition-Builder

Mit dem Definition Builder können Sie Dimensionen, Metriken, Filter und Funktionen per Drag &amp; Drop verschieben, um benutzerdefinierte Metriken basierend auf Containerhierarchielogik, Regeln und Operatoren zu erstellen. Bei dieser Konstruktion können Sie Standardmetriken, Adobe definierte Metriken, berechnete Metriken, Filter, Dimensionen und Funktionen verwenden. Alle diese Komponenten sind im Komponentenbereich des Generators für berechnete Metriken verfügbar. Außerdem können Sie Operatoren und Container in der Definition verwenden.

![Berechnete Metrik erstellen](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Nur Metriken werden als einzelne Komponenten im Bereich **[!UICONTROL Definition]** definiert. Alle anderen Komponenten sind als Container, Umbruchmetriken oder andere Container definiert. Weitere Informationen finden Sie unter [Container](#containers) .

### Metriken

So fügen Sie eine Metrik hinzu:

* Ziehen Sie eine Komponente ![Ereignisse](/help/assets/icons/Event.svg) **[!UICONTROL Metriken]** aus dem Komponentenbereich auf **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen hierher.]** Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.

Wenn Sie eine berechnete Metrik als Teil Ihrer Definition verwenden, wird die berechnete Metrik erweitert.

So ändern Sie eine Metrik:

1. Wählen Sie ![Einstellung](/help/assets/icons/Setting.svg) in einer Metrikkomponente im Bereich **[!UICONTROL Definition]** aus.
1. Im Popup-Dialogfeld können Sie den Typ der Metrik und ein Attributionsmodell definieren. Siehe [Metriktyp und Attribution](m-metric-type-alloc.md).

So löschen Sie eine Metrik:

* Wählen Sie ![Schließen](/help/assets/icons/Close.svg) in der Metrik aus.

### Operatoren

Mit Operatoren können Sie den Operator zwischen Komponenten oder Behältern angeben. Benutzer werden automatisch zwischen

* zwei oder mehr Metriken in einem Container,
* zwei oder mehr Behälter in einem Behälter,
* eine oder mehrere Metriken und einen oder mehrere Behälter in einem Container.

Folgende Optionen stehen zur Auswahl:

| Symbol | Operator |
|:---:|---|
| ![divide](/help/assets/icons/Divide.svg) | Dividieren (Standard) |
| ![close](/help/assets/icons/Close.svg) | Multiplizieren |
| ![Entfernen](/help/assets/icons/Remove.svg) | Subtrahieren |
| ![Hinzufügen](/help/assets/icons/Add.svg) | Hinzufügen |

### Statische Zahl

Sie können Ihrer Definition der berechneten Metrik eine statische Zahl hinzufügen. So fügen Sie eine statische Zahl hinzu:

* Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** aus einem Container aus.
* Wählen Sie **[!UICONTROL Statische Zahl]** aus. Ein Container mit statischen Zahlen wird angezeigt.
* Wählen Sie [!UICONTROL *Klicken Sie auf , um einen Wert hinzuzufügen*] und geben Sie einen Wert ein.


### Container

Sie können Dimensionen, Filter und Funktionen als Container zu einer berechneten Metrikdefinition hinzufügen. Sie können auch einen generischen Container hinzufügen. Container funktionieren wie mathematische Ausdrücke und bestimmen die Reihenfolge der Vorgänge. Alles in einem Container wird vor der nächsten Komponente oder dem nächsten Container verarbeitet.


#### Filter-Container

Sie verwenden das Konzept eines Filtercontainers, um eine [gefilterte Metrik](metrics-with-segments.md) zu erstellen. Sie können einen Filtercontainer mithilfe eines Filters oder mithilfe eines aus einer Dimension erstellten Filters erstellen.

* So fügen Sie einen Filtercontainer aus einer Dimension hinzu:

   1. Ziehen Sie eine Komponente vom Typ ![Dimensionen](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensionen]** aus dem Komponentenbereich auf **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen hierher.]** Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Komponenten zu suchen.
   1. Definieren Sie im Popup-Fenster **[!UICONTROL Filter aus Dimension erstellen]** die Filterbedingung. Wählen Sie aus der Benutzerliste einen Wert aus oder geben Sie einen Wert ein. Beispiel: **[!UICONTROL Monat]** **[!UICONTROL entspricht]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Wählen Sie **[!UICONTROL Fertig]** aus. Der **[!UICONTROL Definition]** wird ein Filtercontainer hinzugefügt.


* Um einen Filtercontainer aus einem Filter hinzuzufügen, können Sie Folgendes verwenden:

   * Ziehen Sie eine Komponente vom Typ ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** aus dem Komponentenbereich auf **[!UICONTROL Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen hierher ziehen und ablegen]**. Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Filtern zu suchen.
Automatisch wird der **[!UICONTROL Definition]** ein Filtercontainer hinzugefügt, der den Namen des Filters verwendet.

   * Ziehen Sie eine Komponente ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** aus dem Komponentenbereich in einen allgemeinen Container. Der Container wird in einen Filterbehälter geändert.

   * Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** aus einem Container aus:

      1. Wählen Sie **[!UICONTROL Filter]** aus. Der **[!UICONTROL Definition]** wird ein Filtercontainer hinzugefügt.
      1. Wählen Sie im neuen Filtercontainer einen Filter aus dem Dropdown-Menü [!UICONTROL *Auswählen..*] aus.

  >[!TIP]
  >
  >Sie können einem Container mehr als einen Filter hinzufügen.

  Die Filter im Container werden nach der Filterkomponente benannt. Beispiel: ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Websitzungen]**. Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup mit Details zum Filter anzuzeigen. Wählen Sie im Popup ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um die Filterdefinition zu bearbeiten.

So entfernen Sie einen Filter aus einem Container:

* Wählen Sie neben dem Filternamen ![Schließen](/help/assets/icons/Close.svg) aus.

Weitere Informationen und Beispiele finden Sie unter [Gefilterte Metriken](metrics-with-segments.md) .

#### Funktionscontainer

Um einen Funktionscontainer hinzuzufügen, können Sie Folgendes verwenden:

* Drag &amp; Drop:

   1. Ziehen Sie eine Komponente ![Funktion](/help/assets/icons/Effect.svg) **[!UICONTROL Funktionen]** aus dem Komponentenbereich in den Arbeitsbereich **[!UICONTROL Ziehen Sie Metriken, Dimensionen, Dimensionselemente, Filter und/oder Funktionen hierher.]** Sie können die ![Suche](/help/assets/icons/Search.svg) in der Komponentenleiste verwenden, um nach bestimmten Funktionen zu suchen.
   1. Automatisch wird der **[!UICONTROL Definition]** ein Funktionscontainer hinzugefügt, der den Namen der Funktion verwendet.

* Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** aus einem Container aus:

   1. Wählen Sie **[!UICONTROL Funktion]** aus.
   1. Wählen Sie im Container eine Funktion aus dem Dropdown-Menü [!UICONTROL *Auswählen..*] aus.

Der Funktionscontainer wird nach der Funktionskomponente benannt. Beispiel: ![Funktion](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATSTAMM (Metrik)]**. Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup mit Details zur Funktion anzuzeigen. Wählen Sie **[!UICONTROL Mehr erfahren]** , um weitere Informationen zur Funktion zu erhalten.

Weitere Informationen zur Verwendung der Funktionen und zur Erstellung einer berechneten Metrik finden Sie unter [Funktionen verwenden](cm-using-functions.md) .


#### Generischer Container

So fügen Sie einen generischen Container hinzu:

* Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** aus einem Container aus.
* Wählen Sie **[!UICONTROL Container]** aus. Der **[!UICONTROL Definition]** wird ein neuer leerer allgemeiner Container hinzugefügt. Sie können einen generischen Container verwenden, um eine Hierarchie in der Definition Ihrer berechneten Metrik zu verschachteln oder zu erstellen.


#### Container löschen

Um einen Container zu löschen, wählen Sie ![Schließen](/help/assets/icons/Close.svg) auf der Behälterebene aus.

>[!MORELIKETHIS]
>
>[Funktionen verwenden](cm-using-functions.md)
>[Filter](/help/components/filters/filters-overview.md)
>

