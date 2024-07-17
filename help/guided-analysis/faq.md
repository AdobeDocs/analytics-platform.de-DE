---
title: Häufig gestellte Fragen zur geführten Analyse
description: Häufig gestellte Fragen zur geführten Analyse.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: df00d954de5db89f0ccc40f7eb2474523d9e774e
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 71%

---

# Häufig gestellte Fragen zur geführten Analyse

Häufig gestellte Fragen zur geführten Analyse.

+++**Hat meine Organisation Zugriff auf die geführte Analyse?**

Geführte Analyseansichten sind in allen Customer Journey Analytics-Packages enthalten. Weitere Informationen zu den Ansichten, die Ihr CJA-Paket entsperrt, finden Sie im Abschnitt [Bereitstellung](overview.md#provisioning) auf der Übersichtsseite .

+++

+++**Welche Implementierungsänderungen sind erforderlich, um die geführte Analyse zu verwenden?**

Wenn Sie Customer Journey Analytics bereits heute verwenden, sind keine zusätzlichen Implementierungsänderungen erforderlich. Die geführte Analyse verwendet dieselben [Datenansichten](../data-views/data-views.md) und [Verbindungen](../connections/overview.md) wie andere CJA-Schnittstellen wie [Analysis Workspace](../analysis-workspace/home.md).

Damit Ihre Endbenutzer mit der geführten Analyse am erfolgreichsten sind, wird empfohlen, in Adobe Experience Platform über ein starkes Ereignisschema und eine leistungsstarke Verwaltungsstrategie sowie in [Datenansichten](../data-views/data-views.md) zu verfügen.

+++

+++**Wann sollten Sie die geführte Analyse oder Analysis Workspace verwenden?**

**Die geführte Analyse** kann Benutzenden helfen, schnell hochwertige Erkenntnisse zu gewinnen. Sie ist nützlich für Produkt-Teams, für Benutzende, die selbstbewusster mit Daten arbeiten möchten, und sogar für Analystinnen und Analysten als Einstieg in tiefere Analysen.

**[Analysis Workspace](../analysis-workspace/home.md)** ist ein frei gestaltbarer Bereich, in dem Sie tiefer in die Daten eintauchen können, um mehr Erkenntnisse zu gewinnen. Es ist nützlich für Analystinnen und Analysten sowie Benutzende, die die Daten gut verstehen und tief in sie eintauchen wollen.

+++

+++**Wie unterscheidet sich die Terminologie zwischen der geführten Analyse und Analysis Workspace?**

Die geführte Analyse verwendet Begriffe, die häufiger von Produkt-Teams verwendet werden. Sie können diese Tabelle referenzieren, wenn Sie zwischen einer geführten Analyse und [Analysis Workspace](../analysis-workspace/home.md) wechseln.

| Begriff der geführten Analyse | Begriff von Analysis Workspace |
| --- | --- |
| Ereignis | Metrik |
| Benutzende | Personen |
| Eigenschaft | Dimension |
| Wert | Dimensionselement |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**Was sind einige Unterschiede bei der Vorgehensweise bei der geführten Analyse und der Analysis Workspace-Berichterstattung?**

[Analysis Workspace](../analysis-workspace/home.md) und die geführte Analyse verwenden zwar dieselben zugrunde liegenden Daten, aber die Art und Weise, wie Sie mit jedem Tool Abfragen dieser Daten erstellen können, ist unterschiedlich.

* **Analysis Workspace ist ein dimensionszentriertes Erlebnis.** Die Tabellen bestehen normalerweise aus dimensionalen Zeilen, während Spalten normalerweise Metriken sind. Filter können sowohl in Zeilen als auch in Spalten angewendet werden, um die gewünschten Daten zu erhalten.

* **Die geführte Analyse ist ein Ereignis und ein benutzerzentriertes Erlebnis.** Jede Analyse beginnt mit der Auswahl von Ereignissen. Anschließend können Dimensionen und Filter hinzugefügt werden, um diese Ereignisdaten zu verfeinern.

![Ansichten in Analysis Workspace und geführten Analysen](assets/structure.png){style="border:1px solid gray"}

Betrachten Sie das folgende Beispiel, in dem Sie sich auf Daten rund um die Startseite Ihrer Website konzentrieren. Teams stellen ähnliche Fragen, aber der Analysenansatz kann unterschiedlich sein.

* Ein typischer, dimensionszentrierter Analysis Workspace-Ansatz wäre: „Sehen wir uns die Startseite an und sehen wir, wie viele Seitenansichten sie erhalten hat.“

  ![Dimensionzentriert](assets/dimension-centered.png){style="border:1px solid gray"}

* Ein typischer ereignisorientierter und benutzerzentrierter Ansatz für die geführte Analyse wäre: &quot;Wie viele Benutzer haben die Homepage besucht?&quot;

  ![Ereigniszentriert](assets/event-centered.png){style="border:1px solid gray"}

+++
