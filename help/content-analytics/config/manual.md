---
title: Manuelle Konfiguration von Content Analytics
description: Manuelles Konfigurieren von Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 100%

---

# Manuelle Konfiguration von Content Analytics

In diesem Artikel werden die manuellen Aktionen beschrieben, die zum Starten oder Stoppen der Datenerfassung einer Content Analytics-Konfiguration oder zum Bearbeiten Ihrer Content Analytics-Implementierung erforderlich sind.

Die folgenden manuellen Konfigurationsaktionen sind verfügbar:

## Starten der Datenerfassung

So starten Sie die Datenerfassung für eine implementierte Content Analytics-Konfiguration:

1. Folgen Sie dem [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"}. Veröffentlichen Sie die Bibliothek für die Tags-Eigenschaft, die Ihre Content Analytics-Konfiguration enthält.

1. [Installieren](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/environments/environments#installation) Sie den eingebetteten Code im `<head>`-Element der Seiten in Ihrer Entwicklungs-, Staging- oder Veröffentlichungsumgebung, die Content Analytics unterliegt.


## Stoppen der Datenerfassung

So stoppen Sie die Datenerfassung für eine implementierte Content Analytics-Konfiguration:

1. Entfernen Sie den [eingebetteten Code](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/environments/environments) im `<head>`-Element der Seiten in Ihrer Entwicklungs-, Staging- oder Produktionsumgebung, die Content Analytics unterliegt.
1. [Löschen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview) Sie die zugehörige Tags-Eigenschaft für Ihre Content Analytics-Konfiguration.



## Ändern der Datenerfassung

Sie können einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des [Assistenten für geführte Konfigurationen](guided.md) vornehmen. Ändern Sie beispielsweise die Datenansicht oder aktivieren bhw. deaktivieren Sie Erlebnisse.

Verwenden Sie die [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview) in der Tags-Eigenschaft, die Ihrer Content Analytics-Konfiguration zugeordnet ist, um Änderungen an den folgenden Artefakten vorzunehmen:

* [Sandbox und Datenstrom](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Stellen Sie sicher, dass Sandbox und Datenstrom, die mit der Adobe Content Analytics-Erweiterung konfiguriert werden sollen, bereits zuvor mithilfe der [geführten Konfiguration](guided.md) für Content Analytics eingerichtet wurden. Durch diese Konfiguration wird sichergestellt, dass alle erforderlichen Artefakte verfügbar sind.<br/><br/>Stellen Sie außerdem sicher, dass Aktualisierungen für Sandboxes oder Datenströme keine andere Content Analytics-Konfiguration beeinträchtigen, die für dieselben Sandboxes oder Datenströme konfiguriert ist.
  >

* [Erlebniserfassung und -definition](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Sie können Erlebnisse aktivieren oder deaktivieren und Kombinationen aus regulären Ausdrücken und Abfrageparametern bearbeiten, um zu bestimmen, wie Inhalte auf Ihrer Website gerendert werden.

* [Ereignissegmentierung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Sie können reguläre Ausdrücke bearbeiten, um die Art und Weise zu ändern, wie Sie Seiten und Assets segmentieren.


Achten Sie nach Änderungen an der Adobe Content Analytics-Erweiterung darauf, den [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} zu verwenden, um die Datenerfassung auf Grundlage der durchgeführten Änderungen zu starten.



>[!MORELIKETHIS]
>
>[Geführte Konfiguration](guided.md)
>>[Datenerfassung – Überblick über Tags und Veröffentlichungen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview)
>


## Versionierung

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

## Identitäten

Content Analytics kann Identitäten wie folgt verarbeiten:

* ECID wird im Abschnitt „`identityMap`“ des Content Analytics-Schemas automatisch gefüllt.
* Wenn Sie andere Identitätswerte in der `identityMap` benötigen, müssen Sie diese Werte im `onBeforeEventSend`-Rückruf innerhalb der Web SDK-Erweiterung festlegen.
* Feldbasiertes Stitching wird nicht unterstützt, da das Schema systemeigen ist. Sie können dem Schema also kein weiteres Feld zur Unterstützung von feldbasiertem Stitching hinzufügen.


Um sicherzustellen, dass Content Analytics-Identitätsdaten und Adobe Experience Platform Web SDK-Identitätsdaten auf Feldebene korrekt zugeordnet werden, müssen Sie Änderungen am Web SDK-Rückruf [on before event send](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"} vornehmen.

1. Navigieren Sie zu Ihrer **[!UICONTROL Tags]**-Eigenschaft, die die Adobe Experience Platform Web SDK-Erweiterung und die Adobe Content Analytics-Erweiterung enthält.
1. Wählen Sie ![Stecker](/help/assets/icons/Plug.svg) **[!UICONTROL Erweiterungen]** aus.
1. Wählen Sie die Erweiterung **[!UICONTROL Adobe Experience Platform Web SDK]** aus.
1. Wählen Sie **[!UICONTROL Konfigurieren]** aus.
1. Scrollen Sie im Abschnitt **[!UICONTROL SDK-Instanzen]** nach unten zu **[!UICONTROL Datenerfassung]** - **[!UICONTROL On before event send callback]**.

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Wählen Sie **[!UICONTROL &lt;/> Provide on before event send callback code]** aus.
1. Fügen Sie folgenden Code hinzu:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**, um den Code zu speichern.
1. Klicken Sie auf **[!UICONTROL Speichern]**, um die Erweiterung zu speichern.
1. [Veröffentlichen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview) Sie die Änderungen an Ihrer Tags-Eigenschaft.





