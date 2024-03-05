---
title: Häufig gestellte Fragen zur geführten Analyse
description: Häufig gestellte Fragen zur geführten Analyse.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Produktanalysen
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: ht
source-wordcount: '434'
ht-degree: 100%

---

# Häufig gestellte Fragen zur geführten Analyse

Häufig gestellte Fragen zur geführten Analyse.

+++**Wie kann für meine Organisation die geführte Analyse bereitgestellt werden?**

„Geführte Analyse“ ist Bestandteil von Adobe Product Analytics, einem kostenpflichtigen Add-on zu Customer Journey Analytics. Wenn Sie dieses Add-on verwenden möchten, wenden Sie sich an Ihr Adobe-Accountteam.

+++

+++**Welche Implementierungsänderungen sind erforderlich, um die geführte Analyse zu verwenden?**

Wenn Sie Customer Journey Analytics bereits heute verwenden, sind keine zusätzlichen Implementierungsänderungen erforderlich. Die geführte Analyse verwendet dieselben [Datenansichten](../data-views/data-views.md) und [Verbindungen](../connections/overview.md) wie andere CJA-Schnittstellen wie [Analysis Workspace](../analysis-workspace/home.md).

Damit Ihre Benutzenden die geführte Analyse so erfolgreich wie möglich nutzen können, sollten Sie über eine solide Ereignisschema- und Verwaltungsstrategie in Adobe Experience Platform und [Datenansichten](../data-views/data-views.md) verfügen.

+++

+++**Wann sollten Sie die geführte Analyse oder Analysis Workspace verwenden?**

**Die geführte Analyse** kann Benutzenden helfen, schnell hochwertige Erkenntnisse zu gewinnen. Sie ist nützlich für Produkt-Teams, für Benutzende, die selbstbewusster mit Daten arbeiten möchten, und sogar für Analystinnen und Analysten als Einstieg in tiefere Analysen.

**[Analysis Workspace](../analysis-workspace/home.md)** ist ein frei gestaltbarer Bereich, in dem Sie tiefer in die Daten eintauchen können, um mehr Erkenntnisse zu gewinnen. Es ist nützlich für Analystinnen und Analysten sowie Benutzende, die die Daten gut verstehen und tief in sie eintauchen wollen.

+++

+++**Worin unterscheidet sich die Terminologie von der geführten Analyse mit Analysis Workspace?**

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

+++**Was sind einige Unterschiede zwischen der Vorgehensweise bei der geführten Analyse und der Berichterstellung mit Analysis Workspace?**

[Analysis Workspace](../analysis-workspace/home.md) und die geführte Analyse verwenden zwar dieselben zugrunde liegenden Daten, aber die Art und Weise, wie Sie mit jedem Tool Abfragen dieser Daten erstellen können, ist unterschiedlich.

* **Analysis Workspace ist ein dimensionszentriertes Erlebnis.** Die Tabellen bestehen normalerweise aus dimensionalen Zeilen, während Spalten normalerweise Metriken sind. Filter können sowohl in Zeilen als auch in Spalten angewendet werden, um die gewünschten Daten zu erhalten.

* **Die geführte Analyse ist ein Ereignis und ein benutzerzentriertes Erlebnis.** Jede Analyse beginnt mit der Auswahl von Ereignissen. Anschließend können Dimensionen und Filter hinzugefügt werden, um diese Ereignisdaten zu verfeinern.

![Ansichten in Analysis Workspace und geführten Analysen](assets/structure.png){style="border:1px solid gray"}

Betrachten Sie das folgende Beispiel, in dem Sie sich auf Daten rund um die Startseite Ihrer Website konzentrieren. Teams stellen ähnliche Fragen, aber der Analysenansatz kann unterschiedlich sein.

* Ein typischer, dimensionszentrierter Analysis Workspace-Ansatz wäre: „Sehen wir uns die Startseite an und sehen wir, wie viele Seitenansichten sie erhalten hat.“

  ![Dimensionzentriert](assets/dimension-centered.png){style="border:1px solid gray"}

* Ein typischer ereignisorientierter und benutzerzentrierter Ansatz für die geführte Analyse wäre: „Wie viele Benutzende haben unsere Startseite besucht?“

  ![Ereigniszentriert](assets/event-centered.png){style="border:1px solid gray"}

+++
