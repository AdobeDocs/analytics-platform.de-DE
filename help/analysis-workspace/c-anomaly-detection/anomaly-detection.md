---
description: Erfahren Sie mehr über die Erkennung von Datenanomalien in Analysis Workspace.
title: Anomalieerkennung – Überblick
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
TQID: https://experienceleague.adobe.com/beFLMQfzXJUoCbg6fSLpFqcbaB7GSuo6SHroSS6V5wI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: aff2ef09-fc60-4018-9197-e2befd623064
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 83%

---

# Anomalieerkennung – Überblick

Datenanomalien können kontextbezogen in Analysis Workspace angezeigt und analysiert werden.

[Video-Tutorial zur Anomalieerkennung](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=de) (4:53)

Die Anomalieerkennung bietet eine statistische Methode, mit der festgestellt wird, wie sich eine bestimmte Metrik in Bezug auf frühere Daten verändert hat.

Die Anomalieerkennung ermöglicht es Ihnen, „echte Signale“ von „Rauschen“ zu trennen und potenzielle Faktoren zu identifizieren, die zu diesen Signalen oder Anomalien beigetragen haben. Mit anderen Worten, es lässt Sie erkennen, welche statistischen Schwankungen von Bedeutung sind und welche nicht. Anschließend können Sie die Grundursache einer echten Anomalie identifizieren. Darüber hinaus können Sie zuverlässige Prognosen für Ihre Metrik (KPI) erhalten.

Beispiele für Anomalien, die Sie untersuchen können:

* Drastische Rückgänge beim durchschnittlichen Bestellwert
* Spitzen bei Bestellungen mit niedrigem Umsatz
* Spitzen oder Rückgänge bei Testregistrierungen
* Rückgänge bei Landingpage-Ansichten
* Spitzen bei Video-Pufferereignissen
* Spitzen bei niedrigen Video-Bitraten

Der Algorithmus zur Anomalieerkennung in Analysis Workspace umfasst

* Unterstützung für stündliche, wöchentliche und monatliche Granularität zusätzlich zur bestehenden täglichen Granularität.
* Berücksichtigung von Saisonalität (wie „Black Friday“) und Feiertagen.
