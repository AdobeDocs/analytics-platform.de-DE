---
description: Erfahren Sie mehr über einige Anwendungsbeispiele für die Kohortenanalyse.
keywords: Analysis Workspace
title: Anwendungsfälle für die Kohortenanalyse
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 51%

---

# Anwendungsfälle für die Kohortenanalyse

In diesem Artikel werden einige Anwendungsbeispiele für die Kohortenanalyse beschrieben.

## Anwendungsfall: Mobile-App-Interaktion

Angenommen Sie möchten herausfinden, wie Benutzer, die Ihre Anwendung installieren, im Laufe der Zeit damit interagieren. Installieren sie die Anwendung, benutzen sie aber nie? Benutzen sie die Anwendung eine Zeit lang und hören dann auf? Oder bleiben Sie die ganze Zeit dabei?

Sie können eine Kohortenanalyse über sechs Monate erstellen.

**Granularität**: Monatlich, von Januar 2015 bis Juni 2015

**Aufnahmemetrik**: Anwendungsinstallationen

**Rückkehrmetrik**: Sitzungen oder Starts

Personen zählen in *Monaten nicht als*, es sei denn, sie haben eine Sitzung oder starten die App zumindest. [!UICONTROL Kohortenanalyse] zeigt dann Nutzungsmuster an, bei denen *App-Installation* immer in Monat 0 erfolgt. Vielleicht stellen Sie fest, dass die Verwendung im zweiten Monat zurückgeht, unabhängig vom Zeitpunkt der Installation der Anwendung durch die Benutzer. (Für diejenigen Benutzer, die die App im Januar 2015 installiert haben, ist Monat 2 März 2015. Für Personen, die die App im Februar 2015 installiert haben, ist Monat 2 April 2015 usw.) Mit dieser Analyse können Sie im zweiten Monat nach der Installation der App eine E-Mail oder eine Push-Nachricht an alle Benutzer senden, um sie an die Verwendung der App zu erinnern.

## Anwendungsfall: Abonnement

Sie arbeiten bei Adobe.com und bieten ein kostenloses Creative Cloud-Abonnement an. Das Ziel besteht darin, dass die Benutzer ein Upgrade von der kostenlosen Version auf das 30-tägige Probe-Abo oder letztlich auf die zahlungspflichtige Version durchführen.

**Granularität**: Monatlich

**Aufnahmemetrik**: Download-Link

**Rückkehrmetrik**: Kauf der zahlungspflichtigen Creative Cloud

Mithilfe [!UICONTROL Kohortenanalyse] konnten Sie beispielsweise sehen, dass im ersten Monat nach der Installation zwischen 8 % und 10 % der kostenlosen Creative Cloud-Benutzenden ein Upgrade durchführen. Unabhängig davon, wann die Benutzer installiert haben. 12–15 % führen im zweiten Monat der Verwendung ein Upgrade durch. Danach lassen die Upgrades merklich nach: 4–5 % im dritten Monat, 3–4 % im vierten Monat und 1–2 % im fünften Monat.

Sie wollen in Monat drei keine potenziellen Kunden verlieren. Sie haben also eine E-Mail-Kampagne eingerichtet, die dazu dient, Mitte des dritten Monats eine Auswahl von Benutzern anzusprechen. Anbieten eines Gutscheins in Höhe von 50 $ für Benutzer, die noch kein Upgrade durchgeführt haben.

Schauen Sie einige Monate später wieder in Ihren Kohortenanalyseberichten vorbei. Bei Kohorten, die nach dem Start der Kampagne gebildet wurden, ist die Konversionsrate auf bezahlte Creative Cloud-Abonnements im dritten Monat von 4-5% auf 13-14% gestiegen. Dieser Anstieg der Konversionsrate resultiert in Hunderttausenden von Dollar pro Kohorte, für jede monatliche Kohorte, die ab diesem Zeitpunkt drei Monate erreicht.

## Anwendungsfall für komplexe Kohortensegmente

Eine große Hotelkette zielt auf mehrere Kundengruppen für Promotionen ab und verfolgt sie auf Grundlage der Leistung nach. Um die besten Gruppen von Benutzerkohorten zu identifizieren, die angesprochen werden sollen, sollten sehr spezifische Kohortengruppen erstellt werden. Mithilfe der erweiterten [!UICONTROL Einschluss] und [!UICONTROL Rückgabe]-Kriterien innerhalb der [!UICONTROL Kohorten]-Tabellen kann die Hotelkette genau die richtigen Kohortengruppierungen mit mehreren Metriken und Segmenten definieren. So kann die Hotelkette leistungsschwache Kundengruppen identifizieren, um Kunden mit Aktionen und Angeboten anzusprechen, um die Buchungen zu erhöhen.

## Anwendungsfall zur Annahme der App-Version

Ein großes Versicherungsunternehmen fördert die Kundenbindung durch die Nutzung seiner mobilen App. Da jedoch immer wieder neue Funktionen zur App hinzugefügt werden, ist es wichtig, dass die Kunden eine Aktualisierung auf die neueste App-Version durchführen. Sie können alle App-Versionen mithilfe der Kohorte [!UICONTROL Benutzerspezifische Dimension] gegeneinander analysieren und miteinander vergleichen, um zu sehen, auf welche Kunden mit welcher App-Version abgezielt werden sollte. Darüber hinaus können sowohl die Bindung als auch die Abwanderung verfolgt werden, um festzustellen, ob bestimmte App-Versionen Kunden davon abhalten, die App im Laufe der Zeit zu nutzen. Durch mobiles Messaging kann eine erneute Interaktion mit solchen Benutzern stattfinden, damit diese eine Aktualisierung auf die neueste Version durchführen, um die Vorteile der neuesten Funktionen nutzen zu können.

## Anwendungsfall zur Kampagnentreue

Ein internationales Medienunternehmen verwendet Zielgruppen-Kampagnen, um Benutzer auf die verschiedenen Plattformen zu leiten und so die Interaktion zu fördern. Die Werbeausgaben pro Plattform basieren auf der Kundeninteraktion und -bindung, daher sind erfolgreiche Kampagnen entscheidend für den Erfolg des Unternehmens. Sie verwenden die neue Funktion [!UICONTROL Benutzerdefinierte Dimension] Kohortentabellen in [!UICONTROL Kohortentabellen] um verschiedene Kampagnen nebeneinander zu vergleichen und so zu ermitteln, welche Kampagnen am effektivsten Benutzende gewinnen und binden können, um die Interaktion zu steigern. Anschließend kann festgestellt werden, welche Aspekte zum Erfolg einer Kampagne beitragen. Diese Erkenntnisse können dann auf andere Kampagnen angewendet werden, um die Interaktion auf den verschiedenen Plattformen zu fördern.

## Anwendungsfall einer Produkteinführung

Ein großer Kleidungseinzelhändler verfügt über viele spezifische Kundensegmente, durch die große Teile des Unternehmensumsatzes gefördert werden. Für jedes Segment werden spezifische Produkte unter Berücksichtigung des jeweiligen Segments entwickelt und hergestellt. Mit jedem Produkt-Launch soll identifiziert werden, wie das neue Produkt im Laufe der Zeit den Verkauf in verschiedenen Kohorten gefördert hat. Mit der neuen Einstellung [!UICONTROL Latenztabelle] in der [!UICONTROL Kohortenanalyse] können das Verhalten und der Umsatz eines bestimmten Kundensegments vor und nach der Markteinführung analysiert werden. Anhand dieser Informationen kann festgestellt werden, durch welche Produkte neue Umsätze generiert werden und welche bei der Kundschaft weniger beliebt sind.

## Anwendungsfall „Individuelle Treue – die meisten treuen Benutzenden“

Bei einer großen Fluggesellschaft hängt der Erfolg und Umsatz zu einem großen Teil von wiederkehrenden und treuen Kunden ab. In vielen Fällen machen treue Reisende den Großteil des Umsatzes aus und die Bindung dieser Kunden ist entscheidend für den langfristigen Erfolg. Oft kann es sich schwierig gestalten herauszufinden, welche die treuesten und beständigsten Kunden sind. Mithilfe der neuen Einstellung [!UICONTROL Rollierende Berechnung] in der [!UICONTROL Kohortenanalyse] kann die Fluggesellschaft jedoch Segmente treuer Kunden analysieren und herausfinden, welche Reisenden Monat für Monat zu Wiederholungskäufern wurden. Die Fluggesellschaft ist auch in der Lage, diese Reisenden mit Prämien und Vergünstigungen für ihre Treue anzusprechen. Darüber hinaus kann die Fluggesellschaft durch die Umstellung des Kohortentyps von Bindung auf Abwanderung feststellen, welche Kunden Monat für Monat keine Wiederholungskäufer sind, und diese Kunden mit Werbeaktionen ansprechen. So kann die Fluggesellschaft wieder mit diesen Kunden in Kontakt treten und sicherstellen, dass sie auch in Zukunft treue Kunden bleiben.
