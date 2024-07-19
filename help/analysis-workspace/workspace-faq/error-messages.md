---
description: Erfahren Sie mehr über die Fehlermeldungen in Adobe Analysis Workspace und den zugehörigen Komponenten.
title: Allgemeine Fehlermeldungen in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 66%

---

# Allgemeine Fehlermeldungen

Bei der Interaktion mit Analysis Workspace können Fehler auftreten, die auch die Leistung beeinflussen. Im Folgenden sind die häufigsten Fehlertypen, die Gründe dafür und Optimierungen aufgeführt, die vorgenommen werden können.

| Fehlermeldung | Grund | Optimierung |
| --- | --- | --- |
| [!UICONTROL Die Datenansicht verzeichnet derzeit ein ungewöhnlich hohes Reporting-Aufkommen. Bitte später erneut versuchen.] | Ihr Unternehmen versucht, zu viele gleichzeitige Anfragen für eine bestimmte Datenansicht auszuführen. Zu diesem Fehler gehören API-Anfragen, geplante Projekte, terminierte Berichte, terminierte Warnhinweise und gleichzeitige Benutzer, die Reporting-Anfragen ausführen. | Verteilen Sie Ihre Anforderungen und Zeitpläne für die Datenansicht gleichmäßig über den Tag.<p>Administratoren können den [Berichterstellungsaktivitäts-Manager verwenden, um Anforderungen zu identifizieren und abzubrechen](/help/reporting-activity-manager/reporting-activity-overview.md), die die Berichtskapazität beanspruchen.</p> |
| [!UICONTROL Dieser Bericht ist zu komplex. Beachten Sie die Best Practices für die Erstellung von Analysis Workspace-Berichten.] | Ihre Reporting-Anfrage ist zu groß und kann nicht ausgeführt werden. Gründe für diesen Fehler sind Timeouts aufgrund der Komplexität der Anfrage. | Vereinfachen Sie Ihre Anforderung, indem Sie den Datumsbereich verkürzen, die Filterkriterien vereinfachen oder einige Spalten oder Zeilen in Ihrer Tabelle entfernen. Alternativ können Sie die Tabelle in separate Anforderungen aufteilen. |
| [!UICONTROL Die Datenansicht überschreitet derzeit die Berichtskapazitäten. Bitte vereinfachen Sie die Anfrage oder versuchen Sie es später erneut.] | Ihr Unternehmen versucht, zu viele gleichzeitige Anfragen für eine bestimmte Datenansicht auszuführen. Gründe für diesen Fehler sind API-Anfragen, geplante Projekte und gleichzeitige Benutzer, die Berichterstellungsanfragen ausführen. | Verteilen Sie Ihre Anforderungen und Zeitpläne für die Datenansicht gleichmäßig über den Tag. |
| [!UICONTROL Es ist ein Systemfehler aufgetreten. Melden Sie eine Anfrage an die Kundenunterstützung unter **[!UICONTROL Hilfe > senden Sie ein Support-Ticket]** und geben Sie Ihren Fehler-Code an.] | Adobe hat ein Problem, das behoben werden muss. | Senden Sie den Fehler-Code an die Kundenunterstützung. |
| [!UICONTROL Fehler 500: Seite konnte nicht geladen werden] | Probleme mit Ihrem lokalen Netzwerk, wie z. B. die [Firewall-Einstellungen](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=de) der Firma, tragen zu diesem Fehler bei. Darüber hinaus tritt bei Adobe möglicherweise ein Problem auf, das behoben werden muss. | Versuchen Sie nach einigen Minuten erneut sich anzumelden. Wenn das Problem weiterhin besteht, senden Sie den EIM-Instanz-ID-Code an die Kundenunterstützung. |
| [!UICONTROL Ihre Anfrage schlug aufgrund zu vieler Spalten oder vorkonfigurierter Zeilen fehl.] | Ihre Tabelle enthält zu viele Freiformzellen (Zeile * Spalten). | Entfernen Sie Spalten oder Zeilen in der Tabelle oder erwägen Sie, die Tabelle in separate Anfragen zu unterteilen. |
