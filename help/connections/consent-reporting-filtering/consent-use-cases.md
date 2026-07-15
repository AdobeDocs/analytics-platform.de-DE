---
title: Anwendungsfälle für Einverständnisberichte und -filterung
description: Erkunden Sie Anwendungsfälle für das Reporting über die Zugehörigkeit zu einer Besuchereinverständnisrichtlinie und das Filtern von Besuchern, die nicht zustimmen, bei der Aufnahme in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 585
ht-degree: 0%

---

# Anwendungsfälle für Einverständnisberichte und -filterung

Mithilfe des Einverständnisberichts und der -filterung können Sie Berichte zur Mitgliedschaft in Einverständnisrichtlinien erstellen und Besucher, die nicht ihr Einverständnis gegeben haben, optional ausschließen, bevor ihre Daten in Customer Journey Analytics eingehen. Übersichtsinformationen finden Sie unter [Übersicht über Einverständnisberichte und -filter](/help/connections/consent-reporting-filtering/consent-overview.md).

In diesem Artikel werden beispielhafte Anwendungsfälle beschrieben. Bevor Sie sie überprüfen, machen Sie sich mit den folgenden Überlegungen vertraut, da sie sich auf die Ergebnisse auswirken, die Sie in Ihren Berichten sehen.

## Überlegungen zum Reporting

* **Filterung gilt für die Verbindungsebene**: Wenn Sie die Filterung aktivieren, erben alle Datenansichten unter der konfigurierten Verbindung dasselbe Verhalten. Sie können eine Datenansicht unter einer Verbindung nicht anders filtern als eine andere.

* **Filterung verwendet Einschlusslogik**: Die Daten eines Besuchers werden nur aufgenommen, wenn der Besucher allen Einverständnisrichtlinien entspricht, die für die aktivierten Marketing-Aktionen gelten. Ein Besucher, dem eine gültige Richtlinie fehlt, wird ausgeschlossen.

* **Ausgeschlossene Daten können nicht wiederhergestellt werden**: Da die Filterung zum Zeitpunkt der Aufnahme erfolgt, werden ausgeschlossene Daten nicht in Customer Journey Analytics gespeichert. Wenn Sie Ihre Konfiguration später ändern, werden ausgeschlossene Daten für vergangene Daten nicht wiederhergestellt.

* **Die Einverständnisrichtlinienmitgliedschaft stammt aus dem Profildatensatz**: Die Berichterstellung spiegelt die im Feld &quot;`consentPoliciesIDMap`&quot; des Profildatensatzes vorhandene Einverständnisrichtlinienmitgliedschaft wider. Ein Besucher muss über ein entsprechendes Ereignis in der Verbindung verfügen, damit es im Reporting angezeigt wird.

## Beispielhafte Anwendungsfälle

### Anwendungsfall 1: Einverständnisbericht ohne Datenfilterung

Erfahren Sie, wie viele Besucher den einzelnen Zustimmungsrichtlinien entsprechen, bevor Sie entscheiden, ob Sie filtern oder Fragen wie diese beantworten möchten:

* _„Wie viele unserer Besucher haben der Verwendung von Analytics zugestimmt?“_
* _„Welche Einverständnisrichtlinien decken unsere Besucher am meisten und am wenigsten ab?“_

**Konfigurationsfluss:**

1. Erstellen Sie eine Konfiguration und wählen Sie die Sandbox, den Profildatensatz und die Verbindung aus, die die Mitgliedschaftsdaten Ihrer Einverständnisrichtlinie enthalten.

1. Lassen Sie sowohl **[!UICONTROL Analytics]** als auch **[!UICONTROL Datenwissenschaft]** die Filterung deaktiviert.

1. Erstellen Sie in Analysis Workspace eine Freiformtabelle mit der Dimension **[!UICONTROL Richtlinienname]** und der Metrik **[!UICONTROL Besucher mit Einverständnis]**, um die Abdeckung pro Richtlinie anzuzeigen.

Verwenden Sie diese Einblicke, um zu entscheiden, ob die Filterung aktiviert werden soll und für welche Marketing-Aktionen.

### Anwendungsfall 2: Ausschließen von Besuchern, die nicht ihr Einverständnis erklärt haben, aus Analytics-Berichten

Stellen Sie sicher, dass Standardberichte nur Besucher enthalten, die der Verwendung von Analytics zugestimmt haben, um Fragen wie diese zu beantworten:

* _„Wie verhält sich unsere Zielgruppe, wenn wir nur über einvernehmliche Besucher berichten?“_
* _„Können wir sicherstellen, dass Besucherdaten, die keine Zustimmung einholen, nie in unsere Analytics-Berichte aufgenommen werden?“_

**Konfigurationsfluss:**

1. Erstellen oder bearbeiten Sie eine Konfiguration für die Verbindung, die Ihre Analytics-Berichte unterstützt.

1. Aktivieren Sie den **[!UICONTROL Analytics]**-Umschalter.

1. Bestätigen Sie die Konfiguration. Ab diesem Zeitpunkt nimmt Customer Journey Analytics die Daten eines Besuchers nur noch dann auf, wenn der Besucher allen Einverständnisrichtlinien entspricht, die für die Analytics-Marketing-Aktion gelten.

Da die Filterung zum Zeitpunkt der Aufnahme erfolgt, spiegeln nachgelagerte Berichte, Exporte und APIs automatisch nur einvernehmliche Besucherinnen und Besucher wider, ohne dass Änderungen zur Berichtszeit erforderlich sind.

### Anwendungsfall 3: Filtern von Anwendungsfällen für Analyse und Datenwissenschaft unabhängig

Wenden Sie verschiedene Einverständnisanforderungen auf standardmäßige Berichte und datenwissenschaftliche Anwendungsfälle an, um Fragen wie diese zu beantworten:

* _„Können wir eine breitere Gruppe von Besuchern in Analytics einbeziehen und gleichzeitig eine strengere Einwilligung für maschinelles Lernen anwenden?“_

**Konfigurationsfluss:**

1. Erstellen oder bearbeiten Sie eine Konfiguration für die entsprechende Verbindung.

1. Aktivieren Sie **[!UICONTROL Umschalter]** Analytics“, den Umschalter **[!UICONTROL Datenwissenschaft]** oder beides, je nach den Einverständnisanforderungen für jeden Anwendungsfall.

1. Bestätigen Sie die Konfiguration. Customer Journey Analytics bewertet die Einverständnisrichtlinien, die für jede aktivierte Marketing-Aktion gelten, unabhängig.

Verwenden Sie diesen Ansatz, wenn Ihr Unternehmen unterschiedliche Einverständnisanforderungen auf verschiedene Kategorien der Datennutzung anwendet.
