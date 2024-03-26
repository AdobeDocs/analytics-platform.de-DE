---
title: Integrieren von Adobe Journey Optimizer in das Entscheidungs-Management in Adobe Customer Journey Analytics
description: Binden Sie Daten ein, die vom Entscheidungs-Management in Adobe Journey Optimizer generiert wurden, und analysieren Sie sie mithilfe von Analysis Workspace in Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '710'
ht-degree: 100%

---

# Integrieren von Entscheidungs-Management in Adobe Customer Journey Analytics


Das [Entscheidungs-Management](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=de) in Adobe Journey Optimizer erleichtert die Personalisierung durch eine zentrale Bibliothek mit Marketing-Angeboten und eine Entscheidungs-Engine. Dabei werden Regeln und Einschränkungen auf die von Adobe Experience Platform erstellten, umfangreichen Echtzeitprofile angewendet, sodass Sie Ihren Kundinnen und Kunden zum richtigen Zeitpunkt das richtige Angebot senden können.

Das Entscheidungs-Management ist Teil von Adobe Journey Optimizer und ist darin integriert. Dank seiner umfassenden [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=de)-Unterstützung kann es auch unabhängig von Journeys und Kampagnen verwendet werden, die in Adobe Journey Optimizer definiert sind.

Gehen Sie wie folgt vor, um vom Entscheidungs-Management generierte Daten zu importieren und eine erweiterte Analyse in Customer Journey Analytics durchzuführen:

## Senden von Daten aus dem Entscheidungs-Management an Adobe Experience Platform

Adobe Experience Platform dient als zentrale Datenquelle und Bindeglied zwischen Entscheidungs-Management und Customer Journey Analytics. Daten aus dem Entscheidungs-Management werden **automatisch** in Experience Platform oder als Teil von **explizit gesendeten Erlebnisereignisse** (zum Beispiel Impressionen oder Klicks) erfasst. Weitere Informationen finden Sie unter [Erste Schritte mit der Datenerfassung](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=de).

## Erstellen einer Verbindung

Sobald sich Entscheidungs-Management-Daten in Adobe Experience Platform befinden, können Sie eine [Verbindung erstellen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de), die auf Ihren Entscheidungs-Management-Datensätzen basiert. Alternativ können Sie einer bestehenden Verbindung Entscheidungs-Management-Datensätze hinzufügen.

Wählen Sie die folgenden Datensätze aus und konfigurieren Sie sie:

| Datensatz | Typ des Datensatzes | Verbindungseinstellungen | Beschreibung |
| --- | --- | --- | --- |
| ODE DecisonEvents – _Sandbox_-Entscheidungsfindung | Ereignis | Personen-ID: `IdentityMap` | Enthält automatisch generierte Daten für Entscheidungsereignisse im Entscheidungs-Management. _Sandbox_ bezieht sich auf den spezifischen Sandbox-Namen. |
| Ereignisdatensatz mit Nachrichten-Feedback in Adobe Journey Optimizer | Ereignis | Personen-ID:`IdentityMap` | Enthält Ereignisse bei der Zustellung von Nachrichten. |
| Erlebnisereignis-Datensatz des E-Mail-Trackings in Adobe Journey Optimizer | Ereignis | Personen-ID: `IdentityMap` | Enthält E-Mail-Tracking-Ereignisse. |
| Erlebnisereignis-Datensatz des Push-Trackings in Adobe Journey Optimizer | Ereignis | Personen-ID: `IdentityMap` | Enthält Push-Tracking-Ereignisse. |
| Adobe Journey Optimizer-Entitätsdatensatz | Suche | Schlüssel: `_id`<br>Passender Schlüssel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Enthält Klassifizierungen, die Journey- und Campaign-Metadaten mit allen Adobe Journey Optimizer-Ereignisdaten verknüpfen. |

{style="table-layout:auto"}

## Erstellen einer Datenansicht

Sobald eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de) erstellen, um die gewünschten Dimensionen und Metriken zu konfigurieren, die in Customer Journey Analytics verfügbar sind.

>[!NOTE]
>
>Die Datenabweichungen zwischen Adobe Journey Optimizer und Customer Journey Analytics betragen in der Regel weniger als 1–2 %. Größere Abweichungen sind bei Daten möglich, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche, die den heutigen Tag ausschließen, um Abweichungen aufgrund der Verarbeitungszeit zu vermeiden.

### Konfigurieren von Dimensionen

Sie können die folgenden Dimensionen in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Dimensionen im Entscheidungs-Management zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für Details zu den Anpassungsoptionen für Dimensionen.

| Dimension | Schemaelement | Einstellungen der Komponente |
| --- | --- | --- |
| Aktivitätsname | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Komponententyp: Dimension |
| Container-Kennung | `_experience.decisioning.containerID` | Komponententyp: Dimension |
| Korrelationskennung | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Komponententyp: Dimension |
| Name der Entscheidungsoption | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Komponententyp: Dimension |
| Name der Fallback-Entscheidungsoption | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Komponententyp: Dimension |
| Name der Platzierung | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Komponententyp: Dimension |

{style="table-layout:auto"}


### Konfigurieren von Metriken

Sie können die folgenden Metriken in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Metriken im Entscheidungs-Management zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für weitere Informationen zu den Anpassungsoptionen von Metriken.

| Metrik | Beschreibung | Schemaelement | Einstellungen der Komponente |
| --- | --- | --- | --- |
| Ereignistyp (umbenennen, um auf ein bestimmtes Ereignis zu verweisen, beispielsweise `Feedback` für `message.feedback`) [1] | Umfang eines bestimmten Ereignistyps | `eventType` | Komponententyp: Metrik<br/>**[!UICONTROL Werteinschluss/-ausschluss festlegen ]**: Ein<br/>**[!UICONTROL Übereinstimmung]**: [!UICONTROL Wenn alle Kriterien erfüllt sind]<br/>**[!UICONTROL Kriterien ]**:**[!UICONTROL  Gleich ]**`message.feedback` |
| Score von Entscheidungsoptionen | Berechneter Wert für eine Entscheidungsoption im Kontext eines einzelnen Geltungsbereichs. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Komponententyp: Metrik |
| Score der Fallback-Entscheidungsoptionen | Berechneter Wert für eine Fallback-Entscheidungsoption im Kontext eines einzelnen Geltungsbereichs. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Komponententyp: Metrik |
| Verwerfen von Angeboten | Die Anzahl der Angebote, die ohne andere direkte Interaktion verworfen oder abgelehnt wurden. | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponententyp: Metrik |
| Angebotsanzeige | Die Anzahl der dem Profil angezeigten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponententyp: Metrik |
| Angebots-Interaktionen | Die Anzahl der dem Profil angezeigten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Komponententyp: Metrik |
| Angebotsversand | Die Anzahl der an das Profil gesendeten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.send` | Komponententyp: Metrik |
| Angebots-Trigger | Die Anzahl der vom Client-SDK ausgewählten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponententyp: Metrik |
| Abmeldung von Angeboten | Die Anzahl der Angebote, die vom Profil angefordert wurden und in Zukunft nicht mehr angezeigt werden. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponententyp: Metrik |

{style="table-layout:auto"}

[1] Sie können für die verschiedenen verfügbaren Ereignistypen mehrere Metriken definieren. Weitere Informationen finden Sie unter [Komponenteneinstellungen für Werteinschluss/-ausschluss](/help/data-views/component-settings/include-exclude-values.md).
