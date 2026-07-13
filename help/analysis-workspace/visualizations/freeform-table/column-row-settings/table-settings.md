---
description: Erfahren Sie, wie Sie Zeileneinstellungen verwenden und wie Zeileneinstellungen je nachdem, welche Komponente Sie in Analysis Workspace in eine Freiformtabelle gezogen haben, variieren.
title: Zeileneinstellungen
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
hold: true
TQID: https://experienceleague.adobe.com/qQKmobJ4J1RPezRG-hk38l7JNioIshzjMaKXWVoUWsM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 5da7d5ec554e61244e839fb1affebc0be9ecb109
workflow-type: tm+mt
source-wordcount: 1596
ht-degree: 56%

---

# Zeileneinstellungen

Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben. Um auf die Einstellungen der Tabellenzeilen zuzugreifen![&#x200B; wählen Sie &#x200B;](/help/assets/icons/Setting.svg)Einstellung **[!UICONTROL Einstellungen]** neben einer Dimension, einem Segment, einer Metrik, einem Zeitraum oder einer Aufschlüsselung in jedem dieser Objekte aus.

![Freiformtabelle mit hervorgehobenem Einstellungssymbol für Metriken](assets/row-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| **[!UICONTROL Aufschlüsselung nach Position:]** | Standardmäßig ist diese Einstellung deaktiviert und die Aufschlüsselungen sind auf statische Zeilenelemente festgelegt. Angenommen, Sie schlüsseln die drei oberen Elemente der Dimension „Seite“ (Startseite, Suchergebnisse, Checkout) nach Marketing-Kanälen auf. Dann verlassen Sie das Projekt und kehren zwei Wochen später zurück. Beim erneuten Öffnen des Projekts haben sich die drei oberen Seiten geändert, und jetzt sind Startseite, Suchergebnisse und Checkout stattdessen die oberen Seiten vier bis sechs. Standardmäßig werden Ihre Aufschlüsselungen des Marketing-Kanals weiterhin unter Startseite, Suchergebnisse und Checkout angezeigt, obwohl sie sich jetzt in den Zeilen 4 bis 6 befinden. <br> Im Gegensatz dazu werden **Aufschlüsselung nach Position** immer die drei obersten Elemente aufgeschlüsselt, unabhängig davon, was sie sind. Wenn Sie auf das Beispiel zurückgreifen, werden die Aufschlüsselungen des Marketing-Kanals beim erneuten Öffnen des Projekts an die drei obersten Seiten der Tabelle gebunden. Und nicht an „Startseite“, „Suchergebnisse“ und „Checkout“, die sich jetzt in den Zeilen 4–6 befinden. |
| **[!UICONTROL Prozentsätze]** | **Prozentsätze nach Spalte berechnen** (Standard): Die in einer Spalte sichtbaren Prozentsätze werden auf der Grundlage der Spaltensumme berechnet. <br>**Prozentsätze nach Zeile berechnen**: Die Prozentsätze in Zellen werden über die Zeile anstatt für die Spalte berechnet. Dabei ist die Gesamtsumme der Nenner. Diese Berechnung ist nützlich für die Trend-Darstellung von Prozentsätzen. |
| **[!UICONTROL Spaltensummen]** | Diese Einstellungen sind nur für [statische Zeilen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verfügbar. <br> **Als Summe der aktuellen Zeilen anzeigen**: Zeigt eine Client-seitige Summe der Zeilen in der Tabelle, was bedeutet, dass bei der Gesamtsumme die Metriken wie „Besuche“ oder „Personen“ *nicht* dedupliziert werden. <br> **Gesamtsumme anzeigen**: Zeigt eine Server-seitige Summe an, d. h. die Gesamtsumme der deduplizierten Metriken. |

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Zeilen- und Spalteneinstellungen in einer Freiformtabelle](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/row-and-column-settings-in-freeform-tables){target="_blank"} finden Sie ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]

## Ändern der Zeilenanzahl

So ändern Sie die Anzahl der angezeigten Zeilen:

1. Klicken Sie auf die Zahl neben **[!UICONTROL Zeilen]** oberhalb der ersten Spalte der Tabelle.

   ![Freiformtabelle mit dem Dropdown-Menü von für die Anzahl der angezeigten Zeilen. „400 Zeilen“ ist ausgewählt.](assets/change-row-count.gif)

1. Wählen Sie aus dem Dropdown-Menü die Anzahl der Zeilen aus, die die Tabelle anzeigen soll.


## Kontextmenü

Die folgenden Kontextmenüoptionen sind bei der Auswahl der Dimensionskopfzeile verfügbar.

| Option | Beschreibung |
| --- | --- |
| **[!UICONTROL Auswahl in Zwischenablage kopieren]** | Zum Kopieren der Auswahl aus der Visualisierung in die Zwischenablage. |
| **[!UICONTROL Objekte als CSV herunterladen (*Dimensionsname*)]** | Zum sofortigen Herunterladen der Dimensionselemente (bis zu maximal 50.000) der Visualisierung auf Ihr lokales Gerät. Maximal 50.000 Dimensionselemente für die ausgewählte Dimension. |
| **[!UICONTROL Auswahl als CSV herunterladen]** | Zum sofortigen Herunterladen der Dimensionselemente der Visualisierung auf Ihr lokales Gerät. |
| **[!UICONTROL Hyperlink für alle Dimensionselemente erstellen]** | Zum Erstellen von Hyperlinks für alle Dimensionselemente. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink für alle Dimensionselemente bearbeiten]** | Zum Bearbeiten von Hyperlinks für alle Dimensionselemente. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink für alle Dimensionselemente entfernen]** | Zum Entfernen von Hyperlinks für alle Dimensionselemente. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Löschen]** | Löscht die Dimension aus der Tabelle. |
| **[!UICONTROL Visualisieren]** | Zum Visualisieren der Dimension mithilfe einer der verfügbaren Visualisierungen. |
| **[!UICONTROL Nur ausgewählte Zeilen anzeigen]** | Zum Anzeigen von nur den ausgewählten Elementen in der Visualisierung. |
| **[!UICONTROL Anmerkung aus Auswahl erstellen]** | Zum Öffnen der **[!UICONTROL Anmerkungsdetails]**, um eine Anmerkung hinzuzufügen. |


Die folgenden zusätzlichen Optionen im Kontextmenü sind verfügbar, wenn ein oder mehrere Dimensionselemente (erste Spalte) oder eine oder mehrere einzelne Zellen in der Freiformtabelle ausgewählt werden.

| Option | Beschreibung |
| --- | --- |
| **[!UICONTROL Auswahl in Zwischenablage kopieren]** | Kopieren Sie die Informationen in die ausgewählten Zellen der Freiformtabelle. |
| **[!UICONTROL Objekte als CSV herunterladen (*Dimensionsname*)]** | Zum sofortigen Herunterladen der Dimensionselemente (bis zu maximal 50.000) der Visualisierung auf Ihr lokales Gerät. Maximal 50.000 Dimensionselemente für die ausgewählte Dimension. |
| **[!UICONTROL Hyperlink erstellen]** | Zum Erstellen eines Hyperlinks für das Element. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink bearbeiten]** | Zum Bearbeiten eines Hyperlinks für das Element. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Hyperlink entfernen]** | Zum Entfernen eines Hyperlinks für das Element. Siehe [Hyperlinks für Dimensionen in einer Freiformtabelle](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Auswahl als CSV herunterladen]** | Zum sofortigen Herunterladen der Dimensionselemente der Visualisierung auf Ihr lokales Gerät. |
| **[!UICONTROL Auswahl löschen]** | Ausgewählte Zeilen löschen. |
| **[!UICONTROL Warnhinweis aus Auswahl erstellen]** | Öffnen Sie die [Warnhinweiserstellung](/help/components/c-intelligent-alerts/alert-builder.md), um einen Warnhinweis aus der Auswahl zu erstellen. |
| **[!UICONTROL Aufschlüsselung]** | Zum Aufschlüsseln des Dimensionselements. Wählen Sie aus der Liste **[!UICONTROL Dimensionen]**, **[!UICONTROL Metriken]**, **[!UICONTROL Segmente]** oder **[!UICONTROL Datumsbereiche]**. Suchen Sie alternativ mit *Suchen* nach einer Komponente. |
| **[!UICONTROL Visualisieren]** | Visualisieren Sie die Auswahl mithilfe einer der verfügbaren Visualisierungen. |
| **[!UICONTROL Trend-Auswahl]** | Zum Erstellen einer Trend-Liniendiagramm-Visualisierung für die Auswahl. |
| **[!UICONTROL Nur ausgewählte Zeilen anzeigen]** | Zum Anzeigen von nur den ausgewählten Zeilen in der Visualisierung. |
| **[!UICONTROL Alle Zeilen anzeigen]** | Zum Anzeigen aller Zeilen in der Visualisierung. |
| **[!UICONTROL Ausgewählte Zeile umbenennen]** | Benennen Sie die ausgewählte Zeile um. Geben Sie **[!UICONTROL Dialogfeld]** Ausgewählte Zeile **[!UICONTROL umbenennen]** einen Namen ein. Wählen Sie **[!UICONTROL OK]**, um zu bestätigen, oder **[!UICONTROL Abbrechen]**, um abzubrechen. Nachdem eine Zeile in einer Freiformtabelle umbenannt wurde, wird der Dimensionsname in der Kopfzeile mit **[!UICONTROL (geändert)]** angehängt und ein ![Zahnradsymbol](/help/assets/icons/Gear.svg) ist verfügbar, um umbenannte Zeilen in der Kopfzeile der Dimension zurückzusetzen. Siehe [Inline-Klassifizierungsbeispiel](#inline-classifications-example). |
| **[!UICONTROL Ausgewählte Zeilen kombinieren]** | Die ausgewählten Zeilen kombinieren. Geben Sie **[!UICONTROL Dialogfeld]** Ausgewählte Zeilen **[!UICONTROL kombinieren]** einen Namen ein. Wählen Sie **[!UICONTROL OK]**, um zu bestätigen, oder **[!UICONTROL Abbrechen]**, um abzubrechen. Sobald Zeilen in einer Freiformtabelle kombiniert sind, wird der Dimensionsname in der Kopfzeile mit **[!UICONTROL (geändert) angehängt]** und ein ![Zahnradsymbol](/help/assets/icons/Gear.svg) ist verfügbar, um umbenannte Zeilen in der Kopfzeile der Dimension zurückzusetzen. Siehe [Inline-Klassifizierungsbeispiel](#inline-classifications-example). |
| **[!UICONTROL Als abgeleitetes Feld erstellen]** | *Sie müssen Customer Journey Analytics-Produktadministrator sein, um diese Option im Kontextmenü anzuzeigen.*<br/> Verfügbar in jeder ausgewählten Zeile einer Freiformtabelle, die durch das Umbenennen oder Kombinieren von Zeilen geändert wird. Wenn diese Option ausgewählt ist[&#x200B; wird die &#x200B;](/help/data-views/derived-fields/derived-fields.md#create-a-derived-field) „Abgeleitetes Feld“ mit den Änderungen geöffnet, die Sie an der bereits vorausgefüllten Freiformtabelle vorgenommen haben. Siehe [Inline-Klassifizierungsbeispiel](#inline-classifications-example). |
| **[!UICONTROL Anmerkung aus Auswahl erstellen]** | Öffnen Sie den [Anmerkungsgenerator](/help/components/annotations/create-annotations.md#annotation-builder), um eine Anmerkung für die Auswahl zu erstellen. |
| **[!UICONTROL Segment aus Auswahl erstellen]** | Öffnen Sie den [Segment Builder](/help/components/segments/seg-builder.md), um ein Segment aus der Auswahl zu erstellen. |
| **[!UICONTROL Zielgruppe aus Auswahl erstellen]** | Öffnen Sie den [Audience Builder](/help/components/audiences/publish.md#audience-builder), um eine Audience aus der Auswahl zu erstellen. |

Die folgenden Kontextmenüoptionen sind bei Auswahl der Kopfzeile einer Metrikspalte verfügbar.

| Option | Beschreibung |
|---|---|
| **[!UICONTROL Metrik aus Auswahl erstellen]** | Zum Erstellen einer neuen Metrik aus der ausgewählten Metrik. Die Metrik kann „Arithmetisches Mittel“, „Medien“, „Spaltenmaximum“, „Spaltenminimum“ oder „Spaltensumme“ sein. Sie können auch „Öffnen“ im Generator für berechnete Metriken auswählen, um eine berechnete Metrik zu erstellen. |
| **[!UICONTROL Spalte mit Zeitraum hinzufügen]** | Zum Hinzufügen einer Zeitraumspalte. Es werden mehrere Optionen angeboten, wobei der Kalenderbereich des Bedienfelds den *Datumsbereich* festlegt: <ul><li>**[!UICONTROL Früherer *Datumsbereich* vor diesem Datumsbereich]**</li><li>**[!UICONTROL Dieser *Datumsbereich* vor diesem Datumsbereich]**.</li><li>**[!UICONTROL Benutzerdefinierter Datumsbereich vor diesem Datumsbereich]**. Öffnet den **[!UICONTROL Datumsbereichsgenerator]**, um den Datumsbereich anzugeben.</li></ul>Weitere Informationen finden Sie unter [Datumsvergleich](/help/components/date-ranges/time-comparison.md). |
| **[!UICONTROL Zeiträume vergleichen]** | Zum Hinzufügen von Zeitraumspalten. Nur verfügbar, wenn die Dimension nicht auf der Zeit basiert. Es werden mehrere Optionen angeboten, die den *Datumsbereich* festlegen: <ul><li>**[!UICONTROL Früherer *Datumsbereich* vor diesem Datumsbereich]**</li><li>**[!UICONTROL Benutzerdefinierter Datumsbereich vor diesem Datumsbereich]**. Öffnet den **[!UICONTROL Datumsbereichsgenerator]**, um den Datumsbereich anzugeben.</li></ul>Weitere Informationen finden Sie unter [Datumsvergleich](/help/components/date-ranges/time-comparison.md). |
| **[!UICONTROL Attributionsmodelle ändern]** | Zum Ändern des Attributionsmodells für die Spalte. |
| **[!UICONTROL Attributionsmodell vergleichen]** | Geben Sie ein neues Attributionsmodell an und vergleichen Sie es mit dem Attributionsmodell für die ausgewählte Spalte. Es wird eine neue Spalte mit den neuen Attributionsmodell-Metriken hinzugefügt. Außerdem wird eine Spalte „Prozentänderung“ zum Vergleich hinzugefügt. |
| **[!UICONTROL Spaltenbreiten zurücksetzen]** | Zum Zurücksetzen der Spaltenbreiten auf die Standardbreite. |
| **[!UICONTROL Anmerkung aus Auswahl erstellen]** | Zum Öffnen der **[!UICONTROL Anmerkungsdetails]**, um eine Anmerkung hinzuzufügen. |
| **[!UICONTROL Segment aus Auswahl erstellen]** | Öffnen Sie den **[!UICONTROL Segment Builder]**, um ein Segment aus der Auswahl zu erstellen. |
| **[!UICONTROL Zielgruppe aus Auswahl erstellen]** | Öffnen Sie das Dialogfeld **[!UICONTROL Zielgruppe erstellen]**, um eine Zielgruppe aus der Auswahl zu erstellen. |


## Ändern der Zeilenhöhe

Sie können die [Anzeigedichte](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/view-density) eines Projekts auf **[!UICONTROL Kompakt]**, **[!UICONTROL Komfortabel]** und **[!UICONTROL Erweitert]**.


## Beispiel für Inline-Klassifizierungen

Dieses Beispiel zeigt, wie die Kontextmenüoptionen **[!UICONTROL Ausgewählte Zeile umbenennen]**, **[!UICONTROL Ausgewählte Zeilen kombinieren]** und **[!UICONTROL Als abgeleitetes Feld erstellen]** verwendet werden. und wie die geänderte Freiformtabelle zurückgesetzt wird.

* Benennen **[!UICONTROL Kein Wert]** Zeile in **[!UICONTROL Andere]** um.

   1. Wählen Sie **[!UICONTROL Ausgewählte Zeile umbenennen]** aus dem Kontextmenü in der ausgewählten Zeile **[!UICONTROL Kein Wert]** aus.

      ![Wählen Sie die Kontextmenüoption Ausgewählte Zeile umbenennen &#x200B;](assets/context-rename.png)

   1. Im Dialogfeld **[!UICONTROL Ausgewählte Zeile umbenennen]**:

      ![Dialogfeld „Ausgewählte Zeile umbenennen](assets/dialog-rename.png)

      1. Enter <code>other</code> für **[!UICONTROL Name]**.
      1. Klicken Sie **[!UICONTROL OK]**.

* Kombinieren Sie **[!UICONTROL Männer]** und **[!UICONTROL Frauen]** Zeilen zu einer **[!UICONTROL Erwachsene]** Zeile.

   1. Wählen Sie **[!UICONTROL Männer]** und **[!UICONTROL Frauen]** Zeile aus.
   1. Wählen Sie **[!UICONTROL Ausgewählte Zeilen kombinieren]** aus dem Kontextmenü aus einer der ausgewählten Zeilen aus.

      ![Menüoption „Ausgewählte Zeilen kombinieren“](assets/context-combine.png)

   1. Im Dialogfeld **[!UICONTROL Ausgewählte Zeilen kombinieren]**:

      ![Dialogfeld „Ausgewählte Zeile kombinieren](assets/dialog-combine.png)

      1. Eintreten <code>Erwachsene</code> für **[!UICONTROL Name]**.
      1. Klicken Sie **[!UICONTROL OK]**.

* Erstellen Sie ein abgeleitetes Feld aus den Änderungen in der Freiformtabelle.

   1. Wählen Sie **[!UICONTROL Als abgeleitetes Feld erstellen]** aus dem Kontextmenü für eine beliebige Zeile in der geänderten Tabelle aus.

      ![Wählen Sie die Menüoption Als abgeleitetes Feld erstellen &#x200B;](assets/context-derived.png)

   1. Überprüfen Sie die Definition des abgeleiteten Felds, ändern Sie sie optional und speichern Sie sie basierend auf allen Änderungen in der Tabelle.

      ![Dialogfeld „Abgeleitetes Feld erstellen“](assets/dialog-derived.png)

* Setzen Sie die Freiformtabelle auf den Status vor den Änderungen zurück.

   1. Klicken Sie ![Zahnrad](/help/assets/icons/Gear.svg) neben **[!UICONTROL _Dimensionsname _(geändert)]**.
   1. Wählen Sie **[!UICONTROL Umbenannte Zeilen zurücksetzen]** aus dem **[!UICONTROL Umbenannte Zeilen]**-Popup.

      ![Freiformtabelle zurücksetzen](assets/popup-reset.png)

