---
title: Geführte Konfiguration für Content Analytics
description: Erfahren Sie, wie Sie Content Analytics mithilfe einer geführten Onboarding-Konfiguration konfigurieren.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
TQID: https://experienceleague.adobe.com/qfRVeaFTYitZOsleqfzxYsSlo5YZrTjdFqJSjIza-hg
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8fc9bde3d0b9eebfcc8185aff78ce0f7f2e7704f
workflow-type: tm+mt
source-wordcount: 4074
ht-degree: 47%

---


# Geführte Content Analytics-Konfiguration

Mit der geführten Konfiguration können Sie Content Analytics schnell und einfach konfigurieren. Bei der geführten Konfiguration wird ein Assistent verwendet, um die Anforderungen für die automatische Konfiguration von Content Analytics für Ihre Organisation festzulegen. Im Bildschirm **[!UICONTROL Konfiguration]** können Sie entweder eine neue Konfiguration erstellen oder eine vorhandene Konfiguration bearbeiten.

>[!IMPORTANT]
>
>Pro Sandbox ist in Ihrer Organisation nur eine Content Analytics-Konfiguration möglich.

>[!NOTE]
>
>Der Konfigurationsassistent unterstützt mehrere Datenansichten und Kanäle und unterscheidet sich von der früheren Version, die nur eine Datenansicht und nur den Webkanal unterstützte. Sie müssen eine Sandbox und eine Verbindung auswählen, bevor Sie eine oder mehrere Datenansichten im Abschnitt [Datenansichten](#data-views) auswählen können. Die Konfigurationen für **[!UICONTROL Erlebniserfassung]**, **[!UICONTROL Datenerfassung]** und **[!UICONTROL Kopfzeilenüberschreibungen]** sind kanalabhängig und Teil jedes Kanals, den Sie im Abschnitt [Kanäle](#channels) konfigurieren.

So greifen Sie auf die Content Analytics-Konfiguration zu:

* Wählen Sie aus dem Hauptmenü in Customer Journey Analytics die Option **[!UICONTROL Daten-Management]** > **[!UICONTROL Content Analytics-Konfiguration]** aus.

Im Bildschirm **[!UICONTROL Content Analytics-Konfigurationen]** wird eine Tabelle mit vorhandenen Content Analytics-Konfigurationen angezeigt.

![Content Analytics-Konfigurationen](../assets/aca-configuration-table.png)
Für jede Konfiguration stehen die folgenden Details zur Verfügung:

| Spalte | Beschreibung |
|---|---|
| **[!UICONTROL Name]** | Der Name der Konfiguration. |
| **[!UICONTROL Erstellt von]** | Das technische Konto, mit dem die Konfiguration erstellt wurde. |
| **[!UICONTROL Erstellt am]** | Der Zeitstempel, wann die Konfiguration erstellt wurde. |
| **[!UICONTROL Geändert am]** | Der Zeitstempel, wann die Konfiguration zuletzt geändert wurde. |
| **[!UICONTROL Sandbox]** | Die Sandbox in der Organisation, in der Content Analytics (voraussichtlich) konfiguriert und implementiert wird. |
| **[!UICONTROL Status]** | Der Status der Konfiguration. Der Status gibt an, für wie viele der aktivierten Kanäle die Konfiguration abgeschlossen ist. Verwenden ![InfoOutline](/help/assets/icons/InfoOutline.svg), um ein Popup mit weiteren Details zu öffnen. |

Sie können ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) verwenden, um die Tabelle anzupassen. Legen Sie fest, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]** aus, um die Änderungen anzuwenden.

Im Bildschirm **[!UICONTROL Konfiguration]** von Content Analytics können Sie eine neue Konfiguration erstellen oder eine vorhandene Konfiguration bearbeiten.

So erstellen Sie eine neue Konfiguration:

* Wählen Sie **[!UICONTROL Konfiguration erstellen]** aus. Hierdurch wird der [Assistent für geführte Konfigurationen](#guided-configuration-wizard) geöffnet.

So bearbeiten Sie eine vorhandene Konfiguration:

* Wählen Sie ![Mehr](/help/assets/icons/More.svg) und dann ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** für eine vorhandene Inhaltsanalysekonfiguration aus. Hierdurch wird der [Assistent für geführte Konfigurationen](#guided-configuration-wizard) geöffnet.

## Assistent für geführte Konfigurationen

Der Assistent für geführte Konfigurationen besteht aus vier Abschnitten ([Details](#details), [Verbindung](#connection), [Datenansicht](#data-view) und [Kanäle](#channels)), in denen Sie aufgefordert werden, die zum ordnungsgemäßen Einrichten und Konfigurieren von Content Analytics erforderlichen Details anzugeben. Schließen Sie jeden Abschnitt ab, bevor Sie zum nächsten Abschnitt wechseln, da einige Einstellungen in einem Abschnitt möglicherweise von den Konfigurationswerten in früheren Abschnitten abhängen.

### Details {#onboarding-details}

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Details"
>abstract="Geben Sie einen Namen für die Verbindung an. Geben Sie in den Abschnitten zu **[!UICONTROL Datenansicht]**, **[!UICONTROL Erlebniserfassung und -definition]** und **[!UICONTROL Datenerfassung]** weitere Details an, um sicherzustellen, dass die Inhaltsanalyse korrekt konfiguriert werden kann."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Details"
>abstract="In dieser Anleitung werden die Anforderungen für die Konfiguration der Inhaltsanalyse festgelegt. Geben Sie einen Namen für diese Konfiguration an"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_boldheader"
>title="Verbindung"
>abstract="**Verbindung**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_header"
>title="Verbindung"
>abstract="Wählen Sie eine bestehende Verbindung aus Customer Journey Analytics aus, mit der Sie Ihre Content Analytics-Daten zusammenführen möchten."

Jede Konfiguration erfordert einen eindeutigen Namen. Beispiel: `Example Content Analytics configuration`. Der Name ist zum Speichern oder Implementieren einer Konfiguration erforderlich.

Für jede Konfiguration müssen Sie auch die Sandbox auswählen, für die Sie Content Analytics konfigurieren möchten.

![Details zur Content Analytics-Konfiguration](../assets/aca-configuration-details.png)

* **[!UICONTROL Name]**: Jede Konfiguration erfordert einen eindeutigen Namen. Beispiel: `Example Content Analytics configuration`. Der Name ist zum Speichern oder Implementieren einer Konfiguration erforderlich.

* **[!UICONTROL Sandbox]**: Die Konfiguration erfordert eine Sandbox. Wählen Sie eine Sandbox aus der Liste der Sandboxes aus, auf die Sie Zugriff haben und in der die Daten erfasst werden, die Sie für Content Analytics verwenden möchten.

  Wenn Sie eine konfigurierte Sandbox ändern, für die Sie eine Verbindung und optional Datenansichten definiert haben, werden Sie benachrichtigt, dass die Verbindung und Datenansichten neu konfiguriert werden müssen.

### Verbindung

Sie müssen eine Verbindung auswählen, zu der Sie die Datenerfassung in Content Analytics hinzufügen möchten.

Wenn Sie keine Verbindung für Ihre Konfiguration ausgewählt haben:

1. Verwenden Sie ![Daten](/help/assets/icons/Data.svg) **[!UICONTROL Verbindung auswählen]** um das Dialogfeld **[!UICONTROL Verbindung auswählen]** zu öffnen, in dem alle in der Sandbox verfügbaren Verbindungen aufgelistet werden.
1. Wählen **[!UICONTROL im Dialogfeld „Verbindung auswählen]** die ![SelectBox](/help/assets/icons/SelectBox.svg) eine Verbindung aus, die Sie verwenden möchten. Sie können nur eine Verbindung auswählen.
1. Wählen **[!UICONTROL Verbindung verwenden]**.

Wenn Sie bereits eine Verbindung ausgewählt haben, diese jedoch ändern möchten:

1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus.
1. Ändern **[!UICONTROL im Dialogfeld „Verbindung auswählen]** die gewünschte Verbindung.
1. Wählen **[!UICONTROL Verbindung verwenden]**.


### Datenansichten {#onboarding-data-view}

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Datenansicht"
>abstract="Für die Konfiguration der Inhaltsanalyse müssen Sie eine vorhandene Datenansicht auswählen. So können Sie Ihre Content Analytics-Daten mit anderen Daten zusammenführen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Datenansicht"
>abstract="Wählen Sie eine vorhandene Datenansicht aus Customer Journey Analytics aus, mit der Ihre Content Analytics-Daten zusammengeführt werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Datenansicht"
>abstract="Wählen Sie eine vorhandene Datenansicht aus Customer Journey Analytics aus, mit der Ihre Content Analytics-Daten zusammengeführt werden sollen.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Neue Datenansicht"
>abstract="Sie haben eine neue Datenansicht für diese Konfiguration ausgewählt. Die neue Datenansicht wird aktualisiert, sodass sie die Dimensionen und Metriken der Inhaltsanalyse einschließt. Diese Metriken und Dimensionen werden aus der ursprünglich ausgewählten Datenansicht entfernt.<br/><br/>Wenn der neuen Datenansicht eine andere Verbindung zugeordnet ist, wird die Verbindung aktualisiert, sodass sie Datensätze der Inhaltsanalyse einschließt. Die Datensätze der Inhaltsanalyse werden nicht aus der ursprünglich ausgewählten Verbindung entfernt."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Bereinigen der ausgewählten Datenansicht"
>abstract="Sie haben eine Datenansicht ausgewählt, die bereits für Content Analytics bereitgestellt ist. Diese vorhandene Content Analytics-Konfiguration wird entfernt und die Datenansicht wird mit Ihrer neuen Konfiguration bereitgestellt."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Bereinigen der vorherigen Datenansicht"
>abstract="Sie haben eine neue Datenansicht ausgewählt. Die Content Analytics-Konfiguration für die zuvor ausgewählte Datenansicht wird entfernt."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="Neue Datenansicht"
>abstract="Sie haben eine neue Datenansicht für diese Konfiguration ausgewählt. Die neue Datenansicht wird aktualisiert, sodass sie die Dimensionen und Metriken der Inhaltsanalyse einschließt. Ähnliche Metriken und Dimensionen werden aus der vorhandenen Datenansicht entfernt.<br/>Wenn der neuen Datenansicht eine andere Verbindung zugeordnet ist, wird die Verbindung aktualisiert, sodass sie Datensätze der Inhaltsanalyse einschließt. Beachten Sie, dass Datensätze der Inhaltsanalyse nicht aus der vorhandenen Konfiguration entfernt werden."


>[!CONTEXTUALHELP]
>id="ac_onboarding_dataviews_button"
>title="Datenansicht"
>abstract="Für die Konfiguration von Content Analytics müssen Sie eine oder mehrere Datenansichten auswählen. So können Sie Ihre Content Analytics-Daten mit anderen Daten zusammenführen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header"
>title="Datenansichten"
>abstract="Wählen Sie eine oder mehrere bestehende Datenansichten aus Customer Journey Analytics aus, mit denen Sie Ihre Content Analytics-Daten zusammenführen möchten."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header_alt"
>title="Datenansichten"
>abstract="Wählen Sie eine oder mehrere bestehende Datenansichten aus Customer Journey Analytics aus, mit denen Sie Ihre Content Analytics-Daten zusammenführen möchten.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_new_dialog"
>title="Ausgewählte Datenansichten"
>abstract="Sie haben die ausgewählten Datenansichten für diese Konfiguration geändert. Die ausgewählten Datenansichten werden aktualisiert, um Content Analytics-Metriken und -Dimensionen einzuschließen. Diese Metriken und Dimensionen werden aus zuvor ausgewählten Datenansichten entfernt, die nicht mehr ausgewählt sind.<br/><br/>Wenn den ausgewählten Datenansichten eine andere Verbindung zugeordnet ist, wird die Verbindung aktualisiert, um Content Analytics-Datensätze einzuschließen. Die Datensätze der Inhaltsanalyse werden nicht aus der ursprünglich ausgewählten Verbindung entfernt.<br/><br/>Alle ausgewählten Datenansichten übernehmen die Kanäle, die Teil dieser Konfiguration sind."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_change_dialog"
>title="Ausgewählte Datenansichten"
>abstract="Sie haben die ausgewählten Datenansichten für diese Konfiguration geändert. Die ausgewählten Datenansichten werden aktualisiert, um Content Analytics-Metriken und -Dimensionen einzuschließen. Diese Metriken und Dimensionen werden aus zuvor ausgewählten Datenansichten entfernt, die nicht mehr ausgewählt sind.<br/><br/>Wenn den ausgewählten Datenansichten eine andere Verbindung zugeordnet ist, wird die Verbindung aktualisiert, um Content Analytics-Datensätze einzuschließen. Die Datensätze der Inhaltsanalyse werden nicht aus der ursprünglich ausgewählten Verbindung entfernt.<br/><br/>Alle ausgewählten Datenansichten übernehmen die Kanäle, die Teil dieser Konfiguration sind."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_current_cleanup_labels_dialog"
>title="Ausgewählte Datenansichten"
>abstract="Sie haben die ausgewählten Datenansichten für diese Konfiguration geändert. Die ausgewählten Datenansichten werden aktualisiert, um Content Analytics-Metriken und -Dimensionen einzuschließen. Diese Metriken und Dimensionen werden aus zuvor ausgewählten Datenansichten entfernt, die nicht mehr ausgewählt sind.<br/><br/>Wenn den ausgewählten Datenansichten eine andere Verbindung zugeordnet ist, wird die Verbindung aktualisiert, um Content Analytics-Datensätze einzuschließen. Die Datensätze der Inhaltsanalyse werden nicht aus der ursprünglich ausgewählten Verbindung entfernt.<br/><br/>Alle ausgewählten Datenansichten übernehmen die Kanäle, die Teil dieser Konfiguration sind."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_prev_cleanup_labels_dialog"
>title="Ausgewählte Datenansichten"
>abstract="Sie haben die ausgewählten Datenansichten für diese Konfiguration geändert. Die ausgewählten Datenansichten werden aktualisiert, um Content Analytics-Metriken und -Dimensionen einzuschließen. Diese Metriken und Dimensionen werden aus zuvor ausgewählten Datenansichten entfernt, die nicht mehr ausgewählt sind.<br/><br/>Wenn den ausgewählten Datenansichten eine andere Verbindung zugeordnet ist, wird die Verbindung aktualisiert, um Content Analytics-Datensätze einzuschließen. Die Datensätze der Inhaltsanalyse werden nicht aus der ursprünglich ausgewählten Verbindung entfernt.<br/><br/>Alle ausgewählten Datenansichten übernehmen die Kanäle, die Teil dieser Konfiguration sind."

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_button"
>title="Kanäle"
>abstract="Aktivieren und konfigurieren Sie einen oder mehrere Kanäle für die Konfiguration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_header"
>title="Kanäle"
>abstract="Aktivieren und konfigurieren Sie einen oder mehrere Kanäle für die Konfiguration. Alle Datenansichten, die Teil der Konfiguration sind, erben die aktivierten Kanäle."


Ihre Konfiguration erfordert die Auswahl einer oder mehrerer [Datenansichten](/help/data-views/data-views.md).

Wenn Sie keine Datenansichten für Ihre Konfiguration ausgewählt haben:

1. Verwenden Sie ![Daten](/help/assets/icons/Data.svg) **[!UICONTROL Datenansicht auswählen]** um das Dialogfeld **[!UICONTROL Datenansicht]** zu öffnen, das alle Datenansichten auflistet, die für die Verbindung verfügbar sind, die Sie für Content Analytics konfiguriert haben.
1. Wählen Sie **[!UICONTROL Dialogfeld]** Datenansicht“ die Option ![SelectBox](/help/assets/icons/SelectBox.svg) eine oder mehrere Datenansichten aus, die Sie verwenden möchten.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

Wenn Sie bereits eine oder mehrere Datenansichten ausgewählt haben, diese Auswahl jedoch ändern möchten:

1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Datenansichtsauswahl bearbeiten]**.
1. Ändern **[!UICONTROL im Dialogfeld]** Datenansicht“ die Auswahl ![SelectBox](/help/assets/icons/SelectBox.svg) der Datenansichten, die Sie verwenden möchten.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

Wenn Sie auf **[!UICONTROL Speichern]** klicken, sehen Sie das Dialogfeld **[!UICONTROL Ausgewählte Datenansichten]** in dem Sie über die Auswirkungen informiert werden, die die Einbeziehung von Content Analytics für die ausgewählten Datenansichten mit sich bringt. Wählen Sie **[!UICONTROL Fortfahren]**, um fortzufahren, oder **[!UICONTROL Abbrechen]**, um abzubrechen.

Die folgenden Aktionen sind im Dialogfeld **[!UICONTROL Datenansicht]** verfügbar:

* Um nach einem bestimmten Datensatz zu suchen, verwenden Sie das Suchfeld ![Suche](/help/assets/icons/Search.svg).
* Wählen Sie zum Filtern der Liste der verfügbaren Datenansichten ![Filter anzeigen](/help/assets/icons/Filter.svg) aus. Sie können die Liste nach [!UICONTROL Inhaber].<br/>Verwenden Sie ![Ausblenden](/help/assets/icons/Filter.svg)**[!UICONTROL Filter ausblenden]**, um den Segmentbereich auszublenden.
* Um zu definieren, welche Spalten in der Tabelle angezeigt werden sollen, wählen Sie ![Spalteneinstellungen](/help/assets/icons/ColumnSetting.svg) aus. Wählen Sie aus, welche Spalten im Dialogfeld **[!UICONTROL Tabelle anpassen]** angezeigt werden sollen, und wählen Sie **[!UICONTROL Anwenden]** aus, um die Änderungen anzuwenden.

### Kanäle

Im Abschnitt **[!UICONTROL Kanäle]** wählen Sie die Kanäle aus, die Sie für Content Analytics aktivieren möchten. Sie können zwischen **[!UICONTROL Mobil]** und **[!UICONTROL Web]** wählen.

* Um einen Kanal auszuwählen, den Sie noch nicht konfiguriert haben, klicken Sie auf **[!UICONTROL Aktivieren]**.
* Um einen Kanal auszuwählen, der bereits konfiguriert ist, für den Sie jedoch die Konfiguration ändern möchten, wählen Sie **[!UICONTROL Konfiguration bearbeiten]**.

Anschließend können Sie den Kanal detaillierter konfigurieren. Diese Konfiguration unterscheidet sich, je nachdem, ob Sie eine Konfiguration für den Kanal [Mobil](#mobile) oder [Web](#web) aktivieren und konfigurieren oder bearbeiten.

#### Mobile {#mobile}

<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_boldheader"
>title="Datenerfassung für mobile Erlebnisspeicherorte"
>abstract="**Auszuschließende Erlebnisorte**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_header"
>title="Datenerfassung für mobile Erlebnisspeicherorte"
>abstract="Geben Sie an, welche Erlebnisspeicherorte **ausgeschlossen) werden sollen** wenn Daten für Content Analytics erfasst werden. Stellen Sie sicher, dass Sie persönlich identifizierbare Erlebnisorte ausschließen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_boldheader"
>title="Datenerfassung für mobile Asset-Speicherorte"
>abstract="**Auszuschließende Asset-Speicherorte**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_header"
>title="Datenerfassung für mobile Asset-Speicherorte"
>abstract="Geben Sie an, welche Asset-Speicherorte **ausgeschlossen** beim Erfassen von Daten für Content Analytics ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Asset-Speicherorte ausschließen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_boldheader"
>title="Datenerfassung für mobile Asset-URLs"
>abstract="**Auszuschließende Asset-URLs**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_header"
>title="Datenerfassung für mobile Asset-URLs"
>abstract="Geben Sie an, welche Asset-URLs **der Datenerfassung für** Content Analytics ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Asset-URLs ausschließen."

Für den mobilen Kanal können Sie [Erlebniserfassung und -definition](#experience-capture-and-definition), [Datenerfassung](#data-collection) und [Überschreibungen](#header-overrides) konfigurieren.

##### Erlebniserfassung und -definition {#mobile-experience-capture-and-definition}

In diesem Abschnitt können Sie auswählen, ob Erlebnisse in die Mobile-Daten einbezogen werden sollen, die Sie mit Content Analytics erfassen.  Für den Mobile-Kanal haben Sie sich mit der Adobe Experience Platform SDK für Content Analytics als Erlebnis registriert.

Standardmäßig ist **[!UICONTROL Erlebnisse einschließen]** deaktiviert.

Erwägen Sie nur, Erlebnisse einzubeziehen, wenn Sie Ihre Mobile App so instrumentiert haben, dass Erlebnisse registriert und Erlebnisansichten und -klicks verfolgt werden.

##### Datenerfassung {#mobile-data-collection}

Mit den Datenerfassungseinstellungen können Sie festlegen, welche Daten (Erlebnisspeicherorte, Asset-Speicherorte, Asset-URLs) Sie für Content Analytics erfassen möchten. Stellen Sie sicher, dass Sie im Rahmen dieser Datenerfassung keine personenbezogenen Daten erfassen.

Konfigurieren der Datenerfassung:

* Verwenden Sie eine vorhandene Eigenschaft für mobile Tags oder erstellen Sie eine neue Eigenschaft für mobile Tags.

   * So verwenden Sie eine vorhandene Mobile-Tags-Eigenschaft:

      1. Wählen Sie **[!UICONTROL Vorhandene auswählen]**.
      2. Wählen Sie aus dem Dropdown-Menü **[!UICONTROL Tags-Eigenschaft]** eine vorhandene Eigenschaft aus. Sie können mit der Eingabe beginnen, um nach den verfügbaren Optionen zu suchen und diese zu beschränken. Sie können keine Tags-Eigenschaft auswählen, die bereits von einer anderen implementierten Content Analytics-Konfiguration verwendet wird.


   * So erstellen Sie eine neue mobile Tags-Eigenschaft:

      1. Wählen Sie **[!UICONTROL Neu erstellen]** aus.
      1. Geben Sie einen **[!UICONTROL Tags-Namen]** an, z. B. `ACA Test for Documentation`.
      1. Geben Sie **[!UICONTROL Domains]** an, z. B. `example.com`.

* Geben Sie an, welche Erlebnisspeicherorte bei der Datenerfassung für Content Analytics ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Erlebnisorte ausschließen.

  Geben Sie eine **[!UICONTROL Zeichenfolge für reguläre Ausdrücke]** für **[!UICONTROL Auszuschließende Erlebnisspeicherorte]** an. <br/>Beispiel: `^(?!.*documentation).*`, um alle Dokumentations-Erlebnisspeicherorte von Content Analytics auszuschließen.

* Geben Sie an, welche Asset-Speicherorte bei der Datenerfassung für Content Analytics ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Asset-Speicherorte ausschließen.

  Geben Sie eine **[!UICONTROL Zeichenfolge für reguläre Ausdrücke]** für **[!UICONTROL Auszuschließende Asset-Speicherorte]** an. <br/>Beispiel: `^(?!.*(logo\.jpg)).*$`, um alle Asset-Speicherorte mit JPEG-Logo-Bildern aus Content Analytics auszuschließen.

* Geben Sie an, welche Asset-URLs bei der Datenerfassung für Content Analytics ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Asset-URLs ausschließen.

  Geben Sie eine **[!UICONTROL Zeichenfolge für reguläre Ausdrücke]** für **[!UICONTROL auszuschließende Asset-URLs]** an. <br/>Zum Beispiel: `^(?!.*(logo\.jpg)).*$`, um alle Asset-URLs auszuschließen, die auf JPEG-Logo-Bilder in Content Analytics verweisen.


##### Überschreibungen des Headers {#mobile-header-overrides}

<!-- needs modification for mobile channel -->

Optional können Sie im Abschnitt **[!UICONTROL Überschreibungen der Kopfzeile]** einen Kopfzeilennamen und einen geheimen Kopfzeilenwert angeben.  Diese Kopfzeile überschreibt die Konfiguration und stellt sicher, dass Content Analytics eine benutzerdefinierte HTTP-Kopfzeile sendet, um Mobile-App-Assets abzurufen, wobei die Bot-Erkennung oder Traffic-Gating-Technologien umgangen werden.

![Abschnitt „Überschreibungen der Kopfzeile“](/help/content-analytics/assets/aca-configuration-header-overrides.png)

1. Aktivieren **[!UICONTROL Konfigurieren von Kopfzeilenüberschreibungen]**.
1. Geben Sie den **[!UICONTROL Header-Namen]** ein. Zum Beispiel `x-asset-service`.
1. Geben Sie den **[!UICONTROL Header-Wert]** ein. Was auch immer Sie angeben, ist geheim und in der Benutzeroberfläche nicht sichtbar (es sei denn, Sie geben explizit den Wert ![Sichtbarkeit](/help/assets/icons/Visibility.svg) während der Eingabe an).

##### Speichern {#mobile-save}

Nachdem Sie den Mobile-Kanal konfiguriert haben, klicken Sie auf **[!UICONTROL Speichern]**, um die Konfiguration zu speichern. Wählen Sie **[!UICONTROL Abbrechen]**, um die Konfiguration abzubrechen.


#### Web {#web}

Für den Web-Kanal können Sie [Erlebniserfassung und -definition](#experience-capture-and-definition-1), [Datenerfassung](#data-collection-1) und [Überschreibungen](#header-overrides-1).

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie können auswählen, dass Erlebnisse in die mit Content Analytics erfassten Daten eingeschlossen werden. Wenn diese Option aktiviert ist, müssen Sie eine oder mehrere Kombinationen aus einem regulären Ausdruck und Abfrageparametern definieren, um festzulegen, für welche URLs Erlebnisse eingeschlossen werden sollen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Erlebniserfassung und -definition"
>abstract="Erlebnisse in Content Analytics erfassen"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Erlebniserfassung und -definition"
>abstract="Geben Sie die Parameter an, die bestimmen, wie Inhalte auf Ihrer Website gerendert werden."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Erlebniserfassung und -definition"
>abstract="Wenn diese Option aktiviert ist, werden Erlebnisdaten erfasst und Erlebnisattribute generiert. Außerdem sind Erlebnisberichte verfügbar."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Erlebniserfassung und -definition"
>abstract="Wenn diese Option aktiviert ist, werden Erlebnisdaten erfasst und Erlebnisattribute generiert. Außerdem sind Erlebnisberichte verfügbar. <br><br/>Verwenden Sie ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]**, um die Datenerfassungskonfiguration für Erlebnisse in der Tags-Eigenschaft zu ändern, die mit der aktuellen Konfiguration verknüpft ist."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Erlebniserfassung und -definition"
>abstract="Sie müssen die Einstellungen für die Erlebnisdatenerfassung in der Adobe Content Analytics-Erweiterung bearbeiten."

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
>abstract="Geben Sie an, welche Seiten bei **Datenerfassung für erfasst werden sollen** oder **ausgeschlossen**. Stellen Sie sicher, dass Sie persönlich identifizierbare Seiten ausschließen."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Datenerfassung"
>abstract="**Einzuschließende/auszuschließende Assets**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Datenerfassung"
>abstract="Geben Sie an, welche Assets bei **Datenerfassung für erfasst** **ausgeschlossen** werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Assets ausschließen."

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


<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_boldheader"
>title="Datenerfassung für Web-Seiten"
>abstract="**Einzuschließende/auszuschließende Seiten**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_header"
>title="Datenerfassung für Web-Seiten"
>abstract="Geben Sie an, welche Seiten bei **Datenerfassung für erfasst werden sollen** oder **ausgeschlossen**."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_boldheader"
>title="Datenerfassung für Web-Assets"
>abstract="**Einzuschließende/auszuschließende Assets**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_header"
>title="Datenerfassung für Web-Assets"
>abstract="Geben Sie an, welche Assets bei **Datenerfassung für erfasst** **ausgeschlossen** werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Assets ausschließen."


##### Erlebniserfassung und -definition {#web-experience-capture-and-definition}

In diesem Abschnitt können Sie auswählen, ob Erlebnisse in die Web-Daten einbezogen werden sollen, die Sie mit Content Analytics erfassen.  Ein Erlebnis besteht aus dem gesamten Text auf einer Web-Seite, der anhand der URL des ersten Benutzerbesuchs reproduzierbar ist.

Standardmäßig ist **[!UICONTROL Erlebnisse einschließen]** deaktiviert. Wenn diese Option aktiviert ist, definieren Sie die URLs, für die Sie Erlebnisse einbeziehen möchten.

Ziehen Sie das Einschließen von Erlebnissen nur in Betracht, wenn Folgendes zutrifft:

* Die Seiten auf der Site müssen unter Verwendung der Seiten-URL reproduzierbar sein.
* Der Textinhalt, der einer Person angezeigt wird, kann über die Seiten-URL reproduziert werden und hängt nicht von Cookies oder anderen Personalisierungsmechanismen ab.

>[!IMPORTANT]
>
>Implementieren Sie die [Content Analytics-Versionierung](manual.md#versioning), um Änderungen zu erfassen, die Sie an den Erlebnissen (Seiten) vornehmen, die Content Analytics unterliegen.



###### Neue Konfiguration {#new-experiences-configuration}

So schließen Sie Erlebnisse in eine neue oder nicht implementierte Konfiguration ein:

![Erfassung und Definition von Erlebnissen bei der Konfiguration von Content Analytics](../assets/aca-configuration-experience.png)

1. Aktivieren Sie **[!UICONTROL Erlebnisse einschließen]**. Das Umschalten zum Aktivieren von Erlebnissen wirkt sich auf Folgendes aus:

   * die Datenerfassung in der Content Analytics-Erweiterung
   * den Prozess, der Erlebnisattribute aus Content Analytics-Ereignisdaten generiert
   * die Berichtsvorlage in Customer Journey Analytics

1. Wählen Sie **[!UICONTROL Regex hinzufügen]**, um eine Kombination aus einem regulären Domain-Ausdruck und Abfrageparametern hinzuzufügen.
1. Geben Sie an, wie Inhalte auf Ihrer Website gerendert werden, indem Sie Kombinationen aus einem **[!UICONTROL regulären Domain-]**) und **[!UICONTROL Abfrageparametern]** definieren, die sich auf den Seiteninhalt auswirken.
   1. Geben Sie einen **[!UICONTROL regulären Domain-Ausdruck]** ein, z. B. `/^(?!.*\b(store|help|admin)\b)/`. Stellen Sie sicher, dass Sie reguläre Ausdrücke mit dem Escape-Zeichen `/` versehen. Der reguläre Ausdruck der Domain gibt an, für welche URLs diese Parameter gelten. Beispielsweise können Sie über mehrere Sites verfügen, bei denen für jede Site der Inhalt durch andere Parameter gesteuert wird. Wenn die Abfrageparameter für alle Ihre Seiten gelten, können Sie `.*` verwenden, um alle Seiten anzugeben.
   1. Geben Sie eine kommagetrennte Liste von **[!UICONTROL Abfrageparametern]** an, z. B. `outdoors, patio, kitchen`.
1. Wählen Sie **[!UICONTROL Entfernen]** aus, wenn Sie eine Kombination aus regulärem Domain-Ausdruck und Abfrageparametern entfernen möchten.
1. Wählen Sie **[!UICONTROL Regulären Ausdruck hinzufügen]** aus, wenn Sie eine weitere Kombination aus einem regulären Ausdruck und Abfrageparametern hinzufügen möchten.


###### Implementierte Konfiguration {#implemented-experiences-configuration}

So bearbeiten Sie vorhandene Erlebnisse oder schließen neue Erlebnisse in eine implementierte Konfiguration ein:

![Erlebniserfassung und -definition bei der Content Analytics-Konfiguration](../assets/aca-configuration-experience-edit.png)

* Schalten Sie **[!UICONTROL Erlebnisse einschließen]** um, um Folgendes zu aktivieren bzw. zu deaktivieren:

   * den Prozess, der Erlebnisattribute aus Content Analytics-Ereignisdaten generiert
   * die Berichtsvorlage in Customer Journey Analytics

* Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]** aus, um die Konfiguration der Datenerfassung für Erlebnisse in Content Analytics weiter zu bearbeiten. Sie werden zur [Adobe Content Analytics-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) in der Tags-Eigenschaft weitergeleitet, die mit der aktuellen Konfiguration verknüpft ist.

##### Datenerfassung {#web-data-collection}

Mit den Datenerfassungseinstellungen können Sie festlegen, welche Daten (Seiten, Assets) Sie für Content Analytics erfassen möchten. Sammeln Sie im Rahmen dieser Datenerfassung keine personenbezogenen Daten.

Konfigurieren der Datenerfassung:

* Verwenden Sie eine vorhandene Web-Tags-Eigenschaft oder erstellen Sie eine neue Web-Tags-Eigenschaft.

   * So verwenden Sie eine vorhandene Web-Tags-Eigenschaft:

      1. Wählen Sie **[!UICONTROL Vorhandene auswählen]**.
      2. Wählen Sie aus dem Dropdown-Menü **[!UICONTROL Tags-Eigenschaft]** eine vorhandene Eigenschaft aus. Sie können mit der Eingabe beginnen, um nach den verfügbaren Optionen zu suchen und diese zu beschränken. Sie können keine Tags-Eigenschaft auswählen, die bereits von einer anderen implementierten Content Analytics-Konfiguration verwendet wird.


   * So erstellen Sie eine neue Web-Tags-Eigenschaft:

      1. Wählen Sie **[!UICONTROL Neu erstellen]** aus.
      1. Geben Sie einen **[!UICONTROL Tags-Namen]** an, z. B. `ACA Test for Documentation`.
      1. Geben Sie **[!UICONTROL Domains]** an, z. B. `example.com`.

     Verwenden Sie eine neue Tags-Eigenschaft, wenn Sie mithilfe der [Content Analytics-JavaScript-Bibliothek eine Tags-unabhängige Implementierung für den Webkanal erstellen ](/help/content-analytics/config/tags-agnostic.md). Die Tags-Eigenschaft wird erstellt, Sie werden die Eigenschaft jedoch nicht in der agnostischen Implementierung verwenden. Für die agnostische Implementierung müssen Sie jedoch den Assistenten für geführte Konfigurationen mindestens einmal ausgeführt haben.

* Geben Sie an, welche Seiten bei der Datenerfassung für Content Analytics ein- oder ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Seiten ausschließen.

  Geben Sie eine **[!UICONTROL Zeichenfolge für reguläre Ausdrücke]** für **[!UICONTROL Seiten zum Ein-/Ausschließen]** an. <br/>Beispiel: `^(?!.*documentation).*`, um alle Dokumentationsseiten aus Content Analytics auszuschließen.

* Geben Sie an, welche Assets bei der Datenerfassung für Content Analytics eingeschlossen oder ausgeschlossen werden sollen. Stellen Sie sicher, dass Sie persönlich identifizierbare Assets ausschließen.

  Geben Sie eine **[!UICONTROL Zeichenfolge für reguläre Ausdrücke]** für **[!UICONTROL Ein-/Auszuschließendes Asset]** an. <br/>Beispiel: `^(?!.*(logo\.jpg)).*$`, um alle Logo-Bilder im JPEG-Format aus Content Analytics auszuschließen.


##### Überschreibungen des Headers {#web-header-overrides}

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_header_overrides_boldheader"
>title="Überschreibungen des Headers"
>abstract="**Überschreibungen der Kopfzeile**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_header_overrides_header"
>title="Überschreibungen des Headers"
>abstract="Erweiterte Funktion zur Umgehung der Bot-Erkennung oder des Gate-Traffics. Content Analytics schließt beim Aufrufen Ihrer Endpunkte Ihre benutzerdefinierten HTTP-Kopfzeilen ein."

<!-- needs modification for mobile channel -->

Optional können Sie im Abschnitt **[!UICONTROL Überschreibungen der Kopfzeile]** einen Kopfzeilennamen und einen geheimen Kopfzeilenwert angeben.  Diese Header-Überschreibungskonfiguration stellt sicher, dass Content Analytics benutzerdefinierte HTTP-Header sendet, um die von Ihnen implementierte Bot-Erkennung oder Traffic-Gating-Technologien zu umgehen.

![Abschnitt „Überschreibungen der Kopfzeile“](/help/content-analytics/assets/aca-configuration-header-overrides.png)

1. Aktivieren **[!UICONTROL Konfigurieren von Kopfzeilenüberschreibungen]**.
1. Geben Sie den **[!UICONTROL Header-Namen]** ein. Zum Beispiel `x-asset-service`.
1. Geben Sie den **[!UICONTROL Header-Wert]** ein. Was auch immer Sie angeben, ist geheim und in der Benutzeroberfläche nicht sichtbar (es sei denn, Sie geben explizit den Wert ![Sichtbarkeit](/help/assets/icons/Visibility.svg) während der Eingabe an).

#### Speichern {#web-save}

Nachdem Sie die Details für den Webkanal angegeben haben, klicken Sie auf **[!UICONTROL Speichern]**, um die Konfiguration zu speichern. Wählen Sie **[!UICONTROL Abbrechen]**, um die Konfiguration abzubrechen.


### Zusammenfassung {#summary}

Nachdem Sie alle erforderlichen Details angegeben haben, werden die Informationen zu den erstellten oder geänderten Artefakten in einer Zusammenfassung aufgeführt.

* Beim Implementieren einer neuen Konfiguration wird Ihnen die Zusammenfassung **[!UICONTROL Sie sind fast bereit, _Konfigurationsname_ für Content Analytics zu implementieren]** angezeigt.

* Für vorhandene implementierte Konfigurationen wird die Zusammenfassung **[!UICONTROL Sie haben _Konfigurationsname_ für Content Analytics implementiert]** angezeigt.

![Zusammenfassung für die Content Analytics-Konfiguration](../assets/aca-configuration-summary.png)

### Aktionen {#actions}

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Bestätigung der Implementierung"
>abstract="Wenn Sie **[!UICONTROL Implementieren]** auswählen, konfigurieren Sie die Inhaltsanalyse basierend auf den in diesem Workflow getätigten Eingaben. Standardmäßig werden mehrere Einstellungen auf Grundlage dessen ausgewählt, was im Allgemeinen für die Inhaltsanalyse nützlich ist. Als für die Daten verantwortliche Person müssen Sie jedoch die Einstellungen der einzelnen Artefakte überprüfen, um zu bestätigen, dass die Einstellungen in Übereinstimmung mit Ihrer Datenschutzrichtlinie, Ihren vertraglichen Rechten und Pflichten sowie den Einverständnisanforderungen nach geltendem Recht implementiert werden.<br/><br/>Beachten Sie, dass Daten erst dann erfasst werden, wenn die mit dieser Konfiguration verknüpfte Tag-Bibliothek manuell veröffentlicht wird.<br/><br/>Um Bild- und Textattribute abzuleiten, ruft Adobe die Attribute ab, und zwar mithilfe:<ol><li>der URL der Seite, die zum Zeitpunkt des Site-Besuchs von Benutzenden gemäß den von Ihnen konfigurierten Datenerfassungseinstellungen erfasst wurde, und</li><li>der URL, unter der das Bild gehostet wird.</li></ol>Bilder, die auf Websites von Drittanbietern gehostet werden, dürfen nicht mit Tags versehen werden."

Wenn Sie eine Konfiguration erstellen oder bearbeiten, haben Sie die folgenden Optionen:

* **[!UICONTROL Verwerfen]**: Alle im Rahmen der Konfiguration vorgenommenen Änderungen werden verworfen.
* **[!UICONTROL Für später speichern]**: Änderungen an einer Konfiguration werden gespeichert. Sie können die Konfiguration zu einem späteren Zeitpunkt erneut aufrufen, um weitere Änderungen vorzunehmen, oder die Konfiguration implementieren. Zum Speichern einer Konfiguration ist lediglich ein Wert für [!UICONTROL Name] erforderlich.
* **[!UICONTROL Implementieren]**: Einstellungen für oder Änderungen an einer Konfiguration werden gespeichert und implementiert. Alle als &quot;![&quot; markierten ](/help/assets/icons/Required.svg) müssen über korrekte Werte verfügen. Die Implementierung besteht aus Folgendem:

   * **[!UICONTROL Customer Journey Analytics-Konfiguration]**:
      * Die ausgewählte Datenansicht wird aktualisiert, um Content Analytics-Dimensionen und -Metriken einzuschließen.
      * Die mit der ausgewählten Datenansicht verknüpfte Verbindung wird geändert, um Ereignis- und Attributdatensätze von Content Analytics einzuschließen.
      * Eine Content Analytics-Berichtsvorlage wird zu Workspace hinzugefügt.


   * **[!UICONTROL Adobe Experience Platform-Konfiguration]**:
      * Die Erstellung von Schemata zur Modellierung von Content Analytics-Ereignissen, Asset-Attributen und (sofern konfiguriert) Erlebnisattributen.
      * Die Erstellung von Datensätzen zur Erfassung von Content Analytics-Ereignissen, Asset-Attributen und (sofern konfiguriert) Erlebnisattributen.
      * Die Erstellung eines Datenflusses, der den Featurisierungs-Service verwendet, um Inhaltsattribute aus Content Analytics-Ereignissen zu generieren und zu aktualisieren.


   * **[!UICONTROL Konfiguration der Datenerfassung]**:
      * Die neue oder vorhandene Tags-Eigenschaft ist so konfiguriert, dass sie die Content Analytics-Datenerfassung unterstützt. Diese Konfiguration impliziert die Einbeziehung der Content Analytics-Erweiterung von Adobe für Tags.
      * Ein Datenstrom wird für Content Analytics-Ereignisse erstellt.
      * Die Content Analytics-Erweiterung von Adobe ist so konfiguriert, dass Content Analytics-Ereignisse an den Datenstrom für Content Analytics gesendet werden.
      * Wenn die Web-SDK oder Mobile-SDK nicht für die Tags-Eigenschaft konfiguriert ist, wird eine neue Web-SDK- oder Mobile-SDK-Konfiguration erstellt, um nur Content Analytics-Ereignisse zu senden.
      * Wenn Web SDK oder Mobile SDK für die Tags-Eigenschaft konfiguriert ist, werden an der vorhandenen Web SDK- oder Mobile SDK-Konfiguration keine Änderungen vorgenommen.


* **[!UICONTROL Speichern]**: Änderungen an einer implementierten Konfiguration werden gespeichert und die Implementierung wird aktualisiert.
* **[!UICONTROL Beenden]**: Die geführte Konfiguration wird beendet. Alle Änderungen an einer implementierten Konfiguration werden verworfen.


## Veröffentlichen {#publish}

Um Daten für Ihre Content Analytics-Konfiguration zu erfassen, müssen Sie [manuell](manual.md) die erstellten Tag-Eigenschaften für die von Ihnen aktivierten Kanäle veröffentlichen.


>[!MORELIKETHIS]
>
>[Manuelle Konfiguration](manual.md)
>

