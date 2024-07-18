---
title: Anzeigen von Anmerkungen
description: Anzeigen von Anmerkungen in Workspace.
role: User
feature: Components
exl-id: c0e4fb37-b20c-463c-b29a-310ca3adb2c7
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 100%

---

# Anzeigen von Anmerkungen

Anmerkungen werden je nachdem, ob sie sich über einen einzelnen Tag oder einen Datumsbereich erstrecken, etwas unterschiedlich angezeigt.

## Anzeigen von Anmerkungen in Liniendiagrammen oder Tabellen

| Datum | Erscheinungsbild |
| --- | --- |
| **Einzeltag** | ![Liniendiagramm-Visualisierung mit hervorgehobener Anmerkung](assets/single-day.png)<p>Wenn Sie den Mauszeiger über die Anmerkung bewegen, können Sie deren Details anzeigen und sie durch Auswahl des Stiftsymbols bearbeiten oder löschen:<p> ![Anmerkungsdetails mit der Option zum Bearbeiten oder Löschen der Anmerkung.](assets/hover.png) |
| **Datumsbereich** | Das Symbol ändert sich, und wenn Sie den Mauszeiger darüber bewegen, wird der Datumsbereich angezeigt.<p>![Symbol für Datumsbereich-Anmerkungen](assets/multi-day.png)<p>Wenn Sie die Anmerkung im Liniendiagramm auswählen, werden ihre Metadaten angezeigt und Sie können sie bearbeiten oder löschen:![](assets/multi-hover.png)<p>In einer Tabelle wird an jedem Datum im Datumsbereich ein Symbol angezeigt.<p>![](assets/multi-day-table.png) |
| **Überlappende Anmerkungen** | An Tagen, an denen es mehr als eine Anmerkung gibt, wird das Symbol grau dargestellt.<p>![Details für sich überschneidende Anmerkungen ](assets/grey.png)<p>Wenn Sie den Mauszeiger über das graue Symbol bewegen, werden alle sich überlappenden Anmerkungen angezeigt:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## Anzeigen von Anmerkungen in einer PDF-Datei

Da Symbole in einer PDF-Datei nicht auf den Mauszeiger reagieren können, enthält diese Datei (nach dem Export) am unteren Rand eines Bedienfelds Anmerkungen zu Erklärungen. Siehe folgendes Beispiel:

![Eine hervorgehobene Ansicht einer PDF-Datei mit Erklärungen zu Anmerkungen.](assets/ann-pdf.png)

## Anzeigen von Anmerkungen mit Daten ohne Trendansicht

Manchmal werden Anmerkungen mit Daten ohne Trendansicht angezeigt, die jedoch an eine bestimmte Dimension gebunden sind. In diesem Fall werden sie nur in einer zusammenfassenden Anmerkung in der rechten unteren Ecke angezeigt. Siehe folgendes Beispiel:

![](assets/non-date.png)

Das Zusammenfassungsdiagramm wird in allen Visualisierungstypen in der Ecke angezeigt, nicht nur in Freiformtabellen ohne Trendansicht und Zusammenfassungszahlen. Es wird auch in Visualisierungen wie dem [!UICONTROL Ringdiagramm], dem [!UICONTROL Fluss], dem [!UICONTROL Fallout], der [!UICONTROL Kohorte] usw. angezeigt.

![Zusammenfassungsdiagramm in Visualisierungen](assets/ann-summary.png)
