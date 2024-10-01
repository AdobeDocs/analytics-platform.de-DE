---
description: Erfahren Sie mehr über Anwendungsfälle für die Kohortenanalyse.
keywords: Analysis Workspace
title: Anwendungsfälle für die Kohortenanalyse
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 388042e24a7b9d33ac88e05a68689308e6258339
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 51%

---

# Anwendungsfälle für die Kohortenanalyse ][!UICONTROL 

In diesem Artikel werden einige Anwendungsfallbeispiele für die [!UICONTROL Kohortenanalyse] beschrieben.

## Anwendungsfall: Mobile-App-Interaktion

Angenommen Sie möchten herausfinden, wie Benutzer, die Ihre Anwendung installieren, im Laufe der Zeit damit interagieren. Installieren sie die Anwendung, benutzen sie aber nie? Benutzen sie die Anwendung eine Zeit lang und hören dann auf? Oder bleiben Sie die ganze Zeit dabei?

Sie können eine [!UICONTROL Kohortenanalyse] über sechs Monate erstellen:

**Granularität**: Monatlich, von Januar 2015 bis Juni 2015

**Aufnahmemetrik**: Anwendungsinstallationen

**Rückkehrmetrik**: Sitzungen oder Starts

Personen zählen in nachfolgenden Monaten nicht als *interagiert*, es sei denn, sie haben eine Sitzung oder starten die App zumindest. [!UICONTROL Kohortenanalyse] zeigt Ihnen dann Nutzungsmuster, bei denen die *App-Installation* immer im Monat 0 auftritt. Vielleicht stellen Sie fest, dass die Verwendung im zweiten Monat zurückgeht, unabhängig vom Zeitpunkt der Installation der Anwendung durch die Benutzer. (Für Benutzer, die die App im Januar 2015 installiert haben, ist der zweite Monat der März 2015. Für die Personen, die die App im Februar 2015 installiert haben, ist der zweite Monat der April 2015 usw.) Diese Analyse ermöglicht es Ihnen, im zweiten Monat nach der Installation der App eine E-Mail oder eine Push-Nachricht an alle Benutzer zu senden, um sie an die Verwendung der App zu erinnern.

## Anwendungsfall: Abonnement

Sie arbeiten bei Adobe.com und bieten ein kostenloses Creative Cloud-Abonnement an. Das Ziel besteht darin, dass die Benutzer ein Upgrade von der kostenlosen Version auf das 30-tägige Probe-Abo oder letztlich auf die zahlungspflichtige Version durchführen.

**Granularität**: Monatlich

**Aufnahmemetrik**: Download-Link

**Rückkehrmetrik**: Kauf der zahlungspflichtigen Creative Cloud

Mithilfe der [!UICONTROL Kohortenanalyse] können Sie beispielsweise sehen, dass zwischen 8 % und 10 % der kostenlosen Creative Cloud-Benutzer im ersten Monat nach der Installation ein Upgrade durchführen. Unabhängig davon, wann die Benutzer installiert sind. 12–15 % führen im zweiten Monat der Verwendung ein Upgrade durch. Danach lassen die Upgrades merklich nach: 4–5 % im dritten Monat, 3–4 % im vierten Monat und 1–2 % im fünften Monat.

Sie möchten keine potenziellen Kunden im dritten Monat verlieren. Sie richten also eine E-Mail-Kampagne ein, die Mitte des dritten Monats an eine Stichprobe von Benutzern gesendet werden soll. Angebot eines Gutscheins von 50 USD für Benutzer, die noch kein Upgrade durchgeführt haben.

Sehen Sie sich einige Monate später Ihre Kohortenanalyseberichte an. Für Kohorten, die nach dem Start der Kampagne gebildet wurden, ist die Konversion in bezahlte Creative Cloud-Abonnements im dritten Monat von 4-5 % auf 13-14 % gestiegen. Dieser Anstieg der Konversionen führt zu Hunderttausenden von Dollar pro Kohorte, für jede monatliche Kohorte, die ab diesem Zeitpunkt den dritten Monat erreicht.

## Anwendungsfall für komplexe Kohortenfilter

Eine große Hotelkette zielt auf mehrere Kundengruppen für Promotionen ab und verfolgt sie auf Grundlage der Leistung nach. Um die besten Gruppen von Benutzerkohorten zu identifizieren, die als Ziel ausgewählt werden sollen, möchten sie sehr spezifische Kohortengruppen erstellen. Mithilfe der erweiterten Kriterien [!UICONTROL Aufnahme] und [!UICONTROL Rückgabe] innerhalb der Tabellen [!UICONTROL Kohorte] kann die Hotelkette genau die richtigen Kohortengruppierungen mit mehreren Metriken und Filtern definieren. So kann die Hotelkette leistungsschwache Kundengruppen identifizieren, um Kunden mit Promotions und Angeboten anzusprechen und so die Buchungen zu steigern.

## Anwendungsfall zur Annahme der App-Version

Ein großes Versicherungsunternehmen treibt die Kundeninteraktion durch die Verwendung seiner mobilen App voran. Da jedoch immer wieder neue Funktionen zur App hinzugefügt werden, ist es wichtig, dass die Kunden eine Aktualisierung auf die neueste App-Version durchführen. Sie können alle App-Versionen mithilfe der Kohorte [!UICONTROL Benutzerspezifische Dimension] gegeneinander analysieren und miteinander vergleichen, um zu sehen, auf welche Kunden mit welcher App-Version abgezielt werden sollte. Darüber hinaus können sowohl die Bindung als auch die Abwanderung verfolgt werden, um festzustellen, ob bestimmte App-Versionen Kunden davon abhalten, die App im Laufe der Zeit zu nutzen. Durch mobiles Messaging kann eine erneute Interaktion mit solchen Benutzern stattfinden, damit diese eine Aktualisierung auf die neueste Version durchführen, um die Vorteile der neuesten Funktionen nutzen zu können.

## Anwendungsfall zur Kampagnentreue

Ein internationales Medienunternehmen verwendet Zielgruppen-Kampagnen, um Benutzer auf die verschiedenen Plattformen zu leiten und so die Interaktion zu fördern. Die Werbeausgaben pro Plattform basieren auf der Kundeninteraktion und -bindung, daher sind erfolgreiche Kampagnen entscheidend für den Erfolg des Unternehmens. Sie verwenden die neue Kohortenfunktion [!UICONTROL Benutzerdefinierte Dimension] in den Tabellen [!UICONTROL Kohorte] , um verschiedene Kampagnen nebeneinander zu vergleichen und herauszufinden, welche Kampagnen am effektivsten sind, um Benutzer zu gewinnen und zu binden und so die Interaktion zu steigern. Anschließend kann festgestellt werden, welche Aspekte zum Erfolg einer Kampagne beitragen. Diese Erkenntnisse können dann auf andere Kampagnen angewendet werden, um die Interaktion auf den verschiedenen Plattformen zu fördern.

## Anwendungsfall einer Produkteinführung

Ein großer Kleidungseinzelhändler verfügt über viele spezifische Kundenfilter, durch die große Teile des Unternehmensumsatzes gefördert werden. Für jeden Filter werden spezifische Produkte unter Berücksichtigung des jeweiligen Filters entwickelt und hergestellt. Bei jeder Produkteinführung soll identifiziert werden, wie das neue Produkt die Verkäufe in den verschiedenen Kohorten im Laufe der Zeit gesteigert hat. Mit der neuen Einstellung [!UICONTROL Latenztabelle] in der [!UICONTROL Kohortenanalyse] können das Verhalten und der Umsatz eines bestimmten Kundenfilters vor und nach der Markteinführung analysiert werden. Anhand dieser Informationen kann festgestellt werden, durch welche Produkte neue Umsätze generiert werden und welche bei den Kunden weniger beliebt sind.

## Individuelle Stickiness - Anwendungsfall der meisten treuen Benutzer

Bei einer großen Fluggesellschaft hängt der Erfolg und Umsatz zu einem großen Teil von wiederkehrenden und treuen Kunden ab. In vielen Fällen machen treue Reisende den Großteil des Umsatzes aus und die Bindung dieser Kunden ist entscheidend für den langfristigen Erfolg. Oft kann es sich schwierig gestalten herauszufinden, welche die treuesten und beständigsten Kunden sind. Mit der neuen Einstellung [!UICONTROL Rollierende Berechnung] in der [!UICONTROL Kohortenanalyse] kann die Fluglinie jedoch Filter für treue Kunden analysieren und herausfinden, welche Reisenden im Monat für Monat erneut Kunden waren. Die Fluggesellschaft ist auch in der Lage, diese Reisenden mit Belohnungen und Prämien für ihre Loyalität anzusprechen. Darüber hinaus kann die Fluggesellschaft durch Umstellung des Kohortentyps von Bindung auf Abwanderung identifizieren, welche Kunden monatlich keine wiederkehrenden Käufer sind, und diese Kunden mit Promotions ansprechen. So kann die Fluggesellschaft wieder mit diesen Kunden interagieren und sicherstellen, dass sie auch in Zukunft treue Kunden bleiben.
