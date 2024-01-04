---
description: Sie können Daten von Analysis Workspace durch Kopieren oder in PDF- und CSV-Formaten herunterladen.
title: Customer Journey Analytics-Daten herunterladen
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 55%

---

# Customer Journey Analytics-Daten herunterladen

Sie können Customer Journey Analytics-Daten auf Ihre Workstation herunterladen. Dies kann in Form von kopierten Daten, CSV oder PDF erfolgen. Eine PDF wird normalerweise bevorzugt, wenn Sie in der heruntergeladenen Datei enthaltene Visualisierungen verwenden möchten. CSV- und kopierte Daten werden bevorzugt, wenn Sie einfach Textdaten verwenden möchten.

Es stehen auch andere Methoden zum Exportieren von Customer Journey Analytics-Daten zur Verfügung, wie unter [Exportübersicht](/help/analysis-workspace/export/export-project-overview.md).

## Als CSV oder PDF herunterladen {#download-project}

1. Führen Sie je nach dem Format, in dem der Download erfolgen soll, einen der folgenden Schritte aus:

   * **PDF:** Auswählen **[!UICONTROL Projekt]** > **[!UICONTROL PDF herunterladen]**.

     Wählen Sie diese Option aus, wenn die heruntergeladene Datei alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt enthalten soll.

   * **CSV:** Auswählen **[!UICONTROL Projekt]** > **[!UICONTROL CSV herunterladen]**.

     Wählen Sie diese Option aus, wenn die heruntergeladene Datei Text enthalten soll.

   ![Das Dropdown-Menü Projekt mit den Optionen CSV herunterladen und PDF herunterladen hervorgehoben.](assets/download-project.png)

1. (Bedingt) Wenn Sie sich für den Download einer PDF entschieden haben, wird eine Nachricht angezeigt, nachdem das Projekt heruntergeladen werden kann. Wählen Sie [!UICONTROL **Herunterladen**] aus.

Beachten Sie beim Herunterladen von Projekten Folgendes:

* Die Anforderung von Projekt-Downloads kann mit oder ohne Speicherung eines Projekts erfolgen.  Es können jedoch nur gespeicherte Projekte [geplant](/help/analysis-workspace/export/t-schedule-report.md) sein.
* Der Export von im Browser heruntergeladenen PDF-Dateien kann mehrere Minuten dauern, da das Projekt auf den Adobe-Servern erneut ausgeführt wird, bevor es im PDF-Format ausgegeben wird. Wir empfehlen, das Projekt nicht zu verlassen, bis die PDF-Datei in Ihren Browser heruntergeladen wurde. Sie können jedoch beim Warten weiterhin Änderungen am Projekt vornehmen. Wenn die Ausgabe einer PDF-Datei länger als 5 Minuten dauert, werden Sie aufgefordert, diese stattdessen per E-Mail zu erhalten.
* PDF-Downloads werden als einzelne Seite ohne Seitenumbruch gerendert.
* Bei der PDF-Ausgabe eines Projekts wird das gerendert, was sich auf der Seite befindet. Wenn ein Projekt Visualisierungen und Bedienfelder in benutzerdefinierter Größe enthält, müssen Sie diese so ändern, dass die Größe automatisch bestimmt wird (Schaltfläche in der oberen rechten Ecke), damit der Inhalt nicht abgeschnitten wird.

## In die Zwischenablage kopieren (Hotkey: Strg+C) {#copy-data}

Die Rechtsklickoption **[!UICONTROL In Zwischenablage kopieren]** ermöglicht Ihnen das schnelle Kopieren von Customer Journey Analytics-Daten aus Workspace und das Einfügen dieser Daten in ein Tool eines Drittanbieters.

* Wenn die angezeigte Tabelle kopiert werden soll, klicken Sie mit der rechten Maustaste auf die Tabellenüberschrift und wählen Sie **Daten in die Zwischenablage kopieren**.
* Wenn Sie möchten, dass nur ein Teil der Daten kopiert wird, wählen Sie die Tabelle aus, und klicken Sie dann mit der rechten Maustaste auf **Auswahl in Zwischenablage kopieren**.

>[!TIP]
>
>Sie können den Hotkey verwenden `Ctrl+C` , um Ihre Auswahl in die Zwischenablage zu kopieren, und verwenden Sie `Ctrl+V` , um es in ein Tool eines Drittanbieters einzufügen.


![Die Option Auswahl in Zwischenablage kopieren ](assets/copy-selection.png)

## Als CSV herunterladen {#download-data}

Die Rechtsklickoption **[!UICONTROL Daten als CSV herunterladen]** ermöglicht Ihnen, eine Tabelle mit Customer Journey Analytics-Daten oder die Datenquelle einer beliebigen Visualisierung als CSV-Datei herunterzuladen.

* Klicken Sie in der Kopfzeile einer beliebigen Tabelle oder Visualisierung mit der rechten Maustaste auf und wählen Sie **[!UICONTROL Daten als CSV herunterladen]**. Dadurch werden die angezeigten Customer Journey Analytics-Daten in der Tabelle oder der zugrunde liegenden Datenquelle für eine Visualisierung als CSV heruntergeladen.

  >[!NOTE]
  >
  >  Hinweis: Diese Option wird von der Map-Visualisierung nicht unterstützt.


* Klicken Sie in einer Tabelle mit der rechten Maustaste und wählen Sie **[!UICONTROL Auswahl als CSV herunterladen]**. Mit dieser Option wird nur die Auswahl heruntergeladen, nicht die vollständige, angezeigte Tabelle.

![Die Option Daten als CSV herunterladen .](assets/download-data-viz.png)

## Objekte als CSV herunterladen {#download-items}

Wenn Sie mehr als die sichtbaren 400 Datenzeilen in einer Tabelle analysieren möchten, klicken Sie mit der rechten Maustaste auf die Tabellenüberschrift oder eine beliebige Zeile und wählen Sie **Elemente als CSV herunterladen (_Name der Dimension_)**. Diese Option exportiert bis zu 50.000 Dimensionselemente (basierend auf der Tabellensortierung) für die ausgewählte Dimension, wobei Sortieroptionen und Filter angewendet werden. Wenn Sie diese Option oben in der Tabelle auswählen, wird die erste Dimension in der Tabelle exportiert. Obwohl in Freiformtabellen keine Beschränkungen gelten, wird empfohlen, die Option zum Herunterladen von Elementen in Tabellen mit weniger als 20 Spalten zu verwenden, um optimale Leistung sicherzustellen.

>[!TIP]
>
> Wenn Ihre Dimension 50.000 Elemente überschreitet, laden Sie die Datei mit unterschiedlichen Sortierkriterien herunter oder wenden Sie einen Filter an. Sortieren Sie z. B. absteigend nach Besuchen in einem Download und dann aufsteigend nach Besuchen in einem zweiten Download. Dieser Tipp hilft Ihnen beim Abrufen von längeren Elementen.

Während eines Downloads können Sie mehrere Aufgaben im Projekt ausführen und sogar zu einem neuen Workspace-Projekt auf derselben Registerkarte navigieren. Der Download wird angehalten, wenn Sie eine neue Browser-Registerkarte öffnen. Der Download wird abgebrochen, wenn Sie Workspace vollständig verlassen oder die Browser-Registerkarte schließen.

![Die Option Elemente als CSV (Seite) herunterladen .](assets/download-items.png)

### Datei mit heruntergeladenen Elementen {#items-file}

Die Eigenschaften der Tabelle werden wie folgt auf die heruntergeladene Datei angewendet:

* Alle Bedienfeldfilter werden als Filter angewendet.
* Aufschlüsselungen **oberhalb** der ausgewählten Dimension in der Tabelle werden als Filter über jeder einzelnen Spalte angezeigt.
* Aufschlüsselungen **unterhalb** der ausgewählten Dimension in der Tabelle werden entfernt.

Im obigen Beispiel werden Seitenelemente mit dem Bedienfeldfilter („Neue Besucher-Kunden“) heruntergeladen und die darüber liegenden Komponenten („Marketing-Kanal = E-Mail“) als Filter angewendet, während die darunter liegenden Komponenten („Typ des Mobilgeräts“) aus der heruntergeladenen CSV-Datei entfernt werden.

![Die heruntergeladene CSV-Datei wurde in Excel geöffnet.](assets/downloaded-file.png)

### Download-Benachrichtigungen {#notifications}

Beim Herunterladen der Datei wird eine Benachrichtigung mit dem Fortschritt angezeigt. Sie können den Download jederzeit abbrechen, indem Sie auf **[!UICONTROL Download abbrechen]** klicken. Durch Schließen des Popups wird der Download **nicht** abgebrochen.

Sobald die Datei abgeschlossen ist, wird eine Benachrichtigung angezeigt und die Datei wird in Ihren Browser heruntergeladen.

Wenn Sie mehrere Downloads gleichzeitig anfordern, erhalten Sie eine Benachrichtigung, dass jeder weitere Download in die Warteschlange gestellt wird, bis der vorherige Download abgeschlossen ist.

![Die Benachrichtigung zum Download-Status, die den Prozentsatz der Fertigstellung und den Link Download abbrechen anzeigt.](assets/toast.png)

## Herunterladen sensibler Daten {#sensitive}

Wenn die Variable **[!UICONTROL Download durchsetzen]** [Data Governance-Politik](/help/data-views/data-governance.md) in der Datenansicht aktiviert ist, über die Sie Berichte erstellen, werden bei jedem Download von Workspace-Projekten (z. B. per E-Mail oder PDF) die als vertraulich gekennzeichneten Datenfelder gehasht. Sie können diese Felder in Workspace weiterhin analysieren, aber wenn Sie versuchen, ein Projekt per E-Mail zu versenden oder anderweitig freizugeben, werden die blockierten Felder in der .pdf- oder .csv-Datei als leer angezeigt.

## Häufig gestellte Fragen {#faq}

| Frage | Antwort |
| --- | --- |
| Warum besteht meine heruntergeladene PDF-Datei aus einer Seite? | In Workspace werden heruntergeladene PDFs derzeit nicht in Seiten unterteilt. |
| Kann ich über die Option &quot;Elemente als CSV herunterladen&quot;mehr als 50.000 Elemente exportieren? | Während jeder Download bis zu 50.000 Dimensionselemente enthalten kann, können Sie die Sortierung der Tabelle ändern, um längere Elemente abzurufen, oder einen Filter anwenden, um spezifischere Elemente herunterzuladen. |
| Beschreibung der Funktion **[!UICONTROL Visualisierung kopieren]** | Unlike [!UICONTROL **Daten in die Zwischenablage kopieren**] oder [!UICONTROL **Auswahl in Zwischenablage kopieren**], die **[!UICONTROL Visualisierung kopieren]** Rechtsklick ist keine Exportoption. Damit können Sie eine Visualisierung oder ein Bedienfeld von einem Bereich in Workspace in einen anderen kopieren. Beispielsweise von einem Bedienfeld in ein anderes im selben Projekt oder von einem Projekt in ein anderes. [Intra-linking-Video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=de) |
