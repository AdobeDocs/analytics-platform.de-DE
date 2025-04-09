---
title: Konzepte und Funktionen von Customer Journey Analytics B2B edition
description: Konzepte und Funktionen für die B2B edition von Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 3812b10e558c1b8a3ee4fe474405543c68433d8e
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# Konzepte und Funktionen von B2B edition

{{draft-b2b}}

In diesem Artikel werden allgemeine Konzepte und Funktionen für Datensätze und Container erläutert und erläutert, wie sich diese zwischen dem Standard und der B2B edition von Customer Journey Analytics unterscheiden.

Datensätze sind die Quellen einer Verbindung. Beim Einrichten einer Verbindung definieren Sie Datensätze als Teil dieser Verbindung.

Container werden in Customer Journey Analytics verwendet, um Funktionen wie Filter, berechnete Metriken und erweiterte Analysefunktionen zu unterstützen und zu erleichtern.




## Standard-Container

Die *Standardversion* von Customer Journey Analytics basiert auf dem Konzept von drei Containern: Person, Sitzung und Ereignis. Bei einem standardmäßigen Customer Journey Analytics-Setup werden diese relevanten Container implizit auf der Grundlage Ihres Setups generiert.

Sie können den Namen dieser Container beim Konfigurieren einer Datenansicht neu definieren, aber konzeptionell verwendet die Standardversion eine personenbasierte Container-Hierarchie.

![B2C](assets/b2c-containers.svg){zoomable="yes"}

In der Verbindung fügen Sie Ereignis-, Profil- und Lookup-Datensätze hinzu und wählen Identitäten aus, die zum Definieren der Verbindung zwischen diesen Datensätzen verwendet werden sollen. Im Rahmen der Verbindung wird automatisch eine personenbasierte Container-Hierarchie generiert. In dieser Hierarchie wird der Sitzungs-Container durch die [Sitzungseinstellungen](/help/data-views/session-settings.md) in Ihrer Datenansicht definiert.


## B2B-Container

In Customer Journey Analytics B2B edition wird der Liste der generierten Container ein Konto-Container hinzugefügt.  Außerdem haben Sie die Möglichkeit, die Generierung zusätzlicher Container wie „Globales Konto“, „Einkaufsgruppe“ und „Opportunity“ zu konfigurieren.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

In der Verbindung fügen Sie Ereignis-, Konto-, Globales Konto-, Opportunity-, Einkaufsgruppen- und andere Lookup-Datensätze hinzu. Sie wählen Konto als primäre ID für die Verbindung aus, damit Sie kontobasierte Identitäten zum Definieren der Verbindung zwischen den Datensätzen verwenden können. Im Rahmen der Verbindung wird automatisch eine Account-basierte Container-Hierarchie generiert. In dieser Hierarchie wird der Sitzungs-Container zwischen dem Personen-Container und dem Ereignis-Container durch die [Sitzungseinstellungen](/help/data-views/session-settings.md) in Ihrer Datenansicht definiert. Darüber hinaus werden Sitzungs-Container, z. B. zwischen Konto und Ereignis, derzeit nicht unterstützt.

Opportunity, Einkaufsgruppe und Person sind gleichrangige Container des Konto-Containers. In der folgenden Tabelle finden Sie eine Beschreibung und eine allgemeine Verwendung.

| B2B-Container | Beschreibung<br/>Grundlegender Anwendungsfall |
|---|---|
| Konto | Ein Unternehmen, das ein Kunde oder potenzieller Kunde Ihres Unternehmens ist. Dies könnte eine Tochtergesellschaft oder ein Geschäftsbereich einer größeren Organisation sein. Konto stellt die Organisation dar, an die Sie verkaufen und die Sie auf dieser Organisationsebene verfolgen möchten. |
| Globales Konto (optional) | Die oberste Muttergesellschaft einer Gruppe verbundener Unternehmen. Ein globales Konto hat keine Muttergesellschaft, kann jedoch Tochtergesellschaften oder Geschäftsbereiche haben, die zum globalen Konto gehören. Ein Konto, das keine übergeordneten oder untergeordneten Elemente hat, sollte sowohl im Feld Konto als auch im Feld Globales Konto aufgeführt werden, wenn beide bei der Einrichtung einer Verbindung aktiviert werden. |
| Opportunity (optional) | Eine Sammlung von Produkten und Dienstleistungen, die zusammen verkauft werden. Eine Opportunity umfasste oft verschiedene Phasen des Verkaufszyklus, um als Verkauf abgeschlossen zu werden.<br>Sie würden Opportunity-Daten verwenden, um den Opportunity-Fortschritt über den Verkaufstrichter zu messen. Beispiel: ein Bericht mit Details zu den wichtigsten Opportunitys, die von Opportunity-Phase 3 zu Phase 4 übergegangen sind. |
| Einkaufsgruppe (optional) | Eine Sammlung von Personen innerhalb einer Organisation, die am Entscheidungsprozess zum Kauf eines Produkts oder einer Dienstleistung beteiligt ist. <br/>Sie würden kaufende Gruppendaten verwenden, um Einkaufsgruppen über das Kampagnen-Management zu verfolgen. Erstellen Sie beispielsweise ein Zielgruppensegment aus wichtigen Einkaufsgruppen.<br/> Sie möchten wahrscheinlich eine Suche von der Einkaufsgruppe zu den Profildaten durchführen, damit Sie Berichte zu den Personen in einer Einkaufsgruppe erstellen können. |
| Person | Eine Person, die häufig durch eine eindeutige E-Mail-Adresse identifiziert wird, die mit dem Unternehmen interagiert hat. <br/>Sie würden die Profildaten verwenden, um Personen zu identifizieren, die für ein Konto arbeiten. Beispiel: Targeting aller Personen auf einem Konto, die sich für eine Konferenz angemeldet haben. |


## Übereinstimmung nach Container oder Feld

Wenn Sie eine Verbindung in Customer Journey Analytics definieren, können Sie für jeden Datensatz (Profil- oder Lookup-Datensatz) definieren, ob dieser Datensatz vom Container oder vom Feld abgeglichen wird.

### Übereinstimmung nach Container

Wenn ein Datensatzdatensatz vom Container abgeglichen wird, z. B. einer Einkaufsgruppe, wird der Datensatzdatensatz als Profildatensatztyp und in der Benutzeroberfläche als Profildatensatz behandelt.

### Übereinstimmung nach Feld

Wenn ein Datensatz anhand eines Felds abgeglichen wird, z. B. eines Marketing-Listenmitglieds, wird der Datensatz als Such-Datensatztyp und in der Benutzeroberfläche als Such-Datensatz behandelt.



## Bericht zu Personen- und Account-basierten Daten

Wenn Sie Berichte zu personenbasierten Containern (und Personenidentitäten) und kontobasierten Containern (und Kontoidentitäten) erstellen möchten, sollten Sie zwei separate Verbindungen innerhalb von Customer Journey Analytics einrichten. Eine Verbindung, bei der Sie Person als Primäre ID auswählen, und eine Verbindung, bei der Sie Account als Primäre ID auswählen. Customer Journey Analytics unterstützt keine personenbasierten und kontobasierten Berichte aus demselben Container.
