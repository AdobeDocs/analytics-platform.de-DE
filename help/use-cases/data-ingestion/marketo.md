---
title: Bericht zu Marketo Engage-Daten
description: Erfahren Sie, wie Sie Berichte zu Marketo Engage-Daten in Customer Journey Analytics erstellen
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
TQID: https://experienceleague.adobe.com/UXeVx5LF0ww0guz-62swqmGapSfjiTduYjojcZqqIYQ
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: e430f26e2b6357a288adb4389a266f26acab68c4
workflow-type: tm+mt
source-wordcount: 1448
ht-degree: 8%

---

# Bericht zu Marketo Engage-Daten

Sie können verfügbare Marketo Engage-Datensätze in Experience Platform nutzen, um B2B-Marketing-Experten wertvolle Analyse- und Reporting-Lösungen bereitzustellen. Danach können Sie einen Bericht zu diesen Datensätzen in Customer Journey Analytics erstellen.

Beachten Sie Folgendes:

* Marketo Engage-Berichte eignen sich am besten für die Messung und Optimierung von Marketing-Programmen direkt in Marketo und sind schnell, präskriptiv und marketerfreundlich.
* Customer Journey Analytics bietet eine viel breitere, anpassbare Analyselösung für Kunden-Journey, die mehrere Kanäle, Produkte und Geschäftsbereiche umfasst, einschließlich, aber nicht beschränkt auf Marketo-Daten.

Siehe [Berichtsvergleich](#reporting-comparison) für weitere Details.

>[!NOTE]
>
>Sie können die [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) in Betracht ziehen, um viel mehr Wert aus den Daten von Marketo Engage zu ziehen. Sie können Marketo Engage-Datensätze mit Konto- und Lookup-Datensätzen kombinieren. Und Berichte zur Konto- und Opportunity-Ebene in Customer Journey Analytics B2B edition erstellen.
>


Gehen Sie wie folgt vor, um Berichte zu Marketo Engage-Daten in Customer Journey Analytics zu erstellen:

+++ID-Strategie auswählen

Wenn Sie Marketo-Aktivitätsdaten in Customer Journey Analytics aufnehmen möchten, müssen Sie eine geeignete ID-Strategie auswählen, um sicherzustellen, dass Marketo-Daten mit Customer Journey Analytics-Daten verknüpft werden können.

Marketo-Daten enthalten nativ keine ECID, das ECID-Feld kann jedoch als benutzerdefiniertes Feld hinzugefügt werden, das mit der `munchkin.js`-Bibliothek erfasst wird. Durch diese Hinzufügung wird eine gemeinsame Kennung zwischen Marketo und vorhandenen Customer Journey Analytics-Web-Daten erstellt.

Um Marketo- und Customer Journey Analytics-Daten zu verknüpfen[ verwenden Sie das ](/help/stitching/gbs.md)-basierte Stitching für die entsprechenden Datensätze. Je nach Implementierung können Sie mehrere verfügbare IDs verwenden:

* ECID, bereitgestellt vom Experience Platform Identity Service
* E-Mail
* Munchkin-ID, bereitgestellt von Marketo Engage
* Händler-ID
* Dunn &amp; Bradstreet Duns\#
* Demandbase-ID
* (Potenziell andere)

Diagrammbasiertes Stitching hilft auf folgende Weise:

* Behält eine persistente ID für Web-Ereignisse bei.
* Verwendet das Identitätsdiagramm, um bekannte Identitäten (wie E-Mail) nach Möglichkeit aufzulösen.
* Wenn keine deterministische Übereinstimmung vorhanden ist, wird die diagrammbasierte Zuordnung auf die persistente ID zurückgesetzt, anstatt das Ereignis wegzulassen.

Diagrammbasiertes Stitching ist aus folgenden Gründen eine praktikable Lösung zur Verknüpfung von Marketo- und Customer Journey Analytics-Daten:

* Web-Ereignisdaten haben in jeder Zeile eine persistente ID (z. B. ECID).
* Marketo-Daten enthalten verlässliche IDs in den Daten mit Munckin-ID, ECID und E-Mail.
* Die diagrammbasierte Zuordnung überbrückt die ECID deterministisch mit der Munchkin-ID, der E-Mail-Adresse oder einer anderen ID, die in den Marketo-Daten verfügbar ist.
* Diagrammbasiertes Stitching verwendet die explizit konfigurierten Identitätsdiagramm-Verknüpfungsregeln und -Namespaces.

Um diese ID-Strategie zu überprüfen, sollten Sie ein gesteuertes diagrammbasiertes Stitching-Pilotprogramm ausführen.

1. Fügen Sie ECID als benutzerdefiniertes Feld in Marketo hinzu und fügen Sie das benutzerdefinierte Feld dem Client-seitigen JavaScript-Code von munckin.js für die Marketo Engage-Datenerfassung hinzu.
1. Richten Sie eine temporäre Kunden-Journey-Verbindung ein, die sowohl einen Marketo-Datensatz als auch einen Web-Ereignis-Datensatz enthält.
1. Definieren Sie einen engen Datenbereich, um eine begrenzte, aber darstellbare Datenmenge einzubringen.
1. Überprüfen Sie die Zuordnung durch Einrichtung einer Datenansicht und von Berichten in Workspace. Weitere Informationen finden Sie in den folgenden Schritten.

+++

+++Zuordnen von Marketo-Quelldatenfeldern zu ihren XDM-Zielen

Ordnen Sie die Objekte [Personen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) und [Aktivitäten](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) den jeweiligen XDM-Schema-Zielfeldern zu.

+++

+++Aufnehmen von Marketo-Daten in Adobe Experience Platform

Verwenden Sie den [Marketo Engage-Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo), um Daten aus Marketo in Experience Platform zu übertragen und mithilfe von Experience Platform-Programmen auf dem neuesten Stand zu halten.

+++

+++ Einrichten einer Verbindung zu diesem Datensatz in Customer Journey Analytics

Um Berichte zu Experience Platform-Datensätzen zu erstellen, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Customer Journey Analytics herstellen. Siehe [Erstellen oder Bearbeiten einer Verbindung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection).

+++


+++Eine oder mehrere Datenansichten erstellen

Eine [Datenansicht](/help/data-views/data-views.md) ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Sie enthält alle in Analysis Workspace verfügbaren Dimensionen und Metriken, in diesem Fall für Marketo spezifische Metriken und Dimensionen. Die Datenansicht gibt auch an, aus welchen Spalten diese Dimensionen und Metriken ihre Daten beziehen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

+++ 

+++Bericht in Analysis Workspace

Ein möglicher Anwendungsfall ist: Wie viele Web-Seitenbesuche durch Leads hatten Sie im April/Juni 2020?

1. Öffnen Sie [Analytics Workspace](/help/analysis-workspace/home.md) und erstellen Sie ein neues Projekt.
Kunden mit B2B/B2P CDP können eine B2C-Analyse in Customer Journey Analytics durchführen. B2B-Objekte sind noch nicht verfügbar.

1. Erstellen Sie [Segment](/help/components/segments/seg-create.md) für Web-Seitenansichten wie folgt: Ereignistyp = web.webpagedetails.pageViews :

   ![Definitionsfenster mit Ereignis- und Ereignistyp](../assets/marketo-filter.png)

1. Ziehen Sie das Segment, das Sie erstellt haben, in die Freiformtabelle - Web-Seitenansichten und rufen Sie dann den Datumsbereich „Monat“ ab. Mit dieser Aktion erhalten Sie monatliche Web-Seitenbesuche nach Leads:

   ![Freiformtabelle mit Ereignissen nach Monat.](../assets/marketo-freeform.png)

1. Oder ziehen Sie die folgenden Dimensionen in die Tabelle: Personen-Schlüssel oder geschäftliche E-Mail-Adresse. Mit dieser Aktion erhalten Sie die Web-Seitenbesuche nach Lead:

   ![Freiformtabelle mit Ereignissen und „workEmail.Address“ und Web-Seitenansichten.](../assets/marketo-freeform2.png)

Marketo Engage-Daten in Customer Journey Analytics können sich von denen in den Berichten in Marketo Engage unterscheiden.

+++


## Vergleich von Berichten

Im folgenden Vergleich zwischen Berichten in Customer Journey Analytics und Marketo Engage werden einige wichtige Unterschiede in den Analytics-Funktionen, der Flexibilität, den Wahrheitsquellen und Anwendungsfällen beschrieben.

### Customer Journey Analytics

Customer Journey Analytics ist ein erweitertes Tool zur kanalübergreifenden Analyse, das auf Adobe Experience Platform basiert. Customer Journey Analytics wurde für Unternehmens-Teams entwickelt, die leistungsstarke, flexible und anpassbare Berichte über digitale und Offline-Datenquellen hinweg benötigen.

#### Wichtige Funktionen

* **Datenquellen**: Kann mehrere Datensätze kombinieren (Web, CRM, E-Mail, Callcenter, Offline, Marketo usw.), für 360°-Kunden-Journey-Reporting.
* **Self-Service-Analyse**: Arbeitsbereich per Drag-and-Drop mit hochgradig interaktiven, anpassbaren Dashboards und Visualisierungen.
* **Erweiterte Attribution**: Unterstützt komplexe, Multi-Touch- und benutzerdefinierte Attributionsmodelle für alle verbundenen Daten, nicht nur für Marketing-Programme.
* **Zielgruppen- und Pfadanalyse**: Detaillierte Segmentierung, Kohorten- und Pfadanalyse in Käufer-Journey.
* **Verwertbare Insights**: Aktiviert die datengesteuerte Orchestrierung (z. B. sendet Insights zurück zu Marketing- oder Personalisierungs-Engines).
* **Enterprise Scale**: Geeignet für Organisationen, die eine Unternehmens-Governance, mehrere Marken und ein hohes Datenvolumen benötigen.

#### Typische Customer Journey Analytics-Anwendungsfälle

* Erweiterte Kunden-Journey-Zuordnung über mehrere Kanäle und Touchpoints hinweg.
* Komplexe Segmentierung und Mischung von Online- und Offline-Daten.
* Benutzerdefinierte KPI-Dashboards für das Reporting auf Führungsebene und für den Betrieb.
* Ganzheitliche Attributionsmodellierung (über digitale oder E-Mail hinaus).


### Marketo Engage

Marketo Engage bietet In-App-Berichte, die sich auf KPIs zur Marketing-Automatisierung, Programm- und Kampagnenmessung und die Analyse der Marketing-Auswirkungen konzentrieren. Alle diese Berichte sind direkt mit Aktivitäten in Marketo verknüpft.

#### Wichtige Funktionen

* **Native Marketing-**: Standardberichte für E-Mail, Landingpages, Kampagnen, Leads, Opportunities, Pipeline und Umsatzzuordnung (zuerst, zuletzt, Multi-Touch).
* **Advanced BI Analytics (Add-on)**: Erstellen von benutzerdefinierten Berichten mit Drag-and-Drop und Point-and-Click zur Analyse von Programm-/Konto-/Lead-Daten (siehe Übersicht über Advanced BI Analytics).
* **Vordefinierte Dashboards**: Für Kampagnenleistung, Kanaleffektivität und Pipeline-/Umsatzbeitrag.
* **Programm- und Kanalanalyse**: Attribution und ROI speziell für von Marketo verwaltete Journey.
* **Marketing-orientiert**: Mit Fokus auf Benutzende, die Transparenz in der Marketing-funnel benötigen: E-Mail-Statistiken, Formulare, intelligente Kampagnen und Auswirkungen auf den Umsatz.


#### Typische Marketo Engage-Anwendungsfälle

* Tracking und Optimierung der E-Mail-, Programm- und Kampagnenleistung.
* Ordnen Sie Leads und Pipelines Marketing-Taktiken zu.
* Überwachen Sie Interaktionstrends und bewerten Sie Leads.
* Teilen Sie Einblicke mit Vertriebs-/Marketing-Teams ohne Data Engineering-Ressourcen.
* Zugriff auf sofort einsatzbereite, marketerfreundliche Berichte.


Unten finden Sie eine kurze Vergleichstabelle zu den Reporting-Funktionen von Marketo Engage und Customer Journey Analytics:

| Funktion | Marketo Engage | Customer Journey Analytics |
|---|---|---|
| **Primärer Fokus** | Marketing-Programm und kampagnenorientierte Berichterstattung. | Ganzheitliches Omni-Channel-Journey und Verhaltensanalysen und Reporting. |
| **Datenquellen** | In und über Marketo Engage generierte Daten. | Kombiniert Daten aus allen Experience Platform-aktivierten Daten, einschließlich Marketo, Website, Mobile App, Offline-Kanälen und mehr. |
| **Attribution** | Einzel- und Multi-Touch-Attribution auf Marketo-Daten. | Benutzerdefinierte, kanalübergreifende Attribution für alle in der Lösung verfügbaren Daten. |
| **Benutzerdefiniertes Reporting und Flexibilität** | Erweitertes BI (Add-on) für umfassende Einblicke in Programme und Konten. | Hohe Flexibilität beim Erstellen von benutzerdefinierten Arbeitsbereichen, Dashboards oder Berichten mit allen verfügbaren Daten. |
| **Zielgruppenanalyse** | Filtern und Segmentieren von Programmlisten, Interaktionen und Smart-Listen. | Umfangreiche Persona- und Journey-Visualisierungen, Zielgruppenpfade und Segmentüberschneidungsanalysen. |
| **Vorgesehene Benutzer** | Marketingexperten, Marketing-Operatoren, Nachfrager, Umsatzverantwortliche. | Analysten, Datenwissenschaftler, Marketing-Strategen, Fachleute für Kundenerlebnisse. |
| **Deduplizierung einer Metrik** | Bei E-Mail-Leistungsberichten werden Metriken automatisch nach Lead-ID, Kampagnen-ID und E-Mail-Asset-ID dedupliziert. Wenn mehrere E-Mails aus demselben E-Mail-Asset erstellt und vom selben Programm an denselben Lead gesendet werden, werden diese E-Mails nur als eine gezählt. | Ohne zusätzliche Filter und Metriken werden die E-Mail-Berichtsdaten als Gesamtanzahl der E-Mail-Leistung ohne [Metrikdeduplizierung](/help/data-views/component-settings/metric-deduplication.md) gemeldet. |

{style="table-layout:fixed"}
