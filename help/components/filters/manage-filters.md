---
title: Filter Manager
description: Erfahren Sie, wie Sie Filter in Customer Journey Analytics verwalten.
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e84010b9ea9e6385574e8b1a04f7eccbba3ebc90
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 19%

---

# Filter Manager

Der Filter-Manager bietet viele Möglichkeiten zum Kuratieren von Filtern, wie das Freigeben, Taggen, Genehmigen, Kopieren, Löschen und Kennzeichnen als Favoriten.

Der Filter-Manager zeigt Ihnen alle Filter an, deren Inhaber Sie sind und die für Sie freigegeben wurden. Benutzer auf Administratorebene können alle Filter der Organisation anzeigen. In dieser Übersicht werden die Benutzeroberfläche und die Funktionen des Filters-Managers vorgestellt.

![](assets/filter-manager-ui.png)

## Zugriff auf den Filter-Manager

1. Wählen Sie unter Customer Journey Analytics die **[!UICONTROL Komponenten]** Registerkarte und wählen Sie **[!UICONTROL Filter]**.

## Verfügbare Aktionen im Filter-Manager

Im Filter-Manager haben Sie folgende Möglichkeiten:

* [Filtern der Filterliste](/help/components/filters/filters-filter.md)

* [Filter als Favoriten markieren](/help/components/filters/filters-favorite.md)

* [Filter genehmigen](/help/components/filters/filters-approve.md)

* [Filter taggen](/help/components/filters/filters-tag.md)

* [Filter freigeben](/help/components/filters/filters-share.md)

* Exportieren Sie einen Filter in eine CSV-Datei.

* [Filter kopieren](/help/components/filters/filters-copy.md)

* Filter löschen

## Spalten konfigurieren

Sie können die für jeden Filter angezeigten Informationen im Filter-Manager konfigurieren, indem Sie die angezeigten Spalten konfigurieren.

So konfigurieren Sie die sichtbaren Spalten im Filter-Manager:

1. Wählen Sie unter Customer Journey Analytics die **[!UICONTROL Komponenten]** Registerkarte und wählen Sie **[!UICONTROL Filter]**.

1. Wählen Sie im Filter-Manager die **Spalten anpassen** icon ![Symbol &quot;Spalten anpassen&quot;](assets/customize-columns-icon.png)und wählen Sie dann die Spalten aus, die im Filter-Manager angezeigt werden sollen.

   Die folgenden Spalten sind verfügbar:

   | Spaltentitel | Beschreibung |
   |---|---|
   | Titel und Beschreibung | Diese Werte werden im Filter-Builder bereitgestellt. Um den Titel und die Beschreibung zu bearbeiten, wählen Sie den Titel-Link aus, um den Filter-Builder zu öffnen. |
   | Favoriten | Zeigt neben jedem Filter Sternensymbole an, mit denen Sie Filter als Favoriten markieren können. Weitere Informationen finden Sie unter [Filter als Favoriten markieren](/help/components/filters/filters-favorite.md). |
   | Datenansicht | Diese Spalte gibt an, in welcher Datenansicht der Filter zuletzt gespeichert wurde. |
   | Verantwortlicher | Zeigt an, wer Inhaber des Filters ist. Wenn Sie kein Administrator sind, können Sie nur Filter sehen, deren Inhaber Sie sind, sowie Filter, die für Sie freigegeben wurden. |
   | Tags (in der Spaltenauswahl nicht aktiviert, weshalb die Spalte nicht angezeigt wird) | Tags, die entweder durch Sie oder durch Personen, die einen Filter für Sie freigegeben haben, auf den Filter angewendet wurden. |
   | Freigegeben für | Zeigt Personen oder Gruppen (nur Administrator) oder „Alle“ (nur Administrator) an, für die Sie den Filter freigegeben haben. <p>Wenn ein Filter von Ihnen oder für Sie freigegeben wird, wird neben dem Filternamen ein Freigabesymbol angezeigt.</p> |
   | Änderungsdatum | Zeigt das Datum der letzten Änderung des Filters an. |
   | Verwendet in | Zeigt an, in wie vielen Komponenten der Filter derzeit verwendet wird. <p>Wenn der Filter beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**].</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung der verwendeten Filter anzuzeigen (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Warnhinweise (2)**]).</p><p>Filter können in einem der folgenden Komponententypen verwendet werden:</p> <ul><li>Berechnete Metriken </li><li>Projekte</li><li>Geplante Projekte</li></ul><p>Diese Informationen können Ihnen dabei helfen festzustellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss.</p><p>Beachten Sie bei der Anzeige dieser Spalte Folgendes:</p><ul><li>Diese Informationen enthalten keine Verwendung von API, Report Builder oder Data Warehouse.</li><li>Die [!UICONTROL **Verwendet in**] -Spalte wird nicht standardmäßig angezeigt. [Spalten konfigurieren](#configure-columns) , um es anzuzeigen.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, aber eine [!UICONTROL **Zuletzt verwendet**] Datum, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li></ul><p>Sie können die [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen, damit Sie die Verwendung von Komponenten in Ihrem Unternehmen verfolgen und besser verstehen können.</p> |
   | Zuletzt verwendet | Zeigt das Datum der letzten Verwendung des Filters in einem der folgenden Komponententypen an: <ul><li>Berechnete Metriken </li><li>Projekte</li><li>Geplante Projekte</li><li>Filter</li></ul> <p>Anhand dieser Informationen können Sie feststellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist oder ob sie gelöscht werden soll.</p><p>Beachten Sie bei der Anzeige dieser Spalte Folgendes:</p><ul><li>Diese Informationen enthalten keine Verwendung von API, Report Builder oder Data Warehouse.</li><li>Bei einigen Komponenten enthält diese Spalte möglicherweise keine Daten, wenn die Komponente zuletzt vor September 2023 verwendet wurde.</li><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li></ul><p>Sie können die [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen, damit Sie die Verwendung von Komponenten in Ihrem Unternehmen verfolgen und besser verstehen können. |

   {style="table-layout:auto"}
