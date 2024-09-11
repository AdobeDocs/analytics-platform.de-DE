---
description: Der Manager für berechnete Metriken bietet verschiedene Möglichkeiten zum Kuratieren von Metriken, wie das Freigeben, Filtern, Taggen, Genehmigen, Kopieren, Löschen und Kennzeichnen als Favoriten.
title: Manager für berechnete Metriken
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: 94a8589378b1aee2b6cc8371f92b3f9801ed1ec3
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 13%

---

# Manager für berechnete Metriken

Die Seite &quot;Berechnete Metrik&quot;bietet viele Möglichkeiten zum Kuratieren von Metriken, z. B. Freigeben, Filtern, Taggen, Genehmigen, Kopieren, Löschen und Kennzeichnen als Favoriten.

Der Manager für berechnete Metriken zeigt Ihnen alle Filter an, deren Inhaber Sie sind und die für Sie freigegeben wurden. Benutzer auf Administratorebene sehen alle benutzerdefinierten Metriken der Organisation. In dieser Übersicht werden die Benutzeroberfläche und die Funktionen des Managers für berechnete Metriken vorgestellt.

![Fenster für berechnete Metriken mit verfügbaren Filtern.](assets/calc-metric-manager.png)

## Zugriff auf den Manager für berechnete Metriken

1. Wählen Sie unter Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Berechnete Metriken**] aus.

## Verfügbare Aktionen im Manager für berechnete Metriken

Im Manager für berechnete Metriken haben Sie folgende Möglichkeiten:

* [Berechnete Metriken filtern](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Berechnete Metriken als Favoriten markieren](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Berechnete Metriken genehmigen](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Berechnete Metriken taggen](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportieren Sie eine berechnete Metrik in eine CSV-Datei.

* [Kopieren von berechneten Metriken](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Berechnete Metriken löschen

## Spalten konfigurieren

Sie können die für jede berechnete Metrik angezeigten Informationen im Manager für berechnete Metriken konfigurieren, indem Sie die angezeigten Spalten konfigurieren.

So konfigurieren Sie die sichtbaren Spalten im Manager für berechnete Metriken:

1. Wählen Sie unter Customer Journey Analytics die Registerkarte **[!UICONTROL Komponenten]** und dann **[!UICONTROL Berechnete Metriken]** aus.

1. Wählen Sie im Manager für berechnete Metriken das Symbol **Spalten anpassen** ![Spaltensymbol anpassen](assets/customize-columns-icon.png) und wählen Sie dann die Spalten aus, die im Manager für berechnete Metriken angezeigt werden sollen.

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
   | Verwendet in | Zeigt an, wo berechnete Metriken derzeit verwendet werden und wie oft sie in den einzelnen Bereichen verwendet werden. <p>Wenn die berechnete Metrik beispielsweise in 40 Projekten und 2 Warnhinweisen verwendet wird, wird der Wert dieser Spalte als [!UICONTROL **42 Komponenten**] angezeigt. <p>Wählen Sie den Wert in dieser Spalte aus, um die Aufschlüsselung der Verwendung der berechneten Metriken anzuzeigen (z. B. [!UICONTROL **Projekte (40)**], [!UICONTROL **mobile Scorecards (2)**]). Darüber hinaus können Sie die Liste der Elemente anzeigen, in denen die berechneten Metriken verwendet werden. Sehen Sie sich beispielsweise die Liste der Projekte an, in denen sie verwendet werden, und klicken Sie auf den Link [!UICONTROL **Projekte (40)**] .</p><p>Jeder der folgenden Bereiche zeigt die Anzahl der Instanzen berechneter Metriken, die in diesem Bereich verwendet werden:</p> <ul><li>[!UICONTROL **Projekte**]<p>Enthält berechnete Metriken, die im Generator für berechnete Metriken ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) erstellt wurden und für alle Projekte verfügbar sind.[</p></li><li>[!UICONTROL **Ad-hoc-Komponenten**]<p>Enthält berechnete Metriken, die [ als schnell berechnete Metriken erstellt wurden](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) und nur in einem einzelnen Projekt verfügbar sind.</p></li><li>[!UICONTROL **Geplante Projekte**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Anmerkungen**]</li><li>[!UICONTROL **Report Builder**]<p>Bei Auswahl dieser Option wird eine CSV-Datei mit den folgenden Datenspalten heruntergeladen:</p><ul><li>Name des Report Builders</li><li>Zuletzt aufgerufen</li><li>Letzter Zugriff auf IMS-Benutzer-ID</li><li>Letzter Benutzername</li></ul></li></ul><p>Diese Informationen können Ihnen dabei helfen festzustellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss.</p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li><li>Die Spalte [!UICONTROL **Verwendet in**] wird nicht standardmäßig angezeigt. [Konfigurieren Sie Spalten](#configure-columns), um sie anzuzeigen.</li><li>Diese Informationen enthalten keine Verwendung über die API oder Data Warehouse.</li><li>Wenn in dieser Spalte keine Daten für eine bestimmte Komponente vorhanden sind, sie jedoch das Datum [!UICONTROL **Zuletzt verwendet**] hat, wurde die Komponente möglicherweise in einer Analyse verwendet, ohne gespeichert zu werden.</li><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen.</p> |
   | Zuletzt verwendet | Zeigt das Datum an, an dem die berechnete Metrik zuletzt in einem der folgenden Komponententypen verwendet wurde: <ul><li>Berechnete Metriken </li><li>Projekte</li><li>Geplante Projekte</li></ul> <p>Anhand dieser Informationen können Sie feststellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist oder ob sie gelöscht werden soll.</p><p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Diese Informationen enthalten keine Verwendung von API, Report Builder oder Data Warehouse.</li><li>Bei einigen Komponenten enthält diese Spalte möglicherweise keine Daten, wenn die Komponente zuletzt vor September 2023 verwendet wurde.</li><li>Diese Informationen sind nur für Systemadministratoren verfügbar.</li></ul><p>Sie können das [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrer Organisation zu verfolgen und besser zu verstehen. |

   {style="table-layout:auto"}
