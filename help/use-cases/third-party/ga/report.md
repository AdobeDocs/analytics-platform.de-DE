---
title: Bericht zu Google Analytics-Daten
description: Zeigt nützliche Berichte zu Google Analytics-Daten in Customer Journey Analytics an
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:08.813Z'
TQID: 'https://experienceleague.adobe.com/dRY1wvTEzrhnNsqE-fJq9DyzOAEKTygzSkVb8r6huoM'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 704
ht-degree: 83%

---

# Bericht zu Google Analytics-Daten

Sobald Daten in Customer Journey Analytics zur Verfügung stehen, bieten die folgenden Beispiele nützliche Szenarien für das Reporting über diese Daten. Eine umfassende Übersicht der Entsprechungen von GA4-Berichten in Customer Journey Analytics finden Sie unter [GA4-Berichte in Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

## Visualisieren von Web-Daten und App-Daten als kombinierte Datensätze

Dieses Venn-Diagramm zeigt die Überschneidung der Benutzer auf Ihrer Website (aus Ihren Google Analytics-Daten) und in Ihrer mobilen App (aus Ihren Firebase-Daten) sowie in Ihrem Callcenter. Sie können auch die leistungsstärksten Produkte sehen – nicht nur im Web, sondern auch in der mobilen App. Mithilfe einer berechneten Kennzahl können sogar die Gesamteinnahmen aus beiden ermittelt werden. Beachten Sie, dass die Top-Produkte eine andere Geschichte erzählen, wenn Sie sich den kombinierten Umsatz ansehen. Ohne die kombinierten Datensätze hätten Sie nie gewusst, dass die „Twill Cap“ eine solch starke Leistung erbringt.

![Kombinierte Datensätze](../../assets/combined-datasets.png)

## Identifizieren Sie die Gründe für die Anrufe und reduzieren Sie das Anrufvolumen.

Es kann ein Trend für die im Callcenter verbrachte Zeit über die letzten zwei Monate ermittelt werden, um das Aufrufvolumen zu bestimmen. Das folgende Beispiel zeigt den Trend dieser Daten über die letzten zwei Monate. Das folgende Beispiel zeigt einen zunehmenden Trend, der sich auf die Organisationskosten auswirken kann.

![Anrufvolumen](../../assets/call-volume.png)

Die Verwendung der Dimension „Anrufgrund“ kann Hinweise darauf geben, wie das Web-Erlebnis verbessert werden kann, um zu verhindern, dass Personen überhaupt anrufen. Das obige Beispiel zeigt, dass das Thema „Beschädigtes Produkt“ eine durchschnittliche Anrufzeit von fast 3 Minuten pro Anruf hat. Dies gibt Ihrem Unternehmen eine präzise Möglichkeit, das Kundenerlebnis zu verbessern und die Kosten für das Callcenter zu senken.

Sie können sehen, welche Produkte die meisten Aufrufe an Ihr Callcenter verursachen und wie viele Kunden diese Aufrufe getätigt haben. Das Blasendiagramm zeigt, dass 20.000 Personen anriefen, mehr als 4 Stunden und 30 Minuten damit verbrachten, 33 Stück des Produkts „Herren T-Shirt mit kurzen Ärmeln“ zurückzugeben.

![Grund für den Anruf](../../assets/call-reason.png)

Bei Anwendung der Dimensionsaufschlüsselung „Anrufgrund“ zeigt das Beispiel eine Dimensionsposition „Beschädigtes Produkt“. Der nächste Schritt besteht darin, sich mit der Abteilung der Qualitätskontrolle in Verbindung zu setzen und herauszufinden, warum die Kunden beschädigte T-Shirts erhalten haben.

Man kann sich ansehen, welche Website-Seiten zu Anrufen im Callcenter geführt haben. Mit diesem Bericht kann man feststellen, wo auf der Website weniger optimale Erfahrungen gemacht wurden, und den Produktmanagern helfen, diese Herausforderungen zu lösen. Im folgenden Beispiel wird eine berechnete Metrik mit einem Teilnahme-Attributionsmodell verwendet, um die Daten nur in Sitzungen zu filtern, die mit einem Callcenter-Aufruf endeten.

Das folgende Beispiel zeigt, dass die Seiten „Warenkorb“ und „Checkout-Informationen“ die meisten Anrufe verursachen.

![Beitragende Seiten](../../assets/contributing-pages.png)

Anhand der Kohortentabelle ist ersichtlich, wie lange es in der Regel dauert, bis die Benutzenden nach dem Besuch der Website das Callcenter anrufen. Das folgende Beispiel zeigt, dass die durchschnittliche Zeit für diesen Beispieldatensatz zwischen drei und vier Wochen liegt.

![Kohorte](../../assets/cohort.png)

## Erweiterte Marketing-Attribution verwenden

Mit Customer Journey Analytics können Sie ausgefeilte Attributionsmodelle für kanalübergreifende Daten verwenden. Im folgenden Beispiel sehen Sie einen Vergleich der Anwendung von Erstkontakt, Letztkontakt, U-förmig und algorithmischer Attribution von Umsatz mit den Channel Grouping-Dimensionen von Google Analytics.

![Marketing-Attribution](../../assets/mktg-attribution.png)

Mithilfe einer berechneten Metrik können Sie diese Attribution auf Ihren Web-Umsatz und den Umsatz mit Mobile Apps anwenden und sogar die Produktretouren abziehen. Infolgedessen können Sie für jeden Marketing-Kanal den tatsächlichen Nettoumsatz sehen.

![Berechnete Kennzahl](../../assets/calc-metric.png)

Mit Attribution können Sie Ihre Daten auch segmentieren. Sie können die Attribution auch für bestimmte Benutzergruppen anzeigen, z. B. nur für Benutzer, die mehr als ein Gerät verwenden.

![Segment](../../assets/filter.png)

Sie können Ihren im Web und über Mobile Apps generierten Umsatz auch Ihren Google-Anzeigeninhalten zuordnen. In unserem Beispiel erzielte dieser Datensatz mehr Umsatz durch die Mobile App mit den Online-Google-Anzeigen als durch das Internet. Wenn Sie Anzeigen nach Web- und Mobile-App-Umsatz sortieren, erhalten Sie ein anderes Bild davon, welches Ihre leistungsstärksten Google-Anzeigen waren.

![Google-Anzeige](../../assets/google-ad.png)

Durch die Kombination von Datensätzen in Customer Journey Analytics können Sie in diesem Beispiel sehen, dass Online-Anzeigen Auswirkungen auf Produkte hatten, die in Ihrer Mobile App gekauft wurden. In der folgenden Visualisierung sehen Sie, dass der Umsatz durch Google Ads über die Mobile App im Vergleich zum Internet allein zusätzliche 14.000 $ bis 15.000 $ ausmacht.

![Google-Anzeige 2](../../assets/google-ad2.png)
