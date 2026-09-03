---
title: Komponenteneinstellungen für die Metrik-Deduplizierung
description: Zählen Sie nur das erste Vorkommen einer Metrik in Berichten.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:57.728Z'
TQID: 'https://experienceleague.adobe.com/bCgBjD9r0cQ3O73fEip-EQHItMHQSX-2AECydDxR9Ms'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 79%

---

# Komponenteneinstellungen für die Metrik-Deduplizierung {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="Deduplizierung einer Metrik"
>abstract="Konfigurieren Sie eine Metrik so, dass nur Werte gezählt werden, die nicht wiederholt auftreten."

<!-- markdownlint-enable MD034 -->


Mit der Metrik-Deduplizierung können Sie eine Metrik so konfigurieren, dass Werte nicht wiederholt gezählt werden.

![Deduplizierung einer Metrik](../assets/metric-deduplication.png)

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Deduplizierung einer Metrik] | Ein Kontrollkästchen, mit dem Sie die Metrik-Deduplizierung aktivieren können. Standardmäßig deaktiviert. |
| [!UICONTROL Umfang der Deduplizierung] | Hiermit können Sie bestimmen, wie weit die eindeutige Prüfung in die Vergangenheit reicht.<br/>**[!UICONTROL Globales Konto &#x200B;]**: Es wird nur das erste Metrikereignis im Reporting-Fenster gezählt.<br/>**[!UICONTROL Konto]**: Es wird nur das erste Metrikereignis im Reporting-Fenster gezählt.<br/>**[!UICONTROL Opportunity &#x200B;]**: Es wird nur das erste Metrikereignis im Reporting-Fenster gezählt.<br/>**[!UICONTROL Einkaufsgruppe]**: Nur das erste Metrikereignis im Berichtsfenster wird gezählt.<br/>**[!UICONTROL Person &#x200B;]**: Nur das erste Metrikereignis im Berichtsfenster wird gezählt.<br>**[!UICONTROL Sitzung]**: Nur das erste Metrikereignis der Sitzung wird gezählt.<br> |
| [!UICONTROL Deduplizierungs-ID] | Ermöglicht es Ihnen, anstelle der Deduplizierung in der Metrik selbst die Metrik-Deduplizierung auf Grundlage einer Dimension anzuwenden. Wertvoll für Dimensionen wie Kauf-ID, um eine Deduplizierung anzuwenden. |
| [!UICONTROL Beizubehaltender Wert] | <ul><li>**Erste Instanz beibehalten**: Verwenden Sie dies in Situationen, in denen die ursprüngliche Instanz der Metrik die gültige ist. Die häufigste wäre wahrscheinlich eine Kaufbestätigung. Selbst wenn jemand versehentlich die Seite neu lädt und wir eine weitere Instanz einer Kaufbestätigung erhalten, ist das erste Ereignis das gültige.</li><li>**Letzte Instanz beibehalten**: Verwenden Sie dies in Situationen, in denen es sinnvoller ist, die letzte Instanz zu erfassen. Beispiel: Eine Person aktualisiert ihr Online-Profil. Wir möchten nur eine dieser Aktualisierungen pro Sitzung zählen. Die Person könnte das Profil während der Sitzung jedoch mehrmals aktualisieren. Wenn wir die erste Instanz beibehalten, kann es Aktivitäten geben, die nicht mit dem Ereignis verknüpft sind. In diesem Fall ist es sinnvoller, die letzte Instanz zu behalten.</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>Deduplizierung im Umfang einer _Person_ wird nach vollständigen Monaten in UTC-Zeit bewertet. Ein Berichtsfenster für einen Teil des Monats zeigt möglicherweise nicht alle ersten oder letzten Instanzen an, wenn einige innerhalb des ganzen Monats, aber außerhalb der Berichtsdaten aufgetreten sind.
