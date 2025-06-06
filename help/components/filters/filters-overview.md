---
title: Überblick über die Segmentierung
description: Erfahren Sie, wofür Segmente verwendet werden und wie Sie ein einfaches Segment erstellen.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: d0268ce9ba22228c5c42d600c173f39cd1001638
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 100%

---


# Überblick über die Segmentierung

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppensegmente für Ihre Berichte erstellen, verwalten, freigeben und anwenden. Mit Segmenten können Sie Teilmengen von Personen, Sitzungen oder Ereignissen anhand von Merkmalen oder Interaktionen identifizieren. Segmente sind als kodifizierte Zielgruppenerkenntnisse konzipiert, die Sie für Ihre speziellen Anforderungen erstellen und dann überprüfen, bearbeiten und für andere Team-Mitglieder freigeben können.

Segmente können auf Folgendem basieren:

- Attributen (Browser-Typ, Gerät, Anzahl der Besuche, Land, Geschlecht),
- Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine),
- Ausstiegen und Eintritten (Personen aus Facebook, einer definierten Landingpage, Referrer Domain, Geofence-Ereignis),
- benutzerdefinierten Variablen (Formularfeld, definierten Kategorien, Kunden-ID),
- und anderen Kriterien.

Unter [Erstellen von Segmenten](/help/components/filters/create-filters.md) finden Sie eine Beschreibung der verschiedenen zum Erstellen von Segmenten verfügbaren Optionen. Anschließend erstellen, ändern und speichern Sie die Definition eines Segments im [Segment Builder](filter-builder.md). Alternativ können Sie Schnellsegmente mit dem [Schnellsegment-Builder](quick-filters.md) erstellen. Außerdem können Sie Segmente auch aus Visualisierungen in Workspace generieren, z. B. mithilfe der Visualisierung [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Segmente verwalten Sie wiederum über den [Segment-Manager](manage-filters.md).

## Planen von Segmenten

Insbesondere für Admins verbessert die ordnungsgemäße Planung von Segmenten die Wahrscheinlichkeit, dass die Segmente verwendet werden. Beachten Sie beim Plan von Segmenten Folgendes:

- **Zielgruppe**: Wer wird Ihre Segmente verwenden? Achten Sie darauf, eine gute Segmentbeschreibung anzugeben, damit die Zielgruppe Folgendes versteht:
   - Wofür ist dieses Segment nützlich?

   - Wann sollte dieses Segment benutzt werden?

- **Umfang**: Welcher [Segment-Container](#segment-containers) repräsentiert die gewünschten Daten am besten? Benutzen Sie den kleinstmöglichen Container.

- **Komponenten**: Entscheiden Sie, welche Komponenten in die Segmentdefinition aufgenommen werden sollen und anhand welcher Werte die Bedingungen validiert werden sollen.

- **Prozess**: Ziehen Sie einen Genehmigungsprozess für Ihre Segmente in Betracht. In Customer Journey Analytics gibt es keinen Genehmigungs-Workflow. Sie können aber trotzdem einen Prozess organisieren, um zu bestimmen, ob Sie ein Segment genehmigen oder nicht.

- **Modularität**: Definieren Sie Segmente unter Berücksichtigung der Modularität. Die Benutzenden Ihrer Segmente sollten in der Lage sein, [Segmente einfach zu stapeln](filter-builder.md#stack-filters), um leistungsstarke neue Segmente zu erstellen.


## Segmenttypen

Sie können drei Typen von Segmenten erstellen:

### Schnellsegmente

Schnellsegmente ermöglichen es Ihnen, Daten innerhalb eines bestimmten Workspace-Projekts einfach zu untersuchen, ohne ein Segment im [Segment Builder](/help/components/filters/create-filters.md) erstellen zu müssen. Sie definieren Ihr Segment direkt in der Workspace-Benutzeroberfläche. Weitere Informationen finden Sie unter [Schnellsegmente](quick-filters.md).

### Reguläre Segmente

Mit regulären Segmenten können Sie Daten (Personen, Sitzungen, Ereignisse) anhand einer oder mehrerer Bedingungen identifizieren. Liegt mehr als eine Bedingung vor, verwenden Sie logische Operatoren wie „Und“ und „Oder“, um das Segment weiter zu definieren. Sie können Container verwenden, um Bedingungen zu gruppieren und komplexere Segmente zu erstellen. Weitere Informationen finden Sie unter [Segment Builder](filter-builder.md).

### Sequenzielle Segmente

>[!IMPORTANT]
>
>Sie müssen über das **Select**-Paket verfügen, um kanalübergreifende sequenzielle Segmente zu erstellen. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Mit sequenziellen Segmenten können Sie Daten (Personen, Sitzungen, Ereignisse) anhand der Navigation (Seitenansichten auf Ihrer Site, Interaktionen mit Szenen in Ihrer App oder Verwendung eines Menüs in einer Set-Top-Box) identifizieren. Durch sequenzielle Segmente können Sie beispielsweise erkennen, was einer Person gefällt und was sie meidet. Sie verwenden den logischen Operator „Dann“, um ein sequenzielles Segment zu definieren. Weitere Informationen finden Sie unter [Sequenzielle Segmente](seg-sequential-build.md).


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Segment-Container {#containers}

Segmente basieren auf einer Hierarchie auf Personen-, Sitzungs- und Ereignisebene und verwenden ein verschachteltes Container-Modell. Mit verschachtelten Containern können Sie Bedingungen zwischen und innerhalb der Container definieren.


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Person</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sitzung</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Ereignis</td>
</tr>
</table>

>[!NOTE]
>
>Für Adobe Analytics-Benutzende:
> 
> - Der Container **Person** wird in Adobe Analytics als Container vom Typ **Besucherin bzw. Besucher** bezeichnet.
> - Der Container **Sitzung** wird in Adobe Analytics als Container vom Typ **Besuch** bezeichnet.
> - Der Container **Ereignis** wird in Adobe Analytics als Container vom Typ **Treffer** bezeichnet.
>

Ein Segment legt Bedingungen fest, um Personen, Sitzungen oder Ereignisse basierend auf Bedingungen zu segmentieren. Bedingungen zum Segmentieren von Personen basieren beispielsweise auf Personenmerkmalen und Navigationseigenschaften. Um die Daten weiter aufzuschlüsseln, können Sie bestimmte Sitzungen, Seitenansichtsereignisse, Tipp-Gesten auf Bildschirmen, Menüoptionen in einer Set-top-Box usw. segmentieren. Sie können auch nach Attributen segmentieren, die Sie aus einem CRM- oder Treuesystem aufgenommen haben. Der [Segment Builder](/help/components/filters/filter-builder.md) bietet eine einfache Benutzeroberfläche zum Erstellen dieser Untergruppen und zum Anwenden von Bedingungen in verschachtelten hierarchische Personen-, Sitzungs- oder Ereignis-Containern.

Die im [Segment Builder](/help/components/filters/filter-builder.md) verwendete Container-Architektur definiert „Person“ als den äußersten Container. Dieser Container enthält übergreifende Daten, die für die Person über Sitzungen und Ereignisse wie Seitenansichten, Bildschirme für Apps oder Menübildschirme in einer Set-top-Box hinweg spezifisch sind. Mit dem verschachtelten Container „Sitzung“ können Sie Regeln festlegen, um die Personendaten auf der Grundlage von Sitzungen aufzuschlüsseln. Mit dem verschachtelten Container „Ereignis“ können Sie Informationen zu Personen auf Grundlage einzelner Interaktionen aufschlüsseln. Jeder Container ermöglicht Berichte über den Verlauf einer Person, nach Sitzung aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container

Der Container „Person“ enthält sämtliche Sitzungen und Ereignisse für Personen, die sich für die im Container angegebene Bedingung qualifizieren. Wenn Sie ein Segment mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Container „Person“ zu Folgendem aufgelöst:

- Allen Personen, die die Seite mit dem Namen `Checkout` besucht haben
- Allen Sitzungen für diese Personen
- Allen Ereignisdaten für diese Personen

Da es sich um den am breitesten definierten Container handelt, liefern Berichte, die auf der Ebene des Besucher-Containers erstellt werden, Ereignisse und Sitzungen über alle Personen hinweg, die sich für das Segment qualifizieren. Der Personen-Container ändert sich auf der Grundlage der definierten Datumsbereiche am wahrscheinlichsten.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf einer Person basieren:

- Tage bis Erstkauf
- Ursprüngliche Einstiegsseite oder Startbildschirm der App
- Ursprüngliche Referrer Domains

### Sitzungs-Container

Mit dem Container „Sitzung“ können Seiteninteraktionen oder Interkationen mit der App, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden. Der Container „Besuch“ ist der am häufigsten verwendete Container, da er das Verhalten für die gesamte Sssitzung erfasst, sobald die Regel erfüllt ist. Mit dem Container „Sitzung“ können Sie außerdem definieren, welche Sitzungen beim Erstellen und Anwenden eines Segments ein- oder ausgeschlossen werden sollen.  Wenn Sie ein Segment mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Container „Sitzung“ zu aufgelöst:

- Allen Sitzungen, in denen eine Seite mit dem Namen `Checkout` besucht wird
- Allen Ereignisdaten für diese Sitzungen

Der Container „Sitzung“ kann Ihnen bei der Beantwortung der folgenden Fragen helfen:

- Wie viele Sitzungen umfassten sowohl Web- als auch Callcenter-Datenquellen?
- Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf den Ereignissen pro Sitzung basieren:

- Sitzungstyp
- Einstiegsseite
- Rückkehrhäufigkeit
- Beitragsmetriken
- Linear zugeordnete Metriken

Mit Datenansichten in Customer Journey Analytics können Sie festlegen, wie lange eine Sitzung dauert, aber auch, wann eine neue Sitzung erstellt werden soll. Sie können beispielsweise eine neue App-Sitzung basierend auf jedem App-Start einer Benutzerin oder eines Benutzers definieren. Weitere Informationen finden Sie unter [Sitzungseinstellungen](/help/data-views/session-settings.md). 

### Ereignis-Container

Der Ereignis-Container definiert, welche Seiten-, App- oder anderen Ereignisse in einem Segment eingeschlossen oder davon ausgeschlossen werden sollen. Er ist der engste verfügbare Container. Damit können Sie bestimmte Klicks, Seitenansichten und Tippvorgänge auf eine Schaltfläche in einer App identifizieren, wenn eine Bedingung erfüllt ist. Mit dem Ereignis-Container können Sie einen einzelnen Trackingcode anzeigen oder das Verhalten innerhalb eines bestimmten Bereichs Ihrer App isolieren. Sie können auch einen bestimmten Wert erkennen, wenn eine Aktion stattfindet, z. B. den Marketing-Kanal, wenn etwas bestellt wurde. Wenn Sie ein Segment mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Ereignis-Container zu Folgendem aufgelöst:

- Allen Seitenansichtsereignissen, bei denen der Seitenname `Checkout` entspricht

Ereignis-Container enthalten wertbasierte Aufschlüsselungen einzelner Seiten für:

- Produkte
- Listen-Props
- Listendimensionen
- Merchandising-Dimensionen (im Kontext von Ereignissen)



### B2B-Container

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Wenn Sie Zugriff auf die [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md) haben, stehen zusätzliche Container zur Verwendung in Segmenten zur Verfügung. Weitere Informationen zum Verwenden dieser zusätzlichen Container finden Sie unter [B2B-Konzepte und -Funktionen](/help/getting-started/cja-b2b-concepts-features.md).


### Container „Logische Gruppe“

„Logische Gruppe“ ermöglicht es Ihnen, Bedingungen in einem einzigen sequenziellen Segment-Checkpoint zu gruppieren. Als Teil der Sequenz wird die Logik, die in dem Container [!UICONTROL Logische Gruppe] definiert ist, nach einem vorherigen sequenziellen Checkpoint und vor einem nachfolgenden sequenziellen Checkpoint ausgewertet. Weitere Informationen finden Sie unter [Logische Gruppe](seg-sequential-build.md#logic-group).

### Verschachteln von Containern

Wenn Sie Container innerhalb anderer Container erstellen, erstellen Sie tatsächlich ein Segment in einem Segment. Auf verschachtelte Container wird die folgende Logik angewendet:

1. Bestimmen, welche Daten enthalten sind, indem der äußerste Container verwendet wird. Alle Daten, die nicht mit dieser „äußeren“ Regel übereinstimmen, werden aus dem Bericht ausgeschlossen.
2. Anwenden der verschachtelten Segmentdefinition auf die verbleibenden Daten. Die verschachtelte Segmentdefinition gilt NICHT für Daten, die im Rahmen der ersten Definition verworfen wurden.
3. Wiederholen, bis alle verschachtelten Container-Segmentdefinitionen berechnet wurden. Die verbleibenden Daten werden dann in das Ergebnis eingeschlossen und für das Reporting verwendet.

>[!NOTE]
>
>Wenn Sie ein Segment innerhalb eines Segments verschachteln (Sie ziehen beispielsweise ein Segment aus dem Panel „Komponenten“ auf Ihre Segmentdefinition), wird ein Container mit einer Kopie (nicht mit einer Referenz) der gezogenen Segmentdefinition erstellt.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Erstellen von Segmenten](create-filters.md)
>>[Segment Builder](filter-builder.md)
>>[Schnellsegmente](quick-filters.md)
>>[Sequenzielle Segmente](seg-sequential-build.md)
>>[Verwalten von Segmenten](manage-filters.md)
>
