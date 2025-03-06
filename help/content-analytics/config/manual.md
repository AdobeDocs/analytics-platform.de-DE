---
title: Manuelle Konfiguration von Content Analytics
description: Manuelles Konfigurieren von Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 1%

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

So aktivieren Sie eine neue Konfiguration oder Änderungen, die Sie an einer vorhandenen Konfiguration vorgenommen haben:

1. Sie müssen den [Publishing-Ablauf“ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Nur wenn Sie die Bibliothek für die Tag-Eigenschaft mit Ihrer Inhaltsanalysekonfiguration erfolgreich veröffentlicht haben, werden Inhaltsanalysedaten für die Domains, Erlebnisse und Assets erfasst, die Sie konfiguriert haben.

1. Sie müssen [ Einbettungs](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)Code je nach Inhaltsanalyse im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Veröffentlichungsumgebung installieren.


## Deaktivieren

So deaktivieren Sie die Erfassung von Inhaltsanalysedaten:

1. Entfernen Sie den [Einbettungs](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)Code vorbehaltlich Inhaltsanalysen im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Produktionsumgebung.
1. [Löschen](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) der zugehörigen Tag-Eigenschaft für Ihre Content Analytics-Konfiguration.



## Ändern

Im Allgemeinen sollten Sie den [Assistenten für geführte Konfigurationen](guided.md) verwenden, um Änderungen an Ihrer Implementierung vorzunehmen.

Alternativ können Sie die [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der Ihrer Content Analytics-Konfiguration zugeordneten Tag-Eigenschaft verwenden, um Änderungen an den folgenden Artefakten vorzunehmen:

* [Sandbox und Datenstrom](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Sie müssen sicherstellen, dass die Sandbox und der Datenstrom, die Sie in der Adobe Content Analytics-Erweiterung konfigurieren, bereits mit der [geführten Konfiguration](guided.md) zu einem früheren Zeitpunkt für Content Analytics konfiguriert wurden. Diese Konfiguration stellt sicher, dass alle erforderlichen Artefakte verfügbar sind.<br/><br/>Sie müssen außerdem sicherstellen, dass Ihre Aktualisierungen für Sandboxes oder Datenströme eine andere Content Analytics-Konfiguration, die für die Verwendung derselben Sandbox oder derselben Datenströme konfiguriert ist, nicht beeinträchtigen.
  >

* [Ereignisfilterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Sie können reguläre Ausdrücke bearbeiten, um zu ändern, wie Sie Seiten und Assets filtern.


Nachdem Sie Änderungen an der Adobe Content Analytics-Erweiterung vorgenommen haben, stellen Sie sicher, dass Sie [Publishing-Ablauf](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} verwenden, um Ihre Änderungen zu aktivieren.



>[!MORELIKETHIS]
>
>[Geführte Konfiguration](guided.md)
>[Übersicht über die Veröffentlichung von Datenerfassungs-Tags](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versionierung

Wenn Sie eine Versionierung Ihrer Content Analytics-Erlebnisse benötigen, müssen Sie auf den Seiten, die Sie als Erlebnisse betrachten, die Sie analysieren möchten, eine globale `adobe.getContentExperienceVersion` hinzufügen.

Die `adobe.getContentExperienceVersion` sollte eine Zeichenfolge als Wert zurückgeben, wobei es sich um alles handeln kann, was Sie zum Identifizieren der Version auswählen. Die Version wird an die Experience ID-URL angehängt.

Wenn die Funktion nicht vorhanden ist oder kein Wert von der Funktion zurückgegeben wird, wird der Wert `NoVersion` als Standard verwendet.

### Beispiel

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
