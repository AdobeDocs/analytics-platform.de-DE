---
description: Verwenden von Schnellsegmenten in Analysis Workspace für Customer Journey Analytics
title: Schnellsegmente
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 716d6423c0cc8b91aa4951952191e0fd0e627c0f
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 59%

---

# Schnellsegmente

Schnellsegmente ermöglichen es Ihnen, Daten innerhalb eines Workspace-Projekts schnell zu untersuchen, ohne dass ein Segment in [Segment Builder“ erstellt ](/help/components/filters/create-filters.md) muss.



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Schnellsegmente in Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


Beachten Sie bei der Verwendung von Schnellsegmenten Folgendes:

* Schnellsegmente werden direkt in einem Workspace-Projekt erstellt. Daher gilt ein Schnellsegment nur für das Workspace-Projekt, in dem Sie das Schnellsegment erstellen. Die Schnellsegmente in Ihrem Workspace-Projekt sind nicht in anderen Projekten verfügbar und können nicht für andere Benutzer freigegeben werden.
* Sie können nur drei Bedingungen als Teil eines Schnellsegments angeben.
* Schnellsegmente unterstützen keine verschachtelten Container oder sequenziellen Bedingungen.
* Sie können Schnellsegmente in einem freigegebenen Workspace-Projekt bearbeiten. Andere Benutzer können die Schnellsegmente in einem Workspace-Projekt bearbeiten, das Sie für diese Benutzer freigegeben haben.

## Erstellen

Schnellsegmente werden auf Bedienfelder angewendet. Sie können für jedes Bedienfeld in Ihrem Workspace-Projekt ein oder mehrere Schnellsegmente erstellen. Jeder Benutzer in Analysis Workspace kann Schnellsegmente erstellen.

So erstellen Sie ein Schnellsegment:

* Wählen ![ oben ](/help/assets/icons/FilterAdd.svg) Bedienfeld „SegmentHinzufügen“ aus. <br/>Bearbeiten Sie dann das Segment direkt im [Quick Segment Builder](#quick-filter-builder).
* Ziehen Sie eine Komponente aus dem Bedienfeld „Komponente“ in den Ablegebereich für Segmente in der Kopfzeile des Bedienfelds. Bewegen Sie nach dem Ablegen den Mauszeiger über das Segment und wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um das Segment im [Quick Segment Builder“ ](#quick-filter-builder) bearbeiten.

Beachten Sie beim Erstellen eines Schnellsegments per Drag-and-Drop Folgendes:

* Es werden nicht alle Komponententypen unterstützt. Berechnete Metriken werden nicht unterstützt, und nur Dimensionen und Metriken, aus denen Sie Segmente erstellen können, werden unterstützt.
* Für Dimensionen und Metrikkomponenten erstellt [Quick Segment Builder](#quick-filter-builder) automatisch eine `exists`. Wenn Sie beispielsweise `City` ziehen und ablegen, wird die Bedingung `City exists` erstellt.
* Für Dimensionswerte erstellt [Quick Segment Builder](#quick-filter-builder) automatisch eine `equals`. Wenn Sie beispielsweise `amsterdam` aus der Dimension `City` ziehen und ablegen, wird die Bedingung `City equals amsterdam` erstellt.
* Wenn Sie `unspecified` oder `none` per Drag-and-Drop verschieben, erstellt [Quick Segment Builder](#quick-filter-builder) automatisch eine `does not exist`.

Die von Ihnen erstellten Schnellsegmente werden oben im Bedienfeld angezeigt. Schnellsegmente haben einen hellblauen, dünnen linken Balken. Wenn sich ein Schnellsegment im Bearbeitungsmodus mit dem [Quick Segment Builder](#quick-filter-builder) befindet, wird der Hintergrund des Schnellsegments hellblau dargestellt.

Die Ergebnisse der Schnellsegmente, die Sie in einem Bedienfeld erstellen, werden (mithilfe der UND-Logik) auf alle Visualisierungen angewendet, die Teil des Bedienfelds sind.


## Verwalten

Um ein Schnellsegment zu verwalten, bewegen Sie den Mauszeiger über das spezifische **[!UICONTROL Schnellsegment]**.

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um [Quick Segment Builder](#quick-filter-builder) zu öffnen und das Schnellsegment zu bearbeiten.
* Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup zu öffnen. Das Popup zeigt Informationen zum Filter an. Sie können auf **[!UICONTROL Für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]** klicken, um das Segment der Komponentenliste ![Segment](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmente]** im Komponentenbereich hinzuzufügen. Ein Dialogfeld **[!UICONTROL Schnellsegment speichern]** wird angezeigt, in dem Sie aufgefordert werden, einen Namen für das Segment anzugeben. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren. Ihr [!UICONTROL Schnellsegment] wird zu einem **[!UICONTROL Segment]**. Das Segment kann nicht mehr mit dem [Quick Segment Builder“ bearbeitet ](#quick-filter-builder). Stattdessen müssen Sie das Segment als reguläres Segment bearbeiten, indem Sie den [Segment Builder“ ](filter-builder.md).

## Quick Segment Builder

Unten finden Sie ein Beispiel für den Quick Segment Builder. Im Beispiel wird der Generator für einen Schnellfilter mit dem Namen `Call Reason = Order Change AND Online Orders is greater than or equal 1` geöffnet. Beide Schnellfilter oben gelten für das Panel [!UICONTROL Dashboard für durchschnittliche Bestellwerte] und für alle darin enthaltenen Visualisierungen, wie die Freiformtabelle [!UICONTROL Durchschnittlicher Bestellwert pro Land].

![Quick Segment Builder](assets/quick-filter-builder.png)

Der Schnellfilter-Generator besteht aus den folgenden Bereichen und Schaltflächen.

### Kopfzeilenbereich

Der Kopfzeilenbereich bestimmt den Namen, den Typ und den Umfang des Schnellfilters. Außerdem wird ein Fenster mit den Ergebnissen des Schnellfilters angezeigt.

| Element | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Der Name wird automatisch aus der Schnellfilterdefinition abgeleitet. |
| **[!UICONTROL Personen]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alert](/help/assets/icons/Alert.svg) | Vorschau der aus dem Schnellfilter resultierenden Daten. Ein Balken und ein Prozentwert liefern Erkenntnisse darüber, wie viele der Gesamtdaten Teil des Ergebnisses des Schnellfilters sind. Ein rotes Symbol ![Alert](/help/assets/icons/Alert.svg) signalisiert, dass der Schnellfilter keine Daten zurückgibt. |
| **[!UICONTROL Einbeziehen]**<br/>**[!UICONTROL Ausschließen]** | Wählen Sie im Dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) aus, ob die Ergebnisse des Schnellfilters aus den Daten im Panel ein- oder ausgeschlossen werden sollen. |
| **[!UICONTROL Ereignis]**<br/>**[!UICONTROL Sitzung]**<br/>**[!UICONTROL Person]** | Wählen Sie im Dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) den Umfang des Schnellfilters aus. |

### Bedingungsbereich

Der Bedingungsbereich gibt die Bedingungen an (maximal drei). Für jede Bedingung können Sie Folgendes angeben:

| Element | Beschreibung |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metrik]**<br/>**[!UICONTROL Datumsbereich]** | Wählen Sie im Dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) aus, ob eine Bedingung für eine Dimension, eine Metrik oder einen Datumsbereich angegeben werden soll. |
| **[!UICONTROL *Komponente *]** | Das Komponentenfeld für die Bedingung. Sie können über [!UICONTROL *Zum Hinzufügen eingeben*] eine Komponente eingeben, eine Komponente aus der Liste auswählen oder eine Komponente per Drag-and-Drop aus dem Panel „Komponente“ ziehen. Sie können ähnliche Komponenten nur im Komponentenfeld der Bedingung ablegen. Beispielsweise können Sie eine Dimensionskomponente nur aus dem Panel „Komponente“ in einer Dimensionsbedingung ablegen. <br/>Sie können per Drag-and-Drop auch eine vorhandene Komponente ersetzen.<br/>Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um die Komponente aus dem Komponentenfeld zu löschen. |
| **[!UICONTROL *Operator *]** | Der Operator für die Komponente. Weitere Informationen finden Sie unter [Operatoren](operators.md). Nur für Dimensionen und Metriken verfügbar. |
| **[!UICONTROL *value *]** | Der Wert für die Bedingung. Je nach ausgewähltem Operator kann der Wert aus einer Liste ausgewählt werden oder Sie geben einen Wert ein. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Wählen Sie diese Option aus, um eine Bedingung aus dem Schnellfilter zu löschen. |

### Schaltflächen

| Schaltfläche | Beschreibung |
|---|---|
| **[!UICONTROL UND]**<br/>**[!UICONTROL ODER]** | Nur verfügbar, wenn Sie mehrere Bedingungen definieren. Wählen Sie im Dropdown ![ChevronDown](/help/assets/icons/ChevronDown.svg) zwischen den Bedingungen. Die Auswahl bestimmt die boolesche Logik für den Schnellfilter. Logik kann nicht gemischt werden, wenn drei Bedingungen vorliegen. Die boolesche Logik lautet entweder **[!UICONTROL UND]** oder **[!UICONTROL ODER]**. |
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) | Hierdurch wird Ihrem Schnellfilter eine weitere Bedingung hinzugefügt. Diese Schaltfläche ist nur verfügbar, wenn Sie eine oder zwei Bedingungen für den Schnellfilter definiert haben. |
| **[!UICONTROL Anwenden]** | Wenden Sie die Änderungen auf den Schnellfilter an. |
| **[!UICONTROL Builder öffnen]** | Sie werden im Dialogfeld **[!UICONTROL Sind Sie sicher?]** zur Bestätigung aufgefordert. Wenn Sie **[!UICONTROL OK]** auswählen, können Sie Ihren Filter nicht länger im [Schnellfilteraufbau](#quick-filter-builder) ändern. Ihr Schnellfilter wird in **[!UICONTROL Filter]** umbenannt und hat jetzt einen dunkelblauen, dünnen linken Balken.<br/>Der reguläre [Filteraufbau](filter-builder.md) wird mit der Option **[!UICONTROL Diesen Filter für alle Projekte verfügbar machen und zur Komponentenliste hinzufügen]** geöffnet. <ul><li>Wenn Sie diese Option auswählen und **[!UICONTROL Anwenden]** wählen, wird der Filter der Komponentenliste ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** im Panel „Komponente“ hinzugefügt.</li><li>Wenn Sie diese Option nicht auswählen und **[!UICONTROL Anwenden]** wählen, bleibt der Filter ein reiner Workspace-Projektfilter.</li></ul> |
| **[!UICONTROL Abbrechen]** | Wählen Sie diese Option aus, um die Erstellung oder Bearbeitung eines Schnellfilters abzubrechen. |

## Schnellfilter im Vergleich zu Filtern

Schnellfilter entsprechen genau ihrem Namen. Sie können Schnellfilter schnell inline erstellen und bearbeiten und sehen die Auswirkungen sofort in Ihrem Panel.

Filter bieten im Vergleich zu Schnellfiltern die folgenden Vorteile.

* Filter können für alle Workspace-Projekte verfügbar gemacht werden
* Filter unterstützen eine höhere Komplexität durch die Verwendung verschachtelter und hierarchischer Container und Sequenzen (durch Verwendung von Sequenzfiltern).


