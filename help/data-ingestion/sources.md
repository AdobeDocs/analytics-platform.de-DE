---
title: Aufnehmen und Verwenden von Daten über Quell-Connectoren
description: Erläuterung der Aufnahme und Verwendung von Daten in Customer Journey Analytics mithilfe von Quell-Connectoren
solution: Customer Journey Analytics
feature: Basics
exl-id: 813d3213-86b3-431a-821c-174e5e36d032
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '2049'
ht-degree: 77%

---

# Aufnehmen und Verwenden von Daten über Quell-Connectoren

In dieser Kurzanleitung wird erläutert, wie Sie Daten in Adobe Experience Platform mithilfe eines Quell-Connectors, der mit einem Datenanbieter verbunden ist, aufnehmen und anschließend in Customer Journey Analytics verwenden können.

Gehen Sie dazu folgendermaßen vor:

- **Richten Sie ein Schema und einen Datensatz** in Adobe Experience Platform ein, um das Modell (Schema) der zu erfassenden Daten zu definieren und um festzulegen, wo die Daten (Datensatz) erfasst werden sollen.

- **Verwenden Sie einen Quell-Connector** in Adobe Experience Platform, um Ihre Daten in den konfigurierten Datensatz zu übertragen.

- **Richten Sie in Customer Journey Analytics eine Verbindung ein**. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Richten Sie in Customer Journey Analytics eine Datenansicht ein**, um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Richten Sie in Customer Journey Analytics ein Projekt ein**, um Berichte und Visualisierungen zu erstellen.



>[!NOTE]
>
>Diese Kurzanleitung ist eine vereinfachte Anleitung zur Aufnahme von Daten in Adobe Experience Platform mithilfe eines Quell-Connectors und deren Verwendung in Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Artikel zu lesen, auf die verwiesen wird.


## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform aufzunehmen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform aufgenommenen Daten müssen einer standardmäßigen, denormalisierten Struktur entsprechen, damit sie von nachgelagerten Funktionen erkannt und genutzt werden können. Das Experience-Datenmodell (XDM) ist das Standard-Framework, das die Struktur in Form von Schemata bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die erfassten Daten zu speichern und zu verwalten. Ein Datensatz ist ein Konstrukt zur Datenspeicherung und -verwaltung (in der Regel eine Tabelle), die ein Schema (Spalten) und Felder (Zeilen) enthält.

Alle in Adobe Experience Platform aufgenommene Daten müssen einem vordefinierten Schema entsprechen, bevor sie als Datensatz gespeichert werden können.

### Einrichten eines Schemas

Im vorliegenden Fall möchten Sie Treuedaten erfassen, z. B. Treueprogramm-ID, Treuepunkte und Treuestatus.
Zunächst müssen Sie ein Schema definieren, das diese Daten modelliert.

Gehen Sie folgendermaßen vor, um das Schema einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemata]** in [!UICONTROL DATEN-MANAGEMENT] aus.

1. Wählen Sie **[!UICONTROL Schema erstellen]** aus.
.
1. Im Schritt Klasse auswählen des Assistenten Schema erstellen :

   1. Wählen Sie **[!UICONTROL Individuelles Profil]** aus.

      ![Erstellen eines Schemafensters mit ausgewähltem individuellem Profil](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ein Erlebnisereignis-Schema wird zum Modellieren des _Verhaltens_ eines Profils verwendet (z. B. Szenenname, Schaltfläche zum Hinzufügen von Artikeln zum Warenkorb). Das Schema „Individuelles Profil“ wird verwendet, um die _Attribute_ eines Profils zu modellieren (z. B. Name, E-Mail, Geschlecht).

   1. Klicken Sie auf **[!UICONTROL Weiter]**.


1. Im [!UICONTROL Schritt „Name und Überprüfung“] des Assistenten [!UICONTROL Schema erstellen]:

   1. Geben Sie einen **[!UICONTROL Schema-Anzeigenamen]** für Ihr Schema und (optional) eine **[!UICONTROL Beschreibung]** ein.

      ![Fenster Schema erstellen mit den Feldern zum Benennen des Schemas ](./assets/create-pr-schema-wizard-step-2.png)

   1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Auf der Registerkarte Struktur des Beispielschemas:

   1. Wählen Sie **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen] aus.

      ![Erstellen eines Schemafensters mit der Feldergruppe hinzufügen](./assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihre Schemata einfach erweitern können.

   1. Wählen Sie im Dialog [!UICONTROL Feldergruppen hinzufügen] die Feldergruppe **[!UICONTROL Treueprogramm-Details]** aus der Liste aus.

      ![Die Feldergruppe „AEP Web SDK ExperienceEvent“](./assets/loyalty-fieldgroup.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören.

      ![Vorschau der Feldergruppe „AEP Web SDK ExperienceEvent“](./assets/loyalty-fieldgroup-preview.png)

      Wählen Sie **[!UICONTROL Zurück]** aus, um die Vorschau zu schließen.

   1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL +]** neben Ihrem Schemanamen im Bedienfeld [!UICONTROL Struktur] aus.

   ![Beispiel für die Schaltfläche zum Hinzufügen eines Feldes zum Schema](./assets/example-loalty-schema-plus.png)

1. Geben Sie im Bedienfeld [!UICONTROL Feldeigenschaften] als Namen `Identification` und als [!UICONTROL Anzeigename]**[!UICONTROL Identifikation]** ein, wählen Sie als [!UICONTROL Typ] **[!UICONTROL Objekt]** und als [!UICONTROL Feldergruppe] **[!UICONTROL Profile Core v2]** aus.

   ![Identifizierungsobjekt](./assets/identifcation-loyalty-field.png)

   Dieses Identifizierungsobjekt fügt Ihrem Schema Identifizierungsfunktionen hinzu. In Ihrem Fall möchten Sie anhand der E-Mail-Adresse in Ihren Batch-Daten Informationen zum Treueprogramm identifizieren.

   Wählen Sie **[!UICONTROL Anwenden]** aus, um dieses Objekt zu Ihrem Schema hinzuzufügen.

1. Wählen Sie das Feld **[!UICONTROL E-Mail]** im soeben hinzugefügten Identifizierungsobjekt aus und danach **[!UICONTROL Identität]** und **[!UICONTROL E-Mail]** in [!UICONTROL Identity-Namespace] im Bedienfeld [!UICONTROL Feldeigenschaften].

   ![Spezifizieren von E-Mail als Identität](./assets/specify-email-loyalty-id.png)

   Sie spezifizieren die E-Mail-Adresse als die Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen zu kombinieren (zusammenzufügen).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im E-Mail-Attribut.

1. Wählen Sie die oberste Ebene Ihres Schemas (trägt den Namen des Schemas) und danach den Umschalter **[!UICONTROL Profil]** aus.

   Sie werden aufgefordert, das Schema für das Profil zu aktivieren. Nach der Aktivierung werden Daten, die auf der Basis dieses Schemas in Datensätze aufgenommen werden, zum Echtzeit-Kundenprofil hinzugefügt.

   Weitere Informationen finden Sie im Abschnitt [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/tutorials/create-schema-ui#profile).

   >[!IMPORTANT]
   >
   >    Nachdem Sie ein für ein Profil aktiviertes Schema gespeichert haben, kann es für das Profil nicht mehr deaktiviert werden.

   ![Aktivieren eines Schemas für ein Profil](./assets/enable-for-profile.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

Sie haben ein Minimalschema erstellt, das die Treueprogramm-Daten modelliert, die in Adobe Experience Platform aufgenommen werden können. Mithilfe des Schemas können Profile anhand der E-Mail-Adresse identifiziert werden. Durch die Aktivierung des Schemas für das Profil stellen Sie sicher, dass von Ihren Streaming-Quellen erfasste Daten zum Echtzeit-Kundenprofil hinzugefügt werden.

Weitere Informationen zum Hinzufügen und Entfernen von Feldergruppen und einzelnen Feldern zu einem Schema finden Sie unter [Erstellen und Bearbeiten von Schemata über die Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=de).

### Erstellen eines Datensatzes

Mit Ihrem Schema haben Sie Ihr Datenmodell definiert. Jetzt müssen Sie das Konstrukt zum Speichern und Verwalten dieser Daten definieren, was über Datensätze erfolgt.

Gehen Sie folgendermaßen vor, um einen Datensatz einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Datensätze]** in [!UICONTROL DATEN-MANAGEMENT].

2. Wählen Sie **[!UICONTROL Erstellen eines Datensatzes]** aus.

   ![Erstellen eines Datensatzes](./assets/create-dataset.png)

3. Wählen Sie **[!UICONTROL Erstellen eines Datensatzes aus einem Schema]** aus.

   ![Erstellen eines Datensatzes aus einem Schema](./assets/create-dataset-from-schema.png)

4. Wählen Sie das zuvor erstellte Schema und danach **[!UICONTROL Weiter]** aus.

5. Benennen Sie Ihren Datensatz und geben Sie (optional) eine Beschreibung ein.

   ![Benennen eines Datensatzes](./assets/name-your-datatest.png)

6. Wählen Sie **[!UICONTROL Beenden]** aus.

7. Wählen Sie den Umschalter **[!UICONTROL Profil]** aus.

   Sie werden aufgefordert, den Datensatz für das Profil zu aktivieren. Nach der Aktivierung reichert der Datensatz das Echtzeit-Kundenprofil mit den aufgenommenen Daten an.

   >[!IMPORTANT]
   >
   >    Sie können einen Datensatz für ein Profil nur aktivieren, wenn das Schema, zu dem der Datensatz gehört, auch für das Profil aktiviert ist.

   ![Aktivieren eines Schemas für ein Profil](./assets/loyalty-dataset-profile.png)

Im [Handbuch zur Datensatz-Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) können Sie nachlesen, wie ein Datensatz angezeigt, in der Vorschau angesehen, erstellt und gelöscht werden kann und wie ein Datensatz für das Echtzeit-Kundenprofil aktiviert wird.


## Verwenden eines Quell-Connectors

Abhängig davon, woher Sie Ihre Treueprogramm-Daten erhalten, wählen Sie einen der in Adobe Experience Platform verfügbaren Quell-Connectoren aus.

Sie können Daten aus einer Vielzahl von Quellen aufnehmen. Im Folgenden sind nur einige der vielen verfügbaren Quellen aufgeführt:

- Adobe-Programme (Quell-Connectoren umfassen [Adobe Analytics](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/analytics), [Adobe Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/audience-manager) und mehr)

- Cloud-Speicher (Quell-Connectoren umfassen [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/cloud-storage/s3), [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/cloud-storage/blob) und mehr)

- Datenbanken (Quell-Connectoren umfassen [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake), [Microsoft SQL Server](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/sql-server) und mehr)

Gehen Sie folgendermaßen vor, um einen Quell-Connector einzurichten:

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Quellen]** aus [!UICONTROL VERBINDUNGEN] in der linken Leiste.

1. Wählen Sie Ihren Quell-Connector aus der Liste der verfügbaren Quell-Connectoren aus.

   Jeder Connector folgt einem ähnlichen Workflow:

   1. **[!UICONTROL Authentifizierung]**. Geben Sie Authentifizierungsinformationen, damit auf die Datenquelle zugegriffen werden kann.

   1. **[!UICONTROL Daten auswählen]**: Sie wählen die Quelldaten aus, die Sie aufnehmen möchten.

   1. **[!UICONTROL Datenflussdetails]**: Sie geben zusätzliche Details zum Datenfluss an, z. B. den Namen und den zu verwendenden Datensatz.

   1. **[!UICONTROL Zuordnung]**: Sie ordnen die eingehenden Quelldatenfelder den Attributen im Schema zu, das mit dem ausgewählten Datensatz verknüpft ist.

   1. **[!UICONTROL Zeitplan]**: Sofern diese Funktion verfügbar ist, können Sie die Datenerfassung zeitlich planen.

   1. **[!UICONTROL Überprüfung]**: Sie können die Definition des Quell-Connectors überprüfen.

1. Jeder Connector bietet eine detaillierte Dokumentation. Gehen Sie folgendermaßen vor, um auf diese Dokumentation zuzugreifen:

   1. Wählen Sie auf der Connector-Kachel die Punkte **[!UICONTROL ...]** neben [!UICONTROL Einrichten] oder [!UICONTROL Daten hinzufügen].

      ![Anzeigen der Dokumentation](./assets/sourceconnector-documentation.png)

   1. Wählen Sie **[!UICONTROL Dokumentation anzeigen]** aus.

Weitere [ zur Verwendung des Adobe Analytics-Quell-Connectors finden Sie ](./analytics.md) „Aufnehmen und Verwenden von Daten aus Adobe Analytics&quot;.

Informationen [ Verwendung des HTTP-API-Quell](./streaming.md)Connectors finden Sie unter „Aufnehmen und Verwenden von Streaming-Daten“.

Einen Überblick über Quell-Connectoren einschließlich Links zu weiteren Informationen zu jedem einzelnen Connector finden Sie unter [Übersicht über Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html#terms-and-conditions).


## Einrichten einer Verbindung

Um die Adobe Experience Platform-Daten in Customer Journey Analytics verwenden zu können, erstellen Sie eine Verbindung, die die Daten enthält, die aus der Einrichtung Ihres Schemas, Datensatzes und Workflows resultieren.

Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Analysis Workspace integrieren. Um über diese Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Adobe Experience Platform und Workspace herstellen.

Gehen Sie folgendermaßen vor, um eine Verbindung zu erstellen:

1. Wählen Sie in der Benutzeroberfläche von Customer Journey Analytics **[!UICONTROL Verbindungen]**, optional unter **[!UICONTROL Datenverwaltung]** im oberen Menü aus.

1. Wählen Sie **[!UICONTROL Neue Verbindung erstellen]** aus.

1. Im Bildschirm **[!UICONTROL Nicht benannte Verbindung]**:

   1. Benennen und beschreiben Sie Ihre Verbindung in den **[!UICONTROL Verbindungseinstellungen]**.

   1. Wählen Sie die entsprechende Sandbox in der Liste **[!UICONTROL Sandbox]** in **[!UICONTROL Dateneinstellungen]** sowie die Anzahl der täglichen Ereignisse in der Liste **[!UICONTROL Durchschnittliche Anzahl der täglichen Ereignisse]** aus.

      ![Verbindungseinstellungen](./assets/cja-connections-1.png)

   1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.

1. Im Schritt **[!UICONTROL Auswählen von Datensätzen]** in **[!UICONTROL Datensätze hinzufügen]**:

   1. Wählen Sie den zuvor erstellten Datensatz aus (`Example Loyalty Dataset`) und etwaige andere Datensätze, die Sie in Ihre Verbindung einschließen möchten.

      ![Hinzufügen von Datensätzen](./assets/cja-connections-2.png)

   1. Wählen Sie **[!UICONTROL Weiter]** aus.

1. Im Schritt **[!UICONTROL Datensatzeinstellungen]** in **[!UICONTROL Datensätze hinzufügen]**:

   Für jeden Datensatz:

   1. Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind.

   1. Wählen Sie die richtige Datenquelle in der Liste [!UICONTROL Datenquellentyp] aus. Wenn Sie **[!UICONTROL Sonstige]** angeben, fügen Sie eine Beschreibung für Ihre Datenquelle hinzu.

   1. Definieren Sie **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Datensatz-Aufstockung vorhandener Daten]** entsprechend Ihren Anforderungen.

      ![Konfigurieren von Datensätzen](./assets/cja-connections-3.png)

   1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.

   1. Wählen Sie **[!UICONTROL Speichern]** aus.

Nachdem Sie eine [Verbindung](/help/connections/overview.md) erstellt haben, können Sie verschiedene Verwaltungsaufgaben ausführen, z. B. [Auswählen und Kombinieren von ](/help/connections/combined-dataset.md), [Überprüfen des Status der Datensätze einer Verbindung und des Status der Datenaufnahme](/help/connections/manage-connections.md) und mehr.

## Einrichten einer Datenansicht

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie die aus einer Verbindung stammenden Daten interpretiert werden sollen. Darin werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

Gehen Sie folgendermaßen vor, um eine Datenansicht zu erstellen:

1. Wählen Sie in der Customer Journey Analytics **[!UICONTROL Benutzeroberfläche im oberen Menü]** Datenansichten **[!UICONTROL optional unter Datenverwaltung]** aus.

2. Wählen Sie **[!UICONTROL Neue Datenansicht erstellen]**.

3. Im Schritt [!UICONTROL Konfigurieren]:

   Wählen Sie Ihre Verbindung in der Liste [!UICONTROL Verbindung].

   Geben Sie einen Namen und (optional) eine Beschreibung für Ihre Verbindung ein.

   ![Konfiguration der Datenansicht](./assets/cja-dataview-1.png)

   Wählen Sie **[!UICONTROL Speichern und fortfahren]** aus.

4. Im Schritt [!UICONTROL Komponenten]:

   Fügen Sie alle Schemafelder und/oder Standardkomponenten hinzu, die Sie in die Komponentenfelder [!UICONTROL METRIKEN] oder [!UICONTROL DIMENSIONEN] einbeziehen möchten.

   ![Datenansichtskomponenten](./assets/cja-dataview-2.png)

   Wählen Sie **[!UICONTROL Speichern und fortfahren]** aus.

5. Im Schritt [!UICONTROL Einstellungen]:

   ![Datenansichtseinstellungen](./assets/cja-dataview-3.png)

   Behalten Sie die Einstellungen bei und wählen Sie **[!UICONTROL Speichern und beenden]**.

Weitere [ dazu, wie Sie eine Datenansicht erstellen und bearbeiten, welche Komponenten in Ihrer Datenansicht verfügbar sind und wie Sie Segment](../data-views/data-views.md) und Sitzungseinstellungen verwenden, finden Sie unter Datenansichten - Übersicht .


## Einrichten eines Projekts

Analysis Workspace ist ein flexibles Browsertool, mit dem Sie schnell Analysen erstellen und Erkenntnisse anderen Team-Mitgliedern zur Verfügung stellen können. Mit Analysis Workspace-Projekten können Sie Datenkomponenten, Tabellen und Visualisierungen kombinieren, um eine Analyse zu erstellen, und diese für andere Personen in Ihrem Unternehmen freigeben.

Gehen Sie folgendermaßen vor, um ein Projekt zu erstellen:

1. Wählen Sie in der Benutzeroberfläche von Customer Journey Analytics **[!UICONTROL Projekte]** im oberen Menü aus.

2. Wählen Sie **[!UICONTROL Projekte]** in der linken Navigation aus.

3. Wählen Sie **[!UICONTROL Projekt erstellen]** aus

   ![Analysis Workspace-Projekt](./assets/cja-projects-1.png)

   Wählen Sie **[!UICONTROL Leeres Projekt]** aus.

   ![Analysis Workspace – Leeres Projekt](./assets/cja-projects-2.png)

4. Wählen Sie Ihre Datenansicht aus der Liste aus.

   ![Workspace – Datenansicht auswählen](./assets/cja-projects-3.png).

5. Um Ihren ersten Bericht zu erstellen, ziehen Sie per Drag-and-Drop Dimensionen und Metriken auf die [!UICONTROL Freiformtabelle] im [!UICONTROL Panel] . Ziehen Sie beispielsweise `Program Points Balance` und `Page View` als Metriken sowie `email` als Dimension auf die Tabelle, um einen kurzen Überblick über die Profile zu erhalten, die Ihre Website besucht haben und Mitglieder des Treueprogramms sind, mit dem Treuepunkte gesammelt werden.

   ![Analysis Workspace – erster Bericht](./assets/cja-projects-5.png)

Weitere Informationen zum Erstellen von Projekten und zum Durchführen einer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern finden Sie unter [Analysis Workspace – Überblick](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Sie haben jetzt alle Schritte ausgeführt. Sie haben zunächst definiert, welche Treueprogramm-Daten erfasst werden sollen (Schema) und wo sie in Adobe Experience Platform gespeichert werden sollen (Datensatz). Dann haben Sie den entsprechenden Quell-Connector konfiguriert, über den die Treueprogramm-Daten übertragen werden. Sie haben eine Verbindung in Customer Journey Analytics definiert, um die aufgenommenen Treueprogramm-Daten und andere Daten zu verwenden. Durch die Definition Ihrer Datenansicht konnten Sie festlegen, welche Dimension und Metriken verwendet werden sollen. Abschließend haben Sie Ihr erstes Projekt erstellt, in dem Ihre Daten visualisiert und analysiert wurden.
