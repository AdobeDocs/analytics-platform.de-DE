---
title: Filterübersicht
description: Erfahren Sie, wofür Filter verwendet werden und wie Sie einen einfachen Filter erstellen.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
source-git-commit: 53a1a6995caad960d8daba4e0d1f4394aa184206
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 27%

---


# Filterübersicht {#overview}

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppenfilter für Ihre Berichte erstellen, verwalten, freigeben und anwenden. Mit Filtern können Sie Personengruppen anhand von Merkmalen oder Interaktionen identifizieren. Filter sind als kodifizierte Zielgruppeneinblicke konzipiert, die Sie für Ihre speziellen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Team-Mitgliedern austauschen können.

Filter können auf

- Attribute (Browsertyp, Gerät, Anzahl Besuche, Land, Geschlecht),
- Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine),
- Ausstiege und Einstiege (Personen aus Facebook, eine definierte Landingpage, Referrer-Domäne, Geofence-Ereignis),
- benutzerdefinierte Variablen (Formularfeld, definierte Kategorien, Kunden-ID),
- und anderen Kriterien.

Sie können Filter im Filtergenerator erstellen und speichern oder Filter aus einer Fallout-Visualisierung (in Workspace) generieren. Darüber hinaus können Filter zusammen als gestapelte Filter verwendet werden.

Die Filterung umfasst den [Filtergenerator](/help/components/filters/filter-builder.md) zum Aufbau von Filtern und zur Ausführung eines Vorab-Tests sowie den [Filter-Manager](/help/components/filters/manage-filters.md) zur Erfassung, Kennzeichnung, Freigabe, Sicherheitseinstellung und Weitergabe von Filtern in Ihrer Organisation.

Die maximale Anzahl von Filtern, die Sie pro IMS-Organisation erstellen können, beträgt 50.000.

## Filtertypen {#types}

Informationen zu den verfügbaren Filtertypen und deren Erstellung finden Sie unter [Filter erstellen](/help/components/filters/create-filters.md).

## Sequenzielle Filter {#sequential}

Mit sequenziellen Filtern können Sie Personen anhand der Navigation identifizieren (Seitenansichten auf der gesamten Site, Interaktionen mit Szenen in Ihrer mobilen App oder über ein Menü in einem Set-Top-Feld). Sequenzielle Filter bieten einen Filter für definierte Aktionen und Interaktionen und helfen Ihnen dabei zu identifizieren, was eine Person mag und was eine Person vermeidet. Beim Erstellen sequenzieller Filter wird der Operator THEN verwendet, um die Personennavigation zu definieren und zu ordnen.

>[!IMPORTANT]
>
>Sie müssen über die **Auswählen** -Paket zum Erstellen von kanalübergreifenden sequenziellen Filtern. Wenden Sie sich an Ihren Administrator, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie haben.

Siehe folgendes Beispiel:

| Sitzung 1 | Sitzung 2 | Sitzung drei |
| --- | --- | --- |
| Der Benutzer besuchte die Haupt-Landingpage A, schloss die Kampagnenseite B aus und sah sich dann die Produktseite C an. | Die Person besuchte erneut die Haupt-Landingpage A, schloss die Kampagnenseite B aus, besuchte erneut die Produktseite C und dann eine neue Seite D. | Die Person hat denselben Pfad wie beim ersten und zweiten Besuch eingegeben und gefolgt und dann Seite F ausgeschlossen, um direkt zu einer Targeting-Produktseite G zu wechseln. |

## Filter-Container {#containers}

Filter basieren auf einer Hierarchie auf Personen-, Sitzungs- und Ereignisebene, die ein verschachteltes Behältermodell verwendet. Mit verschachtelten Container können Sie Besucherattribute definieren sowie Aktionen, die auf Regeln zwischen den Containern und innerhalb der Container basieren.


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Benutzer</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sitzung</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Ereignis-  </td>
</tr>
</table>

>[!NOTE]
>Der Personen-Container wurde früher als Besucher-Container bezeichnet. Der Sitzungs-Container wurde als Besuchs-Container bezeichnet, und der Ereignis-Container war früher der Treffer-Container.

Ein Filter legt Bedingungen zum Filtern einer Person auf der Grundlage der Attribute oder Interaktionen der Person mit Ihrer Site, mobilen App oder einem anderen Gerätetyp fest, von dem Sie Daten erfasst haben. Um Bedingungen in einem Filter festzulegen, legen Sie Regeln fest, mit denen Personen nach Personenmerkmalen und/oder Navigationsmerkmalen gefiltert werden. Um Personendaten weiter aufzuschlüsseln, können Sie nach spezifischen Besuchen und/oder Seitenansichtstreffen, Bildschirmtippen und Menüoptionen für jede Person filtern. Der Filtergenerator bietet eine einfache Architektur zum Erstellen dieser Untergruppen und das Anwenden von Regeln als verschachtelte hierarchische Personen-, Sitzungs- oder Ereignis-Container.

Die im Filtergenerator verwendete Behälterarchitektur definiert Person als den äußersten Behälter. Der Container enthält übergreifende Daten, die für die Person über Besuche und Seitenansichten, Mobilanwendungsbildschirme oder Menübildschirme in einem Set-Top-Feld hinweg spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Daten der Person auf der Grundlage von Sitzungen aufgeschlüsselt werden, und einen verschachtelten Ereignis-Container, mit dem die Personeninformationen auf der Grundlage einzelner Seitenansichten aufgeschlüsselt werden. Jeder Container ermöglicht Berichte über den Verlauf einer Person, nach Sitzungen aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container {#person}

Der Personen-Container enthält alle Besuche und Seitenansichten, mobile App-Bildschirme, Set-Top-Box oder Konsolenspiel-Interaktionen für Personen innerhalb eines bestimmten Zeitraums. Ein Filter auf Benutzerebene gibt die Seitenansichten, die mobile App oder Set-Top-Box-Bildschirme zurück, die die Bedingung erfüllen. Plus alle anderen Seiten und Bildschirme, die von derselben Person über verschiedene Kanäle angesehen werden (und nur durch definierte Datumsbereiche eingeschränkt). Da es sich um den am weitesten definierten Container handelt, geben Berichte, die auf der Ebene des Personen-Containers generiert werden, Seitenansichten, mobile App-Bildschirme und mehr über alle Besuche hinweg zurück und ermöglichen Ihnen die Erstellung einer kanalübergreifenden Analyse mehrerer Besuche. Daher ist der Personen-Container am wahrscheinlichsten, dass er sich basierend auf definierten Datumsbereichen ändert.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf einer Person basieren:

- Tage bis Erstkauf
- Ursprüngliche Einstiegsseite oder Startseite der mobilen App
- Ursprünglich Referrerdomänen 

### Sitzungs-Container {#session}

Mit dem Sitzungs-Container können Sie Seiteninteraktionen oder mobile App-Interaktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifizieren. Der Sitzungs-Container ist der am häufigsten verwendete Container, da er das Verhalten für die gesamte Besuchssitzung erfasst, sobald die Regel erfüllt ist. Mit dem Sitzungs-Container können Sie auch definieren, welche Sitzungen beim Erstellen und Anwenden eines Filters ein- oder ausgeschlossen werden sollen. Es kann Ihnen bei der Beantwortung der folgenden Fragen helfen:

- Bei wie vielen Sitzungen wurden sowohl Web- als auch Callcenter-Datenquellen verwendet?
- Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf dem Auftreten pro Sitzung basieren:

- Sitzungstyp
- Einstiegsseite
- Rückkehrhäufigkeit
- Beitragsmetriken
- Linear zugeordnete Metriken

Mithilfe von Datenansichten in Customer Journey Analytics können Sie festlegen, wie lange eine Sitzung dauert, aber auch, wann eine neue Sitzung erstellt werden soll. Sie können beispielsweise eine neue App-Sitzung definieren, die darauf basiert, wann ein Benutzer Ihre neue App startet. Siehe [Komponenteneinstellungen](/help/data-views/session-settings.md) für weitere Informationen.

### Ereignis-Container {#event}

Der Ereignis-Container definiert, welche Seite, Mobile App oder andere Ereignistypen Sie ein- oder ausschließen möchten. Es handelt sich dabei um die schmalsten verfügbaren Container, mit denen Sie bestimmte Klicks, Seitenansichten und Tippen auf die Schaltfläche in einer mobilen App identifizieren können, in der eine Bedingung wahr ist. Mit dem Ereignis-Container können Sie einen einzelnen Trackingcode anzeigen oder das Verhalten in einem bestimmten Bereich Ihrer App isolieren. Sie können auch einen bestimmten Wert erkennen, wenn eine Aktion stattfindet, z. B. den Marketing-Kanal, wenn ein Auftrag platziert wurde.

Ereignis-Container enthalten wertbasierte Einzelseitenaufschlüsselungen für:

- Produkte
- Listen-Props
- Listendimensionen
- Merchandising-Dimensionen (im Kontext von Ereignissen)

## Vordefinierte Filtervorlage {#template}

Herkömmliche Analytics bietet zahlreiche vordefinierte Vorlagen und berechnete Metriken. Viele von ihnen gelten nicht für Customer Journey Analytics, müssen umbenannt oder neu erstellt werden. Andere hängen von einer Lösung für kontextsensitive Variablen im Customer Journey Analytics ab.

| Filtername | Beschreibung |
| --- | --- |
| Alle Daten | Alle Daten sind ein erforderlicher Filter, der dynamisch zu Berichten hinzugefügt wird, wenn eine Metrik zur Zeile einer Freiformtabelle hinzugefügt wird. |
