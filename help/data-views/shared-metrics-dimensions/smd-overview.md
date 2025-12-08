---
title: Übersicht über freigegebene Metriken und Dimensionen
description: Verwenden Sie dieselbe Dimension oder Metrikreferenz für mehrere Datenansichten.
exl-id: 998a9f9b-cfa7-4b97-b32b-d50e35d01b39
source-git-commit: 1de8b8f40a7e1be0de0e6cbed5cc57ff834f2377
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---

# Übersicht über freigegebene Metriken und Dimensionen

Freigegebene Metriken und Dimensionen bieten einen zentralen Speicherort zum Verwalten von Dimensionen und Metriken, die in einer beliebigen Anzahl von Datenansichten verwendet werden können. Diese Komponenten sind besonders für Organisationen nützlich, die mehrere Datenansichten verwenden, insbesondere wenn diese Datenansichten gemeinsame Komponenteneinstellungen haben. Änderungen an freigegebenen Metriken und Dimensionen werden sofort auf alle Datenansichten angewendet, für die sie freigegeben sind. Beim Bearbeiten einer einzelnen Datenansicht können freigegebene Dimensionen und Metriken durch ein Symbol ![Freigegebene Komponente](/help/assets/icons/CCLibrary.svg) neben dem Komponentennamen identifiziert werden.

Freigegebene Dimensionen und Metriken ermöglichen zwar die Verwendung gemeinsamer Komponenten in vielen Datenansichten, sie können jedoch nicht verbindungsübergreifend freigegeben werden.

## Workflow

Die meisten Unternehmen verwenden den folgenden übergeordneten Workflow, um Dimensionen und Metriken im Zeitverlauf zu deduplizieren und zu verwalten:

1. Importieren Sie Komponenten aus jeder Datenansicht, die über mehrere Datenansichten hinweg freigegeben werden können. Wenn dieselbe Dimension oder Metrik in mehreren Datenansichten vorhanden ist, empfiehlt Adobe, alle Instanzen dieser Komponente zu importieren. Diese Best Practice importiert zwar Duplikate, diese werden jedoch so importiert, dass sie dedupliziert werden können und ihre jeweiligen Verweise auf Workspace-Projekte beibehalten werden.
1. Überprüfen Sie alle Komponenten, die dieselbe Komponenten-ID, aber unterschiedliche Komponenteneinstellungen verwenden. Wählen Sie für jede Gruppe doppelter Komponenten die gewünschten Komponenteneinstellungen aus, die auf alle anderen Komponenten mit dieser Komponenten-ID angewendet werden sollen.
1. Überprüfen Sie alle Komponenten, die dieselbe Komponenten-ID verwenden und dieselben Komponenteneinstellungen haben. Diese Dimensionen oder Metriken können einfach und sicher zusammengeführt werden.

## [!UICONTROL Freigegebene Metriken und Dimensionen] Manager

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Datenansichten]** > **[!UICONTROL Freigegebene Metriken und Dimensionen]**

Wenn Sie zu dieser Benutzeroberfläche navigieren, werden alle aktuellen Dimensionen und Metriken angezeigt, die für die Freigabe über mehrere Datenansichten hinweg verfügbar sind. Oben rechts befinden sich zwei Schaltflächen zum Hinzufügen von Komponenten zu dieser Benutzeroberfläche:

* **[!UICONTROL Importieren]**: Öffnet ein modales Fenster, in dem Sie eine Datenansicht auswählen und anschließend Komponenten auswählen können, die für die Freigabe zur Verfügung gestellt werden sollen.
* **[!UICONTROL Neu erstellen]**: Öffnet den [Freigegebenen Komponenten-Editor](shared-component-editor.md).

Direkt unter diesen beiden Schaltflächen sind vier Übersichtskarten zu sehen:

![Vorschau der Übersichtskarten](assets/overview-cards.png)

* **Metriken**: Die Gesamtzahl der Metriken, die für die Freigabe in Datenansichten für diese Verbindung verfügbar sind. Jede Verbindung kann bis zu 10.000 freigegebene Metriken enthalten.
* **Dimensionen**: Die Gesamtzahl der Dimensionen, die für die Freigabe in Datenansichten für diese Verbindung verfügbar sind. Jede Verbindung kann bis zu 10.000 gemeinsame Dimensionen enthalten.
* **Zu überprüfende Komponenten duplizieren**: Beim Importieren von Komponenten über mehrere Datenansichten hinweg können einige Dimensionen oder Metriken dieselbe Komponenten-ID aufweisen. Die Zahl in dieser Übersichtskarte zeigt die Gesamtzahl der Komponenten an, die dieselbe Komponenten-ID, aber unterschiedliche Komponenteneinstellungen haben. Wenn Sie **[!UICONTROL Überprüfen]** auswählen, können Sie einen Filter einrichten, mit dem Sie die gewünschte Komponente auswählen können, die als Datenquelle für alle anderen Komponenten mit derselben ID dient.
* **Komponenten können zusammengeführt werden**: Wenn eine Dimension oder Metrik dieselbe Komponenten-ID und dieselben Komponenteneinstellungen hat, sind sie effektiv identisch und können dedupliziert werden. Wenn Sie **[!UICONTROL Überprüfen]** auswählen, können Sie alle Komponenten mit derselben Komponenten-ID zu einer einzigen freigegebenen Dimension oder Metrik zusammenführen.

Alle freigegebenen Dimensionen und Metriken werden unter den vier Übersichtskarten angezeigt.

![Vorschau für verfügbare Dimensionen und Metriken](assets/shared-metrics-dimensions.png)

* **Filter**: Wählen Sie das Symbol ![Filter](../../assets/icons/Filter.svg) aus, um verfügbare Filter ein- oder auszublenden. Folgende Filter sind verfügbar:
   * **[!UICONTROL Komponententyp]**: Nur Dimensionen oder nur Metriken anzeigen.
   * **[!UICONTROL Datensatz]**: Nur Komponenten anzeigen, bei denen der Datensatz in den Datenansichten enthalten ist, für die eine Komponente freigegeben ist.
   * **[!UICONTROL Datenansicht]**: Nur Komponenten anzeigen, die für diese Datenansicht freigegeben sind.
   * **[!UICONTROL Erstellt von]**: Nur Komponenten anzeigen, die von einem bestimmten Benutzer erstellt wurden.
   * **[!UICONTROL Duplikate]**: Nur Komponenten anzeigen, die dieselbe Komponenten-ID wie eine andere Komponente haben. Diese Filter sind identisch mit dem Überprüfen von Komponenten über die Übersichtskarten.
* **Suche**: Verwenden Sie das Symbol ![Suchen](../../assets/icons/Search.svg), um nach einer Komponente anhand des Namens zu suchen.
* **[!UICONTROL Verbindung]**: Ein Dropdown-Menü, das die [Verbindung“ &#x200B;](/help/connections/overview.md). Freigegebene Dimensionen und Metriken sind immer spezifisch für eine einzelne Verbindung.
* **[!UICONTROL Tabelle anpassen]**: Wählen Sie das Symbol ![Tabelle anpassen](/help/assets/icons/ColumnSetting.svg) aus, um Spalten in der Tabelle ein- oder auszublenden. Zu den verfügbaren Optionen gehören:
   * **[!UICONTROL Feldname]**: Der Name der freigegebenen Dimension oder Metrik. Dieses Feld ist immer sichtbar.
   * **[!UICONTROL Typ]**: Gibt an, ob die Komponente eine Dimension oder eine Metrik ist. Dieses Feld ist immer sichtbar.
   * **[!UICONTROL Datensatztyp]**: Der Typ des Datensatzes. Die meisten Datensätze sind Ereignis-Datensätze.
   * **[!UICONTROL Für Datenansicht freigegeben]**: Alle Datenansichten, für die diese Komponente freigegeben ist. Dieses Feld ist immer sichtbar. Wählen Sie den Link aus, um ein modales Fenster zu öffnen, in dem alle Datenansichten aufgelistet werden, in denen diese Komponente verfügbar ist.
   * **[!UICONTROL Datensätze]**: Alle Datensätze, die in jeder Datenansicht enthalten sind, für die diese Komponente freigegeben ist. Wählen Sie den Link aus, um ein modales Fenster zu öffnen, in dem alle Datensätze für die Komponente aufgelistet werden.
   * **[!UICONTROL Erstellt von]**: Der Name der Person, die die Komponente erstellt oder in die Oberfläche für freigegebene Metriken und Dimensionen importiert hat.
   * **[!UICONTROL Schematyp]**: Das Format, in dem Daten gespeichert werden. Beispiele sind `string`, `double` oder `boolean`.
   * **[!UICONTROL Komponenten-]**: Die Komponenten-ID der Dimension oder Metrik. Alle Komponenten, die in dieser Benutzeroberfläche dieselbe Komponenten-ID aufweisen, müssen überprüft und dedupliziert werden.
   * **[!UICONTROL Schema]**: Der Schemapfad für die Dimension oder Metrik. Zum Beispiel `web.webPageDetails.URL`.
   * **[!UICONTROL Beschreibung]**: Die [Beschreibung](/help/data-views/component-settings/overview.md) der Komponente.
   * **[!UICONTROL Kontextkennzeichnungen]**: Die [Kontextkennzeichnungen](/help/data-views/component-settings/overview.md) für die Komponente.
   * **[!UICONTROL Werte einschließen/ausschließen]**: Listet die Anzahl der Regeln auf, die unter &quot;[/ausschließen](/help/data-views/component-settings/include-exclude-values.md) angegeben sind.
   * **[!UICONTROL Datennutzungsbezeichnungen]**: Die [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/de/docs/experience-platform/data-governance/labels/overview) für das Schemafeld.
   * **[!UICONTROL Veraltet]**: Gibt an, ob das veraltete Flag gesetzt ist.
   * **[!UICONTROL Format]**: Das Format, in dem Werte angezeigt werden. Boolesche Werte werden in der Regel als `True | False`, Metriken als `Decimal` usw. angezeigt.
   * **[!UICONTROL Metrik-Deduplizierung]**: Die [Metrik-Deduplizierung](/help/data-views/component-settings/metric-deduplication.md) der Komponente.
   * **[!UICONTROL Verhalten]**: Die Einstellungen [Verhalten](/help/data-views/component-settings/behavior.md) der Komponente.
   * **[!UICONTROL Attribution]**: Die Einstellungen [Attribution](/help/data-views/component-settings/attribution.md) der Komponente.
   * **[!UICONTROL Option „Kein Wert]**: Die [Optionen für keinen Wert](/help/data-views/component-settings/no-value-options.md).
   * **[!UICONTROL Wert-Bucketing]**: Die Einstellungen [Wert-Bucketing](/help/data-views/component-settings/value-bucketing.md) der Komponente.
   * **[!UICONTROL Persistenz]**: Die Einstellungen [Persistenz](/help/data-views/component-settings/persistence.md) der Komponente.
   * **[!UICONTROL Kleinbuchstaben]**: Gibt an, ob die Komponente basierend auf den Einstellungen (Verhalten[&#x200B; der Komponente &#x200B;](/help/data-views/component-settings/behavior.md) Kleinbuchstaben aktiviert ist.
   * **[!UICONTROL Teilzeichenfolge]**: Die Einstellungen [Teilzeichenfolge](/help/data-views/component-settings/substring.md) der Komponente.
   * **[!UICONTROL Zusammenfassungsdatengruppe]**: Die Einstellungen [Zusammenfassungsdatengruppe“ &#x200B;](/help/data-views/component-settings/summary-data-group.md) Komponente.
   * **[!UICONTROL Erstellungsdatum]**: Das Datum, an dem die Komponente erstellt oder importiert wurde.
   * **[!UICONTROL Zuletzt geändert]**: Wenn die Komponente nach ihrer Erstellung geändert wurde, das Datum der letzten Änderung.
* **[!UICONTROL Vorgangsverlauf]**: Wenn Sie eine große Anzahl von Komponenten importieren oder freigeben, wird automatisch ein Vorgang erstellt. Wählen Sie das Symbol ![Verlauf](/help/assets/icons/History.svg) aus, um ein modales Fenster zu öffnen, das alle Instanzen des Imports von Dimensionen und Metriken aus einzelnen Datenansichten anzeigt. Wenn keine der Import- oder Freigabeaktionen groß genug ist, um einen Auftrag Trigger, wird diese Schaltfläche nicht angezeigt.

## Bearbeiten von Komponenten oder Freigeben von Komponenten für Datenansichten

Aktivieren Sie das Kontrollkästchen neben einer Komponente, um alle verfügbaren Aktionen anzuzeigen, die Sie ausführen können. Es werden mehrere Auswahlmöglichkeiten unterstützt.

![Vorschau der verfügbaren Aktionen](assets/smd-actions.png)

* ![Bleistiftsymbol](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]**: Öffnen Sie die ausgewählten Dimensionen und Metriken im [freigegebenen Komponenten-Editor](shared-component-editor.md), mit dem Sie ihre [&#x200B; anpassen können](/help/data-views/component-settings/overview.md). Wenn Sie mehrere Komponenten zur Bearbeitung auswählen, werden sie alle im Komponenten-Editor geöffnet. Sie können im Komponenten-Editor Komponenten umschalten und auf sie klicken, um dasselbe Feld für mehrere Komponenten zu bearbeiten.
* ![Freigabesymbol](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Für Datenansicht(en) freigeben]**: Öffnet ein Fenster, das alle in der ausgewählten Verbindung verfügbaren Datenansichten anzeigt. Aktivieren Sie das Kontrollkästchen für jede Datenansicht, in der Sie diese Komponente verfügbar machen möchten, und klicken Sie dann auf **[!UICONTROL Freigeben]**.
* ![Symbol „Freigabe aufheben](/help/assets/icons/SaveTo.svg) **[!UICONTROL Freigabe für Datenansicht(en) aufheben]**: Öffnet ein Fenster, das alle Datenansichten anzeigt, für die diese Komponente derzeit freigegeben ist. Aktivieren Sie das Kontrollkästchen für jede Datenansicht, aus der Sie die Verfügbarkeit dieser Komponente entfernen möchten, und klicken Sie dann auf **[!UICONTROL Freigabe aufheben]**.
* ![Symbol „Duplizieren](/help/assets/icons/Copy.svg) **[!UICONTROL Duplizieren]**: Erstellt eine Kopie der ausgewählten Komponenten. Für duplizierte Komponenten wird eine neue Komponenten-ID generiert.
* ![Löschsymbol](/help/assets/icons/Delete.svg) **[!UICONTROL Löschen]**: Entfernt die ausgewählten Komponenten aus der Benutzeroberfläche. Wenn die ausgewählten Komponenten für Datenansichten freigegeben sind, werden sie aufgehoben.
