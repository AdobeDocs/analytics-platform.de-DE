---
title: Berichte für die Gesamtpopulation
description: Verwenden Sie die Berichte zur Gesamtpopulation in Customer Journey Analytics, um Profile und Konten in Ihren Datensätzen unabhängig von Ereignisaktivitäten oder Datumsbereichen des Bedienfelds zu analysieren.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: f7bbbaf0b737ab33088c7c585d6415f93deff4c8
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---

# Berichte zur Gesamtpopulation

Das Reporting zur Gesamtpopulation bietet die Möglichkeit, Entitäten zu analysieren und Berichte zu ihnen zu erstellen, die in Profil- und Lookup-Datensätzen definiert sind und über die zeitbasierten Ereignisreihen aus Ereignisdatensätzen hinausgehen. Diese Funktion ermöglicht neue Klassen von Abfragen, Metriken und Zielgruppendefinitionen, die den gesamten Umfang des Kundenstamms eines Unternehmens widerspiegeln.

Customer Journey Analytics basiert auf Ereignissen. Jede Metrik, jede Visualisierung, jedes Bedienfeld, jeder Bericht ist mit einem Datums- und Zeitbereich sowie mit Ereignissen, die während dieses Datums- und Zeitbereichs auftreten, verankert. Sie stellen die Lösungen Fragen wie:

| Frage | Ereignis | Datums-/Zeitbereich |
|---|---|---|
| Wie viele Personen haben letzte Woche einen Kauf getätigt? | Kauf | Letzte Woche |
| Wie viele Konten haben die Preisseite im ersten Quartal besucht? | Besuch | Q1 |

Der Datums- und Zeitbereich des Arbeitsbereich-Bedienfelds filtert die Daten, und Ihre Dimensionen und Metriken beschreiben, was während dieses Datums- und Zeitbereichs passiert ist.

Aber nicht jede Frage, die Ihr Unternehmen beantworten muss, betrifft etwas, das passiert ist. Manchmal muss man über die eigene Bevölkerung Bescheid wissen.

| Frage | Ereignis | Datums-/Zeitbereich |
|---|---|---|
| Wie viele aktive Kunden haben wir derzeit? | -/- | K. A. |
| Wie viele Konten befinden sich in unserer Datenbank? | -/- | K. A. |
| Wie viele unserer Mitglieder haben in den letzten 30 Tagen keinen Kauf getätigt? | k. A. | Letzte 30 Tage |

Bei diesen Fragen geht es nicht um Ereignisse, sondern um Menschen und Accounts, die es gibt, egal ob diese Leute oder Accounts kürzlich etwas getan haben oder nicht.

Das Reporting zur Gesamtpopulation führt eine neue Klasse von Metriken ein, die Berichte zu Profildaten erstellen. Diese Profildaten, die Personen und Konten in Ihren Profildatensätzen enthalten können, sind unabhängig vom Datumsbereich eines Bedienfelds. Mit Berichten zur Gesamtpopulation können Sie populationsbasierte Metriken und ereignisbasierte Metriken in derselben Analyse kombinieren, was ein umfassenderes Bild davon bietet, wer Ihre Kundinnen und Kunden sind und was sie getan haben.

Das Reporting zur Gesamtpopulation ermöglicht es Customer Journey Analytics, Berichte zu allen in Profil- und Lookup-Datensätzen definierten Entitäten zu erstellen, unabhängig von der Ereignisaktivität. Diese Berichterstellung umfasst:

* **Profilbasierte Abfragen**: Analysieren Sie Attribute (unabhängig von Ereignissen) von Profilen (alle Personen, Konten, Opportunities und Einkaufsgruppen).
* **Profil abzüglich Ereignisabfragen**: Identifizieren Sie Profile (alle Personen, Konten, Opportunities und Einkaufsgruppen), die während des Reporting-Fensters keine bestimmte Aktion oder kein bestimmtes Erlebnis ausgeführt haben.
* **Freigegebene Suchen**: Unterstützen Sie die Wiederverwendung von Lookup-Datensätzen in mehreren Entitäten, um die Aufnahmekosten zu reduzieren und die Leistung zu verbessern.

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## Berichtsmetriken für die Gesamtpopulation

Berichtsmetriken zur Gesamtpopulation verhalten sich anders als die üblicherweise in Customer Journey Analytics verwendeten Metriken:

* Die Berichtsmetriken zur Gesamtpopulation sind nicht an den Datumsbereich des Bedienfelds gebunden. Eine Berichtsmetrik für die Gesamtpopulation wie **[!UICONTROL Personen insgesamt (Profil)]** gibt die aktuelle Population aus Ihrem Profildatensatz zurück, unabhängig vom auf das Bedienfeld angewendeten Datumsbereich. Datumsfilter und Datumsbereichsvergleiche wirken sich nicht auf die Berichtsmetriken der Gesamtpopulation aus, so wie diese Filter und Vergleiche die Ereignismetriken beeinflussen.
* Berichte zur Gesamtpopulation erfordern einen Profildatensatz für die Verbindung. Berichtsmetriken zur Gesamtpopulation werden nur angezeigt, wenn Ihre Verbindung mindestens einen Profildatensatz und mindestens einen Ereignisdatensatz enthält. Verbindungen nur mit Ereignis-Datensätzen funktionieren weiterhin genau wie zuvor und zeigen keine Berichtsmetriken zur Gesamtpopulation an.

In Workspace werden Gesamtpopulationsmetriken mit einem speziellen Symbol (TBD) gekennzeichnet, sodass Sie schnell identifizieren können, welche Metriken den Datumsbereich des Bedienfelds berücksichtigen und welche nicht. Gesamtpopulationsmetriken können an den meisten Stellen zusammen mit Ereignismetriken verwendet werden. Visualisierungstypen, die von Ereignissequenzen (wie Fallout und Fluss) abhängen, werden jedoch nicht unterstützt.

### Berichtsmetriken der Standardgesamtheit

Standardmäßig umfasst das System drei standardmäßige Berichtsmetriken zur Gesamtpopulation, die für jede Datenansicht verfügbar sind, deren Verbindung einen Profildatensatz enthält:

* **Personen insgesamt (Profil)**: die Gesamtzahl der Personen im Profildatensatz.
* **Konten insgesamt (Profil)**: die Gesamtzahl der Konten im Profildatensatz. [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **Personen insgesamt (Profil + Ereignis)**: Eine Vereinigungsanzahl, bei der Personen, die ein Profil aufweisen, mit Personen kombiniert werden, die ein Ereignis behandeln.

Sie können auch benutzerdefinierte Metriken mit jedem der drei Bereiche erstellen, indem Sie Felder aus Ihren Profildatensätzen verwenden.

## Anforderungen, Voraussetzungen und Überlegungen

Damit die Berichterstattung über die Gesamtpopulation ordnungsgemäß funktioniert, sollten die Voraussetzungen, Anforderungen und Überlegungen berücksichtigt werden.

### Verbindungsanforderungen

Für eine Verbindung zur Unterstützung des Reportings für die Gesamtpopulation:

* Für die Verbindung ist mindestens ein Ereignisdatensatz erforderlich. Reine Profilverbindungen werden nicht unterstützt.
* Der Verbindung muss mindestens ein Profildatensatz hinzugefügt werden. Berichtsmetriken zur Gesamtpopulation werden nicht in Datenansichten angezeigt, die auf Verbindungen basieren, die nur Ereignisdaten enthalten.
* Freigegebene Suchen müssen für jeden Profildatensatz konfiguriert werden. Gemeinsam genutzte Suchen definieren, wie jeder Profildatensatz mit den Ereignissen in Ihrer Verbindung verbunden wird, indem der übereinstimmende Schlüssel, der Namespace (für Identitätszuordnungsfelder) und der Join-Pfad angegeben werden.

#### Konfiguration von Profildatensätzen

Wenn ein Profildatensatz zu einer Verbindung hinzugefügt wird, füllt Customer Journey Analytics eine standardmäßige freigegebene Lookup-Konfiguration, die auf dem Datensatztyp basiert:

* Für Personenprofil-Datensätze: Der Standardwert ist „match-by-Container“ und [!UICONTROL &#x200B; auf „Person] festgelegt, wobei die Identitätszuordnung als Schlüsselfeld dient. Sie können diese Standardeinstellung bearbeiten. Um beispielsweise einen bestimmten Namespace aus der Identitätszuordnung anstelle des Primärschlüssels auszuwählen. Oder um einen sekundären Namespace für Fälle anzugeben, in denen der erste Namespace nicht ausgefüllt ist (dies ist bei zusammengefügten Datensätzen der Fall).
* Für Kontoprofildatensätze [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Der Standardwert ist „match-by-container[!UICONTROL &#x200B; auf „Account] (oder [!UICONTROL Global Account], wenn globale Konten für die Verbindung aktiviert sind) festgelegt. Das Kontofeld kann eine einzelne Kennung oder eine Identitätszuordnung sein. Wenn das Kontofeld eine Identitätszuordnung ist, wählen Sie den zu verwendenden Namespace aus.

Sie können mehrere freigegebene Suchen für einen einzelnen Profildatensatz konfigurieren, um mehrere Join-Pfade zu Ihren Ereignissen zu unterstützen. Wenn dieselbe Identitätszuordnung als Schlüsselfeld über mehrere gemeinsame Suchen hinweg verwendet wird, müssen die Namespace-Auswahlen konsistent sein.

### Anforderungen an die Datenansicht

Für die Reporting-Metriken der Gesamtpopulation, damit sie in einer Datenansicht korrekt funktionieren:

* Die Verbindung muss einen Profildatensatz enthalten (siehe [Verbindungsanforderungen](#connection-requirements)). Wenn Sie den letzten verbleibenden Profildatensatz aus einer Verbindung entfernen, sind die Berichtsmetriken zur Gesamtpopulation für die daraus erstellten Datenansichten nicht verfügbar.
* [Segmente auf Datenansichtsebene](/help/data-views/create-dataview.md#settings-segments) dürfen nicht ereignisexplizit sein. Wenn ein Segment, das direkt auf die Datenansicht angewendet wird, vollständig in Bedingungen im Ereignisbereich definiert ist (z. B. `hit where page = X`), ist das Reporting der Gesamtpopulation für diese Datenansicht nicht möglich. Bevor Sie sich auf die Berichtsmetriken zur Gesamtpopulation verlassen, überprüfen Sie, ob alle Segmente auf Datenansichtsebene mit dem Reporting auf Profilebene kompatibel sind.
* Der Metrikbereich muss korrekt festgelegt sein. Wählen Sie beim Erstellen einer benutzerdefinierten Metrikkomponente im Datenansichts-Builder den entsprechenden Umfang (Ereignis, Profil oder Profil + Ereignis) aus, der auf dem Datensatz des Felds basiert und darauf, wie sich die Metrik verhalten soll. Der Umfang kann nicht geändert werden, nachdem die Metrik in Zielgruppen oder wiederkehrenden Berichten verwendet wurde, ohne diese Abhängigkeiten aufzuheben.

### Workspace-Kompatibilität

Berichtsmetriken zur Gesamtpopulation können in den meisten Workspace-Kontexten zusammen mit ereignisbasierten Metriken verwendet werden: [Freiformtabellen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), [line](/help/analysis-workspace/visualizations/line.md), [bar](/help/analysis-workspace/visualizations/bar.md) und [horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) Visualisierungen, [Kohortentabellen](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) bei entsprechender Konfiguration usw. Einige Visualisierungstypen werden nicht unterstützt, da sie von Natur aus von Ereignissequenzen abhängen:

* [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [Fluss](/help/analysis-workspace/visualizations/c-flow/flow.md)
* Zusätzliche nicht unterstützte Visualisierungstypen müssen vor der Veröffentlichung bestätigt werden.

Wenn Sie einer nicht unterstützten Visualisierung eine Berichtsmetrik für die Gesamtpopulation hinzufügen, gibt Workspace an, dass die Metrik in diesem Kontext nicht verwendet werden kann.

### Überlegungen zur Zielgruppe

Zielgruppen, die auf Berichtsmetriken zur Gesamtpopulation basieren, sind davon abhängig, welche Metriken in der Datenansicht vorhanden bleiben:

* Eine wiederkehrende Zielgruppe, die die Berichtsmetrik Gesamtpopulation verwendet, schlägt fehl und wechselt in den Status FEHLER , wenn die Berichtsmetrik Gesamtpopulation aus der Datenansicht entfernt wird.
* Die Customer Journey Analytics-Benutzeroberfläche verhindert das Entfernen einer Metrik, während eine beliebige aktive wiederkehrende Zielgruppe von der Metrik abhängt, und bietet Anleitungen zur Abhängigkeit, bevor Sie das Entfernen bestätigen.

### Berechtigungen

Zu bestätigen: Sämtliche Rollen- oder Funktionszugriffsanforderungen an die IMS-Organisation oder das Produktprofil des Kunden, bevor die Berichtsmetriken zur Gesamtpopulation sichtbar sind. Es lohnt sich, ihn vor der Veröffentlichung an PM zu kennzeichnen.
