---
title: Manuelle Konfiguration von Content Analytics
description: Erfahren Sie, wie Sie Content Analytics manuell konfigurieren.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: b8b0237a092b37d28bec56bba05c30a853097d4f
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 62%

---


# Manuelle Konfiguration von Content Analytics

In diesem Artikel werden die manuellen Aktionen beschrieben, die zum Starten oder Stoppen der Datenerfassung einer Content Analytics-Konfiguration oder zum Bearbeiten Ihrer Content Analytics-Implementierung erforderlich sind.

Die folgenden manuellen Konfigurationsaktionen sind verfügbar:

## Starten der Datenerfassung

So starten Sie die Datenerfassung für eine implementierte Content Analytics-Konfiguration:

1. Folgen Sie dem [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"}. Die Bibliothek für die Tags-Eigenschaften, die Ihre Content Analytics-Konfiguration enthalten, wurde erfolgreich veröffentlicht.

1. Basierend auf den von Ihnen konfigurierten Kanälen:

   * Für **web**: [Installieren](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/environments/environments#installation) den eingebetteten Code im `<head>` der Seiten in Ihrer Entwicklungs-, Staging- oder Veröffentlichungsumgebung, abhängig von Content Analytics.
   * Für **mobile**: Im lösungsspezifischen [Adobe Content Analytics-Erweiterungshandbuch](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) in der [Dokumentation zu Experience Platform Mobile SDK ](https://developer.adobe.com/client-sdks/home/) Sie, wie Sie Ihre Mobile App für Content Analytics konfigurieren und instrumentieren.

## Stoppen der Datenerfassung

So stoppen Sie die Datenerfassung für eine implementierte Content Analytics-Konfiguration basierend auf den von Ihnen konfigurierten Kanälen:

* Für **web**:

   1. Entfernen Sie den [eingebetteten Code](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/environments/environments) im `<head>`-Element der Seiten in Ihrer Entwicklungs-, Staging- oder Produktionsumgebung, die Content Analytics unterliegt.
   1. Löschen Sie die zugehörige Web-Tags-Eigenschaft für Ihre Content Analytics-Konfiguration.

* Für **mobile**:

   1. Entfernen Sie die [Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)Erweiterung aus Ihrer App.
   1. Löschen Sie die zugehörige Eigenschaft für mobile Tags für Ihre Content Analytics-Konfiguration.

Folgen Sie [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} um die Änderungen anzuwenden.


## Ändern der Datenerfassung

Sie können einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des [Assistenten für geführte Konfigurationen](guided.md) vornehmen. Ändern Sie beispielsweise die Datenansicht oder aktivieren bhw. deaktivieren Sie Erlebnisse.


### Web

Sie verwenden die [Adobe Content Analytics-Web-](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der Tags-Eigenschaft, die Ihrer Content Analytics-Konfiguration zugeordnet ist, um Änderungen an den folgenden Artefakten vorzunehmen:

* [Sandbox und Datenstrom](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Stellen Sie sicher, dass Sandbox und Datenstrom, die mit der Adobe Content Analytics-Erweiterung konfiguriert werden sollen, bereits zuvor mithilfe der [geführten Konfiguration](guided.md) für Content Analytics eingerichtet wurden. Durch diese Konfiguration wird sichergestellt, dass alle erforderlichen Artefakte verfügbar sind.<br/><br/>Stellen Sie außerdem sicher, dass Aktualisierungen für Sandboxes oder Datenströme keine andere Content Analytics-Konfiguration beeinträchtigen, die für dieselben Sandboxes oder Datenströme konfiguriert ist.
  >

* [Erlebniserfassung und -definition](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Sie können Erlebnisse aktivieren oder deaktivieren und Kombinationen aus regulären Ausdrücken und Abfrageparametern bearbeiten, um zu bestimmen, wie Inhalte auf Ihrer Website gerendert werden.

* [Ereignissegmentierung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Sie können reguläre Ausdrücke bearbeiten, um die Art und Weise zu ändern, wie Sie Seiten und Assets segmentieren.


Nachdem Sie Änderungen an der Adobe Content Analytics-Web-Erweiterung vorgenommen haben, verwenden Sie den [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} um mit der Datenerfassung zu beginnen.


### Mobile

Sie verwenden die [Adobe Content Analytics Mobile-Erweiterung](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) in der mit Ihrer Content Analytics-Konfiguration verknüpften Tags-Eigenschaft, um zusätzliche Änderungen vorzunehmen.

Nachdem Sie Änderungen an der Adobe Content Analytics-Web-Erweiterung vorgenommen haben, verwenden Sie den [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} um mit der Datenerfassung zu beginnen.


## Versionierung

>[!NOTE]
>
>Dieser Abschnitt gilt nur für Content Analytics für den Webkanal.


Wenn Sie Content Analytics-Erlebnisse erfassen möchten, sollten Sie die Versionierung implementieren, um sicherzustellen, dass neue Erlebnisse (Änderungen an Ihrer Web-Seite) ordnungsgemäß erfasst werden.

Um die Versionierung zu implementieren, fügen Sie eine globale `adobe.getContentExperienceVersion`-Funktion auf den Seiten hinzu, die Sie als Erlebnisse betrachten und die Sie analysieren möchten.

Die Funktion `adobe.getContentExperienceVersion` sollte eine Zeichenfolge als Wert zurückgeben, bei der es sich um eine beliebige Zeichenfolge handeln kann, die Sie wählen, um die Version zu identifizieren. Die Version wird an die [URL der Erlebnis-ID](/help/content-analytics/report/components.md#experience-metadata) angehängt.

Wenn die Funktion nicht vorhanden ist oder kein Wert von der Funktion zurückgegeben wird, wird standardmäßig der Wert `NoVersion` verwendet.

### Beispiel

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

>[!MORELIKETHIS]
>
>[Geführte Konfiguration](guided.md)
>[Datenerfassung – Überblick über Tags und Veröffentlichungen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview)
>
