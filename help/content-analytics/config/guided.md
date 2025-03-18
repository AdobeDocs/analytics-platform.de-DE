---
title: Geführte Konfiguration für Content Analytics
description: Konfigurieren von Content Analytics mithilfe einer geführten Onboarding-Konfiguration
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 5eb9136107ed872639b02df2549a2f81dee83e76
workflow-type: tm+mt
source-wordcount: '3295'
ht-degree: 13%

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
>abstract="Geben Sie einen Namen für die Verbindung an. Geben Sie in den Abschnitten zu **[!UICONTROL Datenansicht]**, **[!UICONTROL Erlebniserfassung und -definition]** und **[!UICONTROL Datenerfassung]** weitere Details an, um sicherzustellen, dass die Inhaltsanalyse korrekt konfiguriert werden kann."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Details"
>abstract="In diesem Handbuch werden die Anforderungen für die Konfiguration von Content Analytics festgelegt. Geben Sie einen Namen für diese Konfiguration an."

<!-- markdownlint-enable MD034 -->

Jede Konfiguration erfordert einen eindeutigen Namen. Beispiel: `Example Content Analytics configuration`. Der Name ist zum Speichern oder Implementieren einer Konfiguration erforderlich.

![Konfigurationsdetails von Content Analytics](../assets/aca-configuration-details.png)


### Datenansicht {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Datenansicht"
>abstract="Für die Konfiguration der Inhaltsanalyse müssen Sie eine vorhandene Datenansicht auswählen. So können Sie Ihre Inhaltsanalysedaten mit anderen Daten zusammenführen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Datenansicht"
>abstract="Wählen Sie eine vorhandene Datenansicht aus Customer Journey Analytics aus, mit der Ihre Inhaltsanalysedaten zusammengeführt werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Datenansicht"
>abstract="Wählen Sie eine vorhandene Datenansicht aus Customer Journey Analytics aus, mit der Ihre Inhaltsanalysedaten zusammengeführt werden sollen.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Neue Datenansicht"
>abstract="Die Auswahl einer neuen Datenansicht führt zu einer Aktualisierung dieser Datenansicht, um Content Analytics-Metriken und -Dimensionen einzuschließen. Bei Bedarf wird die zugehörige Verbindung ebenfalls aktualisiert, damit die Datensätze der Inhaltsanalyse berücksichtigt werden. Die Verbindung und Datenansicht, die aktuell für die Inhaltsanalyse konfiguriert sind, werden nicht geändert."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Ausgewählte Datenansicht bereinigen"
>abstract="Sie haben eine Datenansicht ausgewählt, die bereits für Content Analytics bereitgestellt ist. Diese bestehende Content Analytics-Konfiguration wird entfernt und die Datenansicht wird mit Ihrer neuen Konfiguration bereitgestellt."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Vorherige Datenansicht bereinigen"
>abstract="Sie haben eine neue Datenansicht ausgewählt. Die Content Analytics-Konfiguration für die zuvor ausgewählte Datenansicht wird entfernt."

<!-- markdownlint-enable MD034 -->

Ihre Konfiguration erfordert die Auswahl einer &quot;[&quot; ](/help/data-views/data-views.md).

1. Datenansicht auswählen

   * Um eine neue Datenansicht für eine Konfiguration auszuwählen, verwenden Sie ![Daten](/help/assets/icons/Data.svg) **[!UICONTROL Datenansicht auswählen]**.

     ![Inhaltsanalysekonfiguration einer Datenansicht](../assets/aca-configuration-dataview.png)

   * Um eine Datenansicht für eine Konfiguration zu ändern, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus.

     ![Inhaltsanalysekonfiguration einer Datenansicht](../assets/aca-configuration-dataview-edit.png)


   In beiden Szenarien wird ein Dialogfeld **[!UICONTROL Datenansicht]** angezeigt, in dem Sie eine Datenansicht für Ihre Konfiguration auswählen können.

   ![Content Analytics-Konfiguration einer Datenansicht - Datenansichtstabelle](../assets/aca-configuration-dataview-dialog.png)

   Für eine neue Konfiguration zeigt die Liste nur Datenansichten an, die mit Sandboxes verknüpft sind, die keine aktive Konfiguration haben.

   Wenn Sie eine vorhandene Konfiguration bearbeiten, zeigt die Liste nur Datenansichten an, die in der Sandbox verfügbar sind, die bereits mit der vorhandenen Konfiguration verknüpft ist.

   * Um nach einer bestimmten Datenansicht zu suchen, verwenden Sie das Feld ![Suche](/help/assets/icons/Search.svg).
   * Um die Liste der verfügbaren Datenansichten zu filtern, wählen Sie ![Filter anzeigen](/help/assets/icons/Filter.svg) aus. Sie können die Liste nach Verbindung, Eigentümer und Sandbox filtern.<br/>Verwenden Sie ![Ausblenden](/help/assets/icons/Filter.svg) **[!UICONTROL Filter ausblenden]**, um den Filterbereich auszublenden.
   * Um zu definieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](/help/assets/icons/ColumnSetting.svg) aus. Wählen Sie aus, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]**, um die Änderungen anzuwenden.

1. Klicken Sie **[!UICONTROL Speichern]**, um die ausgewählte Datenansicht zu bestätigen. Wählen Sie **[!UICONTROL Abbrechen]** zum Abbrechen aus.


Eine Datenansicht ist an eine Customer Journey Analytics ([) ](/help/connections/overview.md). Und eine Verbindung basiert auf einer Sandbox in Ihrer Organisation. Nach dem Speichern der Konfiguration wird **[!UICONTROL Sandbox]** basierend auf der ausgewählten Datenansicht automatisch mit dem Eigennamen der Sandbox ausgefüllt.


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
>id="aca_onboarding_experiences_parameters_header"
>title="Erlebniserfassung und -definition"
>abstract="Geben Sie die Parameter an, die bestimmen, wie Inhalte auf Ihrer Website gerendert werden."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie können die Einstellungen in der Adobe Content Analytics-Erweiterung in der Tags-Eigenschaft bearbeiten, die mit der aktuellen Konfiguration verknüpft ist."

<!-- markdownlint-enable MD034 -->

In diesem Abschnitt können Sie auswählen, ob Erlebnisse in die mit Content Analytics erfassten Daten einbezogen werden sollen.  Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die der Benutzer verwendet hat, der diese Web-Seite ursprünglich besucht hat.

Standardmäßig ist **[!UICONTROL Erlebnisse einschließen]** deaktiviert. Wenn diese Option aktiviert ist, müssen Sie festlegen, für welche URLs Erlebnisse eingeschlossen werden sollen.

Erwägen Sie nur, Erlebnisse einzubeziehen, wenn Folgendes zutrifft:

* Sie können auf den Site-Inhalt nur über öffentlich zugängliche URLs zugreifen. Für den Zugriff auf die Website sind keine personalisierten Token, Cookies oder andere Mechanismen erforderlich, die nicht über die URL verfügbar sind.
* Die Seiten auf der Website müssen unter Verwendung der Seiten-URL reproduzierbar sein.

So schließen Sie Erlebnisse in eine neue oder nicht implementierte Konfiguration ein:

![Erfassung und Definition der Erlebniskonfiguration für Content Analytics](../assets/aca-configuration-experience.png)

1. Aktivieren Sie **[!UICONTROL Erlebnisse einschließen]**.
1. Optional. Geben Sie die Parameter an, wie Inhalte auf Ihrer Website gerendert werden. Bei den Parametern handelt es sich um keine oder mehrere Kombinationen aus einem **[!UICONTROL regulären Domänenausdruck]** und **[!UICONTROL Abfrageparametern]**.
   1. Geben Sie einen **[!UICONTROL Regulären Ausdruck der Domain]** ein, z. B. `/^(?!.*\b(store|help|admin)\b)/`. Stellen Sie sicher, dass Sie reguläre Ausdrücke mithilfe von `/` mit Escape-Zeichen versehen.
   1. Geben Sie eine kommagetrennte Liste von **[!UICONTROL Abfrageparametern]** an, z. B. `outdoors, patio, kitchen`.
1. Wählen **[!UICONTROL Entfernen]** aus, wenn Sie eine Kombination aus regulären Domain-Ausdrücken und Abfrageparametern entfernen möchten.
1. Wählen **[!UICONTROL Regex hinzufügen]** aus, wenn Sie eine weitere Kombination aus einem regulären Ausdruck und Abfrageparametern hinzufügen möchten.

So bearbeiten Sie vorhandene Erlebnisse oder schließen neue Erlebnisse in eine implementierte Konfiguration ein:

![Erfassung und Definition der Erlebniskonfiguration für Content Analytics](../assets/aca-configuration-experience-edit.png)

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus, um die Konfiguration zum Erfassen von Erlebnissen in Content Analytics zu bearbeiten. Sie werden zur [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) in der Tags-Eigenschaft weitergeleitet, die der aktuellen Konfiguration zugeordnet ist.




### Datenerfassung {#onboarding-data-collection}

In diesem Abschnitt konfigurieren Sie, wie Sie Ihre Inhaltsanalysedaten erfassen.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Datenerfassung"
>abstract="Definieren Sie, welche Tags-Eigenschaft Sie verwenden möchten, oder erstellen Sie eine neue. Definieren Sie zudem mithilfe regulärer Ausdrücke die ein- oder auszuschließenden Seiten und Assets."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Datenerfassung"
>abstract="**Geben Sie eine Tags-Eigenschaft an**"

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
>abstract="Sie können die Seiteneinstellungen in der Adobe Content Analytics-Erweiterung in der Tags-Eigenschaft bearbeiten, die der aktuellen Konfiguration zugeordnet ist."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Datenerfassung"
>abstract="Sie können die Einstellungen für Assets in der Adobe Content Analytics-Erweiterung in der Tags-Eigenschaft bearbeiten, die mit der aktuellen Konfiguration verknüpft ist."

<!-- markdownlint-enable MD034 -->

#### Neue Konfiguration {#new-configuration}

In einer neuen Konfiguration müssen Sie definieren, ob Sie eine vorhandene Tags-Eigenschaft verwenden oder eine neue Tags-Eigenschaft erstellen möchten. Außerdem müssen Sie die Seiten und Assets definieren, die Sie mithilfe regulärer Ausdrücke ein- oder ausschließen möchten.

* So verwenden Sie eine vorhandene Tags-Eigenschaft:

  ![Vorhandenes Tag zur Datenerfassung in Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   1. Wählen Sie **[!UICONTROL vorhanden]** aus.
   2. Wählen Sie eine vorhandene Eigenschaft aus dem Dropdown **[!UICONTROL Menü „Eigenschaft für]**&quot; aus. Sie können mit der Eingabe beginnen, um nach den verfügbaren Optionen zu suchen und diese zu beschränken.

* So erstellen Sie eine neue Tag-Eigenschaft:

  ![Neues Tag zur Datenerfassung in Content Analytics](../assets/aca-configuration-datacollection-newtag.png)

   1. Wählen Sie **[!UICONTROL Neu erstellen]** aus.
   2. Geben Sie einen **[!UICONTROL Tag-Namen]** an, z. B. `ACA Test`.
   3. Geben Sie **[!UICONTROL Domains]** an, z. B. `example.com`.

* Wenn Sie sich dafür entschieden haben, Erlebnisse einzubeziehen, geben Sie an, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen.

   * Geben Sie einen regulären Ausdruck für &quot;**[!UICONTROL &quot;]**. Beispiel: `/^(?!.*documentation).*/`, um alle Dokumentationsseiten von Content Analytics auszuschließen. Stellen Sie sicher, dass Sie reguläre Ausdrücke mithilfe von `/` mit Escape-Zeichen versehen.

* Geben Sie an, welche Assets bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen.

   * Geben Sie einen regulären Ausdruck für &quot;**[!UICONTROL &quot;]**. Beispiel: `/^(?!.*(logo\.jpg|\.svg)).*$/`, um alle JPEG- und SVG-Logo-Bilder von Content Analytics auszuschließen. Stellen Sie sicher, dass Sie reguläre Ausdrücke mithilfe von `/` mit Escape-Zeichen versehen.


#### Vorhandene Konfiguration {#existing-configuration}

Für eine vorhandene Konfiguration können Sie die Eigenschaft Tags nicht bearbeiten. Sie können jedoch die Seiten und Assets bearbeiten, die Sie ein- oder ausschließen möchten.

* Um zu bearbeiten, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** unter **[!UICONTROL Erlebnis]**. Sie werden zur Erweiterung [Adobe Content Analytics umgeleitet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) die der Tags-Eigenschaft für die aktuelle Content Analytics-Konfiguration zugeordnet ist. Sie können den regulären Ausdruck bearbeiten, um Seiten ein- oder auszuschließen. Stellen Sie sicher[ dass Sie ](manual.md#publish) Änderungen veröffentlichen.

* Um zu bearbeiten, welche Assets bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** unter **[!UICONTROL Asset]** aus. Sie werden zur Erweiterung [Adobe Content Analytics umgeleitet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) die der Tags-Eigenschaft für die aktuelle Content Analytics-Konfiguration zugeordnet ist. Sie können den regulären Ausdruck bearbeiten, um Assets ein- oder auszuschließen. Stellen Sie sicher[ dass Sie ](manual.md#publish) Änderungen veröffentlichen.

### Zusammenfassung {#summary}

Nachdem Sie alle erforderlichen Details bereitgestellt haben, enthält eine Zusammenfassung Details zu den Artefakten, die erstellt oder geändert werden.

* Wenn Sie **[!UICONTROL neue Konfiguration implementieren, wird die Zusammenfassung _Konfigurationsname_ für]** angezeigt.

* Für vorhandene implementierte Konfigurationen wird die Zusammenfassung **[!UICONTROL Sie haben _Konfigurationsname) für_ Analytics]**.

![Zusammenfassung der Inhaltsanalysekonfiguration](../assets/aca-configuration-summary.png)

### Aktionen {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Bestätigung der Implementierung"
>abstract="Wenn Sie **[!UICONTROL Implementieren]** auswählen, konfigurieren Sie die Inhaltsanalyse basierend auf den in diesem Workflow getätigten Eingaben. Standardmäßig werden mehrere Einstellungen ausgewählt, die darauf basieren, was im Allgemeinen für Content Analytics nützlich ist. Als Datenverantwortlicher müssen Sie jedoch die Einstellungen der einzelnen Artefakte überprüfen, um zu bestätigen, dass die Einstellungen gemäß Ihrer Datenschutzrichtlinie, Ihren vertraglichen Rechten und Pflichten und den Zustimmungsanforderungen nach geltendem Recht implementiert wurden.<br/><br/>Beachten Sie, dass Daten erst dann erfasst werden, wenn die mit dieser Konfiguration verknüpfte Tag-Bibliothek manuell veröffentlicht wird.<br/><br/>Um Bild- und Texteigenschaften abzuleiten, ruft Adobe die Attribute wie folgt ab:<ol><li>Die URL, die zum Zeitpunkt des Site-Besuchs des Benutzers gemäß den von Ihnen konfigurierten Datenerfassungseinstellungen erfasst wurde, und</li><li>der URL, unter der das Bild gehostet wird.</li></ol>Bilder, die auf Websites von Drittanbietern gehostet werden, dürfen nicht mit Tags versehen werden."

<!-- markdownlint-enable MD034 -->

Wenn Sie eine Konfiguration erstellt oder bearbeitet haben, sind die folgenden Aktionen verfügbar.

* **[!UICONTROL Verwerfen]**: Alle Änderungen, die im Rahmen der Erstellung einer neuen Konfiguration oder der Bearbeitung einer vorhandenen Konfiguration vorgenommen wurden, werden verworfen.
* **[!UICONTROL Für später speichern]**: Änderungen an einer neuen Konfiguration oder einer vorhandenen, noch nicht implementierten Konfiguration werden gespeichert. Sie können die Konfiguration zu einem späteren Zeitpunkt erneut aufrufen, um weitere Änderungen vorzunehmen, oder die Konfiguration implementieren.
* **[!UICONTROL Implementieren]**: Einstellungen für oder Änderungen an einer neuen Konfiguration oder einer vorhandenen, noch nicht implementierten Konfiguration werden gespeichert und implementiert. Die Implementierung besteht aus:
   * **[!UICONTROL Adobe Experience Platform]**-Konfiguration:
      * Die Erstellung von Schemas zur Modellierung von Content-Analytics-Ereignissen, Asset-Attributen und (falls konfiguriert) Erlebnisattributen.
      * Die Erstellung von Datensätzen zur Erfassung von Content-Analytics-Ereignissen, Asset-Attributen und (falls konfiguriert) Erlebnisattributen.
      * Die Erstellung eines Datenflusses, der den Feature Service verwendet, um Inhaltsattribute aus Content Analytics-Ereignissen zu generieren und zu aktualisieren.
   * **[!UICONTROL Datenerfassung]** Konfiguration:
      * Die neue oder vorhandene Tags-Eigenschaft ist so konfiguriert, dass sie die Datenerfassung in Content Analytics unterstützt. Diese Konfiguration beinhaltet die Einbindung der Adobe Content Analytics-Erweiterung für Tags.
      * Ein Datenstrom wird für Content Analytics-Ereignisse erstellt.
      * Die Adobe Content Analytics-Erweiterung ist so konfiguriert, dass Inhaltsanalyseereignisse an den Datenstrom für Inhaltsanalysen gesendet werden.
      * Wenn die Web-SDK nicht für die Tags-Eigenschaft konfiguriert ist, wird eine neue Web-SDK-Konfiguration erstellt, um nur Content Analytics-Ereignisse zu senden.
      * Wenn die Web-SDK für diese Tags-Eigenschaft konfiguriert ist, werden an der vorhandenen Web-SDK-Konfiguration keine Änderungen vorgenommen.
   * **[!UICONTROL Customer Journey Analytics]**-Konfiguration:
      * Die ausgewählte Datenansicht wird aktualisiert und enthält jetzt die Dimension und Metriken der Inhaltsanalyse.
      * Die mit der ausgewählten Datenansicht verknüpfte Verbindung wird geändert, um Content Analytics-Ereignisse und -Attributdatensätze einzuschließen.
      * Workspace wird eine Berichtsvorlage für Content Analytics hinzugefügt.
* **[!UICONTROL Speichern]**: Änderungen an einer implementierten Konfiguration werden gespeichert und die Implementierung wird aktualisiert.
* **[!UICONTROL Beenden]**. Beendet die geführte Konfiguration. Alle Änderungen an einer implementierten Konfiguration werden verworfen.


## Veröffentlichen {#publish}

Um Ihre Content Analytics-Konfiguration zu aktivieren, müssen Sie die Tags-Eigenschaft veröffentlichen, die nach der Auswahl von **[!UICONTROL Implementieren]** [Manuell](manual.md) erstellt wird.


## Onboarding-Einstellungen und -Konfigurationen

Customer Journey Analytics Experience Platform In den folgenden Abschnitten werden die Einstellungen und Konfigurationen beschrieben, die im Rahmen der Implementierung einer Content Analytics](#customer-journey-analytics-cja)Konfiguration auf [](#experience-platform-aep), {[}und ](#data-collection-dc) angewendet werden.[

Details werden für die folgenden Szenarien bereitgestellt:

* **Tags** Eigenschaft existiert **✓** oder nicht **✕**.
* **Web SDK** Erweiterung für die Tags-Eigenschaft ist **✓** vorhanden **✕**.
* Adobe **Content Analytics**-Erweiterung für die Tag-Eigenschaft ist **✓** vorhanden oder **✕** nicht vorhanden.

### Customer Journey Analytics {#cja}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Szenarien:</th>
  </tr>
  <tr>
    <th>
      <strong>Wenn</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td>Berichtsvorlage</td>
      <td colspan="4">Eine Berichtsvorlage ist verfügbar</td>
    </tr>
    <tr>
      <td>Datenansicht</td>
      <td colspan="4">Geändert/erstellt, um ACA-Dimensionen und -Metriken zu erhalten</td>
    </tr>
    <tr>
      <td>Verbindung</td>
      <td colspan="4">Geändert, um ACA-Datensätze einzuschließen (ACA-Ereignisse, Asset-Attribute, Erlebnisattribute)</td>
    </tr>
  </tbody>
</table>

### Experience Platform {#aep}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Szenarien:</th>
  </tr>
  <tr>
    <th>
      <strong>Wenn</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics-Ereignisschema</strong></td>
    </tr>
    <tr>
      <td style="margin-left: 160.0px;">Name</td>
      <td>Content Analytics-Ereignisse</td>
      <td>Content Analytics-Ereignisse</td>
      <td>Content Analytics-Ereignisse</td>
      <td>Content Analytics-Ereignisse</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
    </tr>
    <tr>
      <td>Profil aktiviert</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics-Ereignisdatensatz</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics-Ereignisse</td>
      <td>Content Analytics-Ereignisse</td>
      <td>Content Analytics-Ereignisse</td>
      <td>Content Analytics-Ereignisse</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics-Ereignis</td>
      <td>Content Analytics-Ereignis</td>
      <td>Content Analytics-Ereignis</td>
      <td>Content Analytics-Ereignis</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
    </tr>
    <tr>
      <td>Systemdatensatz</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profil aktiviert</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
    </tr>
    <tr>
      <td>Data Governance (DULE-Kennzeichnungen)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Asset-Attributschema</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
    </tr>
    <tr>
      <td>Profil aktiviert</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Assets-Attributdatensatz</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
      <td>Content Analytics-Asset-Attribute</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
    </tr>
    <tr>
      <td>Systemdatensatz</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profil aktiviert</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
    </tr>
    <tr>
      <td>Data Governance (DULE-Kennzeichnungen)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Experience Attributes-Schema</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
    </tr>
    <tr>
      <td>Profil aktiviert</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Experience Attributes-Datensatz</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
      <td>Content Analytics Experience-Attribute</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
      <td><i>vorbestimmte Nachfrist</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
      <td><i>Leer?</i></td>
    </tr>
    <tr>
      <td>Systemdatensatz</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profil aktiviert</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
      <td>Nein</td>
    </tr>
    <tr>
      <td>Data Governance (DULE-Kennzeichnungen)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
  </tbody>
</table>


### Datenerfassung {#dc}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Szenarien:</th>
  </tr>
  <tr>
    <th>
      <strong>Wenn</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Datenstrom</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>vorhandener Wert</i></td>
      <td>Inhaltsanalyse</td>
      <td>Inhaltsanalyse</td>
      <td>Inhaltsanalyse</td>
    </tr>
    <tr>
      <td>Beschreibung</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorher ausgemacht</i></td>
      <td><i>vorher ausgemacht</i></td>
      <td><i>vorher ausgemacht</i></td>
    </tr>
    <tr>
      <td>Zuordnungsschema</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorher ausgemacht</i></td>
      <td><i>vorher ausgemacht</i></td>
      <td><i>vorher ausgemacht</i></td>
    </tr>
    <tr>
      <td>Geolokalisierung und Netzwerksuche</td>
      <td><i>Vorhandene Werte</i></td>
      <td>Alle Optionen ausgeschaltet</td>
      <td>Alle Optionen ausgeschaltet</td>
      <td>Alle Optionen ausgeschaltet</td>
    </tr>
    <tr>
      <td>Gerätesuche</td>
      <td><i>vorhandener Wert</i></td>
      <td>Keine Geräteinformationen erfassen</td>
      <td>Keine Geräteinformationen erfassen</td>
      <td>Keine Geräteinformationen erfassen</td>
    </tr>
    <tr>
      <td>IP-Verschleierung</td>
      <td><i>vorhandener Wert</i></td>
      <td>Keine</td>
      <td>Keine</td>
      <td>Keine</td>
    </tr>
    <tr>
      <td>First-Party-ID-Cookie</td>
      <td><i>vorhandener Wert</i></td>
      <td>Aus</td>
      <td>Aus</td>
      <td>Aus</td>
    </tr>
    <tr>
      <td>Synchronisierung der Drittanbieter-ID</td>
      <td><i>vorhandener Wert</i></td>
      <td>Aus</td>
      <td>Aus</td>
      <td>Aus</td>
    </tr>
    <tr>
      <td>Zugriffstyp</td>
      <td><i>vorhandener Wert</i></td>
      <td>Gemischte Authentifizierung</td>
      <td>Gemischte Authentifizierung</td>
      <td>Gemischte Authentifizierung</td>
    </tr>
    <tr>
      <td>Media Analytics</td>
      <td><i>vorhandener Wert</i></td>
      <td>Aus</td>
      <td>Aus</td>
      <td>Aus</td>
    </tr>
        <tr>
      <td>Bot-Erkennung</td>
      <td><i>vorhandener Wert</i></td>
      <td>Aus</td>
      <td>Aus</td>
      <td>Aus</td>
    </tr>
    <tr>
      <td>Zuordnen</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>Benutzer angegeben</i></td>
      <td><i>Benutzer angegeben</i></td>
      <td><i>Benutzer angegeben</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Tags-Eigenschaft</strong><br/>Eine vorhandene Eigenschaft oder neue Eigenschaft. Name und Domain werden vom Benutzer angegeben.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vom Benutzer angegeben</i> (Standard: "Content Analytics„)</td>
    </tr>
    <tr>
      <td>Domain</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td ><i>vorher ausgemacht</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Tag-Bibliothek</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>
        <br/>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Web SDK-Erweiterung</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Content Analytics - Web-SDK</td>
      <td>Content Analytics - Web-SDK</td>
    </tr>
    <tr>
      <td>IMS-Organisation</td>
      <td><i>Automatisch befüllt</i></td>
      <td><i>Automatisch befüllt</i></td>
      <td><i>Automatisch befüllt</i></td>
      <td><i>Automatisch befüllt</i></td>
    </tr>
    <tr>
      <td>Edge-Domäne</td>
      <td><i>vorhandener Wert<br/> Möglicherweise ist eine Aktualisierung erforderlich, um der AppMeasurement-Implementierung zu entsprechen</i></td>
      <td><i>vorhandener Wert<br/> Möglicherweise ist eine Aktualisierung erforderlich, um der AppMeasurement-Implementierung zu entsprechen</i></td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Datenströme</strong></td>
    </tr>
    <tr>
      <td>Produktion</td>
      <td><i>Vorhandene Wert<br/>Datenstrom-Überschreibung, die zum Senden an einen anderen Datenstrom verwendet wird</i></td>
      <td><i>Vorhandene Wert<br/>Datenstrom-Überschreibung, die zum Senden an einen anderen Datenstrom verwendet wird</i></td>
      <td><i>Benutzer angegeben</i>?</td>
      <td><i>Benutzer angegeben</i>?</td>
    </tr>
    <tr>
      <td>Staging</td>
      <td><i>Vorhandene Wert<br/>Datenstrom-Überschreibung, die zum Senden an einen anderen Datenstrom verwendet wird</i></td>
      <td><i>Vorhandene Wert<br/>Datenstrom-Überschreibung, die zum Senden an einen anderen Datenstrom verwendet wird</i></td>
      <td><i>Benutzer angegeben</i>?</td>
      <td><i>Benutzer angegeben</i>?</td>
    </tr>
    <tr>
      <td>Entwicklung</td>
      <td><i>Vorhandene Wert<br/>Datenstrom-Überschreibung, die zum Senden an einen anderen Datenstrom verwendet wird</i></td>
      <td><i>Vorhandene Wert<br/>Datenstrom-Überschreibung, die zum Senden an einen anderen Datenstrom verwendet wird</i></td>
      <td><i>Benutzer angegeben</i>?</td>
      <td><i>Benutzer angegeben</i>?</td>
    </tr>
    <tr>
      <td>Datenschutz   </td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>In?</td>
      <td>In?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Identität</strong></td>
    </tr>
    <tr>
      <td>Migrieren von ECID</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Geprüft</td>
      <td>Geprüft</td>
    </tr>
    <tr>
      <td>Verwenden von Drittanbieter-Cookies</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Geprüft</td>
      <td>Geprüft</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Personalisierung</strong></td>
    </tr>
    <tr>
      <td>Migrieren von Target von at.js zu Web SDK</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>ungebremst</td>
      <td>ungebremst</td>
    </tr>
    <tr>
      <td>Personalisierungsspeicher aktivieren</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>ungebremst</td>
      <td>ungebremst</td>
    </tr>
    <tr>
      <td>Automatische Klick-Sammlung für Adobe Journey Optimizer</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Immer</td>
      <td>Immer</td>
    </tr>
    <tr>
      <td>Automatische Klick-Sammlung für Adobe Target</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Nie</td>
      <td>Nie</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Datenerfassung</strong></td>
    </tr>
    <tr>
      <td>Erfassen interner Link-Klicks</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>ungebremst</td>
      <td>ungebremst</td>
    </tr>
    <tr>
      <td>Erfassen externer Link-Klicks</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>ungebremst</td>
      <td>ungebremst</td>
    </tr>
    <tr>
      <td>Download-Links und Klicks erfassen</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>ungebremst</td>
      <td>ungebremst</td>
    </tr>
    <tr>
      <td>Beim Senden von Ereignisdaten Folgendes automatisch einschließen</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Alle standardmäßigen Kontextinformationen</td>
      <td>Alle standardmäßigen Kontextinformationen</td>
    </tr>
    <tr>
      <td>Streaming-Medien</td>
      <td><i>Vorhandene Werte</i></td>
      <td><i>Vorhandene Werte</i></td>
      <td>Leere Werte</td>
      <td>Leere Werte</td>
    </tr>
    <tr>
      <td>Überschreibungen der Datenstromkonfiguration</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>Konfiguration des Datenstroms abgleichen</td>
      <td>Konfiguration des Datenstroms abgleichen</td>
    </tr>
    <tr>
      <td>Erweiterte Einstellungen - Edge-Basispfad</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorhandener Wert</i></td>
      <td>ee</td>
      <td>ee</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics-Erweiterung</strong></td>
    </tr>
    <tr>
      <td>Datenströme</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>vorher ausgemacht</i></td>
      <td><i>vorher ausgemacht</i></td>
      <td><i>vorher ausgemacht</i></td>
    </tr>
    <tr>
      <td>Erlebniserfassung und -definition</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>Benutzer angegeben</i></td>
      <td><i>Benutzer angegeben</i></td>
      <td><i>Benutzer angegeben</i></td>
    </tr>
    <tr>
      <td>Ereignisfilterung</td>
      <td><i>vorhandener Wert</i></td>
      <td><i>Benutzer angegeben</i></td>
      <td><i>Benutzer angegeben</i></td>
      <td><i>Benutzer angegeben</i></td>
    </tr>
  </tbody>
</table>

>[!MORELIKETHIS]
>
>[Manuelle Konfiguration](manual.md)
>
