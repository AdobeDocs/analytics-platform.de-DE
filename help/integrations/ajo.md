---
title: Integrieren von Adobe Journey Optimizer in Customer Journey Analytics
description: Binden Sie die von Adobe Journey Optimizer generierten Daten ein und analysieren Sie diese mit Analysis Workspace in Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 6e1db2351aa9fcc4682b892334430c1896cee914
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 83%

---

# Integrieren von Adobe Journey Optimizer in Adobe Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=de) hilft Ihnen bei der Bereitstellung von vernetzten, kontextbezogenen und personalisierten Erlebnissen. Dadurch können Ihre Kundinnen und Kunden leichter zum nächsten Schritt ihrer Customer Journey gelangen.

Sie können von Journey Optimizer generierte Daten importieren, um eine erweiterte Analyse in Customer Journey Analytics durchzuführen. Sie können dies automatisch tun. Bei Bedarf können Sie zusätzliche manuelle Anpassungen an den Datensätzen, Dimensionen oder Metriken vornehmen, die in Ihren Datenansichten verfügbar sind, die Sie für Adobe Journey Optimizer und Customer Journey Analytics verwenden.

## Automatische Konfiguration einer Customer Journey Analytics-Datenansicht für die Verwendung mit Journey Optimizer

Mit einer Konfigurationsoption unter Customer Journey Analytics können Sie eine Customer Journey Analytics-Datenansicht festlegen, die mit Journey Optimizer verwendet werden kann, ohne dass eine manuelle Konfiguration erforderlich ist. <p>Informationen zum Aktivieren dieser Konfigurationsoption finden Sie unter [Kompatibilität](/help/data-views/create-dataview.md#compatibility) Abschnitt in [Datenansicht erstellen oder bearbeiten](/help/data-views/create-dataview.md).

## Manuelles Konfigurieren einer Customer Journey Analytics-Datenansicht für die Verwendung mit Journey Optimizer

In den folgenden Abschnitten wird beschrieben, wie Sie von Journey Optimizer generierte Daten manuell importieren, um eine erweiterte Customer Journey Analytics-Analyse durchzuführen. Dies ist nur erforderlich, wenn die Variable [automatische Konfigurationsoption](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) ist nicht ausreichend für Ihre Bedürfnisse.

### Senden von Daten aus Journey Optimizer an Adobe Experience Platform

Adobe Experience Platform dient als zentrale Datenquelle und Bindeglied zwischen Journey Optimizer und Customer Journey Analytics. Eine schrittweise Anleitung zum Senden von Journey Optimizer-Daten an Platform als Datensatz finden Sie unter [Erste Schritte mit Datensätzen](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=de) im Journey Optimizer-Benutzerhandbuch.

### Erstellen einer Verbindung in Customer Journey Analytics

Sobald sich Journey Optimizer-Daten in Adobe Experience Platform befinden, können Sie eine [Verbindung erstellen](/help/connections/create-connection.md), die auf Ihrem Journey Optimizer-Datensatz basiert. Sie können auch Journey Optimizer-Datensätze zu einer bestehenden Verbindung hinzufügen.

Wählen Sie die folgenden Datensätze aus und konfigurieren Sie sie:

| Datensatz | Typ des Datensatzes | Verbindungseinstellungen | Beschreibung |
| --- | --- | --- | --- |
| Ereignisdatensatz mit Feedback zu AJO-Nachrichten | Ereignis | Personen-ID: `IdentityMap` | Enthält Ereignisse bei der Zustellung von Nachrichten, wie z. B. „[!UICONTROL Sendungen]“ und „[!UICONTROL Bounces]“. |
| Ereignisdatensatz zu Erfahrungen beim AJO-E-Mail-Tracking | Ereignis | Personen-ID: `IdentityMap` | Enthält E-Mail-Tracking-Ereignisse wie „[!UICONTROL Öffnungen]“, „[!UICONTROL Klicks]“ oder „[!UICONTROL Abmeldungen]“. |
| Ereignisdatensatz zu Erfahrungen beim AJO-Push-Tracking | Ereignis | Personen-ID: `IdentityMap` | Enthält Push-Tracking-Ereignisse wie „[!UICONTROL App-Starts]“. |
| Journey-Schritt-Ereignisse | Ereignis | Personen-ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Enthält Ereignisse, die zeigen, welche Profile an den einzelnen Knoten der Journey beteiligt waren. |
| AJO-Entitäts-Datensatz | Suche | Schlüssel: `_id`<br>Passender Schlüssel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Enthält Klassifizierungen, die Journey- und Campaign-Metadaten mit allen Adobe Journey Optimizer-Ereignisdaten verknüpfen. |

{style="table-layout:auto"}


### Konfigurieren der Datenansicht für Journey Optimizer-Dimensionen und -Metriken

Sobald eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) erstellen, um die gewünschten Dimensionen und Metriken zu konfigurieren, die in Customer Journey Analytics verfügbar sind.

>[!NOTE]
>
>Die Datenabweichungen zwischen Adobe Journey Optimizer und Customer Journey Analytics betragen in der Regel weniger als 1–2 %. Größere Abweichungen sind bei Daten möglich, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche, die den heutigen Tag ausschließen, um Abweichungen aufgrund der Verarbeitungszeit zu vermeiden.


#### Konfigurieren der Dimensionen in der Datenansicht

Sie können die folgenden Dimensionen in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Dimensionen in Journey Optimizer zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für Details zu den Anpassungsoptionen für Dimensionen.

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
| In-App-Trigger | Die Häufigkeit, mit der die Decisioning Engine die Nachricht angezeigt hat. Das Mobile SDK kann die Entscheidung überschreiben, wodurch die Anzahl der tatsächlichen Anzeigen reduziert wird. | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.trigger` | |
| In-App-Abweisungen | Die Häufigkeit, mit der eine In-App-Nachricht vom SDK aus der Benutzeroberfläche entfernt wird | Verwenden des Schema-Zeichenfolgenelements `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Konfigurieren von berechneten Metriken in Analysis Workspace

Nachdem Sie die gewünschten Dimensionen und Metriken für den Journey Optimizer-Datensatz konfiguriert haben, können Sie auch [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) für weitere Einblicke in diese Daten konfigurieren. Diese berechneten Metriken basieren auf den oben genannten Metriken, die im Datenansichts-Manager erstellt wurden.

| Berechnete Metrik | Beschreibung | Formel |
| --- | --- | --- |
| Gesendete Nachrichten | Die Gesamtzahl der gesendeten Nachrichten. Enthält erfolgreiche oder fehlgeschlagene Nachrichten. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Zugestellte Nachrichten | Die Anzahl der an Kundinnen und Kunden gesendeten E-Mails. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
