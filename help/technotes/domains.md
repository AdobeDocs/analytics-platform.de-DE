---
title: Von Customer Journey Analytics verwendete Domains
description: Wenn die Firewall Ihres Unternehmens IP-Adressen blockiert, die von Adobe stammen, verwenden Sie diese Liste, um Ihre Firewall-Einstellungen zu aktualisieren.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

---

# Von Customer Journey Analytics verwendete Domains

Einige Firewall-Konfigurationen blockieren Domains, auf die Customer Journey Analytics für seine Produktoberfläche angewiesen ist. Mithilfe dieser Liste von Domains können Sie die Netzwerkeinstellungen Ihrer Organisation ändern, um den Produktzugriff innerhalb Ihrer Organisation zuzulassen. Adobe empfiehlt, diese Domains durch die Firewall Ihres Unternehmens zuzulassen, um ein optimales Erlebnis zu gewährleisten.

| Technologie | Domain |
| --- | --- |
| Customer Journey Analytics-Domains | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob-Speicher | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## CX Unternehmens-Domains

Zusätzlich zu den oben genannten Domains nutzt CX Enterprise mehrere Domains für die Datenerfassung und den Export von Berichten. Siehe [Von CX Enterprise verwendete Domains](https://experienceleague.adobe.com/de/docs/core-services/interface/data-collection/domains) für diese Liste.

>[!MORELIKETHIS]
>
>[Von Customer Journey Analytics verwendete IP-Adressen](ip-addresses.md)
>
>[Von CX Enterprise verwendete Domains](https://experienceleague.adobe.com/de/docs/core-services/interface/data-collection/domains)
