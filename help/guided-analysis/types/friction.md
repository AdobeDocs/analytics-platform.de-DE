---
title: Reibung
description: Konversionsraten zwischen den Schritten vergleichen.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
source-git-commit: 164785f52990c43691c8e13c8fa80e3c201995f7
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# Reibung

{{release-limited-testing}}

Die **Friktion** -Ansicht bietet eine visuelle Darstellung eines kritischen Benutzer-Journey in Ihrem Produkt. Die horizontale Achse stellt jeden Schritt dar, den ein Benutzer durchlaufen muss. Die vertikale Achse stellt den Prozentsatz der Benutzer oder Sitzungen bei jedem Schritt dar. Alle Schritte müssen in der gewünschten Reihenfolge durchgeführt werden, können jedoch jederzeit im Berichtsfenster erfolgen. Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Konversionsanalyse**: Sie können Konversionen in jeder Phase des Trichters analysieren. Indem Sie die Anzahl der Benutzer verfolgen, die von einem Schritt zum nächsten gelangen, können Sie Engpässe identifizieren, die ungewöhnliche oder unerwünschte Konversionsraten aufweisen. Diese Informationen sind nützlich, um zu verstehen, wo Sie Ihr Produkt für sofortige Ergebnisse verbessern können.
* **Onboarding-Optimierung**: Optimieren Sie den Onboarding-Prozess Ihres Produkts, indem Sie das Benutzerverhalten in Bezug auf wichtige Ereignisse untersuchen. Sie können ermitteln, mit welchen Schritten Benutzer zu kämpfen haben oder welche Schritte nicht ausgeführt werden können.
* **Funktionsbereitschaft und Interaktion**: Erfahren Sie, wie Benutzer mit bestimmten Funktionen in Ihrem Produkt interagieren. Durch die Analyse des Fortschritts der Benutzer durch funktionsbezogene Schritte können Sie die Rate der Funktionsbereitstellung bewerten und Bereiche identifizieren, in denen Benutzer bestimmte Funktionen abbrechen oder nicht nutzen können. Anschließend können Sie diese Informationen verwenden, um sich auf Funktionsverbesserungen zu konzentrieren und so die Akzeptanzraten zu erhöhen.
* **Kampagnenbewertung**: Messen Sie die Effektivität von Marketing-Kampagnen. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die eine bestimmte Kampagne berührt haben, und ihren Konversionsprozess mit anderen Kampagnen oder innerhalb Ihres gesamten Produkts vergleichen.

![Reibung](../assets/friction.png)

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Schritte**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jede Leiste im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einbeziehen.
* **Personen**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die Ansicht &quot;Friction&quot;bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **Metrik**: Der Bereich, der auf den Trichter angewendet werden soll. Zu den Optionen gehören Sitzungen und Benutzer. Durch die Auswahl von Sitzungen müssen alle Schritte innerhalb derselben Sitzung erfolgen, damit sie gezählt werden. Durch Auswahl von Benutzern müssen alle Schritte innerhalb des Berichtsfensters erfolgen, das für die Zählung ausgewählt wurde.
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören die Schritte .
* **Konversion von**: Bestimmt die Berechnung des Prozentsatzes von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem ersten Schritt oder dem vorherigen Schritt.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Fristvergleich](../assets/friction-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **Intervall**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Diese Einstellung wirkt sich nicht auf Trend-Ansichten wie &quot;Friction&quot;aus.
* **Datum**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie mit der Kalenderauswahl einen festen Datumsbereich auswählen.