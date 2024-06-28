---
title: Erstellen von Hyperlinks in einer Freiformtabelle in Analysis Workspace
description: Erfahren Sie, wie Sie Hyperlinks für Dimensionselemente in einer Freiformtabelle in Analysis Workspace erstellen.
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: 8941b6a8339294cf121a07ca0c14bac50342d04e
workflow-type: tm+mt
source-wordcount: '1736'
ht-degree: 1%

---

# Erstellen von Hyperlinks für Dimensionen in einer Freiformtabelle

Sie können Hyperlinks für Dimensionselemente erstellen, damit sie in einer Freiformtabelle in Analysis Workspace angeklickt werden können.

Diese Funktion ist besonders beim Erstellen von Hyperlinks für die folgenden Arten von Dimensionselementen nützlich:

* Dimensionen mit URL-Werten, mit denen Sie eine Verknüpfung herstellen möchten (z. B. eine Seite-URL-Dimension)

* Dimension von Elementen, die Aufschlüsselungen mit URL-Werten enthalten, mit denen Sie eine Verknüpfung herstellen möchten (z. B. eine Dimension &quot;Seitenname&quot;, die eine Aufschlüsselung der Dimension &quot;Seiten-URL&quot;aufweist)

* Dimension von Elementen oder Aufschlüsselungen mit Werten, die Teil einer URL sind, mit der Sie eine Verknüpfung herstellen möchten (z. B. eine Dimension &quot;Seitenname&quot;, die Teil einer URL ist)

+++ Sehen Sie sich eine Videodemonstration zu dieser Funktion an.

>[!VIDEO](https://video.tv.adobe.com/v/3430411/?learn=on)

+++

## Erstellen von Hyperlinks für ein oder mehrere Dimensionselemente

Beachten Sie beim Erstellen von Hyperlinks für Dimensionselemente Folgendes:

* Die von Ihnen erstellten Hyperlinks werden in der Freiformtabelle im Analysis Workspace-Projekt gespeichert. Hyperlinks bleiben nicht bestehen, wenn Sie dieselbe Dimension oder dieselben Dimensionselemente in einer anderen Tabelle oder in einem anderen Projekt verwenden.

* Wenn Sie die Datenansicht der Freiformtabelle ändern, sind alle Hyperlinks, die für Dimensionen oder Dimensionselemente in der Tabelle erstellt wurden, weiterhin verfügbar, sofern die Dimension in der Datenansicht vorhanden ist.

* URLs werden beim Erstellen des Hyperlinks nicht auf ihre Gültigkeit überprüft.

  Wenn Sie einen Hyperlink mit einer ungültigen URL erstellen oder einen Hyperlink erstellen, der auf ein Dimensionselement verweist, das keinen URL-Wert aufweist (indem Sie entweder direkt auf das Dimensionselement verweisen oder die `$value` oder `$breakdown` -Variablen), wird Benutzern, die auf den Hyperlink klicken, eine Fehlermeldung angezeigt, dass die URL ungültig ist.

* Hyperlinks, die für ein einzelnes Dimensionselement erstellt werden, überschreiben Hyperlinks, die für die Dimension erstellt werden.

* Hyperlinks funktionieren nicht in [heruntergeladene PDF-Dateien](/help/analysis-workspace/export/download-send.md).

So erstellen Sie Hyperlinks für ein oder mehrere Dimensionselemente:

1. Führen Sie in einer Freiformtabelle in Analysis Workspace einen der folgenden Schritte aus:

   * **Erstellen Sie einen Hyperlink für ein einzelnes Dimensionselement:** Klicken Sie mit der rechten Maustaste auf das Dimensionselement in der Tabelle, für die Sie den Hyperlink erstellen möchten, und wählen Sie [!UICONTROL **Hyperlink erstellen**].

     ![Erstellen eines Hyperlinks für ein einzelnes Dimensionselement](assets/hyperlink-single-add.png)

     Die [!UICONTROL **Hyperlink erstellen**] angezeigt. Der Name des Dimensionselements, für das Sie einen Hyperlink erstellen, wird im Dialogfeld angezeigt.

     ![Erstellen eines Hyperlinks für ein Dialogfeld mit einem einzelnen Element](assets/hyperlink-dialog-single.png)

   * **Erstellen Sie Hyperlinks für alle Dimensionselemente in einer Dimensionsspalte:** Klicken Sie mit der rechten Maustaste auf den Dimensionsnamen in der Spaltenüberschrift der Dimension und wählen Sie [!UICONTROL **Erstellen von Hyperlinks für alle Dimensionselemente**].

     ![Erstellen eines Hyperlinks für eine Dimension](assets/hyperlink-multiple-add.png)

     Die [!UICONTROL **Erstellen von Hyperlinks für alle Dimensionselemente**] angezeigt. Der Name der Dimension, für die Sie Hyperlinks erstellen, wird im Dialogfeld angezeigt.

     ![Dialogfeld &quot;Hyperlinks erstellen&quot;](assets/hyperlink-dialog-multiple.png)

1. Wählen Sie aus den folgenden Optionen:

   * [!UICONTROL **Den Wert des Dimensionselements als URL verwenden**]: Wählen Sie diese Option für Dimensionselemente mit URL-Werten, wie z. B. die Dimension Seiten-URL .

     Wenn Sie beispielsweise die Dimension &quot;Seiten-URL&quot;verwenden, bei der der Wert jedes Dimensionselements eine URL ist, wird bei Auswahl dieser Option ein Hyperlink zur URL erstellt.

   * [!UICONTROL **Benutzerdefinierte URL erstellen**]: Geben Sie entweder eine statische oder eine dynamische benutzerdefinierte URL an. Wählen Sie diese Option, um Hyperlinks für Dimensionselemente zu erstellen, die keine URL-Werte haben.

     Wenn Sie beispielsweise die Dimension &quot;Seitenname&quot;verwenden, bei der der Wert jedes Dimensionselements der Name einer Seite ist (und keine vollständige URL), können Sie bei Auswahl dieser Option einen Hyperlink angeben, der als Link für das Dimensionselement verwendet werden soll.

     Wenn Sie dynamische URLs für mehrere Dimensionselemente erstellen möchten, können Sie die `$value` und `$breakdown` Variablen innerhalb Ihrer benutzerdefinierten URL. Weitere Informationen finden Sie in der unten stehenden Tabelle.

     Geben Sie die folgenden Informationen an, um eine benutzerdefinierte URL zu erstellen:

     | Feld | Beschreibung |
     |---------|----------|
     | [!UICONTROL **Benutzerspezifische URL**] | Geben Sie eine benutzerdefinierte URL an, die Sie für den Hyperlink verwenden möchten. URLs müssen als vollständig qualifizierte URLs eingegeben werden. Beispiel: <https://www.example.com><p>Die von Ihnen erstellte benutzerdefinierte URL kann statisch oder dynamisch sein:</p> <ul><li>**Statische URLs:** Wenn Sie einen Hyperlink für ein einzelnes Dimensionselement erstellen, kann eine statische URL ausreichen. <p>Betrachten Sie das folgende Beispiel: Wenn Sie beispielsweise über ein Dimensionselement &quot;Seitenname&quot;verfügen, können Sie eine statische URL erstellen, die Benutzer mit der spezifischen Webseite verknüpft, die Sie mit dem Seitennamen verknüpfen möchten.</p><p>Angenommen, Sie möchten Hyperlinks für eine Liste von Dimensionselementen erstellen, von denen jede innerhalb einer internen Wiki-Seite mit der entsprechenden Definition in der Dokumentation verknüpft ist.</p><p>Sie können dies erreichen, indem Sie für jedes Dimensionselement eine statische URL erstellen. Zum Beispiel:</p><p>https://wiki.internal.company_name/page_name#item_definition</p></li><li>**Dynamische URLs** Wenn Sie einen Hyperlink für mehrere Dimensionselemente oder für alle Dimensionselemente in einer Dimensionsspalte erstellen, ist eine dynamische URL wahrscheinlich praktischer. <p>Damit benutzerdefinierte URLs dynamisch sind, fügen Sie Variablen in die URL ein, die eine dynamische Änderung der URL ermöglichen, basierend auf dem Wert der Dimension selbst oder dem Wert der Aufschlüsselungsdimension.</p><p>Bei Verwendung von Variablen werden alle Dimensionselemente, die Zeichen enthalten, die in URLs nicht gültig sind (z. B. Leerzeichen), URL-kodiert.</p><p>Die folgenden Variablen sind verfügbar: (**Hinweis**: Sie können diese Variablen zwar in derselben URL verwenden, es ist jedoch wahrscheinlich häufiger, sie separat zu verwenden.)</p> <ul><li>**`$value`:** Fügt den Wert des Dimensionselements in die von Ihnen angegebene URL ein. <p>Betrachten Sie das folgende Szenario als Beispiel:</p><p>Angenommen, Sie möchten Hyperlinks für alle Dimensionselemente &quot;Seitenname&quot;in einer Freiformtabelle erstellen, wobei der Wert jedes Dimensionselements Teil der URL einer Webseite ist. In diesem Fall können Sie eine einzelne benutzerdefinierte URL erstellen, die sich dynamisch für jedes Dimensionselement anpasst. </p><p>Fügen Sie dazu die `$value` an das Ende der von Ihnen angegebenen benutzerdefinierten URL. Zum Beispiel:</p> <p>https://company-name.com/browse/product#\$value</p><p>Wenn diese benutzerdefinierte URL auf die Dimensionselemente für den Seitennamen angewendet wird, deren Werte &quot;ProductY&quot;und &quot;ProductZ&quot;sind, würden die generierten Hyperlinks ungefähr so aussehen: </p><p>https://company-name.com/browse/product#ProductY</p><p>und</p><p> https://company-name.com/browse/product#ProductZ </p><p>![Werte in Hyperlinks verwenden](assets/table-hyperlinks-vaule.png)</p><p>**Tipp**: Wenn Sie nur die `$value` in das Feld &quot;Benutzerdefinierte URL&quot;eingeben, entspricht dies der Auswahl der [!UICONTROL **Wert des Dimensionselements verwenden**] bei der Erstellung der URL.</p></li><li>**`$breakdown`:** Fügt den Wert des Aufschlüsselungsdimensionselements in die von Ihnen angegebene URL ein. Auf diese Weise können Sie eine Dimension mit einem benutzerfreundlichen Namen in Ihrem Bericht (z. B. die Dimension &quot;Produktname&quot;) verwenden, während Sie den Hyperlink basierend auf einer Aufschlüsselungsdimension erstellen, die möglicherweise weniger benutzerfreundlich ist (z. B. Dimension &quot;Produkt-ID&quot;oder &quot;Seiten-URL&quot;).<p>Beim Referenzieren einer Aufschlüsselungsdimension ist es am häufigsten, nur ein Aufschlüsselungselement für ein bestimmtes Dimensionselement zu verwenden. Wenn für ein bestimmtes Dimensionselement mehrere Aufschlüsselungselemente vorhanden sind, wird der Wert des ersten Aufschlüsselungselements in der URL verwendet. Wenn keine Aufschlüsselungselemente aufgelistet sind, ist die URL ungültig. Dieselbe Sortierreihenfolge wird auf die Aufschlüsselungselemente angewendet, die auf die Tabelle angewendet werden.</p><p>Sie legen die Aufschlüsselungsdimension im [!UICONTROL **Aufschlüsselungsdimension**] unten.</p> <p>Betrachten Sie das Beispielszenario für [!UICONTROL **Aufschlüsselungsdimension**] unten.</p></li></ul> |
     | [!UICONTROL **Aufschlüsselungsdimension (optional)**] | Beginnen Sie mit der Eingabe des Namens der Aufschlüsselungsdimension, die Sie verwenden möchten, und wählen Sie sie dann aus der Dropdownliste aus. <p>Wenn Sie in diesem Feld eine Aufschlüsselungsdimension auswählen, müssen Sie diese mithilfe der `$breakdown` in der URL, die Sie in der Variablen [!UICONTROL **Benutzerspezifische URL**] -Feld.</p><p>Betrachten Sie das folgende Szenario als Beispiel:</p><p>Angenommen, Sie möchten Hyperlinks für alle Dimensionselemente &quot;Produktname&quot;in einer Freiformtabelle erstellen. Jedes Dimensionselement &quot;Produktname&quot;enthält eine Aufschlüsselung der Dimension Produkt-ID .</p></p>In diesem Fall können Sie Hyperlinks für jede Dimension &quot;Produktname&quot;erstellen, die Benutzer mithilfe des Wertes der Aufschlüsselungsdimension &quot;Produkt-ID&quot;zur Produktseite weiterleitet. </p><p>Fügen Sie dazu die `$breakdown` an das Ende der benutzerdefinierten URL, die Sie in der Variablen [!UICONTROL **Benutzerspezifische URL**] -Feld. Zum Beispiel:</p><p>https://company-name.com/browse/product/$breakdown</p><p>Wenn diese benutzerdefinierte URL auf Ihre Dimensionselemente für Produktnamen mit Aufschlüsselungsdimensionen angewendet wird, deren Werte &quot;ProductY&quot;und &quot;ProductZ&quot;sind, würden die generierten Hyperlinks ungefähr so aussehen:</p><p>https://company-name.com/browse/product/ProductY</p><p>und</p><p>https://company-name.com/browse/product/ProductZ</p><p>Wählen Sie dann die Dimension Produkt-ID im [!UICONTROL **Aufschlüsselungsdimension**] field </p><p>![Aufschlüsselungen in Hyperlinks verwenden](assets/table-hyperlinks-breakdown.png)</p> |

1. Wählen Sie [!UICONTROL **Erstellen**] aus.

   Benutzer, die die Freiformtabelle anzeigen, sehen die per Hyperlink verbundenen Dimensionselemente. Beim Klicken auf ein Dimensionselement werden die Benutzer in einer separaten Browser-Registerkarte zu den per Hyperlink verbundenen Seiten geleitet.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Projekt speichern](/help/analysis-workspace/build-workspace-project/save-projects.md) , um Ihre Änderungen zu speichern.

## Hyperlinks bearbeiten

Sie können Hyperlinks bearbeiten, die für Dimensionen oder Dimensionselemente in einer Freiformtabelle erstellt wurden.

1. Führen Sie in einer Freiformtabelle in Analysis Workspace einen der folgenden Schritte aus:

   * **Bearbeiten Sie einen Hyperlink für ein einzelnes Dimensionselement:** Klicken Sie mit der rechten Maustaste auf das Dimensionselement in der Tabelle, in der Sie den Hyperlink bearbeiten möchten.

     ![Hyperlink für ein einzelnes Dimensionselement bearbeiten](assets/hyperlink-single-edit.png)

   * **Bearbeiten Sie Hyperlinks für alle Dimensionselemente in einer Dimensionsspalte:** Klicken Sie mit der rechten Maustaste auf den Dimensionsnamen in der Dimensionsspaltenüberschrift.

     ![Hyperlink für eine Dimension bearbeiten](assets/hyperlink-dimension-edit.png)

1. Auswählen [!UICONTROL **Hyperlink bearbeiten**] über das Kontextmenü.

   Die [!UICONTROL **Hyperlinks für Dimensionselemente bearbeiten**] angezeigt.

1. Informationen zu den Konfigurationsoptionen für die Bearbeitung des Hyperlinks finden Sie in Schritt 3 im Abschnitt [Erstellen von Hyperlinks für ein oder mehrere Dimensionselemente](#create-hyperlinks-for-one-or-more-dimension-items) Abschnitt weiter oben und wählen Sie dann [!UICONTROL **Anwenden**] wenn Sie mit Ihren Aktualisierungen fertig sind.

1. [Projekt speichern](/help/analysis-workspace/build-workspace-project/save-projects.md) , um Ihre Änderungen zu speichern.

## Hyperlinks entfernen

Sie können Hyperlinks entfernen, die für Dimensionselemente in einer Freiformtabelle erstellt wurden.

>[!NOTE]
>
>Wenn Sie in einer Freiformtabelle eine Dimension löschen, die Hyperlinks enthält, bleiben die Hyperlinks nicht erhalten, wenn Sie dieselbe Dimension wieder zur Freiformtabelle hinzufügen.

So entfernen Sie Hyperlinks aus Dimensionselementen:

1. Führen Sie in einer Freiformtabelle in Analysis Workspace einen der folgenden Schritte aus:

   * **Entfernen Sie einen Hyperlink aus einem einzelnen Dimensionselement:** Klicken Sie mit der rechten Maustaste auf das Dimensionselement in der Tabelle, in der Sie den Hyperlink entfernen möchten.

     ![Entfernen von Hyperlinks aus einem einzelnen Dimensionselement](assets/hyperlink-single-remove.png)

   * **Entfernen Sie Hyperlinks aus allen Dimensionselementen in einer Dimensionsspalte:** Klicken Sie mit der rechten Maustaste auf den Dimensionsnamen in der Dimensionsspaltenüberschrift.

     ![Entfernen von Hyperlinks aus Dimensionen](assets/hyperlink-dimension-remove.png)

1. Auswählen [!UICONTROL **Hyperlink entfernen**] über das Kontextmenü.

   Der Hyperlink wird aus dem einzelnen Dimensionselement (wenn Sie ein einzelnes Dimensionselement ausgewählt haben) oder aus allen Dimensionselementen entfernt (wenn Sie den Dimensionsnamen in der Dimensionsspaltenüberschrift ausgewählt haben).

1. [Projekt speichern](/help/analysis-workspace/build-workspace-project/save-projects.md) , um Ihre Änderungen zu speichern.
