---
title: Häufig gestellte Fragen zur geführten Analyse
description: Häufig gestellte Fragen zur geführten Analyse.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Produktanalyse
source-git-commit: 2fe26bb906600a1987d9f4a07c5863030d52173a
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Häufig gestellte Fragen zur geführten Analyse

Häufig gestellte Fragen zur geführten Analyse.

+++**Wie kann meine Organisation für die geführte Analyse bereitgestellt werden?**

Geführte Analysen sind Teil von Adobe Product Analytics, einem kostenpflichtigen Add-on zu Customer Journey Analytics. Wenden Sie sich an Ihr Adobe-Account-Team, wenn Sie mit der Verwendung dieses Add-ons beginnen möchten.

+++

+++**Welche Implementierungsänderungen sind erforderlich, um die geführte Analyse zu verwenden?**

Wenn Sie Customer Journey Analytics bereits heute verwenden, sind keine zusätzlichen Implementierungsänderungen erforderlich. Die geführte Analyse verwendet dieselbe [Datenansichten](../data-views/data-views.md) und [Verbindungen](../connections/overview.md) als andere CJA-Schnittstellen wie [Analysis Workspace](../analysis-workspace/home.md).

Damit Ihre Endbenutzer mit der geführten Analyse am erfolgreichsten sind, wird empfohlen, in Adobe Experience Platform über ein starkes Ereignisschema und eine leistungsstarke Verwaltungsstrategie zu verfügen und [Datenansichten](../data-views/data-views.md).

+++

+++**Wann sollten Sie die Geführte Analyse oder Analysis Workspace verwenden?**

**Geführte Analyse** kann Benutzern dabei helfen, schnell hochwertige Einblicke zu erhalten. Dies ist nützlich für Produktteams, Benutzer, die vertraulicher mit Daten arbeiten möchten, und sogar für Analysten als Vorsprung zu einer tieferen Analyse.

**[Analysis Workspace](../analysis-workspace/home.md)** ist ein Freiformraum, mit dem Sie weiter in die Daten eintauchen können, um weitere Einblicke zu erhalten. Es ist nützlich für Analysten und Power-Benutzer, die die Daten gut verstehen und tief in sie eintauchen möchten.

+++

+++**Wie unterscheidet sich die Terminologie zwischen der geführten Analyse und Analysis Workspace?**

Geführte Analyse verwendet Begriffe, die häufiger von Produktteams verwendet werden. Sie können diese Tabelle referenzieren, wenn Sie zwischen der geführten Analyse und [Analysis Workspace](../analysis-workspace/home.md).

| Geführter Analysebegriff | Analysis Workspace-Begriff |
| --- | --- |
| Ereignis-   | Metrik |
| Benutzer | Personen |
| Eigenschaft | Dimension |
| Wert | Dimension |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**Was sind einige Unterschiede in der Vorgehensweise bei der geführten Analyse und der Berichterstellung mit Analysis Workspace?**

while [Analysis Workspace](../analysis-workspace/home.md) und geführte Analysen verwenden dieselben zugrunde liegenden Daten. Die Art und Weise, mit der jedes Tool Abfragen dieser Daten erstellen kann, ist anders.

* **Analysis Workspace ist ein dimensionszentriertes Erlebnis.** Tabellen bestehen normalerweise aus dimensionalen Zeilen, während Spalten normalerweise Metriken sind. Filter können sowohl in Zeilen als auch in Spalten angewendet werden, um die gewünschten Daten zu erhalten.

* **Geführte Analyse ist ein Ereignis und ein benutzerzentriertes Erlebnis.** Jede Analyse beginnt mit der Auswahl von Ereignissen. Anschließend können Dimensionen und Filter hinzugefügt werden, um diese Ereignisdaten zu verfeinern.

![Ansichten der Analysis Workspace- und Guided-Analyse](assets/structure.png)

Betrachten Sie das folgende Beispiel, in dem Sie sich auf Daten rund um die Startseite Ihrer Website konzentrieren. Teams stellen ähnliche Fragen, aber der Analysenansatz kann unterschiedlich sein.

* Ein typischer, dimensionszentrierter Analysis Workspace-Ansatz wäre: &quot;Sehen wir uns die Startseite an und sehen Sie, wie viele Seitenansichten sie erhalten hat.&quot;

  ![Dimension zentriert](assets/dimension-centered.png)

* Ein typisches Ereignis und benutzerzentrierter Ansatz für die angeleitete Analyse wäre: &quot;Wie viele Benutzer haben unsere Homepage besucht?&quot;

  ![Ereignis zentriert](assets/event-centered.png)

+++
