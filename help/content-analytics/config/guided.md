---
title: Geführte Inhaltsanalysekonfiguration
description: Einrichten der Inhaltsanalyse mithilfe einer geführten Onboarding-Konfiguration
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 46%

---

# Geführte Inhaltsanalysekonfiguration

Mit der geführten Konfiguration können Sie die Inhaltsanalyse schnell und einfach konfigurieren. Bei der geführten Konfiguration wird ein Assistent verwendet, um die Anforderungen für die automatische Konfiguration der Inhaltsanalyse für Ihre Organisation festzulegen. Im Bildschirm **[!UICONTROL Konfiguration]** können Sie entweder eine neue Konfiguration erstellen oder eine vorhandene Konfiguration bearbeiten.

>[!IMPORTANT]
>
>Pro Sandbox ist in Ihrer Organisation nur eine Inhaltsanalysekonfiguration möglich.

So greifen Sie auf die Inhaltsanalysekonfiguration zu:

* Wählen **[!UICONTROL Daten-Management]** > **[!UICONTROL Content Analytics-]** im Hauptmenü von Customer Journey Analytics aus.

Auf dem Bildschirm **[!UICONTROL Content Analytics]** Konfigurationen wird eine Tabelle der bestehenden Content Analytics-Konfigurationen angezeigt.

![Inhaltsanalysekonfigurationen](../assets/aca-configuration-table.png)
Für jede Konfiguration stehen die folgenden Details zur Verfügung:

| Spalte | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Der Name der Konfiguration. |
| **[!UICONTROL Erstellt von]** | Das technische Konto, mit dem die Konfiguration erstellt wurde. |
| **[!UICONTROL Erstellt am]** | Der Zeitstempel, wann die Konfiguration erstellt wurde. |
| **[!UICONTROL Geändert am]** | Der Zeitstempel, wann die Konfiguration zuletzt geändert wurde. |
| **[!UICONTROL Sandbox]** | Die Sandbox in der Organisation, in der die Inhaltsanalyse (voraussichtlich) konfiguriert und implementiert wird. |
| **[!UICONTROL Status]** | Der Status der Konfiguration. Der Status kann lauten: <br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Entwurf]**: Die Konfiguration wird für später gespeichert und nicht bereitgestellt.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Fehlgeschlagen]**: Die Konfiguration ist fehlgeschlagen. Sie können auf **[!UICONTROL Bearbeiten]** klicken, um Informationen zum Fehler zu erhalten. Adobe geht proaktiv gegen fehlgeschlagene Implementierungen vor. Weitere Informationen erhalten Sie bei der Kundenunterstützung.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Beendet]**: Die Konfiguration wurde abgeschlossen und erfolgreich implementiert. |

Sie können ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) verwenden, um die Tabelle anzupassen. Legen Sie fest, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]** aus, um die Änderungen anzuwenden.

Im Bildschirm **[!UICONTROL Konfiguration]** der Inhaltsanalyse können Sie eine neue Konfiguration erstellen oder eine vorhandene Konfiguration bearbeiten.

So erstellen Sie eine neue Konfiguration:

* Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus. Diese Aktion öffnet den [Konfigurationsassistenten](#guided-configuration-wizard).

So bearbeiten Sie eine vorhandene Konfiguration:

* Wählen Sie ![Mehr](/help/assets/icons/More.svg) und dann ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** für eine vorhandene Inhaltsanalysekonfiguration aus. Diese Aktion öffnet den [Konfigurationsassistenten](#guided-configuration-wizard).

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
>abstract="In dieser Anleitung werden die Anforderungen für die Konfiguration der Inhaltsanalyse festgelegt. Geben Sie einen Namen für diese Konfiguration an"

<!-- markdownlint-enable MD034 -->

Jede Konfiguration erfordert einen eindeutigen Namen. Beispiel: `Example Content Analytics configuration`. Der Name ist zum Speichern oder Implementieren einer Konfiguration erforderlich.

![Details zur Inhaltsanalysekonfiguration](../assets/aca-configuration-details.png)


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
>abstract="Die Auswahl einer neuen Datenansicht führt zu einer Aktualisierung dieser Datenansicht, um Metriken und Dimensionen der Inhaltsanalyse einzuschließen. Bei Bedarf wird die zugehörige Verbindung ebenfalls aktualisiert, damit die Datensätze der Inhaltsanalyse berücksichtigt werden. Die Verbindung und Datenansicht, die aktuell für die Inhaltsanalyse konfiguriert sind, werden nicht geändert."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Ausgewählte Datenansicht bereinigen"
>abstract="Sie haben eine Datenansicht ausgewählt, die bereits für Content Analytics bereitgestellt ist. Diese bestehende Content Analytics-Konfiguration wird entfernt und die Datenansicht wird mit Ihrer neuen Konfiguration bereitgestellt."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Vorherige Datenansicht bereinigen"
>abstract="Sie haben eine neue Datenansicht ausgewählt. Die Content Analytics-Konfiguration für die zuvor ausgewählte Datenansicht wird entfernt."

<!-- markdownlint-enable MD034 -->

Ihre Konfiguration erfordert die Auswahl einer [Datenansicht](/help/data-views/data-views.md).

1. Datenansicht auswählen

   * Um eine neue Datenansicht für eine Konfiguration auszuwählen, verwenden Sie ![Daten](/help/assets/icons/Data.svg) **[!UICONTROL Datenansicht auswählen]**.

     ![Content Analytics-Konfiguration einer Datenansicht](../assets/aca-configuration-dataview.png)

   * Um eine Datenansicht für eine Konfiguration zu ändern, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus.

     ![Content Analytics-Konfiguration einer Datenansicht](../assets/aca-configuration-dataview-edit.png)


   In beiden Szenarien wird ein Dialogfeld **[!UICONTROL Datenansicht]** angezeigt, in dem Sie eine Datenansicht für Ihre Konfiguration auswählen können.

   ![Content Analytics-Konfiguration einer Datenansicht - Datenansichtstabelle](../assets/aca-configuration-dataview-dialog.png)

   Für eine neue Konfiguration zeigt die Liste nur Datenansichten an, die mit Sandboxes verknüpft sind, die keine aktive Konfiguration haben. Außerdem sehen Sie nur Datenansichten, die mit Sandboxes verknüpft sind, auf die Sie Zugriff haben, und Verbindungen, zu denen Sie berechtigt sind, sie zu ändern.

   Wenn Sie eine vorhandene Konfiguration bearbeiten, zeigt die Liste nur Datenansichten an, die in der Sandbox verfügbar sind, die bereits mit der vorhandenen Konfiguration verknüpft ist.

   Sie können die folgenden Aktionen ausführen:

   * Um nach einer bestimmten Datenansicht zu suchen, verwenden Sie das Feld ![Suche](/help/assets/icons/Search.svg).
   * Um die Liste der verfügbaren Datenansichten zu filtern, wählen Sie ![Filter anzeigen](/help/assets/icons/Filter.svg) aus. Sie können die Liste nach [!UICONTROL Verbindung], &quot;[!UICONTROL &quot; ] &quot;[!UICONTROL &quot; ].<br/>Verwenden Sie ![Ausblenden](/help/assets/icons/Filter.svg) **[!UICONTROL Ausblenden von]**, um den Segmentbereich auszublenden.
   * Um zu definieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](/help/assets/icons/ColumnSetting.svg) aus. Wählen Sie aus, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]** aus, um die Änderungen anzuwenden.

1. Wählen Sie ![SelectBox](/help/assets/icons/SelectBox.svg) die Datenansicht aus, die Sie verwenden möchten.
1. Klicken Sie **[!UICONTROL Speichern]**, um die ausgewählte Datenansicht zu bestätigen. Wählen Sie zum Abbrechen **[!UICONTROL Abbrechen]** aus.


In Customer Journey Analytics ist eine [Datenansicht](/help/data-views/data-views.md) an eine Customer Journey Analytics ([) ](/help/connections/overview.md). Und eine Verbindung basiert auf einer Sandbox in Ihrer Organisation. Nachdem Sie die Konfiguration gespeichert haben **[!UICONTROL wird]** Feld „Sandbox“ basierend auf der ausgewählten Datenansicht automatisch mit dem Namen der Sandbox ausgefüllt.


### Erlebniserfassung und -definition {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie können auswählen, ob Erlebnisse in die mit Content Analytics erfassten Daten einbezogen werden sollen. Wenn diese Option aktiviert ist, müssen Sie eine oder mehrere Kombinationen aus einem regulären Ausdruck und Abfrageparametern definieren, um festzulegen, für welche URLs Erlebnisse eingeschlossen werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Erlebniserfassung und -definition"
>abstract="Erlebnisse in der Inhaltsanalyse erfassen"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Erlebniserfassung und -definition"
>abstract="Geben Sie die Parameter an, die bestimmen, wie Inhalte auf Ihrer Website gerendert werden."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Erlebniserfassung und -definition"
>abstract="Wenn diese Option aktiviert ist, werden Erlebnisdaten erfasst, Erlebnisattribute generiert und Erlebnisberichte sind verfügbar."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Erlebniserfassung und -definition"
>abstract="Wenn diese Option aktiviert ist, werden Erlebnisdaten erfasst, Erlebnisattribute generiert und Erlebnisberichte sind verfügbar. <br><br/>Verwenden Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]**, um die Datenerfassungskonfiguration für Erlebnisse in der Tags-Eigenschaft zu ändern, die der aktuellen Konfiguration zugeordnet ist."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie müssen die Einstellungen für die Erlebnisdatenerfassung in der Adobe Content Analytics-Erweiterung bearbeiten."

<!-- markdownlint-enable MD034 -->

In diesem Abschnitt können Sie auswählen, ob Erlebnisse in die mit Content Analytics erfassten Daten einbezogen werden sollen.  Ein Erlebnis ist der gesamte Text auf einer Web-Seite, der anhand der URL reproduzierbar ist, die die Benutzerin bzw. der Benutzer verwendet hat, die bzw. der diese Web-Seite ursprünglich besucht hat.

Standardmäßig ist **[!UICONTROL Erlebnisse einschließen]** deaktiviert. Wenn diese Option aktiviert ist, müssen Sie festlegen, für welche URLs Erlebnisse eingeschlossen werden sollen.

Erwägen Sie nur, Erlebnisse einzubeziehen, wenn Folgendes zutrifft:

* Die Seiten auf der Website müssen unter Verwendung der Seiten-URL reproduzierbar sein.
* Der Textinhalt, der von einem bestimmten Benutzer angezeigt wird, kann mithilfe der Seiten-URL reproduziert werden und hängt nicht von Cookies oder anderen Personalisierungsmechanismen ab.

>[!IMPORTANT]
>
>Implementieren Sie die [Content Analytics](manual.md#versioning)Versionierung, um Änderungen zu erfassen, die Sie an den Erlebnissen (Seiten) vornehmen, die Content Analytics unterliegen.



#### Neue Konfiguration {#new-experiences-configuration}

So schließen Sie Erlebnisse in eine neue oder nicht implementierte Konfiguration ein:

![Erfassung und Definition von Erlebnissen bei der Konfiguration der Inhaltsanalyse](../assets/aca-configuration-experience.png)

1. Aktivieren Sie **[!UICONTROL Erlebnisse einschließen]**. Der Umschalter zum Aktivieren von Erlebnissen wirkt sich auf Folgendes aus:

   * Datenerfassung in der Content Analytics-Erweiterung
   * Der Prozess, der Erlebnisattribute aus Content Analytics-Ereignisdaten generiert
   * Die Berichtsvorlage in Customer Journey Analytics.

1. Geben Sie die Parameter an, wie Inhalte auf Ihrer Website gerendert werden sollen. Bei den Parametern handelt es sich um keine oder mehrere Kombinationen aus einem **[!UICONTROL regulären Domänenausdruck]** und **[!UICONTROL Abfrageparametern]**. Die Abfrageparameter geben an, welche Parameter sich auf den Inhalt auf Ihrer Seite auswirken. Mit dieser Eingabe kann Content Analytics alle Parameter ignorieren, die sich nicht auf den Inhalt der Seite auswirken, wenn ein eindeutiges Erlebnis definiert wird.
   1. Geben Sie einen **[!UICONTROL Regulären Ausdruck der Domain]** ein, z. B. `/^(?!.*\b(store|help|admin)\b)/`. Stellen Sie sicher, dass Sie reguläre Ausdrücke mithilfe von `/` mit Escape-Zeichen versehen. Der reguläre Ausdruck der Domain gibt an, für welche URLs diese Parameter gelten. Beispielsweise können Sie mehrere Sites haben, und für jede Site steuern andere Parameter den Inhalt. Wenn die Abfrageparameter für alle Ihre Seiten gelten, können Sie `.*` verwenden, um alle Seiten anzugeben.
   1. Geben Sie eine durch Kommas getrennte Liste von **[!UICONTROL Abfrageparametern]** an, z. B. `outdoors, patio, kitchen`.
1. Wählen Sie **[!UICONTROL Entfernen]** aus, wenn Sie eine Kombination aus regulärem Domain-Ausdruck und Abfrageparametern entfernen möchten.
1. Wählen **[!UICONTROL Regex hinzufügen]** aus, wenn Sie eine weitere Kombination aus einem regulären Ausdruck und Abfrageparametern hinzufügen möchten.


#### Implementierte Konfiguration {#implemented-experiences-configuration}

So bearbeiten Sie vorhandene Erlebnisse oder schließen neue Erlebnisse in eine implementierte Konfiguration ein:

Erfassung und Definition der Content Analytics-Konfiguration für das Erlebnis](../assets/aca-configuration-experience-edit.png)![

* Schalten Sie **[!UICONTROL Erlebnisse einschließen]** um:

   * Der Prozess, der Erlebnisattribute aus Content Analytics-Ereignisdaten generiert
   * Die Berichtsvorlage in Customer Journey Analytics.

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus, um die Konfiguration der Datenerfassung für Erlebnisse in Content Analytics weiter zu bearbeiten. Sie werden zur [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) in der Tags-Eigenschaft weitergeleitet, die der aktuellen Konfiguration zugeordnet ist.


### Datenerfassung {#onboarding-data-collection}

In diesem Abschnitt konfigurieren Sie, wie Sie Ihre Inhaltsanalysedaten erfassen.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Datenerfassung"
>abstract="Definieren Sie, welche Tag-Eigenschaft verwendet werden soll, oder erstellen Sie eine neue. Definieren Sie zudem mithilfe regulärer Ausdrücke die ein- oder auszuschließenden Seiten und Assets."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Datenerfassung"
>abstract="**Angeben einer Tag-Eigenschaft**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Datenerfassung"
>abstract="**Einzuschließende/auszuschließende Seiten**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Datenerfassung"
>abstract="Geben Sie an, welche Seiten bei der Datenerfassung zur Inhaltsanalyse **eingeschlossen** oder **ausgeschlossen** werden sollen"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Datenerfassung"
>abstract="**Einzuschließende/auszuschließende Assets**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Datenerfassung"
>abstract="Geben Sie an, welche Assets bei der Datenerfassung zur Inhaltsanalyse **eingeschlossen** oder **ausgeschlossen** werden sollen"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Datenerfassung"
>abstract="Sie können die Einstellungen für Seiten in der Adobe-Erweiterung für die Inhaltsanalyse in der Tag-Eigenschaft bearbeiten, die mit der aktuellen Konfiguration verknüpft ist."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Datenerfassung"
>abstract="Sie können die Einstellungen für Assets in der Adobe-Erweiterung für die Inhaltsanalyse in der Tag-Eigenschaft bearbeiten, die mit der aktuellen Konfiguration verknüpft ist."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="Tag-Eigenschaft deaktiviert"
>abstract="Content Analytics-Erweiterung ist bereits aktiv."

<!-- markdownlint-enable MD034 -->

#### Neue Konfiguration {#new-configuration}

In einer neuen Konfiguration müssen Sie definieren, ob Sie eine vorhandene Tags-Eigenschaft verwenden oder eine neue Tags-Eigenschaft erstellen möchten. Außerdem müssen Sie mithilfe regulärer Ausdrücke festlegen, welche Seiten und Assets eingeschlossen oder ausgeschlossen werden sollen.

* So verwenden Sie eine vorhandene Tags-Eigenschaft:

  ![Vorhandenes Tag bei der Datenerfassung der Inhaltsanalyse](../assets/aca-configuration-datacollection-existingtag.png)

   1. Wählen Sie **[!UICONTROL Vorhandenes auswählen]**.
   2. Wählen Sie eine vorhandene Eigenschaft aus dem Dropdown **[!UICONTROL Menü „Eigenschaft für]**&quot; aus. Sie können mit der Eingabe beginnen, um nach den verfügbaren Optionen zu suchen und diese zu beschränken. Sie können keine Tags-Eigenschaft auswählen, die bereits von einer anderen implementierten Content Analytics-Konfiguration verwendet wird.


* So erstellen Sie eine neue Tag-Eigenschaft:

  ![Neues Tag bei der Datenerfassung der Inhaltsanalyse](../assets/aca-configuration-datacollection-newtag.png)

   1. Wählen Sie **[!UICONTROL Neu erstellen]** aus.
   1. Geben Sie einen **[!UICONTROL Tag-Namen]** an, z. B. `ACA Test for Documentation`.
   1. Geben Sie **[!UICONTROL Domains]** an, z. B. `example.com`.

* Geben Sie an, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen.

  Geben Sie eine Zeichenfolge für reguläre Ausdrücke für (**[!UICONTROL ein-/auszuschließende Seiten]** an. <br/>Beispiel: `^(?!.*documentation).*`, um alle Dokumentationsseiten aus Content Analytics auszuschließen.

* Geben Sie an, welche Assets bei der Datenerfassung zur Inhaltsanalyse eingeschlossen oder ausgeschlossen werden sollen.

  Geben Sie eine Zeichenfolge für reguläre Ausdrücke für **[!UICONTROL Assets an, die ein-/ausgeschlossen werden]**. <br/>Beispiel: `^(?!.*(logo\.jpg|\.svg)).*$`, um alle JPEG- und SVG-Logobilder von Content Analytics auszuschließen.

>[!IMPORTANT]
>
>Entfernen Sie manuell die automatisch eingeschlossene Web SDK-Erweiterung aus der neu erstellten Tags-Eigenschaft, falls Sie über eine bestehende Web SDK-Implementierung verfügen, die die [JavaScript](https://experienceleague.adobe.com/de/docs/experience-platform/web-sdk/install/library)Bibliothek anstelle der [Tags-Erweiterung) ](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration).
>



#### Vorhandene Konfiguration {#existing-configuration}

Für eine vorhandene Konfiguration können Sie die Eigenschaft Tags nicht bearbeiten. Sie können jedoch die Seiten und Assets bearbeiten, die ein- oder ausgeschlossen werden sollen.

* Um zu bearbeiten, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** unter **[!UICONTROL Erlebnis]**. Sie werden zur Erweiterung [Adobe Content Analytics umgeleitet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) die der Tags-Eigenschaft für die aktuelle Content Analytics-Konfiguration zugeordnet ist. Sie können den regulären Ausdruck bearbeiten, um Seiten ein- oder auszuschließen. Stellen Sie sicher[ dass Sie ](#publish) Änderungen veröffentlichen.

* Um zu bearbeiten, welche Assets bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** unter **[!UICONTROL Asset]** aus. Sie werden zur Erweiterung [Adobe Content Analytics umgeleitet](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) die der Tags-Eigenschaft für die aktuelle Content Analytics-Konfiguration zugeordnet ist. Sie können den regulären Ausdruck bearbeiten, um Assets ein- oder auszuschließen. Stellen Sie sicher[ dass Sie ](#publish) Änderungen veröffentlichen.

### Zusammenfassung {#summary}

Nachdem Sie alle erforderlichen Details bereitgestellt haben, enthält eine Zusammenfassung Details zu den Artefakten, die erstellt oder geändert werden.

* Beim Implementieren einer neuen Konfiguration wird Ihnen die Zusammenfassung **[!UICONTROL Sie sind fast bereit, _Konfigurationsname_ für die Inhaltsanalyse zu implementieren]** angezeigt.

* Für vorhandene implementierte Konfigurationen wird die Zusammenfassung **[!UICONTROL Sie haben _Konfigurationsname_ für die Inhaltsanalyse implementiert]** angezeigt.

![Zusammenfassung für die Inhaltsanalysekonfiguration](../assets/aca-configuration-summary.png)

### Aktionen {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Bestätigung der Implementierung"
>abstract="Wenn Sie **[!UICONTROL Implementieren]** auswählen, konfigurieren Sie die Inhaltsanalyse basierend auf den in diesem Workflow getätigten Eingaben. Standardmäßig werden mehrere Einstellungen auf Grundlage dessen ausgewählt, was im Allgemeinen für die Inhaltsanalyse nützlich ist. Als für die Daten verantwortliche Person müssen Sie jedoch die Einstellungen der einzelnen Artefakte überprüfen, um zu bestätigen, dass die Einstellungen in Übereinstimmung mit Ihrer Datenschutzrichtlinie, Ihren vertraglichen Rechten und Pflichten sowie den Einverständnisanforderungen nach geltendem Recht implementiert werden.<br/><br/>Beachten Sie, dass Daten erst dann erfasst werden, wenn die mit dieser Konfiguration verknüpfte Tag-Bibliothek manuell veröffentlicht wird.<br/><br/>Um Bild- und Textattribute abzuleiten, ruft Adobe die Attribute ab, und zwar mithilfe:<ol><li>der URL, die zum Zeitpunkt des Site-Besuchs von Benutzenden gemäß den von Ihnen konfigurierten Datenerfassungseinstellungen erfasst wurde, und</li><li>der URL, unter der das Bild gehostet wird.</li></ol>Bilder, die auf Websites von Drittanbietern gehostet werden, dürfen nicht mit Tags versehen werden."

<!-- markdownlint-enable MD034 -->

Wenn Sie eine Konfiguration erstellen oder bearbeiten, haben Sie die folgenden Optionen:

* **[!UICONTROL Verwerfen]**: Alle im Rahmen der Konfiguration vorgenommenen Änderungen werden verworfen.
* **[!UICONTROL Für später speichern]**: Änderungen an einer Konfiguration werden gespeichert. Sie können die Konfiguration zu einem späteren Zeitpunkt erneut aufrufen, um weitere Änderungen vorzunehmen, oder die Konfiguration implementieren. Zum Speichern einer Konfiguration [!UICONTROL  nur ein Wert für ]Name“ erforderlich.
* **[!UICONTROL Implementieren]**: Einstellungen für oder Änderungen an einer Konfiguration werden gespeichert und implementiert. Alle als &quot;![&quot; markierten ](/help/assets/icons/Required.svg) müssen über geeignete Werte verfügen. Die Implementierung besteht aus Folgendem:

   * **[!UICONTROL Customer Journey Analytics-Konfiguration]**:
      * Die ausgewählte Datenansicht wird aktualisiert, um Content Analytics-Dimensionen und -Metriken einzuschließen.
      * Die mit der ausgewählten Datenansicht verknüpfte Verbindung wird geändert, um Content Analytics-Ereignisse und -Attributdatensätze einzuschließen.
      * Workspace wird eine Berichtsvorlage für Content Analytics hinzugefügt.


   * **[!UICONTROL Adobe Experience Platform-Konfiguration]**:
      * Die Erstellung von Schemata zur Modellierung von Inhaltsanalyse-Ereignissen, Asset-Attributen und (sofern konfiguriert) Erlebnisattributen.
      * Die Erstellung von Datensätzen zur Erfassung von Inhaltsanalyse-Ereignissen, Asset-Attributen und (sofern konfiguriert) Erlebnisattributen.
      * Die Erstellung eines Datenflusses, der den Feature Service verwendet, um Inhaltsattribute aus Content Analytics-Ereignissen zu generieren und zu aktualisieren.


   * **[!UICONTROL Datenerfassungskonfiguration]**:
      * Die neue oder vorhandene Tags-Eigenschaft ist so konfiguriert, dass sie die Datenerfassung in Content Analytics unterstützt. Diese Konfiguration impliziert die Einbeziehung der Inhaltsanalyse-Erweiterung von Adobe für Tags.
      * Ein Datenstrom wird für Inhaltsanalyse-Ereignisse erstellt.
      * Die Inhaltsanalyse-Erweiterung von Adobe ist so konfiguriert, dass Inhaltsanalyse-Ereignisse an den Datenstrom für die Inhaltsanalyse gesendet werden.
      * Wenn das Web SDK nicht für die Tags-Eigenschaft konfiguriert ist, wird eine neue Web SDK-Konfiguration erstellt, um ausschließlich Inhaltsanalyse-Ereignisse zu senden.
      * Wenn die Web-SDK für diese Tags-Eigenschaft konfiguriert ist, werden an der vorhandenen Web-SDK-Konfiguration keine Änderungen vorgenommen.


* **[!UICONTROL Speichern]**: Änderungen an einer implementierten Konfiguration werden gespeichert und die Implementierung wird aktualisiert.
* **[!UICONTROL Beenden]**: Die geführte Konfiguration wird beendet. Alle Änderungen an einer implementierten Konfiguration werden verworfen.


## Veröffentlichen {#publish}

Um Daten für Ihre Content Analytics-Konfiguration zu erfassen, müssen Sie [manuell](manual.md) die Tags-Eigenschaft veröffentlichen, die nach der Auswahl von **[!UICONTROL Implementieren]** erstellt wird.


>[!MORELIKETHIS]
>
>[Manuelle Konfiguration](manual.md)
>
