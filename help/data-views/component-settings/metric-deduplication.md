---
title: Komponenteneinstellungen für die Metrik-Deduplizierung
description: Zählen Sie nur das erste Vorkommen einer Metrik in Berichten.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 100%

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
| [!UICONTROL Deduplizierung der Metrik] | Ein Kontrollkästchen, mit dem Sie die Metrik-Deduplizierung aktivieren können. Standardmäßig deaktiviert. |
| [!UICONTROL Umfang der Deduplizierung] | Hiermit können Sie bestimmen, wie weit die eindeutige Prüfung in die Vergangenheit reicht.<br>**Sitzung**: Es wird nur das erste Metrikereignis der Sitzung gezählt.<br>**Person**: Es wird nur das erste Metrikereignis im Reporting-Fenster gezählt. |
| [!UICONTROL Deduplizierungs-ID] | Ermöglicht es Ihnen, anstelle der Deduplizierung in der Metrik selbst die Metrik-Deduplizierung auf Grundlage einer Dimension anzuwenden. Wertvoll für Dimensionen wie Kauf-ID, um eine Deduplizierung anzuwenden. |
| [!UICONTROL Beizubehaltender Wert] | <ul><li>**Erste Instanz beibehalten**: Verwenden Sie dies in Situationen, in denen die ursprüngliche Instanz der Metrik die gültige ist. Die häufigste wäre wahrscheinlich eine Kaufbestätigung. Selbst wenn jemand versehentlich die Seite neu lädt und wir eine weitere Instanz einer Kaufbestätigung erhalten, ist das erste Ereignis das gültige.</li><li>**Letzte Instanz beibehalten**: Verwenden Sie dies in Situationen, in denen es sinnvoller ist, die letzte Instanz zu erfassen. Beispiel: Eine Person aktualisiert ihr Online-Profil. Wir möchten nur eine dieser Aktualisierungen pro Sitzung zählen. Die Person könnte das Profil während der Sitzung jedoch mehrmals aktualisieren. Wenn wir die erste Instanz beibehalten, kann es Aktivitäten geben, die nicht mit dem Ereignis verknüpft sind. In diesem Fall ist es sinnvoller, die letzte Instanz zu behalten.</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>Deduplizierung im Umfang einer _Person_ wird nach vollständigen Monaten in UTC-Zeit bewertet. Ein Berichtsfenster für einen Teil des Monats zeigt möglicherweise nicht alle ersten oder letzten Instanzen an, wenn einige innerhalb des ganzen Monats, aber außerhalb der Berichtsdaten aufgetreten sind.
