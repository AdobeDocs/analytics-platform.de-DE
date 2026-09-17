---
title: Migrieren von AppMeasurement oder Tags zu XDM
description: Erfahren Sie mehr über die Migration von AppMeasurement oder Tags zu XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '2338'
ht-degree: 16%
---
# Migrieren von Tags zu XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="Migrationsübersicht"
>abstract="Migrieren Sie beim Upgrade auf Customer Journey Analytics eine Tags-Implementierung in das Adobe Experience Platform Web SDK.<br/>Fahren Sie mit einer bestehenden Migration fort oder starten Sie eine neue."

<!-- markdownlint-enable MD034 -->

Der Migrationsplaner bietet einen Migrationsassistenten, der die Migration von Tags zu XDM automatisiert, einschließlich der Schemaerstellung. Dies sind einige der komplexesten und zeitaufwendigsten Aufgaben im Zusammenhang mit einem Upgrade von Adobe Analytics auf Customer Journey Analytics.

## Unterstützte Adobe Analytics-Implementierungen

Der Migrationsplaner unterstützt Adobe Analytics-Implementierungen, die die Analytics-Erweiterung (Tags) verwenden.

Der Migrationsplaner ist nicht für Adobe Analytics-Implementierungen verfügbar, die AppMeasurement oder die Experience Platform Web SDK verwenden.

## Im Migrationsplaner enthaltene Upgrade-Aufgaben

Der Migrationsplaner bietet einen Migrationsassistenten, der die folgenden komplexen und zeitaufwendigen Upgrade-Aufgaben automatisiert:

* **XDM-Schemaerstellung**: Erstellt automatisch ein neues XDM-Schema, das auf Ihren Adobe Analytics Report Suite-Variablen basiert. Der Migrationsplaner scannt Ihre Adobe Analytics-Report-Suite-Variablen intelligent und verwendet diese Informationen, um die erforderlichen Felder in XDM zu erstellen. Das resultierende XDM-Schema enthält nur die Felder, die in Ihrem Customer Journey Analytics-Schema benötigt werden.

  Alternativ können Sie auf ein vorhandenes XDM-Schema verweisen oder ein XDM-Schema von Grund auf neu erstellen.

  +++ Wenn Sie sich dafür entscheiden, ein XDM-Schema von Grund auf neu zu erstellen, können Sie diesen Abschnitt erweitern, um Informationen zu hilfreichen Ressourcen zu erhalten.

  * [Planen Sie Ihre XDM-Schemaarchitektur](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

  * [Erstellen Sie das gewünschte benutzerdefinierte Schema in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

    Beachten Sie beim Erstellen Ihres Schemas die folgenden Optionen:

    * Wenn Sie Customer Journey Analytics mit RTCDP integrieren möchten, müssen Sie die Option **[!UICONTROL Profil]** für Ihr Schema aktivieren, wie in [Erstellen eines XDM-Schemas zur Verwendung mit Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"} beschrieben. Wenn diese Option aktiviert ist und Daten auf der Basis dieses Schemas in Datensätze aufgenommen werden, werden diese Daten mit dem Echtzeit-Kundenprofil zusammengeführt.

    * Wenn Sie Streaming-Mediendaten einbeziehen möchten, müssen Sie [Ihr Schema für die Aufnahme und Verwendung von Streaming-Daten konfigurieren](/help/data-ingestion/streaming.md){target="_blank"}.

    +++

  * **Migration Ihrer Adobe Analytics-Implementierung auf die Web-SDK**: Unabhängig davon, ob Ihre Adobe Analytics-Implementierung Tags oder JavaScript verwendet, führt Sie der Migrationsplaner durch die Migration auf die Experience Platform Web-SDK.

    * **Migrieren von Tag-Eigenschaften aus AppMeasurement in die Web-SDK**:

    * **Migrieren einer JavaScript-Implementierung von AppMeasurement zur Web SDK JavaScript-Bibliothek**

  * **Erstellen von Datenansichten in Customer Journey Analytics**: Erstellt automatisch Datenansichten und befüllt diese mit Komponenten, basierend auf den erstellten XDM-Schemafeldern.


## Voraussetzungen

Bevor Sie eine Migration erstellen, stellen Sie Folgendes sicher:

* Eine unterstützte Adobe Analytics-Implementierung (die Analytics-Erweiterung für Tags). Siehe [Unterstützte Adobe Analytics-Implementierungen](#supported-adobe-analytics-implementations).

* Zugriff auf die Adobe Tags-Eigenschaft, die Sie migrieren möchten, in der Experience Cloud-Organisation, bei der Sie angemeldet sind.

* Zugriff auf die Adobe Analytics Report Suite, deren Variablen Sie XDM zuordnen möchten.

* Berechtigung zum Erstellen von Schemata in Adobe Experience Platform.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Migrieren einer Analytics-Implementierung zum Web SDK

Eine Migration durchläuft drei Phasen: [!UICONTROL **Audit**], [!UICONTROL **Mapping**] und [!UICONTROL **Implementierung**]. Führen Sie die folgenden Schritte aus, um eine Migration zu erstellen, und fahren Sie dann mit [Migration validieren und bereitstellen](#validate-and-deploy-a-migration) fort, um jedes einzelne Stadium abzuschließen.

1. Öffnen Sie in Customer Journey Analytics den [!UICONTROL **Migrationsplaner**].

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. Wählen Sie im Migrationsplaner auf der Registerkarte [!UICONTROL **Migrationen**] die Option [!UICONTROL **Neu**] aus.

   <!-- Confirm the exact image: ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png) -->


1. Geben Sie die folgenden Informationen an:

   | Feldname | Funktion |
   | --------- | ---------- |
   | [!UICONTROL **Name**] | Geben Sie einen Namen für diese Migration an. |
   | [!UICONTROL **Beschreibung**] | Geben Sie eine optionale Beschreibung für diese Migration an. |
   | [!UICONTROL **Tags-Eigenschaft**] | Wählen Sie die Adobe Tags-Eigenschaft aus, die Sie migrieren möchten. Weitere Informationen finden Sie unter [Eigenschaften](https://experienceleague.adobe.com/de/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"} in der Experience Platform-Dokumentation. |
   | [!UICONTROL **Tags-Bibliothek**] | Wählen Sie den Snapshot der Tag-Bibliothek aus, auf dem die Migration basiert. Der Schnappschuss bestimmt, welche Version Ihrer Tag-Bibliothek verwendet wird. Weitere Informationen finden Sie unter [Publishing-Übersicht](https://experienceleague.adobe.com/de/docs/experience-platform/tags/publish/overview){target="_blank"} in der Dokumentation zu Experience Platform. |

1. Geben [!UICONTROL **im Feld**] einen Namen für diese Migration ein und klicken Sie dann auf [!UICONTROL **Weiter**].

1. Wählen Sie die Tag-Eigenschaft aus, die Sie migrieren möchten, und klicken Sie dann auf [!UICONTROL **Weiter**].

   Es werden nur die Tag-Eigenschaften angezeigt, die für Ihre angemeldete Experience Cloud-Organisation verfügbar sind.

1. Wählen Sie den Snapshot der Tag-Bibliothek aus, den Sie migrieren möchten, und klicken Sie dann auf [!UICONTROL **Weiter**].

   Der Snapshot bestimmt, auf welcher Version Ihrer Tag-Bibliothek die Migration basiert. Jeder Schnappschuss zeigt seine Umgebung an ([!UICONTROL **Entwicklung**], [!UICONTROL **Staging**] oder [!UICONTROL **&#x200B;**]).

1. Wählen Sie den Zuordnungssatz aus, um zu bestimmen, wie Analytics-Variablen XDM-Schemafeldern zugeordnet werden sollen.

   Führen Sie einen der folgenden Schritte aus:

   * Wählen [!UICONTROL **Neuen Zuordnungssatz erstellen**] aus.

   * Einen vorhandenen Zuordnungssatz auswählen.

     Es können Zuordnungssätze ausgewählt werden, die während einer vorherigen Migration oder als eigenständiger Zuordnungssatz erstellt wurden.

     Bei der Wiederverwendung eines Zuordnungssatzes über mehrere Migrationen hinweg werden dieselben Zuordnungen auf jede Migration angewendet.

1. Wählen Sie [!UICONTROL **Migration erstellen**] aus.

1. Fahren Sie mit dem folgenden Abschnitt fort: [&#x200B; und Bereitstellen einer Migration](#validate-and-deploy-a-migration).

## Validieren und Bereitstellen einer Migration

Nachdem Sie eine Migration erstellt haben, öffnen Sie sie, um ihre drei Phasen [!UICONTROL **Audit**], [!UICONTROL **Mapping**] und [!UICONTROL **Implementierung**] abzuschließen.

1. Wählen Sie im Migrationsplaner die Registerkarte [!UICONTROL **Migrationen**] aus.

1. Klicken Sie neben der Migration, die Sie validieren möchten, auf [!UICONTROL **Öffnen**].

   Auf der Seite Migrationsübersicht werden die drei abzuschließenden Phasen zusammen mit einer Zusammenfassung Ihrer Migration und der zugehörigen Artefakte angezeigt.

   <!-- Confirm the exact image: ![The migration overview page with the Audit, Mapping, and Implementation stage cards.](assets/migration-planner-overview.png) -->

1. Schließen Sie die [!UICONTROL **Audit**]-Phase ab:

   1. Wählen Sie auf der Auditkarte ([!UICONTROL **Tag Extension Audit**] oder [!UICONTROL **JavaScript Audit**], je nach Ihrem Migrationstyp) die Option [!UICONTROL **Audit starten**] aus, um die in der Migration enthaltenen Regeln und Datenelemente zu überprüfen.

      <!-- Confirm the exact image: ![The audit page, where you select rules and data elements and resolve any findings.](assets/migration-planner-audit.png) -->

   1. Wählen Sie auf [!UICONTROL **Registerkarten**] und [!UICONTROL **Datenelemente**] die Elemente aus, die in die Migration eingeschlossen werden sollen.

      Regeln mit [!UICONTROL **In Bibliothek**] werden veröffentlicht. Regeln, [!UICONTROL **als „Nur Eigenschaft**] gekennzeichnet sind, sind in der Eigenschaft vorhanden, aber nicht Teil der ausgewählten Bibliothek.

   1. Überprüfen Sie alle Ergebnisse zu den ausgewählten Regeln. Wählen Sie für jedes Ergebnis [!UICONTROL **Überprüfen**], um es zu beheben, oder [!UICONTROL **Ignorieren**], um es nicht anzugehen.

      Wenn beispielsweise zwei Regeln identische Ereignisse und Bedingungen aufweisen, können Sie mit der Suche [!UICONTROL **Regelereignisse duplizieren**] eine Regel beibehalten und die andere entfernen oder [!UICONTROL **Keine Aktion auswählen**] um die Ergebnisse ohne Änderung zu bestätigen.

      Das Beheben von Ergebnissen ist optional, bevor Sie fortfahren. Eine vollständige Liste der Suchtypen und deren Behebung finden Sie unter [Überprüfen und Beheben von Prüfungsergebnissen](#review-and-resolve-audit-findings).

   1. Wählen Sie [!UICONTROL **Speichern und fortfahren**] aus.

1. Schließen Sie die [!UICONTROL **Zuordnung**] ab:

   1. Wählen Sie auf der Karte [!UICONTROL **Analytics → XDM**] Zuordnung“ [!UICONTROL **Neue Zuordnung erstellen**] aus.

   1. Wählen Sie aus, ob ein neues Schema auf der Grundlage Ihrer Analytics-Variablen erstellt oder ein bestehendes Experience Platform-Schema zugeordnet werden soll. Befolgen Sie dann die Anweisungen zur Auswahl Ihrer Report Suite, zur Zuordnung von Feldern und zur Überprüfung des Schemas.

      Ausführliche Anweisungen finden Sie unter [Zuordnen von Analytics-Variablen zu XDM-Feldern](#map-analytics-variables-to-xdm-fields). Informationen zur Wiederverwendung eines Zuordnungssatzes für mehrere Migrationen finden Sie unter [Erstellen und Verwalten von Zuordnungssätzen](#create-and-manage-mapping-sets).

1. Schließen Sie die [!UICONTROL **Implementierung**] ab:

   1. Verwenden Sie auf [!UICONTROL **Karte „Web SDK-Implementierung**] generieren“ die Audit- und Zuordnungsergebnisse, um das Web SDK-Implementierungspaket zu generieren und es dann auf Ihrer Site bereitzustellen.

      Ausführliche Anweisungen finden Sie unter [Generieren und Bereitstellen der Web SDK-Implementierung](#generate-and-deploy-the-web-sdk-implementation).


## Überprüfen und Beheben von Auditergebnissen

Während der [!UICONTROL **Audit**]-Phase kennzeichnet der Migrationsplaner die Ergebnisse der von Ihnen ausgewählten Regeln. Das Beheben von Ergebnissen ist optional, bevor Sie fortfahren, aber es hilft, eine saubere Migration sicherzustellen.

Wählen Sie für jede Suche [!UICONTROL **Überprüfen**] aus, um die Suche zu öffnen und zu beheben, oder wählen Sie [!UICONTROL **Ignorieren**] aus, um sie nicht anzugehen.

Der Migrationsplaner kann die folgenden Arten von Ergebnissen kennzeichnen:

* [!UICONTROL **Duplizieren von Regelereignissen**]: Zwei oder mehr Regeln haben identische Ereignisse und Bedingungen. Wenn Sie die Suche überprüfen, vergleichen Sie die primären und die doppelten Regeln, halten Sie dann eine Regel aufrecht und entfernen Sie die andere oder wählen Sie [!UICONTROL **Nichts tun**], um die Ergebnisse zu bestätigen, ohne eine Änderung vorzunehmen.

* [!UICONTROL **Regellogik duplizieren**]: Regeln verwenden dieselbe Logik. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **Fehlerhafte Regelaktionen**]: Die Aktionen einer Regel werden in einer Reihenfolge ausgeführt, die während der Migration Probleme verursachen kann. <!-- Confirm the exact remediation options for this finding type. -->

Wenn für einen Fund keine geführte Problembehebung vorhanden ist, zeigt der Migrationsplaner [!UICONTROL **Keine Problembehebungsdetails verfügbar**] an. Überprüfen Sie den Fund manuell und schließen Sie ihn ab, wenn er behoben ist.

Das [!UICONTROL **Ergebnisse**] zeigt an, wie viele Ergebnisse Sie angesprochen haben und wie viele noch offen sind. Wenn Sie fertig sind, wählen Sie [!UICONTROL **Speichern und fortfahren**].

## Zuordnen von Analytics-Variablen zu XDM-Feldern

Während des [!UICONTROL **Mapping**]-Schritts ordnen Sie Ihre Analytics-Variablen XDM-Feldern zu und generieren oder wählen Sie das Zielschema aus. Wählen Sie auf der Karte [!UICONTROL **Analytics → XDM**] Zuordnung“ [!UICONTROL **Neue Zuordnung erstellen**] aus und führen Sie dann die folgenden Schritte aus:

1. **Schemaauswahl**: Wählen Sie aus, ob ein neues Schema auf der Grundlage Ihrer Analytics-Variablen erstellt oder einem bestehenden Experience Platform-Schema zugeordnet werden soll.

1. **Report Suite**: Wählen Sie die Analytics-Report Suite aus, deren Variablen Sie zuordnen möchten.

1. **Experience Platform-Schema**: Erstellen Sie das Ziel-XDM-Schema oder wählen Sie das vorhandene Schema aus, dem zugeordnet werden soll.

1. **Manuelles Mapping**: Überprüfen Sie die automatischen Zuordnungen und passen Sie die Zuordnung einzelner Analytics-Variablen zu XDM-Feldern an.

1. **Schema überprüfen**: Überprüfen Sie die resultierenden Zuordnungen und das Schema und bestätigen Sie dann Ihre Auswahl.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

Informationen zur Wiederverwendung eines Zuordnungssatzes für mehrere Migrationen finden Sie unter [Erstellen und Verwalten von Zuordnungssätzen](#create-and-manage-mapping-sets).

## Migrationsergebnisse vergleichen

Verwenden Sie [!UICONTROL **Ausgaben vergleichen**] auf der Seite Migrationsübersicht , um Ihre Migration zu validieren, bevor Sie sie bereitstellen.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Erstellen und Bereitstellen der Web SDK-Implementierung

Während der [!UICONTROL **-**] verwendet der Migrationsplaner Ihre Audit- und Zuordnungsergebnisse, um das Web SDK-Implementierungspaket zu erstellen.

1. Generieren Sie auf der Seite Migrationsübersicht auf der Karte [!UICONTROL **Web SDK-Implementierung generieren**] das Implementierungspaket.

1. Erstellen Sie die Tag-Bibliothek für die Migration, indem Sie [!UICONTROL **Tag-Bibliothek erstellen**] auswählen.

1. Konfigurieren Sie die doppelte Bereitstellung und stellen Sie dann die Web-SDK-Implementierung auf Ihrer Site bereit.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

Die von diesem Schritt erstellten Artefakte finden Sie unter [Exportieren von Migrationsartefakten](#export-migration-artifacts).

## Exportieren von Migrationsartefakten

Die Seite Migrationsübersicht enthält die Artefakte, die der Migrationsplaner generiert. Sie können einzelne Artefakte aus dem Bedienfeld [!UICONTROL **Projektartefakte**] herunterladen oder auf [!UICONTROL **Alle exportieren**] klicken, um alles gleichzeitig zu exportieren.

Die folgenden Artefakte sind verfügbar:

* [!UICONTROL **Mapping JSON**]: Die Zuordnung zwischen Ihren Analytics-Variablen und XDM-Feldern.

* [!UICONTROL **XDM-Schema (JSON)**] Das für die Migration erstellte XDM-Zielschema.

* [!UICONTROL **Tag Development Library**]: Die Tag-Bibliothek, die für die Web-SDK-Implementierung erstellt wurde.

Jedes Artefakt zeigt seinen Status an, z [!UICONTROL **B. &quot;**]&quot; oder [!UICONTROL **Nicht erstellt**]. Ein Artefakt kann heruntergeladen werden, nachdem es im entsprechenden Schritt generiert wurde.

## Erstellen und Verwalten von Zuordnungssätzen {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="Zuordnungssätze"
>abstract="Zuordnungssätze bestimmen, wie Analytics-Variablen XDM-Feldern zugeordnet werden.<br/>Erstellen Sie einen neuen Zuordnungssatz oder wählen Sie einen vorhandenen aus, um dieselben Zuordnungen auf verschiedene Migrationen anzuwenden. Außerdem können Sie in anderen Migrationsaufgaben auf Zuordnungssätze verweisen."

<!-- markdownlint-enable MD034 -->

Zuordnungssätze bestimmen, wie Analytics-Variablen XDM-Schemafeldern zugeordnet werden.

Sie können einen neuen Zuordnungssatz erstellen [während des Migrationsprozesses](#migrate-an-analytics-implementation-to-the-web-sdk). Sie können auch einen eigenständigen Zuordnungssatz erstellen, der mit einer zukünftigen Migration oder mit anderen Migrationsaufgaben verwendet werden kann.

### Erstellen eigenständiger Zuordnungssätze {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="Auswählen eines Schemas"
>abstract="Zuordnungssätze bestimmen, wie Analytics-Variablen XDM-Feldern zugeordnet werden.<br/>Erstellen Sie einen neuen Zuordnungssatz oder wählen Sie einen vorhandenen aus, um dieselben Zuordnungen auf verschiedene Migrationen anzuwenden. Außerdem können Sie in anderen Migrationsaufgaben auf Zuordnungssätze verweisen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="Voreinstellung für Feldergruppen"
>abstract="Wählen Sie Standardfeldgruppen aus, um nach Möglichkeit veröffentlichte Adobe-Feldgruppen zu verwenden. Dies fördert größtmögliche Konsistenz und greift auf benutzerdefinierte Mandantenfelder zurück, wenn keine Standardfelder verfügbar sind.<br/>Wählen Sie benutzerdefinierte Feldergruppen aus, um nach Möglichkeit benutzerdefinierte Felder mit Mandanten-Namespace zu verwenden. Dies fördert ein Höchstmaß an Flexibilität."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="Lookback-Zeitraum"
>abstract="Steuert, wie weit man zurückschaut, wenn man ermittelt, welche Variablen aktiv Daten empfangen. Variablen, die Daten innerhalb des Lookback-Zeitraums enthalten, werden in das Schema aufgenommen."

<!-- markdownlint-enable MD034 -->

1. Wählen Sie im Migrationsplaner die Registerkarte &quot;[!UICONTROL **&quot;**].

1. Wählen Sie [!UICONTROL **Neuer Zuordnungssatz**] aus.

1. Geben [!UICONTROL **im Feld**] einen beschreibenden Namen ein, damit Sie diesen Zuordnungssatz später identifizieren können, und klicken Sie dann auf [!UICONTROL **Weiter**].

1. Wählen Sie im [!UICONTROL **Report Suite**]-Menü die Report Suite aus, deren Variablen Sie XDM-Feldern zuordnen möchten, und klicken Sie dann auf [!UICONTROL **Weiter**].

1. Wählen [!UICONTROL **im Abschnitt „Schema für die XDM-Zuordnung auswählen**] aus, ob ein neues Schema basierend auf Ihren Analytics-Variablen erstellt oder einem bestehenden Experience Platform-Schema zugeordnet werden soll.

   Wenn Sie sich für die Erstellung eines neuen Schemas entscheiden, werden Sie durch den Prozess der Zuordnung Ihrer Analytics-Variablen zu XDM-Feldern geführt. Wenn Sie sich für die Verwendung eines vorhandenen Schemas entscheiden, können Sie Ihre Variablen manuell einem vorregistrierten Schema in der Experience Platform-Schemaregistrierung zuordnen.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **Neues Schema erstellen**]: Führen Sie die einfachen und erweiterten Scans aus, um automatisch XDM-Feldzuordnungen für Ihre Analytics-Variablen vorzuschlagen, und überprüfen Sie dann das resultierende Schema.

   * [!UICONTROL **Vorhandenes Schema verwenden**]: Suchen Sie nach einem Schema, das bereits in der Experience Platform-Schemaregistrierung registriert ist, und wählen Sie es aus. Ziehen Sie dann Analytics-Variablen manuell auf XDM-Felder.

1. Wählen Sie [!UICONTROL **Dropdown-Menü**] Feldergruppenvoreinstellung“ aus, wie Sie benutzerdefinierte Variablen in Feldergruppen organisieren möchten:

   * [!UICONTROL **Standard zuerst**]: Verwenden Sie nach Möglichkeit veröffentlichte Adobe-Feldergruppen. Dies fördert größtmögliche Konsistenz und greift auf benutzerdefinierte Mandantenfelder zurück, wenn keine Standardfelder verfügbar sind.

   * [!UICONTROL **Benutzerdefiniert zuerst**]: Verwenden Sie nach Möglichkeit benutzerdefinierte Felder vom Typ „Mandanten-Namespace“. Dies fördert ein Höchstmaß an Flexibilität.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. Wählen Sie im Feld [!UICONTROL **Lookback**] Zeitraum, wie weit Sie zurückschauen möchten, um zu bestimmen, welche Variablen aktiv Daten empfangen. Variablen, die Daten innerhalb des Lookback-Zeitraums enthalten, werden in das Schema aufgenommen.

1. Wählen [!UICONTROL **Zuordnungssatz erstellen**] aus.

Der neue Zuordnungssatz wird auf der Registerkarte [!UICONTROL **Zuordnungssätze**] angezeigt, wo Sie ihn öffnen können, um seine Details zu überprüfen.

### Exportieren eines Zuordnungssatzes

Sie können einen Zuordnungssatz exportieren, um ihn mit anderen Migrationsaufgaben oder in anderen Tools zu verwenden.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### Veröffentlichungs- und Versionszuordnungssätze

Jeder Zuordnungssatz hat einen Status und eine Version. Auf der Registerkarte [!UICONTROL **Zuordnungssätze**] kann ein Zuordnungssatz wie folgt angezeigt werden:

* [!UICONTROL **Entwurf**]: Der Zuordnungssatz wird noch bearbeitet.

* [!UICONTROL **veröffentlicht**]: Der Zuordnungssatz wurde abgeschlossen.

* [!UICONTROL **in der Migration**]: Der Zuordnungssatz ist an eine oder mehrere Migrationen gebunden.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### Bearbeiten eines Zuordnungssatzes <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### Löschen eines Zuordnungssatzes <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## Verwalten vorhandener Migrationen

### Suchen und Verfolgen von Migrationen

Auf [!UICONTROL **Registerkarte**] Migrationen“ werden Ihre Migrationen und deren Fortschritt aufgelistet. Verwenden Sie sie, um eine Migration zu finden, die fortgesetzt werden soll, oder um den Status der laufenden Migrationen zu überprüfen.

* **Suche**: Verwenden Sie das Suchfeld, um eine Migration anhand des Namens oder der Eigenschaft zu finden.

* **Filtern**: Filtern Sie die Liste nach Migrationstyp oder Status.

* **Fortschritt verfolgen**: Jede Migration zeigt den Fortschritt in den drei Phasen (z. B. 1/3) und einen Gesamtstatus an:

  * [!UICONTROL **Nicht gestartet**]: Die Migration wurde erstellt, aber es ist keine Phase abgeschlossen.

  * [!UICONTROL **In Bearbeitung**]: Mindestens ein Schritt ist abgeschlossen.

  * [!UICONTROL **Abgeschlossen**]: Alle drei Schritte sind abgeschlossen.

Um mit der Migration fortzufahren, wählen [!UICONTROL **neben**] Option „Öffnen“ aus.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

