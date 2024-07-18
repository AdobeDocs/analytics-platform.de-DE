---
description: Erfahren Sie, wie Sie die Touchpoints angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen.
title: Fallout-Visualisierung konfigurieren
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 67%

---

# Fallout-Visualisierung konfigurieren

Sie können die Touchpoints angeben, um eine mehrdimensionale Fallout-Sequenz zu erstellen. Ein Touchpoint ist im Allgemeinen eine Seite auf Ihrer Website. Touchpoints sind jedoch nicht auf Webseiten eingeschränkt. Sie können beispielsweise Ereignisse wie Einheiten sowie Unique Users und Wiederkehrbesuche hinzufügen. Auch Dimensionen können Sie hinzufügen (wie Kategorie, Browsertyp oder interner Suchbegriff).

Sie können sogar Filter innerhalb eines Touchpoints hinzufügen. Vielleicht möchten Sie zum Beispiel Filter vergleichen, etwa iOS- und Android-Benutzer. Wenn Sie die gewünschten Filter per Drag-and-Drop an den oberen Rand des Fallouts ziehen, werden Informationen über diese Filter zum Fallout-Bericht hinzugefügt. Wenn Sie möchten, dass nur diese Filter angezeigt werden, können Sie die Grundlinie „Alle Besuche“ entfernen.

Bezüglich der Anzahl der Schritte, die hinzugefügt, oder der Dimensionen, die verwendet werden können, gibt es keine Einschränkungen.

Sie können Pathing an eVars vornehmen, einschließlich Merchandising-eVars und [listVars](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=de) (Variablen, die mehrere Werte pro Ereignis haben können, wie Produkte, listVars, Merchandising-eVars und Listen-Props). Beispiel: Angenommen, jemand sucht auf der einen Seite nach „Schuhe, Shirt“ und auf der nächsten Seite nach „Schuhe, Socken“. Der nächste Produktflussbericht von Schuhe wird „Shirt und Socken“ lauten, NICHT „Shirt“.

1. Ziehen Sie eine [!UICONTROL Fallout]-Visualisierung aus dem Dropdownfeld „Visualisierung“ in eine [!UICONTROL Freiformtabelle].

1. Ziehen Sie die Dimension „Seite“ in die Freiformtabelle und ziehen Sie von dort eine Seite (in diesem Fall „Startseite – JJEsquire“) als ersten Touchpoint in das Feld **[!UICONTROL Touchpoint hinzufügen]**.

   ![Die Dropdown-Liste Alle Besuche mit JJEsquire wurde in das Feld Touchpoint hinzufügen gezogen.](assets/fallout1.png)

   Bewegen Sie den Mauszeiger über einen Touchpoint, um den Fallout und andere Informationen zu dieser Ebene anzuzeigen, z. B. den Namen des Touchpoints, die Anzahl der Personen an diesem Punkt und die Erfolgsrate für diesen Touchpoint (sowie den Vergleich der Erfolgsrate mit anderen Touchpoints).

   Die umkreisten Zahlen im grauen Abschnitt der Leiste zeigen den Fallout zwischen Touchpoints an (nicht den gesamten Fallout bis zu diesem Punkt). Der Touchpoint-Prozentsatz zeigt den erfolgreichen Fall-through vom vorherigen Schritt zum aktuellen Schritt im Fallout-Bericht an.

   Sie können auch eine einzelne Seite anstatt der gesamten Dimension zum Fallout-Bericht hinzufügen. Klicken Sie auf den rechten Pfeil „>“ auf der Seitendimension, um die Seite auszuwählen, die Sie zum Fallout-Bericht hinzufügen möchten.

1. Fügen Sie weitere Touchpoints hinzu, bis Ihre Sequenz vollständig ist.

   Sie können **mehrere Touchpoints kombinieren**, indem Sie mindestens einen weiteren Touchpoint auf einen Touchpoint ziehen.

   >[!NOTE]
   >
   >Hinweis: Mehrere Segmente werden mit AND verbunden, mehrere Elemente wie Dimensionselemente und Metriken hingegen mit OR.

   ![Die Seiten:CamerRoll oder Seite: Kamera-Touchpoints hervorgehoben.](assets/multiple_obj_touchpoint.png)

1. Sie können einzelne Touchpoints auch auf das nächste Ereignis **(im Gegensatz zu &quot;am Ende&quot;) im Pfad beschränken.** Jedem Touchpoint unterliegen die Auswahlmöglichkeiten „Pfad am Ende“ und „Nächster Hit“:

   ![Die Ansicht &quot;Alle Besuche&quot;mit der Option &quot;Pfad am Ende&quot;wurde hervorgehoben. ](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pfad am Ende </p> <p>(Standard) </p> </td> 
   <td colname="col2"> <p>Besucher werden gezählt, die "am Ende"auf der nächsten Seite im Pfad landen, aber nicht notwendigerweise beim nächsten Ereignis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nächster Treffer </p> </td> 
   <td colname="col2"> <p>Besucher werden gezählt, die auf der nächsten Seite im Pfad des nächsten Ereignisses landen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fallout-Einstellungen {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Einstellung | Beschreibung |
|--- |--- |
| Fallout-Container <ul><li>Besuch</li><li>Besucher</li></ul> | Ermöglicht Ihnen den Wechsel zwischen Besuch und Besucher zur Analyse der Personenpfade. Die Standardeinstellung lautet „Besucher“.  Mithilfe dieser Einstellungen können Sie die Interaktion der Person auf der Personenebene (besuchsübergreifend) nachvollziehen oder die Analyse auf einen einzelnen Besuch beschränken. |

Wenn Sie **mit der rechten Maustaste auf einen Touchpoint klicken**, werden die folgenden Optionen angezeigt:

| Option | Beschreibung |
|--- |--- |
| Trend-Touchpoint | Zeigt Trenddaten für einen Touchpoint in einem Kantengraphen mit einigen vorab definierten Anomalieerkennungsdaten an. |
| Trend-Touchpoint (%) | Trends für den gesamten Fallout-Prozentsatz. |
| Trenderstellung aller Touchpoints (%) | Trends für alle Touchpoint-Prozentsätze im Fallout (außer „Alle Besuche“, falls vorhanden) im selben Diagramm. |
| Aufschlüsselung des Fallthrough an diesem Touchpoint | Sehen Sie sich an, welche Personen zwischen zwei Touchpoints (diesem Touchpoint und dem nächsten Touchpoint) ausgeführt haben, wenn sie zum nächsten Touchpoint übergegangen sind. Diese Option erstellt eine Freiformtabelle, die Ihre Dimensionen enthält. Dimensionen und andere Elemente der Tabelle können Sie austauschen. |
| Aufschlüsselung des Fallout an diesem Touchpoint | Zeigt an, was Besucher, die nicht im Trichter verblieben sind, unmittelbar nach dem ausgewählten Schritt getan haben. |
| Erstellen eines Filters aus einem Touchpoint | Erstellen Sie einen neuen Filter aus dem ausgewählten Touchpoint. |
