---
title: Von Customer Journey Analytics verwendete Domains
description: Wenn die Firewall Ihres Unternehmens IP-Adressen blockiert, die von Adobe stammen, verwenden Sie diese Liste, um Ihre Firewall-Einstellungen zu aktualisieren.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Von Customer Journey Analytics verwendete Domains

Einige Firewall-Konfigurationen blockieren Domains, die von Customer Journey Analytics für die Produktoberfläche benötigt werden. Mithilfe dieser Liste von Domains können Sie die Netzwerkeinstellungen Ihrer Organisation ändern, um den Produktzugriff innerhalb Ihrer Organisation zuzulassen. Adobe empfiehlt, diese Domains durch die Firewall Ihres Unternehmens laufen zu lassen, um ein optimales Erlebnis zu gewährleisten.

| Technologie | Domain |
| --- | --- |
| Customer Journey Analytics-Domains | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud-Domains

Zusätzlich zu den oben genannten Domains nutzt die Adobe Experience Cloud mehrere Domains für die Datenerfassung und den Export von Berichten. Siehe [Von der Adobe Experience Cloud verwendete Domains](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) für diese Liste.

>[!MORELIKETHIS]
>
>[Von Customer Journey Analytics verwendete IP-Adressen](ip-addresses.md)
>
>[Von der Adobe Experience Cloud verwendete Domains](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
