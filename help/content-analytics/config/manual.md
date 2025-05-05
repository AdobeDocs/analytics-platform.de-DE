---
title: Manuelle Konfiguration der Inhaltsanalyse
description: Manuelles Konfigurieren der Inhaltsanalyse
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 3%

---

# Manuelle Konfiguration der Inhaltsanalyse

In diesem Artikel werden die manuellen Aktionen beschrieben, die zum Starten oder Stoppen der Datenerfassung einer Content Analytics-Konfiguration oder zum Bearbeiten Ihrer Content Analytics-Implementierung erforderlich sind.

Die folgenden manuellen Konfigurationsaktionen sind verfügbar:

## Starten der Datenerfassung

So starten Sie die Datenerfassung für eine implementierte Content Analytics-Konfiguration:

1. Folgen Sie dem [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"}. Die Bibliothek für die Tags-Eigenschaft mit Ihrer Content Analytics-Konfiguration wurde erfolgreich veröffentlicht.

1. [Installieren Sie ](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/environments/environments#installation) eingebetteten Code im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Veröffentlichungsumgebung, je nach Content Analytics.


## Beenden der Datenerfassung

So stoppen Sie die Datenerfassung für eine implementierte Content Analytics-Konfiguration:

1. Entfernen Sie den [eingebetteten Code](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/environments/environments) im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Produktionsumgebung, je nach Content Analytics.
1. [Löschen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview) der zugehörigen Tags-Eigenschaft für Ihre Content Analytics-Konfiguration.



## Datenerfassung ändern

Sie können einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des [Konfigurationsassistenten“ ](guided.md). Ändern Sie beispielsweise die Datenansicht oder aktivieren oder deaktivieren Sie Erlebnisse.

Sie verwenden die [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der Tags-Eigenschaft, die Ihrer Content Analytics-Konfiguration zugeordnet ist, um Änderungen an den folgenden Artefakten vorzunehmen:

* [Sandbox und Datenstrom](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Stellen Sie sicher, dass die Sandbox und der Datenstrom, die Sie in der Adobe Content Analytics-Erweiterung konfigurieren, bereits mit der [geführten Konfiguration](guided.md) in einem früheren Schritt für Content Analytics konfiguriert sind. Durch diese Konfiguration wird sichergestellt, dass alle erforderlichen Artefakte verfügbar sind.<br/><br/>Stellen Sie außerdem sicher, dass Aktualisierungen für Sandboxes oder Datenströme eine andere Content Analytics-Konfiguration, die für die Verwendung derselben Sandbox oder derselben Datenströme konfiguriert ist, nicht beeinträchtigen.
  >

* [Erlebniserfassung und -definition](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Sie können Erlebnisse aktivieren oder deaktivieren und die Kombinationen aus regulären Ausdrücken und Abfrageparametern bearbeiten, um zu bestimmen, wie Inhalte auf Ihrer Website gerendert werden.

* [Segmentierung von Ereignissen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Sie können reguläre Ausdrücke bearbeiten, um die Segmentierung von Seiten und Assets zu ändern.


Nachdem Sie Änderungen an der Adobe Content Analytics-Erweiterung vorgenommen haben, stellen Sie sicher, dass Sie [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} verwenden, um die Datenerfassung auf der Grundlage der vorgenommenen Änderungen zu starten.



>[!MORELIKETHIS]
>
>[Geführte Konfiguration](guided.md)
>[Übersicht über die Veröffentlichung von Datenerfassungs-Tags](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview)
>


## Versionierung

Wenn Sie Content Analytics-Erlebnisse erfassen möchten, sollten Sie die Versionierung implementieren, um sicherzustellen, dass neue Erlebnisse (Änderungen an Ihrer Web-Seite) ordnungsgemäß erfasst werden.

Um die Versionierung zu implementieren, fügen Sie den Seiten, die Sie als Erlebnisse betrachten, eine globale `adobe.getContentExperienceVersion` hinzu, die Sie analysieren möchten.

Die `adobe.getContentExperienceVersion` sollte eine Zeichenfolge als Wert zurückgeben, bei der es sich um eine beliebige Zeichenfolge handeln kann, um die Version zu identifizieren. Die Version wird an die [Erlebnis-ID-URL) ](/help/content-analytics/report/components.md#experience-metadata).

Wenn die Funktion nicht vorhanden ist oder kein Wert von der Funktion zurückgegeben wird, wird der Wert `NoVersion` als Standard verwendet.

### Beispiel

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
