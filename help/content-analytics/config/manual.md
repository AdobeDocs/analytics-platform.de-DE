---
title: Manuelle Konfiguration der Inhaltsanalyse
description: Manuelles Konfigurieren der Inhaltsanalyse
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 60%

---

# Manuelle Konfiguration der Inhaltsanalyse

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

* [Segmentierung von Ereignissen](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Sie können reguläre Ausdrücke bearbeiten, um die Segmentierung von Seiten und Assets zu ändern.


Achten Sie nach Änderungen an der Adobe Content Analytics-Erweiterung darauf, den [Publishing-Ablauf](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} zu verwenden, um die Datenerfassung auf Grundlage der durchgeführten Änderungen zu starten.



>[!MORELIKETHIS]
>
>[Geführte Konfiguration](guided.md)
>>[Datenerfassung – Überblick über Tags und Veröffentlichungen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview)
>


## Versionierung

Wenn Sie Content Analytics-Erlebnisse erfassen möchten, sollten Sie die Versionierung implementieren, um sicherzustellen, dass neue Erlebnisse (Änderungen an Ihrer Web-Seite) ordnungsgemäß erfasst werden.

Um die Versionierung zu implementieren, fügen Sie den Seiten, die Sie als Erlebnisse betrachten, eine globale `adobe.getContentExperienceVersion` hinzu, die Sie analysieren möchten.

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

* ECID wird automatisch im `identityMap` Teil des Content Analytics-Schemas ausgefüllt.
* Wenn Sie andere Identitätswerte in der `identityMap` benötigen, müssen Sie diese Werte im `onBeforeEventSend`-Callback innerhalb der Web SDK-Erweiterung festlegen.
* Feldbasiertes Stitching wird nicht unterstützt, da das Schema in Systembesitz ist. Sie können dem Schema also kein weiteres Feld hinzufügen, um feldbasiertes Stitching zu unterstützen


Um sicherzustellen, dass Content Analytics-Identitätsdaten und Adobe Experience Platform Web SDK-Daten-Identitätsdaten auf Feldebene korrekt zugeordnet sind, müssen Sie Änderungen am Web SDK [on vor dem Ereignisversand vornehmen](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"} Callback.

1. Navigieren Sie zu Ihrer **[!UICONTROL Tags]**-Eigenschaft, die die Adobe Experience Platform Web SDK-Erweiterung und die Adobe Content Analytics-Erweiterung enthält.
1. Wählen Sie ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensions]** aus.
1. Wählen Sie die Erweiterung **[!UICONTROL Adobe Experience Platform Web SDK]** aus.
1. Wählen Sie **[!UICONTROL Konfigurieren]** aus.
1. Scrollen Sie im Abschnitt **[!UICONTROL SDK]** Instanzen nach unten zu **[!UICONTROL Datenerfassung]** - **[!UICONTROL Ein vor Ereignisversand-Rückruf]**.

   ![Ein vor Ereignisversand-Rückruf](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Wählen Sie **[!UICONTROL &lt;/> Bereitstellen eines Ereignisses vor dem Senden des Callback-Codes]**.
1. Fügen Sie den folgenden Code hinzu:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Ein vor Ereignisversand-Rückruf](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Wählen **[!UICONTROL Speichern]**, um den Code zu speichern.
1. Wählen **[!UICONTROL Speichern]**, um die Erweiterung zu speichern.
1. [Veröffentlichen](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview) der Aktualisierungen für Ihre Tags-Eigenschaft.





