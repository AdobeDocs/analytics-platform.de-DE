---
title: Häufig gestellte Fragen zur Zuordnung
description: Häufig gestellte Fragen zum Stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 80d5a864e063911b46ff248f2ea89c1ed0d14e32
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 29%

---

# Häufig gestellte Fragen

Im Folgenden finden Sie einige häufig gestellte Fragen zum Stitching:

+++**Wie kann ich die Zuordnung verwenden, um zu sehen, wie sich Personen von einem Kanal zum anderen bewegen?**

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und erstellen Sie ein leeres Workspace-Projekt.
2. Wählen Sie auf der linken Seite die Registerkarte **[!UICONTROL ** Visualisierungen **]** aus und ziehen Sie eine Visualisierung des Typs **[!UICONTROL ** Fluss **]** auf die Arbeitsfläche auf der rechten Seite.
3. Wählen Sie auf der linken Seite die Registerkarte **[!UICONTROL ** Komponenten **]** aus und ziehen Sie die Dimension **[!UICONTROL ** Datensatz-ID **]** an die mittlere Position mit der Bezeichnung **[!UICONTROL ** Dimension oder Element **]**.
4. Dieser Flussbericht ist interaktiv. Um die Flüsse auf nachfolgende oder vorherige Seiten zu erweitern, wählen Sie einen der Werte aus. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

+++

+++**Wie weit reicht die Zuordnung von Besuchern zur Wiederholung zurück?**

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der Wiederholung der Daten ab. Wenn Sie beispielsweise die Zuordnung so einrichten, dass Daten einmal wöchentlich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie die Zuordnung so einrichten, dass Daten täglich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung einen Tag.

+++

+++**Wie werden gemeinsam genutzte Geräte gehandhabt?**

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

+++

+++**Wie behandelt das Stitching Situationen, in denen eine einzelne Person über viele beständige IDs verfügt?**

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Ein Beispiel ist eine Person, die häufig die Cookies des Browsers löscht oder den privaten/Inkognito-Modus des Browsers verwendet.

Bei feldbasiertem Stitching ist die Anzahl der beständigen IDs für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit von Customer Journey Analytics auswirkt, Geräte zuzuordnen.

Für eine grafikbasierte Zuordnung kann eine einzelne Person im Identitätsdiagramm über viele beständige IDs verfügen. Die Diagrammbasierte Zuordnung verwendet die beständige ID basierend auf dem angegebenen Namespace. Wenn für denselben Namespace eine beständige ID vorhanden ist, wird die lexikografische erste beständige ID verwendet.

+++

+++**Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar ist, nachdem ich mein Adobe Account-Team mit den gewünschten Informationen kontaktiert habe?**

Die Live-Stitching-Funktion ist ca. eine Woche nach der Adobe-Aktivierung verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

+++

+++**Was ist der Unterschied zwischen geräteübergreifender Analyse (eine Funktion in herkömmlichem Analytics) und kanalübergreifender Analyse?**

[Geräteübergreifende Analysen](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) sind eine Funktion, die speziell für herkömmliche Adobe Analytics entwickelt wurde und Ihnen Aufschluss darüber gibt, wie Benutzer geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

Die kanalübergreifende Analyse ist ein für das Customer Journey Analytics spezifischer Anwendungsfall, mit dem Sie verstehen können, wie Benutzer auf Geräten und Kanälen arbeiten. Er ordnet die Personen-ID eines Datensatzes zu, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion funktioniert im Design ähnlich wie die geräteübergreifende feldbasierte Zuordnung für Analysen, aber die Implementierung unterscheidet sich aufgrund der unterschiedlichen Datenarchitektur zwischen herkömmlichem Analytics und Customer Journey Analytics. Weitere Informationen finden Sie unter [Stitching](overview.md) und im Anwendungsfall [Cross-Channel-Analyse](../use-cases/cross-channel/cross-channel.md) .

+++

+++**Wie behandelt die Zuordnung Datenschutzanfragen?**

Adobe verarbeitet Datenschutzanfragen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

+++

+++**Was passiert, wenn das Feld für die beständige ID in einem oder mehreren Ereignissen leer ist?**

Wenn das Feld &quot;Persistente ID&quot;bei einem Ereignis in einem Datensatz, der zugeordnet wird, leer ist, wird die zugeordnete ID für dieses Ereignis auf zwei Arten ermittelt:

* Wenn das Feld für die Übergangs-ID nicht leer ist, verwendet Customer Journey Analytics den Wert in der Übergangs-ID als zugeordnete ID.
* Wenn das Feld für die Verlaufs-ID leer ist, lässt Customer Journey Analytics auch die zugeordnete ID leer. In diesem Fall sind die beständige ID, die vorübergehende ID und die zugeordnete ID im Ereignis leer. Diese Ereignistypen werden bei jeder Customer Journey Analytics-Verbindung mit dem Datensatz abgelegt, der zugeordnet wird und in dem die zugeordnete ID als Personen-ID ausgewählt wurde.

+++


+++**Was passiert, wenn das Feld für die Verlaufs-ID in einem oder mehreren Ereignissen Platzhalterwerte wie &quot;Undefiniert&quot;aufweist?**

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

+++**Wie vergleichen sich Metriken in Customer Journey Analytics zugeordneten Datensätzen mit ähnlichen Metriken in Customer Journey Analytics nicht zugeordneten Datensätzen und mit Adobe Analytics?**

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken in herkömmlichem Analytics, andere unterscheiden sich jedoch je nach dem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete Customer Journey Analytics-Daten** | **Nicht zugeordnete Customer Journey Analytics-Daten** | **Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl unterschiedlicher Personen-IDs, bei denen die zugeordnete ID als Personen-ID ausgewählt wird. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Zählung unterschiedlicher Personen-IDs basierend auf der Spalte, die als Personen-ID ausgewählt wurde. **Personen** in den Analytics-Quell-Connector-Datensätzen ähnelt **Unique Visitors** im herkömmlichen Adobe Analytics, wenn `endUserIDs._experience.aaid.id` als Personen-ID im Customer Journey Analytics verwendet wird. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird anhand der Sitzungseinstellungen in der Customer Journey Analytics-Datenansicht definiert. Der Zuordnungsprozess kann einzelne Sitzungen auf mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der Customer Journey Analytics-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einer leeren beständigen ID. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass bei Ereignissen, die eine leere Personen-ID in den nicht zugewiesenen Daten im Experience Platform Data Lake aufweisen, diese Ereignisse nicht im Customer Journey Analytics enthalten sind. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). |

Andere Metriken können in Customer Journey Analytics und Adobe Analytics ähnlich sein. Beispielsweise ist die Gesamtanzahl der benutzerspezifischen Adobe Analytics-Ereignisse [1-100 zwischen dem herkömmlichen Adobe Analytics und dem herkömmlichen Customer Journey Analytics (ob zugeordnet oder nicht zugeordnet) vergleichbar. ](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) [Unterschiede in den Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen Customer Journey Analytics und Adobe Analytics, können zu Diskrepanzen zwischen den beiden Produkten führen.

+++

+++**Kann Customer Journey Analytics Identitätszuordnungsfelder verwenden?**

Nein, Customer Journey Analytics kann derzeit keine Identity Map-Felder zum Stitching verwenden.

+++

+++**Müssen Daten neu gezählt werden, um vom feldbasierten Stitching zum grafikbasierten Stitching zu wechseln?**
Daten müssen nicht in Experience Platform neu aufgenommen werden, sie müssen jedoch in Customer Journey Analytics neu konfiguriert werden. Führen Sie folgende Schritte aus:

1. Richten Sie den neuen graphenbasierten zugeordneten Datensatz ein.
1. Konfigurieren Sie den neuen Datensatz als Teil einer neuen Verbindung in Customer Journey Analytics.
1. Wechseln Sie Ihre vorhandene Datenansicht zur Verwendung der neuen Verbindung (und als solche zum neuen, auf Diagrammen basierenden gestuften Datensatz)
1. Entfernen Sie die alte Verbindung, die den feldbasierten zugeordneten Datensatz verwendet hat.

+++

+++**Gibt es irgendeine Unterbrechung bei vorhandenen Berichten?**

Nicht, wenn Sie die oben beschriebenen Schritte ausführen. Andernfalls bitten Sie Adobe Consulting um zusätzlichen Support.

+++


