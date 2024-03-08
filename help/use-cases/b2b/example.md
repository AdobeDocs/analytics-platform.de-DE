---
title: Beispiel für ein B2B-Projekt
description: Erfahren Sie, wie Sie B2B-Daten einrichten, konfigurieren und Berichte zu diesen erstellen
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1755'
ht-degree: 17%

---

# Beispiel für ein B2B-Projekt

In diesem Artikel wird anhand von Beispielen erläutert, wie B2B-Daten in Customer Journey Analytics eingerichtet, konfiguriert und in Berichten behandelt werden.

## Verbindung

Definieren Sie Ihre Verbindung, um alle relevanten B2B-Datensätze aus Experience Platform einzuschließen. Dazu gehören die wichtigen Lookup-Datensätze, die für eine typische B2B-Einrichtung innerhalb von Experience Platform erforderlich sind. Siehe [Hinzufügen von Daten auf Kontoebene als Lookup-Datensatz](b2b.md) für weitere Informationen.

Datensätze, die Sie Ihrer Verbindung hinzufügen können:

| Datensatz | Schema | Typ des Schemas | Basisklasse | Beschreibung |
|---|---|---|---|---|
| B2B-Aktivitätsdatensatz | B2B-Aktivitätsschema | Ereignis | XDM ExperienceEvent | Ein ExperienceEvent ist ein Faktendatensatz, in dem aufgezeichnet wird, was geschehen ist, einschließlich des Zeitpunkts und der Identität der beteiligten Person. ExperienceEvents kann entweder explizit (direkt beobachtbare menschliche Aktionen) oder implizit (ohne direkte menschliche Aktion ausgelöst) sein und ohne Aggregation oder Interpretation aufgezeichnet werden. Sie sind für die Zeitdomänenanalyse von entscheidender Bedeutung, da sie die Beobachtung und Analyse von Änderungen ermöglichen, die in einem bestimmten Zeitfenster auftreten, und den Vergleich zwischen mehreren Zeitfenstern, um Trends zu verfolgen. |
| B2B-Personendatensatz | B2B-Personenschema | Profil | Individuelles XDM-Profil | Ein individuelles XDM-Profil bildet eine einzige Darstellung der Attribute und Interessen sowohl identifizierter als auch teilweise identifizierter Personen. Weniger identifizierte Profile dürfen nur anonyme Verhaltenssignale wie Browser-Cookies enthalten, während hoch identifizierte Profile detaillierte persönliche Informationen wie Name, Geburtsdatum, Ort und E-Mail-Adresse enthalten können. Mit zunehmendem Profil wird es zu einem robusten Repository mit personenbezogenen Daten, Identifizierungsinformationen, Kontaktdaten und Kommunikationseinstellungen für eine Person. |
| B2B Campaign-Mitgliederdatensatz | B2B Campaign-Mitgliederschema | Suche | XDM Business Campaign Members | XDM Business Campaign-Mitglieder sind eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die einen Kontakt oder einen Lead beschreibt, der mit einer Geschäftskampagne verknüpft ist. |
| B2B-Kontodatensatz | B2B-Kontoschema | Suche | XDM Business Account | XDM Business Account ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften eines Geschäftskontos erfasst. |
| Datensatz zur B2B-Konto-Personenbeziehung | B2B-Konto-Personalisierungsschema | Suche | XDM Business Account Person Relation | XDM Business Account Person Relation ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Person erfasst, die mit einem Geschäftskonto verknüpft ist. |
| B2B-Angebotsdatensatz | Schema für B2B-Chancen | Suche | XDM Business Opportunity | XDM Business Opportunity ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Geschäftschance erfasst. |
| Datensatz zu B2B-Chancen-Personenbeziehungen | B2B Opportunity Person Relationschema | Suche | XDM Business Opportunity Person Relation | XDM Business Opportunity Person Relation ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Person erfasst, die mit einer Geschäftschance verknüpft ist. |
| B2B-Kampagnensatz | B2B-Kampagnenschema | Suche | XDM Business Campaign | XDM Business Campaign ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Geschäftskampagne erfasst. |
| Datensatz der B2B-Marketingliste | B2B-Marketinglisten-Schema | Suche | XDM-Marketingliste | XDM Business Marketing List ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die die erforderlichen Mindesteigenschaften einer Marketing-Liste erfasst. Marketinglisten ermöglichen es Ihnen, potenzielle Kunden zu priorisieren, die Ihr Produkt am ehesten kaufen. |
| B2B Marketing List Members Datensatz | Schema der B2B-Marketinglisten-Mitglieder | Suche | XDM-Marketing-Listenmitglieder | XDM Business Marketing List Members ist eine standardmäßige Experience-Datenmodell (XDM)-Klasse, die Mitglieder, Personen oder Kontakte beschreibt, die mit einer Marketingliste verknüpft sind. |

Die Beziehung zwischen den Lookup-Schemas, dem Profilschema und dem Ereignisschema wird in der B2B-Einrichtung innerhalb von Experience Platform definiert. Siehe Schemas in [Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html) und [Definieren einer 1:1-Beziehung zwischen zwei Schemas in Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html) für weitere Details.

![Beziehung zwischen B2B-Schemata](assets/classes.png)

Für jeden Lookup-Datensatz, den Sie Ihrer Verbindung hinzufügen, müssen Sie die Beziehung zu einem Ereignis-Datensatz explizit mit Schlüssel und Übereinstimmungsschlüssel im Dialogfeld Datensatz bearbeiten definieren. Zum Beispiel:

![Schlüssel - Übereinstimmung mit Schlüssel](assets/key-matchingkey.png)


Die nachstehende Tabelle bietet eine Beispielübersicht über die [!UICONTROL Personen-ID], [!UICONTROL Schlüssel], und [!UICONTROL Übereinstimmungsschlüssel] -Werte für jeden Datensatz.


| Datensatz | Personen-ID | Schlüssel | Übereinstimmungsschlüssel (im Ereignis-Datensatz) |
|---|---|---|---|
| B2B-Aktivitätsdatensatz | `personKey.sourceKey` | | |
| B2B-Personendatensatz | `b2b.personKey.sourceKey` | | |
| B2B-Kontodatensatz | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B-Angebotsdatensatz | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B-Kampagnensatz | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| Datensatz der B2B-Marketingliste | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


In der Tabelle *_organizationID*`.interaction.*`, bezieht sich auf die benutzerdefinierte Feldergruppe, die Sie dem Schema B2B-Aktivität hinzugefügt haben, um die Beziehung zum Schema B2B-Konto und B2B-Chancen zu definieren. Die `listOperations.listKey.sourceKey` bezieht sich auf die Feldergruppe Zu Liste hinzufügen , die zum Schema B2B-Aktivität hinzugefügt wurde und verfolgt werden soll, wenn eine Person zu einer bestimmten Liste hinzugefügt wird.

Siehe [Hinzufügen und Konfigurieren von Datensätzen](../../connections/create-connection.md) Weitere Informationen zum Konfigurieren von Einstellungen für einen Datensatz.


## Datenansicht

Um beim Erstellen Ihres Workspace-Projekts Zugriff auf relevante B2B-Dimensionen und -Metriken zu erhalten, müssen Sie Ihre Datenansicht entsprechend definieren.

Dieser Abschnitt enthält Empfehlungen und Vorschläge zu den Dimensionen und Metriken, die bei der Definition der [Komponenten](../../data-views/create-dataview.md#components) für B2B-Datensätze in Ihrer Datenansicht.

Für jede Komponente werden der Name, der Schematyp, der Schemapfad und (falls zutreffend) Details zur Konfiguration bereitgestellt.

+++ B2B-Aktivitäts-Datensatz

### Metriken

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Zu Kampagne hinzufügen | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `leadOperation.addToCampaign` |
| Zu Chancen hinzufügen | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `opportunityEvent.addToOpportunity` |
| Anwendung geschlossen | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `application.close` |
| Anwendungsstart | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `application.launch` |
| Kampagnen-Stream | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** ` leadOperation.changeCampaignStream` |
| Checkout | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `commerce.checkouts` |
| Blei konvertieren | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `leadOperation.convertLead` |
| E-Mail angeklickt | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `directMarketing.emailClicked` |
| Zugestellt E-Mail | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `directMarketing.emailDelivered` |
| E-Mail geöffnet | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `directMarketing.emailOpened` |
| E-Mail gesendet | Zeichenfolge | eventType | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `directMarketing.emailSent` |
| E-Mail-Abmeldung | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `directMarketing.emailUnsubscribed` |
| Ausgefülltes Formular | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `web.formFilledOut` |
| Formulare gestartet | Zeichenfolge | `web.fillOutForm.webFormName` | |
| Interessenten | Zeichenfolge | eventType | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `leadOperation.newLead` |
| Chancen aktualisiert | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `opportunityEvent.opportunityUpdated` |
| Preis | Double | *_organizationID*`.interactions.products.price` |  |
| Priorität | Ganzzahl | `leadOperation.changeScore.priority` |  |
| Hinzufügen von Produktlisten | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `commerce.productListAdds.value` |
| Liste öffnen | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `commerce.productListOpens.value` |
| Produktansicht | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `commerce.productViews.value` |
| Einkäufe | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `commerce.purchases.value` |
| Aus Opportunity entfernen | Zeichenfolge | `eventType` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `opportunityEvent.removeFromOpportunity` |
| Für Später speichern | Zeichenfolge | eventType | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensionen

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Kontoschlüssel (Quellschlüssel) | Zeichenfolge | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Konvertierter Status | Zeichenfolge | `leadOperation.convertLead.convertedStatus` | |
| Ereignistyp | Zeichenfolge | `eventType` | |
| Name des Formulars | Zeichenfolge | `leadOperation.newLead.formName` | |
| Kennung | Zeichenfolge | `_id` | |
| Wird gesendet | Boolesch | `leadOperation.convertLead.isSentNotificationEmail` | |
| Suchbegriffe | Zeichenfolge | `search.keywords` | |
| Listen-ID | Zeichenfolge | `listOperations.listID` | |
| Listenname | Zeichenfolge | `leadOperation.newLead.listName` | |
| Seitenname | Zeichenfolge | `web.webPageDetails.name` | |
| Personen-Schlüssel (Quellschlüssel) | Zeichenfolge | `personKey.sourceKey` | |
| hergestellt von | Zeichenfolge | productionBy | |
| Produktname | Zeichenfolge | *_organizationID*`.Interactions.products.name` | |
| Rolle | Zeichenfolge | `opportunityEvent.role` | |
| Zeitstempel | Datum-Uhrzeit | `timestamp` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| URL | Zeichenfolge | `web.webPageDetails.URL` | |
| Webformularname | Zeichenfolge | `web.fillOutForm.webFormName` | |
| Produkt-URL | Zeichenfolge | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person-Datensatz


### Metriken

Als Teil dieses Datensatzes werden keine Metrikkomponenten definiert.


### Dimensionen

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Letztes Aktivitätsdatum | Datum-Uhrzeit | `extSourceSystemAudit.lastActivityDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Personen-ID | Zeichenfolge | `personID` | |

{style="table-layout:auto"}

+++


+++  B2B Opportunity-Datensatz

### Metriken

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Erwarteter Umsatz | Double | `expectedRevenue.amount` | Verhalten: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Verhalten: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | Zeichenfolge | `opportunityStage` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `Closed - Booked` |
| Opportunity Stage - Prospect | Zeichenfolge | `opportunityStage` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `Prospect` |
| Opportunity stage - Qualification | Zeichenfolge | `opportunityStage` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `Opportunity Qualification` |
| Opportunity stage - Solution Definition | Zeichenfolge | `opportunityStage` | **[!UICONTROL Ein-/Ausschlusswerte festlegen]**<br/>**[!UICONTROL Groß-/Kleinschreibung]**<br/>Übereinstimmung:**[!UICONTROL  Wenn alle Kriterien erfüllt sind]**<br/>Kriterien: **[!UICONTROL Gleich]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensionen

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Geschlossenes Flag | Boolesch | `isClosed` | |
| Firmen-ID | Zeichenfolge | `opportunityID` | |
| Prognosekategorie | Zeichenfolge | `forecastCategoryName` | |
| Letztes Aktivitätsdatum | Datum-Uhrzeit | `lastActivityDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Lead-Quelle | Zeichenfolge | `leadSource` | |
| Opportunity Name | Zeichenfolge | `opportunityName` | |
| Opportunity status | Zeichenfolge | `opportunityStage` | |
| Won Flag | Boolesch | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B-Campaign-Datensatz

### Metriken

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Kampagnenkosten | Double | `actualCost.amount` | |

{style="table-layout:auto"}


### Dimensionen

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Kampagnen-ID | Zeichenfolge | `campaignID` | |
| Kampagnenname | Zeichenfolge | `campaignName` | |
| Kampagnenstartdatum | Datum-Uhrzeit | `campaignStartDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Kanalname | Zeichenfolge | `channelName` | |
| Übergeordnete Kampagnen-ID | Zeichenfolge | `parentCampaignID` | |

{style="table-layout:auto"}

+++



+++ B2B-Kontodatensatz

### Metriken

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Jahresumsatz | Double | `accountOrganization.annualRevenue.amount` | |
| Anzahl der Beschäftigten | Ganzzahl | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensionen

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Kontokennung | Zeichenfolge | `accountID` | |
| Kontotyp | Zeichenfolge | `accountType` | |
| Stadt | Zeichenfolge | `accountBillingAddress.city` | |
| Land | Zeichenfolge | `accountBillingAddress.country` | |
| Branche | Zeichenfolge | `accountOrganization.industry` | |
| Region | Zeichenfolge | `accountBillingAddress.region` | |
| Quell-ID | Zeichenfolge | `accountKey.sourceID` | |
| Quellinstanz-ID | Zeichenfolge | `accountKey.sourceInstanceID` | |
| Quellschlüssel | Zeichenfolge | `accountKey.sourceKey` | |
| Quellentyp | Zeichenfolge | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign-Mitgliederdatensatz

### Metriken

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Nicht zugestellt | Lang | *_organizationID*`.campaignBounced` | Verhalten: **[!UICONTROL Count values]** |
| Angeklickt | Lang | *_organizationID*`.campaignClicked` | Verhalten: **[!UICONTROL Count values]** |
| Geöffnet | Lang | *_organizationID*`.CampaignOpened` | Verhalten: **[!UICONTROL Count values]** |
| Gesendet | Lang | *_organizationID*`.campaignSent` | Verhalten: **[!UICONTROL Count values]** |
| Abonniert | Lang | *_organizationID*`.campaignSubscribed` | Verhalten: **[!UICONTROL Count values]** |
| Webinar-Registrierungen | Lang | *_organizationID*`.Registrations` | Verhalten: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensionen

| Name der Komponente | Datentyp des Schemas | Pfad des Schemas | Konfiguration |
|---|---|---|---|
| Kampagnen-ID | Zeichenfolge | `campaignID` | |
| Kampagnenmitglieder-ID | Zeichenfolge | `campaignMemberID` | |
| Status des Kampagnenmitglieds | Zeichenfolge | `memberStatus` | |
| Grund des Kampagnenmitglieds | Zeichenfolge | `memberStatusReason` | |
| Erstellungsdatum | Datum-Uhrzeit | `extSourceSystemAudit.createdDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Erstes Antwortdatum | Zeichenfolge | `firstRespondedDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Hat Erfolg erreicht | Boolesch | `hasReachedSuccess` | |
| Hat reagiert | Boolesch | `hasResponded` | |
| Letzter Status | Zeichenfolge | `lastStatus` | |
| Letztes Aktualisierungsdatum | Datum-Uhrzeit | `extSourceSystemAudit.lastUpdatedDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Datum der Mitgliedschaft | Datum-Uhrzeit | `membershipDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Krankenpflege | Zeichenfolge | `nurtureCadence` | |
| Name der Krankenpflege | Zeichenfolge | `nurtureTrackName` | |
| Personen-ID | Zeichenfolge | `personID` | |
| Erreichtes Erfolgsdatum | Datum-Uhrzeit | `reachedSuccessDate` | Datum-Uhrzeit-Format: **[!UICONTROL Tag]** |
| Webinar-Registrierungs-ID | Zeichenfolge | `webinarRegistrationID` | |
| Webinar-Registrierungs-URL | Zeichenfolge | `webinarConfirmationUrl` | |
| isExhausted | Boolesch | isExhausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## Workspace

Nachdem Sie Ihre Komponenten ordnungsgemäß definiert haben, können Sie jetzt spezifische B2B-Visualisierungen in Ihrem Workspace-Projekt erstellen.

Nachfolgend finden Sie ein Beispielprojekt, das auf der oben beschriebenen Verbindungs- und Datenansicht basiert. Weitere Informationen finden Sie in den Beschreibungen für jede Visualisierung.

+++ Beispielprojekt

![Visualisierungen](assets/visualizations.png)

+++
