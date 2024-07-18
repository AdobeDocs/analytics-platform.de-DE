---
title: Von Customer Journey Analytics verwendete Domänen
description: Wenn die Firewall Ihres Unternehmens IP-Adressen blockiert, die von Adobe stammen, verwenden Sie diese Liste, um Ihre Firewall-Einstellungen zu aktualisieren.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Von Customer Journey Analytics verwendete Domänen

Einige Firewall-Konfigurationen blockieren Domänen, auf die Customer Journey Analytics für die Produktoberfläche angewiesen ist. Sie können diese Liste von Domänen verwenden, um die Netzwerkeinstellungen Ihres Unternehmens zu ändern und den Produktzugriff innerhalb Ihres Unternehmens zuzulassen. Adobe empfiehlt, diese Domänen über die Firewall Ihres Unternehmens zuzulassen, um ein optimales Erlebnis zu erzielen.

| Technologie | Domain |
| --- | --- |
| Customer Journey Analytics-Domänen | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud-Domains

Zusätzlich zu den oben genannten Domänen ist die Adobe Experience Cloud für die Datenerfassung und den Export von Berichten auf mehrere Domänen angewiesen. Eine Liste der Domänen finden Sie unter [Domänen, die von der Adobe Experience Cloud verwendet werden](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains).

>[!MORELIKETHIS]
>
>[Von Customer Journey Analytics](ip-addresses.md) verwendete IP-Adressen
>
>[Von der Adobe Experience Cloud verwendete Domänen](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
