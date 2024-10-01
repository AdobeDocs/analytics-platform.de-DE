---
description: Erfahren Sie mehr über die Fehlermeldungen und die Fehlerbehebung in Adobe Analysis Workspace.
title: Häufige Fehler und Fehlerbehebung in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: ec32b7bca6fd4fc4b2652d1265048ec788f19718
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 74%

---

# Fehler und Fehlerbehebung

Bei der Interaktion mit Analysis Workspace können Fehler auftreten, die die Funktionalität oder Leistung des Programms beeinflussen können. Im Folgenden sind die häufigsten Fehlertypen, die Gründe dafür und Optimierungen aufgeführt, die vorgenommen werden können.

## Fehlermeldungen

Einige häufige Fehlermeldungen, die bei der Verwendung von Analysis Workspace angezeigt werden:

| Fehlermeldung | Warum tritt der Fehler auf? | Optimierung |
| --- | --- | --- |
| [!UICONTROL Die Datenansicht verzeichnet derzeit ein ungewöhnlich hohes Reporting-Aufkommen. Bitte später erneut versuchen.] | Ihr Unternehmen versucht, zu viele Anfragen gleichzeitig für eine bestimmte Datenansicht auszuführen. Dieser Fehler kann etwa ausgelöst werden durch API-Anfragen, geplante Projekte, terminierte Berichte, terminierte Warnhinweise und die gleichzeitige Ausführung von Reporting-Anfragen durch mehrere Benutzende. | Verteilen Sie die Anfragen und Zeitpläne für die Datenansicht gleichmäßiger über den Tag.<p>Admins können den [Berichterstellungsaktivitäts-Manager verwenden, um Anfragen zu identifizieren und abzubrechen](/help/reporting-activity-manager/reporting-activity-overview.md), die Berichtskapazität verbrauchen.</p> |
| [!UICONTROL Dieser Bericht ist zu komplex. Beachten Sie die Best Practices für die Erstellung von Analysis Workspace-Berichten.] | Ihre Reporting-Anfrage ist zu groß und kann nicht ausgeführt werden. Gründe für diesen Fehler sind Zeitüberschreitungen aufgrund der Komplexität der Anfrage. | Vereinfachen Sie Ihre Anfrage. Verkürzen Sie beispielsweise den Datumsbereich, vereinfachen Sie die Filterkriterien oder entfernen Sie einige Spalten oder Zeilen in Ihrer Tabelle. Sie können die Tabelle auch in separate Anforderungen unterteilen. |
| [!UICONTROL Die Datenansicht überschreitet derzeit die Berichtskapazitäten. Bitte vereinfachen Sie die Anfrage oder versuchen Sie es später erneut.] | Ihr Unternehmen versucht, zu viele Anfragen gleichzeitig für eine bestimmte Datenansicht auszuführen. Dieser Fehler kann etwa ausgelöst werden durch API-Anfragen, geplante Projekte und die gleichzeitige Ausführung von Reporting-Anfragen durch mehrere Benutzende. | Verteilen Sie die Anfragen und Zeitpläne für die Datenansicht gleichmäßiger über den Tag. |
| [!UICONTROL Es ist ein Systemfehler aufgetreten. Melden Sie eine Anfrage an die Kundenunterstützung unter **[!UICONTROL Hilfe > senden Sie ein Support-Ticket]** und geben Sie Ihren Fehler-Code an.] | Adobe hat ein Problem, das behoben werden muss. | Senden Sie den Fehler-Code an die Kundenunterstützung. |
| [!UICONTROL Fehler 500: Seite konnte nicht geladen werden] | Probleme mit Ihrem lokalen Netzwerk, wie z. B. die [Firewall-Einstellungen](https://experienceleague.adobe.com/en/docs/analytics/technotes/ip-addresses) der Firma, tragen zu diesem Fehler bei. Darüber hinaus tritt bei Adobe möglicherweise ein Problem auf, das behoben werden muss. | Versuchen Sie nach einigen Minuten erneut sich anzumelden. Wenn das Problem weiterhin besteht, senden Sie den EIM-Instanz-ID-Code an die Kundenunterstützung. |
| [!UICONTROL Ihre Anfrage schlug aufgrund zu vieler Spalten oder vorkonfigurierter Zeilen fehl.] | Ihre Tabelle enthält zu viele Freiformzellen (Zeile * Spalten). | Entfernen Sie Spalten oder Zeilen in der Tabelle oder erwägen Sie, die Tabelle in separate Anfragen zu unterteilen. |


## Fehlerbehebung

Bei Verwendung von Analysis Workspace können Sie die folgenden Informationen verwenden, um einige häufige Probleme zu beheben.

| Problem | Fehlerbehebung |
|---|---|
| Wenn ich eine Metrik ziehe, wird *Ungültige Daten* angezeigt. | „Ungültige Daten“ bedeuten, dass Adobe keine Daten mit der Kombination von Dimensionen und Metriken zurückgeben kann, die im Bericht verwendet werden. Beispielsweise können zwei Metriken, die übereinander gestapelt sind, nicht als Daten zurückgegeben werden, da es nicht möglich ist, zwei Metriken in dieser Weise anzuzeigen. Platzieren Sie die Metriken stattdessen nebeneinander. |
| Wenn ich eine Metrik ziehe, sehe ich keine tatsächlichen Daten - nur Nullen. | Wenn Sie einen Workspace-Bericht erfolgreich erstellt haben, aber keine Daten vorhanden sind, können Sie einige Punkte prüfen:<ul><li>Wenn Sie einen Filter in Ihrem Bericht angewendet haben, stimmen die Filterkriterien möglicherweise nicht mit den Daten überein. Versuchen Sie, den Filter zu entfernen oder die Filterdefinition anzupassen.</li><li>Überprüfen Sie den Datumsbereich in der oberen rechten Ecke und stellen Sie sicher, dass er auf einen erwarteten Wert eingestellt ist.</li><li>Navigieren Sie zu Ihrer Website und überprüfen Sie mit dem [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=de), ob Daten erfasst werden.</li></ul> |
