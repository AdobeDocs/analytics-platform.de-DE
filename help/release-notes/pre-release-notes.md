---
title: Hinweise zu Vorabversionen von Customer Journey Analytics
description: Aktuelle Versionshinweise zu Customer Journey Analytics vor der Veröffentlichung anzeigen
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 81%

---

# Hinweise zu Vorabversionen von Adobe Customer Journey Analytics

>[!IMPORTANT]
>
>Dieses Dokument ist als **Vorschau** der Versionshinweise für den aktuellen Monat gedacht. Release-Elemente können sich ändern und in der endgültigen Version hinzugefügt oder entfernt werden.

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 2. Juni 2025 bis zum 15. Juli 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht.

Versionshinweise zu Adobe Experience Platform und anderen Programmen finden Sie in der folgenden Dokumentation:

* [Adobe Experience Platform](https://experienceleague.adobe.com/de/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [Komposition föderierter Zielgruppen](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Das linke Panel in Analysis Workspace wird beim Bewegen des Mauszeigers nicht mehr geöffnet und geschlossen** | Das linke Panel in Analysis Workspace wird verwendet, um Ihrem Projekt Elemente wie Komponenten, Panels und Visualisierungen hinzuzufügen. Die Option zum vorübergehenden Öffnen des linken Panels durch Bewegen des Mauszeigers über eines der Symbole ganz links ist nicht mehr verfügbar. Klicken Sie stattdessen einfach auf eines dieser Symbole, damit das Panel geöffnet bleibt, und klicken Sie dann auf dasselbe Symbol, um es zu schließen. |  | &#x200B;2. Juni 2025 <p>(Veröffentlichung ursprünglich für den 29. Mai 2025 geplant)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition unterstützt B2B-Unternehmen dabei, ihre Marketing-, Vertriebs- und Produkt-Teams aufeinander abzustimmen, indem verwertbare Kontoerkenntnisse bereitgestellt werden, die das Umsatzwachstum fördern. Wenn das Konto in den Mittelpunkt des Datenmodells gestellt wird, konzentriert sich die gesamte Analyse auf die Konto-Journey. Durch das Hinzufügen einer neuen Ebene von Entitäten (Konten, Opportunities und Käufergruppen) zu Personen- und zeitbasierten Ereignissen erhalten Sie ein vollständiges Bild vom Lebenszyklus des B2B-Marketings und Umsatzes. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18. Juni 2025 |
| **Unterstützung für sichere Ziele in Report Builder** | Dem Report Builder-Add-in wurden neue Exportziele hinzugefügt. Die folgenden Cloud-Speicherziele werden unterstützt: <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 18. Juni 2025 |
| **Neues Vorschauerlebnis** | Der Vorschaubereich, der zur Vorschau von Segmenten, berechneten Metriken und mehr verwendet wird, nutzt jetzt eine Darstellung mit horizontalen Balken anstelle einer Darstellung mit Ringdiagrammen. |  | 18. Juni 2025 |
| **Geändertes Dialogfeld für Attributionsmodelle** | Sie können nun den Container und den Zeitraum separat im Dialogfeld für Attributionsmodelle definieren. |  | 18. Juni 2025 |
| **Verbindungszuordnung** | Eine neue [Verbindungszuordnungs-Schnittstelle](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection#connection-map) ist verfügbar, um die Verbindungskonfiguration visuell anzuzeigen. |  | 18. Juni 2025 |
| **Hinzufügen und Anzeigen von Kommentaren in Analysis Workspace-Projekten** | Eine neue [Kommentarfunktion](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) in Analysis Workspace ermöglicht es Ihnen, im Rahmen eines Analysis Workspace-Projekts Erkenntnisse zu teilen und Fragen zu stellen. Dadurch können Diskussionen über die Daten optimiert werden, sodass Gespräche im Kontext der diskutierten Daten geführt werden. Sie können <ul><li>jedes Analysis Workspace-Projekt kommentieren, auf das Sie Zugriff haben,</li><li>einen bestimmten Punkt in einer Visualisierung kommentieren oder allgemeine Kommentare zu einem Projekt abgeben,</li><li>andere Benutzende taggen, um sie über Ihre Kommentare zu informieren,</li><li>vorhandene Kommentare verwalten (bearbeiten, anheften, schließen usw.).</li></ul>Customer Journey Analytics-Admins können die [Kommentarfunktion auf Organisationsebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Projektverantwortliche können die [Kommentarfunktion auf Projektebene deaktivieren](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | &#x200B;25. Juni 2025 <p>(Veröffentlichung ursprünglich für den 29. Mai 2025 geplant)</p> |
