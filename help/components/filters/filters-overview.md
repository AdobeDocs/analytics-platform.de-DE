---
title: Segmentierung – Übersicht
description: Erfahren Sie, wofür Segmente verwendet werden und wie Sie ein einfaches Segment erstellen.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---


# Segmentierung – Übersicht

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppensegmente erstellen, verwalten, freigeben und auf Ihre Berichte anwenden. Mit Segmenten können Sie Untergruppen von Personen, Sitzungen oder Ereignissen anhand von Merkmalen oder Interaktionen identifizieren. Segmente sind als kodierte Zielgruppeneinblicke konzipiert, die Sie für Ihre spezifischen Anforderungen erstellen und dann überprüfen, bearbeiten und für andere Team-Mitglieder freigeben können.

Segmente können auf Folgendem basieren:

- Attribute (Browser-Typ, Gerät, Anzahl der Besuche, Land, Geschlecht),
- Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine),
- Ausstiege und Einstiege (Personen aus Facebook, eine definierte Landingpage, Referrer-Domain, Geofence-Ereignis),
- benutzerdefinierte Variablen (Formularfeld, definierte Kategorien, Kunden-ID),
- und andere Kriterien.

Unter [Segmente erstellen](/help/components/filters/create-filters.md) finden Sie die verschiedenen Optionen zum Erstellen von Segmenten. Anschließend erstellen, ändern und speichern Sie die Definition eines Segments im [Segment Builder](filter-builder.md). Alternativ können Sie Schnellsegmente mit dem [Quick Segment Builder“ ](quick-filters.md). Außerdem können Sie Segmente auch aus Visualisierungen in Workspace generieren, z. B. mithilfe der [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)-Visualisierung.

Sie verwenden den [Segment-Manager](manage-filters.md), um Segmente zu verwalten.

## Segmente planen

Insbesondere für Admins verbessert die ordnungsgemäße Planung von Segmenten die Chancen, dass die Segmente verwendet werden. Beachten Sie bei der Planung von Segmenten Folgendes:

- **Zielgruppe**: Wer wird Ihre Segmente verwenden? Stellen Sie sicher, dass Sie eine gute Segmentbeschreibung bereitstellen, damit die Zielgruppe Folgendes versteht:
   - Wofür ist dieses Segment nützlich?

   - Wann sollte dieses Segment benutzt werden?

- **Umfang**: Welcher [Segment-Container](#filter-containers) repräsentiert die Daten, nach denen Sie suchen, am besten? Benutzen Sie den kleinstmöglichen Container.

- **Komponenten**: Entscheiden Sie, welche Komponenten in die Segmentdefinition aufgenommen werden sollen und anhand welcher Werte die Bedingungen validiert werden sollen.

- **Prozess**: Erwägen Sie einen Genehmigungsprozess für Ihre Segmente. In Customer Journey Analytics gibt es keinen Genehmigungs-Workflow, Sie können jedoch trotzdem einen Prozess organisieren, um zu bestimmen, ob Sie ein Segment genehmigen oder nicht.

- **Modularität**: Definieren Sie Segmente unter Berücksichtigung der Modularität. Die Benutzer Ihrer Segmente sollten in der Lage sein, einfach [Segmente zu stapeln](filter-builder.md#stack-filters) um leistungsstarke neue Segmente zu erstellen.


## Segmenttypen

Sie können drei Segmenttypen erstellen:

### Schnellsegmente

Schnellsegmente ermöglichen Ihnen, Daten innerhalb eines bestimmten Workspace-Projekts einfach zu untersuchen, ohne dass ein Segment in [Segment Builder“ erstellt ](/help/components/filters/create-filters.md) muss. Sie definieren Ihr Segment direkt in der Workspace-Benutzeroberfläche. Weitere Informationen finden [ unter ](quick-filters.md)Schnellsegmente“.

### Reguläre Segmente

Mit regulären Segmenten können Sie Daten (Personen, Sitzungen, Ereignisse) anhand einer oder mehrerer Bedingungen identifizieren. Wenn Sie mehr als eine Bedingung haben, verwenden Sie logische Operatoren wie Und und Oder, um das Segment weiter zu definieren. Sie können Container verwenden, um Bedingungen zu gruppieren und komplexere Segmente zu erstellen. Weitere Informationen finden [ unter ](filter-builder.md)Segment Builder“.

### Sequenzielle Segmente

>[!IMPORTANT]
>
>Sie müssen über das Paket **Auswählen** verfügen, um sequenzielle kanalübergreifende Segmente zu erstellen. Wenden Sie sich an Ihre Admins, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

Mit sequenziellen Segmenten können Sie Daten (Personen, Sitzungen, Ereignisse) anhand der Navigation (Seitenansichten auf Ihrer Site, Interaktionen mit Szenen in Ihrer Mobile App oder mithilfe eines Menüs in einer Set-Top-Box) identifizieren. Sequenzielle Segmente helfen Ihnen beispielsweise dabei, zu erkennen, was eine Person mag und was sie meidet. Sie verwenden den logischen Operator Then, um ein sequenzielles Segment zu definieren. Weitere Informationen finden [ unter ](seg-sequential-build.md) von Segmenten.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Segment-Container {#containers}

Segmente basieren auf einer Hierarchie auf Personen-, Sitzungs- und Ereignisebene, wobei ein verschachteltes Container-Modell verwendet wird. Mit verschachtelten Containern können Sie Bedingungen zwischen und innerhalb der Container definieren.


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

Ein Segment legt Bedingungen fest, um Personen, Sitzungen oder Ereignisse basierend auf Bedingungen zu segmentieren. Bedingungen zum Segmentieren von Personen basieren beispielsweise auf Personeneigenschaften und Navigationseigenschaften. Um die Daten weiter aufzuschlüsseln, können Sie Sitzungen, Seitenansichtsereignisse, Bildschirmtipps, Menüoptionen in einer Set-Top-Box usw. segmentieren. Sie können auch nach Attributen segmentieren, die Sie aus einem CRM- oder Treuesystem aufgenommen haben. Der [Segment Builder](/help/components/filters/filter-builder.md) bietet eine einfache Schnittstelle zum Erstellen dieser Untergruppen und zum Anwenden von Bedingungen in verschachtelten, hierarchischen Personen-, Sitzungs- oder Ereignis-Containern.

Die im Segmentaufbau verwendete Container[Architektur definiert ](/help/components/filters/filter-builder.md) Person als den äußersten Container. Dieser Container enthält übergreifende Daten, die für die Person über Sitzungen und Ereignisse wie Seitenansichten, Bildschirme für Mobile Apps oder Menübildschirme in einer Set-Top-Box hinweg spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Daten der Person auf der Grundlage von Sitzungen aufgeschlüsselt werden. Mit einem verschachtelten Ereignis-Container können Sie Personeninformationen auf der Grundlage einzelner Interaktionen aufschlüsseln. Jeder Container ermöglicht Berichte über den Verlauf einer Person, nach Sitzungen aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container

Der Container Person enthält jede Sitzung und jedes Ereignis für die Personen, die für die im Container angegebene Bedingung qualifiziert sind. Wenn Sie ein Segment mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, löst der Container Person auf zu:

- Alle Personen, die die Seite mit dem Namen `Checkout` besucht haben.
- Alle Sitzungen für diese Personen.
- Alle Ereignisdaten für diese Personen.

Als am breitesten definierter Container geben Berichte, die auf der Ebene des Personen-Containers generiert wurden, Ereignisse und Sitzungen für alle Personen zurück, die für das Segment qualifiziert sind. Der Container Person ist am anfälligsten für Änderungen basierend auf definierten Datumsbereichen.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf einer Person basieren:

- Tage vor dem ersten Kauf.
- Ursprüngliche Einstiegsseite oder Startbildschirm der Mobile App.
- Ursprünglich verweisende Domains.

### Sitzungs-Container

Mit dem Sitzungs-Container können Seiteninteraktionen oder Mobile-App-Interaktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden. Der Sitzungs-Container ist der am häufigsten verwendete Container, da er Verhaltensweisen für die gesamte Sitzung erfasst, sobald die Regel erfüllt wird. Mit dem Sitzungs-Container können Sie auch definieren, welche Sitzungen Sie beim Erstellen und Anwenden eines Segments ein- oder ausschließen möchten.  Wenn Sie ein Segment mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Sitzungs-Container aufgelöst zu:

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

Der Ereignis-Container definiert, welche Seite, Mobile App oder andere Ereignistypen Sie in ein Segment einbeziehen oder daraus ausschließen möchten. Es ist der schmalste der verfügbaren Behälter. Damit können Sie bestimmte Klicks, Seitenansichten und Tippen auf eine Schaltfläche in einer Mobile App identifizieren, für die eine Bedingung erfüllt ist. Mit dem Ereignis-Container können Sie einen einzelnen Trackingcode anzeigen oder das Verhalten in einem bestimmten Bereich Ihrer Mobile App isolieren. Möglicherweise möchten Sie auch einen bestimmten Wert bestimmen, wenn eine Aktion auftritt, z. B. den Marketing-Kanal, wenn eine Bestellung aufgegeben wurde. Wenn Sie ein Segment mit einer einfachen Bedingung wie `Page Name equals Checkout` definieren, wird der Ereignis-Container aufgelöst zu:

- Alle Seitenansichtsereignisse, bei denen der Seitenname `Checkout` entspricht.

Ereignis-Container enthalten wertbasierte Aufschlüsselungen einzelner Seiten für:

- Produkte
- Listen-Props
- Listendimensionen
- Merchandising-Dimensionen (im Kontext von Ereignissen)



### B2B-Container

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

Wenn Sie Zugriff auf [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) haben, stehen zusätzliche Container zur Verwendung in Segmenten zur Verfügung. Weitere Informationen zur Verwendung dieser zusätzlichen Container finden Sie unter „B2B[Konzepte und -Funktionen](/help/getting-started/cja-b2b-concepts-features.md).


### Logischer Gruppen-Container

Mit der logischen Gruppe können Sie Bedingungen in einem einzigen sequenziellen Segment-Checkpoint gruppieren. Als Teil der Sequenz wird die Logik, die in dem als &quot;[!UICONTROL &quot; identifizierten Container definiert &#x200B;], nach einem vorherigen sequenziellen Checkpoint und vor einem nachfolgenden sequenziellen Checkpoint ausgewertet. Siehe [Logikgruppe](seg-sequential-build.md#logic-group) für weitere Informationen.

### Container verschachteln

Wenn Sie Container in anderen Containern erstellen, erstellen Sie tatsächlich ein Segment innerhalb eines Segments. Die folgende Logik wird auf verschachtelte Container angewendet:

1. Bestimmen, welche Daten enthalten sind, indem der äußerste Container verwendet wird. Daten, die nicht mit dieser äußeren Regel übereinstimmen, werden im Bericht verworfen.
2. Wenden Sie die verschachtelte Segmentdefinition auf die verbleibenden Daten an. Die verschachtelte Segmentdefinition gilt NICHT für Daten, die die erste Definition verworfen hat.
3. Wiederholen Sie diesen Vorgang, bis alle Segmentdefinitionen des verschachtelten Containers berechnet wurden. Die verbleibenden Daten werden dann in das Ergebnis aufgenommen und für das Reporting verwendet.

>[!NOTE]
>
>Wenn Sie ein Segment innerhalb eines Segments verschachteln (Sie ziehen beispielsweise ein Segment aus dem Bedienfeld „Komponenten“ auf Ihre Segmentdefinition), wird ein Container mit einer Kopie (nicht einer Referenz) der gezogenen Segmentdefinition erstellt.

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
>[Segmente erstellen](create-filters.md)
>[Segment Builder](filter-builder.md)
>[Schnellsegmente](quick-filters.md)
>[Sequenzielle ](seg-sequential-build.md)
>[Segmente verwalten](manage-filters.md)
>
