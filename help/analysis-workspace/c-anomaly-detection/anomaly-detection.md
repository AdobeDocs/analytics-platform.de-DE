---
description: Erfahren Sie mehr über die Erkennung von Datenanomalien in Analysis Workspace.
title: Anomalieerkennung – Überblick
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 25%

---

# Anomalieerkennung – Überblick

Datenanomalien können kontextbezogen in Analysis Workspace angezeigt und analysiert werden.

[Video-Tutorial zur Anomalieerkennung](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=de) (4:53)

Die Anomalieerkennung bietet eine statistische Methode, mit der festgestellt wird, wie sich eine bestimmte Metrik in Bezug auf frühere Daten verändert hat.

Mit der Anomalieerkennung können Sie „wahre Signale“ von „Rauschen“ trennen und dann potenzielle Faktoren identifizieren, die zu diesen Signalen oder Anomalien beigetragen haben. Mit anderen Worten, es lässt Sie erkennen, welche statistischen Schwankungen von Bedeutung sind und welche nicht. Anschließend können Sie die Grundursache einer echten Anomalie identifizieren. Darüber hinaus können Sie zuverlässige Metrik (KPI)-Prognosen abrufen.

Beispiele für Anomalien, die Sie untersuchen können:

* Drastische Rückgänge beim durchschnittlichen Bestellwert
* Spitzen bei Aufträgen mit geringem Umsatz
* Spitzen oder Rückgänge bei Testregistrierungen
* Drops in Landingpage-Ansichten
* Spitzen bei Videopuffer-Ereignissen
* Spitzen bei niedrigen Video-Bitraten

Der Anomalieerkennungsalgorithmus von Analysis Workspace umfasst

* Unterstützung für stündliche, wöchentliche und monatliche Granularität zusätzlich zur vorhandenen täglichen Granularität.
* Bewusstsein für Saisonabhängigkeit (wie „Black Friday„) und Feiertage.
