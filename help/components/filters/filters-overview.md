---
title: Filterübersicht
description: Erfahren Sie, wofür Filter verwendet werden und wie Sie einen einfachen Filter erstellen.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 5fbb228fc02304be2246f0b49cb49de7f160b227
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# Filterübersicht

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppenfilter für Ihre Berichte erstellen, verwalten, freigeben und anwenden. Mit Filtern können Sie Untergruppen von Personen, Sitzungen oder Ereignissen anhand von Merkmalen oder Interaktionen identifizieren. Filter sind als kodifizierte Zielgruppeneinblicke konzipiert, die Sie für Ihre speziellen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Team-Mitgliedern austauschen können.

Filter können auf Folgendem basieren:

- Attribute (Browsertyp, Gerät, Anzahl Besuche, Land, Geschlecht),
- Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine),
- Ausstiege und Einstiege (Personen aus Facebook, eine definierte Landingpage, Referrer-Domäne, Geofence-Ereignis),
- benutzerdefinierte Variablen (Formularfeld, definierte Kategorien, Kunden-ID),
- und anderen Kriterien.

Unter [Filter erstellen](/help/components/filters/create-filters.md) finden Sie die verschiedenen Optionen zum Erstellen von Filtern. Anschließend erstellen, ändern und speichern Sie die Definition eines Filters im [Filter-Builder](filter-builder.md). Alternativ können Sie mit dem Filter [Schnellfilter-Aufzähler](quick-filters.md) Schnellfilter erstellen. Sie können auch Filter aus Visualisierungen in Workspace generieren, z. B. mithilfe der Visualisierung [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) .

Sie verwenden den [Filter-Manager](manage-filters.md) zum Verwalten von Filtern.

## Filter planen

Insbesondere als Administrator verbessert die ordnungsgemäße Filterplanung die Wahrscheinlichkeit, dass die Filter verwendet werden. Beachten Sie bei der Filterplanung Folgendes:

- **Zielgruppe**: Wer wird Ihre Filter verwenden? Stellen Sie sicher, dass Sie eine gute Filterbeschreibung bereitstellen, damit die Zielgruppe Folgendes versteht:
   - Wofür ist dieser Filter nützlich?

   - Wann sollte dieser Filter benutzt werden?

- **Umfang**: Welcher [Filter-Container](#filter-containers) stellt die Daten, nach denen Sie suchen, am besten dar? Benutzen Sie den kleinstmöglichen Container.

- **Komponenten**: Entscheiden Sie, welche Komponenten in die Filterdefinition aufgenommen werden sollen und anhand welcher Werte die Bedingungen validieren sollen.

- **Prozess**: Ziehen Sie einen Genehmigungsprozess für Ihren Filter in Erwägung. Es gibt keinen Genehmigungs-Workflow im Customer Journey Analytics, aber Sie können trotzdem einen Prozess organisieren, um zu bestimmen, ob Sie einen Filter genehmigen oder nicht.

- **Modularität**: Definieren Sie Filter unter Berücksichtigung der Modularität. So können die Benutzer Ihrer Filter einfach [Stack-Filter](filter-builder.md#stack-filters) verwenden, um leistungsstarke neue Filter zu erstellen.


## Filtertypen

Sie können drei Filtertypen erstellen:

### Schnellfilter

Schnellfilter ermöglichen es Ihnen, Daten innerhalb eines bestimmten Workspace-Projekts einfach zu untersuchen, ohne einen Filter im [Filtergenerator](/help/components/filters/create-filters.md) erstellen zu müssen. Sie definieren Ihren Filter direkt in der Workspace-Benutzeroberfläche. Weitere Informationen finden Sie unter [Schnellfilter](quick-filters.md) .

### Reguläre Filter

Mit regulären Filtern können Sie Daten (Personen, Sitzungen, Ereignisse) anhand einer oder mehrerer Bedingungen identifizieren. Bei mehr als einer Bedingung verwenden Sie logische Operatoren wie Und und Oder , um den Filter weiter zu definieren. Sie können Behälter verwenden, um Bedingungen zu gruppieren und komplexere Filter zu erstellen. Weitere Informationen finden Sie unter [Filter Builder](filter-builder.md) .

### Sequenzielle Filter

>[!IMPORTANT]
>
>Sie müssen über das Paket **Select** verfügen, um kanalübergreifende sequenzielle Filter zu erstellen. Wenden Sie sich an Ihren Administrator, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie haben.

Mit sequenziellen Filtern können Sie Daten (Personen, Sitzungen, Ereignisse) basierend auf der Navigation (Seitenansichten auf Ihrer Site, Interaktionen mit Szenen in Ihrer mobilen App oder über ein Menü in einer Set-Top-Box) identifizieren. Mit sequenziellen Filtern können Sie beispielsweise erkennen, was eine Person mag und was eine Person meidet. Verwenden Sie den logischen Operator Dann , um einen sequenziellen Filter zu definieren. Weitere Informationen finden Sie unter [Sequenzielle Filter](seg-sequential-build.md) .


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Filter-Container {#containers}

Filter basieren auf einer Hierarchie auf Personen-, Sitzungs- und Ereignisebene, die ein verschachteltes Behältermodell verwendet. Mit verschachtelten Containern können Sie Bedingungen zwischen und innerhalb der Container definieren.


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
>Für Benutzer von Adobe Analytics:
> 
> - Der Behälter **Person** wird in Adobe Analytics als **Besucher** -Container bezeichnet.
> - Der Behälter **Sitzung** wird in Adobe Analytics als **Besuchsbehälter** bezeichnet.
> - Der **Ereignis** -Container wird in Adobe Analytics als **Trefferbehälter** bezeichnet.
>

Ein Filter legt Bedingungen fest, um Personen, Sitzungen oder Ereignisse anhand von Bedingungen zu filtern. Beispielsweise Bedingungen zum Filtern von Personen anhand von Personenmerkmalen und Navigationsmerkmalen. Um die Daten weiter aufzuschlüsseln, können Sie nach bestimmten Sitzungen, Seitenansichtsereignissen, Bildschirmtippen, Menüoptionen in einem Set-Top-Feld und mehr filtern. Filtern Sie jedoch auch nach Attributen, die Sie aus einem CRM- oder Treuesystem erfasst haben. Der [Filter-Builder](/help/components/filters/filter-builder.md) bietet eine einfache Oberfläche zum Erstellen dieser Untergruppen und zum Anwenden von Bedingungen in verschachtelten, hierarchischen Personen-, Sitzungs- oder Ereignis-Containern.

Die im [Filter-Builder](/help/components/filters/filter-builder.md) verwendete Behälterarchitektur definiert Person als den äußersten Behälter. Der Container enthält sitzungs- und ereignisübergreifende übergeordnete Daten, wie Seitenansichten, Mobilanwendungsbildschirme oder Menübildschirme, die für die Person spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Daten der Person auf der Grundlage von Sitzungen aufgeschlüsselt werden. Mit einem verschachtelten Ereignis-Container können Sie Personeninformationen auf der Grundlage einzelner Interaktionen aufschlüsseln. Jeder Container ermöglicht Berichte über den Verlauf einer Person, nach Sitzungen aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container

Der Personen-Container enthält jede Sitzung und jedes Ereignis für die Personen, die sich für die im Container angegebene Bedingung qualifizieren. Wenn Sie einen Filter mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Personen-Container aufgelöst zu:

- Alle Personen, die die Seite mit dem Namen `Checkout` besucht haben.
- Alle Sitzungen für diese Personen.
- Alle Ereignisdaten für diese Personen.

Als am weitesten definierter Container geben Berichte, die auf der Ebene des Personen-Containers generiert werden, Ereignisse und Sitzungen für alle Personen zurück, die für den Filter qualifiziert sind. Der Personen-Container ändert sich am wahrscheinlichsten je nach definierten Datumsbereichen.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf einer Person basieren:

- Tage vor dem ersten Kauf.
- Ursprüngliche Entrypage oder Startbildschirm der mobilen App.
- Ursprüngliche Referrerdomänen.

### Sitzungs-Container

Mit dem Sitzungs-Container können Sie Seiteninteraktionen oder mobile App-Interaktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifizieren. Der Sitzungs-Container ist der am häufigsten verwendete Container, da er das Verhalten für die gesamte Sitzung erfasst, sobald die Regel erfüllt ist. Mit dem Sitzungs-Container können Sie auch definieren, welche Sitzungen beim Erstellen und Anwenden eines Filters ein- oder ausgeschlossen werden sollen.  Wenn Sie einen Filter mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Sitzungs-Container aufgelöst zu:

- Alle Sitzungen, in denen eine Seite mit dem Namen &quot;`Checkout`&quot; besucht wird.
- Alle Ereignisdaten für diese Sitzungen.

Der Sitzungs-Container kann Ihnen bei der Beantwortung der folgenden Fragen helfen:

- Wie viele Sitzungen umfassten sowohl Web- als auch Callcenter-Datenquellen?
- Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf Ereignissen pro Sitzung basieren:

- Sitzungstyp.
- Entrypage.
- Rückkehrhäufigkeit.
- Beitragsmetriken.
- Linear zugeordnete Metriken.

Mithilfe von Datenansichten in Customer Journey Analytics können Sie festlegen, wie lange eine Sitzung dauert, aber auch, wann eine neue Sitzung erstellt werden soll. Sie können beispielsweise eine neue App-Sitzung definieren, die auf jedem Start der App durch einen Benutzer basiert. Weitere Informationen finden Sie unter [Sitzungseinstellungen](/help/data-views/session-settings.md) .

### Ereignis-Container

Der Ereignis-Container definiert, welche Seite, Mobile App oder andere Ereignistypen Sie ein- oder ausschließen möchten. Es handelt sich dabei um die schmalsten verfügbaren Container, mit denen Sie bestimmte Klicks, Seitenansichten und Tippen auf die Schaltfläche in einer mobilen App identifizieren können, in der eine Bedingung wahr ist. Mit dem Ereignis-Container können Sie einen einzelnen Trackingcode anzeigen oder das Verhalten in einem bestimmten Bereich Ihrer App isolieren. Sie können auch einen bestimmten Wert bestimmen, wenn eine Aktion stattfindet, z. B. den Marketing-Kanal, wenn eine Bestellung aufgegeben wurde. Wenn Sie einen Filter mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Ereignis-Container aufgelöst zu:

- Alle Seitenansichtsereignisse, bei denen der Seitenname gleich `Checkout` ist.

Ereignis-Container enthalten wertbasierte Einzelseitenaufschlüsselungen für:

- Produkte
- Listen-Props
- Listendimensionen
- Merchandising-Dimensionen (im Kontext von Ereignissen)


### Logischer Gruppenbehälter

Mit der logischen Gruppe können Sie Bedingungen zu einem einzigen sequenziellen Filter-Checkpoint gruppieren. Als Teil der Sequenz wird die im Container definierte Logik, die als [!UICONTROL logische Gruppe] identifiziert wird, nach jedem vorherigen sequenziellen Checkpoint und vor jedem nachfolgenden sequenziellen Checkpoint ausgewertet. Weitere Informationen finden Sie unter [Logische Gruppe](seg-sequential-build.md#logic-group) .

### Verschachteln von Containern

Beim Erstellen von Containern in anderen Containern erstellen Sie tatsächlich einen Filter innerhalb eines Filters. Die folgende Logik wird auf verschachtelte Container angewendet:

1. Bestimmen, welche Daten enthalten sind, indem der äußerste Container verwendet wird. Alle Daten, die nicht mit dieser äußeren Regel übereinstimmen, werden im Bericht verworfen.
2. Wenden Sie die verschachtelte Filterdefinition auf die verbleibenden Daten an. Die Definition verschachtelter Filter gilt NICHT für Daten, die von der ersten Definition verworfen wurden.
3. Wiederholen Sie diesen Vorgang, bis alle Filterdefinitionen für verschachtelte Container berechnet wurden. Die verbleibenden Daten werden dann in das Ergebnis aufgenommen und für die Berichterstellung verwendet.

>[!NOTE]
>
>Wenn Sie einen Filter innerhalb eines Filters verschachteln (z. B. einen Filter aus dem Bereich &quot;Komponenten&quot;auf Ihre Filterdefinition ziehen), wird ein Container mit einer Kopie (keine Referenz) der gezogenen Filterdefinition erstellt.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Filter erstellen](create-filters.md)
>[Filter Builder](filter-builder.md)
>[Quick filters](quick-filters.md)
>[Sequenzielle Filter](seg-sequential-build.md)
>[Filter verwalten](manage-filters.md)
>
