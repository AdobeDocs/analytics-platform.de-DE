---
title: Integrieren von Adobe Journey Optimizer in Customer Journey Analytics
description: Binden Sie die von Adobe Journey Optimizer generierten Daten ein und analysieren Sie diese mit Analysis Workspace in Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 529dd2ed2af60f8b417a5bf7d728a201dad70218
workflow-type: tm+mt
source-wordcount: '1547'
ht-degree: 52%

---

# Integrieren von Journey Optimizer mit Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/get-started) hilft Ihnen bei der Bereitstellung von vernetzten, kontextbezogenen und personalisierten Erlebnissen. Dadurch können Ihre Kundinnen und Kunden leichter zum nächsten Schritt ihrer Customer Journey gelangen.

Sie können von Journey Optimizer generierte Daten konfigurieren, um eine erweiterte Analyse in Customer Journey Analytics durchzuführen. Sie können diese Integration automatisch konfigurieren. Bei Bedarf können Sie zusätzliche manuelle Anpassungen an den Datensätzen, Dimensionen oder Metriken vornehmen, die in Ihrer Verbindung oder in Datenansichten verfügbar sind.

## Journey Optimizer-Integration automatisch konfigurieren

{{release-limited-testing-section}}

Journey Optimizer unterstützt die Verwendung von Customer Journey Analytics als Reporting-Engine. Siehe [Erste Schritte mit der neuen Reporting-Oberfläche](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja) in der Journey Optimizer-Dokumentation.

Wenn Sie die Customer Journey Analytics-Berichterstellung für Journey Optimizer aktiviert haben, wird automatisch ein [connection](/help/connections/overview.md) und [Datenansicht](/help/data-views/data-views.md) werden für die spezifische Sandbox erstellt.

### Verbindung

Die Verbindung hat den Namen **[!UICONTROL AJO-aktivierte Verbindung (*Sandbox-Name*)]** und verfügt über die folgenden vordefinierten Werte für Konfiguration und Datensätze:

| **Verbindungseinstellungen** | Wert |
|---|---| 
| [!UICONTROL Name der Verbindung] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Beschreibung der Verbindung] | [!UICONTROL *Ihre Verbindung hier beschreiben*] |
| [!UICONTROL Tags] | [!UICONTROL *Tags auswählen*] |


| **Dateneinstellungen** | Wert |
|---|---| 
| [!UICONTROL Rollierendes Datenfenster aktivieren] | Aktiviert. [!UICONTROL Ausgewählte Anzahl von Monaten] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *Name der Sandbox*] (deaktiviert; Sie können diese Einstellung nicht ändern). |
| [!UICONTROL Durchschnittliche Anzahl der täglichen Ereignisse] | weniger als 1 Million (deaktiviert; Sie können diese Einstellung nicht ändern). |


| Datensatzname | Schema | Typ des Datensatzes | Datenquellentyp | Personen-ID | Schlüssel | Übereinstimmender Schlüssel | Neue Daten importieren | Daten aufstocken |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO-Entitätsdatensatz] | [!UICONTROL AJO-Entitätsdatensatz-Schema] | [!UICONTROL Suche] | [!UICONTROL Sonstige] | – | ` _id` | `_experience.decisioning.`<br/>`propositions.scopeDetails.`<br/>`correlationID` | ![Status Grün](assets/../../connections/assets/status-green.svg) on | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Journey-Schrittereignisse] | [!UICONTROL Journey Schritt-Ereignisschema für Journey Orchestration] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL  IdentityMap(\&lt;primary>)] | – | – | ![Status Grün](assets/../../connections/assets/status-green.svg) on | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Datensatz zum AJO-E-Mail-Tracking-Erlebnis] | [!UICONTROL AJO E-Mail-Tracking-Erlebnisereignisschema] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary>)] | – | – | ![Status Grün](assets/../../connections/assets/status-green.svg) on | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Datensatz zum AJO-E-Mail-Tracking-Erlebnis] | [!UICONTROL AJO E-Mail-Tracking-Erlebnisereignisschema] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary>)] | – | – | ![Status Grün](assets/../../connections/assets/status-green.svg) on | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL AJO Message Feedback-Ereignisdatensatz] | [!UICONTROL AJO Message Feedback-Ereignisschema] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary>)] | – | – | ![Status Grün](assets/../../connections/assets/status-green.svg) on | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL AJO-Datensatz zum Push-Tracking-Erlebnis] | [!UICONTROL AJO-Ereignisschema für Push-Tracking] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary>)] | – | – | ![Status Grün](assets/../../connections/assets/status-green.svg) on | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |


### Datenansicht

Die Datenansicht hat den Namen **AJO Datenansicht aktivieren (*Sandbox-Name*)**.

- Im **[!UICONTROL Konfigurieren]** -Tab, sind die folgenden Werte vorkonfiguriert.

  | Einstellungen  | Wert |
  |---|---|
  | [!UICONTROL Verbindung] | AJO-aktivierte Verbindung (*Sandbox-Name*) |
  | [!UICONTROL Name] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL Externe ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (aus dem Namen abgeleitet) |
  | [!UICONTROL Beschreibung] | `undefined` |

  {style="table-layout:fixed"}

  | Kompatibilität | Wert |
  |---|---|
  | [!UICONTROL Als Standarddatenansicht in Adobe Journey Optimizer festlegen] | Aktiviert (Standard).<br/><br/>Mit dieser Konfigurationsoption können Sie eine Datenansicht festlegen, die mit Journey Optimizer verwendet werden soll, ohne dass eine manuelle Konfiguration erforderlich ist. Informationen zum Aktivieren dieser Konfigurationsoption (sofern diese nicht standardmäßig aktiviert ist) finden Sie in der [Kompatibilität](/help/data-views/create-dataview.md#compatibility) Abschnitt in [Datenansicht erstellen oder bearbeiten](/help/data-views/create-dataview.md). <br/><br/>Wenn Sie die Option deaktivieren, werden Sie in einem Dialogfeld aufgefordert, die Standarddatenansicht weiter zu ändern. Wenn Sie **[!UICONTROL Weiter]** müssen Sie eine andere Datenansicht als Standarddatenansicht auswählen. Auswählen **[!UICONTROL Bestätigen]** um Ihre Auswahl zu bestätigen. Auswählen **[!UICONTROL Abbrechen]** , um die Änderung der Standarddatenansicht abzubrechen. |

  | Behälter | Wert |
  |---|---|
  | [!UICONTROL Container-Name für Person] | `Person` |
  | [!UICONTROL Container-Name für Sitzung] | `Session` |
  | [!UICONTROL Container-Name für Ereignis] | `Event` |

  | Kalender | Wert |
  |---|---|
  | [!UICONTROL Zeitzone] | Zeitzone entsprechend Ihrer Position |
  | [!UICONTROL Kalendertyp] | Gregorianisch |
  | [!UICONTROL Erster Monat des Jahres] | Januar  |
  | [!UICONTROL Erster Wochentag] | Sonntag |


- Im **Komponenten** tab:
   - Alle Metriken und Dimensionen mit **[!UICONTROL (AJO)]** an ihren Namen angehängt werden, werden im Rahmen dieser automatischen Konfiguration automatisch hinzugefügt.
   - Einige der automatisch hinzugefügten Metriken oder Dimensionen basieren auf abgeleiteten Feldern. Diese abgeleiteten Felder werden speziell für diese Integration erstellt. Beispielsweise basiert die Metrik Landingpage-Klicks (AJO) auf dem abgeleiteten Feld Landingpage-Klicks .
   - Einige Metriken oder Dimensionen verfügen über eine zusätzliche Konfiguration. Beispielsweise sind die Einstellungen &quot;Format&quot;und &quot;Include Exclude Values&quot;auf die Funktion &quot;Spam Complaint&quot;(AJO) angewendet.
   - Alle automatisch hinzugefügten Metriken und Dimensionen haben eine Kontextbeschriftung mit dem Namen **[!UICONTROL :*name_of_metric_or_dimension *]**. Beispiel: die[!UICONTROL Landingpage-Klicks (AJO)] -Metrik hat die Kontextbezeichnung [!UICONTROL :Landingpage-Klicks (AJO)].

- Im **[!UICONTROL Einstellungen]** Registerkarte, es werden keine spezifischen Konfigurationswerte angewendet

>[!IMPORTANT]
>
>Die Änderung eines der automatisch konfigurierten Werte für die Verbindungs- und Datenansicht hat Konsequenzen für die Journey Optimizer-Berichterstellung, die auf der automatisch konfigurierten Customer Journey Analytics-Integration basiert und diese verwendet.


## Manuelles Konfigurieren einer Datenansicht für die Verwendung mit Journey Optimizer

In den folgenden Abschnitten wird beschrieben, wie Sie manuell von Journey Optimizer generierte Daten verwenden können, um eine erweiterte Customer Journey Analytics-Analyse durchzuführen. Dies ist nur erforderlich, wenn die Variable [automatische Konfigurationsoption](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) ist nicht ausreichend für Ihre Bedürfnisse.

### Daten von Journey Optimizer an Experience Platform senden

Adobe Experience Platform dient als zentrale Datenquelle und Bindeglied zwischen Journey Optimizer und Customer Journey Analytics. Siehe [Erste Schritte mit Datensätzen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) Anweisungen zum Senden von Journey Optimizer-Daten an Experience Platform als Datensatz finden Sie im Journey Optimizer-Benutzerhandbuch .

### Erstellen einer Verbindung in Customer Journey Analytics

Sobald sich Journey Optimizer-Daten in Adobe Experience Platform befinden, können Sie eine [Verbindung erstellen](/help/connections/create-connection.md), die auf Ihrem Journey Optimizer-Datensatz basiert. Sie können auch Journey Optimizer-Datensätze zu einer bestehenden Verbindung hinzufügen.

Wählen Sie die folgenden Datensätze aus und konfigurieren Sie sie:

| Datensatz | Typ des Datensatzes | Verbindungseinstellungen | Beschreibung |
| --- | --- | --- | --- |
| Ereignisdatensatz mit Feedback zu AJO-Nachrichten | Ereignis | Personen-ID: `IdentityMap` | Enthält Ereignisse bei der Zustellung von Nachrichten, wie z. B. „[!UICONTROL Sendungen]“ und „[!UICONTROL Bounces]“. |
| Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Ereignis | Personen-ID: `IdentityMap` | Enthält E-Mail-Tracking-Ereignisse wie „[!UICONTROL Öffnungen]“, „[!UICONTROL Klicks]“ oder „[!UICONTROL Abmeldungen]“. |
| Ereignisdatensatz zu Erfahrungen beim AJO-Push-Tracking | Ereignis | Personen-ID: `IdentityMap` | Enthält Push-Tracking-Ereignisse wie „[!UICONTROL App-Starts]“. |
| Journey-Schritt-Ereignisse | Ereignis | Personen-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Enthält Ereignisse, die zeigen, welche Profile an den einzelnen Knoten der Journey beteiligt waren. |
| AJO-Entitäts-Datensatz | Suche | Schlüssel: `_id`<br>Passender Schlüssel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Enthält Classifications, die Journey- und Campaign-Metadaten mit allen Journey Optimizer-Ereignisdaten verknüpfen. |

{style="table-layout:auto"}


### Konfigurieren der Datenansicht für Journey Optimizer-Dimensionen und -Metriken

Sobald eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) erstellen, um die gewünschten Dimensionen und Metriken zu konfigurieren, die in Customer Journey Analytics verfügbar sind.

>[!NOTE]
>
>Datendiskrepanzen zwischen Journey Optimizer und Customer Journey Analytics liegen in der Regel unter 1-2 %. Größere Abweichungen sind bei Daten möglich, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche, die den heutigen Tag ausschließen, um Abweichungen aufgrund der Verarbeitungszeit zu vermeiden.


#### Konfigurieren der Dimensionen in der Datenansicht

Sie können die folgenden Dimensionen in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Dimensionen in Journey Optimizer zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichtsmanager für weitere Informationen zu den Dimensionsanpassungsoptionen.

| Dimension | Schemaelement | Einstellungen der Komponente |
| --- | --- | --- |
| Name der Journey | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Komponententyp: Dimension |
| Name und Version der Journey | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Komponententyp: Dimension |
| Journey-Knotenname | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | Komponententyp: Dimension |
| Journey-Knotentyp | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Komponententyp: Dimension |
| Kampagnenname | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Komponententyp: Dimension |
| Kanal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Komponententyp: Dimension |
| Push-Titel | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Komponententyp: Dimension |
| E-Mail-Betreff | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Komponententyp: Dimension |
| Link-Bezeichnung | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Komponententyp: Dimension |
| Experimentname | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Komponententyp: Dimension<br>Kontextkennzeichnungen: Experimentierexperiment |
| Abwandlungsname | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Komponententyp: Dimension<br>Kontextkennzeichnungen: Experimentvariante |
| Grund für fehlgeschlagenen E-Mail-Versand | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Komponententyp: Dimension |
| Grund für Ausschluss vom E-Mail-Versand | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Komponententyp: Dimension |
| Elementbezeichnung | `_experience.decisioning.propositionAction.label` | Komponententyp: Dimension |

{style="table-layout:auto"}

#### Konfigurieren von Metriken in der Datenansicht

Sie können die folgenden Metriken in einer Datenansicht erstellen, um eine ungefähre Übereinstimmung mit ähnlichen Metriken in Journey Optimizer zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für weitere Informationen zu den Anpassungsoptionen von Metriken.

| Metrik | Beschreibung | Schemaelement | Einstellungen der Komponente |
| --- | --- | --- | --- |
| Bounces | Die Anzahl der Bounce-Nachrichten, einschließlich der unmittelbaren Bounces und Bounces nach dem Versand. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Wenn ein Kriterium erfüllt ist<br>Gleich: `bounce`, Gleich: `denylist` |
| Bounces nach dem Versand | Einige E-Mail-Dienste melden zugestellte E-Mails und schicken sie dann später zurück. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `async` |
| E-Mail-Klicks | Anzahl der Klicks in Nachrichten. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `click` |
| E-Mail-Öffnungen | Anzahl geöffneter Nachrichten. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `open` |
| Fehler | Die Anzahl der fehlerhaften Nachrichten. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `error` |
| Ausgeschlossen sind | Die Anzahl der ausgeschlossenen Nachrichten. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `exclude` |
| Sendungen | Die Anzahl der Nachrichten, die von E-Mail-Anbietern akzeptiert wurden. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `sent` |
| Spam-Beschwerden | Anzahl der Beschwerden wegen Spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `spam_complaint` |
| Abonnementkündigungen | Anzahl der Abonnementkündigungen. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `unsubscribe` |
| Edge-Sendungen | Die Häufigkeit, mit der das Edge-Netzwerk eine Nachricht entweder an das Web- oder Mobile-SDK sendet | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.send` | |
| Eingehende Anzeigen | Die Häufigkeit, mit der den Benutzenden eine Web- oder In-App-Nachricht angezeigt wird | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.display` | |
| Eingehende Klicks | Die Anzahl der Klicks auf Web- oder In-App-Nachrichten | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.interact` | |
| In-App-Trigger | Die Häufigkeit, mit der die Decisioning Engine die Nachricht angezeigt hat. Das Mobile SDK kann die Entscheidung überschreiben und so die Anzahl der tatsächlichen Anzeigen reduzieren. | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.trigger` | |
| In-App-Abweisungen | Die Häufigkeit, mit der eine In-App-Nachricht vom SDK aus der Benutzeroberfläche entfernt wird | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Konfigurieren von berechneten Metriken in Analysis Workspace

Nachdem Sie die gewünschten Dimensionen und Metriken für den Journey Optimizer-Datensatz konfiguriert haben, können Sie auch [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) für weitere Einblicke in diese Daten konfigurieren. Diese berechneten Metriken basieren auf den oben genannten Metriken, die im Datenansichts-Manager erstellt wurden.

| Berechnete Metrik | Beschreibung | Formel |
| --- | --- | --- |
| Gesendete Nachrichten | Die Gesamtzahl der gesendeten Nachrichten. Enthält erfolgreiche oder fehlgeschlagene Nachrichten. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Zugestellte Nachrichten | Die Anzahl der an Kundinnen und Kunden gesendeten E-Mails. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
