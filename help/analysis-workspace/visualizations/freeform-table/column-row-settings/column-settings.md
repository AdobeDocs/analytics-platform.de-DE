---
description: Erfahren Sie, wie Sie Spalteneinstellungen bearbeiten, um die Spaltenformatierung zu konfigurieren, von denen einige bedingt sein können.
title: Spalteneinstellungen
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 141c95b23695c09dd194c61c7cef0ce34e05ac33
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 21%

---

# [!UICONTROL Spalteneinstellungen]

[!UICONTROL Spalteneinstellungen] ermöglichen die Konfiguration der Spaltenformatierung, wobei einige davon bedingte Bedingungen sein können.


>[!BEGINSHADEBOX]

Siehe ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Zeilen- und Spalteneinstellungen in einer Freiformtabelle](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} für ein Demovideo.

{{videoaa}}

>[!ENDSHADEBOX]


Um auf [!UICONTROL Spalteneinstellungen] zuzugreifen, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in der Spaltenüberschrift aus.

![Spalteneinstellungen](assets/column-settings.png)


Sie können Einstellungen für mehrere Spalten gleichzeitig bearbeiten. Wählen Sie mehrere Spalten aus und wählen ![Einstellung](/help/assets/icons/Setting.svg) in einer der ausgewählten Spalten aus. Jede Änderung, die Sie vornehmen, gilt für alle Spalten, in denen Zellen ausgewählt sind.

| Option | Beschreibung |
| --- | --- |
| **[!UICONTROL Summe anzeigen]** | Zeigt eine Client-seitige Summe der Spalte an. Diese Gesamtzahl dedupliziert **Metriken wie Sitzungen** Personen nicht. |
| **[!UICONTROL Gesamtsumme anzeigen]** | Zeigt eine Server-seitige Summe der Spalte an. Die Gesamtsumme dedupliziert Metriken wie Sitzungen oder Personen. |
| **[!UICONTROL Sparkline anzeigen]** | Ein Liniendiagramm in der Spaltenüberschrift anzeigen. |
| **[!UICONTROL Nummer]** | Ermitteln Sie, ob eine Zelle den numerischen Wert für die Metrik ein- oder ausblendet. Ist die Metrik beispielsweise „Seitenansichten“, ist der numerische Wert die Anzahl an Seitenansichten für dieses Zeilenelement. |
| **[!UICONTROL Prozent]** | Ermitteln Sie, ob eine Zelle den Prozentwert für die Metrik anzeigt/ausblendet. Wenn die Metrik beispielsweise Seitenansichten lautet, ist der Prozentwert die Anzahl der Seitenansichten für das Zeilenelement dividiert durch die Gesamtzahl der Seitenansichten für die Spalte.  Hinweis: Prozentsätze über 100 % sind möglich, um Genauigkeit sicherzustellen. Die Obergrenze der Obergrenze kann auf 1.000 % verschoben werden, um zu verhindern, dass die Spaltenbreite zu groß wird. |
| **[!UICONTROL Anomalien anzeigen]** | Prüfen Sie, ob die Anomalieerkennung für die Werte in dieser Spalte ausgeführt wird. |
| **[!UICONTROL Prognose anzeigen]** | Stellen Sie fest, ob Prognosewerte in dieser Spalte angezeigt werden. |
| **[!UICONTROL Kopfzeilentext umbrechen]** | Betten Sie den Kopfzeilentext in Freiformtabellen ein, um die Lesbarkeit der Kopfzeilen und die Freigabe der Tabellen zu verbessern. Der Umbruch ist für das PDF-Rendering und für Metriken mit langen Namen nützlich. Standardmäßig aktiviert. |
| **[!UICONTROL Null nicht als Wert interpretieren]** | Legen Sie für Zellen mit dem Wert 0 fest, ob eine 0- oder eine leere Zelle angezeigt werden soll. Diese Interpretation ist nützlich, wenn Sie Daten für jeden Tag eines Monats betrachten, und einige Tage liegen in der Zukunft.  Statt 0 für zukünftige Datumsangaben werden stattdessen leere Zellen angezeigt. Diagramme berücksichtigen auch diese Einstellung (d. h. die Diagramme zeigen keine Linie oder keinen Balken mit 0 Werten an). |
| **[!UICONTROL Hintergrund]** | Ermitteln Sie, ob in einer Zelle alle Zellformatierungen ein-/ausgeblendet werden, einschließlich Balkendiagramm und bedingter Formatierung. |
| **[!UICONTROL Balkendiagramm]** | Ein horizontales Balkendiagramm anzeigen, das den Zellenwert im Verhältnis zur Gesamtsumme der Spalte darstellt. |
| **[!UICONTROL Bedingte Formatierung]** | Verwenden der bedingten Formatierung. Siehe [Abschnitt](#conditional-formatting) unten. |
| **[!UICONTROL Vorschau der Tabellenzelle]** | Eine Vorschau der Darstellung der einzelnen Zellen mit den aktuell ausgewählten Formatierungsoptionen. |
| **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** | Verwenden Sie ein nicht standardmäßiges Attributionsmodell. Siehe [Abschnitt](#use-non-default-attribution-model) unten. |

## Bedingte Formatierung {#conditional-formatting}

Die bedingte Formatierung gilt für Obergrenzen, Mittelwerte und Untergrenzen, die Sie definieren können. Das Anwenden bedingter Formatierung in Freiformtabellen wird auch bei Aufschlüsselungen automatisch aktiviert, es sei denn[!UICONTROL Benutzerdefinierte] Beschränkungen sind ausgewählt.

![Bedingte Formatierung](./assets/conditional-formatting.png)

| Bedingte Formatierungsoptionen | Beschreibung |
| --- | --- |
| **[!UICONTROL Prozentuale Limits verwenden]** | Ändern Sie das Limit, das auf Prozentsätzen basieren soll anstatt auf absoluten Werten. Der Bereich für die prozentuale Begrenzung funktioniert für Metriken, die ausschließlich prozentualbasiert sind (z. B. Absprungrate), und für Metriken, die eine Anzahl und einen Prozentsatz aufweisen (z. B. Seitenansichten). |
| **[!UICONTROL Automatisch generiert]** | Obere/mittlere/untere Limits automatisch auf Basis der Daten berechnen. Die Obergrenze entspricht dem höchsten Wert in dieser Spalte. Die Untergrenze entspricht dem niedrigsten Wert und der Mittelpunkt ist der Durchschnittswert der Ober- und der Untergrenze. |
| **[!UICONTROL Benutzerspezifisch]** | Weisen Sie **[!UICONTROL Obergrenze]**, **[!UICONTROL Mittelwert]** und **[!UICONTROL Untergrenze]** manuell zu. Beschränkungen bieten die Flexibilität, zu bestimmen, wann ein Spaltenwert gut, durchschnittlich oder schlecht wird. |
| **[!UICONTROL Bedingte Formatierungspalette]** | Wenden Sie einen vorkonfigurierten Farbsatz auf Zellen an. Je nachdem, welches der vier ausgewählten Farbschemata verwendet wird, werden hohen, mittleren und niedrigen Werten unterschiedliche Farben zugewiesen. <br> Wenn Sie eine Dimension in der Tabelle ersetzen, werden die Grenzwerte für die bedingte Formatierung zurückgesetzt. Wenn Sie eine Metrik ersetzen, werden die Grenzwerte für diese Spalte zurückgesetzt (dabei wird eine Metrik auf der X-Achse und eine Dimension auf der Y-Achse dargestellt). |

## Nicht standardmäßiges Attributionsmodell verwenden {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="Nicht standardmäßiges Attributionsmodell verwenden"
>abstract="Aktivieren Sie ein nicht standardmäßiges Attributionsmodell für die ausgewählten Spalten."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="Nicht standardmäßiges Attributionsmodell verwenden"
>abstract="Der nicht standardmäßige Attributionsmodus ist für diese Metrik nicht verfügbar."

<!-- markdownlint-enable MD034 -->



Sie können das standardmäßige Attributionsmodell überschreiben, das in &quot;[&quot; konfiguriert ](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Beachten Sie Folgendes, wenn Sie die Attribution einer Komponente auf ein nicht standardmäßiges Attributionsmodell aktualisieren:
>
>* **Bei Verwendung der Komponente in einem Bericht mit *einer einzelnen Dimension*:** Die Attribution der Komponente ignoriert das Zuordnungsmodell, wenn ein nicht standardmäßiges Attributionsmodell verwendet wird.
>
>* **Bei Verwendung der Komponente in einem Bericht mit *mehreren Dimensionen*:** Die Attribution der Komponente behält das Zuordnungsmodell bei, wenn ein nicht standardmäßiges Attributionsmodell verwendet wird.
>
>   Mehrere Dimensionen sind nur beim [Exportieren von Daten in die Cloud](/help/analysis-workspace/export/export-cloud.md) verfügbar.
>
> Weitere Informationen zur Zuordnung finden Sie unter [Persistenz - Komponenteneinstellungen](/help/data-views/component-settings/persistence.md).

So verwenden Sie ein nicht standardmäßiges Attributionsmodell für eine Metrik in einer Analysis Workspace:

1. Wählen **[!UICONTROL Nicht-standardmäßiges Attributionsmodell verwenden]**. Wenn Sie bereits ausgewählt sind, verwenden **[!UICONTROL Bearbeiten]**, um das Attributionsmodell zu bearbeiten. Oder heben Sie die Auswahl auf, um zum standardmäßigen Attributionsmodell zurückzukehren.

   ![Die Spalteneinstellungsoptionen, in denen die Option „Dateneinstellungen“ hervorgehoben ist: Verwenden Sie einen nicht standardmäßigen Attributionsmodus.](assets/attribution-checkbox.png)

2. Wählen **[!UICONTROL im]** Spalten-Attributionsmodell“ ein **[!UICONTROL Modell]** und ein **[!UICONTROL Lookback-Fenster]**. Das Lookback-Fenster bestimmt das Fenster der Datenattribution, das für jede Konversion angewendet wird.

   ![Die Optionen des Spalten-Attributionsmodells mit Linear ausgewählt.](assets/attribution-select.png)


### Attributionsmodelle

{{attribution-models-details}}

### Lookback-Fenster

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [Datenquellen verwalten](/help/analysis-workspace/visualizations/t-sync-visualization.md)
