---
description: Adobe bietet verschiedene berechnete Metriken, die Sie verwenden können. Auf dieser Seite werden diese Metriken und die vorgesehenen Verwendungszwecke aufgelistet.
title: Standardmäßige berechnete Metriken
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 28%

---

# Standardmäßige berechnete Metriken

Customer Journey Analytics bietet die folgenden berechneten Metriken, um die häufigsten Anwendungsfälle abzudecken:

| Name der berechneten Metrik | Beschreibung | Formel |
|---------|----------|---------|
| Startrate der Sitzung | Der Prozentsatz, zu dem ein Dimensionselement beim ersten Ereignis einer Sitzung aufgetreten ist.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Session Starts]` [Standardkomponente](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen.</p> | `[Session Starts] / [Sessions]` |
| Aufgewendete Zeit pro Person   | Die durchschnittliche Zeit, die eine Person mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Time Spent (seconds)]` [Standardkomponente](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen.</p> | `[Time Spent (seconds)] / [Users]` |
| Sitzungen pro Person | Die durchschnittliche Anzahl von Sitzungen pro Person. | `[Sessions] / [Users]` |
| Aufgewendete Zeit pro Sitzung | Die durchschnittliche Zeit, die eine Person pro Sitzung mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Time Spent (seconds)]` [Standardkomponente](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen.</p> | `[Time Spent (seconds)] / [Sessions]` |
| Endrate der Sitzung | Der Prozentsatz, zu dem ein Dimensionselement beim letzten Ereignis einer Sitzung aufgetreten ist. <p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Session Ends]` [Standardkomponente](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen.</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
