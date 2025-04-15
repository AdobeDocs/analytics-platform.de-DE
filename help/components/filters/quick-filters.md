---
description: Verwenden von Schnellfiltern in Analysis Workspace für Customer Journey Analytics
title: Schnellfilter
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: ht
source-wordcount: '1170'
ht-degree: 100%

---

# Schnellfilter

Schnellfilter ermöglichen es Ihnen, Daten innerhalb eines Workspace-Projekts schnell zu untersuchen, ohne dass ein Filter im [filter builder](/help/components/filters/create-filters.md) erstellt werden muss.



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Schnellsegmente in Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]


Beachten Sie bei der Verwendung von Schnellfiltern Folgendes:

* Schnellfilter werden direkt in einem Workspace-Projekt erstellt. Daher gilt ein Schnellfilter nur für das Workspace-Projekt, in dem Sie den Schnellfilter erstellen. Die Schnellfilter in Ihrem Workspace-Projekt sind nicht in anderen Projekten verfügbar und können nicht für andere Benutzende freigegeben werden.
* Sie können nur drei Bedingungen als Teil eines Schnellfilters angeben.
* Schnellfilter unterstützen keine verschachtelten Container oder sequenziellen Bedingungen.
* Sie können Schnellfilter in einem freigegebenen Workspace-Projekt bearbeiten. Auf diese Weise können andere Benutzende die Schnellfilter in einem Workspace-Projekt bearbeiten, das Sie für diese Benutzenden freigegeben haben.

## Erstellen

Schnellfilter werden auf Panels angewendet. Sie können für jedes Panel in Ihrem Workspace-Projekt einen oder mehrere Schnellfilter erstellen. Alle Analysis Workspace-Benutzenden können Schnellfilter erstellen.

So erstellen Sie einen Schnellfilter:

* Wählen Sie oben im Panel ![FilterAdd](/help/assets/icons/FilterAdd.svg) aus. <br/>Bearbeiten Sie dann den Filter direkt im [Schnellfilteraufbau](#quick-filter-builder).
* Ziehen Sie eine Komponente aus dem Panel „Komponente“ in den Filter-Ablagebereich im Header des Panels. Bewegen Sie den Mauszeiger nach dem Ablegen über den Filter und wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um den Filter im [Schnellfilteraufbau](#quick-filter-builder) zu bearbeiten.

Beachten Sie beim Erstellen eines Schnellfilters per Drag-and-Drop Folgendes:

* Es werden nicht alle Komponententypen unterstützt. Berechnete Metriken werden nicht unterstützt. Es werden nur Dimensionen und Metriken unterstützt, aus denen Sie Filter erstellen können.
* Für Dimensionen und Metrikkomponenten erstellt der [Schnellfilteraufbau](#quick-filter-builder) automatisch eine `exists`-Bedingung. Wenn Sie beispielsweise `City` ziehen und ablegen, wird die Bedingung `City exists` erstellt.
* Für Dimensionswerte erstellt der [Schnellfilteraufbau](#quick-filter-builder) automatisch eine `equals`-Bedingung. Wenn Sie beispielsweise `amsterdam` aus der Dimension `City` ziehen und ablegen, wird die Bedingung `City equals amsterdam` erstellt.
* Wenn Sie `unspecified` oder `none` ziehen und ablegen, erstellt der [Schnellfilteraufbau](#quick-filter-builder) automatisch eine `does not exist`-Bedingung.

Die von Ihnen erstellten Schnellfilter werden oben im Panel angezeigt. Schnellfilter haben einen hellblauen, dünnen linken Balken. Wenn sich ein Schnellfilter im Bearbeitungsmodus mit dem [Schnellfilteraufbau](#quick-filter-builder) befindet, ist der Hintergrund des Schnellfilters hellblau.

Die Ergebnisse der Schnellfilter, die Sie in einem Panel erstellen, werden (mithilfe der UND-Logik) auf alle Visualisierungen angewendet, die Teil des Panels sind.


## Verwalten

Um einen Schnellfilter zu verwalten, bewegen Sie den Mauszeiger über den entsprechenden **[!UICONTROL Schnellfilter]**.

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um den [Schnellfilteraufbau](#quick-filter-builder) zu öffnen und den Schnellfilter zu bearbeiten.
* Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup zu öffnen. Das Popup zeigt Informationen zum Filter an. Sie können **[!UICONTROL Für alle Projekte verfügbar machen und Ihrer Komponentenliste hinzufügen]** auswählen, um den Filter zur Komponentenliste ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** im Panel „Komponente“ hinzuzufügen. Das Dialogfeld **[!UICONTROL Schnellfilter speichern]** wird angezeigt und fordert Sie auf, einen Namen für den Filter anzugeben. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren. Ihr [!UICONTROL Schnellfilter] wird zu einem **[!UICONTROL Filter]**. Sie können den Filter nicht mehr mit dem [Schnellfilteraufbau](#quick-filter-builder) bearbeiten. Stattdessen müssen Sie den Filter als regulären Filter mit dem [Filteraufbau](filter-builder.md) bearbeiten.

## Schnellfilteraufbau

Unten finden Sie ein Beispiel für den Schnellfilteraufbau. Im Beispiel wird der Generator für einen Schnellfilter mit dem Namen `Call Reason = Order Change AND Online Orders is greater than or equal 1` geöffnet. Beide Schnellfilter oben gelten für das Panel [!UICONTROL Dashboard für durchschnittliche Bestellwerte] und für alle darin enthaltenen Visualisierungen, wie die Freiformtabelle [!UICONTROL Durchschnittlicher Bestellwert pro Land].

![Schnellfilter-Generator](assets/quick-filter-builder.png)

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


