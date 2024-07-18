---
description: Ein Bedienfeld ist eine Sammlung von Tabellen und Visualisierungen
title: Übersicht über Bedienfelder
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 665dcd8edcfae6bbf3239c0812ce70843f2ce07c
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 100%

---

# Übersicht über Bedienfelder

Ein [!UICONTROL Bedienfeld] ist eine Sammlung von Tabellen und Visualisierungen. Sie können über das Symbol oben links in Arbeitsbereich oder über ein [leeres Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md) auf Bedienfelder zugreifen. Bedienfelder sind hilfreich, wenn Sie Ihre Projekte nach Zeiträumen, Datenansichten oder Anwendungsfällen für Analysen organisieren möchten.

## Bedienfeldtypen

Die folgenden Bedienfeldtypen sind in Analysis Workspace für [!UICONTROL Customer Journey Analytics] verfügbar:

| Name des Bedienfelds | Beschreibung |
| --- | --- |
| [Leeres Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md) | Wählen Sie zum Beginnen Ihrer Analyse aus den verfügbaren Bedienfeldern und Visualisierungen. |
| [Bedienfeld „Quick Insights“](quickinsight.md) | Sie können rasch eine Freiformtabelle und eine entsprechende Visualisierung erstellen, um Einblicke schneller zu analysieren und bereitzustellen. |
| [Attributionsbedienfeld](attribution.md) | Vergleichen und visualisieren Sie im Handumdrehen eine beliebige Anzahl von Attributionsmodellen unter Verwendung verschiedener Dimensionen und Konversionskennzahlen. |
| [Freiform-Bedienfeld](freeform-panel.md) | Führen Sie unbegrenzte Vergleiche und Aufschlüsselungen durch und fügen Sie dann Visualisierungen hinzu, um eine ausführliche Story mit den Daten zu erzählen. |
| [Bedienfeld „Gleichzeitige Medienbetrachter“](media-concurrent-viewers.md) | Analysieren Sie gleichzeitige Betrachter über einen längeren Zeitraum. Sie erhalten Details zum maximalen gleichzeitigen Zugriff und die Möglichkeit, aufzuschlüsseln und zu vergleichen. |
| [Bedienfeld „Mit Medienwiedergabe verbrachte Zeit“](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Durch die Analyse der Wiedergabedauer können Sie erkennen, wo Spitzenzeiten bei gleichzeitigen Ansichten aufgetreten sind oder wo es zu Abbrüchen gekommen ist. |

![Das Bedienfeld „Customer Journey Analytics“ listet die verfügbaren Bedienfeldtypen auf.](assets/panel-overview.png)

Die Bedienfelder [!UICONTROL Quick Insights], [!UICONTROL Leer] und [!UICONTROL Freiform] eignen sich hervorragend als Ausgangspunkt für Ihre Analyse. [!UICONTROL Attribution IQ] bietet sich für erweiterte Analysen an. In Projekten steht eine `"+"`-Schaltfläche zur Verfügung, mit der Sie jederzeit leere Bedienfelder hinzufügen können.

Das standardmäßige Startbedienfeld ist das [!UICONTROL Freiform-]Bedienfeld. Sie können jedoch auch das [leere Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md) als Standard festlegen.

## Kalender {#calendar}

Über den Panel-Kalender wird der Reporting-Bereich für Tabellen und Visualisierungen innerhalb eines Panels festgelegt.

Hinweis: Wenn eine (violette) Datumsbereichskomponente in einer Tabelle, Visualisierung oder dem Ablagebereich eines Bedienfelds verwendet wird, wird der Bedienfeldkalender überschrieben.

![Das Kalenderfenster mit dem ausgewählten Datumsbereich.](assets/panel-calendar.png)

Sie können unter den erweiterten Einstellungen Ihres Bedienfeldkalenders einen Datumsbereich auf Minutenebene anwenden. Wenn Sie Berichte zu einem Datumsbereich erstellen, der viele Tage umfasst, gilt als Startzeit der erste Tag und als Endzeit der letzte Tag in Ihrem Bereich.

## Ablagebereich {#dropzone}

Mit dem Ablagebereich eines Bedienfelds können Sie Filter und Dropdown-Filter auf alle Tabellen und Visualisierungen innerhalb des Bedienfelds anwenden. Sie können einen oder mehrere Filter auf ein Bedienfeld anwenden.

### Filter

Ziehen Sie einen beliebigen Filter aus der linken Leiste in den Ablagebereich des Bedienfelds, um mit dem Filtern des Bedienfelds zu beginnen.  Wiederholen Sie diesen Vorgang, um dem Bedienfeld weitere Filter hinzuzufügen. Filter werden oben im Bedienfeld nebeneinander angezeigt.

![Die linke Leiste zeigt verfügbare Metriken, und die Mobile-Kunden-Metrik wurde in den Ablegebereich des Bedienfelds gezogen.](assets/segment-filter.png)

### Ad-hoc-Filter

Komponenten, die keine Filter sind, können ebenfalls direkt in den Ablagebereich gezogen werden, um Ad-hoc-Filter zu erstellen. Dadurch muss Filter Builder nicht aufgerufen werden. Auf diese Weise erstellte Filter werden automatisch als Filter auf Ereignisebene definiert. Diese Definition kann geändert werden, indem Sie auf das Informationssymbol (i) neben dem Filter und dann auf das stiftförmige Bearbeitungssymbol klicken und sie in Filter Builder bearbeiten.

Ad-hoc-Filter sind eine Art Schnellfilter und für das Projekt lokal verfügbar. Sie werden nicht in der linken Leiste angezeigt, es sei denn, Sie machen sie öffentlich.

Weitere Informationen finden Sie unter [Schnellfilter](/help/components/filters/quick-filters.md).

![Ad-hoc-Filter, die veröffentlicht und in im Ablegebereich abgelegt werden.](assets/adhoc-segment-filter.png)

### Statische Dropdown-Filter

Statische Dropdown-Filter ermöglichen Ihnen eine kontrollierte Interaktion mit den Daten. Sie können beispielsweise einen Dropdown-Filter für Typen von Mobilgeräten hinzufügen, damit Sie das Bedienfeld nach Tablet, Mobiltelefon oder Desktop filtern können.

Statische Dropdown-Filter können auch verwendet werden, um mehrere Projekte in einem Projekt zu bündeln. Wenn Sie z. B. mehrere Versionen desselben Projekts mit unterschiedlichen Filtern je nach Land verwenden, können Sie alle Versionen in einem Projekt zusammenfassen und einen Dropdown-Filter „Land“ hinzufügen.

![Statische Dropdown-Filter, die den Filter „Direkt“ für den Marktkanal hervorgehoben anzeigen. ](assets/dropdown-filter-intro.png)

#### Erstellen von statischen Dropdown-Filtern

* Wählen Sie für Dropdown-Filter mit Dimensionselementen eine einzelne Dimension aus der linken Leiste aus und legen Sie sie im Ablagebereich des Bedienfelds ab, **während Sie `[Shift]`** gedrückt halten. Dadurch wird ein Dropdown-Filter mit allen Dimensionselementen erstellt, die mit dieser Dimension verknüpft sind.

  Wenn Sie möchten, dass der Dropdown-Filter nur bestimmte Dimensionselemente enthält, die mit einer Dimension verknüpft sind, klicken Sie in der linken Leiste auf das Pfeilsymbol neben der gewünschten Dimension. Diese Aktion legt alle verfügbaren Dimensionselemente offen. Wählen Sie mithilfe von `[Shift + Click]` oder `[Ctrl + Click]` mehrere Dimensionselemente aus dieser Liste aus und legen Sie sie dann im Ablegebereich des Bedienfelds ab, **während** Sie `[Shift]` gedrückt halten.

* Wählen Sie für Dropdown-Filter, die einen einzelnen Komponententyp verwenden (z. B. nur Dimensionen, nur Filter oder nur Metriken), in der linken Leiste über `[Shift + Click]` oder `[Ctrl + Click]` mehrere Elemente desselben Typs aus und legen Sie sie dann im Ablagebereich des Bedienfelds ab, **während Sie `[Shift]`** gedrückt halten.

  Mit den von Ihnen ausgewählten Komponenten wird ein einzelner Dropdown-Filter erstellt.

* Wählen Sie für Dropdown-Filter, die gemischte Komponententypen (etwa 2 Metriken und 3 Filter) verwenden, mithilfe von `[Shift + Click]` oder `[Ctrl + Click]` mehrere Komponenten aus. Legen Sie die Auswahl im Ablegebereich des Bedienfelds ab, **während Sie`[Shift]`** gedrückt halten. In diesem Kontext werden alle Komponententypen als separate Dropdown-Filter behandelt. Wenn Sie beispielsweise sowohl Metriken als auch Dimensionselemente in Ihre Auswahl aufnehmen, werden zwei separate Dropdown-Filter erstellt: Der eine enthält Dimensionselemente und der andere Metriken.

  ![Das Fenster „Bedienfelder“ mit dem Feld „Mobilkundensegment“ ist verfügbar, um einen statischen Dropdown-Filter abzulegen. ](assets/create-dropdown.png)

Wenn Sie mit der rechten Maustaste auf einen Dropdown-Filter klicken, stehen folgende Optionen zur Verfügung:

* **[!UICONTROL Dropdown-Filter löschen]**: Entfernt den Dropdown-Filter aus dem Bedienfeld.
* **[!UICONTROL Label löschen]**: Entfernt den Text über einem Dropdown-Filter.  Wählen Sie zum Ändern des Labels das Stiftsymbol aus.
* **[!UICONTROL Titel hinzufügen]**: Wenn Sie einem Projekt einen Dropdown-Filter hinzufügen, wird für einen Titel automatisch der Komponentenname festgelegt. Wenn Sie den Titel löschen, können Sie ihn mit dieser Option erneut hinzufügen.
* **[!UICONTROL Auswahl erforderlich]**: Erfordert, dass im Bedienfeld ein Filter festgelegt ist.

[Sehen Sie sich das Video an](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=de), um mehr über das Hinzufügen von Dropdown-Filtern zu Ihrem Projekt zu erfahren.

#### Verwenden statischer Dropdown-Filter

Benutzende können das Dropdown-Filtermenü auf eine der folgenden Arten verwenden, um das Bedienfeld zu filtern:

* Wenden Sie einen einzelnen Filter auf das Bedienfeld an, indem Sie ihn über den Dropdown-Filter auswählen.

* Wenden Sie mehrere Filter auf das Bedienfeld an, indem Sie mehr als einen Filter über den Dropdown-Filter auswählen. Das Bedienfeld wird gefiltert, um alle ausgewählten Filter einzuschließen.

  ![Auswählen mehrerer Filter](assets/dropdown-filter-multiselect.png)

### Dynamische Dropdown-Filter

Dynamische Dropdown-Filter ermöglichen es Ihnen, verfügbare Werte basierend auf Daten innerhalb des Berichtsbereichs des Bedienfelds und Werte in anderen Dropdown-Filtern zu bestimmen. Sie können beispielsweise zwei dynamische Dropdown-Listen mit einer Dimension „Länder“ und einer Dimension „Städte“ erstellen. Wenn Sie ein Land aus der Dropdown-Liste „UICONTROL Länder“ auswählen, wird die Dropdown-Liste „Städte“ dynamisch angepasst, sodass nur Städte in diesem Land angezeigt werden.

Dieses Konzept gilt für alle Dimensionen. Es werden nur Dimensionselemente, die innerhalb des Datumsbereichs des Bedienfelds erscheinen, und ausgewählte Filter angezeigt.  In statischen Dropdown-Filtern ausgewählte Dimensionen wirken sich auf verfügbare Werte in dynamischen Dropdown-Filtern aus. Das Gegenteil ist jedoch nicht der Fall: In dynamischen Dropdown-Filtern ausgewählte Dimensionselemente wirken sich nicht auf verfügbare Werte in statischen Dropdown-Filtern aus.

Eine manuelle Auswahl von Dimensionselementen ist verfügbar, wenn Sie erwarten, dass ein bestimmtes Dimensionselement in Zukunft erfasst wird. Sie können auch einen dynamischen Dropdown-Filter löschen, sodass dieser keinen Wert enthält, wodurch andere dynamische Dropdown-Filter mehr Werte enthalten können. Wählen Sie **[!UICONTROL Alle zurücksetzen]** aus, um die Auswahl aus allen Dropdown-Filtern für dieses Bedienfeld zu löschen.

So erstellen Sie einen dynamischen Dropdown-Filter:

* Ziehen Sie eine einzelne Dimension in den Ablegebereich des Bedienfelds, **während Sie`[Shift]`** gedrückt halten.
* Dynamische Dropdown-Filter sind nicht für Metriken, Filter oder Datumsbereiche verfügbar.
* Klicken Sie mit der rechten Maustaste auf einen Dropdown-Filter und wählen Sie **[!UICONTROL Filter löschen]** aus, um ihn zu löschen.

Wenn Sie mit der rechten Maustaste auf einen dynamischen Dropdown-Filter klicken, stehen dieselben Optionen zur Verfügung wie für statische Dropdown-Filter.

## Rechtsklickmenü {#right-click}

Weitere Funktionen für ein Bedienfeld sind verfügbar, wenn Sie mit der rechten Maustaste auf die Bedienfeldüberschrift klicken.

![Die Rechtsklick-Optionen für eine Bedienfeldüberschrift.](assets/right-click-menu.png)

Folgende Einstellungen sind verfügbar:

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Kopiertes Bedienfeld/kopierte Visualisierung einfügen] | Ermöglicht es Ihnen, das kopierte Bedienfeld oder die kopierte Visualisierung an einer anderen Stelle innerhalb des Projekts oder in ein ganz anderes Projekt einzufügen. |
| [!UICONTROL Bedienfeld kopieren] | Ermöglicht es Ihnen, mit der rechten Maustaste auf ein Bedienfeld zu klicken und es zu kopieren, sodass Sie es an einer anderen Stelle innerhalb des Projekts oder in ein anderes Projekt einfügen können. |
| [!UICONTROL Bedienfeld duplizieren] | Fertigt ein exaktes Duplikat des aktuellen Bedienfelds an, das Sie dann bearbeiten können. |
| [!UICONTROL Alle Bedienfelder reduzieren/erweitern] | Reduziert und erweitert alle Projektbedienfelder. |
| [!UICONTROL Alle Visualisierungen im Bedienfeld reduzieren/erweitern] | Reduziert bzw. erweitert alle Visualisierungen im aktuellen Bedienfeld. |
| [!UICONTROL Beschreibung bearbeiten] | Hiermit können Sie einen Text zur Beschreibung des Bedienfelds hinzufügen (oder bearbeiten). |
| [!UICONTROL Bereichslink abrufen] | Sie können Personen zu einem bestimmten Bereich innerhalb eines Projekts leiten. Wenn auf den Link geklickt wird, muss sich der Empfänger anmelden, bevor er zu genau dem Bedienfeld weitergeleitet wird, mit dem er verknüpft ist. |
