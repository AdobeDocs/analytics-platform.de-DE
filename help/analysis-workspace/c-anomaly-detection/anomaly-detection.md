---
description: Erfahren Sie mehr über die Erkennung von Datenanomalien in Analysis Workspace.
title: Übersicht über die Anomalieerkennung
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 96%

---

# Übersicht über die Anomalieerkennung

Datenanomalien können kontextbezogen in Analysis Workspace angezeigt und analysiert werden.

[Video-Tutorial zur Anomalieerkennung](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=de) (4:53)

Die Anomalieerkennung bietet eine statistische Methode, mit der festgestellt wird, wie sich eine bestimmte Metrik in Bezug auf frühere Daten verändert hat.

Die Anomalieerkennung ermöglicht es Ihnen, „echte Signale“ von „Rauschen“ zu unterscheiden. Zudem hilft sie Ihnen anschließend dabei, potenzielle Faktoren zu bestimmen, die zu diesen Signalen oder Anomalien beigesteuert haben. Auf diese Weise können Sie feststellen, welche statistischen Schwankungen relevant sind, und anschließend die Ursache eines echten Fehlers feststellen. Zudem erhalten Sie eine zuverlässige Metrikvorhersage (KPI).

Zu Beispielen von Fehlern, die ein Eingreifen Ihrerseits erfordern, zählen:

* Erhebliche Verwerfungen im durchschnittlichen Bestellwert
* Spitzen in Bestellungen mit geringem Umsatz
* Spitzen oder Verwerfungen in Testprogrammregistrierungen
* Verwerfungen bei Landingpage-Aufrufen
* Spitzen in Videopufferereignissen
* Spitzen in niedrigen Video-Bitraten

Der Algorithmus der Analysis Workspace-Anomalieerkennung umfasst:

* Unterstützung für die Einstellungen „Stündlich“, „Wöchentlich“ und „Monatlich“ (zusätzlich zur vorhandenen Einstellung „Täglich“)
* Berücksichtigung von besonderen Tagen (wie z. B. Black Friday) und Feiertagen
