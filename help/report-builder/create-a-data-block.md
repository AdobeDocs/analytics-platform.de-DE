---
title: Erstellen eines Datenblocks in Report Builder
description: Erfahren Sie, wie Sie einen Datenblock erstellen.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/MdIYz3KjKm6YUCTNT31LGIvEvfezHyOpemy7xg1FCvE
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 773
ht-degree: 25%

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
>[Auswählen eines Datumsbereichs](select-date-range.md)
>[Filterdimensionen](filter-dimensions.md)
>[Arbeiten mit Segmenten](work-with-filters.md)
>
