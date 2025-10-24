---
title: Beispiel für ein B2B-Projekt
description: Erfahren Sie, wie Sie B2B-Daten einrichten, konfigurieren und Berichte dazu erstellen
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: d1097ca5f981623283a7d02200d5023548046429
workflow-type: tm+mt
source-wordcount: '1373'
ht-degree: 8%

---

# Beispiel für ein personenbasiertes B2B-Projekt

Dieser Artikel veranschaulicht einen Anwendungsfall, bei dem Sie im Rahmen eines typischen personenbasierten B2B-Setups in Customer Journey Analytics ordnungsgemäß Berichte zu Personendaten erstellen möchten. Eine solche Konfiguration wird durch die [Real-Time CDP B2B edition](https://experienceleague.adobe.com/de/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview) erleichtert.  In diesem Anwendungsbeispiel wird erläutert, wie B2B-Daten auf Profilebene (Personen) in Customer Journey Analytics eingerichtet und konfiguriert werden und wie Berichte erstellt werden.

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Mit der Veröffentlichung von [Customer Journey Analytics B2B edition wird ein separater Abschnitt für Anwendungsfälle des kontobasierten Reportings &#x200B;](/help/getting-started/cja-b2b-edition.md).

## Verbindung

Definieren Sie Ihre Verbindung, um alle relevanten B2B-Datensätze von Experience Platform einzuschließen. Datensätze, die Sie Ihrer Verbindung hinzufügen können:

| Datensatz (optional) | Schema | Typ des Schemas | Basisklasse | Beschreibung |
|---|---|---|---|---|
| B2B-Aktivitätsdatensatz | B2B-Aktivitätsschema | Ereignis | XDM ExperienceEvent | Ein ExperienceEvent ist eine Aufzeichnung von Ereignissen, einschließlich des Zeitpunkts und der Identität der beteiligten Person. ExperienceEvents können entweder explizit (direkt beobachtbare menschliche Aktionen) oder implizit (ohne direkte menschliche Aktion ausgelöst) sein und werden ohne Aggregation oder Interpretation aufgezeichnet. Erlebnisereignisse sind für die Zeitbereichsanalyse von entscheidender Bedeutung, da sie die Beobachtung und Analyse von Änderungen, die in einem bestimmten Zeitfenster auftreten, und den Vergleich zwischen mehreren Zeitfenstern ermöglichen, um Trends zu verfolgen. |
| B2B-Personendatensatz | B2B-Personen-Schema | Profil | Individuelles XDM-Profil | Ein XDM Individual Profile bildet eine einzige Darstellung der Attribute und Interessen sowohl identifizierter als auch teilweise identifizierter Personen. Weniger identifizierte Profile können nur anonyme Verhaltenssignale enthalten, wie z. B. Browser-Cookies, während stark identifizierte Profile detaillierte persönliche Informationen wie Name, Geburtsdatum, Standort und E-Mail-Adresse enthalten können. Wenn ein Profil wächst, wird es zu einem robusten Speicher für persönliche Informationen, Identifizierungsinformationen, Kontaktdaten und Kommunikationsvoreinstellungen einer Person. |
| B2B-Kontodatensatz | B2B-Kontoschema | Lookup | XDM Business Account | Ein XDM Business-Konto ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften eines Geschäftskontos erfasst. Diese XDM-Klasse kann dem Profil nur dann hinzugefügt werden, wenn die B2B- oder B2P-Edition verwendet wird. |
| B2B-Opportunity-Datensatz | B2B-Opportunity-Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Business Opportunity erfasst. Diese XDM-Klasse kann dem Profil nur dann hinzugefügt werden, wenn die B2B- oder B2P-Edition verwendet wird. |
| B2B-Kampagnen-Datensatz | B2B-Kampagnenschema | Lookup | XDM Business Campaign | XDM Business Campaign ist eine Standardklasse des XDM (Experience Data Model), die die erforderlichen Mindesteigenschaften einer Unternehmenskampagne erfasst. Diese XDM-Klasse kann dem Profil nur dann hinzugefügt werden, wenn die B2B- oder B2P-Edition verwendet wird. |
| B2B-Marketing-Listen-Datensatz | B2B-Marketing-Listenschema | Lookup | XDM Business Marketing List | XDM Business Marketing List ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Marketing-Liste erfasst. Mithilfe von Marketing-Listen können Sie sich auf potenzielle Kunden konzentrieren, die am ehesten Ihr Produkt kaufen würden. Diese XDM-Klasse kann dem Profil nur dann hinzugefügt werden, wenn die B2B- oder B2P-Edition verwendet wird. |
| B2B-Konto-Personen-Beziehungsdatensatz | B2B-Konto-Personen-Beziehungsschema | Lookup | XDM Business Account Person Relation | XDM Business Account Person Relation ist eine Standardklasse des XDM (Experience Data Model), die die erforderlichen Mindesteigenschaften einer Person erfasst, die einem Geschäftskonto zugeordnet ist. |
| B2B-Opportunity-Personenbeziehungsdatensatz | B2B-Opportunity-Personenbeziehungsschema | Lookup | XDM Business Opportunity Person Relation | XDM Business Opportunity Person Relation ist eine Standardklasse des XDM (Experience Data Model), die die erforderlichen Mindesteigenschaften einer Person erfasst, die einer Geschäftschance zugeordnet ist. |
| B2B-Marketing-Listenmitglied-Datensatz | B2B-Marketing-Listenmitglied-Schema | Lookup | XDM Marketing List Members | XDM Business Marketing List Members ist eine Standardklasse des XDM (Experience-Datenmodell), die Mitglieder, Personen oder Kontakte beschreibt, die mit einer Marketing-Liste verknüpft sind. |
| B2B-Kampagnenmitglied-Datensatz | B2B-Kampagnenmitglied-Schema | Lookup | XDM Business Campaign Members | XDM Business Campaign Members ist eine Standardklasse des XDM (Experience Data Model), die einen Kontakt oder Lead beschreibt, der einer Unternehmenskampagne zugeordnet ist. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


Die Beziehung zwischen den B2B-Lookup-Schemas, dem Profilschema und dem Ereignisschema wird im B2B-Setup in Experience Platform definiert. Siehe Schemata in [Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/de/docs/experience-platform/rtcdp/schemas/b2b) und [Definieren einer Viele-zu-eins-Beziehung zwischen zwei Schemata in Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/relationship-b2b).


Um eine ordnungsgemäße Einrichtung einer Verbindung sicherzustellen, die personenbasierte Suchen Ihrer B2B-Daten unterstützt, verwenden Sie die folgende Abbildung für einen Überblick und führen Sie die folgenden Schritte aus:

![B2B-Schemata mit Anmerkungen](assets/b2b-schemas-annotated.svg)

1. Fügen Sie Datensätze aus der obigen Tabelle zu Ihrer Verbindung hinzu.
1. Für jeden Lookup-Datensatz, den Sie Ihrer Verbindung hinzufügen, müssen Sie die Beziehung zu einem Ereignis-Datensatz explizit mit dem **[!UICONTROL Schlüssel]** und dem **[!UICONTROL Übereinstimmungsschlüssel]** im Dialogfeld **[!UICONTROL Datensatz bearbeiten]** definieren.
1. Aktivieren Sie für jeden Lookup-Datensatz, den Sie für personenbasierte B2B-Suchen umwandeln möchten **[!UICONTROL die Option „Datensatz]**&quot;, um sicherzustellen, dass die Daten für personenbasierte Suchen umgewandelt werden. Weitere [&#x200B; finden Sie unter „Transformieren von Datensätzen für B2B](/help/connections/transform-datasets-b2b-lookups.md)Suchen“.

   ![Schlüssel - Passender Schlüssel](assets/key-matchingkey.png)

   Die nachstehende Tabelle bietet eine Beispielübersicht über die [!UICONTROL Personen-ID], [!UICONTROL Schlüssel] und [!UICONTROL Übereinstimmender Schlüssel] Beispielwerte für jeden der Datensätze.

   >[!IMPORTANT]
   >
   >Die Werte für **Personen-ID**, **Schlüssel** und **übereinstimmender Schlüssel** in der folgenden Tabelle sind **Beispielwerte** und können in Ihrer spezifischen Umgebung unterschiedlich sein.
   >


   | Datensatz (optional) | Personen-ID | Schlüssel<br/> | Übereinstimmender Schlüssel <br/>im Ereignisdatensatz)<br/> |
   |---|---|---|---| 
   | B2B-Aktivitätsdatensatz | SourceKey <br/>**personKey.sourceKey** | | |
   | B2B-Personendatensatz | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | B2B-Kontodatensatz | | SourceKey <br/>**accountKey.sourceKey**&#x200B;❶ | SourceKey<br>(B2B-Personen-Datensatz)<br/>**b2b.accountKey.sourceKey**&#x200B;❶ |
   | B2B-Opportunity-Datensatz | | Source Key <br/>**OpportunityKey.sourceKey**&#x200B;❷ | SourceKey<br/>(B2B Opportunity Relation-Datensatz)<br/>**OpportunityKey.sourceKey**&#x200B;❷ |
   | B2B-Kampagnen-Datensatz | | SourceKey <br/>**campaignKey.sourceKey**&#x200B;❸ | SourceKey<br/>(B2B-Kampagnenmitglied-Datensatz)<br/>**campaignKey.sourceKey**&#x200B;❸<br/> |
   | B2B-Marketing-Listen-Datensatz | | SourceKey <br/>**marketingListKey.sourceKey**&#x200B;❹ | SourceKey<br/>(B2B-Marketing-Listenmitglied-Datensatz)<br/>**marketingListKey.sourceKey**&#x200B;❹ |
   | B2B-Konto-Personen-Beziehungsdatensatz | | SourceKey <br/>**personKey.sourceKey**&#x200B;❺ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❺ |
   | B2B-Opportunity-Personenbeziehungsdatensatz | | SourceKey <br/>**personKey.sourceKe** y❻ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❻ |
   | B2B-Kampagnenmitglied-Datensatz | | SourceKey <br/>**personKey.sourceKey**&#x200B;❼ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❼ |
   | B2B-Marketing-Listenmitglied-Datensatz | | SourceKey <br/>**personKey.sourceKey**&#x200B;❽ | Source Key<br/>(Event datasets)<br/>**personKey.sourceKey**&#x200B;❽ |

{style="table-layout:auto"}

Weitere [&#x200B; zum Konfigurieren von Einstellungen für einen Datensatz finden &#x200B;](../../connections/create-connection.md) unter „Hinzufügen und Konfigurieren von Datensätzen“.


## Datenansicht

Um beim Erstellen Ihres Workspace-Projekts Zugriff auf relevante B2B-Dimensionen und -Metriken zu erhalten, müssen Sie Ihre Datenansicht entsprechend definieren.

Sie können beispielsweise die folgenden Komponenten zu Ihrer Datenansicht hinzufügen, um sicherzustellen, dass Sie auf Personenebene Berichte zu Ihren B2B-Daten erstellen können. Die Komponentennamen werden manchmal geändert, um die Klarheit ausgehend von den ursprünglichen Schemanamen zu verbessern.

+++Metriken 

>[!IMPORTANT]
>
>Die Metriken und ihre Werte (**Komponentenname**, **Datensatz**, **Datensatztyp** und **[!UICONTROL Schemapfad])** der folgenden Tabelle **Beispiele**. Definieren Sie relevante B2B-Metriken (Komponentenname, Datensatz, Datentyp und Schemapfad) für Ihre spezifische Situation.
>

| Name der Komponente | Datensatz | Datentyp | Pfad des Schemas |
|---|---|---|---|
| Jährliche Kontoeinnahmen | B2B-Kontodatensatz | Double | accountOrganization.annualRevenue.amount |
| Anzahl der Mitarbeiter | B2B-Kontodatensatz | Ganzzahl | accountOrganization.numberOfEmployees |
| Tatsächliche Kampagnenkosten | B2B-Kampagnen-Datensatz | Double | actualCost.amount |
| Budgetierte Kampagnenkosten | B2B-Kampagnen-Datensatz | Double | budgetedCost.amount |
| Erwarteter Opportunity-Umsatz | B2B-Opportunity-Datensatz | Double | expectedRevenue.amount |
| Erwarteter Kampagnenumsatz | B2B-Kampagnen-Datensatz | Double | expectedRevenue.amount |
| Opportunity-Betrag | B2B-Opportunity-Datensatz | Double | opportunityAmount.amount |

+++

+++Dimensionen

>[!IMPORTANT]
>
>Die Dimensionen und ihre Werte (**Komponentenname**, **Datensatz**, **Datensatztyp** und **[!UICONTROL Schemapfad])** der folgenden Tabelle **Beispiele**. Definieren Sie relevante B2B-Dimensionen (Komponentenname, Datensatz, Datentyp und Schemapfad) für Ihre spezifische Situation.
>

| Name der Komponente | Datensatz | Datentyp | Pfad des Schemas |
|---|---|---|---|
| Kontoname | B2B-Kontodatensatz | Zeichenfolge | accountName |
| Kampagnenname | B2B-Kampagnen-Datensatz | Zeichenfolge | campaignName |
| Kanalname | B2B-Kampagnen-Datensatz | Zeichenfolge | channelName |
| Land | B2B-Kontodatensatz | Zeichenfolge | accountBillingAddress.country |
| Name der Vorhersagekategorie | B2B-Opportunity-Datensatz | Zeichenfolge | forecastCategoryName |
| Branche | B2B-Kontodatensatz | Zeichenfolge | accountOrganization.industry |
| Last name | B2B-Personendatensatz | Zeichenfolge | person.name.lastName |
| Marketing-Listenname | B2B-Marketing-Listen-Datensatz | Zeichenfolge | marketingListName |
| Opportunity-Name | B2B-Opportunity-Datensatz | Zeichenfolge | OpportunityName |
| Opportunity-Phase | B2B-Opportunity-Datensatz | Zeichenfolge | OpportunityStage |
| Opportunity-Typ | B2B-Opportunity-Typ-Datensatz | Zeichenfolge | OpportunityType |
| Name der Webinar-Sitzung | B2B-Kampagnen-Datensatz | Zeichenfolge | webinarSessionName |

+++

## Workspace

Nachdem Sie Ihre Komponenten ordnungsgemäß in der Datenansicht definiert haben, können Sie jetzt spezifische B2B-Berichte und Visualisierungen in Ihrem Workspace-Projekt erstellen.

Im Folgenden finden Sie einen Screenshot eines Beispielprojekts, das auf der oben beschriebenen Verbindung und Datenansicht basiert. Die Visualisierungsbeschreibungen erläutern, welche der Freiformtabellen-Visualisierungen auf den umgewandelten B2B-Lookup-Daten basieren.

![Beispielprojekt](assets/sample-workspace-project.png)

