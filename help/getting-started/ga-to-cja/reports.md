---
title: GA4-Berichte in Customer Journey Analytics
description: Finden Sie die Customer Journey Analytics-Entsprechung für jeden GA4-Berichtsabschnitt.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# GA4-Berichte in Customer Journey Analytics

Verwenden Sie diese Seite als Lookup-Referenz, wenn Sie wissen, welchen GA4-Bericht Sie anzeigen, und dessen ungefähre Entsprechung in Analysis Workspace neu erstellen möchten. Die Berichte sind nach den Navigationsabschnitten der GA4 geordnet. Erweiterte Cross-Channel-Reporting-Szenarien, die nach der Migration von GA-Daten nach Customer Journey Analytics verfügbar werden, finden Sie unter [Bericht zu Google Analytics-Daten](/help/use-cases/third-party/ga/report.md).

## Echtzeit

+++Echtzeit

Der Echtzeitbericht der GA4 zeigt die Aktivität der letzten 30 Minuten an - aktive Benutzer, ausgelöste Ereignisse, wo sich Benutzer befinden, was den Traffic steuert und auf welchen Seiten sie sich befinden.

Customer Journey Analytics verfügt über keinen separaten Echtzeitberichtsbereich. Erstellen Sie stattdessen ein Bedienfeld in Analysis Workspace und aktivieren Sie den Umschalter **[!UICONTROL Echtzeit-Aktualisierung]** (Teil des **Ultimate**-Pakets), damit seine Visualisierungen jede Minute aktualisiert werden:

1. Erstellen Sie ein [Freiform](/help/analysis-workspace/c-panels/freeform-panel.md)-Bedienfeld (der Umschalter funktioniert auch in [leeren](/help/analysis-workspace/c-panels/blank-panel.md), [Attribution](/help/analysis-workspace/c-panels/attribution.md) und [Nächstes oder vorheriges Element](/help/analysis-workspace/c-panels/next-previous.md)-Bedienfeldern) mit den Dimensionen und Metriken, die Sie überwachen möchten. Verwenden Sie zum Spiegeln der Echtzeit-Karten von GA4 **[!UICONTROL Dimension]** Seite **[!UICONTROL Ereignistyp]**, **[!UICONTROL Referrerdomäne]** oder **[!UICONTROL Länder]** mit **[!UICONTROL Sitzungen]** .
2. Aktivieren Sie den **[!UICONTROL Echtzeit-Aktualisierung]** und wählen Sie einen Zeitraum von **[!UICONTROL Letzte 15 Minuten]** bis **[!UICONTROL Letzte 24 Stunden]**. Die Daten sind auf ein rollierendes 24-Stunden-Fenster beschränkt und das Bedienfeld wird jede Minute für bis zu 30 Minuten aktualisiert.

Das Echtzeit-Reporting bevorzugt Daten auf Ereignis- und Sitzungsebene und kann keine Zuordnung verwenden. Daher sollten Sie **[!UICONTROL Sitzungen]** gegenüber **[!UICONTROL Personen]** bevorzugen. Unter [Echtzeitberichte verwenden](/help/components/real-time/use-real-time.md) finden Sie das vollständige Verfahren und [Übersicht über das Echtzeit-Reporting](/help/components/real-time/real-time.md) Informationen zu Berechtigungen und Latenzen.

+++

## Akquise

+++Benutzerakquise (Erstkontakt)

Der Bericht zur Benutzerakquise von GA4 schreibt jeden Benutzer dem Kanal, der Quelle und dem Medium zu, über die er zum ersten Mal auf Ihre Site gelangt ist, wobei die Attribution auf Erstkontakt-Zugriff basiert.

Wenden Sie in Analysis Workspace ein **[!UICONTROL Erstkontakt]** Attributionsmodell auf die Dimension **[!UICONTROL Marketing-Kanal]** an. Marketing-Kanäle müssen vor der Verwendung konfiguriert werden. Siehe [Erstellen eines von einem Marketing-Kanal abgeleiteten Felds](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md).

1. Ziehen Sie die Dimension **[!UICONTROL Marketing]** Kanal) in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Klicken Sie mit der rechten Maustaste auf eine Metrik-Spaltenüberschrift und wählen Sie **[!UICONTROL Nicht-standardmäßiges Attributionsmodell verwenden]** aus.
3. Wählen Sie **[!UICONTROL Erstkontakt]** mit einem für Ihre Analyse geeigneten Lookback-Fenster aus.

Alternativ können Sie das Bedienfeld [[!UICONTROL Attribution] verwenden](/help/analysis-workspace/c-panels/attribution.md) um einen direkten Vergleich der Leistung von Erstkontakt- und Letztkontakt-Kanälen durchzuführen.

+++

+++Traffic-Erfassung (sitzungsbasiert)

Der Traffic-Erfassungsbericht von GA4 ordnet jede Sitzung dem Kanal, der Quelle und dem Medium zu, die bzw. das sie initiiert hat, wobei die sitzungsbasierte Attribution verwendet wird. Sie können sie nach standardmäßiger Kanalgruppe, Quelle/Medium, Referrer oder Kampagne aufschlüsseln.

In Analysis Workspace **[!UICONTROL die Dimension]** Marketing-Kanal“ mit dem standardmäßigen **[!UICONTROL Letztkontakt]**-Attributionsmodell sitzungsbasierte Kanalberichte:

1. Ziehen Sie die Dimension **[!UICONTROL Marketing]** Kanal) in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Ziehen Sie die gewünschten Metriken neben die Standardmetrik **[!UICONTROL Ereignisse]** .

Die Aufschlüsselungen von GA4 werden diesen Customer Journey Analytics-Dimensionen zugeordnet:

* **channel**: **[!UICONTROL Marketing-Kanal]**. Customer Journey Analytics verfügt über keine integrierten Kanalgruppierungen - sie werden mithilfe der Funktionsvorlage „Marketing[Kanäle](/help/data-views/derived-fields/derived-fields.md) als **[!UICONTROL abgeleitetes Feld definiert oder Regeln]** Adobe Analytics übernommen, wenn der Analytics-Quell-Connector verwendet wird (siehe &quot;[ von Marketing-Kanal-Dimensionen ](/help/use-cases/aa-data/marketing-channels.md)).
* **Source/Medium und Empfehlungen**: **[!UICONTROL Referrer-]** und **[!UICONTROL Referrer-Typ]**.
* **Kampagne**: Die `utm_*` Parameter von GA4 werden nicht automatisch erfasst. Jeder muss während der Implementierung einem XDM-Feld zugeordnet werden, bevor es als Dimension angezeigt wird. Wenn Kampagnenwerte als Trackingcode eingehen, verwenden Sie die Dimension **[!UICONTROL Trackingcode]** .

+++

+++Attributions- und Konversionspfade

Die Attributionsberichte von GA4 (unter Advertising) zeigen, wie verschiedene Kanäle zu Konversionen beitragen und ermöglichen Modellvergleiche und Konversionspfadanalysen.

Verwenden Sie in Analysis Workspace das Bedienfeld [[!UICONTROL Attribution] : ](/help/analysis-workspace/c-panels/attribution.md)

1. Wählen Sie das Symbol Bedienfelder aus und ziehen Sie ein Bedienfeld **[!UICONTROL Attribution]** auf die Arbeitsfläche.
2. Ziehen Sie die Dimension **[!UICONTROL Marketing]** Kanal) in das Feld **[!UICONTROL Dimension hinzufügen]**.
3. Ziehen Sie Ihre Konversionsmetrik (z. B. ein Kaufereignis) in das Feld **[!UICONTROL Metrik hinzufügen]**.
4. Wählen Sie **[!UICONTROL Erstellen]** aus.

Das [!UICONTROL Attributionsbedienfeld] erstellt eine Modellvergleichstabelle und eine [!UICONTROL Kanalfluss]-Visualisierung, die die wichtigsten Pfade anzeigt, die Besucher vor der Konvertierung verwendet haben. Wählen Sie **[!UICONTROL Modell hinzufügen]** aus, um mehrere Attributionsmodelle gleichzeitig zu vergleichen.

+++

## Interaktion

+++Seiten und Bildschirme

Der Bericht „Seiten und Bildschirme“ von GA4 zeigt Leistungsmetriken für einzelne Seiten und Anwendungsbildschirme an.

Ziehen Sie in Analysis Workspace die Dimension **[!UICONTROL Seite]** in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) und fügen Sie Ihre gewünschten Metriken hinzu. Zu den gebräuchlichen Metriken gehören ****, **[!UICONTROL Personen]**, **[!UICONTROL Absprungrate]** und **[!UICONTROL Aufgewendete Zeit pro Sitzung]**.

Um Seiten nach URL-Pfadstruktur zu gruppieren (z. B. `/blog/` oder `/products/`), verwenden Sie die Dimension **[!UICONTROL Site-Bereich]** , wenn Ihre Implementierung sie definiert, oder erstellen Sie ein [abgeleitetes Feld](/help/data-views/derived-fields/derived-fields.md) das die Seiten-URL mit der Funktion **[!UICONTROL URL Parse]** analysiert. Wenn Sie eine explizite Zuordnung von Seite zu Abschnitt beibehalten, kann stattdessen ein [Lookup](/help/connections/standard-lookups.md)Datensatz) die Gruppierung bereitstellen.

+++

+++Landingpages

Der Landingpage-Bericht von GA4 zeigt an, auf welchen Seiten Benutzer zu Beginn einer Sitzung ankommen.

Ziehen Sie in Analysis Workspace die Dimension **[!UICONTROL Einstiegsseite]** in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). **[!UICONTROL Sitzungen]** ist die wichtigste Metrik für diese Dimension.

+++

+++Ereignisse

Der Ereignisbericht von GA4 zeigt an, wie oft jedes Ereignis ausgelöst wurde, mit Metriken auf Ereignisebene.

In GA4 haben Ereignisse einen Namen und optionale Parameter (z. B. `video_play` mit `video_title`). In Customer Journey Analytics lautet die Standarddimension für den Ereignisnamen **[!UICONTROL Ereignistyp]** (aus `xdm.eventType`). Ereignisparameter werden anderen XDM-Feldern zugeordnet, deren Namen von Ihrer Implementierung abhängen.

Ziehen Sie die Dimension **[!UICONTROL Ereignistyp]** in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), um alle Ereignistypen neben der Metrik **[!UICONTROL Ereignisse]** aufzulisten.

+++

+++Wichtige Ereignisse (Konversionen)

Der Bericht zu Schlüsselereignissen von GA4 (früher Konversionen) listet jedes Schlüsselereignis nach Name mit der Anzahl auf. Ereignisse, die in der GA4-Eigenschaftskonfiguration als geschäftskritisch gekennzeichnet sind.

Customer Journey Analytics verfügt über keine Markierung „Schlüsselereignis“. Jede Interaktion ist ein Ereignis, sodass keine voreingestellte Liste der Konversionen geöffnet werden kann.

Um die Konversionsliste von GA4 nach Namen neu zu erstellen, verwenden Sie **Segmente als Zeilen**. Eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) kann eine Metrik nicht an der Zeilenposition platzieren, aber sie kann dort ein Segment platzieren:

1. Erstellen Sie für jede Konversion ein Segment, das seine Ereignisse isoliert, z. B. ein Segment im Ereignisbereich, in dem `xdm.eventType` gleich `commerce.purchases`. Benennen Sie jedes Segment nach der Konversion, die es darstellt (z. B **„Käufe**).
2. Ziehen Sie jedes Konversionssegment in den Zeilenbereich einer [!UICONTROL Freiformtabelle], einen pro Zeile.
3. Fügen Sie **[!UICONTROL Metrik]** Ereignisse“ als Spalte hinzu. Jede Zeile zeigt die Anzahl dieser Konvertierung an und spiegelt die Liste der Schlüsselereignisse von GA4 wider. Verwenden Sie **[!UICONTROL Personen]**, um eindeutige Konverter zu zählen.

Um eine Konversionsrate hinzuzufügen, erstellen Sie eine berechnete Metrik (wählen Sie das Symbol **+** neben der Metrikliste aus), die als Konversionsmetrik dividiert durch **[!UICONTROL Sitzungen]** oder **[!UICONTROL Personen]** definiert ist.

Jede Konvertierung, die Sie hier isolieren, kann auch als wiederverwendbare Metrik in Ihrer Datenansicht definiert werden. Wie Sie dies einrichten können, erfahren Sie **Eintrag „Schlüsselereignisse → Benutzerdefinierte**&quot; unter [Allgemeine ](#common-metrics)&quot;.

+++

## Monetarisierung

+++E-Commerce-Käufe

Der E-Commerce-Kaufbericht von GA4 zeigt Kaufdaten auf Produktebene einschließlich Artikel, Umsatz und Menge an.

In Customer Journey Analytics verwenden E-Commerce-Berichte die Dimension **[!UICONTROL Produkt]** neben Kaufmetriken. Dieser Bericht erfordert, dass Ihre Implementierung XDM-Commerce-Daten (z. B. `xdm.commerce.purchases`, `xdm.commerce.order` und `xdm.productListItems`) sendet.

1. Ziehen Sie die Dimension **[!UICONTROL Produkt]** in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Ziehen Sie E-Commerce-Metriken **[!UICONTROL Bestellungen]**, **[!UICONTROL Umsatz]** und **[!UICONTROL Einheiten]** neben die Metrik **[!UICONTROL Ereignisse]**.

+++

+++Journey (funnel) kaufen

Der Bericht „Kauf-Journey&quot; von GA4 zeigt, wie Benutzende Ihre Einkaufs-funnel durchlaufen - z. B. vom Hinzufügen zum Warenkorb, um mit dem Kaufen zu beginnen - und wo sie abbrechen.

Verwenden Sie in Analysis Workspace die [**[!UICONTROL Fallout]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)-Visualisierung:

1. Wählen Sie das Symbol Visualisierungen aus und ziehen Sie eine **[!UICONTROL Fallout]**-Visualisierung auf die Arbeitsfläche.
2. Suchen Sie die Dimension **[!UICONTROL Seite]** und erweitern Sie sie, um einzelne Seitenwerte anzuzeigen.
3. Ziehen Sie den ersten funnel-Schritt (z. B. eine Produktseite) in den ersten **[!UICONTROL Touchpoint hinzufügen]**-Steckplatz.
4. Fügen Sie für jeden Schritt weitere Touchpoints hinzu.

Die Fallout-Visualisierung akzeptiert jede Dimension, jede Metrik oder jedes Segment als Touchpoint und nicht nur als Seiten, sodass sie mit den ereignisbasierten Trichtern von GA4 übereinstimmt und sich auf Sequenzen erstreckt, in denen Ereignisse, Seiten und Segmente gemischt werden.

+++

+++Promotions

Der Bericht zu Promotions von GA4 zeigt, wie interne Promotions (Banner, vorgestellte Platzierungen) die Produktinteraktionen fördern.

In Customer Journey Analytics müssen Sie für Promotion-Daten Promotion-Impressions und -Klicks in XDM-Schemafeldern erfassen. Erstellen Sie nach der Erfassung eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) die die Dimension Promotion-Name mit Impression- und Klickmetriken enthält. Wenden Sie sich an Ihren Customer Journey Analytics-Administrator, um zu bestätigen, welche Promotion-Daten in Ihrer Datenansicht verfügbar sind.

+++

+++Publisher-Anzeigen

Der Bericht zu Publisher-Anzeigen von GA4 zeigt den Anzeigenumsatz von Google Ad Manager oder AdMob für von Publisher monetarisierte Eigenschaften an.

Customer Journey Analytics verfügt über keine native Publisher-Anzeigenumsatzintegration. Um diese Daten zu melden, nehmen Sie die Umsatzzahlen von Ihrer Anzeigenmonetarisierungsplattform (z. B. Google Ad Manager oder AdMob) mithilfe eines Quell-Connectors oder der direkten Datenaufnahme als Datensatz in Adobe Experience Platform auf. Nach der Aufnahme sind die Daten für das Reporting in Customer Journey Analytics verfügbar.

+++

## Kundentreue

+++Aufbewahrungsübersicht

Der Bericht „Bindungsübersicht“ von GA4 kombiniert mehrere Bindungsansichten - neue gegenüber wiederkehrende Benutzende und ein Kohortendiagramm, das anzeigt, wie viele Benutzende im Laufe der Zeit zurückkehren.

**Neue im Vergleich zu wiederkehrenden**: Verwenden Sie die Segmente **[!UICONTROL Erste]**) und **[!UICONTROL Wiederkehrende Sitzungen]** als Zeilen in einer [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md):

1. Ziehen Sie das Segment **[!UICONTROL Erste Sitzung]** aus dem Bedienfeld „Komponenten“ in den Zeilenbereich der Tabelle und ziehen Sie dann das Segment **[!UICONTROL Wiederkehrende Sitzungen]** darunter.
2. Fügen Sie Ihre gewünschten Metriken zusammen mit der Standardmetrik **[!UICONTROL Ereignisse]** hinzu.
3. Um einen Trend im Zeitverlauf zu verfolgen, ziehen Sie eine [**[!UICONTROL Linie]**](/help/analysis-workspace/visualizations/line.md)-Visualisierung über die Tabelle und klicken Sie dann bei gedrückter Strg- (Windows) bzw. Befehlstaste (Mac) auf jede Zeile, um beide Segmente zu markieren.

**Bindung im Zeitverlauf**: Verwenden der Visualisierung [**[!UICONTROL Kohortentabelle]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Wählen Sie das Symbol Visualisierungen aus und ziehen Sie eine **[!UICONTROL Kohortentabelle]** auf die Arbeitsfläche.
2. Ziehen Sie die Metrik **[!UICONTROL Personen]** sowohl in die Felder Einschlusskriterium als auch Rückgabekriterium und wählen Sie dann **[!UICONTROL Erstellen]** aus.

Die [!UICONTROL Kohortentabelle] gruppiert Personen nach ihrem anfänglichen Zeitraum und verfolgt das Rückkehrverhalten über nachfolgende Zeiträume. Die Einschluss-, Rückgabe- und Granularitätskriterien sind alle konfigurierbar.

+++

## Benutzer

+++Demografische Details

Der Bericht „Demografische Details“ von GA4 behandelt Benutzermerkmale - Alter, Geschlecht und Interessen (unterstützt durch Google Signals, was erfordert, dass Benutzende bei einem Google-Konto mit aktivierter Personalisierung angemeldet sind) - sowie Standort (Land, Region, Stadt) und Sprache.

**Standort** wird direkt den Customer Journey Analytics-Dimensionen zugeordnet: Verwenden Sie **[!UICONTROL Länder]**, **[!UICONTROL Regionen]** oder **[!UICONTROL Städte]** in einer [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) oder die [[!UICONTROL Map]](/help/analysis-workspace/visualizations/map.md)-Visualisierung für eine geografische Übersicht (ziehen Sie die **[!UICONTROL Personen]**-Metrik in den **[!UICONTROL Metrik hinzufügen]**-Slot und wählen Sie **[!UICONTROL Erstellen]**.

**Alter, Geschlecht und Interessen** erfordern First-Party-Daten. Wenn Ihr Unternehmen demografische Daten über CRM, Registrierungsformulare oder einverständnisbasierte Umfragen erfasst, nehmen Sie sie als [Profildatensatz](/help/connections/create-connection.md#profile-dataset) auf und verbinden Sie sie mit Ereignisdaten. Dieser Ansatz erzeugt zuverlässigere Daten als das abgeleitete Google-Signalmodell von GA4, da es einvernehmliche First-Party-Attribute verwendet.

+++

+++Technische Details

Der technische Bericht von GA4 zeigt die Kategorien Browser, Betriebssystem, Bildschirmauflösung und Gerät an.

In Analysis Workspace sind die folgenden Dimensionen den technischen Dimensionen von GA4 zugeordnet, die jeweils aus einem Standard-XDM-Feld bezogen werden:

| GA4 - Technische Dimension | Analysis Workspace-Dimension | XDM-Feld |
|---|---|---|
| Browser | **[!UICONTROL Browser]** | `xdm.environment.browserDetails.name` |
| Betriebssystem | **[!UICONTROL Betriebssystem]** | `xdm.environment.operatingSystem` |
| Bildschirmauflösung | **[!UICONTROL Bildschirmauflösung]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| Gerätekategorie (Mobil, Desktop, Tablet) | **[!UICONTROL Mobilgerätetyp]** | `xdm.device.type` |
| Gerätemodell | **[!UICONTROL Mobilgerät]** | `xdm.device.model` |

Ziehen Sie eine dieser Dimensionen aus dem Bedienfeld Komponenten in eine [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

>[!NOTE]
>
>Da moderne Browser die Details in der Benutzeragenten-Zeichenfolge reduziert haben, hängen vollständige und genaue Werte von der Erfassung von [Benutzeragenten-Client-](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints)) in Ihrer Web SDK-Konfiguration ab.

+++

## erkunden

+++Freiformexploration

Die Freiform-Exploration von GA4 ist eine leere Arbeitsflächen-Tabelle mit konfigurierbaren Zeilen, Spalten und optionalen Diagrammüberlagerungen.

Analysis Workspaces [**[!UICONTROL Freiformtabelle]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ist das direkte Äquivalent und die Grundlage der meisten Workspace-Projekte. Ziehen Sie eine beliebige Dimension in die Zeilen, eine beliebige Metrik in die Spalten und ein beliebiges Segment in den Ablegebereich für Segmente über der Tabelle.

Siehe [Erste Schritte in Analysis Workspace](home.md#getting-started-in-analysis-workspace) für die Terminologiezuordnung zwischen GA4-Explorer und Workspace.

+++

+++Funnel-Exploration

Die Funnel-Exploration von GA4 definiert eine Abfolge von Schritten und misst Abschluss und Abbruch bei jedem Schritt.

Verwenden Sie in Analysis Workspace die [**[!UICONTROL Fallout]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)-Visualisierung:

1. Wählen Sie das Symbol Visualisierungen aus und ziehen Sie eine **[!UICONTROL Fallout]**-Visualisierung auf die Arbeitsfläche.
2. Ziehen Sie die Dimension, Metrik oder das Segment, die bzw. das Ihren ersten Schritt darstellt, in den ersten **[!UICONTROL Touchpoint hinzufügen]**-Slot.
3. Fahren Sie mit dem Hinzufügen eines Touchpoints für jeden nachfolgenden Schritt in der Sequenz fort.

Da jede Dimension, jede Metrik oder jedes Segment als Touchpoint dienen kann, stimmt [!UICONTROL Fallout] mit den ereignisbasierten Trichtern von GA4 überein und erstreckt sich auf kanalübergreifende Sequenzen, in denen Ereignisse, Seiten und Segmente gemischt werden.

+++

+++Pfadforschung

Die Pfadforschung von GA4 (Universal Analytics namens This Users Flow) visualisiert die Sequenzen von Seiten oder Ereignissen, durch die Benutzer navigieren.

Verwenden Sie in Analysis Workspace die [**[!UICONTROL Fluss]**](/help/analysis-workspace/visualizations/c-flow/flow.md)-Visualisierung:

1. Wählen Sie das Symbol Visualisierungen aus und ziehen Sie eine **[!UICONTROL Fluss]**-Visualisierung auf die Arbeitsfläche.
2. Ziehen Sie einen Wert aus der Dimension, der Sie den Pfad zuweisen möchten (z. B **[!UICONTROL einen]** Seiten- oder **[!UICONTROL Ereignistyp]**-Wert) in die Mitte des Flusses.
3. Die Visualisierung zeigt, was Benutzer vor und nach diesem Zeitpunkt getan haben.

Die [!UICONTROL Fluss]-Visualisierung ist interaktiv - wählen Sie einen beliebigen Knoten aus, um Pfade in beide Richtungen weiter zu erweitern. Es kann eine beliebige Dimension verwendet werden, sodass Sie Pfade auf Seiten, Ereignissen, Marketing-Kanälen oder benutzerdefinierten Links erstellen können.

+++

+++Segmentüberschneidung

Die Untersuchung der Segmentüberschneidung bei GA4 zeigt, wie sich mehrere Benutzersegmente überschneiden, visualisiert als Venn-Diagramm.

Verwenden Sie in Analysis Workspace die [**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md)-Visualisierung:

1. Wählen Sie das Symbol Visualisierungen aus und ziehen Sie eine **[!UICONTROL Venn]**-Visualisierung auf die Arbeitsfläche.
2. Ziehen Sie bis zu drei Segmente aus dem Bedienfeld Komponenten in die Visualisierung.

Das Venn-Diagramm zeigt Schnittmengen, und die [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) darunter zeigt die zugrunde liegenden Daten.

+++

+++Kohortenforschung

Die Kohorten-Exploration von GA4 gruppiert Benutzende nach einem gemeinsamen Merkmal (in der Regel Akquisitionsdatum) und verfolgt ihr Verhalten im Laufe der Zeit.

Verwenden Sie in Analysis Workspace die Visualisierung [**[!UICONTROL Kohortentabelle]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Wählen Sie das Symbol Visualisierungen aus und ziehen Sie eine **[!UICONTROL Kohortentabelle]** auf die Arbeitsfläche.
2. Ziehen Sie die **[!UICONTROL Personen]**-Metrik in die Felder Einschlusskriterium und Rückgabekriterium .
3. Wählen Sie **[!UICONTROL Erstellen]** aus.

Die [!UICONTROL Kohortentabelle] gruppiert Personen nach ihrem Anfangszeitraum und verfolgt das Rückkehrverhalten über nachfolgende Zeiträume. Standardmäßig erfolgt die Kohorte am Akquisitionsdatum, aber die Einschluss-, Rückgabe- und Granularitätskriterien sind alle konfigurierbar.

+++

+++Benutzer-Explorer

Der User Explorer von GA4 zeigt einzelne Benutzer, ihren Sitzungsverlauf und eine Zeitleiste von Ereignissen an.

Customer Journey Analytics unterstützt Analysen auf Benutzerebene auf zwei Arten:

* **Bei aktivierter**: Erstellen Sie einen Segmentbereich für einen bestimmten Personen-ID-Wert und wenden Sie ihn auf jedes Workspace-Projekt an. Der **[!UICONTROL Person]**-Container isoliert die zusammengefügten Aktivitäten dieses Kontakts über Sitzungen und Kanäle hinweg.
* **Rohe Ereignisdaten**: Verwenden Sie **Datensatzvorschau** in der Adobe Experience Platform-Benutzeroberfläche, um unformatierte XDM-Ereignisdatensätze zu überprüfen. Diese Ansicht ist nützlich für die Validierung der Implementierung und das Debugging einzelner Ereignisse.

+++

+++Lebensdauer des Benutzers

Die User Lifetime Exploration von GA4 misst den kumulierten Wert und die Interaktion jedes Benutzers über seine gesamte Beziehung zu Ihrem Unternehmen hinweg und nicht innerhalb eines festen Datumsbereichs. Sie kombiniert historische Lebenszeitmetriken mit den maschinellen Lernprognosen von Google für die Kaufwahrscheinlichkeit, die Abwanderungswahrscheinlichkeit und den prognostizierten Umsatz.

Diese sind Customer Journey Analytics in zwei Teilen zugeordnet:

**Historischer Lebenszeitwert** ist nativ erreichbar. Da Customer Journey Analytics Berichte für Ihr gesamtes Datenaufbewahrungsfenster erstellt, können Sie einen langen Datumsbereich festlegen und den kumulierten Umsatz und die Interaktion jeder Person in diesem Lookback aggregieren. Mit Zuordnung oder einer persistenten Personen-ID verknüpft **[!UICONTROL Container]** Person“ diese Aktivität mit einer Person, und berechnete Metriken drücken den Wert pro Person aus. Das Ergebnis ist keine unbegrenzte Lebensdauer, sondern ein langer, konfigurierbarer Lookback, der etwa einer entspricht.

**Prognostizierter Lebenszeitwert** ist nicht integriert. Customer Journey Analytics verfügt über kein produktinternes Modell für Kaufwahrscheinlichkeit, Abwanderung oder prognostizierten Umsatz. Um prädiktive Werte zu verwenden, berechnen Sie sie extern (z. B. in einem CRM- oder Datenwissenschafts-Workflow) und bringen Sie sie in Customer Journey Analytics als Profildatensatz ein. Anschließend bringen Sie sie als Dimensionen oder Metriken an die Oberfläche. Adobe empfiehlt, bei der Entwicklung dieses Ansatzes mit einem Implementierungsberater zusammenzuarbeiten.

+++

## Allgemeine Metriken

+++Aktive Benutzer → Personen

Die **Aktive Benutzer** von GA4 zählt Benutzer, die mindestens eine engagierte Sitzung im Datumsbereich hatten.

In Customer Journey Analytics ist die nächste Entsprechung **[!UICONTROL Personen]**, eine Anzahl eindeutiger Personen-IDs im Datumsbereich. [!UICONTROL Personen] umfasst alle identifizierten Personen, unabhängig vom Interaktionsniveau. Daher ist dieser Wert bei Sites mit signifikantem passivem Traffic normalerweise höher als der der aktiven GA4-Benutzer.

Wenden Sie für einen genaueren Verhaltensvergleich ein [Segment für interaktive Sitzungen](compare-data.md#engaged-sessions) an, um die Metrik [!UICONTROL Personen] auf Benutzer anzuwenden, die Ihre Interaktionskriterien erfüllen.

+++

+++Interaktive Sitzungen → berechnete Metrik

Die &quot;**Sitzungen“ von GA4** Sitzungen, die 10 oder mehr Sekunden dauerten, zwei oder mehr Seitenansichten aufwiesen oder mindestens ein Schlüsselereignis enthielten.

Customer Journey Analytics verfügt über keine integrierte Metrik für engagierte Sitzungen . Sie definieren sie als Segment, das Ihre Interaktionskriterien erfasst und dann zusammen mit der Metrik **[!UICONTROL Sitzungen]** verwendet. Unter [Interaktionssitzungen](compare-data.md#engaged-sessions) finden Sie den empfohlenen Ansatz und erfahren, wie Sie daraus eine Interaktionsrate ableiten.

+++

+++Interaktionsrate → berechnete Metrik

Die „Interaktionsrate **von GA4** der Prozentsatz der Sitzungen, die interagiert wurden: Interaktionssitzungen dividiert durch die Gesamtzahl der Sitzungen.

Erstellen Sie sie in Customer Journey Analytics als berechnete Metrik aus Ihrer Definition für „Interaktive Sitzungen“. Eine [ Anleitung finden Sie ](compare-data.md#engagement-rate) „Interaktive Sitzungen“.

+++

+++Durchschnittliche Interaktionszeit → Besuchszeit pro Sitzung

Die &quot;**Interaktionszeit“ von GA4** die durchschnittliche Zeit an, die sich der Browser oder die App während interaktiver Sitzungen im Vordergrund befand.

Verwenden Sie in Customer Journey Analytics **[!UICONTROL Sitzungsdauer (Sekunden)]** um die verstrichene Zeit vom ersten Ereignis zum letzten Ereignis in einer Sitzung zu messen. Diese Komponente umfasst Zeiträume, in denen der Benutzer möglicherweise nicht aktiv war, sodass die Werte von der GA4-Messung abweichen können. Dies ist das nächste integrierte Äquivalent.

+++

+++Ereignisanzahl → Ereignisse

Die &quot;**&quot; von GA4** die Gesamtzahl der aufgezeichneten Ereignisse.

In Customer Journey Analytics lautet die äquivalente Metrik **[!UICONTROL Ereignisse]** - die Gesamtzahl der Ereignisdatensätze im Datensatz für den ausgewählten Datumsbereich und die angewendeten Segmente.

+++

+++Sitzungen → Sitzungen

In den **Sitzungen** von GA4 und in **[!UICONTROL Sitzungen]** von Customer Journey Analytics wird die Anzahl der Sitzungen in einem Datumsbereich gemessen. Die Anzahl kann aufgrund unterschiedlicher Sitzungsdefinitionsregeln unterschiedlich sein. Einzelheiten finden [ unter „Warum sich GA4- und Customer Journey Analytics](compare-data.md#sessions)Daten unterscheiden.

+++

+++Neue Benutzer → erstes Sitzungssegment, das auf Personen angewendet wird

Die **Neue Benutzer** von GA4 zählt Benutzer, die ihre erste Sitzung im ausgewählten Datumsbereich hatten.

In Analysis Workspace:

1. Suchen Sie das Segment **[!UICONTROL Erste Sitzung]** im Bedienfeld „Komponenten“.
2. Ziehen Sie ihn in den Ablegebereich für Segmente über Ihrer [[!UICONTROL Freiformtabelle]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
3. Verwenden Sie die Metrik **[!UICONTROL Personen]** zum Zählen eindeutiger neuer Personen.

+++

+++Absprungrate → Absprungrate (mit Einschränkungen)

Die „Absprungrate **von GA4** der Prozentsatz der Sitzungen, die nicht interagiert haben (unter 10 Sekunden, kein Schlüsselereignis, weniger als 2 Seitenaufrufe). Es ist der Kehrwert der Interaktionsrate.

Die Metrik **[!UICONTROL Absprungrate]** von Customer Journey Analytics verwendet standardmäßig eine andere Definition und kann pro Datenansicht konfiguriert werden. Diese Unterschiede führen zu wesentlich unterschiedlichen Zahlen, die unterschiedliche Verhaltensweisen messen.

Um die Absprungrate von GA4 in Customer Journey Analytics abzuschätzen, erstellen Sie eine Metrik für die Interaktionsrate und invertieren Sie sie mit einer zweiten berechneten Metrik, die als `1 - Engagement Rate` definiert ist. Informationen [ schrittweisen Erstellung finden ](compare-data.md#engagement-rate) unter „Interaktive Sitzungen .

Eine ausführliche Erläuterung [ Definitionsunterschieds finden Sie unter ](compare-data.md#bounce-rate)Warum sich GA4- und Customer Journey Analytics-Daten unterscheiden“.

+++

+++Schlüsselereignisse → Metriken für benutzerspezifische Ereignisse

Die **Schlüsselereignisse“ von GA4** früher Konversionen genannt) sind Ereignisse, die als wichtige Geschäftsergebnisse in der GA4-Eigenschaftskonfiguration bezeichnet werden.

In Customer Journey Analytics ist eine Konversion eine benutzerdefinierte Ereignismetrik, die in der Datenansicht konfiguriert ist. Jedes XDM-Ereignis kann als Metrik bereitgestellt werden und eine Metrik kann so festgelegt werden, dass sie anhand eines XDM-Feldwerts erhöht wird, z. B. eine **[!UICONTROL Purchases]**-Metrik, die erhöht wird, wenn `xdm.eventType` gleich `commerce.purchases` ist. Suchen Sie die entsprechende Metrik anhand ihrer Beschriftung im Bedienfeld „Komponenten“ von Analysis Workspace. Der Name spiegelt wider, wie Ihr Administrator sie konfiguriert hat.

Informationen zum Reproduzieren der Schlüsselereignisse von GA4 *Bericht* (eine Liste jeder Konversion mit ihrer Anzahl) finden Sie im **Schlüsselereignisse (Konversionen)** Eintrag unter [Interaktion](#engagement) auf dieser Seite.

+++

>[!MORELIKETHIS]
>
>* [Bericht zu Google Analytics-Daten](/help/use-cases/third-party/ga/report.md)
