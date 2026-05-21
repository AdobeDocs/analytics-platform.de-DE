---
title: Upgrade von Adobe Analytics auf Customer Journey Analytics
description: Erfahren Sie mehr über die empfohlenen Schritte für das Upgrade von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bd19250e-91c0-49f6-b6dc-3abd641344aa
TQID: https://experienceleague.adobe.com/DtETa7Qh3l2X9YSjkX56zX8CmDTWVpGvvyrd9HFayt4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c4147b6e-073b-4d3c-9ab1-d60f2f4434efid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1186
ht-degree: 15%

---

# Vorbereiten der Organisation für das Upgrade auf Customer Journey Analytics

Ein erfolgreiches Upgrade (wie unter [Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) beschrieben) dient dazu, Ihr Unternehmen vorzubereiten, indem Sie sich auf bestimmte betriebliche Überlegungen konzentrieren. Zur Vorbereitung Ihrer Organisation wird Folgendes empfohlen:

* Akzeptanz und Ausrichtung bei wichtigen Stakeholdern

* Ziele definieren und dokumentieren

* Setzen Sie realistische und durchdachte Zeitpläne

* Klare Verantwortlichkeiten für Mitwirkende definieren

## Akzeptanz und Ausrichtung bei Stakeholdern

Die wichtigsten Stakeholder und Entscheidungsträger in Ihrem Unternehmen müssen Ihr Upgrade auf Customer Journey Analytics abstimmen.

In den folgenden Abschnitten werden Möglichkeiten beschrieben, wie Sie eine Ausrichtung an Stakeholdern erreichen können.

### Wertorientierung

Konzentrieren Sie sich auf den Wert, den Customer Journey Analytics für Ihr Unternehmen hat, und darauf, wie es Ihre Geschäftsziele schneller erreichen kann.

Die folgende Tabelle enthält einige wichtige Funktionen, die Sie hervorheben möchten.

| Funktion | Vorteil | Beispiel |
|---------|----------|---------|
| **[Unterkunft für alle Arten von Daten](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home)** | Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. | Ein Einzelhandelsunternehmen könnte durch die Integration der folgenden Arten von Daten in eine einzige Ansicht Einblick in die vollständige Kunden-Journey gewähren: <ul><li>Web-Clickstream-Transaktionen</li><li>Mobile-App-Transaktionen</li><li>In-Store-Transaktionen</li><li>CRM- und Treuedaten</li></ul> |
| **[Cross-Channel-Analyse](/help/use-cases/cross-channel/cross-channel.md)** | Ermöglicht eine einzige konsolidierte Ansicht des Kundenverhaltens über verschiedene Kanäle hinweg, indem Daten aus verschiedenen Web-, Mobile- und Offline-Eigenschaften vereinheitlicht werden. | Ein Einzelhandelsunternehmen, das Daten aus mehreren Kanälen erfasst, könnte die folgende Art von Analyse durchführen:<p>Ein Käufer klickt auf eine Paid-Search-Anzeige, surft online in Jeans, erhält eine Push-Benachrichtigung und kauft zwei Tage später im Geschäft. Diese einheitliche Perspektive ermöglicht eine genaue kanalübergreifende Attribution und zeigt auf, wie digitale Touchpoints zum Umsatz in Geschäften beitragen. Sie unterstützt auch eine präzisere Segmentierung, z. B. die Abfrage von Kunden, die online surfen oder im Geschäft gekauft haben, mit maßgeschneiderten Angeboten. Darüber hinaus bietet sie ein klares, kanalübergreifendes Reporting über Umsätze in einem Dashboard, das fragmentierte, isolierte Einblicke durch ein ganzheitliches Verständnis des Kundenverhaltens ersetzt. |
| **[Verarbeitung zur Berichtszeit](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Wenden Sie rückwirkende Einstellungen an und erstellen Sie mehrere Versionen der Variablenpersistenz, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen. | Da Sie mit Customer Journey Analytics Metriken, Dimensionen und Attributionsmodelle dynamisch erstellen und anpassen können, ohne Daten erneut aufzunehmen oder erneut zu verarbeiten, könnte ein Einzelhandelsunternehmen sehen, wie eine kürzlich durchgeführte Social-Media-Kampagne sowohl den Online- als auch den Ladenverkauf beeinflusst hat, ohne das Engineering bitten zu müssen, Datensätze neu zu erstellen. Sie können das Attributionsmodell sofort von der Letztkontakt- zur Erstkontakt- oder benutzerdefinierten regelbasierten Attribution ändern. |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | Hilft Marketing-Fachleuten zu verstehen, wie sich Inhalte auf die von einem Unternehmen definierten wichtigsten Leistungsindikatoren auswirken. Zusätzlich zu den Verhaltensdaten erfasst Content Analytics Daten darüber, wie Inhalte konsumiert werden und wie Inhalte die Auswirkungen steuern. | Durch die Integration von Web-, App-, E-Mail- und sogar In-Store-Daten kann ein Einzelhandelsunternehmen genau erkennen, wie jede digitale Inhaltskomponente, die es erstellt, zum Kunden-Journey und zur Konversion beiträgt. <p>Das Einzelhandelsunternehmen konnte erkennen, dass ein „Summer Denim Style Guide“ auf einer beliebten Social-Media-Plattform ein hohes Engagement unter den Treueprogramm-Mitgliedern fördert, und dass diese Mitglieder innerhalb einer Woche 40 % häufiger Denim im-Store kaufen.</p> |

### Benennen eines Executive Sponsors

Finden Sie in Ihrem Unternehmen einen Executive Sponsor und ernennen Sie ihn. Dieser Sponsor aus der Führungsebene muss wissen, wie Customer Journey Analytics die Erreichung Ihrer Geschäftsziele beschleunigt.

Der Executive Sponsor ist entscheidend, da er:

* Verfechten von Customer Journey Analytics innerhalb des Unternehmens

* Hindernisse beseitigen

* Ressourcen genehmigen

### Sichern Sie sich den Support von wichtigen Führungskräften in Ihrem gesamten Unternehmen

Sichern Sie sich mithilfe Ihres Executive Sponsors die Unterstützung anderer wichtiger Führungskräfte in Ihrem gesamten Unternehmen. Es ist wichtig, dass Führungskräfte aus den folgenden Bereichen Ihres Unternehmens die Vorteile von Customer Journey Analytics verstehen und dass sie bereit sind, zu einer erfolgreichen Implementierung beizutragen:

* Analytics

* Marketing

* IT

* Rechtliche und Compliance-Anforderungen

* Einzelne Geschäftsbereiche

## Entwickeln eines Aktualisierungs- und Kommunikationsplans

### Entwickeln eines Aktualisierungsplans und Verteilen an die beteiligten Akteure

Ein Upgrade-Plan kann die folgenden Informationen enthalten:

* Eine klare Beschreibung, warum das Upgrade erfolgt. Beschreiben Sie beispielsweise die Vorteile für Benutzende und für das Unternehmen oder das Unternehmen als Ganzes. Weitere Informationen zu den Vorteilen finden Sie unter [Wert in den Mittelpunkt](#focus-on-value).

* Einen allgemeinen Zeitplan, z. B. für den geplanten Beginn des Upgrades, eine Übersicht über die wichtigsten Meilensteine und eine Schätzung, wann das Upgrade abgeschlossen sein soll.

* Ein Hinweis darauf, wann Benutzer offizielle Schulungen zum Umgang mit Customer Journey Analytics beginnen können. Weitere Informationen finden Sie unter [Schulung von Endbenutzenden in Ihrem gesamten Unternehmen](#train-end-users-throughout-your-organization).

* Informationen darüber, wer das Upgrade leitet und wie und wann sich Personen mit Fragen an Sie wenden können.

### Kommunikationsplan erstellen

Ein Kommunikationsplan kann die folgenden Überlegungen enthalten:

* Eine definierte Zeitspanne für den Versand von Nachrichten an Stakeholder und Benutzer

* Eine Übersicht über die Art der zu sendenden Informationen

* Ein Plan dafür, wer Nachrichten senden wird

* Definierte Feedback-Schleifen, mit denen Anwender und Stakeholder Fragen stellen oder Feedback geben können

## Bewertung und Prüfung der Adobe Analytics-Implementierung

Führen Sie eine gründliche Bewertung und Prüfung Ihrer Adobe Analytics-Implementierung durch, wobei Sie sich auf die folgenden Schlüsselbereiche konzentrieren:

* Aktuelle Benutzende

* Benutzerzugriff

* Projekte

* Geschäftsprozesse

* Benutzerdefinierte Komponenten

Weitere Informationen finden Sie in den folgenden Ressourcen:

* [Analytics-Inventar](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/analytics-inventory)

  Stellt Informationen zur Anzahl der Projekte, Segmente, berechneten Metriken, Report Suites und Benutzenden in Ihrer Organisation bereit.

* [Vorbereiten der Migration von Komponenten und Projekten von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Enthält Informationen zur Vorbereitung auf die Migration von Komponenten, Projekten und Benutzern.

## Identifizieren von Champions und Early Adopters

Identifizieren Sie Champions in Ihrem gesamten Unternehmen. Diese Champions sollten:

* Hauptbenutzer von Adobe Analytics

* Können schnell Kenntnisse in Customer Journey Analytics erwerben

* Verfügbar als Hilfe und Coach für andere, da Customer Journey Analytics auf breiterer Basis eingeführt wird

## Schulung von Endbenutzern in Ihrem gesamten Unternehmen

* Praktische Schulungen zu den Unterschieden bei Datenmodellen, Reporting-Paradigmen und neuen Funktionen in Customer Journey Analytics

* Bieten Sie sowohl Live-Sitzungen (Workshops oder Bürozeiten) als auch On-Demand-Ressourcen (Video-Tutorials, dynamische Wiki-Seiten und interne Dokumentation) an.

* Leiten Sie Benutzer zu relevanten Schulungen, Tutorials und Dokumentationen zu Experience League.

  Die folgenden Ressourcen können Ihnen bei den ersten Schritten helfen:

   * [Tutorials zu Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Was ist Customer Journey Analytics?](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Einführung in Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Unterstützung der Customer Journey Analytics-Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md)

## Befolgen Sie die empfohlenen Upgrade-Schritte

Wenn Sie bereit sind, den Upgrade-Prozess zu starten, befolgen Sie die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Upgrade-Schritte im Customer Journey Analytics-Upgrade-Handbuch. Um über Customer Journey Analytics auf den Leitfaden zuzugreifen, wählen Sie die Registerkarte **[!UICONTROL Arbeitsbereich]** und dann im linken Panel die Option **[!UICONTROL Upgrade auf Customer Journey Analytics]** aus. Befolgen Sie die Anweisungen auf dem Bildschirm.
