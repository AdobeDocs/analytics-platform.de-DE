---
title: Häufig gestellte Fragen zur Zuordnung
description: Erfahren Sie mehr über häufig gestellte Fragen zum Zusammenfügen.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
TQID: https://experienceleague.adobe.com/0y2eqwQxkHefcODFhxXCuioMnL-YCXm21335Z2upPB0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 19cf20236196ab9c2518bf299a36d32f65210227
workflow-type: tm+mt
source-wordcount: 2373
ht-degree: 71%

---

# Häufig gestellte Fragen

Im Folgenden finden Sie einige häufig gestellte Fragen zur Zuordnung:

## Kanalübergreifendes Verschieben

**Frage** Wie kann ich Stitching verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

+++Antwort

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und erstellen Sie ein leeres Workspace-Projekt.
2. Klicken Sie auf der linken Seite auf die Registerkarte **[!UICONTROL ** Visualisierungen **]** und ziehen Sie eine **[!UICONTROL ** Fluss **]**-Visualisierung in die Arbeitsfläche auf der rechten Seite.
3. Klicken Sie auf die Registerkarte **[!UICONTROL ** Komponenten **]** auf der linken Seite und ziehen Sie die Dimension **[!UICONTROL ** Datensatz-ID **]** an die mittlere Position mit der Bezeichnung **[!UICONTROL ** Dimension oder Element **]**.
4. Dieser Flussbericht ist interaktiv. Um die Flüsse auf nachfolgende oder vorherige Seiten zu erweitern, wählen Sie einen der Werte aus. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

+++

## Wiederholung

**Frage**: Wie weit zurück wiederholt das Zusammenfügen von Profilen?

+++Antwort

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der Datenwiederholung ab. Wenn Sie beispielsweise die Zuordnung so einrichten, dass Daten einmal wöchentlich wiederholt werden, umfasst das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie die Zuordnung so einrichten, dass Daten jeden Tag wiederholt werden, umfasst das Lookback-Fenster für die Neuzuweisung einen Tag.

+++

**Frage**: Wann wird der Wiederholungsprozess genau ausgeführt?

+++Antwort

* Die **wöchentliche** Wiederholung beginnt jeweils **Samstag** abends (Zeitzone des Kunden) und die Daten werden in Customer Journey Analytics-Berichten bis Montagmorgen aktualisiert.
* Die **tägliche** Wiederholung wird um **3** (Zeitzone des Kunden) ausgeführt und die Daten werden in Customer Journey Analytics-Berichten bis zum Morgen aktualisiert.

>[!IMPORTANT]
>
>Der Tag der wöchentlichen Wiederholung und die Stunde der täglichen Wiederholung können nicht über eine benutzerdefinierte Anfrage geändert werden.
>

+++

## Gemeinsam verwendete Geräte

**Frage**: Wie werden freigegebene Geräte gehandhabt?

+++Antwort

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die Personen-ID setzt die persistente ID außer Kraft, sodass gemeinsam verwendete Geräte als separate Personen betrachtet werden (auch wenn sie vom selben Gerät stammen).

Weitere Informationen finden Sie im  Anwendungsbeispiel für [Gemeinsam verwendete Geräte](/help/use-cases/stitching/shared-devices.md).

+++

## Viele persistente IDs

**Frage**: Wie behandelt die Zuordnung Situationen, in denen eine einzelne Person viele persistente IDs hat?

+++Antwort

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Ein Beispiel hierfür ist eine Person, die häufig die Cookies des Browsers löscht oder den Privat-/Inkognito-Modus des Browsers verwendet.

Bei der feldbasierten Zuordnung ist die Personen-ID entscheidend, die Anzahl der persistenten IDs ist irrelevant. Eine einzelne Person kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit von Customer Journey Analytics auswirkt, geräteübergreifende Zuordnungen vorzunehmen.

Bei der diagrammbasierten Zuordnung kann eine einzelne Person über viele beständige IDs im Identitätsdiagramm verfügen. Die diagrammbasierte Zuordnung verwendet die persistente ID basierend auf dem angegebenen Namespace. Falls es persistentere IDs für denselben Namespace gibt, wird die lexikografische erste persistente ID verwendet.

+++

## Zuordnungsvorgang

**Frage**: Sobald ich mich mit den gewünschten Informationen an mein Adobe-Account-Team gewandt habe, wie lange dauert es, bis der neu verschlüsselte Datensatz verfügbar ist?

+++Antwort

Die Live-Zuordnung ist etwa eine Woche nach Aktivierung der Zuordnung durch Adobe verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

+++

## Geräteübergreifende Analyse vs. kanalübergreifende Analyse

**Frage**: Was ist der Unterschied zwischen geräteübergreifender Analyse (eine Funktion im herkömmlichen Analytics) und kanalübergreifender Analyse?

+++Antwort

[Geräteübergreifende Analyse](https://experienceleague.adobe.com/de/docs/analytics/components/cda/overview) ist eine Funktion, die speziell für das herkömmliche Adobe Analytics entwickelt wurde und Ihnen hilft, zu verstehen, wie Benutzende geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

Kanalübergreifende Analyse ist eine Customer Journey Analytics-spezifische Funktion, mit der Sie verstehen können, wie Personen sowohl über Geräte als auch Kanäle hinweg agieren. Sie ordnet die Personen-ID eines Datensatzes zu, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion ähnelt im Design der feldbasierten Zuordnung, aber die Implementierung unterscheidet sich aufgrund der unterschiedlichen Datenarchitektur von Adobe Analytics und Customer Journey Analytics. Weitere Informationen finden Sie unter [Zuordnung](overview.md) und im Anwendungsfall für die [kanalübergreifende Analyse](../use-cases/cross-channel/cross-channel.md).

+++

## Datenschutz

**Frage**: Wie handhabt Stitching Datenschutzanfragen?

+++Antwort

Adobe bearbeitet Datenschutzanfragen gemäß den lokalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/de/docs/experience-platform/privacy/home) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

>[!IMPORTANT]
>
>Das Verfahren zur Aufhebung der Zuordnung im Rahmen von Datenschutzanfragen ändert sich Anfang 2025. Das aktuelle Verfahren ordnet Ereignisse anhand der neuesten Version bekannter Identitäten neu zu. Diese Neuzuweisung von Ereignissen an eine andere Identität kann unerwünschte rechtliche Folgen haben. Um diesen Bedenken zu begegnen, werden Ereignisse, die Gegenstand der Datenschutzanfrage sind, ab 2025 durch das neue Verfahren zur Aufhebung der Zuordnung mit der persistenten ID aktualisiert.
> 

Zur Veranschaulichung stellen Sie sich die folgenden Daten für Identitäten und Ereignisse vor und nach der Zuordnung vor.

| Identitätszuordnung | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ECID | Bob | CustId |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Ereignisdatensatz | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| | 2 | ts1 | 123 | ECID | Bob | CustId |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Zugeordneter Datensatz | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace | resultierende ID | Zugeordneter Namespace |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | Bob | CustId |
| | 2 | ts1 | 123 | ECID | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |


**Aktueller Prozess für Datenschutzanfragen**

Wenn eine Datenschutzanfrage für eine Person mit CustID „Bob“ empfangen wird, werden die Zeilen mit durchgestrichenen Einträgen gelöscht. Andere Ereignisse werden mithilfe der Identitätszuordnung neu zugeordnet. Beispielsweise wird die erste zugeordnete ID im zugeordneten Datensatz auf **Alex** aktualisiert.

| Identitätszuordnung | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| ![Löschsymbol](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Ereignisdatensatz | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![Löschsymbol](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Zugeordneter Datensatz | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace | resultierende ID | Zugeordneter Namespace |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **Alex** | CustId |
| ![Löschsymbol](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |


**Neuer Prozess für Datenschutzanfragen**

Wenn eine Datenschutzanfrage für eine Person mit CustID „Bob“ empfangen wird, werden die Zeilen mit durchgestrichenen Einträgen gelöscht. Andere Ereignisse werden mit der persistenten ID neu zugeordnet. Beispielsweise wird die erste zugeordnete ID im zugeordneten Datensatz auf **123** aktualisiert.

| Identitätszuordnung | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| ![Löschsymbol](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Ereignisdatensatz | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![Löschsymbol](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Zugeordneter Datensatz | ID | Zeitstempel | Persistente ID | Persistenter Namespace | Personen-ID | Personen-Namespace | resultierende ID | Zugeordneter Namespace |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **123** | ECID |
| ![Löschsymbol](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |

+++

## Leere Werte für persistente ID

**Frage**: Was passiert, wenn das Feld „Persistente ID“ in einem oder mehreren Ereignissen leer ist?

+++Antwort

Wenn das Feld „Persistente ID“ bei einem Ereignis in einem zugeordneten Datensatz leer ist, wird die resultierende ID für dieses Ereignis auf eine dieser zwei Arten bestimmt:

* Wenn das Feld Personen-ID nicht leer ist, verwendet Customer Journey Analytics den Wert in der Personen-ID als resultierende ID.
* Wenn das Feld Personen-ID leer ist, lässt Customer Journey Analytics auch die resultierende ID leer. In diesem Fall sind die Felder „Persistente ID“, „Personen-ID“ und „resultierende ID“ für das Ereignis leer. Diese Ereignistypen werden aus jeder Customer Journey Analytics-Verbindung herausgenommen, die den zugeordneten Datensatz verwendet, bei dem die resultierende ID als Personen-ID ausgewählt wurde.

+++


## Nicht definierte Werte für Personen-ID

**Frage**: Was passiert, wenn das Feld für die Personen-ID in einem oder mehreren Ereignissen Platzhalterwerte enthält, z. B. `Undefined`?

+++Antwort

Seien Sie vorsichtig bezüglich „Personen-Kollaps“, der auftritt, wenn die Zuordnung auf Daten angewendet wird, die Platzhalterwerte für transiente IDs verwenden. In der folgenden Beispieltabelle werden undefinierte Personen-IDs, die aus einem Datensatz aus einem CRM-System stammen, mit dem Wert „Nicht definiert“ ausgefüllt, was zu einer falschen Darstellung von Personen führt.

| Ereignis | Zeitstempel | Persistente ID (Cookie-ID) | Transiente ID | resultierende ID (nach der Wiederholung) |
|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | 123 | – | **Cory** |
| 2 | 12.05.2023 12:02 | 123 | Cory | **Cory** |
| 3 | 12.05.2023 12:03 | 456 | Nicht definiert | **Nicht definiert** |
| 4 | 12.05.2023 12:04 | 456 | – | **Nicht definiert** |
| 5 | 12.05.2023 12:05 | 789 | Nicht definiert | **Nicht definiert** |
| 6 | 12.05.2023 12:06 | 012 | Nicht definiert | **Nicht definiert** |
| 7 | 12.05.2023 12:07 | 012 | – | **Nicht definiert** |
| 8 | 12.05.2023 12:03 | 789 | Nicht definiert | **Nicht definiert** |
| 9 | 12.05.2023 12:09 | 456 | – | **Nicht definiert** |
| 10 | 12.05.2023 12:02 | 123 | – | **Cory** |
| | | **4 Geräte** | **2 Personen:**<br/>Ereignisse 1, 4, 7, 9, 10 ignoriert | **2 Personen:**<br/>Cory, nicht authentifiziert (auf eine Person reduziert) |

+++

## Vergleich von Metriken

**Frage**: Wie lassen sich Metriken in zugeordneten Customer Journey Analytics-Datensätzen mit ähnlichen Metriken in nicht zugeordneten Customer Journey Analytics-Datensätzen und mit Adobe Analytics vergleichen?

+++Antwort

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken im herkömmlichen Analytics. Andere unterscheiden sich jedoch davon, je nachdem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete Customer Journey Analytics-Daten** | **Nicht zugeordnete Customer Journey Analytics-Daten** | **Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl unterschiedlicher Personen-IDs, bei denen die resultierende ID als Personen-ID ausgewählt wird. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Anzahl der einzelnen Personen-IDs basierend auf der Spalte, die als Personen-ID ausgewählt wurde. **Personen** in Datensätzen des Adobe-Quell-Connectors ähnelt den **Unique Visitors** im herkömmlichen Adobe Analytics, wenn in Customer Journey Analytics `endUserIDs._experience.aaid.id` als Personen-ID verwendet wird. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/de/docs/analytics/components/metrics/people). |
| **Sitzungen**: Wird anhand der Sitzungseinstellungen in der Customer Journey Analytics-Datenansicht definiert. Der Zuordnungsprozess kann einzelne Sitzungen auf mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der Customer Journey Analytics-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/de/docs/analytics/components/metrics/visits). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/de/docs/analytics/components/cda/setup) angegeben sind. |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einer leeren persistenten ID. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass Ereignisse, die eine leere Personen-ID in den nicht zugeordneten Daten im Data Lake von Experience Platform aufweisen, nicht in Customer Journey Analytics aufgenommen werden. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/de/docs/analytics/components/metrics/occurrences). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/de/docs/analytics/components/metrics/occurrences). |

Andere Metriken können in Customer Journey Analytics und Adobe Analytics ähnlich sein. Beispielsweise ist die Gesamtanzahl für die [benutzerdefinierten Ereignisse](https://experienceleague.adobe.com/de/docs/analytics/components/metrics/custom-events) 1–100 in Adobe Analytics zwischen herkömmlichem Analytics und Customer Journey Analytics vergleichbar (ob zugeordnet oder nicht zugeordnet). [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md), z. B. die Deduplizierung zwischen Customer Journey Analytics und Adobe Analytics, können zu Diskrepanzen zwischen den beiden Produkten führen.

+++

## Identitätszuordnung

**Frage**: Kann Customer Journey Analytics Identity Map-Felder verwenden?

+++Antwort

Ja, Customer Journey Analytics kann Identitätszuordnungsfelder sowohl für [ (feldbasierte](/help/stitching/fbs.md#identitymap) als auch für [diagrammbasierte](/help/stitching/gbs.md#identitymap) Zuordnung verwenden.

+++

## Wechseln zur diagrammbasierten Zuordnung

**Frage**: Müssen Daten erneut aufgenommen werden, um von feldbasiertem Stitching zu diagrammbasiertem Stitching zu wechseln?

+++Antwort

Daten müssen nicht erneut in Experience Platform aufgenommen werden. Daten müssen jedoch in Customer Journey Analytics neu konfiguriert werden. Gehen Sie wie folgt vor:

1. Richten Sie den neuen diagrammbasierten zugeordneten Datensatz mithilfe der diagrammbasierten Zuordnung ein.
1. Erstellen Sie eine neue temporäre Verbindung mit einem sehr kleinen Zeitfenster an Daten.
1. Konfigurieren Sie den neuen diagrammbasierten Datensatz als Teil dieser temporären Verbindung.
1. Überprüfen Sie mit dieser neuen temporären Verbindung, ob die diagrammbasierte Zuordnung ordnungsgemäß funktioniert.
1. Wenn die diagrammbasierte Zuordnung erwartungsgemäß funktioniert, fordern Sie eine zusätzliche Aufstockung für den diagrammbasierten Datensatz an und tauschen Sie dann den feldbasierten Datensatz in Ihrer ursprünglichen Verbindung mit dem neuen diagrammbasierten Datensatz aus.
1. Entfernen Sie die temporäre Verbindung.

+++

## Störungen in Berichten

**Frage**: Würde es zu Störungen bei bestehenden Berichten kommen?

+++Antwort

Nicht, wenn Sie die oben beschriebenen Schritte befolgen. Andernfalls wenden Sie sich bitte an Adobe Consulting, um weitere Unterstützung zu erhalten.

+++

## Aktivieren eines Datensatzes für den Identity Service

**Frage**: Wie wird ein Datensatz nur für den Identity Service aktiviert?

+++Antwort

Stellen Sie sicher, dass ein Datensatz für Identity Service aktiviert ist, um den Datensatz beim diagrammbasierten Stitching zu verwenden.

Sie benötigen keine Lizenz für Real-Time Customer Data Platform, um die diagrammbasierte Zuordnung verwenden zu können. Die diagrammbasierte Zuordnung basiert auf einem verfügbaren Identitätsdiagramm und nicht auf Echtzeit-Kundenprofilen.

Um einen vorhandenen Datensatz zu überprüfen und den Datensatz nur für den Identity Service zu aktivieren, verwenden Sie eine `PATCH`-Anfrage an den `/datasets`-Endpunkt, der nur das `unifiedIdentity`-Tag verwendet. Zum Beispiel:

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

Solange Sie keine Lizenz für das Real-Time Customer Data-Profil  besitzen, gibt jede Verwendung des `unifiedProfile`-Tags in der Anfrage einen Fehler zurück.

Weitere Informationen finden Sie unter [Erstellen eines Datensatzes, der für Profil und Identität aktiviert ist](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset).

+++


## Zugeordnete Namespace-Werte

**Frage**: Warum stimmen die Werte für zugeordnete Namespaces nicht immer mit dem Identity-Namespace-Wert überein, den Sie möglicherweise in einem anderen Datensatz innerhalb der CJA-Verbindung verwenden?

+++Antwort

Standardmäßig werden die Werte des zusammengefügten Namespace in Kleinbuchstaben geschrieben. `custEmail` wird also `custemail`. Wenn Sie keinen anderen Datensatz mit einem Identity-Namespace-Wert von `custEmail` haben, stimmen die beiden Werte nicht überein. Um dieses Verhalten im Reporting zu umgehen, können Sie die abgeleitete [lowercase() verwenden](/help/data-views/derived-fields/derived-fields.md#lowercase) um die Identitäts-Namespace-Werte abzugleichen.

+++
