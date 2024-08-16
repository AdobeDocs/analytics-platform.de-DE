---
title: Beispiel für ein B2B-Projekt
description: Erfahren Sie, wie Sie B2B-Daten einrichten, konfigurieren und Berichte zu diesen erstellen
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 20756b289912dfcc4e0539db4d1ae36d1496a266
workflow-type: tm+mt
source-wordcount: '1205'
ht-degree: 9%

---

# Beispiel für ein B2B-Projekt

In diesem Artikel wird beschrieben, wie Sie B2B-Daten auf Profil-(Personen-)Ebene in Customer Journey Analytics einrichten, konfigurieren und Berichte dazu erstellen.

## Verbindung

Definieren Sie Ihre Verbindung, um alle relevanten B2B-Datensätze aus Experience Platform einzuschließen. Datensätze, die Sie Ihrer Verbindung hinzufügen können:

| Datensatz | Schema | Typ des Schemas | Basisklasse | Beschreibung |
|---|---|---|---|---|
| B2B-Aktivitätsdatensatz | B2B-Aktivitätsschema | Ereignis | XDM ExperienceEvent | Ein ExperienceEvent ist ein Faktendatensatz, in dem aufgezeichnet wird, was geschehen ist, einschließlich des Zeitpunkts und der Identität der beteiligten Person. ExperienceEvents kann entweder explizit (direkt beobachtbare menschliche Aktionen) oder implizit (ohne direkte menschliche Aktion ausgelöst) sein und ohne Aggregation oder Interpretation aufgezeichnet werden. Erlebnisereignisse sind für die Zeitdomänenanalyse von entscheidender Bedeutung, da sie die Beobachtung und Analyse von Änderungen ermöglichen, die in einem bestimmten Zeitfenster auftreten, und den Vergleich zwischen mehreren Zeitfenstern, um Trends zu verfolgen. |
| B2B-Personendatensatz | B2B-Personenschema | Profil | Individuelles XDM-Profil | Ein individuelles XDM-Profil bildet eine einzige Darstellung der Attribute und Interessen sowohl identifizierter als auch teilweise identifizierter Personen. Weniger identifizierte Profile dürfen nur anonyme Verhaltenssignale wie Browser-Cookies enthalten, während hoch identifizierte Profile detaillierte persönliche Informationen wie Name, Geburtsdatum, Ort und E-Mail-Adresse enthalten können. Mit zunehmendem Profil wird es zu einem robusten Repository mit personenbezogenen Daten, Identifizierungsinformationen, Kontaktdaten und Kommunikationseinstellungen für eine Person. |
| B2B-Kontodatensatz | B2B-Kontoschema | Suche | XDM Business Account | Ein XDM-Geschäftskonto ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften eines Geschäftskontos erfasst. Diese XDM-Klasse kann nur für Kunden mit B2B oder B2P Edition in das Profil aufgenommen werden. |
| B2B-Angebotsdatensatz | Schema für B2B-Chancen | Suche | XDM Business Opportunity | XDM Business Opportunity ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Geschäftschance erfasst. Diese XDM-Klasse kann nur für Kunden mit B2B oder B2P Edition in das Profil aufgenommen werden. |
| B2B-Kampagnensatz | B2B-Kampagnenschema | Suche | XDM Business Campaign | XDM Business Campaign ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Geschäftskampagne erfasst. Diese XDM-Klasse kann nur für Kunden mit B2B oder B2P Edition in das Profil aufgenommen werden. |
| Datensatz der B2B-Marketingliste | B2B-Marketinglisten-Schema | Suche | XDM Business Marketing List | XDM Business Marketing List ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Marketing-Liste erfasst. Marketinglisten ermöglichen es Ihnen, potenzielle Kunden zu priorisieren, die Ihr Produkt am ehesten kaufen. Diese XDM-Klasse kann nur für Kunden mit B2B oder B2P Edition in das Profil aufgenommen werden. |
| Datensatz zur B2B-Konto-Personenbeziehung | B2B-Konto-Personalisierungsschema | Suche | XDM Business Account Person Relation | XDM Business Account Person Relation ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Person erfasst, die mit einem Geschäftskonto verknüpft ist. |
| Datensatz zu B2B-Chancen-Personenbeziehungen | B2B Opportunity Person Relationschema | Suche | XDM Business Opportunity Person Relation | XDM Business Opportunity Person Relation ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Person erfasst, die mit einer Geschäftschance verknüpft ist. |
| B2B Marketing List Member Datensatz | B2B Marketing List Member Schema | Suche | XDM-Marketing-Listenmitglieder | XDM Business Marketing List Members ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die Mitglieder, Personen oder Kontakte beschreibt, die mit einer Marketingliste verknüpft sind. |
| B2B Campaign-Mitgliederdatensatz | B2B Campaign-Mitgliederschema | Suche | XDM Business Campaign Members | XDM Business Campaign-Mitglieder sind eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die einen Kontakt oder einen Lead beschreibt, der mit einer Geschäftskampagne verknüpft ist. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


Die Beziehung zwischen den B2B-Lookup-Schemas, dem Profilschema und dem Ereignisschema wird in der B2B-Einrichtung innerhalb von Experience Platform definiert. Siehe Schemas in [Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) und [Definieren einer n:1-Beziehung zwischen zwei Schemas in Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b).


Um eine ordnungsgemäße Einrichtung einer Verbindung sicherzustellen, die personenbasierte Suchen Ihrer B2B-Daten unterstützt, verwenden Sie die folgende Abbildung für eine Übersicht und führen Sie die folgenden Schritte aus:

![B2B-Schemas kommentiert](assets/b2b-schemas-annotated.svg)

1. Fügen Sie Ihrer Verbindung Datensätze aus der obigen Tabelle hinzu.
1. Für jeden Lookup-Datensatz, den Sie Ihrer Verbindung hinzufügen, müssen Sie die Beziehung zu einem Ereignis-Datensatz explizit mit dem Schlüssel **[!UICONTROL 1} und dem Schlüssel**[!UICONTROL &#x200B;Übereinstimmung ]**im Dialogfeld**[!UICONTROL  Datensatz bearbeiten ]**definieren.]**
1. Aktivieren Sie für jeden Lookup-Datensatz, den Sie für personenbasierte B2B-Suchen transformieren möchten, **[!UICONTROL Datensatz transformieren]** , um sicherzustellen, dass die Daten für personenbasierte Suchen umgewandelt werden. Weitere Informationen finden Sie unter [Transform datasets for B2B lookups](/help/connections/transform-datasets-b2b-lookups.md) .

   ![Schlüssel - Abgleichschlüssel](assets/key-matchingkey.png)

   Die nachstehende Tabelle bietet eine Beispielübersicht der Werte [!UICONTROL Personen-ID], [!UICONTROL Schlüssel] und [!UICONTROL Schlüssel-Übereinstimmung] für jeden Datensatz.

   | Datensatz | Personen-ID | Schlüssel | Übereinstimmung mit Schlüssel<br/> (im Ereignis-Datensatz) |
   |---|---|---|---| 
   | B2B-Aktivitätsdatensatz | `personKey.sourceKey` | | |
   | B2B-Personendatensatz | `b2b.personKey.sourceKey` | | |
   | B2B-Kontodatensatz | | `accountKey.sourceKey`❶<br/> Source-Schlüssel | `b2b.accountKey.sourceKey`❶<br/>(B2B-Personendatensatz) |
   | B2B-Angebotsdatensatz | | `opportunityKey.sourceKey`❷<br/> Source-Schlüssel | `opportunityKey.sourceKey`❷<br/>(B2B Opportunity Relation DataSet) |
   | B2B-Kampagnensatz | | `campaignKey.sourceKey`❸<br/> Source-Schlüssel | `campaignKey.sourceKey`❸<br/>(B2B-Datensatz der Kampagnenmitglieder) |
   | Datensatz der B2B-Marketingliste | | `marketingListKey.sourceKey`❹<br/> Source-Schlüssel | `marketingListKey.sourceKey`❹<br/>(B2B Marketing List Member Datensatz) |
   | Datensatz zur B2B-Konto-Personenbeziehung | | `personKey.sourceKey`❺<br/> Source-Schlüssel | `personKey.sourceKey`❺<br/>Source-Schlüssel (Ereignis-Datensätze) |
   | Datensatz zu B2B-Chancen-Personenbeziehungen | | `personKey.sourceKey`❻<br/> Source-Schlüssel | `personKey.sourceKey`❻<br/>Source-Schlüssel (Ereignis-Datensätze) |
   | B2B Campaign-Mitgliederdatensatz | | `personKey.sourceKey`❼<br/> Source-Schlüssel | `personKey.sourceKey`❼<br/>Source-Schlüssel (Ereignis-Datensätze) |
   | B2B Marketing List Member Datensatz | | `personKey.sourceKey`❽<br/> Source-Schlüssel | `personKey.sourceKey`❽<br/>Source-Schlüssel (Ereignis-Datensätze) |

{style="table-layout:auto"}

Weitere Informationen zum Konfigurieren von Einstellungen für einen Datensatz finden Sie unter [Hinzufügen und Konfigurieren von Datensätzen](../../connections/create-connection.md) .


## Datenansicht

Um beim Erstellen Ihres Workspace-Projekts Zugriff auf relevante B2B-Dimensionen und -Metriken zu erhalten, müssen Sie Ihre Datenansicht entsprechend definieren.

Sie können beispielsweise die folgenden Komponenten zu Ihrer Datenansicht hinzufügen, um sicherzustellen, dass Sie Berichte auf personenbasierter Ebene auf Ihre B2B-Daten erstellen können. Die Komponentennamen werden manchmal aus Gründen der Klarheit aus den ursprünglichen Schemanamen geändert.

+++Metriken

| Name der Komponente | Datensatz | Datentyp | Pfad des Schemas |
|---|---|---|---|
| Jahresumsatz | B2B-Kontodatensatz | Double | accountOrganization.annualRevenue.amount |
| Anzahl der Mitarbeiter | B2B-Kontodatensatz | Ganzzahl | accountOrganization.numberOfEmployees |
| Tatsächliche Kampagnenkosten | B2B-Kampagnensatz | Double | actualCost.amount |
| Geplante Kampagnenkosten | B2B-Kampagnensatz | Double | budgetedCost.amount |
| Erwarteter Opportunity-Umsatz | B2B-Angebotsdatensatz | Double | expectedRevenue.amount |
| Erwarteter Kampagnenumsatz | B2B-Kampagnensatz | Double | expectedRevenue.amount |
| Opportunity Amount | B2B-Angebotsdatensatz | Double | opportunityAmount.amount |

+++

+++Dimensionen

| Name der Komponente | Datensatz | Datentyp | Pfad des Schemas |
|---|---|---|---|
| Kontoname | B2B-Kontodatensatz | Zeichenfolge | accountName |
| Kampagnenname | B2B-Kampagnensatz | Zeichenfolge | campaignName |
| Kanalname | B2B-Kampagnensatz | Zeichenfolge | channelName |
| Land | B2B-Kontodatensatz | Zeichenfolge | accountBillingAddress.country |
| Prognostizierter Kategoriename | B2B-Angebotsdatensatz | Zeichenfolge | forecastCategoryName |
| Branche | B2B-Kontodatensatz | Zeichenfolge | accountOrganization.industry |
| Last name | B2B-Personendatensatz | Zeichenfolge | person.name.lastName |
| Name der Marketing-Liste | Datensatz der B2B-Marketingliste | Zeichenfolge | marketingListName |
| Opportunity Name | B2B-Angebotsdatensatz | Zeichenfolge | OpportunityName |
| Opportunity Stage | B2B-Angebotsdatensatz | Zeichenfolge | OpportunityStage |
| Opportunity type | Datensatz vom Typ B2B-Chancen | Zeichenfolge | OpportunityType |
| Webinar-Sitzungsname | B2B-Kampagnensatz | Zeichenfolge | webinarSessionName |

+++

## Workspace

Nachdem Ihre Komponenten in der Datenansicht ordnungsgemäß definiert wurden, können Sie jetzt spezifische B2B-Berichte und -Visualisierungen in Ihrem Workspace-Projekt erstellen.

Im Folgenden finden Sie einen Screenshot eines Beispielprojekts, das auf der oben beschriebenen Verbindungs- und Datenansicht basiert. Die Visualisierungsbeschreibungen erklären, welche der Freiformtabellen-Visualisierungen auf den umgewandelten B2B-Suchdaten basieren.

![Beispielprojekt](assets/sample-workspace-project.png)

