---
title: Erstellen oder Bearbeiten einer Datenansicht
description: Alle Einstellungen, die Sie anpassen können, um eine Datenansicht zu erstellen oder zu bearbeiten.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: bab067f50e04b7eb1a211d8767cd2cd7a2acd9c5
workflow-type: tm+mt
source-wordcount: '1884'
ht-degree: 97%

---

# Erstellen oder Bearbeiten einer Datenansicht

Das Erstellen einer Datenansicht beinhaltet entweder das Erstellen von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in Customer Journey Analytics funktioniert.

+++ Sehen Sie sich ein Video an, in dem Datenansichten in Customer Journey Analytics veranschaulicht werden.

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

+++

So erstellen oder bearbeiten Sie eine Datenansicht:

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und gehen Sie zur Registerkarte **[!UICONTROL Datenansichten]**.
1. Um eine Datenansicht zu erstellen, wählen Sie **[!UICONTROL Neue Datenansicht erstellen]** aus. Sie können auch eine vorhandene Datenansicht aus der Liste der Datenansichten auswählen und diese bearbeiten.


## Konfigurieren {#configure}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_externalid"
>title="Externe ID"
>abstract="Das Ändern der externen ID kann sich darauf auswirken, wie der Name der Datenansicht in externen Quellen angezeigt wird, z. B. in Business-Intelligence-Tools."

<!-- markdownlint-enable MD034 -->


So konfigurieren Sie eine neue oder vorhandene Datenansicht:

1. Wählen Sie die Registerkarte **[!UICONTROL Konfigurieren]** aus (sofern noch nicht aktiv).

   ![Konfigurieren der Datenansicht](assets/dataview-configure.png)
1. Legen Sie Angaben für [!UICONTROL Einstellungen], [!UICONTROL Container] und [!UICONTROL Kalender] fest (siehe unten).
1. Wählen Sie **[!UICONTROL Speichern und fortfahren]** aus, um mit der Konfiguration der neuen oder vorhandenen Datenansicht fortzufahren. Wählen Sie **[!UICONTROL Speichern]** aus, um die Konfiguration für die vorhandene Datenansicht zu speichern.


### Einstellungen

Stellt übergreifende Einstellungen für die Datenansicht bereit.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL **Verbindung**] | In diesem Feld wird die Datenansicht mit der zuvor eingerichteten Verbindung verknüpft, die einen oder mehrere Adobe Experience Platform-Datensätze enthält. |
| [!UICONTROL **Name**] | Erforderlich. Der Name der Datenansicht. Dieser Wert wird in der Dropdown-Liste oben rechts in Analysis Workspace angezeigt. |
| [!UICONTROL **Externe ID**] | Erforderlich. Der Name der Datenansicht, die Sie in externen Quellen verwenden können, beispielsweise in Business-Intelligence-Tools. Der Standardwert ist `unspecified`. Wenn Sie keine externe ID angeben, wird der Name aus dem Namen der Datenansicht erstellt, wobei Leerzeichen durch Unterstriche ersetzt werden. |
| [!UICONTROL **Beschreibung**] | Optional. Adobe empfiehlt eine detaillierte Beschreibung, damit Benutzer verstehen, warum die Datenansicht vorhanden ist und für wen sie konzipiert ist. |

{style="table-layout:auto"}

### Kompatibilität {#compatibility}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_dataviewsinadobejourneyoptimizer"
>title="Datenansichten in Journey Optimizer"
>abstract="Customer Journey Analytics muss eine Verbindung und eine Datenansicht verwenden, die mit Adobe Journey Optimizer kompatibel sind. Standardmäßig werden zu diesem Zweck automatisch eine Verbindung und eine Datenansicht erstellt.<br/>Alternativ können Sie diese Option aktivieren, um dies zur standardmäßigen Datenansicht zu machen, die in Adobe Journey Optimizer-Berichten verwendet wird. Wenn diese Option aktiviert ist, werden alle für Journey Optimizer erforderlichen Komponenten dieser Datenansicht hinzugefügt und alle erforderlichen Journey Optimizer-Datensätze werden der mit dieser Datenansicht verknüpften Verbindung hinzugefügt."
>additional-url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/integrations/ajo#connection" text="Welche Komponenten und Datensätze hinzugefügt werden."

<!-- markdownlint-enable MD034 -->


Bietet Einstellungen, die angewendet werden können, wenn Adobe Journey Optimizer zusätzlich zu Customer Journey Analytics verwendet wird.

Dieser Abschnitt ist nur für Admins sichtbar, denen Journey Optimizer bereitgestellt wird.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL **Als Standard-Datenansicht in Adobe Journey Optimizer festlegen**] | Diese Konfigurationsoption standardisiert die Berichterstellung zwischen Journey Optimizer und Customer Journey Analytics. Sie können auch eine erweiterte Analyse Ihrer Adobe Journey Optimizer-Daten in Customer Journey Analytics durchführen (indem Sie in Journey Optimizer ![Öffnen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **In CJA analysieren**] auswählen).<p>Für die Durchführung dieser Art von Analyse benötigt Journey Optimizer Zugriff auf eine Customer Journey Analytics-Datenansicht.<p>Aktivieren Sie diese Option, um diese Datenansicht als Standardansicht für die Journey Optimizer-Berichterstellung für Ihre Sandbox zu verwenden.</p><p>Diese Konfigurationsoption führt Folgendes automatisch durch:</p><ul><li>Konfiguration alle rerforderlichen Journey Optimizer-Datensätze in der zugehörigen Verbindung in Customer Journey Analytics für die Verwendung mit Journey Optimizer.</li><li>Erstellung eines Satzes von Journey Optimizer-Metriken und -Dimensionen in der Datenansicht (einschließlich abgeleiteter Felder und berechneter Metriken). Kontextbezeichnungen werden für alle diese Metriken und Dimensionen automatisch festgelegt.</li></ul><p><p>Beachten Sie beim Aktivieren dieser Option Folgendes: <ul><li>Sie können die Standarddatenansicht zu einem späteren Zeitpunkt ändern. Hierdurch können sich jedoch Ihre Journey Optimizer-Berichtsdaten ändern.  Wenn Sie diese Option deaktivieren, nachdem sie aktiviert war, werden Sie aufgefordert, eine neue Standarddatenansicht auszuwählen.</li><li>Wenn Sie bereits manuelle Anpassungen an den Datensätzen, Dimensionen oder Metriken in der Customer Journey Analytics-Datenansicht vorgenommen haben, bleiben Ihre manuellen Anpassungen beim Aktivieren dieser Konfigurationsoption erhalten. Diese Option ermöglicht zusätzliche Anpassungen, die die Berichterstellung zwischen Journey Optimizer und Customer Journey Analytics weiter standardisieren. Sie können manuelle Anpassungen auch nach dem Aktivieren dieser Option vornehmen.</li></ul>Weitere Informationen finden Sie unter [Integrieren von Adobe Journey Optimizer mit Adobe Customer Journey Analytics](/help/integrations/ajo.md). |

{style="table-layout:auto"}

### Container

Gibt den Namen der Container für die Datenansicht an. Container-Namen werden häufig in [Filtern](/help/components/filters/filters-overview.md#Filter-containers) verwendet.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL **Container-Name für Person**] | [!UICONTROL Person] (Standard). Der Container [!UICONTROL Person] enthält sämtliche Sitzungen und Ereignisse für Personen innerhalb des angegebenen Zeitrahmens. Wenn Ihr Unternehmen einen anderen Begriff verwendet (z. B. „Besucher“ oder „Benutzer“), können Sie den Container hier umbenennen. |
| [!UICONTROL **Container-Name für Sitzung**] | [!UICONTROL Sitzung] (Standard). Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte [!UICONTROL Sitzung] identifiziert werden. Sie können diesen Container in „Besuch“ oder einen anderen von Ihrem Unternehmen bevorzugten Begriff umbenennen. |
| [!UICONTROL **Container-Name für Ereignis**] | [!UICONTROL Ereignis] (Standard). Der Container [!UICONTROL Ereignis] definiert einzelne Ereignisse in einem Datensatz. Wenn Ihr Unternehmen einen anderen Begriff verwendet (z. B. „Hits“ oder „Seitenansichten“), können Sie den Container hier umbenennen. |

{style="table-layout:auto"}

### Kalender

Gibt das Kalenderformat an, dem die Datenansicht folgen soll. Sie können mehrere Datenansichten basierend auf derselben [Verbindung](/help/connections/create-connection.md) haben und ihnen unterschiedliche Kalendertypen oder Zeitzonen zuweisen. Diese Datenansichten können es Teams, die verschiedene Kalendertypen verwenden, ermöglichen, ihre jeweiligen Anforderungen mit denselben zugrunde liegenden Daten zu erfüllen.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL **Zeitzone**] | Wählen Sie die Zeitzone aus, in der Ihre Daten angezeigt werden sollen. Wenn Sie eine Zeitzone auswählen, die mit der Sommerzeit arbeitet, werden die Daten automatisch entsprechend angepasst. Im Frühling, wenn die Uhren eine Stunde vor gestellt werden, besteht eine Lücke von einer Stunde. Im Herbst, wenn die Uhren eine Stunde zurück gestellt werden, wird während der Sommerzeit eine Stunde wiederholt. |
| [!UICONTROL **Kalendertyp**] | Bestimmen Sie, wie die Wochen des Monats gruppiert werden.<br>**Gregorianisch:** Standardkalenderformat. Die Quartale werden nach Monat gruppiert.<br>**4-5-4 Einzelhandel:** Ein standardisierter 4-5-4 Einzelhandelskalender. Der erste und der letzte Monat des Quartals enthalten 4 Wochen, während der zweite Monat des Quartals 5 Wochen umfasst.<br>**Benutzerspezifisch (4-5-4):** Ähnlich wie der 4-5-4-Kalender, mit dem Unterschied, dass Sie den ersten Tag des Jahres und das Jahr auswählen können, in dem die „zusätzliche“ Woche liegt.<br>**Benutzerspezifisch (4-4-5):** Der erste und zweite Monat jedes Quartals enthalten 4 Wochen, während die letzte Woche jedes Quartals 5 Wochen umfasst.<br>**Benutzerspezifisch (5-4-4):** Der erste Monat jedes Quartals umfasst 5 Wochen, während der zweite und dritte Monat jedes Quartals 4 Wochen umfassen. |
| [!UICONTROL **Erster Monat des Jahres**] und [!UICONTROL **Erster Wochentag**] | Sichtbar für den gregorianischen Kalender. Geben Sie an, mit welchem Monat das Kalenderjahr beginnen soll und mit welchem Tag jede Woche beginnen soll. |
| [!UICONTROL **Erster Tag des aktuellen Jahres**] | Für benutzerdefinierte Kalendertypen sichtbar. Geben Sie an, an welchem Tag des Jahres das aktuelle Jahr beginnen soll. Der Kalender formatiert automatisch den ersten Wochentag auf Grundlage dieses Werts. |
| [!UICONTROL **Jahr mit „zusätzlicher“ Woche**] | Bei den meisten 364-tägigen Kalendern (52 Wochen mit jeweils 7 Tagen) sammeln sich jedes Jahr verbleibende Tage, bis sie eine zusätzliche Woche ausmachen. Diese zusätzliche Woche wird dann zum letzten Monat des Jahres hinzugefügt. Geben Sie an, zu welchem Jahr die zusätzliche Woche hinzugefügt werden soll. |

{style="table-layout:auto"}

## Komponenten

Als Nächstes können Sie die Komponenten einer Datenansicht festlegen, d. h., Sie können Metriken und Dimensionen aus Schemaelementen erstellen. Sie können auch Standardkomponenten verwenden.

>[!IMPORTANT]
>
>Zu einer Datenansicht können bis zu 5.000 Metriken und 5.000 Dimensionen hinzugefügt werden.

1. Wählen Sie die Registerkarte **[!UICONTROL Komponenten]** aus.

   ![Registerkarte „Komponenten“](assets/dataview-components.png)

   Links oben sehen Sie die [!UICONTROL Verbindung], die die Datensätze enthält, und unten ihre [!UICONTROL Schemafelder].  Bei den bereits eingeschlossenen Komponenten handelt es sich um die (vom System generierten) Standardkomponenten, die für alle Datenansichten benötigt werden (z. B. Ereignisse, Personen, Sitzungsmetriken und die Dimensionen „Minute“, „Quartal“und „Woche“). Adobe wendet auch den Filter **[!UICONTROL Enthält Daten]** und **[!UICONTROL Ist nicht veraltet]** standardmäßig an, sodass nur Schemafelder angezeigt werden, die Daten enthalten und nicht veraltet sind.

1. Suchen Sie nach einem Schemafeld mit ![Suchsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Suchschemafeldern]** oder suchen Sie ein Feld, indem Sie in eine der Datensatzsammlungen wechseln, z. B. ![Ordnersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL Ereignisdatensätze]**.<br/>Alternativ können Sie über ![Datensymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Abgeleitetes Feld erstellen** ein abgeleitetes Feld erstellen. Weitere Informationen finden Sie unter [Abgeleitete Felder](./derived-fields/derived-fields.md).

1. Wenn Sie Ihr spezifisches Schemafeld gefunden oder Ihr abgeleitetes Feld definiert haben, ziehen Sie dieses Feld, z. B. ![Handle-Symbol](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Seitenname]**, aus der linken Leiste in den Bereich „Metriken“ oder „Dimensionen“.
Sie können dasselbe Schema mehrmals in die Bereiche „Dimensionen“ oder „Metriken“ ziehen und dieselbe Dimension bzw. Metrik auf unterschiedliche Weise konfigurieren. Beispielsweise können Sie im pageName-Feld eine Dimension namens „Produktseiten“ und eine weitere Dimension „Fehlerseiten“ erstellen, indem Sie rechts verschiedene [Komponenteneinstellungen](component-settings/overview.md) verwenden.
Wenn Sie einen Ordner mit Schemafeldern aus der linken Leiste ziehen, werden diese automatisch in typische Abschnitte unterteilt. Zeichenfolgenfelder landen im Abschnitt [!UICONTROL Dimensionen] und numerische Schematypen landen im Abschnitt [!UICONTROL Metriken]. Sie können auch auf **[!UICONTROL Alle hinzufügen]** klicken, dann werden alle Schemafelder zu ihren jeweiligen Speicherorten hinzugefügt.

1. Nachdem Sie eine Komponente ausgewählt haben, werden die Einstellungen auf der rechten Seite angezeigt.

   ![Ausgewählte Datenansichtskomponente](assets/dataview-component-pagename.png)

   Konfigurieren Sie die Komponente mit [Komponenteneinstellungen](component-settings/overview.md). Die verfügbaren Komponenteneinstellungen hängen davon ab, ob es sich bei der Komponente um eine Dimension/Metrik und um den Schemadatentyp handelt. Zu den Einstellungen gehören:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Verhalten]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Werte einschließen/ausschließen]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Deduplizierung der Metrik]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Keine Wertoptionen]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistenz]](component-settings/persistence.md)
   * [[!UICONTROL Wert-Bucketing]](component-settings/value-bucketing.md)

1. Wählen Sie **[!UICONTROL Speichern und fortfahren]** aus, um mit der Konfiguration der neuen oder vorhandenen Datenansicht fortzufahren. Wählen Sie **[!UICONTROL Speichern]** aus, um die Konfiguration für die vorhandene Datenansicht zu speichern.

**Duplizieren von Metriken oder Dimensionen**

Das Duplizieren von Metriken oder Dimensionen und das anschließende Ändern spezifischer Einstellungen ist eine einfache Möglichkeit, mehrere Metriken oder Dimensionen aus einem einzelnen Schemafeld zu erstellen. Wählen Sie die Einstellung [!UICONTROL Duplizieren] unter dem Namen der Metrik oder Dimension oben rechts aus. Ändern Sie dann die neue Dimension oder Metrik und speichern Sie sie unter einem aussagekräftigeren Namen.

**Filtern von Schemafeldern oder Datensätzen**

Sie können ![Filtersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) Schemafelder in der linken Leiste nach [!UICONTROL Datentyp], [!UICONTROL Datensätzen], [!UICONTROL Data Governance] und [!UICONTROL anderen] Kriterien ([!UICONTROL Enthält Daten], [!UICONTROL Ist Identität] und [!UICONTROL Ist nicht veraltet]) filtern:

![Filtern von Feldern](assets/dataview-components-filter.png)

>[!TIP]
>
>Wenn die Komponenten in Ihrer Datenansicht nicht ordnungsgemäß geladen werden und stattdessen eine Fehlermeldung angezeigt wird, lesen Sie bitte den Abschnitt [Fehlende Berechtigungen](../troubleshooting/lack-of-permissions.md), um das Problem zu beheben.



## Einstellungen

1. Wählen Sie die Registerkarte **[!UICONTROL Einstellungen]** aus.
1. Konfigurieren Sie Filter, die auf die gesamte Datenansicht angewendet werden sollen. Siehe [Einstellungen (Filter)](#settings-filters) unten.
1. Konfigurieren Sie Sitzungs-Timeout und Metriken. Siehe [Sitzungseinstellungen](#session-settings) unten.
1. Wählen Sie **[!UICONTROL Speichern und fortfahren]** aus, um mit der Konfiguration der neuen oder vorhandenen Datenansicht fortzufahren. Wählen Sie **[!UICONTROL Speichern]** aus, um die Konfiguration für die vorhandene Datenansicht zu speichern.

### Einstellungen (Filter)

Sie können Filter hinzufügen, die für die gesamte Datenansicht gelten. Dieser Filter wird auf alle Berichte angewendet, die Sie in Arbeitsbereich ausführen. Ziehen Sie einen Filter aus der Liste in das Feld [!UICONTROL Filter hinzufügen] in der linken Leiste.

### Sitzungseinstellungen

Legen Sie den Zeitraum der Inaktivität zwischen Ereignissen fest, bevor eine Sitzung abläuft und eine neue gestartet wird. Ein Zeitraum ist erforderlich. Sie können optional auch den Start einer neuen Sitzung erzwingen, wenn ein Ereignis eine bestimmte Metrik enthält. Siehe [Sitzungseinstellungen](session-settings.md) für weitere Details.

Nachdem alle gewünschten Einstellungen angegeben wurden, klicken Sie auf **[!UICONTROL Speichern und beenden]**.
