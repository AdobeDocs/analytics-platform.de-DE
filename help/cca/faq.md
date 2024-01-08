---
title: Häufig gestellte Fragen zu Cross-Channel Analytics
description: Häufig gestellte Fragen zu Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '1057'
ht-degree: 100%

---

# Häufig gestellte Fragen

## Wie kann ich CCA verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [analytics.adobe.com](https://analytics.adobe.com) an und erstellen Sie ein leeres Arbeitsbereich-Projekt.
2. Klicken Sie auf der linken Seite auf die Registerkarte „Visualisierungen“ und ziehen Sie eine Flussvisualisierung in die Arbeitsfläche auf der rechten Seite.
3. Klicken Sie auf die Registerkarte „Komponenten“ auf der linken Seite und ziehen Sie die Dimension „Datensatz-ID“ an die mittlere Position mit der Bezeichnung „Dimension oder Element“.
4. Dieser Flussbericht ist interaktiv. Klicken Sie auf einen der Werte, um den Fluss auf nachfolgende oder vorherige Seiten zu erweitern. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

## Wie weit zurück werden Personen bei der Cross-Channel-Analyse neu zugewiesen?

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der [Wiederholung](replay.md) der Daten ab. Wenn Sie beispielsweise die CCA so einrichten, dass Daten einmal wöchentlich wiederholt werden, umfasst das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie CCA so einrichten, dass Daten jeden Tag wiederholt werden, umfasst das Lookback-Fenster für die Neuzuweisung einen Tag.

## Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

## Wie behandelt CCA Situationen, in denen eine einzelne Person mehrere beständige IDs hat?

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Dazu gehören beispielsweise Personen, die Browser-Cookies häufig löschen oder den privaten bzw. Inkognito-Modus des Browsers verwenden.

Die Anzahl der beständigen IDs ist für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit von CCA auswirkt, Zuordnungen geräteübergreifend vorzunehmen.

## Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar ist, nachdem ich meinem Adobe-Accountteam die gewünschten Informationen mitgeteilt habe?

Die Echtzeit-Zuordnung ist etwa eine Woche nach der Aktivierung von Cross-Channel Analytics durch Adobe verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, bei großen Datensätzen (1 Milliarde Ereignisse pro Tag) durchaus eine Woche oder länger.

## Was ist der Unterschied zwischen geräteübergreifenden Analysen (eine Funktion in Adobe Analytics) und Cross-Channel-Analyse?

[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) ist eine Funktion, die speziell für das herkömmliche Adobe Analytics entwickelt wurde und Ihnen hilft, zu verstehen, wie Benutzende geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

[Cross-Channel-Analyse](/help/stitching/overview.md) ist eine Customer Journey Analytics-spezifische Funktion, mit der Sie verstehen können, wie Personen über Geräte und Kanäle hinweg agieren. Dabei wird die Personen-ID eines Datensatzes neu definiert, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion wirkt in Bezug auf das Design ähnlich wie die feldbasierte Zuordnung von CDA, aber die Implementierung ist aufgrund der unterschiedlichen Datenarchitektur von Adobe Analytics und Customer Journey Analytics anders.

## Wie handhabt Cross-Channel Analytics DSGVO- und CCPA-Anforderungen?

Adobe handhabt DSGVO- und CCPA -Anforderungen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

## Was passiert, wenn das Feld „Persistent ID“ in einem oder mehreren Ereignissen leer ist?

Wenn das Feld `Persistent ID` bei einem Ereignis in einem Datensatz, der mit feldbasierter Zuordnung verknüpft ist, leer ist, füllt CCA die `Stitched ID` für dieses Ereignis auf eine dieser zwei Arten aus:

* Wenn das Feld `Transient ID` nicht leer ist, verwendet CCA den Wert in `Transient ID` als `Stitched ID`.
* Wenn das Feld `Transient ID` leer ist, lässt CCA auch das Feld `Stitched ID` leer. In diesem Fall sind die Felder `Persistent ID`, `Transient ID` und `Stitched ID` für das Ereignis alle leer. Diese Arten von Ereignissen werden aus jeder Customer Journey Analytics-Verbindung herausgenommen, die den zugeordneten Datensatz verwendet, bei dem die `Stitched ID` als `Person ID` gewählt wurde.

## Wie stellt sich ein Vergleich zwischen Metriken in zugeordneten Customer Journey Analytics-Datensätzen und ähnlichen Metriken in nicht zugeordneten Customer Journey Analytics-Datensätzen sowie mit dem herkömmlichen Adobe Analytics dar?

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken in Adobe Analytics. Andere unterscheiden sich jedoch davon, je nachdem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete Customer Journey Analytics-Daten** | **Nicht zugeordnete Customer Journey Analytics-Daten** | **Traditionelles Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl der einzelnen `Person ID`s, für die `Stitched ID` als `Person ID` ausgewählt ist. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Anzahl der einzelnen `Person ID`s basierend auf der Spalte, die als `Person ID` ausgewählt wurde. **Personen** in Datensätzen des Adobe-Quell-Connectors ist ähnlich wie **Unique Visitors** im herkömmlichen Adobe Analytics, wenn `endUserIDs._experience.aaid.id` als `Person ID` in Customer Journey Analytics gewählt wird. | **Unique Visitors** = Anzahl unterschiedlicher Personen-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird anhand der Sitzungseinstellungen in der Customer Journey Analytics-Datenansicht definiert. Der Zuordnungsprozess kann einzelne Sitzungen auf mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der Customer Journey Analytics-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einer leeren `Persistent ID`. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass Ereignisse, die eine leere `Person ID` in den nicht zugeordneten Daten im Data Lake von Experience Platform aufweisen, nicht in Customer Journey Analytics aufgenommen werden. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). |

Andere Metriken können in Customer Journey Analytics und herkömmlichem Adobe Analytics ähnlich sein. Beispielsweise ist die Gesamtanzahl für [benutzerdefinierte Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) in Adobe Analytics (Ereignisse 1–100) in herkömmlichem Adobe Analytics und Customer Journey Analytics allgemein vergleichbar (unabhängig davon, ob zugeordnet oder nicht zugeordnet). [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen Customer Journey Analytics und herkömmlichem Adobe Analytics, können zu Diskrepanzen zwischen den beiden Produkten führen.

## Kann CCA Identity Map-Felder verwenden?

Nein, CCA kann derzeit keine Identity Map-Felder verwenden.
