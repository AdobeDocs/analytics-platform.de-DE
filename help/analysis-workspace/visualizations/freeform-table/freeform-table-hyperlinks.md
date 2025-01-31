---
title: Erstellen von Hyperlinks in einer Freiformtabelle
description: Erfahren Sie, wie Sie Hyperlinks für Dimensionselemente in einer Freiformtabelle in Analysis Workspace erstellen
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---

# Erstellen von Hyperlinks in einer Freiformtabelle

Sie können Hyperlinks für Dimensionselemente erstellen, um sie in einer Freiformtabelle in Analysis Workspace anklickbar zu machen.

Diese Funktion ist besonders beim Erstellen von Hyperlinks für die folgenden Arten von Dimensionselementen nützlich:

* Seitenelemente mit URL-Werten (z. B. die Dimension Dimensionen-URL ).

* Dimension-Elemente, die Aufschlüsselungen mit URL-Werten enthalten (z. B. eine Seitennamendimension mit einer Aufschlüsselung einer Seiten-URL-Dimension).

* Elemente oder Aufschlüsselungen einer Dimension, deren Werte Teil einer URL sind (z. B. eine Seitennamendimension, die Teil einer URL ist).


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Erstellen von Hyperlinks in einer Freiformtabelle](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"} für ein Demovideo.

>[!ENDSHADEBOX]


## Erstellen von Hyperlinks

Beachten Sie Folgendes, wenn Sie Hyperlinks für ein oder mehrere Dimensionselemente erstellen:

* Die von Ihnen erstellten Hyperlinks werden in der Freiformtabelle im Analysis Workspace-Projekt gespeichert. Hyperlinks bleiben nicht erhalten, wenn dieselbe Dimension oder Dimensionselemente in einer anderen Tabelle oder in einem anderen Projekt verwendet werden.

* Wenn Sie die Datenansicht der Freiformtabelle ändern, sind alle Hyperlinks, die für Dimensionen oder Dimensionselemente in der Tabelle erstellt wurden, weiterhin verfügbar. Bei dieser Funktion wird davon ausgegangen, dass die Dimension weiterhin in der Datenansicht vorhanden ist.

* URLs werden beim Erstellen des Hyperlinks nicht auf ihre Gültigkeit überprüft. Wenn Sie

   * einen Hyperlink mit einer ungültigen URL erstellen oder
   * Erstellen Sie einen Hyperlink, der auf ein Dimensionselement verweist, das keinen URL-Wert hat (indem Sie entweder direkt auf das Dimensionselement verweisen oder die Variablen `$value` oder `$breakdown` verwenden),

  dann wird Benutzern, die auf den Hyperlink klicken, eine Fehlermeldung angezeigt, die besagt, dass die URL ungültig ist.

* Hyperlinks, die für ein einzelnes Dimensionselement erstellt werden, überschreiben Hyperlinks, die für die Dimension erstellt werden.

* Hyperlinks funktionieren nicht in [heruntergeladenen PDF-](/help/analysis-workspace/export/download-send.md).

So erstellen Sie Hyperlinks für ein oder mehrere Dimensionselemente:

1. Führen Sie in einer Freiformtabelle in Analysis Workspace einen der folgenden Schritte aus:

   * **Erstellen eines Hyperlinks für ein einzelnes Dimensionselement:** Sie mit der rechten Maustaste auf das Dimensionselement in der Tabelle, für die Sie den Hyperlink erstellen möchten, und wählen Sie dann [!UICONTROL **Hyperlink erstellen**].

      1. Öffnen Sie das Kontextmenü für das Dimensionselement.
      1. Wählen [!UICONTROL **aus dem**] „Hyperlink erstellen“ aus.

         Das [!UICONTROL **Hyperlink erstellen**] wird angezeigt. Der Name des Dimensionselements, für das Sie einen Hyperlink erstellen, wird im Dialogfeld angezeigt.

         ![Erstellen eines Hyperlinks für ein Dialogfeld mit einem Element](assets/hyperlink-dialog-single.png)

   * **Erstellen von Hyperlinks für alle Dimensionselemente in einer Dimensionsspalte:** Klicken Sie mit der rechten Maustaste auf den Dimensionsnamen in der Spaltenüberschrift der Dimension und wählen Sie [!UICONTROL **Erstellen von Hyperlinks für alle Dimensionselemente**].

      1. Öffnen Sie das Kontextmenü über die Spaltenüberschrift der Dimension .
      1. Wählen Sie [!UICONTROL **Hyperlink für alle Dimensionselemente erstellen**] aus dem Kontextmenü aus.

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         Das [!UICONTROL **Erstellen von Hyperlinks für alle Dimensionselemente**] wird angezeigt. Der Name der Dimension, für die Sie Hyperlinks erstellen, wird im Dialogfeld angezeigt.

         ![Dialogfeld „Hyperlinks erstellen“](assets/hyperlink-dialog-multiple.png)

1. Wählen Sie aus den folgenden Optionen:

   * [!UICONTROL **Wert des Dimensionselements als URL verwenden**]: Wählen Sie diese Option für Dimensionselemente mit URL-Werten, wie z. B. die Dimension Seiten-URL .

     Wenn Sie beispielsweise eine Seiten-URL -Dimension verwenden, bei der der Wert jedes Dimensionselements eine URL ist, wird durch die Auswahl dieser Option ein Hyperlink zur URL erstellt.

   * [!UICONTROL **Erstellen einer benutzerdefinierten URL**]: Geben Sie entweder eine statische oder eine dynamische benutzerdefinierte URL an. Wählen Sie diese Option aus, um Hyperlinks für Dimensionselemente zu erstellen, die keine URL-Werte haben.

     Beispiel: Sie verwenden eine Dimension Seitenname , bei der der Wert jedes Dimensionselements der Name einer Seite (und keine vollständige URL) ist. Wählen Sie dann diese Option, um einen Hyperlink anzugeben, der als Link für das Dimensionselement verwendet werden soll.

     Wenn Sie dynamische URLs für mehrere Dimensionselemente erstellen möchten, können Sie die Variablen `$value` und `$breakdown` in Ihrer benutzerdefinierten URL verwenden. Weitere Informationen finden Sie in der Tabelle unten.

     Um eine benutzerdefinierte URL zu erstellen, geben Sie die folgenden Informationen an:

     | Feld | Beschreibung |
     |---------|----------|
     | [!UICONTROL **Benutzerdefinierte URL**] | Geben Sie eine benutzerdefinierte URL an, die Sie für den Hyperlink verwenden möchten. URLs müssen als vollständig qualifizierte URLs eingegeben werden. Beispiel: <https://www.example.com><p>Die von Ihnen erstellte benutzerdefinierte URL kann statisch oder dynamisch sein:</p> <ul><li>**Statische URLs:** Sie können eine statische URL für ein einzelnes Dimensionselement oder für alle Dimensionselemente angeben, wenn alle Elemente mit derselben URL verknüpft werden sollen. Beispiel: `https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**Dynamische URLs:** Sie können eine dynamische URL erstellen, wenn Sie eindeutige Hyperlinks für mehrere Dimensionselemente oder für alle Dimensionselemente in einer Dimensionsspalte erstellen möchten.<p>Um benutzerdefinierte URLs dynamisch zu gestalten, schließen Sie eine Variable in die URL ein, um die URL basierend auf dem Wert der Dimension oder dem Wert der Aufschlüsselungsdimension zu ändern.</p><p>Bei Verwendung von Variablen werden alle Dimensionselemente, die Zeichen enthalten, die in URLs ungültig sind (z. B. Leerzeichen), URL-kodiert.</p><p>Die folgenden Variablen sind verfügbar: (**Hinweis**: Sie können diese Variablen zwar in derselben URL verwenden, es ist jedoch üblicher, sie separat zu verwenden.)</p> <ul><li>**`$value`:** Ermöglicht Ihnen, den Wert des Dimensionselements in die von Ihnen angegebene URL einzufügen. <p>Angenommen, Sie möchten Hyperlinks für alle Dimensionselemente des Seitennamens in einer Freiformtabelle erstellen, wobei der Wert jedes Dimensionselements Teil der URL einer Web-Seite ist. In diesem Fall können Sie eine einzelne benutzerdefinierte URL erstellen, die sich für jedes Dimensionselement dynamisch anpasst. <br/>Beispiel: `https://company-name.com/browse/product#\$value`</p><p>Wenn diese benutzerdefinierte URL auf Dimensionselemente mit Seitennamen angewendet wird, deren Werte „ProductY“ und „ProductZ“ sind, sehen die generierten Hyperlinks wie folgt aus: <br/>`https://company-name.com/browse/product#ProductY` und<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![Verwenden von Werten in Hyperlinks](assets/table-hyperlinks-vaule.png)</p><p>**Tipp**: Wenn Sie dem Feld „Benutzerdefinierte URL“ nur die Variable &quot;`$value`&quot; hinzufügen, wird [!UICONTROL **Option „Wert des Dimensionselements verwenden**] beim Erstellen der URL ausgewählt.</p></li><li>**`$breakdown`:** Ermöglicht Ihnen, den Wert des Aufschlüsselungs-Dimensionselements in die von Ihnen angegebene URL einzufügen. Mit `$breakdown` können Sie eine Dimension mit einem benutzerfreundlichen Namen in Ihrem Bericht verwenden (z. B. eine Dimension „Produktname„). Und einen Hyperlink basierend auf einer Aufschlüsselungsdimension generieren, der möglicherweise weniger benutzerfreundlich ist (z. B. eine Produkt-ID oder Seiten-URL-Dimension).<p>Beim Referenzieren einer Aufschlüsselungsdimension ist es am häufigsten, nur ein Aufschlüsselungselement für ein bestimmtes Dimensionselement zu haben. Wenn für ein bestimmtes Dimensionselement mehrere Aufschlüsselungselemente vorhanden sind, wird der Wert des ersten Aufschlüsselungselements in der URL verwendet. Wenn keine Aufschlüsselungselemente aufgelistet sind, ist die URL ungültig. Auf die Aufschlüsselungselemente wird die gleiche Sortierreihenfolge angewendet wie auf die Tabelle.</p><p>Die Aufschlüsselungsdimension geben Sie im Feld [!UICONTROL **Aufschlüsselungsdimension**] unten an.</p> <p>Betrachten Sie das unten beschriebene Beispielszenario für das Feld [!UICONTROL **Aufschlüsselungsdimension**].</p></li></ul> |
     | [!UICONTROL **Aufschlüsselungsdimension (optional)**] | Geben Sie den Namen der Aufschlüsselungsdimension ein, die Sie verwenden möchten, und wählen Sie sie dann aus der Dropdown-Liste aus. <p>Wenn Sie eine Aufschlüsselungsdimension in diesem Feld auswählen, müssen Sie sie mithilfe der `$breakdown` in der URL referenzieren, die Sie im Feld [!UICONTROL **Benutzerdefinierte URL**] angeben.</p><p>Angenommen, Sie möchten Hyperlinks für alle Dimensionselemente des Produktnamens in einer Freiformtabelle erstellen. Jedes Dimensionselement Produktname enthält eine Aufschlüsselung einer Produkt-ID-Dimension.</p></p>In diesem Fall können Sie Hyperlinks für jede Dimension „Produktname“ erstellen, die Benutzer mithilfe des Werts der Dimension „Produkt-ID-Aufschlüsselung“ zur Produktseite weiterleitet. </p><p>Fügen Sie die Variable `$breakdown` am Ende der benutzerdefinierten URL hinzu, die Sie im Feld [!UICONTROL **Benutzerdefinierte URL**] angeben. z. B.:</p><p>`https://company-name.com/browse/product/$breakdown`</p>Wenn diese benutzerdefinierte URL auf die Dimensionselemente Ihres Produktnamens angewendet wird (die Aufschlüsselungs-Dimensionselemente haben, deren Werte „ProductY“ und „ProductZ“ sind), sehen die generierten Hyperlinks wie folgt aus:<br/>`https://company-name.com/browse/product/ProductY` und<br/>`https://company-name.com/browse/product/ProductZ`</p><p>Wählen Sie dann die Dimension Produkt-ID im Feld [!UICONTROL **Aufschlüsselungsdimension**] aus </p><p>![Aufschlüsselungen in Hyperlinks verwenden](assets/table-hyperlinks-breakdown.png)</p> |

1. Wählen Sie [!UICONTROL **Erstellen**] aus.

   Benutzer, die die Freiformtabelle anzeigen, sehen die mit Hyperlinks versehenen Dimensionselemente. Beim Klicken auf ein Dimensionselement werden die Benutzer in einer separaten Browser-Registerkarte zu den mit Hyperlinks versehenen Seiten weitergeleitet.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Speichern Sie das Projekt](/help/analysis-workspace/build-workspace-project/save-projects.md), um Ihre Änderungen zu speichern.

## Hyperlinks bearbeiten

Sie können Hyperlinks bearbeiten, die für Dimensionen oder Dimensionselemente in einer Freiformtabelle erstellt wurden.

1. Führen Sie in einer Freiformtabelle in Analysis Workspace einen der folgenden Schritte aus:

   * **Bearbeiten eines Hyperlinks für ein einzelnes Dimensionselement:**

      1. Öffnen Sie das Kontextmenü für das Dimensionselement.
      1. Wählen [!UICONTROL **Hyperlink bearbeiten**] aus dem Kontextmenü aus.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **Hyperlinks für alle Dimensionselemente in einer Dimensionsspalte bearbeiten:**

      1. Öffnen Sie das Kontextmenü über die Spaltenüberschrift der Dimension .
      1. Wählen Sie **[!UICONTROL Hyperlink für alle Dimensionselemente bearbeiten]** aus dem Kontextmenü aus.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. Wählen [!UICONTROL **Hyperlinks für alle Dimensionselemente bearbeiten**] aus dem Kontextmenü aus.

   Das [!UICONTROL **„Hyperlinks für Dimensionselemente bearbeiten**] wird angezeigt.

1. Weitere Informationen zu den Konfigurationsoptionen für die Bearbeitung des Hyperlinks finden Sie in Schritt 3 im Abschnitt [Erstellen von Hyperlinks für ein oder mehrere Dimensionselemente](#create-hyperlinks-for-one-or-more-dimension-items) und wählen Sie dann [!UICONTROL **Anwenden**] aus, wenn Sie mit Ihren Aktualisierungen fertig sind.

1. [Speichern Sie das Projekt](/help/analysis-workspace/build-workspace-project/save-projects.md), um Ihre Änderungen zu speichern.

## Entfernen von Hyperlinks

Sie können Hyperlinks entfernen, die für Dimensionselemente in einer Freiformtabelle erstellt wurden.

>[!NOTE]
>
>Wenn Sie in einer Freiformtabelle eine Dimension löschen, die Hyperlinks enthält, bleiben die Hyperlinks nicht erhalten, wenn Sie dieselbe Dimension wieder zur Freiformtabelle hinzufügen.

So entfernen Sie Hyperlinks aus Dimensionselementen:

1. Führen Sie in einer Freiformtabelle in Analysis Workspace einen der folgenden Schritte aus:

   * **Entfernen eines Hyperlinks aus einem einzelnen Dimensionselement:**

      1. Öffnen Sie das Kontextmenü für das Dimensionselement.
      1. Wählen [!UICONTROL **Hyperlink entfernen**] aus dem Kontextmenü aus.
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **Entfernen von Hyperlinks aus allen Dimensionselementen in einer Dimensionsspalte:**

      1. Öffnen Sie das Kontextmenü über die Spaltenüberschrift der Dimension .
      1. Wählen Sie **[!UICONTROL Hyperlink für alle Dimensionselemente entfernen]** aus dem Kontextmenü aus.

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   Der Hyperlink wird aus dem einzelnen Dimensionselement entfernt, wenn Sie ein einzelnes Dimensionselement ausgewählt haben. Oder aus allen Dimensionselementen, wenn Sie den Dimensionsnamen in der Spaltenüberschrift der Dimension ausgewählt haben.

1. [Speichern Sie das Projekt](/help/analysis-workspace/build-workspace-project/save-projects.md), um Ihre Änderungen zu speichern.
