---
description: Verwenden von Schnellfiltern in Analysis Workspace für Customer Journey Analytics
title: Schnellfilter
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 2%

---

# Schnellfilter

Mit Schnellfiltern können Sie Daten in einem Workspace-Projekt schnell untersuchen, ohne einen Filter im [Filtergenerator](/help/components/filters/create-filters.md) erstellen zu müssen.


+++ Im folgenden Video wird die Verwendung von Schnellfiltern veranschaulicht.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

Beachten Sie bei der Verwendung von Schnellfiltern Folgendes:

* Schnellfilter werden direkt in einem Workspace-Projekt erstellt. Daher gilt ein Schnellfilter nur für das Workspace-Projekt, in dem Sie den Schnellfilter erstellen. Die Schnellfilter in Ihrem Workspace-Projekt sind nicht in anderen Projekten verfügbar und können nicht für andere Benutzer freigegeben werden.
* Im Rahmen eines Schnellfilters können Sie nur drei Bedingungen festlegen.
* Schnellfilter unterstützen keine verschachtelten Container oder sequenziellen Bedingungen.
* Sie können Schnellfilter in einem freigegebenen Workspace-Projekt bearbeiten. Somit können andere Benutzer die Schnellfilter in einem Workspace-Projekt bearbeiten, das Sie für diese Benutzer freigegeben haben.

## Erstellen

Schnellfilter werden auf Bedienfelder angewendet. Sie können für jedes Bedienfeld in Ihrem Workspace-Projekt einen oder mehrere Schnellfilter erstellen. Jeder Benutzer in Analysis Workspace kann Schnellfilter erstellen.

So erstellen Sie einen Schnellfilter:

* Wählen Sie oben im Bedienfeld ![FilterAdd](/help/assets/icons/FilterAdd.svg) aus. <br/>Bearbeiten Sie dann den Filter direkt im [Schnellfilter-Builder](#quick-filter-builder).
* Ziehen Sie eine Komponente aus dem Komponentenbereich in die Dropzone Filter in der Bedienfeldkopfzeile. Bewegen Sie nach dem Ablegen den Mauszeiger über den Filter und wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um den Filter im [Schnellfilter-Builder](#quick-filter-builder) zu bearbeiten.

Beachten Sie bei der Erstellung eines Schnellfilters per Drag &amp; Drop Folgendes:

* Es werden nicht alle Komponententypen unterstützt. Berechnete Metriken werden nicht unterstützt und es werden nur Dimensionen und Metriken unterstützt, aus denen Sie Filter erstellen können.
* Für Dimensionen und Metrikkomponenten erstellt der [Schnellfilter-Builder](#quick-filter-builder) automatisch eine `exists` -Bedingung. Wenn Sie beispielsweise `City` per Drag-and-Drop verschieben, wird die Bedingung `City exists` erstellt.
* Für Dimensionswerte erstellt der [Schnellfilter-Builder](#quick-filter-builder) automatisch eine `equals` -Bedingung. Wenn Sie beispielsweise `amsterdam` aus der Dimension `City` ziehen und ablegen, wird die Bedingung `City equals amsterdam` erstellt.
* Wenn Sie `unspecified` oder `none` per Drag-and-Drop verschieben, erstellt der [Schnellfilter-Builder](#quick-filter-builder) automatisch eine `does not exist` -Bedingung.

Schnellfilter, die Sie erstellen, werden oben im Bedienfeld angezeigt. Schnellfilter verfügen über eine hellblaue, dünne linke Leiste. Wenn sich ein Schnellfilter mit dem [Quick filter Builder](#quick-filter-builder) im Bearbeitungsmodus befindet, ist der Hintergrund des Schnellfilters hellblau.

Die Ergebnisse der Schnellfilter, die Sie in einem Bedienfeld erstellen, werden (mithilfe der AND-Logik) auf alle Visualisierungen angewendet, die Teil des Bedienfelds sind.


## Verwalten

Um einen Schnellfilter zu verwalten, bewegen Sie den Mauszeiger über den jeweiligen **[!UICONTROL Schnellfilter]**.

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um den [Schnellfilter-Builder](#quick-filter-builder) zu öffnen und den Schnellfilter zu bearbeiten.
* Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup zu öffnen. Das Popup zeigt Informationen zum Filter an. Sie können &quot;**[!UICONTROL Für alle Projekte verfügbar machen&quot;auswählen und Ihrer Komponentenliste hinzufügen]**&quot;. So fügen Sie den Filter zur Komponentenliste ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** im Komponentenbereich hinzu. Es wird ein Dialogfeld **[!UICONTROL Schnellfilter speichern]** angezeigt, in dem Sie aufgefordert werden, einen Namen für den Filter anzugeben. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren. Ihr [!UICONTROL Schnellfilter] wird zu einem **[!UICONTROL Filter]**. Sie können den Filter nicht mehr mit dem [Schnellfilter-Builder](#quick-filter-builder) bearbeiten. Stattdessen müssen Sie den Filter mit dem [Filter-Builder](filter-builder.md) als regulären Filter bearbeiten.

## Schnellfilter-Builder

Unten finden Sie ein Beispiel für den Schnellfilter-Builder. In diesem Beispiel wird der Builder für einen Schnellfilter mit dem Namen `Call Reason = Order Change AND Online Orders is greater than or equal 1` geöffnet. Beide Quick-Filter oben gelten für das Dashboard [!UICONTROL Durchschnittlicher Bestellwert] und alle Visualisierungen innerhalb von, z. B. die Freiformtabelle [!UICONTROL Durchschnittlicher Bestellwert pro Land].

![Schnellfilter-Generator](assets/quick-filter-builder.png)

Der Schnellfilter-Builder besteht aus den folgenden Bereichen und Schaltflächen.

### Kopfzeilenbereich

Der Header-Bereich bestimmt den Namen, den Typ und den Umfang des Schnellfilters. Außerdem werden die Ergebnisse des Schnellfilters visuell dargestellt.

| Element | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Der Name wird automatisch aus der Definition des Schnellfilters abgeleitet. |
| **[!UICONTROL Personen]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Warnung](/help/assets/icons/Alert.svg) | Vorschau der aus dem Schnellfilter resultierenden Daten Ein Balken und ein Prozentsatz geben Aufschluss darüber, wie viele der Gesamtdaten Teil des Ergebnisses des Schnellfilters sind. Ein roter ![Warnhinweis](/help/assets/icons/Alert.svg) signalisiert, dass der Schnellfilter keine Daten zurückgibt. |
| **[!UICONTROL include]**<br/>**[!UICONTROL exclude]** | Wählen Sie aus dem Dropdown-Menü ![ChevronDown](/help/assets/icons/ChevronDown.svg) aus, ob Sie die Ergebnisse des Schnellfilters aus den Daten im Bereich einbeziehen oder ausschließen möchten. |
| **[!UICONTROL event]**<br/>**[!UICONTROL session]**<br/>**[!UICONTROL person]** | Wählen Sie aus dem Dropdown-Menü ![ChevronDown](/help/assets/icons/ChevronDown.svg) den Bereich des Schnellfilters aus. |

### Bedingungsbereich

Der Bedingungsbereich gibt die Bedingungen an (maximal drei). Für jede Bedingung können Sie Folgendes angeben:

| Element | Beschreibung |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metrik]**<br/>**[!UICONTROL Datumsbereich]** | Wählen Sie aus dem Dropdown-Menü ![ChevronDown](/help/assets/icons/ChevronDown.svg) aus, ob Sie eine Bedingung für eine Dimension, Metrik oder einen Datumsbereich angeben möchten. |
| **[!UICONTROL *component *]** | Das Komponentenfeld für die Bedingung. Sie können [!UICONTROL *Typ eingeben, um eine Komponente hinzuzufügen*], eine Komponente aus der Liste auszuwählen oder eine Komponente per Drag-and-Drop aus dem Komponentenbereich ziehen. Sie können ähnliche Komponenten nur im Komponentenfeld der Bedingung ablegen. Beispielsweise können Sie eine Dimensionskomponente nur in einer Dimensionsbedingung aus dem Komponentenbereich ablegen. <br/>Sie können auch per Drag-and-Drop eine vorhandene Komponente ersetzen.<br/>Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um die Komponente aus dem Komponentenfeld zu löschen. |
| **[!UICONTROL *operator *]** | Der -Operator für die Komponente. Weitere Informationen finden Sie unter [Operatoren](operators.md) . Nur für Dimensionen und Metriken verfügbar. |
| **[!UICONTROL *value *]** | Der -Wert für die Bedingung. Je nach gewähltem Operator kann der Wert aus einer Liste ausgewählt oder ein Wert eingegeben werden. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Wählen Sie diese Option aus, um eine Bedingung aus dem Schnellfilter zu löschen. |

### Schaltflächen

| Schaltfläche | Beschreibung |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Nur verfügbar, wenn Sie mehrere Bedingungen definieren. Wählen Sie aus dem Dropdown-Menü ![ChevronDown](/help/assets/icons/ChevronDown.svg) zwischen den Bedingungen aus. Die Auswahl bestimmt die boolesche Logik für den Schnellfilter. Bei drei Bedingungen kann Logik nicht gemischt werden. Die boolesche Logik lautet entweder **[!UICONTROL AND]** oder **[!UICONTROL OR]**. |
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) | Fügt dem Schnellfilter eine weitere Bedingung hinzu. Diese Schaltfläche ist nur verfügbar, wenn Sie eine oder zwei Bedingungen für den Schnellfilter definiert haben. |
| **[!UICONTROL Anwenden]** | Wenden Sie die Änderungen auf den Schnellfilter an. |
| **[!UICONTROL Builder öffnen]** | Sie werden mit dem Wert &quot;**[!UICONTROL Sind Sie sicher?&quot;zur Bestätigung aufgefordert.]** Dialogfeld. Wenn Sie **[!UICONTROL OK]** auswählen, können Sie Ihren Filter im [Quick filter Builder](#quick-filter-builder) nicht mehr ändern. Ihr Schnellfilter wird in **[!UICONTROL Filter]** umbenannt und verfügt jetzt über eine dunkelblaue, blaue, blaue Leiste auf der linken Seite.<br/>Der reguläre [Filter-Builder](filter-builder.md) wird mit der Option **[!UICONTROL geöffnet. Stellen Sie diesen Filter für alle Ihre Projekte zur Verfügung und fügen Sie ihn zu Ihrer Komponentenliste hinzu.]** <ul><li>Wenn Sie diese Option auswählen und **[!UICONTROL Anwenden]** auswählen, wird der Filter der Komponentenliste ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** im Komponentenbereich hinzugefügt.</li><li>Wenn Sie diese Option nicht auswählen und **[!UICONTROL Anwenden]** auswählen, bleibt der Filter nur ein Workspace-Projektfilter.</li></ul> |
| **[!UICONTROL Abbrechen]** | Wählen Sie diese Option aus, um die Erstellung oder Bearbeitung eines Schnellfilters abzubrechen. |

## Schnellfilter versus Filter

Schnellfilter heißen genau. Sie können Schnellfilter schnell inline erstellen und bearbeiten und die Effekte sofort in Ihrem Bedienfeld anzeigen.

Filter bieten im Vergleich zu Schnellfiltern die folgenden Vorteile:

* Filter können für alle Ihre Workspace-Projekte verfügbar gemacht werden
* Filter unterstützen mehr Komplexität durch verschachtelte und hierarchische Container und Sequenzen (mithilfe von Sequenzfiltern).


