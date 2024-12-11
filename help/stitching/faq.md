---
title: Häufig gestellte Fragen zur Zuordnung
description: Häufig gestellte Fragen zum Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 78803a2062b38b0f4a80837d18dbf3e9cc609cc8
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 28%

---

# Häufig gestellte Fragen

Im Folgenden finden Sie einige häufig gestellte Fragen zum Stitching:

## Kanalübergreifend

+++ Wie kann ich das Stitching verwenden, um zu sehen, wie Benutzer von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und erstellen Sie ein leeres Workspace-Projekt.
2. Wählen Sie auf der linken Seite die Registerkarte **[!UICONTROL ** Visualisierungen **]** aus und ziehen Sie eine Visualisierung des Typs **[!UICONTROL ** Fluss **]** auf die Arbeitsfläche auf der rechten Seite.
3. Wählen Sie auf der linken Seite die Registerkarte **[!UICONTROL ** Komponenten **]** aus und ziehen Sie die Dimension **[!UICONTROL ** Datensatz-ID **]** an die mittlere Position mit der Bezeichnung **[!UICONTROL ** Dimension oder Element **]**.
4. Dieser Flussbericht ist interaktiv. Um die Flüsse auf nachfolgende oder vorherige Seiten zu erweitern, wählen Sie einen der Werte aus. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

+++

## Wiederholen

+++ Wie weit reicht die Zuordnung von wiedergegebenen Besuchern zurück?

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der Wiederholung der Daten ab. Wenn Sie beispielsweise die Zuordnung so einrichten, dass Daten einmal wöchentlich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie die Zuordnung so einrichten, dass Daten täglich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung einen Tag.

+++

## Freigegebene Geräte

+++ Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

+++

## Viele beständige IDs

+++ Wie behandelt das Stitching Situationen, in denen eine einzelne Person über viele beständige IDs verfügt?

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Ein Beispiel ist eine Person, die häufig die Cookies des Browsers löscht oder den privaten/Inkognito-Modus des Browsers verwendet.

Bei feldbasiertem Stitching ist die Anzahl der beständigen IDs für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit von Customer Journey Analytics auswirkt, Geräte zuzuordnen.

Für eine grafikbasierte Zuordnung kann eine einzelne Person im Identitätsdiagramm über viele beständige IDs verfügen. Die Diagrammbasierte Zuordnung verwendet die beständige ID basierend auf dem angegebenen Namespace. Wenn für denselben Namespace eine beständige ID vorhanden ist, wird die lexikografische erste beständige ID verwendet.

+++

## Stitching-Prozess

+++ Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar ist, nachdem ich meinem Adobe-Accountteam die gewünschten Informationen mitgeteilt habe?

Die Live-Stitching-Funktion ist ca. eine Woche nach der Adobe-Aktivierung verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

+++

## Geräteübergreifende Analyse versus kanalübergreifende Analyse

+++ Was ist der Unterschied zwischen geräteübergreifender Analyse (eine Funktion in herkömmlichem Analytics) und kanalübergreifender Analyse?

[Geräteübergreifende Analysen](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) sind eine Funktion, die speziell für herkömmliche Adobe Analytics entwickelt wurde und Ihnen Aufschluss darüber gibt, wie Benutzer geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

Die kanalübergreifende Analyse ist ein für das Customer Journey Analytics spezifischer Anwendungsfall, mit dem Sie verstehen können, wie Benutzer auf Geräten und Kanälen arbeiten. Er ordnet die Personen-ID eines Datensatzes zu, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion funktioniert im Design ähnlich wie die geräteübergreifende feldbasierte Zuordnung für Analysen, aber die Implementierung unterscheidet sich aufgrund der unterschiedlichen Datenarchitektur zwischen herkömmlichem Analytics und Customer Journey Analytics. Weitere Informationen finden Sie unter [Stitching](overview.md) und im Anwendungsfall [Cross-Channel-Analyse](../use-cases/cross-channel/cross-channel.md) .

+++

## Datenschutz   

+++ Wie verarbeitet die Zuordnung Datenschutzanfragen?

Adobe verarbeitet Datenschutzanfragen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

>[!IMPORTANT]
>
>Die Aufhebung der Zuordnung als Teil von Datenschutzanfragen wird Anfang 2025 geändert. Der aktuelle Auftrennungsprozess löst Ereignisse anhand der neuesten Version bekannter Identitäten zurück. Diese Umbenennung von Ereignissen zu einer anderen Identität könnte unerwünschte rechtliche Folgen haben. Um diese Bedenken auszuräumen, aktualisiert der neue Auftrennungsprozess ab 2025 Ereignisse, die Gegenstand der Datenschutzanfrage sind, mit der beständigen ID.
> 

Stellen Sie sich die folgenden Daten für Identitäten, Ereignisse vor dem Stitching und nach dem Stitching vor.

| Identitätszuordnung | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Ereignis-Datensatz | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Zusammengefügter Datensatz | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace | Angeheftete ID | Zusammengestellter Namespace |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Aktueller Prozess für Datenschutzanfragen**

Wenn eine Datenschutzanfrage für Kunden mit CustID Bob empfangen wird, werden die Zeilen mit Durchstreichen-Einträgen gelöscht. Andere Ereignisse werden mithilfe der Identitätszuordnung erneut ausgelöst. Beispielsweise wird die erste zugeordnete ID im zugeordneten Datensatz auf **Alex** aktualisiert.

| Identitätszuordnung | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Ereignis-Datensatz | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Zusammengefügter Datensatz | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace | Angeheftete ID | Zusammengestellter Namespace |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Neuer Prozess für Datenschutzanfragen**

Wenn eine Datenschutzanfrage für Kunden mit CustID Bob empfangen wird, werden die Zeilen mit Durchstreichen-Einträgen gelöscht. Andere Ereignisse werden mithilfe der beständigen ID zurückgegeben. Beispielsweise wird die erste zugeordnete ID im zugeordneten Datensatz auf **123** aktualisiert.

| Identitätszuordnung | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Ereignis-Datensatz | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Zusammengefügter Datensatz | ID | timestamp | beständige ID | persistenter Namespace | vorübergehende ID | vorübergehender Namespace | Angeheftete ID | Zusammengestellter Namespace |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Leere beständige ID-Werte

+++ Was passiert, wenn das Feld „Persistent ID“ in einem oder mehreren Ereignissen leer ist?

Wenn das Feld &quot;Persistente ID&quot;bei einem Ereignis in einem Datensatz, der zugeordnet wird, leer ist, wird die zugeordnete ID für dieses Ereignis auf zwei Arten ermittelt:

* Wenn das Feld für die Übergangs-ID nicht leer ist, verwendet Customer Journey Analytics den Wert in der Übergangs-ID als zugeordnete ID.
* Wenn das Feld für die Verlaufs-ID leer ist, lässt Customer Journey Analytics auch die zugeordnete ID leer. In diesem Fall sind die beständige ID, die vorübergehende ID und die zugeordnete ID im Ereignis leer. Diese Ereignistypen werden bei jeder Customer Journey Analytics-Verbindung mit dem Datensatz abgelegt, der zugeordnet wird und in dem die zugeordnete ID als Personen-ID ausgewählt wurde.

+++


## Undefinierte vorübergehende ID-Werte

+++ Was passiert, wenn das Feld für die Verlaufs-ID in einem oder mehreren Ereignissen Platzhalterwerte wie `Undefined` aufweist?

Seien Sie vorsichtig mit &quot;Personen reduzieren&quot;, was auftritt, wenn die Zuordnung auf Daten angewendet wird, die Platzhalterwerte für Übergangs-IDs verwenden. In der folgenden Beispieltabelle werden nicht definierte Personen-IDs aus einem Datensatz, der aus einem CRM-System stammt, mit dem Wert &quot;Undefiniert&quot;ausgefüllt, was zu einer falschen Darstellung von Personen führt.

| Ereignis | Zeitstempel | Beständige ID (Cookie-ID) | Verlaufs-ID (Anmelde-ID) | Zugeordnete ID (nach der Wiederholung) |
|---|---|---|---|---|
| 1 | 12.05.2023 12:01 | 123 | – | **Geschichte** |
| 2 | 2023-05-12 12:02 | 123 | Geschichte | **Geschichte** |
| 3 | 2023-05-12 12:03 | 456 | Nicht definiert | **Nicht definiert** |
| 4 | 2023-05-12 12:04 | 456 | – | **Nicht definiert** |
| 5 | 2023-05-12 12:05 | 789 | Nicht definiert | **Nicht definiert** |
| 6 | 2023-05-12 12:06 | 012 | Nicht definiert | **Nicht definiert** |
| 7 | 2023-05-12 12:07 | 012 | – | **Nicht definiert** |
| 8 | 2023-05-12 12:03 | 789 | Nicht definiert | **Nicht definiert** |
| 9 | 2023-05-12 12:09 | 456 | – | **Nicht definiert** |
| 10 | 2023-05-12 12:02 | 123 | – | **Geschichte** |
| | | **4 Geräte** | **2 Personen**:<br/>Die Ereignisse 1, 4, 7, 9, 10 wurden gelöscht | **2 Personen**:<br/>Geschichte, Nicht authentifiziert (auf eine Person reduziert) |

+++

## Vergleich von Metriken

+++ Wie vergleichen sich Metriken in Customer Journey Analytics zugeordneten Datensätzen mit ähnlichen Metriken in Customer Journey Analytics nicht zugeordneten Datensätzen und mit Adobe Analytics?

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken in herkömmlichem Analytics, andere unterscheiden sich jedoch je nach dem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete Customer Journey Analytics-Daten** | **Nicht zugeordnete Customer Journey Analytics-Daten** | **Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl unterschiedlicher Personen-IDs, bei denen die zugeordnete ID als Personen-ID ausgewählt wird. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Zählung unterschiedlicher Personen-IDs basierend auf der Spalte, die als Personen-ID ausgewählt wurde. **Personen** in den Analytics-Quell-Connector-Datensätzen ähnelt **Unique Visitors** im herkömmlichen Adobe Analytics, wenn `endUserIDs._experience.aaid.id` als Personen-ID im Customer Journey Analytics verwendet wird. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird anhand der Sitzungseinstellungen in der Customer Journey Analytics-Datenansicht definiert. Der Zuordnungsprozess kann einzelne Sitzungen auf mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der Customer Journey Analytics-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einer leeren beständigen ID. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass bei Ereignissen, die eine leere Personen-ID in den nicht zugewiesenen Daten im Experience Platform Data Lake aufweisen, diese Ereignisse nicht im Customer Journey Analytics enthalten sind. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). |

Andere Metriken können in Customer Journey Analytics und Adobe Analytics ähnlich sein. Beispielsweise ist die Gesamtanzahl der benutzerspezifischen Adobe Analytics-Ereignisse [1-100 zwischen dem herkömmlichen Adobe Analytics und dem herkömmlichen Customer Journey Analytics (ob zugeordnet oder nicht zugeordnet) vergleichbar. ](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) [Unterschiede in den Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen Customer Journey Analytics und Adobe Analytics, können zu Diskrepanzen zwischen den beiden Produkten führen.

+++

## Identitätszuordnung

+++ Kann Customer Journey Analytics Identity Map-Felder verwenden?

Nein, Customer Journey Analytics kann derzeit keine Identity Map-Felder zum Stitching verwenden.

+++

## Wechsel zur grafisch basierten Zuordnung

+++ Müssen Daten neu erfasst werden, um von feldbasiertem Stitching zu grafischem Stitching zu wechseln?

Daten müssen nicht in Experience Platform neu aufgenommen werden, sie müssen jedoch in Customer Journey Analytics neu konfiguriert werden. Führen Sie folgende Schritte aus:

1. Richten Sie den neuen graphenbasierten zugeordneten Datensatz ein.
1. Konfigurieren Sie den neuen Datensatz als Teil einer neuen Verbindung in Customer Journey Analytics.
1. Wechseln Sie Ihre vorhandene Datenansicht zur Verwendung der neuen Verbindung (und als solche zum neuen, auf Diagrammen basierenden gestuften Datensatz)
1. Entfernen Sie die alte Verbindung, die den feldbasierten zugeordneten Datensatz verwendet hat.

+++

## Berichtsunterbrechung

+++ Bestehen irgendwelche Störungen bei bestehenden Berichten?

Nicht, wenn Sie die oben beschriebenen Schritte ausführen. Andernfalls bitten Sie Adobe Consulting um zusätzlichen Support.

+++


