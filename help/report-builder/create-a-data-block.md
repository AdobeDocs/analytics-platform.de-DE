---
title: Erstellen eines Datenblocks in Report Builder
description: Erfahren Sie, wie Sie einen Datenblock erstellen.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 23%

---

# Erstellen eines Datenblocks

Ein *Datenblock* ist die Datentabelle, die von einer einzelnen Datenanforderung erstellt wird. Eine Report Builder-Arbeitsmappe kann mehrere Datenblöcke enthalten. Wenn Sie einen Datenblock erstellen, konfigurieren Sie ihn zunächst und erstellen Sie dann den Build.

## Datenblock konfigurieren

Konfigurieren Sie die anfänglichen Datenblockparameter für die Position des Datenblocks, die Datenansichten und einen Datumsbereich.

1. Wählen Sie ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Erstellen]**.

   ![Screenshot mit der Option „Datenblock erstellen“](./assets/create-data-block.png){zoomable="yes"}


1. Legen Sie den **[!UICONTROL Speicherort des Datenblocks]** fest.

   Die Option Datenblock-Speicherort definiert den Speicherort des Arbeitsblatts, an dem Report Builder die Daten zu Ihrem Arbeitsblatt hinzufügt.

   Um den Speicherort des Datenblocks anzugeben, wählen Sie eine einzelne Zelle im Arbeitsblatt aus oder geben Sie eine Zellenadresse ein, z. B. `a3`, `\\\$a3`, `a\\\$3` oder `sheet1!a2`. Die angegebene Zelle wird zur oberen linken Ecke des Datenblocks, wenn die Daten abgerufen werden.

   Verwenden ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg), um eine Datenblockposition aus der aktuell ausgewählten Zelle im Blatt auszuwählen.

1. Wählen Sie die **[!UICONTROL Datenansichten]** aus.

   Mit der Option „Datenansichten“ können Sie eine Datenansicht aus einem Dropdown-Menü auswählen oder auf eine Datenansicht aus einer Zellenposition verweisen.

   Wählen Sie ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) aus, um eine Datenansicht aus einer Zelle zu erstellen.

1. Legen Sie den **[!UICONTROL Datumsbereich]** fest.

   Mit **[!UICONTROL Option]** Datumsbereich) können Sie einen Datumsbereich auswählen. Datumsbereiche können fest oder rollierend sein.

   Wählen Sie **[!UICONTROL Kalender]** aus, um einen Datenbereich mithilfe von ![Kalender](/help/assets/icons/Calendar.svg) auszuwählen, oder geben Sie einen Datumsbereich manuell ein. Optional können Sie eine Vorgabe aus dem Dropdown **[!UICONTROL _Menü &quot;_]**&quot; auswählen.

   Wählen Sie **[!UICONTROL Aus Zelle]**, um Start- und Enddaten basierend auf einer Zelle im aktuellen Blatt zu definieren.

   Weitere Informationen zu Datumsbereichsoptionen finden Sie unter [Einen Datumsbereich auswählen](select-date-range.md).

1. Klicken Sie auf **[!UICONTROL Weiter]**.

   ![Screenshot mit der Option „Datumsbereich“ und der Schaltfläche „Aktiv Weiter“.](./assets/choose_date_data_view3.png)

   Nach der Konfiguration des Datenblocks können Sie Dimensionen, Metriken und Segmente auswählen, um Ihren Datenblock zu erstellen. Die **[!UICONTROL Dimensionen]**, **[!UICONTROL Metriken]** und **[!UICONTROL Segmente]** werden über dem Bereich **[!UICONTROL Tabelle]** angezeigt.

## Datenblock erstellen

Um den Datenblock zu erstellen, wählen Sie Berichtkomponenten aus und passen Sie dann das Layout an.

1. Fügen Sie **[!UICONTROL Dimensionen]**, **[!UICONTROL Metriken]** und **[!UICONTROL Segmente]** hinzu.

   Scrollen Sie in den Komponentenlisten oder verwenden Sie das Feld ![Suchen](/help/assets/icons/Search.svg) **[!UICONTROL _Komponenten suchen_]**, um Komponenten zu finden. Ziehen Sie Komponenten per Drag-and[!UICONTROL Drop in den Bereich &#x200B;]Tabelle“ oder doppelwählen Sie einen Komponentennamen in der Liste aus, um die Komponente dem Bereich [!UICONTROL Tabelle] hinzuzufügen.

   Doppelklicken Sie auf eine Komponente, um sie einem Standardabschnitt der Tabelle hinzuzufügen.

   - Dimension-Komponenten werden dem Abschnitt ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** oder dem Abschnitt ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** hinzugefügt, wenn die Dimension bereits in den Spalten vorhanden ist.
   - Datumskomponenten werden dem Abschnitt ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** hinzugefügt.
   - Segmentkomponenten werden zum Abschnitt ![Segmentierung](/help/assets/icons/Segmentation.svg)**[!UICONTROL Segmente]** hinzugefügt.
   - Metrikkomponenten werden zum Abschnitt ![Ereignis](/help/assets/icons/Event.svg)**[!UICONTROL Werte]** hinzugefügt.

1. Ordnen Sie die Elemente im Tabellenbereich an, um das Layout Ihres Datenblocks anzupassen.

   Ziehen Sie Komponenten per Drag-and-Drop in jede Liste im Tabellenbereich, um die Komponenten neu anzuordnen, oder wählen Sie ![MehrKlein](/help/assets/icons/MoreSmall.svg) und wählen Sie ![Pfeil](/help/assets/icons/ArrowUp.svg) Nach oben, ![PfeilNach unten](/help/assets/icons/ArrowDown.svg) Nach unten und mehr aus, um Komponenten innerhalb einer Liste zu verschieben.

   Wenn Sie Komponenten zur Tabelle hinzufügen, wird eine Vorschau des Datenblocks an der Stelle des Datenblocks im Arbeitsblatt angezeigt. Das Layout der Datenblock-Vorschau wird automatisch aktualisiert, wenn Sie in der Tabelle Elemente hinzufügen, verschieben oder entfernen.

   ![Screenshot mit den hinzugefügten Komponenten und dem aktualisierten Arbeitsblatt.](./assets/image10.png)


1. Legen Sie optional das **[!UICONTROL Startdatum]** als Dimension fest, um das Startdatum Ihres Datenblocks zu identifizieren. Das Hinzufügen der Startdaten als Dimension ist hilfreich, wenn Sie einen regelmäßig terminierten Bericht mit einem rollierenden Datumsbereich haben. Oder wenn Sie einen unkonventionellen Datumsbereich haben und Sie das Startdatum explizit angeben müssen.

   ![Screenshot mit dem Startdatum in der Liste der Dimensionen.](./assets/start-date-dimension.png)

1. Optional können Sie Zeilen- und Spaltenüberschriften ein- oder ausblenden. Gehen Sie dazu wie folgt vor:

   1. Wählen Sie das Symbol **[!UICONTROL Tabelle]** ![Einstellung](/help/assets/icons/Setting.svg)Einstellungen aus.

      ![Screenshot mit der Option „Tabelleneinstellungen“](./assets/table-settings.png)

   1. Aktivieren oder deaktivieren Sie die Option **[!UICONTROL Zeilen- und Spaltenüberschriften anzeigen]**. Die Kopfzeilen werden standardmäßig angezeigt.

1. Optional können Sie auch Dimensionsbeschriftungen und Metrikkopfzeilen ein- oder ausblenden. Gehen Sie dazu wie folgt vor:

   1. Wählen Sie ![MehrKlein](/help/assets/icons/MoreSmall.svg) auf der Dimensionsbeschriftung oder in der Spaltenüberschrift aus, um das Kontextmenü anzuzeigen.

      ![Das Symbol mit den Auslassungspunkten im Zeilenabschnitt.](./assets/row-heading.png)

   1. Wählen Sie ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** oder ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** aus, um die Dimensionsbeschriftung oder Spaltenüberschrift umzuschalten. Alle Beschriftungen werden standardmäßig angezeigt.

1. Wählen **[!UICONTROL Beenden]**, um die Konfiguration Ihres Datenblocks abzuschließen.

1. Eine Verarbeitungsmeldung **[!UICONTROL #BUSY]** wird angezeigt, während die Analysedaten abgerufen werden.

   ![Die Verarbeitungsmeldung.](./assets/image11.png)

1. Report Builder ruft die Daten ab und zeigt den abgeschlossenen Datenblock im Arbeitsblatt an.

   ![Der abgeschlossene Datenblock.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Datenansicht auswählen](select-data-view.md)
>[Datumsbereich auswählen](select-date-range.md)
>[Filterdimensionen](filter-dimensions.md)
>[Arbeiten mit Segmenten](work-with-filters.md)
>
