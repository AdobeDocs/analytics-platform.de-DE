---
title: Integrieren von Adobe Journey Optimizer in Customer Journey Analytics
description: Binden Sie die von Adobe Journey Optimizer generierten Daten ein und analysieren Sie diese mit Analysis Workspace in Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5434b8432608ba5ee49f7062070fa1624af1b46a
workflow-type: tm+mt
source-wordcount: '3028'
ht-degree: 70%

---

# Integrieren von Journey Optimizer in Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/get-started/get-started) hilft Ihnen bei der Bereitstellung von vernetzten, kontextbezogenen und personalisierten Erlebnissen. Dadurch können Ihre Kundinnen und Kunden leichter zum nächsten Schritt ihrer Customer Journey gelangen.

Sie können von Journey Optimizer generierte Daten konfigurieren, um eine erweiterte Analyse in Customer Journey Analytics durchzuführen.  Sie können diese Integration automatisch konfigurieren. Bei Bedarf können Sie zusätzliche manuelle Anpassungen an den Datensätzen, Dimensionen oder Metriken vornehmen, die in Ihrer Verbindung oder in Datenansichten verfügbar sind.

## Automatisches Konfigurieren der Integration von Journey Optimizer

{{release-limited-testing-section}}

Journey Optimizer unterstützt die Verwendung von Customer Journey Analytics als Berichterstellungs-Engine. Weitere Informationen finden Sie unter [Erste Schritte mit der neuen Berichterstellungs-Oberfläche](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/channel-report/report-gs-cja) in der Dokumentation zu Journey Optimizer.

Wenn Sie die Customer Journey Analytics-Berichterstellung für Journey Optimizer aktiviert haben, werden automatisch eine [Verbindung](/help/connections/overview.md) und eine [Datenansicht](/help/data-views/data-views.md) für die spezifische Sandbox erstellt.

### Verbindung

Die Verbindung hat den Namen **[!UICONTROL AJO-fähige Verbindung (*Sandbox-Name*)]** und verfügt über die folgenden vorkonfigurierten Werte für Konfiguration und Datensätze:

| **Verbindungseinstellungen** | Wert |
|---|---| 
| [!UICONTROL Name der Verbindung] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Beschreibung der Verbindung] | [!UICONTROL *Beschreiben Sie hier Ihre Verbindung*] |
| [!UICONTROL Tags] | [!UICONTROL *Tags auswählen*] |


| **Dateneinstellungen** | Wert |
|---|---| 
| [!UICONTROL Rollierendes Datenfenster aktivieren] | Aktiviert.  [!UICONTROL Ausgewählte Anzahl der Monate] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *Name der Sandbox*] (deaktiviert; Sie können diese Einstellung nicht ändern). |
| [!UICONTROL Durchschnittliche Anzahl der täglichen Ereignisse] | weniger als 1 Million (deaktiviert; Sie können diese Einstellung nicht ändern). |


| Datensatzname | Schema | Datensatztyp | Datenquellentyp | Personen-ID | Schlüssel | Übereinstimmender Schlüssel | Neue Daten importieren | Daten aufstocken |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO-Entitäts-Datensatz] | [!UICONTROL Schema des AJO-Entitätseintrags] | [!UICONTROL Suche] | [!UICONTROL Sonstige] | – | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Status „Grün“](assets/../../connections/assets/status-green.svg) Ein | ![Status „Grau“](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Journey-Schrittereignisse] | [!UICONTROL Journey-Schrittereignisschema für Journey-Orchestrierung] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | – | – | ![Status „Grün“](assets/../../connections/assets/status-green.svg) Ein | ![Status Grau](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking] | [!UICONTROL Erlebnisereignisschema beim AJO-E-Mail-Tracking] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary\>)] | – | – | ![Status „Grün“](assets/../../connections/assets/status-green.svg) Ein | ![Status „Grau“](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Ereignisdatensatz mit Feedback zu AJO-Nachrichten] | [!UICONTROL Ereignisschema mit Feedback zu AJO-Nachrichten] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary\>)] | – | – | ![Status „Grün“](assets/../../connections/assets/status-green.svg) Ein | ![Status „Grau“](assets/../../connections/assets/status-gray.svg) Aus |
| [!UICONTROL Erlebnisereignisdatensatz beim AJO-Push-Tracking] | [!UICONTROL Erlebnisereignisschema beim AJO-Push-Tracking] | [!UICONTROL Ereignis] | [!UICONTROL Sonstige] | [!UICONTROL IdentityMap(\&lt;primary\>)] | – | – | ![Status „Grün“](assets/../../connections/assets/status-green.svg) Ein | ![Status „Grau“](assets/../../connections/assets/status-gray.svg) Aus |


### Datenansicht

Die Datenansicht hat den Namen **AJO-Datenansicht aktivieren (*Sandbox-Name*)**.

- Auf der Registerkarte **[!UICONTROL Konfigurieren]** sind die folgenden Werte vorkonfiguriert.

  | Einstellungen | Wert |
  |---|---|
  | [!UICONTROL Verbindung] | AJO-fähige Verbindung (*Sandbox-Name*) |
  | [!UICONTROL Name] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL Externe ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (vom Namen abgeleitet) |
  | [!UICONTROL Beschreibung] | `undefined` |

  {style="table-layout:fixed"}

  | Kompatibilität | Wert |
  |---|---|
  | [!UICONTROL Als Standarddatenansicht in Adobe Journey Optimizer festlegen] | Aktiviert (Standard).<br/><br/>Mit dieser Konfigurationsoption können Sie eine Datenansicht festlegen, die mit Journey Optimizer verwendet werden soll, ohne dass eine manuelle Konfiguration erforderlich ist. Informationen zum Aktivieren dieser Konfigurationsoption (sofern diese nicht bereits standardmäßig aktiviert ist) finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](/help/data-views/create-dataview.md) im Abschnitt [Kompatibilität](/help/data-views/create-dataview.md#compatibility).  <br/><br/>Wenn Sie die Option deaktivieren, werden Sie in einem Dialogfeld dazu aufgefordert, mit der Änderung der Standarddatenansicht fortzufahren. Wenn Sie **[!UICONTROL Weiter]** auswählen, müssen Sie eine andere Datenansicht als Standarddatenansicht auswählen. Wählen Sie **[!UICONTROL Bestätigen]** aus, um Ihre Auswahl zu bestätigen. Wählen Sie **[!UICONTROL Abbrechen]** aus, um die Änderung der Standarddatenansicht abzubrechen.  |

  | Container | Wert |
  |---|---|
  | [!UICONTROL Container-Name für Person] | `Person` |
  | [!UICONTROL Container-Name für Sitzung] | `Session` |
  | [!UICONTROL Container-Name für Ereignis] | `Event` |

  | Kalender | Wert |
  |---|---|
  | [!UICONTROL Zeitzone] | Zeitzone entsprechend Ihrer Position |
  | [!UICONTROL Kalendertyp] | Gregorianisch |
  | [!UICONTROL Erster Monat des Jahres] | Januar  |
  | [!UICONTROL Erster Tag der letzten Woche] | Sonntag |


- Auf der Registerkarte **Komponenten**:
   - Alle Metriken und Dimensionen, an deren Namen [!UICONTROL (AJO)] angehängt wird, werden im Rahmen dieser automatischen Konfiguration automatisch hinzugefügt.
   - Einige der automatisch hinzugefügten Metriken oder Dimensionen basieren auf abgeleiteten Feldern. Diese abgeleiteten Felder werden speziell für diese Integration erstellt. Beispielsweise basiert die Metrik [!UICONTROL Landingpage-Klicks (AJO)] auf dem abgeleiteten Feld [!UICONTROL Landingpage-Klicks].
   - Einige der Metriken oder Dimensionen verfügen über eine zusätzliche Konfiguration. Beispiel: Auf [!UICONTROL Beschwerden wegen Spam (AJO)] wurden die Einstellungen [!UICONTROL Format] und [!UICONTROL Werte einschließen/ausschließen] angewendet.
   - Alle automatisch hinzugefügten Metriken und Dimensionen haben ein Kontext-Label mit dem Namen `:`*`name_of_metric_or_dimension`*. Beispiel: Die Metrik [!UICONTROL Landingpage-Klicks (AJO)] hat das Kontext-Label `:Landing page clicks (AJO)`.

- Auf die Registerkarte **[!UICONTROL Einstellungen]** werden keine spezifischen Konfigurationswerte angewendet.

>[!IMPORTANT]
>
>Die Änderung eines der automatisch konfigurierten Werte für die Verbindungs- und Datenansicht hat Konsequenzen für die Journey Optimizer-Berichterstellung, die auf der automatisch konfigurierten Customer Journey Analytics-Integration basiert und diese verwendet.


## Manuelles Konfigurieren einer Datenansicht für die Verwendung mit Journey Optimizer

In den folgenden Abschnitten wird beschrieben, wie Sie von Journey Optimizer generierte Daten manuell verwenden können, um eine erweiterte Analyse für Customer Journey Analytics durchzuführen. Diese manuelle Konfiguration ist nur erforderlich, wenn die [automatische Konfigurationsoption](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) nicht ausreicht, um Ihre Anforderungen zu erfüllen.

### Senden von Daten aus Journey Optimizer an Experience Platform

Adobe Experience Platform dient als zentrale Datenquelle und Bindeglied zwischen Journey Optimizer und Customer Journey Analytics. Eine schrittweise Anleitung zum Senden von Journey Optimizer-Daten an Experience Platform als Datensatz finden Sie im Journey Optimizer-Benutzerhandbuch unter [Erste Schritte mit Datensätzen](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/data-management/datasets/get-started-datasets).

### Erstellen einer Verbindung

Sobald sich Journey Optimizer-Daten in Adobe Experience Platform befinden, können Sie eine [Verbindung erstellen](/help/connections/create-connection.md), die auf Ihrem Journey Optimizer-Datensatz basiert. Sie können auch Journey Optimizer-Datensätze zu einer bestehenden Verbindung hinzufügen.

Wählen Sie die folgenden Datensätze aus und konfigurieren Sie sie:

| Datensatz | Datensatztyp | Verbindungseinstellungen | Beschreibung |
| --- | --- | --- | --- |
| Ereignisdatensatz mit Feedback zu AJO-Nachrichten | Ereignis | Personen-ID: `IdentityMap` | Enthält Ereignisse bei der Zustellung von Nachrichten, wie z. B. „[!UICONTROL Sendungen]“ und „[!UICONTROL Bounces]“. |
| Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Ereignis | Personen-ID: `IdentityMap` | Enthält E-Mail-Tracking-Ereignisse wie „[!UICONTROL Öffnungen]“, „[!UICONTROL Klicks]“ oder „[!UICONTROL Abmeldungen]“. |
| Ereignisdatensatz zu Erfahrungen beim AJO-Push-Tracking | Ereignis | Personen-ID: `IdentityMap` | Enthält Push-Tracking-Ereignisse wie „[!UICONTROL App-Starts]“. |
| Journey-Schritt-Ereignisse | Ereignis | Personen-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Enthält Ereignisse, die zeigen, welche Profile an den einzelnen Knoten der Journey beteiligt waren. |
| AJO-Entitäts-Datensatz | Suche | Schlüssel: `_id`<br>Passender Schlüssel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Enthält Klassifizierungen, die Journey- und Campaign-Metadaten mit allen Journey Optimizer-Ereignisdaten verknüpfen. |

{style="table-layout:auto"}


### Datenansicht konfigurieren

Sobald eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) erstellen, um die gewünschten Dimensionen und Metriken zu konfigurieren, die in Customer Journey Analytics verfügbar sind.

>[!NOTE]
>
>Die Datenabweichungen zwischen Journey Optimizer und Customer Journey Analytics betragen in der Regel weniger als 1–2 %. Größere Abweichungen sind bei Daten möglich, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche, die den heutigen Tag ausschließen, um Abweichungen aufgrund der Verarbeitungszeit zu vermeiden.


#### Konfigurieren von Dimensionen

Sie können die folgenden Dimensionen in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Dimensionen in Journey Optimizer zu erreichen. Siehe die [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für Details zu den Anpassungsoptionen für Dimensionen.

| Dimension | Beschreibung | Datensätze | Schemaelement | Komponenteneinstellungen |
| --- | --- | --- | --- | --- |
| Fehler bei Aktionsausführung (AJO) | Fehlerbedingung, die die Ausführung der Aktion durch Journey Runtime verhinderte. | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | Komponententyp: Dimension |
| Aktionsbeschriftungen (AJO) | Der kundenseitig generierte Anzeigename des Elements, mit dem die Endbenutzerin bzw. der Endbenutzer interagiert hat. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositionAction.label` | Komponententyp: Dimension |
| Batch-ID (AJO) | GUID, die beim Aufruf jeder neuen Batch-Instanz für eine geplante Journey- oder Kampagnenaktion erstellt wird. Wenn beispielsweise eine geplante Journey- oder Kampagnenaktion um 8.00 Uhr und 10.00 Uhr ausgeführt wird, gibt es zwei separate BatchInstanceIDs. | AJO Push Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | Komponententyp: Dimension |
| Zeitstempel der Batch-Instanz (AJO) | Der Zeitstempel der Batch-Instanz. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | Abgeleitete Felder | Komponententyp: Dimension (abgeleitetes Feld) |
| Kampagnen-ID (AJO) | Die ID der Kampagne. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | Komponententyp: Dimension |
| Kampagnenname (AJO) | Der Name der Kampagne. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | Komponententyp: Dimension |
| Campaign-Versions-ID (AJO) | Die Versions-ID der Kampagne. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | Komponententyp: Dimension |
| Kanal (AJO) | Der Kanal, mit dem diese Daten verknüpft werden sollen. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | Komponententyp: Dimension |
| Korrelations-ID (AJO) | Die Korrelations-ID. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | Komponententyp: Dimension |
| Entscheidungsrichtlinien-ID (AJO) | Die ID der Entscheidungsrichtlinie, die bei der Entscheidung verwendet wird, wenn es darum geht, welche Elemente in diesen Vorschlag aufgenommen werden sollen. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | Abgeleitete Felder | Komponententyp: Dimension (abgeleitetes Feld) |
| E-Mail-Empfänger-Domain (AJO) | Domain der E-Mail-Adresse | AJO Push Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | Komponententyp: Dimension |
| E-Mail-Betreff (AJO) | E-Mail-Betreff, nicht personalisiert | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | Komponententyp: Dimension |
| Ereignis-ID (AJO) | Eine eindeutige Kennung für das Zeitreihenereignis: | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_id` | Komponententyp: Dimension (abgeleitetes Feld) |
| Ausstiegskriteriums-ID (AJO) | Die ID des Ausstiegskriteriums, anhand derer bestimmt wird, ob die Journey beendet werden soll. | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | Komponententyp: Dimension |
| Name des Ausstiegskriteriums (AJO) | Name der Ausstiegskriterien. | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | Komponententyp: Dimension |
| Experiment-ID (AJO) | Die ID des Experiments. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Komponententyp: Dimension |
| Experimentname (AJO) | Der Name des Experiments. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | Komponententyp: Dimension Context-Beschriftungen: Experimentierexperiment |
| Fehler beim Abrufen (AJO) | Fehlerbedingung, die die Ausführung des Abrufs durch Journey Runtime verhinderte. | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | Komponententyp: Dimension |
| Ist für Sendezeit optimiert (AJO) | Ist die Nachrichtenausführung SendTimeOptimized | AJO Push Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | Komponententyp: Dimension |
| Ist Test-Journey (AJO) | Ist das Ereignis Teil der Ausführung einer Test-Journey | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | Komponententyp: Dimension |
| Ist Testnachricht (AJO) | Wird Nachricht als Testausführung gesendet | AJO Push Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | Komponententyp: Dimension |
| Element-ID (AJO) | Die ID des Elements. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositions.items.id` | Komponententyp: Dimension |
| Elementname (AJO) | Der Name des Elements | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositions.items.name` | Komponententyp: Dimension |
| Journey-Action-ID | Journey Action ID, für die MessageExecution ausgelöst wird. | AJO Push Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | Komponententyp: Dimension |
| Knotenname der Journey-Aktion (AJO) | Der Knotenname der Journey-Aktion. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz, AJO Entity Datensatz | Abgeleitete Felder | Komponententyp: Dimension (abgeleitetes Feld) |
| Knotenname des Journey-Ereignisses (AJO) | Dieser Wert wird immer dann festgelegt, wenn in einer Journey ein Segment oder ein externes Ereignis auftritt. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz, AJO Entity Datensatz | Abgeleitete Felder | Komponententyp: Dimension (abgeleitetes Feld) |
| Journey-ID (AJO) | Die ID der Journey. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | Komponententyp: Dimension |
| Journey-Name (AJO) | Der Name der Journey. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | Komponententyp: Dimension |
| Name und Version der Journey (AJO) | Der Name und die Version der Journey. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | Komponententyp: Dimension |
| Journey-Version-ID (AJO) | Die Versions-ID der Journey. | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | Komponententyp: Dimension |
| Landingpage-ID (AJO) | Eindeutige Kennung für die Landingpage. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | Komponententyp: Dimension |
| Landingpage-Quelle (AJO) | Die Quelle der Landingpage. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Abgeleitete Felder | Komponententyp: Dimension (abgeleitetes Feld) |
| Link-URL (AJO) | Die von den Benutzenden angeklickte URL. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Komponententyp: Dimension |

{style="table-layout:auto"}

#### Konfigurieren von Metriken

Sie können die folgenden Metriken in einer Datenansicht erstellen, um eine ungefähre Übereinstimmung mit ähnlichen Metriken in Journey Optimizer zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für weitere Informationen zu den Anpassungsoptionen von Metriken.

| Metrik | Beschreibung | Datensätze | Schemaelement | Komponenteneinstellungen |
| --- | --- | --- | --- | --- |
| App-Installationen (AJO) | Anzahl der App-Installationen | Ereignisdatensatz zu Erfahrungen beim AJO-Push-Tracking | `application.installs.value` | Komponententyp: Metrik |
| App-Starts (AJO) | Häufigkeit, mit der die mobile App gestartet wird | Ereignisdatensatz zu Erfahrungen beim AJO-Push-Tracking | `application.launches.value` | Komponententyp: Metrik |
| Bounces für ausgehende Kanäle (AJO) | Gesamtzahl der über ausgehende Kanäle hinweg nicht erfolgreich zugestellten Nachrichten | Ereignisdatensatz mit Feedback zu AJO-Nachrichten | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik |
| Klicks (AJO) | Gesamtanzahl an Klicks über alle Kanäle hinweg | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Email Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Anzahl der Fallback-Angebote (AJO) | Anzahl der Fallback-Angebote. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | Komponententyp: Metrik |
| Anzahl der Angebote (AJO) | Anzahl der Angebote. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | ` _experience.decisioning.`<br/>`propositions.items.id` | Komponententyp: Metrik |
| Deduplizierungsmetrik (AJO) | Deduplizierungsmetrik | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_id` | Komponententyp: Metrik |
| Zugestellt (AJO) | Gesamtzahl der zugestellten Nachrichten. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Verworfen (AJO) | Zählt jedes Mal, wenn die In-App-Nachricht vom Adobe SDK geschlossen wird, unabhängig davon, welche Aktion die Endbenutzerin bzw. der Endbenutzer zum Schließen auswählt. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Komponententyp: Metrik |
| Anzeigen (AJO) | Hier werden die Anzeigen von AJO-Nachrichten gezählt. Dazu gehören das Öffnen von E-Mails, Web-Anzeigen und In-App-Anzeigen. Mobile Plattformen melden keine Anzeigen von SMS- und Push-Nachrichten, weshalb sie nicht mitgezählt werden. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Email Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| E-Mail-Öffnungen (AJO) | Gesamtzahl der E-Mail-Öffnungen | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponententyp: Metrik |
| Eingehende Klicks (AJO) | Gesamtzahl an Klicks über eingehende Kanäle | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositionEventType.interact` | Komponententyp: Metrik |
| Eingehende Abweisungen (AJO) | Gesamtzahl der Abweisungen über eingehende Kanäle | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Komponententyp: Metrik |
| Eingehende Impressionen (AJO) | Gesamtzahl der Impressionen über eingehende Kanäle | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponententyp: Metrik |
| Journey-Ende (AJO) | True , wenn der aktuelle Schritt zum Beenden einer Instanz des Journey führte. Dass der letzte Schritt in einer Journey für ein bestimmtes Profil erfolgreich ausgeführt wurde. | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Komponententyp: Metrik |
| Journey-Eintritte (AJO) | True, wenn das Schrittereignis ein Journey-Eintrittsereignis für ein Profil war. | Journey-Schritt-Ereignisse | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Journey-Austritte (AJO) | True , wenn der aktuelle Schritt zum Beenden einer Instanz des Journey führte. Dies ist der letzte Schritt in einer Journey für ein bestimmtes Profil, der erfolgreich ausgeführt wurde. | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Komponententyp: Metrik |
| Journey-Fehler (AJO) | Gibt den aktuellen Status des Schritts an, der abgeschlossen ist. Mögliche Werte: `Transitions` (Der nächste Schritt erfolgt bei einer Ereignisübergabe), `EndStep` (Der letzte Schritt in dieser Journey-Instanz wurde ausgeführt), `Error` (bei diesem Schritt ist eine Fehlerbedingung aufgetreten, die die aktuelle Journey-Instanz beendet hat), `TimedOut` (Der aktuelle Schritt wurde aufgrund einer Zeitüberschreitung beim Abrufen oder bei einer Aktion beendet). | Journey-Schritt-Ereignisse | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | Komponententyp: Metrik |
| Landingpage-Klicks (AJO) | Gesamtanzahl an Klicks auf die Landingpage. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Landingpage-Konversionen (AJO) | Gesamtanzahl der Konversionen auf der Landingpage. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponententyp: Metrik |
| Ansichten der Landingpage (AJO) | Gesamtzahl der Ansichten auf der Landingpage. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponententyp: Metrik |
| Knoteneintritte (AJO) | True, wenn das Schrittereignis ein Knoteneintrittsereignis für ein Profil war. | Journey-Schritt-Ereignisse | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Ausgehende Klicks (AJO) | Gesamtanzahl an Klicks über ausgehende Kanäle | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponententyp: Metrik |
| Ausgehende Fehler (AJO) | Gesamtanzahl der Nachrichten mit Fehlern in allen ausgehenden Kanälen | Ereignisdatensatz mit Feedback zu AJO-Nachrichten | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik |
| Ausgehende Ausschlüsse (AJO) | Gesamtanzahl der über ausgehende Kanäle hinweg ausgeschlossenen Ereignisse | Ereignisdatensatz mit Feedback zu AJO-Nachrichten | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik |
| Ausgehende Sendungen (AJO) | Gesamtzahl der über ausgehende Kanäle gesendeten Nachrichten | Ereignisdatensatz mit Feedback zu AJO-Nachrichten | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Komponententyp: Metrik |
| Benutzerdefinierte Push-Aktionen (AJO) | Gesamtanzahl an benutzerdefinierten Aktionen in einer Push-Interaktion. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `eventType` | Komponententyp: Metrik |
| Push-Interaktionen (AJO) | Häufigkeit, mit der eine mobile App aufgrund einer direkten Push-Nachrichten-Interaktion gestartet wird | Ereignisdatensatz zu Erfahrungen beim AJO-Push-Tracking | `application.launches.value` | Komponententyp: Metrik |
| Sendevorgänge (AJO) | Gesamtzahl der über alle Kanäle gesendeten Nachrichten | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Eingehende SMS-Nachrichten (AJO) | SMS-eingehende Antwort. Beispielsweise Stopp, Start, Abonnement usw. | AJO Push Tracking Experience Event Datensatz, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Komponententyp: Metrik |
| Spam-Beschwerde (AJO) | Gesamtzahl der Beschwerden wegen Spam | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponententyp: Metrik |
| Hinzufügungen zur Abonnement-Liste (AJO) | Gesamtzahl aller Hinzufügungen zur Abonnement-Liste. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Entfernungen von Abonnement-Listen (AJO) | Gesamtzahl der Entfernungen aus der Abonnement-Liste. | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| An Zielgruppe gerichtet (AJO) | Hier wird gezählt, wie oft ein Vorschlag an eine Person gerichtet wurde. Dies ist die Anzahl der Male, in denen ein Vorschlag für die Anzeige bei einer Person in Betracht gezogen wurde. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | Abgeleitete Felder | Komponententyp: Metrik (abgeleitetes Feld) |
| Ausgelöst (AJO) | Der Vorschlag wurde zur Anzeige durch das Adobe SDK ausgewählt. Andere Faktoren können verhindern, dass er tatsächlich angezeigt wird. | AJO Push Tracking Experience Event Datensatz, Journey Step Events, AJO Message Feedback Event Datensatz, AJO Email Tracking Experience Event Datensatz | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponententyp: Metrik |
| Unique Visitors im Experiment (AJO) | Die Unique Visitors im Experiment | AJO-Entitäts-Datensatz | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Komponententyp: Metrik |
| Abonnementkündigungen (AJO) | Gesamtanzahl der Abmeldungen | Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Komponententyp: Metrik |

{style="table-layout:auto"}
