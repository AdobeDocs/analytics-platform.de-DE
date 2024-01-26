---
description: Der Manager für berechnete Metriken bietet verschiedene Möglichkeiten zum Kuratieren von Metriken, wie das Freigeben, Filtern, Taggen, Genehmigen, Kopieren, Löschen und Kennzeichnen als Favoriten.
title: Manager für berechnete Metriken
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: e84010b9ea9e6385574e8b1a04f7eccbba3ebc90
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 12%

---

# Manager für berechnete Metriken

Die Seite &quot;Berechnete Metrik&quot;bietet viele Möglichkeiten zum Kuratieren von Metriken, z. B. Freigeben, Filtern, Taggen, Genehmigen, Kopieren, Löschen und Kennzeichnen als Favoriten.

Der Manager für berechnete Metriken zeigt Ihnen alle Filter an, deren Inhaber Sie sind und die für Sie freigegeben wurden. Benutzer auf Administratorebene sehen alle benutzerdefinierten Metriken der Organisation. In dieser Übersicht werden die Benutzeroberfläche und die Funktionen des Managers für berechnete Metriken vorgestellt.

![Fenster für berechnete Metriken mit verfügbaren Filtern.](assets/calc-metric-manager.png)

## Zugriff auf den Manager für berechnete Metriken

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Berechnete Metriken**].

## Verfügbare Aktionen im Manager für berechnete Metriken

Im Manager für berechnete Metriken haben Sie folgende Möglichkeiten:

* [Berechnete Metriken filtern](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Berechnete Metriken als Favoriten markieren](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Berechnete Metriken genehmigen](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Berechnete Metriken taggen](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportieren Sie eine berechnete Metrik in eine CSV-Datei.

* [Berechnete Metriken kopieren](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Berechnete Metriken löschen

## Spalten konfigurieren

Sie können die für jede berechnete Metrik angezeigten Informationen im Manager für berechnete Metriken konfigurieren, indem Sie die angezeigten Spalten konfigurieren.

So konfigurieren Sie die sichtbaren Spalten im Manager für berechnete Metriken:

1. Wählen Sie unter Customer Journey Analytics die **[!UICONTROL Komponenten]** Registerkarte und wählen Sie **[!UICONTROL Berechnete Metriken]**.

1. Wählen Sie im Manager für berechnete Metriken die **Spalten anpassen** icon ![Symbol &quot;Spalten anpassen&quot;](assets/customize-columns-icon.png)und wählen Sie dann die Spalten aus, die im Manager für berechnete Metriken angezeigt werden sollen.

   Die folgenden Spalten sind verfügbar:

   | Spaltentitel | Beschreibung |
   |---|---|
   | Favoriten | Zeigt neben jeder berechneten Metrik Sternensymbole an, mit denen Sie berechnete Metriken als Favoriten markieren können. Weitere Informationen finden Sie unter [Berechnete Metriken als Favoriten markieren](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Titel und Beschreibung | Diese Werte werden im Generator für berechnete Metriken bereitgestellt. Um den Titel und die Beschreibung zu bearbeiten, wählen Sie den Titel-Link aus, um den Generator für berechnete Metriken zu öffnen. |
   | Report Suite | Gibt an, in welcher Report Suite die Metrik zuletzt gespeichert wurde. |
   | Inhaber | Gibt den Inhaber der benutzerdefinierten Metrik an. Als Benutzer ohne Administratorrechte können Sie nur Metriken sehen, deren Inhaber Sie sind, sowie Metriken, die für Sie freigegeben wurden. |
   | Tags | Zeigt Tags an, die entweder von Ihnen oder von Personen, die die berechnete Metrik für Sie freigegeben haben, auf die Metrik angewendet wurden. |
   | Freigegeben für | Listet Personen oder Gruppen (nur Administrator) oder Alle (nur Administrator) auf, für die Sie die berechnete Metrik freigegeben haben. <p>Wenn eine berechnete Metrik freigegeben wird, wird neben dem Namen der berechneten Metrik ein Freigabesymbol angezeigt.</p> |
   | Änderungsdatum | Gibt das Datum der letzten Änderung der benutzerdefinierten Metrik an. |
   | Verwendet in | Zeigt an, in wie vielen Komponenten die berechnete Metrik derzeit verwendet wird. <p>Wenn die berechnete Metrik beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**].</p> <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung der Verwendung der berechneten Metrik anzuzeigen (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **Warnhinweise (2)**]).</p><p>Berechnete Metriken können in einem der folgenden Komponententypen verwendet werden:</p> <ul><li>Projekte</li><li>Geplante Projekte</li></ul><p>Diese Informationen können Ihnen dabei helfen festzustellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss.</p><p>Beachten Sie bei der Anzeige dieser Spalte Folgendes:</p><ul><li>Diese Informationen enthalten keine Verwendung von API, Report Builder oder Data Warehouse.</li><li>Die [!UICONTROL **Verwendet in**] -Spalte wird nicht standardmäßig angezeigt. [Spalten konfigurieren](#configure-columns) , um es anzuzeigen.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, aber eine [!UICONTROL **Zuletzt verwendet**] Datum, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li></ul><p>Sie können die [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen, damit Sie die Verwendung von Komponenten in Ihrem Unternehmen verfolgen und besser verstehen können.</p> |
   | Zuletzt verwendet | Zeigt das Datum an, an dem die berechnete Metrik zuletzt in einem der folgenden Komponententypen verwendet wurde: <ul><li>Berechnete Metriken </li><li>Projekte</li><li>Geplante Projekte</li></ul> <p>Anhand dieser Informationen können Sie feststellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist oder ob sie gelöscht werden soll.</p><p>Beachten Sie bei der Anzeige dieser Spalte Folgendes:</p><ul><li>Diese Informationen enthalten keine Verwendung von API, Report Builder oder Data Warehouse.</li><li>Bei einigen Komponenten enthält diese Spalte möglicherweise keine Daten, wenn die Komponente zuletzt vor September 2023 verwendet wurde.</li><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li></ul><p>Sie können die [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen, damit Sie die Verwendung von Komponenten in Ihrem Unternehmen verfolgen und besser verstehen können. |

   {style="table-layout:auto"}
