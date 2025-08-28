---
description: Stellen von Fragen zur Customer Journey Analytics-Dokumentation
title: KI-Assistent für Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 82b36895fe5186f0133c128d434470ea7f875677
workflow-type: ht
source-wordcount: '648'
ht-degree: 100%

---


# KI-Assistent für Adobe Customer Journey Analytics

Der KI-Assistent liefert ein Gesprächserlebnis, mit dem Fachleute Aufgaben schnell ausführen können. Dies gilt unabhängig davon, ob es darum geht, Konzepte zu verstehen, Probleme zu beheben oder Informationen zu durchsuchen. Der KI-Assistent ermöglicht es auch Nichtexpertinnen und -experten, Expertenaufgaben durchzuführen, und erhöht die allgemeine Qualität der Arbeit.

Der KI-Assistent in Customer Journey Analytics wurde für die zugehörige Adobe Experience League-Dokumentation trainiert. Wenn eine Frage gestellt wird, antwortet der KI-Assistent mit einer hilfreichen Antwort, die schnelles Lernen ermöglicht.

Neue Benutzende können den KI-Assistenten verwenden, um Customer Journey Analytics-Konzepte zu erlernen und sich mit unbekannten Produkten und Funktionen vertraut zu machen. Erfahrene Benutzende können den KI-Assistenten verwenden, um komplexere Anwendungsfälle oder Tipps und Tricks zu präsentieren.

Einige Beispiele für Fragen konzeptueller Natur:

* Was ist der Unterschied zwischen Batch- und Streaming-Aufnahme?
* Wofür wird Customer Journey Analytics am besten verwendet?
* Wie richte ich eine Datenansicht ein?

Fragen, die nicht in den Umfang von Customer Journey Analytics fallen, z. B. Fragen zu anderen Adobe-Produkten wie Adobe Target und der Adobe Creative Cloud Suite, können nicht beantwortet werden.

Der KI-Assistent für Customer Journey Analytics ist für alle Produktstufen verfügbar.

## Produktkenntnisse {#knowledge}

| Produktkenntnisse | Beispiele |
| --- | --- |
| Punktuelles Lernen | <ul><li>Was ist der Unterschied zwischen Adobe Analytics und Customer Journey Analytics?</li><li>Wie erstelle ich eine berechnete Metrik?</li></ul> |
| Offene Erkundung | <ul><li>Wie exportiere ich ein Workspace-Projekt?</li><li>Wie suche ich nach doppelten Workspace-Komponenten?</li></ul> |
| Fehlerbehebung | <ul><li>Wie lange dauert es, bis Daten in CJA eintreffen?</li><li>Wie viele abgeleitete Felder sind in einer Customer Journey Analytics-Verbindung möglich?</li></ul> |

## Datenanalyse

Data Insights Agent, auf den über den KI-Assistenten in Customer Journey Analytics zugegriffen werden kann, ist ein auf generativer KI basierender Konversationsagent, der Fragen zu Ihren Daten schnell und effizient beantwortet. Er erstellt relevante Visualisierungen in Analysis Workspace mithilfe von Komponenten aus Ihrer Datenansicht und unter Verwendung Ihrer tatsächlichen Daten.

Weitere Informationen zur Verwendung von Data Insights Agent im KI-Assistenten finden Sie unter [Visualisieren von Daten mit Data Insights Agent](/help/data-analysis-ai.md).

## Funktionszugriff

Die folgenden Parameter regeln den Zugriff auf den KI-Assistenten:

* **Lösungsbasierter Zugriff**: Der KI-Assistent ist in Customer Journey Analytics verfügbar, aber nicht in Adobe Analytics. Er ist auch in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP und weiteren Experience Platform-Anwendungen verfügbar.

* **Zugriff auf vertraglicher Grundlage**: Wenn Sie den KI-Assistenten nicht verwenden können, wenden Sie sich an die bzw. den Admin Ihrer Organisation oder die Adobe-Kundenbetreuung. Bevor Ihre Organisation den KI-Assistenten nutzen kann, müssen Sie bestimmten rechtlichen Bedingungen im Zusammenhang mit generativer KI zustimmen.

* **Berechtigungen**: In der [!UICONTROL Adobe Admin Console] bestimmt die [!UICONTROL Reporting-Tools-Berechtigung] **[!UICONTROL KI-Assistent: Produktkenntnisse]** den Zugriff auf dieses Tool. Sie als [Produktprofil-Admin](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) müssen diese Schritte in der [!UICONTROL Admin Console] ausführen:
   1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Dienste]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]**.
   1. Wählen Sie den Titel des Produktprofils aus, für das Zugriff auf [!UICONTROL KI-Assistent: Produktkenntnisse] gewährt werden soll.
   1. Wählen Sie im entsprechenden Produktprofil die Option **[!UICONTROL Berechtigungen]** aus.
   1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um **[!UICONTROL Reporting-Tools]** zu bearbeiten.
   1. Wählen Sie ![Hinzufügen](/help/assets/icons/AddCircle.svg) aus, um **KI-Assistent: Produktkenntnisse** zu **[!UICONTROL Eingeschlossene Berechtigungseinträge]** hinzuzufügen.

      ![Hinzufügen einer Berechtigung](assets/ai-assistant-permissions.png)

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

Weitere Informationen finden Sie unter [Zugriffssteuerung](/help/technotes/access-control.md#access-control).

## Zugreifen auf den KI-Assistenten in der Customer Journey Analytics-Benutzeroberfläche

1. Um den KI-Assistenten zu starten, wählen Sie oben auf einer beliebigen Seite in der Customer Journey Analytics-Benutzeroberfläche das Symbol „KI-Assistent“ aus.

   ![Symbol „KI-Assistent“](assets/ai-asst1.png)

   Bei der erstmaligen Verwendung des KI-Assistenten wird ein Haftungsausschluss mit einigen Nutzungsbedingungen für den Assistenten angezeigt.

1. Stellen Sie dem KI-Assistenten im bereitgestellten Feld eine spezifische Frage in natürlicher Sprache.

   ![Fragefeld](assets/ai-asst2.png)

1. (Optional) Klicken Sie zur Anzeige von Quellen auf **[!UICONTROL Quellen anzeigen]**. Anschließend werden die Dokumentationsquelle(n) angezeigt, auf denen die Antwort basiert.

1. (Optional) Sie können die Nützlichkeit einer bestimmten Antwort auch mit „Daumen hoch“ oder „Daumen runter“ bewerten.

1. (Optional) Sie können die Antwort bei unangemessenen oder schädlichen Inhalten markieren.
