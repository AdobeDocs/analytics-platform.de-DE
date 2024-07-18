---
description: Erfahren Sie mehr über Anwendungsfälle für die Kohortenanalyse.
keywords: Analysis Workspace
title: Anwendungsfälle für die Kohortenanalyse
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 96%

---

# Anwendungsfälle für die [!UICONTROL Kohortenanalyse]

Anwendungsfälle für die [!UICONTROL Kohortenanalyse].

## Anwendungsfall: Mobile-App-Interaktion

Angenommen Sie möchten herausfinden, wie Benutzer, die Ihre Anwendung installieren, im Laufe der Zeit damit interagieren. Installieren sie die Anwendung, benutzen sie aber nie? Benutzen sie die Anwendung eine Zeit lang und hören dann auf? Oder bleiben Sie die ganze Zeit dabei?

Sie können eine [!UICONTROL Kohortenanalyse] über sechs Monate erstellen:

**Granularität**: Monatlich, von Januar 2015 bis Juni 2015

**Aufnahmemetrik**: Anwendungsinstallationen

**Rückkehrmetrik**: Sitzungen oder Starts

Besucher werden in den Folgemonaten nicht als *`engaged`* gezählt, es sei denn, sie haben eine Sitzung oder starten mindestens die App. Die [!UICONTROL Kohortenanalyse] zeigt Ihnen dann Nutzungsmuster, bei denen *`App Install`* immer in Monat 0 auftritt. Vielleicht stellen Sie fest, dass die Verwendung im zweiten Monat zurückgeht, unabhängig vom Zeitpunkt der Installation der Anwendung durch die Benutzer. (Für diejenigen, die die Anwendung im Januar 2015 installiert haben, ist der zweite Monat der März 2015. Für diejenigen, die die Anwendung im Februar 2015 installiert haben, ist der zweite Monat der April 2015 usw.) Diese Analyse bietet Ihnen die Möglichkeit, im zweiten Monat nach der Installation der Anwendung an alle Benutzer eine E-Mail oder eine Push-Nachricht zu senden, um sie daran zu erinnern, die Anwendung zu verwenden.

## Anwendungsfall: Abonnement

Sie arbeiten bei Adobe.com und bieten ein kostenloses Creative Cloud-Abonnement an. Das Ziel besteht darin, dass die Benutzer ein Upgrade von der kostenlosen Version auf das 30-tägige Probe-Abo oder letztlich auf die zahlungspflichtige Version durchführen.

**Granularität**: Monatlich

**Aufnahmemetrik**: Download-Link

**Rückkehrmetrik**: Kauf der zahlungspflichtigen Creative Cloud

Mithilfe dieser [!UICONTROL Kohortenanalyse] könnten Sie z. B. sehen, dass zwischen 8 % und 10 % der Benutzer der kostenlosen Creative Cloud-Version im ersten Monat nach der Installation ein Upgrade durchführen, unabhängig vom Zeitpunkt der Installation. 12–15 % führen im zweiten Monat der Verwendung ein Upgrade durch. Danach lassen die Upgrades merklich nach: 4–5 % im dritten Monat, 3–4 % im vierten Monat und 1–2 % im fünften Monat.

Da deutlich wird, dass Sie im dritten Monat keine potenziellen Kunden verlieren sollten, richten Sie eine E-Mail-Kampagne ein, die in der Mitte des dritten Monats an eine Stichprobe der Benutzer herausgeht und Benutzern, die noch kein Upgrade durchgeführt haben, einen Gutschein über 50 $ anbietet.

Einige Monate später erstellen Sie erneut einen Kohortenanalysebericht. Für Kohorten, die nach dem Start der Kampagne gebildet wurden, ist die Konversion zu zahlungspflichtigen Creative Cloud-Abonnements von 4–5 % auf 13–14 % gestiegen, was pro Kohorte für mehrere hunderttausend Dollar steht, für alle monatlichen Kohorten, die ab diesem Punkt den dritten Monat erreichen.

## Anwendungsfall für komplexe Kohortenfilter

Eine große Hotelkette zielt auf mehrere Kundengruppen für Promotionen ab und verfolgt sie auf Grundlage der Leistung nach. Um die besten Gruppen von Benutzerkohorten für die Zielgruppe zu identifizieren, sollen sehr spezifische Kohortengruppen gebildet werden. Mithilfe der erweiterten [!UICONTROL Einschluss]- und [!UICONTROL Rückgabe]-Kriterien innerhalb der [!UICONTROL Kohortentabellen] sind sie in der Lage, genau die richtigen Kohortengruppierungen mit mehreren Metriken und Filtern zu definieren, um leistungsschwache Kundengruppen zu identifizieren und sie gezielt mit Werbeaktionen und Angeboten anzusprechen, um die Buchungen zu steigern.

## Anwendungsfall zur Annahme der App-Version

Bei einem großen Versicherungsunternehmen wird ein großer Teil der Kundeninteraktion über die Nutzung der mobilen Anwendung gefördert. Da jedoch immer wieder neue Funktionen zur App hinzugefügt werden, ist es wichtig, dass die Kunden eine Aktualisierung auf die neueste App-Version durchführen. Sie können alle App-Versionen mithilfe der Kohorte [!UICONTROL Benutzerspezifische Dimension] gegeneinander analysieren und miteinander vergleichen, um zu sehen, auf welche Kunden mit welcher App-Version abgezielt werden sollte. Darüber hinaus können sowohl die Bindung als auch die Abwanderung verfolgt werden, um festzustellen, ob bestimmte App-Versionen Kunden davon abhalten, die App im Laufe der Zeit zu nutzen. Durch mobiles Messaging kann eine erneute Interaktion mit solchen Benutzern stattfinden, damit diese eine Aktualisierung auf die neueste Version durchführen, um die Vorteile der neuesten Funktionen nutzen zu können.

## Anwendungsfall zur Kampagnentreue

Ein internationales Medienunternehmen verwendet Zielgruppen-Kampagnen, um Benutzer auf die verschiedenen Plattformen zu leiten und so die Interaktion zu fördern. Die Werbeausgaben pro Plattform basieren auf der Kundeninteraktion und -bindung, daher sind erfolgreiche Kampagnen entscheidend für den Erfolg des Unternehmens. Unsere neue Funktion für die Kohorte [!UICONTROL Benutzerspezifische Dimension] in [!UICONTROL Kohortentabellen] wird verwendet, um verschiedene Kampagnen nebeneinander zu vergleichen und herauszufinden, welche Kampagnen am effektivsten sind, um Benutzer zu gewinnen und zu binden und so die Interaktion zu fördern. Anschließend kann festgestellt werden, welche Aspekte zum Erfolg einer Kampagne beitragen. Diese Erkenntnisse können dann auf andere Kampagnen angewendet werden, um die Interaktion auf den verschiedenen Plattformen zu fördern.

## Anwendungsfall einer Produkteinführung

Ein großer Kleidungseinzelhändler verfügt über viele spezifische Kundenfilter, durch die große Teile des Unternehmensumsatzes gefördert werden. Für jeden Filter werden spezifische Produkte unter Berücksichtigung des jeweiligen Filters entwickelt und hergestellt. Bei jeder Produkteinführung soll identifiziert werden, wie das neue Produkt die Verkäufe in den verschiedenen Kohorten im Laufe der Zeit gesteigert hat. Mit der neuen Einstellung [!UICONTROL Latenztabelle] in der [!UICONTROL Kohortenanalyse] können das Verhalten und der Umsatz eines bestimmten Kundenfilters vor und nach der Markteinführung analysiert werden. Anhand dieser Informationen kann festgestellt werden, durch welche Produkte neue Umsätze generiert werden und welche bei den Kunden weniger beliebt sind.

## Individuelle Stickiness - Anwendungsfall der meisten treuen Benutzer

Bei einer großen Fluggesellschaft hängt der Erfolg und Umsatz zu einem großen Teil von wiederkehrenden und treuen Kunden ab. In vielen Fällen machen treue Reisende den Großteil des Umsatzes aus und die Bindung dieser Kunden ist entscheidend für den langfristigen Erfolg. Oft kann es sich schwierig gestalten herauszufinden, welche die treuesten und beständigsten Kunden sind. Mithilfe der neuen Einstellung [!UICONTROL Rollierende Berechnung] in der [!UICONTROL Kohortenanalyse] konnte das Unternehmen jedoch Filter für treue Kunden analysieren und herausfinden, welche Reisenden Monat für Monat zu Wiederholungskäufern wurden. So konnten diese Reisenden dann mit Vorteilen und Vergünstigungen für ihre Treue belohnt werden. Darüber hinaus konnte durch die Umstellung des Kohortentyps von Bindung auf Abwanderung auch monatsweise festgestellt werden, welche Reisenden nicht erneut eingekauft hatten. Für diese Filter können dann Marketingaktionen durchgeführt werden, sodass erneut eine Verbindung mit diesen Kunden aufgebaut und sichergestellt werden kann, dass sie auch in Zukunft treue Kunden bleiben.
