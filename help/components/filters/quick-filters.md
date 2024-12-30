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

Schnellfilter ermöglichen es Ihnen, Daten innerhalb eines Workspace-Projekts schnell zu untersuchen, ohne dass ein Filter im [Filtergenerator“ erstellt ](/help/components/filters/create-filters.md) muss.


+++ Das folgende Video zeigt die Verwendung von Schnellfiltern.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

Beachten Sie bei der Verwendung von Schnellfiltern Folgendes:

* Schnellfilter werden direkt in einem Workspace-Projekt erstellt. Daher gilt ein Schnellfilter nur für das Workspace-Projekt, in dem Sie den Schnellfilter erstellen. Die Schnellfilter in Ihrem Workspace-Projekt sind nicht in anderen Projekten verfügbar und können nicht für andere Benutzer freigegeben werden.
* Sie können nur drei Bedingungen als Teil eines Schnellfilters angeben.
* Schnellfilter unterstützen keine verschachtelten Container oder sequenziellen Bedingungen.
* Sie können Schnellfilter in einem freigegebenen Workspace-Projekt bearbeiten. Andere Benutzer können die Schnellfilter in einem Workspace-Projekt bearbeiten, das Sie für diese Benutzer freigegeben haben.

## Erstellen

Schnellfilter werden auf Bedienfelder angewendet. Sie können für jedes Bedienfeld in Ihrem Workspace-Projekt einen oder mehrere Schnellfilter erstellen. Jeder Benutzer in Analysis Workspace kann Schnellfilter erstellen.

So erstellen Sie einen Schnellfilter:

* Wählen ![ oben ](/help/assets/icons/FilterAdd.svg) Bedienfeld „FilterHinzufügen“ aus. <br/>Bearbeiten Sie dann den Filter direkt im [Schnellfilter-Generator](#quick-filter-builder).
* Ziehen Sie eine Komponente aus dem Bedienfeld „Komponente“ in den Ablagebereich für Filter in der Kopfzeile des Bedienfelds. Bewegen Sie nach dem Ablegen den Mauszeiger über den Filter und wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um den Filter im [Schnellfilter-Generator“ ](#quick-filter-builder) bearbeiten.

Beachten Sie beim Erstellen eines Schnellfilters per Drag-and-Drop Folgendes:

* Nicht alle Komponententypen werden unterstützt. Berechnete Metriken werden nicht unterstützt, und nur Dimensionen und Metriken, aus denen Sie Filter erstellen können, werden unterstützt.
* Für Dimensionen und Metrikkomponenten erstellt [Schnellfilter-Generator](#quick-filter-builder) automatisch eine `exists`. Wenn Sie beispielsweise per Drag-and-Drop `City`, wird die Bedingung `City exists` erstellt.
* Für Dimensionswerte erstellt der [Schnellfilter-Generator](#quick-filter-builder) automatisch eine `equals`. Wenn Sie beispielsweise `amsterdam` per Drag-and-Drop aus der Dimension `City` ziehen, wird die `City equals amsterdam` erstellt.
* Wenn Sie `unspecified` oder `none` per Drag-and-Drop verschieben, erstellt [Schnellfilter-Generator](#quick-filter-builder) automatisch eine `does not exist`.

Die von Ihnen erstellten Schnellfilter werden oben im Bedienfeld angezeigt. Schnellfilter haben einen hellblauen, dünnen linken Balken. Wenn sich ein Schnellfilter im Bearbeitungsmodus mit dem [Schnellfilter-Generator](#quick-filter-builder) befindet, ist der Hintergrund des Schnellfilters hellblau.

Die Ergebnisse der Schnellfilter, die Sie in einem Bedienfeld erstellen, werden (mithilfe der UND-Logik) auf alle Visualisierungen angewendet, die Teil des Bedienfelds sind.


## Verwalten

Um einen Schnellfilter zu verwalten, bewegen Sie den Mauszeiger über den entsprechenden **[!UICONTROL Schnellfilter]**.

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um den [Schnellfilter-Generator](#quick-filter-builder) zu öffnen und den Schnellfilter zu bearbeiten.
* Wählen Sie ![InfoOutline](/help/assets/icons/InfoOutline.svg) aus, um ein Popup zu öffnen. Das Popup zeigt Informationen zum Filter an. Sie können auf **[!UICONTROL Für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]** klicken, um den Filter zur Komponentenliste ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** im Komponentenbereich hinzuzufügen. Ein Dialogfeld **[!UICONTROL Schnellfilter speichern]** wird angezeigt, in dem Sie aufgefordert werden, einen Namen für den Filter anzugeben. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren. Ihr [!UICONTROL Schnellfilter] wird zu einem **[!UICONTROL Filter]**. Sie können den Filter nicht mehr mit dem [Schnellfilter-Generator](#quick-filter-builder) bearbeiten. Stattdessen müssen Sie den Filter als regulären Filter bearbeiten, indem Sie den [Filter-Builder](filter-builder.md) verwenden.

## Schnellfilter-Generator

Unten finden Sie ein Beispiel für den Schnellfilter-Generator. Im Beispiel wird der Builder für einen Schnellfilter mit dem Titel `Call Reason = Order Change AND Online Orders is greater than or equal 1` geöffnet. Beide Schnellfilter oben gelten für das Bedienfeld [!UICONTROL Dashboard für durchschnittliche Bestellwerte] und für alle darin enthaltenen Visualisierungen, wie [!UICONTROL  Freiformtabelle Durchschnittlicher Bestellwert pro Land].

![Schnellfilter-Generator](assets/quick-filter-builder.png)

Der Schnellfilter-Generator besteht aus den folgenden Bereichen und Schaltflächen.

### Kopfzeilenbereich

Der Kopfzeilenbereich bestimmt den Namen, den Typ und den Umfang des Schnellfilters. Außerdem wird ein visuelles Fenster mit den Ergebnissen des Schnellfilters angezeigt.

| Element | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Der Name wird automatisch aus der Schnellfilterdefinition abgeleitet. |
| **[!UICONTROL People]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![alert](/help/assets/icons/Alert.svg) | Vorschau der aus dem Schnellfilter resultierenden Daten. Ein Balken und ein Prozentwert geben Aufschluss darüber, wie viel der Gesamtdaten Teil des Ergebnisses des Schnellfilters ist. Ein rotes ![Warnhinweis](/help/assets/icons/Alert.svg) signalisiert, dass der Schnellfilter keine Daten zurückgibt. |
| **[!UICONTROL include]**<br/>**[!UICONTROL exclude]** | Wählen Sie aus dem Dropdown-![ChevronDown](/help/assets/icons/ChevronDown.svg) aus, ob Sie die Ergebnisse des Schnellfilters aus den Daten im Bedienfeld ein- oder ausschließen möchten. |
| **[!UICONTROL event]**<br/>**[!UICONTROL session]**<br/>**[!UICONTROL person]** | Wählen Sie aus dem Dropdown-![ChevronDown](/help/assets/icons/ChevronDown.svg) den Umfang des Schnellfilters aus. |

### Bedingungsbereich

Der Bedingungsbereich gibt die Bedingungen an (maximal drei). Für jede Bedingung können Sie Folgendes angeben:

| Element | Beschreibung |
|---|---|
| **[!UICONTROL Dimension ]**<br/>**[!UICONTROL Metrik]**<br/>**[!UICONTROL Datumsbereich]** | Wählen Sie aus dem Dropdown![ChevronDown](/help/assets/icons/ChevronDown.svg) aus, ob Sie eine Bedingung für eine Dimension, eine Metrik oder einen Datumsbereich angeben möchten. |
| **[!UICONTROL *Komponente *]** | Das Komponentenfeld für die Bedingung. Sie können [!UICONTROL *Komponente hinzufügen*] eine Komponente eingeben, eine Komponente aus der Liste auswählen oder eine Komponente per Drag-and-Drop aus dem Komponentenfeld ziehen. Sie können ähnliche Komponenten nur im Komponentenfeld der Bedingung ablegen. Beispielsweise können Sie eine Dimensionskomponente nur aus dem Komponentenbereich in einer Dimensionsbedingung ablegen. <br/>Sie können auch per Drag-and-Drop eine vorhandene Komponente ersetzen.<br/>Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um die Komponente aus dem Komponentenfeld zu löschen. |
| **[!UICONTROL *Operator *]** | Der Operator für die Komponente. Weitere Informationen finden [ unter ](operators.md)Operatoren“. Nur für Dimensionen und Metriken verfügbar. |
| **[!UICONTROL *value *]** | Der Wert für die Bedingung. Je nach ausgewähltem Operator kann der Wert aus einer Liste ausgewählt werden oder Sie geben einen Wert ein. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Wählen Sie diese Option aus, um eine Bedingung aus dem Schnellfilter zu löschen. |

### Schaltflächen

| Schaltfläche | Beschreibung |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Nur verfügbar, wenn Sie mehrere Bedingungen definieren. Wählen Sie aus dem Dropdown-Menü ![ChevronDown](/help/assets/icons/ChevronDown.svg) zwischen den Bedingungen aus. Die Auswahl bestimmt die boolesche Logik für den Schnellfilter. Logik kann nicht gemischt werden, wenn drei Bedingungen vorliegen. Die boolesche Logik lautet entweder **[!UICONTROL AND]** oder **[!UICONTROL OR]**. |
| ![Hinzufügen](/help/assets/icons/AddCircle.svg) | Fügt eine weitere Bedingung zu Ihrem Schnellfilter hinzu. Diese Schaltfläche ist nur verfügbar, wenn Sie eine oder zwei Bedingungen für den Schnellfilter definiert haben. |
| **[!UICONTROL Anwenden]** | Wenden Sie die Änderungen auf den Schnellfilter an. |
| **[!UICONTROL Builder öffnen]** | Sie werden zur Bestätigung mit einem **[!UICONTROL Sind Sie sicher?Dialogfeld]**. Wenn Sie **[!UICONTROL OK]** auswählen, können Sie Ihren Filter im [Schnellfilter-Generator](#quick-filter-builder) nicht mehr ändern. Ihr Schnellfilter wird in **[!UICONTROL Filter]** umbenannt und hat jetzt einen dunkelblauen, dünnen linken Balken.<br/>Der reguläre [Filter-Builder](filter-builder.md) wird mit der Option geöffnet **[!UICONTROL Diesen Filter für alle Projekte verfügbar machen und zur Komponentenliste hinzufügen]**. <ul><li>Wenn Sie diese Option auswählen und **[!UICONTROL Anwenden]** wählen, wird der Filter der Komponentenliste ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** im Komponentenfeld hinzugefügt.</li><li>Wenn Sie diese Option nicht auswählen und auf **[!UICONTROL Anwenden]** klicken, bleibt der Filter ein reiner Workspace-Projektfilter.</li></ul> |
| **[!UICONTROL Abbrechen]** | Wählen Sie diese Option aus, um die Erstellung oder Bearbeitung eines Schnellfilters abzubrechen. |

## Schnellfilter im Vergleich zu Filtern

Schnellfilter haben genau den Namen, den sie haben. Sie können Schnellfilter schnell inline erstellen und bearbeiten und die Auswirkungen sofort in Ihrem Bedienfeld sehen.

Filter haben im Vergleich zu Schnellfiltern die folgenden Vorteile.

* Filter können für alle Workspace-Projekte verfügbar gemacht werden
* Filter unterstützen eine höhere Komplexität durch die Verwendung verschachtelter und hierarchischer Container und Sequenzen (die Sequenzfilter verwenden).


