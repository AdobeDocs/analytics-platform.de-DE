---
title: Manuelle Konfiguration von Content Analytics
description: Manuelles Konfigurieren von Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Manuelle Konfiguration von Content Analytics

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}

In diesem Artikel werden die manuellen Aktionen beschrieben, die zum Aktivieren oder Deaktivieren einer Content Analytics-Konfiguration oder zum Bearbeiten Ihrer Content Analytics-Implementierung erforderlich sind.

Die folgenden manuellen Konfigurationsaktionen sind verfügbar:

## Aktivieren

Um eine neue Konfiguration oder Änderungen an einer vorhandenen Konfiguration zu aktivieren, müssen Sie [ zugehörige Tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}Eigenschaft veröffentlichen. Nur wenn Sie Ihre Content Analytics-Tag-Eigenschaft veröffentlichen, werden Content Analytics-Daten für die Domains, Erlebnisse und Assets erfasst, die Sie konfiguriert haben.


## Deaktivieren

Um die Erfassung von Inhaltsanalysedaten zu deaktivieren, [ Sie die Veröffentlichung ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} zugehörigen Tag-Eigenschaft für Ihre Inhaltsanalysekonfiguration auf.



## Ändern

Im Allgemeinen sollten Sie den [Assistenten für geführte Konfigurationen](guided.md) verwenden, um Änderungen an Ihrer Implementierung vorzunehmen.

Alternativ können Sie die Adobe Content Analytics-Erweiterung in der Ihrer Content Analytics-Konfiguration zugeordneten Tag-Eigenschaft verwenden, um Änderungen an den folgenden Artefakten vorzunehmen:

* [Sandbox und Datenstrom](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Sie müssen sicherstellen, dass die Sandbox und der Datenstrom, die Sie in der Adobe Content Analytics-Erweiterung konfigurieren, bereits mit der [geführten Konfiguration](guided.md) zu einem früheren Zeitpunkt für Content Analytics konfiguriert wurden. Diese Konfiguration stellt sicher, dass alle erforderlichen Artefakte verfügbar sind.<br/><br/>Sie müssen außerdem sicherstellen, dass Ihre Aktualisierungen für Sandboxes oder Datenströme eine andere Content Analytics-Konfiguration, die für die Verwendung derselben Sandbox oder derselben Datenströme konfiguriert ist, nicht beeinträchtigen.
  >

* [Ereignisfilterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  Sie können reguläre Ausdrücke bearbeiten, um zu ändern, wie Sie Seiten und Assets filtern.


Nachdem Sie Änderungen an der Adobe Content Analytics-Erweiterung vorgenommen haben, stellen Sie sicher, dass Sie [ Änderungen ](#activate) (aktivieren).



>[!MORELIKETHIS]
>
>[Geführte Konfiguration](guided.md)
>[Übersicht über die Veröffentlichung von Datenerfassungs-Tags](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>