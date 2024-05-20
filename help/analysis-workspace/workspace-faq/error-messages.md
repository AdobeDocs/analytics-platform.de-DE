---
description: Erfahren Sie mehr über die Fehlermeldungen in Adobe Analysis Workspace und den zugehörigen Komponenten.
title: Allgemeine Fehlermeldungen in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: 51a20b0a1f003d2e6ce8baf4d7cec16bfa2fe5b3
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 88%

---

# Allgemeine Fehlermeldungen

Bei der Interaktion mit Analysis Workspace können Fehler auftreten, die auch die Leistung beeinflussen. Im Folgenden sind die häufigsten Fehlertypen, die Gründe dafür und Optimierungen aufgeführt, die vorgenommen werden können.

| Fehlermeldung | Grund | Optimierung |
| --- | --- | --- |
| [!UICONTROL Die Datenansicht überschreitet derzeit die Berichterstellungskapazität. Bitte vereinfachen Sie die Anfrage oder versuchen Sie es später erneut.] | Ihre Reporting-Anforderung ist zu komplex und muss vereinfacht werden. | Schränken Sie Ihre Berichtskriterien ein und versuchen Sie es erneut. |
| [!UICONTROL Es ist ein Systemfehler aufgetreten. Melden Sie eine Anfrage an die Kundenunterstützung unter **[!UICONTROL Hilfe > senden Sie ein Support-Ticket]** und geben Sie Ihren Fehler-Code an.] | Adobe hat ein Problem, das behoben werden muss. | Senden Sie den Fehler-Code an die Kundenunterstützung. |
| [!UICONTROL Fehler 500: Seite konnte nicht geladen werden] | Probleme mit Ihrem lokalen Netzwerk, wie z. B. die [Firewall-Einstellungen](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=de) der Firma, tragen zu diesem Fehler bei. Darüber hinaus tritt bei Adobe möglicherweise ein Problem auf, das behoben werden muss. | Versuchen Sie nach einigen Minuten erneut sich anzumelden. Wenn das Problem weiterhin besteht, senden Sie den EIM-Instanz-ID-Code an die Kundenunterstützung. |
| [!UICONTROL Einer der Filter oder die Suche in dieser Visualisierung enthält eine Textsuche, die zu viele Ergebnisse zurückgibt.] | Ihre Filterkriterien oder Berichtsfilter sind zu breit angelegt. | Schränken Sie die Suchtextkriterien ein und führen Sie die Anfrage erneut aus. |
| [!UICONTROL Die Anfrage ist zu komplex.] | Ihre Reporting-Anfrage ist zu groß und kann nicht ausgeführt werden. Gründe für diesen Fehler sind Zeitüberschreitungen aufgrund der Anfragengröße, zu viele übereinstimmende Elemente in einem Filter oder Suchfilter, zu viele eingeschlossene Metriken, inkompatible Dimensions- und Metrikkombinationen usw. | Vereinfachen Sie Ihre Anfrage, indem Sie einige Spalten oder Zeilen in der Tabelle entfernen oder die Tabelle in separate Anfragen aufteilen. |
| [!UICONTROL Ihre Anfrage schlug aufgrund zu vieler Spalten oder vorkonfigurierter Zeilen fehl.] | Ihre Tabelle enthält zu viele Freiformzellen (Zeile * Spalten). | Entfernen Sie Spalten oder Zeilen in der Tabelle oder erwägen Sie, die Tabelle in separate Anfragen zu unterteilen. |
