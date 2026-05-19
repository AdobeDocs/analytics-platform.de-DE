---
title: Von Customer Journey Analytics verwendete Domains
description: Wenn die Firewall Ihres Unternehmens IP-Adressen blockiert, die von Adobe stammen, verwenden Sie diese Liste, um Ihre Firewall-Einstellungen zu aktualisieren.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
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
