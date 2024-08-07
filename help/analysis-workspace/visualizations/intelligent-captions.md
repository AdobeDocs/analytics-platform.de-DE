---
description: Verwenden Sie intelligente Beschriftungen, um Einblicke in natürliche Sprachen zu generieren, um schnell Trends innerhalb von Visualisierungen zu überdecken.
title: Intelligente Beschriftungen
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# Intelligente Beschriftungen

Intelligente Untertitel verwenden fortschrittliches maschinelles Lernen und generative KI, um wertvolle Einblicke in natürliche Sprachen für Workspace-Visualisierungen bereitzustellen. Die erste Version bietet automatisch generierte Einblicke für die [Linie](line.md) -Visualisierung. (Es folgen weitere Visualisierungen.)

Intelligente Beschriftungen sind auf Folgendes ausgerichtet:

* Analysten, die Geschichten benötigen, um sie für andere Benutzer freizugeben. Analysten benötigen diese Einblicke, um ihren Benutzern Kontext bieten zu können.
* Geschäftsbenutzer, die schnell allgemeine Schnellzugriffe entdecken möchten.

Untertitel sind für alle Customer Journey Analytics-Benutzer verfügbar und erfordern keine speziellen Berechtigungen.

## Intelligente Beschriftungen starten {#launch}

Um automatisch generierte Untertitel für eine Linienvisualisierung zu starten, klicken Sie oben rechts in der Visualisierung auf das Symbol **[!UICONTROL Intelligente Untertitel]** .

![Das Fenster &quot;Analyse starten&quot;mit den intelligenten Beschriftungen für den Trend zu Produktansichten. ](assets/intell-caps-1.png)

Einblicke in natürliche Sprachen werden jetzt generiert.

Bedenken Sie Folgendes

* Sie benötigen mindestens 3 Datenpunkte, damit Beschriftungen erfolgreich generiert werden können. Andernfalls wird möglicherweise ein Fehler mit der Meldung &quot;Nicht genügend Daten zur Analyse&quot;angezeigt.

* Beschriftungen werden jedes Mal generiert, wenn sich die zugrunde liegenden ausgewählten Daten in der Tabelle ändern, die die Visualisierung ermöglicht.

* Wenn die Tabelle mehrere Metriken enthält, werden Untertitel nur für die erste Metrik oder die Metrik generiert, die aktuell vom Benutzer ausgewählt wird.

* Wenn Sie das Projekt zu diesem Zeitpunkt speichern und es später erneut laden, werden die Beschriftungen automatisch mit neuen Daten aktualisiert. Dasselbe gilt für geplante Projekte und PDF-Dateien, die aus diesem Projekt exportiert werden.

## Anzeigen und Interpretieren von Untertiteln {#view}

Im Folgenden finden Sie ein Beispiel dafür, wie die Beschriftungen aussehen könnten:

![Intelligente Beschriftungen für die Linienvisualisierung, einschließlich Saisonabhängigkeit, Min., Max., Spitze und Rückgang.](assets/captions.png)

## In Zwischenablage kopieren {#copy}

Sie können die Beschriftungen in eine Zwischenablage kopieren und in ein PowerPoint- oder ein anderes Tool einfügen. Suchen Sie das Symbol **[!UICONTROL Beschriftungen in die Zwischenablage kopieren]** oben rechts im Dialogfeld &quot;Beschriftungen&quot;.

## Bearbeiten von Beschriftungen {#edit}

Sie können die Beschriftungen bearbeiten, z. B. eine bestimmte Kategorie von Einblicken ein- oder ausblenden. Wenn Sie beispielsweise keinen Einblick in die Mindestreihenfolge wünschen, können Sie sie einfach ausblenden und auf &quot;Anwenden&quot;klicken, sodass sie nicht erneut angezeigt wird.

1. Klicken Sie auf das Symbol &quot;**[!UICONTROL Intelligente Beschriftungen bearbeiten&quot;neben dem Symbol für die Zwischenablage.]**

1. Klicken Sie im Dialogfeld &quot;Bearbeiten&quot;auf das Augensymbol neben dem Einblick, den Sie ausblenden möchten.

1. Klicken Sie auf **[!UICONTROL Anwenden]**.

Verwenden Sie denselben Prozess, um Beschriftungen wieder einzublenden.

## Untertitel exportieren {#export}

Sie können **Untertitel über PDF** exportieren, solange das Projekt mit den generierten Untertiteln gespeichert wird.

## Beschriftungen deaktivieren {#toggle}

Wenn Sie keine intelligenten Untertitel erstellen möchten, können Sie diese Funktion deaktivieren, indem Sie die Voreinstellungen für die Visualisierung aufrufen und die Option **[!UICONTROL Intelligente Untertitel anzeigen]** deaktivieren.

![Linienvisualisierungsoptionen mit der Option zum Deaktivieren der Option &quot;Intelligente Untertitel anzeigen&quot;](assets/toggle-captions.png)

## Intelligente Beschriftungen in mobilen Scorecards

Intelligente Untertitel sind auch in Customer Journey Analytics [mobile Scorecards](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) verfügbar.