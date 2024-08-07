---
description: Fragen zur Customer Journey Analytics-Dokumentation stellen
title: KI-Assistent für Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 3ed6eabae8607a10920c8917a818f0497b337893
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 5%

---


# KI-Assistent für Adobe Customer Journey Analytics

AI Assistant ist eine Dialogerfahrung, die es Fachleuten ermöglicht, Aufgaben schnell auszuführen - unabhängig davon, ob sie Konzepte verstehen, Probleme beheben oder nach Informationen suchen. Er ermöglicht es auch Nichtexpertinnen und -experten, Expertenaufgaben durchzuführen, und erhöht die allgemeine Qualität der Arbeit.

Der KI-Assistent im Customer Journey Analytics wird in der Adobe Experience League-Dokumentation geschult. Bei der Beantwortung einer Frage antwortet der KI-Assistent mit einer hilfreichen Antwort, die schnelles Lernen ermöglicht.

Als Anfänger können Sie mit dem KI-Assistenten Customer Journey Analytics-Konzepte erlernen und sich selbst mit Produkten und Funktionen vertraut machen, mit denen Sie nicht vertraut sind. Erfahrene Benutzer können mit dem AI-Assistenten erweiterte Anwendungsfälle oder Tipps und Tricks präsentieren.

Zu den Beispielen für Konzeptfragen gehören:

* Was ist der Unterschied zwischen Batch- und Streaming-Erfassung?
* Wofür wird Customer Journey Analytics am besten verwendet?
* Wie richte ich eine Datenansicht ein?

Fragen, die außerhalb des Anwendungsbereichs von Customer Journey Analytics liegen, wie z. B. Fragen zu anderen Adobe-Produkten wie Adobe Target und der Adobe Creative Cloud Suite, können nicht beantwortet werden.

Der KI-Assistent für Customer Journey Analytics ist für alle Produktkategorien verfügbar.

## Produktwissen {#knowledge}

Das Produktkennungsabfragemodell wird auf Customer Journey Analytics trainiert. Andere Funktionen wie die Datenanalyse werden zu einem späteren Zeitpunkt eingeführt.

| Produktwissen | Beispiele |
| --- | --- |
| Zielgerichtetes Lernen | <ul><li>Was ist der Unterschied zwischen Adobe Analytics und Customer Journey Analytics?</li><li>Wie erstelle ich eine berechnete Metrik?</li></ul> |
| Offene Entdeckung | <ul><li>Wie kann ich ein Workspace-Projekt exportieren?</li><li>Wie finde ich doppelte Workspace-Komponenten?</li></ul> |
| Fehlerbehebung | <ul><li>Wie lange dauert es, bis Daten in CJA eingehen?</li><li>Wie viele abgeleitete Felder kann ich in einer Customer Journey Analytics-Verbindung haben?</li></ul> |

## Funktionszugriff

In dieser ersten Version wird der Zugriff auf die Funktion des AI-Assistenten durch die folgenden Parameter gesteuert:

* **Lösungszugriff**: Der AI-Assistent ist im Customer Journey Analytics, nicht aber in Adobe Analytics verfügbar. Es ist auch in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP und zusätzlichen Experience Platform-Apps verfügbar.

* **Vertragszugriff**: Wenn Sie den KI-Assistenten nicht verwenden können, wenden Sie sich an den Administrator oder Adobe-Kundenbetreuer Ihres Unternehmens. Bevor der KI-Assistent von Ihrer Einrichtung verwendet werden kann, muss Ihr Unternehmen bestimmten GenAI-bezogenen gesetzlichen Bestimmungen zustimmen.

* **Berechtigungen**: In [!UICONTROL Adobe Admin Console] bestimmt die Berechtigung [!UICONTROL Berichterstellungs-Tools] &quot;AI-Assistent: Produktwissen&quot;den Zugriff auf dieses Tool. Ein [Produktprofiladministrator](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) muss die folgenden Schritte in Admin Console ausführen:
   1. Navigieren Sie zu [!UICONTROL Admin Console] > [!UICONTROL Produkte und Dienste] > [!UICONTROL Customer Journey Analytics] > [!UICONTROL Produktprofil] > [!UICONTROL Berechtigungen] > [!UICONTROL Berichterstellungs-Tools bearbeiten].
   1. Fügen Sie &quot;AI Assistant: Product Knowledge&quot;hinzu.
      ![Berechtigung hinzufügen](assets/image.png)

## Zugriff auf den KI-Assistenten in der Customer Journey Analytics-Benutzeroberfläche

1. Um den KI-Assistenten zu starten, wählen Sie das Symbol KI-Assistent in der oberen Kopfzeile einer beliebigen Seite der Customer Journey Analytics-Benutzeroberfläche aus.

   ![Symbol &quot;KI-Assistent&quot;](assets/ai-asst1.png)

   Bei der erstmaligen Verwendung des AI-Assistenten erscheint ein Haftungsausschluss mit einigen Nutzungsbedingungen des Assistenten.

1. Stellen Sie in dem bereitgestellten Feld eine spezifische Frage in natürlicher Sprache an den KI-Assistenten.

   ![Fragefeld](assets/ai-asst2.png)

1. (Optional) Um Quellen anzuzeigen, klicken Sie auf &quot;**[!UICONTROL Quellen anzeigen]**&quot;. Außerdem werden die Dokumentationsquelle bzw. die Quellen angezeigt, die die Antwort erhalten haben.

1. (Optional) Sie können auch eine Daumen-Up- oder Daumen-Down-Abstimmung über die Nützlichkeit einer gegebenen Antwort geben.

1. (Optional) Sie können die Antwort auf unangemessene oder schädliche Inhalte kennzeichnen.
