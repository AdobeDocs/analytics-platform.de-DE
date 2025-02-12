---
title: Geführte Konfiguration für Content Analytics
description: Konfigurieren von Content Analytics mithilfe einer geführten Onboarding-Konfiguration
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 3bf62bebebfe2ef52abbd29245ef6e8e65807491
workflow-type: tm+mt
source-wordcount: '1856'
ht-degree: 10%

---

# Geführte Konfiguration für Content Analytics

>[!WARNING]
>
>Dieser Artikel ist eine vorläufige inoffizielle Entwurfsversion einer kommenden endgültigen Version und Teil der Inhaltsanalysedokumentation. Alle Inhalte unterliegen Änderungen und es können keinerlei rechtlichen Verpflichtungen aus der aktuellen Version dieses Artikels abgeleitet werden.
>

{{release-limited-testing}}

Mit der geführten Konfiguration können Sie Content Analytics schnell und einfach konfigurieren. Die geführte Konfiguration verwendet einen Assistenten, um die Anforderungen für die automatische Konfiguration von Content Analytics für Ihr Unternehmen einzurichten. Im Bildschirm **[!UICONTROL Konfiguration]** können Sie entweder eine neue Konfiguration erstellen oder eine vorhandene Konfiguration bearbeiten.

>[!IMPORTANT]
>
>Pro Sandbox kann in Ihrer Organisation nur eine Inhaltsanalysekonfiguration verwendet werden.


So greifen Sie auf die Content Analytics-Konfiguration zu

* Wählen **[!UICONTROL Daten-Management]** > **[!UICONTROL Inhaltsanalyse]** aus dem Hauptmenü in Customer Journey Analytics.

Im Bildschirm „Content Analytics-Konfiguration“ sehen Sie eine Tabelle der vorhandenen Content Analytics-Konfigurationen.

![Inhaltsanalysekonfigurationen](../assets/aca-configuration-table.png)
Für jede Konfiguration stehen die folgenden Details zur Verfügung:

| Spalte | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Der Name der Konfiguration. |
| **[!UICONTROL Erstellt von]** | Das technische Konto, das die Konfiguration erstellt hat. |
| **[!UICONTROL Erstellt am]** | Der Zeitstempel, zu dem die Konfiguration erstellt wurde. |
| **[!UICONTROL Geändert am]** | Der Zeitstempel, wann die Konfiguration zuletzt geändert wurde. |
| **[!UICONTROL Sandbox]** | Die Sandbox in der Organisation, in der Content Analytics konfiguriert (geplant) und implementiert wird. |
| **[!UICONTROL Status]** | Der Status der Konfiguration. Der Status kann lauten: <br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]**: Die Konfiguration wird für später gespeichert und nicht bereitgestellt.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**: Die Konfiguration ist fehlgeschlagen. Sie müssen die Konfiguration bearbeiten und die erforderlichen Änderungen vornehmen.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: Die Konfiguration wurde abgeschlossen und erfolgreich implementiert. |

Sie können &quot;![&quot; verwenden](/help/assets/icons/ColumnSetting.svg) um die Tabelle anzupassen. Wählen Sie aus, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]**, um die Änderungen anzuwenden.

Auf dem Bildschirm Inhaltsanalysekonfiguration **[!UICONTROL Konfiguration]** können Sie eine neue Konfiguration erstellen oder eine vorhandene Konfiguration bearbeiten.

So erstellen Sie eine neue Konfiguration:

* Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus. Diese Aktion öffnet den Assistenten für geführte Konfigurationen.

So bearbeiten Sie eine vorhandene Konfiguration:

* Wählen Sie ![Mehr](/help/assets/icons/More.svg) und dann ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** für eine vorhandene Content Analytics-Konfiguration aus. Diese Aktion öffnet den Assistenten für geführte Konfigurationen.

## Assistent für geführte Konfigurationen

Der Assistent für geführte Konfigurationen besteht aus vier Abschnitten ([Details](#details), [Datenansicht](#data-view), [Erlebniserfassung und -definition](#experience-capture-and-definition) und [Datenerfassung](#data-collection)), in denen Sie aufgefordert werden, die zum ordnungsgemäßen Einrichten und Konfigurieren von Content Analytics erforderlichen Details anzugeben. Schließen Sie jeden Abschnitt ab, bevor Sie zum nächsten Abschnitt wechseln, da einige Einstellungen in einem Abschnitt möglicherweise von den Konfigurationswerten in früheren Abschnitten abhängen.

### Details {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Details"
>abstract="Geben Sie einen Namen für die Verbindung an. In den **[!UICONTROL Datenansicht]**, **[!UICONTROL Erlebniserfassung und -definition]** und **[!UICONTROL Datenerfassung]** geben Sie weitere Details an, um sicherzustellen, dass die Inhaltsanalyse korrekt konfiguriert werden kann."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Details"
>abstract="In dieser Anleitung werden die Anforderungen für die Konfiguration der Inhaltsanalyse festgelegt. Geben Sie einen Namen für diese Konfiguration an."

<!-- markdownlint-enable MD034 -->

Jede Konfiguration erfordert einen eindeutigen Namen. Zum Beispiel `Example Content Analytics configuration`.

![Konfigurationsdetails von Content Analytics](../assets/aca-configuration-details.png)


### Datenansicht {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Datenansicht"
>abstract="Für die Konfiguration von Content Analytics müssen Sie eine vorhandene Datenansicht auswählen. So können Sie Ihre Inhaltsanalysedaten mit anderen Daten zusammenführen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Datenansicht"
>abstract="Wählen Sie eine vorhandene Datenansicht aus Customer Journey Analytics aus, mit der Sie Ihre Inhaltsanalysedaten zusammenführen möchten."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Datenansicht"
>abstract="Wählen Sie eine vorhandene Datenansicht aus Customer Journey Analytics aus, mit der Sie Ihre Inhaltsanalysedaten zusammenführen möchten.<br/>"

<!-- markdownlint-enable MD034 -->

Ihre Konfiguration erfordert die Auswahl einer &quot;[&quot; ](/help/data-views/data-views.md).

![Inhaltsanalysekonfiguration einer Datenansicht](../assets/aca-configuration-dataview.png)

So wählen Sie eine Datenansicht:

1. Verwenden Sie ![Daten](/help/assets/icons/Data.svg) **[!UICONTROL Datenansicht auswählen]**. Es wird ein **[!UICONTROL Datenansicht]** angezeigt, in dem Sie eine Datenansicht für Ihre Konfiguration auswählen können.

   Wenn Sie eine neue Konfiguration erstellen, zeigt die Liste nur Datenansichten an, die mit Sandboxes verknüpft sind, die keine aktive Konfiguration haben.
Wenn Sie eine vorhandene Konfiguration bearbeiten, zeigt die Liste nur Datenansichten an, die in der Sandbox verfügbar sind, die bereits mit der vorhandenen Konfiguration verknüpft ist.

   * Um die Liste der verfügbaren Datenansichten zu filtern, wählen Sie ![Filter anzeigen](/help/assets/icons/Filter.svg) aus. Sie können die Liste nach Verbindung, Eigentümer und Sandbox filtern.<br/>Verwenden Sie ![Ausblenden](/help/assets/icons/Filter.svg) **[!UICONTROL Filter ausblenden]**, um den Filterbereich auszublenden.
   * Um zu definieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](/help/assets/icons/ColumnSetting.svg) aus. Wählen Sie aus, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]**, um die Änderungen anzuwenden.
1. Klicken Sie **[!UICONTROL Speichern]**, um die ausgewählte Datenansicht zu bestätigen. Wählen Sie **[!UICONTROL Abbrechen]** zum Abbrechen aus.

Eine Datenansicht ist an eine Customer Journey Analytics ([) ](/help/connections/overview.md). Und eine Verbindung basiert auf einer Sandbox in Ihrer Organisation. Nachdem Sie die Konfiguration gespeichert haben **[!UICONTROL wird]** Sandbox) basierend auf der ausgewählten Datenansicht automatisch mit dem Eigennamen der Sandbox ausgefüllt.


### Erlebniserfassung und -definition {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie können auswählen, ob Erlebnisse in die mit der Inhaltsanalyse erfassten Daten einbezogen werden sollen. Wenn diese Option aktiviert ist, müssen Sie eine oder mehrere Kombinationen aus einem regulären Ausdruck und Abfrageparametern definieren, um festzulegen, für welche URLs Erlebnisse eingeschlossen werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Erlebniserfassung und -definition"
>abstract="Erfassen von Erlebnissen in der Inhaltsanalyse"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_url_header"
>title="Erlebniserfassung und -definition"
>abstract="Geben Sie URLs an, für die die folgenden Parameter gelten."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie können die Einstellungen in der Adobe Content Analytics-Erweiterung in der Tag-Eigenschaft bearbeiten, die mit der ausgewählten Konfiguration verknüpft ist."



<!-- markdownlint-enable MD034 -->

In diesem Abschnitt können Sie auswählen, ob Erlebnisse in die mit Content Analytics erfassten Daten einbezogen werden sollen.  Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die der Benutzer verwendet hat, der diese Web-Seite ursprünglich besucht hat.

Standardmäßig ist **[!UICONTROL Erlebnisse einschließen]** deaktiviert. Wenn diese Option aktiviert ist, müssen Sie festlegen, für welche URLs Erlebnisse eingeschlossen werden sollen.

So schließen Sie Erlebnisse in eine neue oder nicht implementierte Konfiguration ein:

![Erfassung und Definition der Erlebniskonfiguration für Content Analytics](../assets/aca-configuration-experience.png)

1. Aktivieren Sie **[!UICONTROL Erlebnisse einschließen]**.
1. Geben Sie die Parameter an, die bestimmen, wie Inhalte auf Ihrer Website gerendert werden. Bei den Parametern handelt es sich um keine oder mehrere Kombinationen aus einem **[!UICONTROL regulären Domänenausdruck]** und **[!UICONTROL Abfrageparametern]**.
   1. Geben Sie einen **[!UICONTROL Regulären Ausdruck der Domain]** ein, z. B. `(?!.*\b(store|help|admin)\b)`.
   1. Geben Sie eine kommagetrennte Liste von **[!UICONTROL Abfrageparametern]** an, z. B. `outdoors, patio, kitchen`.
1. Wählen **[!UICONTROL Entfernen]** aus, wenn Sie eine Kombination aus regulären Domain-Ausdrücken und Abfrageparametern entfernen möchten.
1. Wählen **[!UICONTROL Weitere hinzufügen]** aus, wenn Sie eine weitere Kombination aus einem regulären Ausdruck und Abfrageparametern hinzufügen möchten.

So bearbeiten Sie vorhandene Erlebnisse oder schließen neue Erlebnisse in eine implementierte Konfiguration ein:

![Erfassung und Definition der Erlebniskonfiguration für Content Analytics](../assets/aca-configuration-experience-edit.png)

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um die Parameter in der Adobe Content Analytics-Erweiterung in der Tag-Eigenschaft zu bearbeiten, die mit der ausgewählten Konfiguration verknüpft ist.


### Datenerfassung {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Datenerfassung"
>abstract="Definieren Sie, welche Tag-Eigenschaft verwendet werden soll, oder erstellen Sie eine neue. Und definieren Sie die Seiten und Assets, die Sie mithilfe regulärer Ausdrücke ein- oder ausschließen möchten."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Datenerfassung"
>abstract="Angeben einer Tag-Eigenschaft"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Datenerfassung"
>abstract="**Einzuschließende/auszuschließende Seiten**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Datenerfassung"
>abstract="Geben Sie an, welche Seiten bei der Datenerfassung zur Inhaltsanalyse **eingeschlossen** oder **ausgeschlossen** werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Datenerfassung"
>abstract="**Einzuschließende/auszuschließende Assets**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Datenerfassung"
>abstract="Geben Sie an, welche Assets bei der Datenerfassung zur Inhaltsanalyse **eingeschlossen** oder **ausgeschlossen** werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Datenerfassung"
>abstract="Sie können die Seiteneinstellungen in der Adobe Content Analytics-Erweiterung in der Tag-Eigenschaft bearbeiten, die mit der ausgewählten Konfiguration verknüpft ist."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Datenerfassung"
>abstract="Sie können die Einstellungen für Assets in der Adobe Content Analytics-Erweiterung in der Tag-Eigenschaft bearbeiten, die mit der ausgewählten Konfiguration verknüpft ist."

<!-- markdownlint-enable MD034 -->

#### Neue Konfiguration

In einer neuen Konfiguration müssen Sie definieren, welche Tag-Eigenschaft Sie verwenden möchten, oder eine neue Tag-Eigenschaft erstellen. Außerdem müssen Sie die Seiten und Assets definieren, die Sie mithilfe regulärer Ausdrücke ein- oder ausschließen möchten.

* So verwenden Sie eine vorhandene Tag-Eigenschaft:

  ![Vorhandenes Tag zur Datenerfassung in Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   * Wählen Sie **[!UICONTROL vorhanden]** aus.
   * Wählen Sie eine vorhandene Eigenschaft aus dem Dropdown **[!UICONTROL Menü „Tag]** Eigenschaft“ aus.

* So erstellen Sie eine neue Tag-Eigenschaft:

  ![Neues Tag zur Datenerfassung in Content Analytics](../assets/aca-configuration-datacollection-newtag.png)

   1. Wählen Sie **[!UICONTROL Neu erstellen]** aus.
   2. Geben Sie einen **[!UICONTROL Tag-Namen]** an, z. B. `ACA Test`.
   3. Geben Sie **[!UICONTROL Domains]** an, z. B. `example.com`.

* Wenn Sie sich dafür entschieden haben, Erlebnisse einzubeziehen, geben Sie an, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen.

   * Geben Sie einen regulären Ausdruck für &quot;**[!UICONTROL &quot;]**. Beispiel: `(?!.*\b(store|help|admin)\b)`.

* Geben Sie an, welche Assets bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen.

   * Geben Sie einen regulären Ausdruck für &quot;**[!UICONTROL &quot;]**. Beispiel: `(?!.*\b(store|help|admin)\b)`.


#### Vorhandene Konfiguration

Für eine vorhandene Konfiguration können Sie die Tag-Eigenschaft nicht bearbeiten. Sie können jedoch die Seiten und Assets bearbeiten, die Sie ein- oder ausschließen möchten.

* Um zu bearbeiten, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** unter **[!UICONTROL Erlebnis]**.

* Um zu bearbeiten, welche Assets bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** unter **[!UICONTROL Asset]** aus.

### Zusammenfassung {#summary}

Nachdem Sie alle erforderlichen Details bereitgestellt haben, enthält eine Zusammenfassung Details zu den Artefakten, die erstellt oder geändert werden.

* Wenn Sie **[!UICONTROL neue Konfiguration implementieren, wird die Zusammenfassung _Konfigurationsname_ für]** angezeigt.

* Für vorhandene implementierte Konfigurationen wird die Zusammenfassung **[!UICONTROL Sie haben _Konfigurationsname) für_ Analytics]**.

![Zusammenfassung der Inhaltsanalysekonfiguration](../assets/aca-configuration-summary.png)

### Aktionen {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning"
>title="Onboarding-Implementierungswarnung"
>abstract="Dadurch wird Content Analytics teilweise basierend auf den Eingaben konfiguriert, die Sie in diesem Workflow bereitgestellt haben. Verschiedene andere Einstellungen werden automatisch ausgewählt, basierend auf dem, was im Allgemeinen für Inhaltsanalysen nützlich ist. Sie sollten die Einstellungen der einzelnen Artefakte überprüfen, um sicherzustellen, dass sie Ihren Anforderungen und Richtlinien entsprechen. <br/>Beachten Sie, dass keine Daten erfasst werden, bis die mit dieser Konfiguration verknüpfte Tag-Bibliothek manuell veröffentlicht wird.<br/>Beachten Sie außerdem, dass Adobe zum Ableiten von Bild- und Textattributen diese Attribute mithilfe der URL abruft, die zum Zeitpunkt des Benutzerbesuchs gemäß den von Ihnen implementierten Datenerfassungseinstellungen erfasst wurde."

<!-- markdownlint-enable MD034 -->


Wenn Sie eine Konfiguration erstellt oder bearbeitet haben, sind die folgenden Aktionen verfügbar.

* **[!UICONTROL Verwerfen]**: Alle Änderungen, die im Rahmen der Erstellung einer neuen Konfiguration oder der Bearbeitung einer vorhandenen Konfiguration vorgenommen wurden, werden verworfen.
* **[!UICONTROL Für später speichern]**: Änderungen an einer neuen Konfiguration oder einer vorhandenen, noch nicht implementierten Konfiguration werden gespeichert. Sie können die Konfiguration zu einem späteren Zeitpunkt erneut aufrufen, um weitere Änderungen vorzunehmen, oder die Konfiguration implementieren.
* **[!UICONTROL Implementieren]**: Änderungen an einer neuen Konfiguration oder einer vorhandenen, noch nicht implementierten Konfiguration werden gespeichert und implementiert. Die Implementierung besteht aus:
   * **[!UICONTROL Adobe Experience Platform]**-Konfiguration:
      1. Die Erstellung von Schemas zur Modellierung von Content-Analytics-Ereignissen, Asset-Attributen und (falls konfiguriert) Erlebnisattributen.
      1. Die Erstellung von Datensätzen zur Erfassung von Content-Analytics-Ereignissen, Asset-Attributen und (falls konfiguriert) Erlebnisattributen.
   * **[!UICONTROL Inhaltsanalyse]** Konfiguration:
      * Einrichtung eines Assembler-Prozesses für Funktionen basierend auf der Konfiguration.
   * **[!UICONTROL Customer Journey Analytics]**-Konfiguration:
      1. Die ausgewählte Datenansicht wird aktualisiert und enthält jetzt die Dimension und Metriken der Inhaltsanalyse.
      1. Die mit der ausgewählten Datenansicht verknüpfte Verbindung wird geändert, um Ereignis- und Attributdatensätze aus der Inhaltsanalyse einzuschließen.
      1. Berichtsvorlagen für Content Analytics werden zu Workspace hinzugefügt.
   * **[!UICONTROL Datenerfassung]** Konfiguration:
      1. Die neue oder vorhandene Tag-Eigenschaft ist so konfiguriert, dass sie die Datenerfassung in der Inhaltsanalyse unterstützt. Diese Konfiguration beinhaltet die Einbindung der Adobe Content Analytics-Erweiterung für Tags.
      1. Ein Datenstrom wird für Content Analytics-Ereignisse erstellt.
      1. Die Adobe Content Analytics-Erweiterung ist so konfiguriert, dass Inhaltsanalyseereignisse an den Datenstrom für Inhaltsanalysen gesendet werden.
      1. Wenn die Web-SDK nicht für die Tags-Eigenschaft konfiguriert ist, wird eine neue Web-SDK-Konfiguration erstellt, um nur Content Analytics-Ereignisse zu senden.
      1. Wenn die Web-SDK für diese Tag-Eigenschaft konfiguriert ist, werden an der vorhandenen Web-SDK-Konfiguration keine Änderungen vorgenommen.
* **[!UICONTROL Speichern]**: Änderungen an einer implementierten Konfiguration werden gespeichert und die Implementierung wird aktualisiert.
* **[!UICONTROL Beenden]**. Beendet die geführte Konfiguration. Alle Änderungen an einer implementierten Konfiguration werden verworfen.

>[!MORELIKETHIS]
>
>[Manuelle Konfiguration der Inhaltsanalyse](manual.md)
>
