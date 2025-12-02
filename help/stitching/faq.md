---
title: Häufig gestellte Fragen zum Stitching
description: Häufig gestellte Fragen zum Zusammenfügen
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2069'
ht-degree: 23%

---

# Häufig gestellte Fragen

Im Folgenden finden Sie einige häufig gestellte Fragen zum Zusammenfügen:

## Kanalübergreifend verschieben

+++ Wie kann ich Stitching verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [Customer Journey Analytics an &#x200B;](https://analytics.adobe.com) erstellen Sie ein leeres Workspace-Projekt.
2. Wählen Sie auf der linken Seite **[!UICONTROL ** Visualisierungen **]** aus und ziehen Sie eine **[!UICONTROL **&#x200B; Fluss &#x200B;**]**-Visualisierung auf die Arbeitsfläche auf der rechten Seite.
3. Wählen Sie auf der linken Seite **[!UICONTROL ** Komponenten **]** und ziehen Sie die Dimension **[!UICONTROL ** Datensatz-ID **]** an die mittlere Position mit der Bezeichnung **[!UICONTROL **&#x200B; Dimension oder Element &#x200B;**]**.
4. Dieser Flussbericht ist interaktiv. Um die Flüsse zu nachfolgenden oder vorherigen Seiten zu erweitern, wählen Sie einen der Werte aus. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

+++

## Wiederholen

+++ Wie weit zurück werden beim Zusammenfügen Wiederholprofile wiedergegeben?

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der Datenwiederholung ab. Wenn Sie beispielsweise das Zusammenfügen einrichten, um Daten einmal wöchentlich wiederzugeben, beträgt das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie die Zuordnung so einrichten, dass Daten jeden Tag wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung einen Tag.

+++

## Gemeinsam verwendete Geräte

+++ Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die Personen-ID überschreibt die persistente ID, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

Weitere Informationen finden Sie [&#x200B; Anwendungsbeispiel &#x200B;](/help/use-cases/stitching/shared-devices.md)Freigegebene Geräte“.

+++

## Viele persistente IDs

+++ Wie werden beim Zusammenfügen Situationen gehandhabt, in denen eine einzelne Person über viele persistente IDs verfügt?

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Ein Beispiel hierfür ist eine Person, die häufig Cookies des Browsers löscht oder den Privat-/Inkognito-Modus des Browsers verwendet.

Bei der feldbasierten Zuordnung ist die Anzahl der persistenten IDs zugunsten der Personen-ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit von Customer Journey Analytics auswirkt, Zuordnungen geräteübergreifend vorzunehmen.

Bei der diagrammbasierten Zuordnung kann eine einzelne Person über viele beständige IDs im Identitätsdiagramm verfügen. Diagrammbasiertes Stitching verwendet die persistente ID basierend auf dem angegebenen Namespace. Falls es persistentere ID für denselben Namespace gibt, wird die lexikografische erste persistente ID verwendet.

+++

## Heftvorgang

+++ Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar ist, nachdem ich meinem Adobe-Accountteam die gewünschten Informationen mitgeteilt habe?

Die Echtzeit-Zuordnung ist etwa eine Woche, nachdem Adobe die Zuordnung aktiviert hat, verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

+++

## Geräteübergreifende Analyse versus kanalübergreifende Analyse

+++ Was ist der Unterschied zwischen geräteübergreifender Analyse (eine Funktion im herkömmlichen Analytics) und kanalübergreifender Analyse?

[Geräteübergreifende Analyse](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) ist eine Funktion, die speziell für das herkömmliche Adobe Analytics entwickelt wurde und Ihnen hilft, zu verstehen, wie Benutzende geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

Die Cross-Channel-Analyse ist ein für Customer Journey Analytics spezifisches Anwendungsbeispiel, mit dem Sie verstehen können, wie benutzende Personen auf beiden Geräten und Kanälen arbeiten. Er verknüpft die Personen-ID eines Datensatzes, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion funktioniert im Design ähnlich wie die geräteübergreifende Analyse beim feldbasierten Stitching, aber die Implementierung unterscheidet sich aufgrund der unterschiedlichen Datenarchitektur von herkömmlichem Analytics und Customer Journey Analytics. Siehe [Zusammenfügen](overview.md) und den [Cross-Channel-Analyse](../use-cases/cross-channel/cross-channel.md)-Anwendungsfall für weitere Informationen.

+++

## Datenschutz

+++ Wie handhabt Stitching Datenschutzanfragen?

Adobe bearbeitet Datenschutzanfragen in Übereinstimmung mit lokalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

>[!IMPORTANT]
>
>Der Unstitching-Prozess im Rahmen von Datenschutzanfragen ändert sich Anfang 2025. Der aktuelle Unstitching-Prozess ordnet Ereignisse anhand der neuesten Version bekannter Identitäten neu zu. Diese Neuzuweisung von Ereignissen an eine andere Identität kann unerwünschte rechtliche Folgen haben. Um diese Bedenken zu beheben, werden Ereignisse, die Gegenstand der Datenschutzanfrage sind, ab 2025 durch den neuen Prozess zur Aufhebung der Zuordnung mit der persistenten ID aktualisiert.
> 

Zur Veranschaulichung stellen Sie sich die folgenden Daten für Identitäten, Ereignisse vor und nach dem Zusammenfügen vor.

| Identitätszuordnung | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-IO | Personen-Namespace |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ECID | Bob | CustId |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Ereignis-Datensatz | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| | 2 | ts1 | 123 | ECID | Bob | CustId |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Zusammengefügter Datensatz | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace | Zusammengefügte ID | Zusammengefügter Namespace |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | Bob | CustId |
| | 2 | ts1 | 123 | ECID | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |


**Aktueller Prozess für Datenschutzanfrage**

Wenn eine Datenschutzanfrage für einen Kunden mit CustID Bob empfangen wird, werden die Zeilen mit durchgestrichenen Einträgen gelöscht. Andere Ereignisse werden mithilfe der Identitätszuordnung neu zugeordnet. Beispielsweise wird die erste zusammengefügte ID im zusammengefügten Datensatz auf &quot;**&quot;**.

| Identitätszuordnung | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Ereignis-Datensatz | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Zusammengefügter Datensatz | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace | Zusammengefügte ID | Zusammengefügter Namespace |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |


**Neuer Prozess für Datenschutzanfrage**

Wenn eine Datenschutzanfrage für einen Kunden mit CustID Bob empfangen wird, werden die Zeilen mit durchgestrichenen Einträgen gelöscht. Andere Ereignisse werden mit der persistenten ID neu zugeordnet. Beispielsweise wird die erste zusammengefügte ID im zusammengefügten Datensatz auf **123)**.

| Identitätszuordnung | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Ereignis-Datensatz | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Zusammengefügter Datensatz | ID | timestamp | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace | Zusammengefügte ID | Zusammengefügter Namespace |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **123** | ECID |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |

+++

## Leere persistente ID-Werte

+++ Was passiert, wenn das Feld „Persistente ID“ in einem oder mehreren Ereignissen leer ist?

Wenn das Feld für persistente ID bei einem Ereignis in einem Datensatz, der zugeordnet wird, leer ist, wird die zugeordnete ID für dieses Ereignis auf eine dieser zwei Arten bestimmt:

* Wenn das Feld für die vorübergehende ID nicht leer ist, verwendet Customer Journey Analytics den Wert in der vorübergehenden ID als zusammengefügte ID.
* Wenn das Feld Vorübergehende ID leer ist, lässt Customer Journey Analytics auch die zugeordnete ID leer. In diesem Fall sind die Felder „Persistente ID“, „Vorübergehende ID“ und „Zugeordnete ID“ beim Ereignis leer. Diese Ereignistypen werden aus jeder Customer Journey Analytics-Verbindung herausgenommen, die den zugeordneten Datensatz verwendet, bei dem die zugeordnete ID als Personen-ID ausgewählt wurde.

+++


## Nicht definierte Personen-ID-Werte

+++ Was passiert, wenn das Personen-ID-Feld in einem oder mehreren Ereignissen Platzhalterwerte enthält, z. B. `Undefined`?

Seien Sie vorsichtig beim „Personen-Kollaps“, der auftritt, wenn das Zusammenfügen auf Daten angewendet wird, die Platzhalterwerte für vorübergehende IDs verwenden. In der folgenden Beispieltabelle werden undefinierte Personen-IDs, die aus einem Datensatz stammen, der aus einem CRM-System stammt, mit dem Wert „Undefiniert“ ausgefüllt, was zu einer falschen Darstellung von Personen führt.

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Vorübergehende ID | Zusammengefügte ID (nach der Wiederholung) |
|---|---|---|---|---|
| 1 | 12.05.2023:01 | 123 | – | **Cory** |
| 2 | 12.05.2023:02 | 123 | Cory | **Cory** |
| 3 | 12.05.2023:03 | 456 | Nicht definiert | **Nicht definiert** |
| 4 | 12.05.2023:04 | 456 | – | **Nicht definiert** |
| 5 | 12.05.2023:05 | 789 | Nicht definiert | **Nicht definiert** |
| 6 | 12.05.2023:06 | 012 | Nicht definiert | **Nicht definiert** |
| 7 | 12.05.2023:07 | 012 | – | **Nicht definiert** |
| 8 | 12.05.2023:03 | 789 | Nicht definiert | **Nicht definiert** |
| 9 | 12.05.2023:09 | 456 | – | **Nicht definiert** |
| 10 | 12.05.2023:02 | 123 | – | **Cory** |
| | | **4-Geräte** | **2 Personen**:<br/>Ereignisse 1, 4, 7, 9, 10 fallen gelassen | **2 Personen**:<br/>Cory, Nicht authentifiziert (für eine Person reduziert) |

+++

## Vergleich von Metriken

+++ Wie lässt sich ein Vergleich zwischen Metriken in zugeordneten Customer Journey Analytics-Datensätzen und ähnlichen Metriken in nicht zugeordneten Customer Journey Analytics-Datensätzen und mit Adobe Analytics vornehmen?

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken im herkömmlichen Analytics, andere unterscheiden sich jedoch je nachdem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete Customer Journey Analytics-Daten** | **Nicht zugeordnete Customer Journey Analytics-Daten** | **Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl unterschiedlicher Personen-IDs, bei denen die zusammengefügte ID als Personen-ID ausgewählt wird. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Anzahl unterschiedlicher Personen-IDs basierend auf der Spalte, die als Personen-ID ausgewählt wurde. **Personen** in Datensätzen des Analytics-Quell-Connectors ist ähnlich wie **Unique Visitors** im herkömmlichen Adobe Analytics, wenn `endUserIDs._experience.aaid.id` als Personen-ID in Customer Journey Analytics verwendet wird. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird anhand der Sitzungseinstellungen in der Customer Journey Analytics-Datenansicht definiert. Der Zuordnungsprozess kann einzelne Sitzungen auf mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der Customer Journey Analytics-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einer leeren persistenten ID. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass Ereignisse, die in den nicht zugeordneten Daten im Data Lake von Experience Platform eine leere Personen-ID aufweisen, nicht in Customer Journey Analytics aufgenommen werden. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). |

Andere Metriken können in Customer Journey Analytics und Adobe Analytics ähnlich sein. Beispielsweise ist die Gesamtanzahl für Adobe Analytics [benutzerspezifische Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) 1-100 im herkömmlichen Adobe Analytics und Customer Journey Analytics vergleichbar (unabhängig davon, ob zugeordnet oder nicht zugeordnet). [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen Customer Journey Analytics und Adobe Analytics, können zu Diskrepanzen zwischen den beiden Produkten führen.

+++

## Identitätszuordnung

+++ Kann Customer Journey Analytics Identity Map-Felder verwenden?

Ja, Customer Journey Analytics kann Identitätszuordnungsfelder sowohl für [&#x200B; (feldbasierte](/help/stitching/fbs.md#identitymap) als auch für [diagrammbasierte](/help/stitching/gbs.md#identitymap) Zuordnung verwenden.

+++

## Zu diagrammbasiertem Stitching wechseln

+++ Müssen Daten erneut aufgenommen werden, um von feldbasiertem Stitching zu diagrammbasiertem Stitching zu wechseln?

Daten müssen nicht erneut in Experience Platform aufgenommen werden. Sie müssen jedoch in Customer Journey Analytics neu konfiguriert werden. Führen Sie die folgenden Schritte aus:

1. Richten Sie den neuen diagrammbasierten zugeordneten Datensatz mithilfe der diagrammbasierten Zuordnung ein.
1. Erstellen Sie eine neue temporäre Verbindung mit einem sehr kleinen Zeitfenster an Daten.
1. Konfigurieren Sie den neuen diagrammbasierten Datensatz als Teil dieser temporären Verbindung.
1. Überprüfen Sie mit dieser neuen temporären Verbindung, ob das diagrammbasierte Stitching ordnungsgemäß funktioniert.
1. Wenn das diagrammbasierte Stitching erwartungsgemäß funktioniert, fordern Sie eine zusätzliche Aufstockung für den diagrammbasierten Datensatz an und tauschen Sie dann den feldbasierten Datensatz in Ihrer ursprünglichen Verbindung mit dem neuen diagrammbasierten Datensatz aus.
1. Entfernen Sie die temporäre Verbindung.

+++

## Unterbrechung des Reportings

+++ Würden bestehende Berichte in irgendeiner Weise beeinträchtigt?

Nicht, wenn Sie die oben beschriebenen Schritte befolgen. Andernfalls bitten wir Sie um zusätzliche Unterstützung bei Adobe Consulting.

+++

## Aktivieren eines Datensatzes für den Identity Service

+++ Wie wird ein Datensatz nur für den Identity Service aktiviert? 

Sie müssen sicherstellen, dass ein Datensatz für Identity Service aktiviert ist, damit der Datensatz beim diagrammbasierten Stitching verwendet werden kann.

Sie müssen für Real-Time Customer Data Platform nicht lizenziert sein, um das diagrammbasierte Stitching verwenden zu können. Die diagrammbasierte Zuordnung basiert auf einem verfügbaren Identitätsdiagramm und nicht auf Echtzeit-Kundenprofilen.

Um einen Datensatz nur für den Identity Service zu aktivieren, verwenden Sie eine `POST`-Anfrage an den `/datasets`-Endpunkt, der nur das `unifiedIdentity`-Tag verwendet. Zum Beispiel:

```shell
curl -X POST \
  https://platform.adobe.io/data/foundation/catalog/dataSets \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
    "schemaRef": {
        "id": "https://ns.adobe.com/{TENANT_ID}/schemas/31670881463308a46f7d2cb09762715",
        "contentType": "application/vnd.adobe.xed-full-notext+json; version=1"
    },
    "tags": {
       "unifiedIdentity": ["enabled:true"]
    }
  }'
```

Jede Verwendung des `unifiedProfile`-Tags in der Anfrage gibt einen Fehler zurück, obwohl Sie nicht für das Echtzeit-Kundendatenprofil lizenziert sind.

Weitere [&#x200B; finden Sie unter „Erstellen eines Datensatzes, der für Profil und &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/enable-for-profile#create-a-dataset-enabled-for-profile-and-identity) aktiviert ist“.

+++ 
