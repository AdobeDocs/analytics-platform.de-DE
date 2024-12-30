---
title: Erstellen eines Datenblocks mit Report Builder in Customer Journey Analytics
description: Beschreibt, wie ein Datenblock erstellt wird.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 68%

---

# Datenblock erstellen

Ein *Datenblock* ist die Datentabelle, die von einer einzelnen Datenanforderung erstellt wird. Eine Report Builder-Arbeitsmappe kann mehrere Datenblöcke enthalten. Wenn Sie einen Datenblock erstellen, konfigurieren Sie ihn zunächst und erstellen Sie dann den Build.

## Datenblock konfigurieren

Konfigurieren Sie die anfänglichen Datenblockparameter für die Position des Datenblocks, die Datenansichten und einen Datumsbereich.

1. Klicken Sie auf **Datenblock erstellen**.

   ![Screenshot mit der Option „Datenblock erstellen“.](./assets/create_db.png)

1. Legen Sie den **Speicherort des Datenblocks** fest.

   Die Option „Datenblock-Speicherort“ definiert den Speicherort des Arbeitsblatts, an dem Report Builder die Daten zu Ihrem Arbeitsblatt hinzufügt.

   Um den Speicherort des Datenblocks anzugeben, wählen Sie eine einzelne Zelle im Arbeitsblatt aus oder geben Sie eine Zellenadresse ein, z. B. a3, \\\$a3, a\\\$3 oder sheet1!a2. Die angegebene Zelle ist die obere linke Ecke des Datenblocks, wenn die Daten abgerufen werden.

1. Wählen Sie die **Datenansichten** aus.

   Mit der Option „Datenansichten“ können Sie eine Datenansicht aus einem Dropdown-Menü auswählen oder auf eine Datenansicht aus einer Zellenposition verweisen.

1. Legen Sie den **Datumsbereich** fest.

   Mit der Option „Datumsbereich“ können Sie einen Datumsbereich auswählen. Datumsbereiche können fest oder rollierend sein. Weitere Informationen zu Datumsbereichsoptionen finden Sie unter [Einen Datumsbereich auswählen](select-date-range.md).

1. Klicken Sie auf **Weiter**.

   ![Screenshot mit der Option „Datumsbereich“ und der Schaltfläche „Aktiv Weiter“.](./assets/choose_date_data_view3.png)

   Nach der Konfiguration des Datenblocks können Sie Dimensionen, Metriken und Filter auswählen, um Ihren Datenblock zu erstellen. Die Registerkarten „Dimensionen“, „Metriken“ und „Filter“ werden über dem Bereich „Tabellen-Builder“ angezeigt.

## Datenblock erstellen

Um den Datenblock zu erstellen, wählen Sie Berichtkomponenten aus und passen Sie dann das Layout an.

1. Fügen Sie Dimensionen, Metriken und Filter hinzu.

   Scrollen Sie in den Komponentenlisten oder verwenden Sie das Feld **Suchen**, um Komponenten zu finden. Ziehen Sie Komponenten per Drag &amp; Drop in den Tabellenbereich oder doppelklicken Sie auf einen Komponentennamen in der Liste, um die Komponente automatisch zum Tabellenbereich hinzuzufügen.

   Doppelklicken Sie auf eine Komponente, um sie einem Standardabschnitt der Tabelle hinzuzufügen.

   - Dimensionskomponenten werden zum Bereich „Zeile“ oder zum Bereich „Spalte“ hinzugefügt, wenn bereits eine Dimension in den Spalten vorhanden ist.
   - Datumskomponenten werden dem Abschnitt „Spalte“ hinzugefügt.
   - Filterkomponenten werden dem Abschnitt „Filter“ hinzugefügt.

   **Startdatum als Dimension**

   Legen Sie das Startdatum als Dimension fest, um das Startdatum Ihres Datenblocks eindeutig zu identifizieren. Dies ist hilfreich, wenn Sie einen regelmäßig geplanten Bericht mit einem rollierenden Datumsbereich haben oder wenn Sie einen unkonventionellen Datumsbereich haben und Sie das Startdatum löschen müssen.

   ![Screenshot mit dem Startdatum in der Liste der Dimensionen.](./assets/start-date-dimension.png){width="30%"}

1. Ordnen Sie die Elemente im Tabellenbereich an, um das Layout Ihres Datenblocks anzupassen.

   Ziehen Sie Komponenten per Drag &amp; Drop in den Tabellenbereich, um sie neu anzuordnen, oder klicken Sie mit der rechten Maustaste auf einen Komponentennamen und wählen Sie im Optionsmenü die Option aus.

   Wenn Sie Komponenten zur Tabelle hinzufügen, wird eine Vorschau des Datenblocks an der Stelle des Datenblocks im Arbeitsblatt angezeigt. Das Layout der Datenblock-Vorschau wird automatisch aktualisiert, wenn Sie in der Tabelle Elemente hinzufügen, verschieben oder entfernen.

   ![Screenshot mit den hinzugefügten Komponenten und dem aktualisierten Arbeitsblatt.](./assets/image10.png)

   **Zeilen- und Spaltenüberschriften anzeigen oder ausblenden**

1. Klicken Sie auf **Symbol &quot;**&quot;.

   ![Screenshot mit der Option „Tabelleneinstellungen“](./assets/table-settings.png){width="35%"}

1. Aktivieren oder deaktivieren Sie die Option, um Zeilen- und Spaltenüberschriften anzuzeigen. Die Kopfzeilen werden standardmäßig angezeigt.

   **Dimensionskennzeichnungen und Metrikkopfzeilen ein- oder ausblenden**

1. Klicken Sie auf das Symbol mit den Auslassungspunkten entweder auf den Dimensionen oder auf den Spaltenüberschriften, um die Einstellungen anzuzeigen.

   ![Das Symbol mit den Auslassungspunkten im Zeilenabschnitt.](./assets/row-heading.png){width="35%"}

1. Klicken Sie auf Ausblenden oder Anzeigen , um die Dimensionsbeschriftungen oder Spaltenüberschriften umzuschalten. Alle Beschriftungen werden standardmäßig angezeigt.

1. Klicken Sie auf **Beenden**.

   Eine Verarbeitungsmeldung wird angezeigt, während die Analysedaten abgerufen werden.

   ![Die Verarbeitungsmeldung.](./assets/image11.png)

   Report Builder ruft die Daten ab und zeigt den abgeschlossenen Datenblock im Arbeitsblatt an.

   ![Der abgeschlossene Datenblock.](./assets/image12.png)
