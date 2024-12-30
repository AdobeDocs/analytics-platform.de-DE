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

- Attribute (Browser-Typ, Gerät, Anzahl der Besuche, Land, Geschlecht),
- Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine),
- Ausstiege und Einstiege (Personen aus Facebook, einer definierten Landingpage, Referrer-Domain, Geofence-Ereignis),
- benutzerdefinierte Variablen (Formularfeld, definierte Kategorien, Kunden-ID),
- und andere Kriterien.

Siehe [Erstellen von Filtern](/help/components/filters/create-filters.md) für die verschiedenen verfügbaren Optionen zum Erstellen von Filtern. Anschließend erstellen, ändern und speichern Sie die Definition eines Filters im [Filter Builder](filter-builder.md). Alternativ können Sie Schnellfilter mit dem Schnellfilter[Generator ](quick-filters.md). Sie können auch Filter aus Visualisierungen in Workspace generieren, z. B. mithilfe der [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)-Visualisierung.

Sie verwenden den [Filter-Manager](manage-filters.md) um Filter zu verwalten.

## Filter planen

Insbesondere als Administrator verbessert die ordnungsgemäße Planung von Filtern die Chancen, dass die Filter verwendet werden. Beachten Sie bei der Planung von Filtern Folgendes:

- **Zielgruppe**: Wer wird Ihre Filter verwenden? Stellen Sie sicher, dass Sie eine gute Filterbeschreibung bereitstellen, damit die Zielgruppe Folgendes versteht:
   - Wofür ist dieser Filter nützlich?

   - Wann sollte dieser Filter benutzt werden?

- **Umfang**: Welcher [Filter-Container](#filter-containers) repräsentiert die Daten, nach denen Sie suchen? Benutzen Sie den kleinstmöglichen Container.

- **Komponenten**: Entscheiden Sie, welche Komponenten in die Filterdefinition aufgenommen werden sollen und anhand welcher Werte die Bedingungen validiert werden sollen.

- **Prozess**: Erwägen Sie einen Genehmigungsprozess für Ihren Filter. Es gibt keinen Genehmigungs-Workflow in Customer Journey Analytics. Sie können jedoch trotzdem einen Prozess organisieren, um zu bestimmen, ob Sie einen Filter genehmigen oder nicht.

- **Modularität**: Filter mit Blick auf Modularität definieren. Die Benutzer Ihrer Filter können also einfach [Filter stapeln](filter-builder.md#stack-filters) um leistungsstarke neue Filter zu erstellen.


## Filtertypen

Sie können drei Filtertypen erstellen:

### Schnellfilter

Mit Schnellfiltern können Sie Daten innerhalb eines bestimmten Workspace-Projekts problemlos untersuchen, ohne dass ein Filter im [Filtergenerator“ erstellt ](/help/components/filters/create-filters.md) muss. Sie definieren Ihren Filter direkt in der Workspace-Oberfläche. Weitere Informationen finden [ unter ](quick-filters.md)Schnellfilter“.

### Reguläre Filter

Mit regulären Filtern können Sie Daten (Personen, Sitzungen, Ereignisse) anhand einer oder mehrerer Bedingungen identifizieren. Bei mehr als einer Bedingung verwenden Sie logische Operatoren wie Und und Oder, um den Filter weiter zu definieren. Sie können Container verwenden, um Bedingungen zu gruppieren und komplexere Filter zu erstellen. Weitere Informationen finden [ unter ](filter-builder.md)Filtergenerator“.

### Sequenzielle Filter

>[!IMPORTANT]
>
>Sie müssen über das Paket **Auswählen** verfügen, um kanalübergreifende sequenzielle Filter zu erstellen. Wenden Sie sich an Ihren Administrator, wenn Sie nicht sicher sind, welches Customer Journey Analytics-Paket Sie haben.

Mit sequenziellen Filtern können Sie Daten (Personen, Sitzungen, Ereignisse) anhand der Navigation (Seitenansichten auf Ihrer Site, Interaktionen mit Szenen in Ihrer Mobile App oder mithilfe eines Menüs in einer Set-Top-Box) identifizieren. Mit sequenziellen Filtern können Sie beispielsweise identifizieren, was eine Person mag und was sie meidet. Sie verwenden den logischen Operator Dann , um einen sequenziellen Filter zu definieren. Siehe [Sequenzielle Filter](seg-sequential-build.md) für weitere Informationen.


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Filter-Container {#containers}

Filter basieren auf einer Hierarchie auf Personen-, Sitzungs- und Ereignisebene, wobei ein verschachteltes Container-Modell verwendet wird. Mit verschachtelten Containern können Sie Bedingungen zwischen und innerhalb der Container definieren.


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
>Für Adobe Analytics-Benutzer:
> 
> - Der **Person**-Container wird in Adobe Analytics als **Besucher-** bezeichnet.
> - Der **Sitzungs**-Container wird in Adobe Analytics als **Besuchs**-Container bezeichnet.
> - Der **Ereignis**-Container wird in Adobe Analytics als **Treffer**-Container bezeichnet.
>

Ein Filter legt Bedingungen fest, um Personen, Sitzungen oder Ereignisse anhand von Bedingungen zu filtern. Beispielsweise Bedingungen zum Filtern von Personen anhand von Personenmerkmalen und Navigationseigenschaften. Um die Daten weiter aufzuschlüsseln, können Sie nach bestimmten Sitzungen, Seitenansichtsereignissen, Bildschirmtipps, Menüoptionen in einer Set-Top-Box und mehr filtern. Sie können aber auch nach Attributen filtern, die Sie aus einem CRM- oder Treuesystem aufgenommen haben. Der [Filtergenerator](/help/components/filters/filter-builder.md) bietet eine einfache Schnittstelle zum Erstellen dieser Teilmengen und zum Anwenden von Bedingungen in verschachtelten, hierarchischen Personen-, Sitzungs- oder Ereignis-Containern.

Die im Filtergenerator verwendete Container[Architektur definiert ](/help/components/filters/filter-builder.md) Person als den äußersten Container. Der Container enthält übergreifende Daten, die für die Person über Sitzungen und Ereignisse wie Seitenansichten, Bildschirme von Mobile Apps oder Menübildschirme in einer Set-Top-Box hinweg spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Daten der Person auf der Grundlage von Sitzungen aufgeschlüsselt werden. Mit einem verschachtelten Ereignis-Container können Sie Personeninformationen auf der Grundlage einzelner Interaktionen aufschlüsseln. Jeder Container ermöglicht Berichte über den Verlauf einer Person, nach Sitzungen aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container

Der Container Person enthält jede Sitzung und jedes Ereignis für die Personen, die für die im Container angegebene Bedingung qualifiziert sind. Wenn Sie einen Filter mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, löst der Container Person auf zu:

- Alle Personen, die die Seite mit dem Namen `Checkout` besucht haben.
- Alle Sitzungen für diese Personen.
- Alle Ereignisdaten für diese Personen.

Als am breitesten definierter Container geben Berichte, die auf der Ebene des Personen-Containers generiert werden, Ereignisse und Sitzungen für alle Personen zurück, die für den Filter qualifiziert sind. Der Container Person ist am anfälligsten für Änderungen basierend auf definierten Datumsbereichen.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf einer Person basieren:

- Tage vor dem ersten Kauf.
- Ursprüngliche Einstiegsseite oder Startbildschirm der Mobile App.
- Ursprünglich verweisende Domains.

### Sitzungs-Container

Mit dem Sitzungs-Container können Seiteninteraktionen oder Mobile-App-Interaktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden. Der Sitzungs-Container ist der am häufigsten verwendete Container, da er Verhaltensweisen für die gesamte Sitzung erfasst, sobald die Regel erfüllt wird. Mit dem Sitzungs-Container können Sie auch definieren, welche Sitzungen Sie beim Erstellen und Anwenden eines Filters ein- oder ausschließen möchten.  Wenn Sie einen Filter mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Sitzungs-Container aufgelöst zu:

- Alle Sitzungen, in denen eine Seite mit dem Namen `Checkout` besucht wird.
- Alle Ereignisdaten für diese Sitzungen.

Der Sitzungs-Container kann Ihnen bei der Beantwortung der folgenden Fragen helfen:

- Wie viele Sitzungen umfassten sowohl Web- als auch Callcenter-Datenquellen?
- Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf Ereignissen pro Sitzung basieren:

- Sitzungstyp.
- Einstiegsseite.
- Rückkehrhäufigkeit.
- Teilnahmemetriken.
- Linear zugeordnete Metriken.

Mit Datenansichten in Customer Journey Analytics können Sie festlegen, wie lange eine Sitzung dauert, aber auch, wann eine neue Sitzung erstellt werden soll. Sie können beispielsweise eine neue Mobile-App-Sitzung basierend auf jedem Start Ihrer Mobile App durch einen Benutzer definieren. Siehe [Sitzungseinstellungen](/help/data-views/session-settings.md) für weitere Informationen.

### Ereignis-Container

Der Ereignis-Container definiert, welche Seite, Mobile App oder andere Arten von Ereignissen Sie in einen Filter einschließen oder daraus ausschließen möchten. Dies ist der engste verfügbare Container, mit dem Sie spezifische Klicks, Seitenansichten und Tippen auf eine Schaltfläche in einer Mobile App identifizieren können, bei der eine Bedingung erfüllt ist. Mit dem Ereignis-Container können Sie einen einzelnen Trackingcode anzeigen oder das Verhalten in einem bestimmten Bereich Ihrer Mobile App isolieren. Möglicherweise möchten Sie auch einen bestimmten Wert bestimmen, wenn eine Aktion auftritt, z. B. den Marketing-Kanal, wenn eine Bestellung aufgegeben wurde. Wenn Sie einen Filter mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Ereignis-Container aufgelöst zu:

- Alle Seitenansichtsereignisse, bei denen der Seitenname `Checkout` entspricht.

Ereignis-Container enthalten wertbasierte Aufschlüsselungen einzelner Seiten für:

- Produkte
- Listen-Props
- Listendimensionen
- Merchandising-Dimensionen (im Kontext von Ereignissen)


### Logischer Gruppen-Container

Mit der Logikgruppe können Sie Bedingungen in einem einzigen sequenziellen Filtercheckpoint gruppieren. Als Teil der Sequenz wird die Logik, die in dem als &quot;[!UICONTROL &quot; identifizierten Container definiert ], nach einem vorherigen sequenziellen Checkpoint und vor einem nachfolgenden sequenziellen Checkpoint ausgewertet. Siehe [Logikgruppe](seg-sequential-build.md#logic-group) für weitere Informationen.

### Container verschachteln

Wenn Sie Container in anderen Containern erstellen, erstellen Sie tatsächlich einen Filter innerhalb eines Filters. Die folgende Logik wird auf verschachtelte Container angewendet:

1. Bestimmen, welche Daten enthalten sind, indem der äußerste Container verwendet wird. Daten, die nicht mit dieser äußeren Regel übereinstimmen, werden im Bericht verworfen.
2. Wenden Sie die verschachtelte Filterdefinition auf die verbleibenden Daten an. Die verschachtelte Filterdefinition gilt NICHT für Daten, die die erste Definition verworfen hat.
3. Wiederholen, bis alle verschachtelten Container-Filterdefinitionen berechnet wurden. Die verbleibenden Daten werden dann in das Ergebnis aufgenommen und für das Reporting verwendet.

>[!NOTE]
>
>Wenn Sie einen Filter in einem Filter verschachteln (Sie ziehen beispielsweise einen Filter aus dem Bedienfeld Komponenten auf Ihre Filterdefinition), wird ein Container mit einer Kopie (nicht einer Referenz) der gezogenen Filterdefinition erstellt.

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
>[Filtergenerator](filter-builder.md)
>[Schnellfilter](quick-filters.md)
>[Sequenzielle Filter](seg-sequential-build.md)
>[Filter verwalten](manage-filters.md)
>
