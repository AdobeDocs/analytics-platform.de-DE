---
title: Konzepte und Funktionen von Customer Journey Analytics B2B edition
description: Konzepte und Funktionen für die B2B edition von Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 326a82e93c0c8d57db224023ed5f3a7ab94a8997
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---


# Konzepte und Funktionen von B2B edition

{{draft-b2b}}

In diesem Artikel werden Konzepte wie Verbindungen, Kennungen, Container und Datensätze erläutert, die häufig in Customer Journey Analytics verwendet werden. Und wie Customer Journey Analytics B2B edition zusätzliche Funktionen zu diesen Konzepten hinzufügt.


## Verbindungen und Kennungen

In Customer Journey Analytics wählen Sie eine allgemeine Kennung, die Personen-ID, um Ihre Ereignisdaten mit anderen Datensätzen wie Profildatensätzen und Lookup-Datensätzen zu verbinden. Dieser Verbindungstyp wird als personenbasierte Verbindung bezeichnet, die das personenbasierte Reporting und die Analyse erleichtert.

In Customer Journey Analytics B2B edition können Sie zwischen einer personenbasierten Verbindung und einer kontobasierten Verbindung wählen. Eine Account-basierte Verbindung erleichtert die Account-basierte Berichterstellung und Analyse.

* Für eine personenbasierte Verbindung wählen Sie Person als primäre Kennung. Anschließend können Sie Ihre Verbindungs-, Datenansichts- und Arbeitsbereich-Projekte für personenbasierte Berichte konfigurieren und einrichten.
* Für eine kontobasierte Verbindung wählen Sie Konto als primäre Kennung aus. Anschließend können Sie optional zusätzliche Container für Globales Konto, Einkaufsgruppe und Opportunity hinzufügen. Je nachdem, ob Sie ein globales Konto hinzufügen oder nicht, ist Ihre primäre Kennung eine Kontokennung oder eine globale Kontokennung.


## Container

In Customer Journey Analytics werden Container im Rahmen der Konfiguration einer Verbindung und Datenansicht generiert. Container speichern nur Kennungen, um die schnelle und leistungsstarke Ausführung von Funktionen wie Segmentierung, Aufschlüsselungen und mehr zu erleichtern.

### Standard-Container

Customer Journey Analytics basiert auf dem Konzept von drei Containern: Person, Sitzung und Ereignis. Während einer Konfiguration werden diese Container implizit generiert.

Sie können beim Konfigurieren einer Datenansicht den Namen dieser Container neu definieren, aber die Hierarchie und die Beziehungen zwischen den Containern sind vorbestimmt. Der Sitzungs-Container wird basierend auf der Definition einer Sitzung in den [Sitzungseinstellungen](/help/data-views/session-settings.md) in Ihrer Datenansicht generiert.

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### B2B-Container

In Customer Journey Analytics B2B edition wird der Liste der generierten Container ein Konto-Container hinzugefügt. Außerdem haben Sie die Möglichkeit, die Generierung zusätzlicher Container wie „Globales Konto“, „Einkaufsgruppe“ und „Opportunity“ zu konfigurieren.

Die Hierarchie und die Beziehungen zwischen den Containern sind vorgegeben. Opportunity, Einkaufsgruppe und Person sind gleichrangige Container des Konto-Containers. In dieser Hierarchie wird der Sitzungs-Container zwischen dem Personen-Container und dem Ereignis-Container basierend auf der Definition einer Sitzung in den [Sitzungseinstellungen](/help/data-views/session-settings.md) in Ihrer Datenansicht generiert. Zusätzliche Sitzungs-Container, z. B. zwischen dem Konto-Container und dem Ereignis-Container, werden derzeit nicht generiert und unterstützt. In der folgenden Tabelle finden Sie eine Beschreibung und eine allgemeine Verwendung der B2B-Container.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| B2B-Container | Beschreibung<br/>Grundlegender Anwendungsfall |
|---|---|
| Konto | Ein Unternehmen, das ein Kunde oder potenzieller Kunde Ihres Unternehmens ist. Das Unternehmen könnte eine Tochtergesellschaft oder ein Geschäftsbereich einer größeren Organisation sein. Konto stellt die Organisation dar, an die Sie verkaufen und die Sie auf dieser Organisationsebene verfolgen möchten. |
| Globales Konto (optional) | Die oberste Muttergesellschaft einer Gruppe verbundener Unternehmen. Ein globales Konto hat keine Muttergesellschaft, kann jedoch Tochtergesellschaften oder Geschäftsbereiche haben, die zum globalen Konto gehören. Wenn Sie den Container Globales Konto in Ihrer Verbindung konfiguriert haben, sollte ein Konto, das keine übergeordneten oder untergeordneten Elemente hat, sowohl im Feld Konto als auch im Feld Globales Konto aufgeführt werden. |
| Opportunity (optional) | Eine Sammlung von Produkten und Dienstleistungen, die zusammen verkauft werden. Eine Opportunity umfasste oft verschiedene Phasen des Verkaufszyklus bis zum Abschluss des Verkaufs.<br>Sie würden Daten verwenden, um den Opportunity-Fortschritt durch den Verkaufstrichter zu messen. Beispiel: ein Bericht mit Details zu den wichtigsten Opportunitys, die von Phase 3 zu Phase 4 übergegangen sind. |
| Einkaufsgruppe (optional) | Eine Sammlung von Personen innerhalb einer Organisation, die am Entscheidungsprozess zum Kauf eines Produkts oder einer Dienstleistung beteiligt ist. <br/>Sie würden kaufende Gruppendaten verwenden, um Einkaufsgruppen über das Kampagnen-Management zu verfolgen. Erstellen Sie beispielsweise ein Zielgruppensegment aus wichtigen Einkaufsgruppen.<br/> Sie möchten wahrscheinlich eine Suche von der Einkaufsgruppe zu den Profildaten durchführen, damit Sie Berichte zu den Personen in einer Einkaufsgruppe erstellen können. |
| Person | Eine Person, die häufig durch eine eindeutige E-Mail-Adresse identifiziert wird, die mit dem Unternehmen interagiert hat. <br/>Sie würden die Profildaten verwenden, um Personen zu identifizieren, die für ein Konto arbeiten. Beispiel: Targeting aller Personen auf einem Konto, die sich für eine Konferenz angemeldet haben. |

>[!IMPORTANT]
>
>* Wenn Sie **aktiviert** den Container Globales Konto in einer kontobasierten Verbindung haben, sollte jeder Datensatz in Ihren Ereignisdatensätzen eine Konto-ID und eine globale Konto-ID enthalten. Andernfalls wird der Datensatz übersprungen.
>* Wenn Sie **nicht aktiviert** den Container Globales Konto in einer kontobasierten Verbindung aktiviert haben, sollte jeder Datensatz in Ihren Ereignisdatensätzen eine Konto-ID enthalten. Andernfalls wird der Datensatz übersprungen.

## Datensätze

Beim Konfigurieren [Datensatzeinstellungen](/help/connections/create-connection.md#dataset-settings) für Ihre kontobasierte Verbindung in Customer Journey Analytics B2B edition hängen die für einige Einstellungen verfügbaren Optionen vom [Datensatztyp](/help/connections/create-connection.md#dataset-types) ab. Sie müssen beispielsweise:

* Geben Sie Kennungen für jeden der Container an, die Sie für Ihre Ereignis-Datensätze konfiguriert haben.
* Definieren Sie ein Kontofeld oder ein globales Kontofeld für Ihre Profildatensätze.
* Definieren Sie Schlüssel und wie diese Schlüssel (nach Container des Felds) für Lookup-Datensätze zugeordnet werden.

## Übereinstimmung nach Container oder Feld

Sie können für jeden Lookup-Datensatz definieren, unabhängig davon, ob Sie dem Datensatz nach Feld oder nach Container entsprechen.

### Übereinstimmung nach Container

Wenn ein Datensatzdatensatz eine Übereinstimmung nach Container verwendet, wird der Datensatzdatensatz in der Benutzeroberfläche als Profildatensatztyp und als Profildatensatz behandelt. Verwenden Sie „Übereinstimmung nach Container“ für Datensätze, die Ihre konfigurierten Container unterstützen. Beispiel: ein Datensatz für eine Einkaufsgruppe.

### Übereinstimmung nach Feld

Wenn ein Datensatzdatensatz ein Feld vom Typ Übereinstimmung verwendet, wird der Datensatzdatensatz in der Benutzeroberfläche als Such-Datensatztyp und als Such-Datensatz behandelt. Verwenden Sie das Feld „Übereinstimmung nach“ für Datensätze, die zusätzliche Details über die Suche unterstützen, z. B. einen Marketing-Listenmitglied-Datensatz oder einen Produktdetails-Datensatz.


## Bericht zu Personen- und Account-basierten Daten

Wenn Sie Berichte zu personenbasierten Containern (und Personenidentitäten) und kontobasierten Containern (und Kontoidentitäten) erstellen möchten, sollten Sie zwei separate Verbindungen innerhalb von Customer Journey Analytics einrichten. Eine Verbindung, bei der Sie Person als Primäre ID auswählen, und eine Verbindung, bei der Sie Account als Primäre ID auswählen. Customer Journey Analytics unterstützt keine personenbasierten und kontobasierten Berichte aus einer einzelnen Container-Hierarchie.

