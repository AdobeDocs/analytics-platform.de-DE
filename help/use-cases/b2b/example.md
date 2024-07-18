---
title: Beispiel für ein B2B-Projekt
description: Erfahren Sie, wie Sie B2B-Daten einrichten, konfigurieren und Berichte zu diesen erstellen
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 9c60c00818e82a6ca891ab9d90260922437c6cca
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 11%

---

# Beispiel für ein B2B-Projekt

In diesem Artikel wird beschrieben, wie Sie B2B-Daten auf Profil-(Personen-)Ebene in Customer Journey Analytics einrichten, konfigurieren und Berichte dazu erstellen.

## Verbindung

Definieren Sie Ihre Verbindung, um alle relevanten B2B-Datensätze aus Experience Platform einzuschließen. Stellen Sie sicher, dass Sie alle relevanten Lookup-Datensätze einschließen und transformieren, die für ein typisches B2B-personenbasiertes Berichtsszenario erforderlich sind. Weitere Informationen finden Sie unter [Transformieren von B2B-Lookup-Datensätzen](/help/connections/transform-datasets-b2b-lookups.md) .

Datensätze, die Sie Ihrer Verbindung hinzufügen können:

| Datensatz | Schema | Typ des Schemas | Basisklasse | Beschreibung |
|---|---|---|---|---|
| B2B-Aktivitätsdatensatz | B2B-Aktivitätsschema | Ereignis | XDM ExperienceEvent | Ein ExperienceEvent ist ein Faktendatensatz, in dem aufgezeichnet wird, was geschehen ist, einschließlich des Zeitpunkts und der Identität der beteiligten Person. ExperienceEvents kann entweder explizit (direkt beobachtbare menschliche Aktionen) oder implizit (ohne direkte menschliche Aktion ausgelöst) sein und ohne Aggregation oder Interpretation aufgezeichnet werden. Sie sind für die Zeitdomänenanalyse von entscheidender Bedeutung, da sie die Beobachtung und Analyse von Änderungen ermöglichen, die in einem bestimmten Zeitfenster auftreten, und den Vergleich zwischen mehreren Zeitfenstern, um Trends zu verfolgen. |
| B2B-Personendatensatz | B2B-Personenschema | Profil | Individuelles XDM-Profil | Ein individuelles XDM-Profil bildet eine einzige Darstellung der Attribute und Interessen sowohl identifizierter als auch teilweise identifizierter Personen. Weniger identifizierte Profile dürfen nur anonyme Verhaltenssignale wie Browser-Cookies enthalten, während hoch identifizierte Profile detaillierte persönliche Informationen wie Name, Geburtsdatum, Ort und E-Mail-Adresse enthalten können. Mit zunehmendem Profil wird es zu einem robusten Repository mit personenbezogenen Daten, Identifizierungsinformationen, Kontaktdaten und Kommunikationseinstellungen für eine Person. |
| Datensatz zur B2B-Konto-Personenbeziehung | B2B-Konto-Personalisierungsschema | Suche | XDM Business Account Person Relation | XDM Business Account Person Relation ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Person erfasst, die mit einem Geschäftskonto verknüpft ist. |
| Datensatz zu B2B-Chancen-Personenbeziehungen | B2B Opportunity Person Relationschema | Suche | XDM Business Opportunity Person Relation | XDM Business Opportunity Person Relation ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Person erfasst, die mit einer Geschäftschance verknüpft ist. |
| B2B Marketing List Members Datensatz | Schema der B2B-Marketinglisten-Mitglieder | Suche | XDM-Marketing-Listenmitglieder | XDM Business Marketing List Members ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die Mitglieder, Personen oder Kontakte beschreibt, die mit einer Marketingliste verknüpft sind. |
| B2B Campaign-Mitgliederdatensatz | B2B Campaign-Mitgliederschema | Suche | XDM Business Campaign Members | XDM Business Campaign-Mitglieder sind eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die einen Kontakt oder einen Lead beschreibt, der mit einer Geschäftskampagne verknüpft ist. |
<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


Die Beziehung zwischen den Lookup-Schemas, dem Profilschema und dem Ereignisschema wird in der B2B-Einrichtung innerhalb von Experience Platform definiert. Weitere Informationen finden Sie unter Schemas in [Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html) und unter [Definieren einer n:1-Beziehung zwischen zwei Schemas in Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html) .

![Beziehung zwischen B2B-Schemata](assets/classes.png)

Für jeden Lookup-Datensatz, den Sie Ihrer Verbindung hinzufügen, müssen Sie die Beziehung zu einem Ereignis-Datensatz explizit mit **[!UICONTROL Schlüssel]** und **[!UICONTROL Übereinstimmungsschlüssel]** im Dialogfeld **[!UICONTROL Datensatz bearbeiten]** definieren. Zum Beispiel:

![Schlüssel - Abgleichschlüssel](assets/key-matchingkey.png)

Es werden explizit vier Schemas verwendet, um das Personen-Schema mit anderen relevanten Schemas zu verbinden: Konto, Chancen, Kampagne und Marketingliste. Diese Schemas basieren auf den folgenden Schemaklasse:

* XDM Business Account Person Relation
* XDM Business Opportunity Person Relation
* XDM Business Marketing List Members
* XDM Business Campaign Members

Für jeden Lookup-Datensatz aktivieren Sie für ein Schema, das auf einer solchen Schemaklasse basiert, außerdem **[!UICONTROL Datensatz transformieren]** , um sicherzustellen, dass die Daten für personenbasierte Suchen umgewandelt werden. Weitere Informationen finden Sie unter [Umwandeln von Datensätzen für B2B-Suchen](/help/connections/transform-datasets-b2b-lookups.md).

Die nachstehende Tabelle bietet eine Beispielübersicht der Werte [!UICONTROL Personen-ID], [!UICONTROL Schlüssel] und [!UICONTROL Schlüssel-Übereinstimmung] für jeden Datensatz.


| Datensatz | Personen-ID | Schlüssel | Übereinstimmungsschlüssel (im Ereignis-Datensatz) |
|---|---|---|---|
| B2B-Aktivitätsdatensatz | `personKey.sourceKey` | | |
| B2B-Personendatensatz | `b2b.personKey.sourceKey` | | |
| B2B-Konto-Personendatensatz | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B-Angebotsdatensatz | | `personKey.sourceKey` | `personKey.sourceKey` |
| Datensatz mit B2B-Kampagnenmitgliedern | | `personKey.sourceKey` | `personKey.sourceKey` |
| Datensatz der B2B-Marketingliste | | `personKey.sourceKey` | `personKey.sourceKey` |

{style="table-layout:auto"}

Weitere Informationen zum Konfigurieren von Einstellungen für einen Datensatz finden Sie unter [Hinzufügen und Konfigurieren von Datensätzen](../../connections/create-connection.md) .


## Datenansicht

Um beim Erstellen Ihres Workspace-Projekts Zugriff auf relevante B2B-Dimensionen und -Metriken zu erhalten, müssen Sie Ihre Datenansicht entsprechend definieren.

Sie können die folgenden Komponenten als Dimensionen zu Ihrer Datenansicht hinzufügen, um sicherzustellen, dass Sie auf personenbasierter Ebene Berichte zu Ihren B2B-Daten erstellen können. Die Komponentennamen werden für mehr Klarheit geändert.

| Name der Komponente | Datensatz | Datentyp des Schemas | Pfad des Schemas |
|---|---|---|---|
| Benutzer | B2B-Aktivität | Zeichenfolge | `personID` |
| Konto | B2B-Kontoperson | Zeichenfolge | `accountKey.sourceID` |
| Kampagne | B2B Campaign-Mitglied | Zeichenfolge | `campaignKey.sourceKey` |
| Name der Marketing-Liste | B2B-Marketingliste | Zeichenfolge | `marketingListID` |
| Opportunity | B2B-Opportunity Person | Zeichenfolge | `opportunityKey.sourceID` |


<!--
This section provides recommendations and suggestions on what dimensions and metrics to include when defining the [components](../../data-views/create-dataview.md#components) for B2B datasets in your data view.

For each component, the name, schema type, schema path, and (when applicable) details about the configuration are provided.


+++ B2B Activity dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Add To Campaign | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Add To Opportunity | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Application Closed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.close` |
| Application Launch | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.launch` |
| Campaign Stream | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Checkout | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.checkouts` |
| Convert Lead | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| Email Clicked | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| Email Delivered | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| Email Opened | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| Email Sent | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| Email Unsubscribed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Form Filled Out | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `web.formFilledOut` |
| Form Started | String | `web.fillOutForm.webFormName` | |
| Leads | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunity Updated | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Price | Double | *_organizationID*`.interactions.products.price` |  |
| Priority | Integer | `leadOperation.changeScore.priority` |  |
| Prod List Add | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Prod List Open | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Prod View | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Purchases | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Remove From Opportunity | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Save for Laters | String | eventType |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Account Key (Source Key) | String | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Converted Status | String | `leadOperation.convertLead.convertedStatus` | |
| Event Type | String | `eventType` | |
| Form Name | String | `leadOperation.newLead.formName` | |
| Identifier | String | `_id` | |
| Is Sent Notification | Boolean | `leadOperation.convertLead.isSentNotificationEmail` | |
| Keywords | String | `search.keywords` | |
| List ID | String | `listOperations.listID` | |
| List Name | String | `leadOperation.newLead.listName` | |
| Page Name | String | `web.webPageDetails.name` | |
| Person Key (Source Key) | String | `personKey.sourceKey` | |
| Produced By | String | producedBy | |
| Product Name | String | *_organizationID*`.Interactions.products.name` | |
| Role | String | `opportunityEvent.role` | | 
| Timestamp | Date-time | `timestamp` | Date-Time format: **[!UICONTROL Day]** |
| URL | String | `web.webPageDetails.URL` | |
| Web Form Name | String | `web.fillOutForm.webFormName` | |
| Product URL | String | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person dataset


### Metrics

No metric components are defined as part of this dataset.


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Last Activity Date | Date-time | `extSourceSystemAudit.lastActivityDate` | Date-Time format: **[!UICONTROL Day]** |
| Person ID | String | `personID` | |

{style="table-layout:auto"}

+++

+++ B2B Account Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Annual Revenue | Double | `accountOrganization.annualRevenue.amount` | |
| Number of employees | Integer | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Acount | String | `accountKey.sourceID` | 

{style="table-layout:auto"}

| Account Identifier | String | `accountID` | |
| Account Type | String | `accountType` | |
| City | String | `accountBillingAddress.city` | |
| Country | String | `accountBillingAddress.country` | |
| Industry | String | `accountOrganization.industry` | |
| Region | String | `accountBillingAddress.region` | |
| Source ID | String | `accountKey.sourceID` | |
| Source Instance ID | String | `accountKey.sourceInstanceID` | |
| Source Key | String | `accountKey.sourceKey` | |
| Source Type | String | `accountKey.sourceType` | |


+++

+++  B2B Opportunity Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Expected Revenue | Double | `expectedRevenue.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Closed - Booked` |
| Opportunity Stage - Prospect | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Prospect` |
| Opportunity Stage - Qualification | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Opportunity Stage - Solution Definition | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Closed Flag | Boolean | `isClosed` | |
| Company ID | String | `opportunityID` | |
| Forecast Category | String | `forecastCategoryName` | |
| Last Activity Date | Date-time | `lastActivityDate` | Date-time format: **[!UICONTROL Day]** |
| Lead Source | String | `leadSource` | |
| Opportunity Name | String | `opportunityName` | | 
| Opportunity Status | String | `opportunityStage` | |
| Won Flag | Boolean | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign Member dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Bounced | Long | *_organizationID*`.campaignBounced` | Behavior: **[!UICONTROL Count values]** |
| Clicked | Long | *_organizationID*`.campaignClicked` | Behavior: **[!UICONTROL Count values]** |
| Opened | Long | *_organizationID*`.CampaignOpened` | Behavior: **[!UICONTROL Count values]** |
| Sent | Long | *_organizationID*`.campaignSent` | Behavior: **[!UICONTROL Count values]** |
| Subscribed | Long | *_organizationID*`.campaignSubscribed` | Behavior: **[!UICONTROL Count values]** |
| Webinar Registrations | Long | *_organizationID*`.Registrations` | Behavior: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Campaign ID | String | `campaignID` | |
| Campaign Member ID | String | `campaignMemberID` | |
| Campaign Member Status | String | `memberStatus` | |
| Campaign Member Status Reason | String | `memberStatusReason` | |
| Created Date | Date-time | `extSourceSystemAudit.createdDate` | Date-time format: **[!UICONTROL Day]** |
| First Responded Date | String | `firstRespondedDate` | Date-time format: **[!UICONTROL Day]** |
| Has Reached Success | Boolean | `hasReachedSuccess` | |
| Has Responded | Boolean | `hasResponded` | |
| Last Status | String | `lastStatus` | |
| Last Updated Date | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Date-time format: **[!UICONTROL Day]** |
| Membership Date | Date-time | `membershipDate` | Date-time format: **[!UICONTROL Day]** |
| Nurture Cadence | String | `nurtureCadence` | |
| Nurture Track Name | String | `nurtureTrackName` | |
| Person ID | String | `personID` | |
| Reached Success Date | Date-time | `reachedSuccessDate` | Date-time format: **[!UICONTROL Day]** |
| Webinar Registration ID | String | `webinarRegistrationID` | |
| Webinar Registration URL | String | `webinarConfirmationUrl` | |
| isExhausted | Boolean | isExhausted | |

{style="table-layout:auto"}

+++

+++ B2B Marketing List Member dataset

### Metrics

### Dimensions

+++

-->

## Workspace

Nachdem Ihre Komponenten in der Datenansicht ordnungsgemäß definiert wurden, können Sie jetzt spezifische B2B-Berichte und -Visualisierungen in Ihrem Workspace-Projekt erstellen.

Nachfolgend finden Sie ein Beispielprojekt, das auf der oben beschriebenen Verbindungs- und Datenansicht basiert.

![Beispielprojekt](assets/sample-project.png)

<!-- See the descriptions for each visualization for more details.

+++ Example project

![Visualizations](assets/visualizations.png)

+++
-->
