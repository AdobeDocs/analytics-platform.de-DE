---
title: AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector
description: Hier erfahren Sie, wie der Analytics-Quell-Connector mit Adobe Analytics-Identitätsfeldern umgeht.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '503'
ht-degree: 100%

---

# AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector

Adobe Analytics-Daten enthalten mehrere Identitätsfelder. Drei wichtige Identitätsfelder werden vom [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) besonders behandelt: AAID, ECID, AACUSTOMID.

## AAID

Die Adobe Analytics-ID (AAID) ist die primäre Gerätekennung in Adobe Analytics und ist garantiert bei jedem Ereignis vorhanden, das über den Analytics-Quell-Connector weitergeleitet wird. AAID wird manchmal als „veraltete Analytics-ID“ oder `s_vi` Cookie-ID bezeichnet. Eine AAID wird jedoch auch dann erstellt, wenn das `s_vi`-Cookie gar nicht vorhanden ist. AAID wird durch die Spalten `post_visid_high/post_visid_low` in [Adobe Analytics-Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de#columns%2C-descriptions%2C-and-data-types) dargestellt.

Im Analytics-Quell-Connector wird AAID in `HEX(post_visid_high) + "-" + HEX(post_visid_low)` umgewandelt. Das Feld „AAID“ für ein bestimmtes Ereignis enthält eine einzelne Identität, die einen von mehreren verschiedenen Typen besitzen kann, wie unter [Reihenfolge der Vorgänge für Analytics-IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=de%5B%5D) beschrieben. (Innerhalb einer gesamten Report Suite kann AAID eine Mischung aus Typen über Ereignisse hinweg enthalten. Der Typ für jedes Ereignis wird in der Spalte `post_visid_type` in Analytics-Daten-Feeds angezeigt.) Siehe auch die [Datenspaltenreferenz](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de).

## ECID

ECID (Experience Cloud-ID), manchmal auch als MCID (Marketing Cloud-ID) bezeichnet, ist ein separates Gerätekennungsfeld, das in Adobe Analytics ausgefüllt wird, wenn Analytics mithilfe des [Identity Service von Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=de) implementiert wird. ECID wird in den Adobe Analytics-Daten-Feeds durch die Spalte `mcvisid` dargestellt.

Wenn eine ECID für ein Ereignis vorhanden ist, kann AAID auf ECID basieren, je nachdem, ob die Analytics-Variable [Nachfrist](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=de) konfiguriert ist oder nicht. Siehe auch [Anforderungen an die Analytics- und Experience Cloud-ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=de).

## AACUSTOMID

AACUSTOMID ist ein separates Kennungsfeld, das in Adobe Analytics auf der Grundlage der Verwendung der Variable `s.VisitorID` in der Analytics-Implementierung ausgefüllt wird. AACUSTOMID wird in Adobe Analytics-Daten-Feeds durch die Spalte `cust_visid` dargestellt. Wenn AACUSTOMID vorhanden ist, basiert AAID auf AACUSTOMID. (AACUSTOMID überträgt alle anderen Kennungen, wie durch die Reihenfolge der oben genannten Vorgänge definiert.)

## Behandlung dieser Identitäten durch den Analytics-Quell-Connector

Der Analytics-Quell-Connector übergibt diese Identitäten in XDM-Form an Adobe Experience Platform als:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Diese Felder sind nicht als Identitäten markiert. Stattdessen werden dieselben Identitäten als Schlüssel-Wert-Paare wie folgt in die **_identityMap_** von XDM kopiert:

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

Die Elemente in den Klammern &lt;> stellen Positionen dar, an denen tatsächliche Werte erscheinen würden.

Innerhalb der identityMap:

* Wenn ECID vorhanden ist, wird sie als primäre Identität für das Ereignis markiert. Beachten Sie, dass in diesem Fall AAID gemäß der obigen Diskussion auf ECID basieren kann.
Andernfalls wird AAID als primäre Identität für das Ereignis markiert.
* AACUSTOMID wird nie als primäre ID für das Ereignis markiert. Wenn jedoch AACUSTOMID vorhanden ist, basiert AAID gemäß der obigen Diskussion auf AACUSTOMID.

## Customer Journey Analytics und primäre ID

Für Customer Journey Analytics ist die Definition der primären ID nur dann wichtig, wenn Sie die primäre ID als Personen-ID verwenden. Dies ist jedoch nicht zwingend erforderlich. Sie können auch eine andere Identitätsspalte als Personen-ID auswählen.
