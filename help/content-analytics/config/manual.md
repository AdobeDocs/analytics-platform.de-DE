---
title: Manuelle Konfiguration von Content Analytics
description: Manuelles Konfigurieren von Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 1%

---

# Manuelle Konfiguration von Content Analytics

{{draft-aca}}

{{release-limited-testing}}

In diesem Artikel werden die manuellen Aktionen beschrieben, die zum Aktivieren oder Deaktivieren einer Content Analytics-Konfiguration oder zum Bearbeiten Ihrer Content Analytics-Implementierung erforderlich sind.

Die folgenden manuellen Konfigurationsaktionen sind verfügbar:

## Aktivieren

So aktivieren Sie eine neue Konfiguration oder Änderungen, die Sie an einer vorhandenen Konfiguration vorgenommen haben:

1. Sie müssen den [Publishing-Ablauf“ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Die Bibliothek für die Tags-Eigenschaft mit Ihrer Content Analytics-Konfiguration wurde erfolgreich veröffentlicht.

1. Sie müssen [ eingebetteten ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Veröffentlichungsumgebung installieren (je nach Content Analytics).


## Deaktivieren

So deaktivieren Sie die Erfassung von Inhaltsanalysedaten:

1. Entfernen Sie den [eingebetteten Code](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Produktionsumgebung, je nach Content Analytics.
1. [Löschen](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) der zugehörigen Tags-Eigenschaft für Ihre Content Analytics-Konfiguration.



## Ändern

Sie können einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des [Konfigurationsassistenten“ ](guided.md). Ändern Sie beispielsweise die Datenansicht.

Sie verwenden die [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der Tags-Eigenschaft, die Ihrer Content Analytics-Konfiguration zugeordnet ist, um Änderungen an den folgenden Artefakten vorzunehmen:

* [Sandbox und Datenstrom](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Stellen Sie sicher, dass die Sandbox und der Datenstrom, die Sie in der Adobe Content Analytics-Erweiterung konfigurieren, bereits mit der [geführten Konfiguration](guided.md) in einem früheren Schritt für Content Analytics konfiguriert sind. Durch diese Konfiguration wird sichergestellt, dass alle erforderlichen Artefakte verfügbar sind.<br/><br/>Stellen Sie außerdem sicher, dass Aktualisierungen für Sandboxes oder Datenströme eine andere Content Analytics-Konfiguration, die für die Verwendung derselben Sandbox oder derselben Datenströme konfiguriert ist, nicht beeinträchtigen.
  >

* [Erlebniserfassung und -definition](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Sie können den regulären Ausdruck bearbeiten, um zu ändern, wie Sie .

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

Die `adobe.getContentExperienceVersion` sollte eine Zeichenfolge als Wert zurückgeben, bei der es sich um eine beliebige Zeichenfolge handeln kann, um die Version zu identifizieren. Die Version wird an die [Erlebnis-ID-URL) ](/help/content-analytics/report/components.md#experience-metadata).

Wenn die Funktion nicht vorhanden ist oder kein Wert von der Funktion zurückgegeben wird, wird der Wert `NoVersion` als Standard verwendet.

### Beispiel

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
