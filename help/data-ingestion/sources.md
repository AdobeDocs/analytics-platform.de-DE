---
title: Aufnehmen und Verwenden von Daten über Quell-Connectoren
description: Erläuterung der Aufnahme und Verwendung von Daten in Customer Journey Analytics mithilfe von Quell-Connectoren
solution: Customer Journey Analytics
feature: Basics
exl-id: 813d3213-86b3-431a-821c-174e5e36d032
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1967'
ht-degree: 86%

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
>Diese Kurzanleitung ist eine vereinfachte Anleitung zur Aufnahme von Daten mithilfe eines Quell-Connectors in Adobe Experience Platform und zur Verwendung dieser Daten in Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Artikel zu lesen, auf die verwiesen wird.


## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform zu erfassen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform aufgenommenen Daten müssen einer standardmäßigen, denormalisierten Struktur entsprechen, damit sie von nachgelagerten Funktionen erkannt und genutzt werden können. Experience-Datenmodell (XDM) ist das Standard-Framework, das die Struktur in Form von Schemas bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die erfassten Daten zu speichern und zu verwalten. Ein Datensatz ist ein Speicher- und Verwaltungskonstrukt für eine Datenerfassung (normalerweise eine Tabelle), die ein Schema (Spalten) und Felder (Zeilen) enthält.

Alle in Adobe Experience Platform aufgenommene Daten müssen einem vordefinierten Schema entsprechen, bevor sie als Datensatz gespeichert werden können.

### Einrichten eines Schemas

Im vorliegenden Fall möchten Sie Treuedaten erfassen, z. B. Treueprogramm-ID, Treuepunkte und Treuestatus.
Zunächst müssen Sie ein Schema definieren, das diese Daten modelliert.

Gehen Sie folgendermaßen vor, um das Schema einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemata]** in [!UICONTROL DATEN-MANAGEMENT] aus.

1. Auswählen **[!UICONTROL Schema erstellen]**. .
1. Im Schritt Klasse auswählen des Assistenten Schema erstellen :

   1. Auswählen **[!UICONTROL Individuelles Profil]**.

      ![Erstellen eines Schemafensters mit ausgewähltem individuellen Profil](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ein Erlebnisereignis-Schema wird zum Modellieren der _Verhalten_ eines Profils (wie Name der Szene, Schaltfläche zum Hinzufügen zum Warenkorb). Das Schema „Individuelles Profil“ wird verwendet, um die _Attribute_ eines Profils zu modellieren (z. B. Name, E-Mail, Geschlecht).

   1. Klicken Sie auf **[!UICONTROL Weiter]**.


1. Im [!UICONTROL Name und Überprüfungsschritt] des [!UICONTROL Schema erstellen] Assistent:

   1. Geben Sie einen **[!UICONTROL Anzeigename des Schemas]** für Ihr Schema und (optional) a **[!UICONTROL Beschreibung]**.

      ![Schema-Fenster erstellen mit Feldern zum Benennen Ihres Schemas ](./assets/create-pr-schema-wizard-step-2.png)

   1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Auf der Registerkarte Struktur des Beispielschemas:

   1. Wählen Sie **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen] aus.

      ![Schema-Fenster mit der Feldergruppe hinzufügen erstellen](./assets/add-field-group-button.png)

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

   Weitere Informationen finden Sie im Abschnitt [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de#profile).

   >[!IMPORTANT]
   >
   >    Nachdem Sie ein für ein Profil aktiviertes Schema gespeichert haben, kann es für das Profil nicht mehr deaktiviert werden.

   ![Aktivieren eines Schemas für ein Profil](./assets/enable-for-profile.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

Sie haben ein Minimalschema erstellt, das die Treueprogramm-Daten modelliert, die in Adobe Experience Platform aufgenommen werden können. Mithilfe des Schemas können Profile anhand der E-Mail-Adresse identifiziert werden. Durch die Aktivierung des Schemas für das Profil stellen Sie sicher, dass von Ihren Streaming-Quellen erfasste Daten zum Echtzeit-Kundenprofil hinzugefügt werden.

Weitere Informationen zum Hinzufügen und Entfernen von Feldergruppen und einzelnen Feldern zu einem Schema finden Sie unter [Erstellen und Bearbeiten von Schemata über die Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=de).

### Erstellen eines Datensatzes

Mit Ihrem Schema haben Sie Ihr Datenmodell definiert. Jetzt müssen Sie das Konstrukt definieren, um diese Daten zu speichern und zu verwalten, was über Datensätze erfolgt.

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

Gehen Sie folgendermaßen vor, um einen Quell-Connector einzurichten:

1. Wählen Sie in der Benutzeroberfläche von Experience Platform in der linken Leiste **[!UICONTROL Quellen]** unter [!UICONTROL VERBINDUNGEN].

2. Wählen Sie einen Quell-Connector aus der Liste der verfügbaren Quell-Connectoren aus. Jeder Connector folgt einem ähnlichen Workflow:

   - **[!UICONTROL Authentifizierung]**. Geben Sie Authentifizierungsinformationen, damit auf die Datenquelle zugegriffen werden kann.

   - **[!UICONTROL Daten auswählen]**: Sie wählen die Quelldaten aus, die Sie aufnehmen möchten.

   - **[!UICONTROL Datenflussdetails]**: Sie geben zusätzliche Details zum Datenfluss an, z. B. den Namen und den zu verwendenden Datensatz.

   - **[!UICONTROL Zuordnung]**: Sie ordnen die eingehenden Quelldatenfelder den Attributen im Schema zu, das mit dem ausgewählten Datensatz verknüpft ist.

   - **[!UICONTROL Zeitplan]**: Sofern diese Funktion verfügbar ist, können Sie die Datenerfassung zeitlich planen.

   - **[!UICONTROL Überprüfung]**: Sie können die Definition des Quell-Connectors überprüfen.

   Jeder Connector bietet eine detaillierte Dokumentation.

   Gehen Sie folgendermaßen vor, um auf diese Dokumentation zuzugreifen:

   - Wählen Sie auf der Connector-Kachel die Punkte **[!UICONTROL ...]** neben [!UICONTROL Einrichten] oder [!UICONTROL Daten hinzufügen].

     ![Anzeigen der Dokumentation](./assets/sourceconnector-documentation.png)

   - Wählen Sie **[!UICONTROL Dokumentation anzeigen]** aus.

Weitere Informationen zur Verwendung des Adobe Analytics-Quell-Connectors finden Sie unter [Aufnahme und Verwendung der Daten im herkömmlichen Adobe Analytics](./analytics.md).

Weitere Informationen zur Verwendung des HTTP-API-Quell-Connectors finden Sie unter [Aufnehmen und Verwenden von Streaming-Daten](./streaming.md).

Einen Überblick über Quell-Connectoren einschließlich Links zu weiteren Informationen zu jedem einzelnen Connector finden Sie unter [Übersicht über Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=de#terms-and-conditions).


## Einrichten einer Verbindung

Um die Adobe Experience Platform-Daten in Customer Journey Analytics verwenden zu können, erstellen Sie eine Verbindung, die die Daten enthält, die aus der Einrichtung Ihres Schemas, Datensatzes und Workflows resultieren.

Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Analysis Workspace integrieren. Um über diese Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Adobe Experience Platform und Workspace herstellen.

Gehen Sie folgendermaßen vor, um eine Verbindung zu erstellen:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Verbindungen]** in der oberen Navigation aus.

2. Wählen Sie **[!UICONTROL Neue Verbindung erstellen]** aus.

3. Im Bildschirm [!UICONTROL Nicht benannte Verbindung]:

   Benennen und beschreiben Sie Ihre Verbindung in den [!UICONTROL Verbindungseinstellungen].

   Wählen Sie die entsprechende Sandbox in der Liste [!UICONTROL Sandbox] in [!UICONTROL Dateneinstellungen] sowie die Anzahl der täglichen Ereignisse in der Liste [!UICONTROL Durchschnittliche Anzahl der täglichen Ereignisse] aus.

   ![Verbindungseinstellungen](./assets/cja-connections-1.png)

   Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.

   Im Schritt [!UICONTROL Auswählen von Datensätzen] in [!UICONTROL Datensätze hinzufügen]:

   - Wählen Sie den zuvor erstellten Datensatz aus (`Example Loyalty Dataset`) und etwaige andere Datensätze, die Sie in Ihre Verbindung einschließen möchten.

     ![Hinzufügen von Datensätzen](./assets/cja-connections-2.png)

   - Wählen Sie **[!UICONTROL Weiter]** aus.

   Im Schritt [!UICONTROL Datensatzeinstellungen] in [!UICONTROL Datensätze hinzufügen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle in der Liste [!UICONTROL Datenquellentyp] aus. Wenn Sie **[!UICONTROL Sonstige]** angeben, fügen Sie eine Beschreibung für Ihre Datenquelle hinzu.

      - Definieren Sie **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Datensatz-Aufstockung vorhandener Daten]** entsprechend Ihren Anforderungen.

     ![Konfigurieren von Datensätzen](./assets/cja-connections-3.png)

   - Wählen Sie **[!UICONTROL Datensätze hinzufügen]** aus.

   Wählen Sie **[!UICONTROL Speichern]** aus.

Weitere Informationen zum Erstellen und Verwalten einer Verbindung und zum Auswählen und Kombinieren von Datensätzen finden Sie unter [Verbindungen – Überblick](../connections/overview.md).

## Einrichten einer Datenansicht

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie die aus einer Verbindung stammenden Daten interpretiert werden sollen. Darin werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

Gehen Sie folgendermaßen vor, um eine Datenansicht zu erstellen:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Datenansichten]** in der oberen Navigationsleiste.

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

Weitere Informationen dazu, wie Sie eine Datenansicht erstellen und bearbeiten, welche Komponenten in Ihrer Datenansicht verfügbar sind und wie Filter- und Sitzungseinstellungen verwendet werden, finden Sie in [Datenansichten – Überblick](../data-views/data-views.md).


## Einrichten eines Projekts

Analysis Workspace ist ein flexibles Browsertool, mit dem Sie schnell Analysen erstellen und Erkenntnisse anderen Team-Mitgliedern zur Verfügung stellen können. Mit Analysis Workspace-Projekten können Sie Datenkomponenten, Tabellen und Visualisierungen kombinieren, um eine Analyse zu erstellen, und diese für andere Personen in Ihrem Unternehmen freigeben.

Gehen Sie folgendermaßen vor, um ein Projekt zu erstellen:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Projekte]** in der oberen Navigationsleiste.

2. Wählen Sie **[!UICONTROL Projekte]** in der linken Navigation aus.

3. Wählen Sie **[!UICONTROL Projekt erstellen]** aus

   ![Analysis Workspace-Projekt](./assets/cja-projects-1.png)

   Wählen Sie **[!UICONTROL Leeres Projekt]** aus.

   ![Analysis Workspace – Leeres Projekt](./assets/cja-projects-2.png)

4. Wählen Sie Ihre Datenansicht aus der Liste aus.

   ![Workspace – Datenansicht auswählen](./assets/cja-projects-3.png).

5. Um Ihren ersten Bericht zu erstellen, ziehen Sie Dimensionen und Metriken per Drag-and-Drop in die [!UICONTROL Freiformtabelle] im [!UICONTROL Bedienfeld] . Ziehen Sie beispielsweise `Program Points Balance` und `Page View` als Metriken sowie `email` als Dimension auf die Tabelle, um einen kurzen Überblick über die Profile zu erhalten, die Ihre Website besucht haben und Mitglieder des Treueprogramms sind, mit dem Treuepunkte gesammelt werden.

   ![Analysis Workspace – erster Bericht](./assets/cja-projects-5.png)

Weitere Informationen zum Erstellen von Projekten und zum Durchführen einer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern finden Sie unter [Analysis Workspace – Überblick](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Sie haben jetzt alle Schritte ausgeführt. Sie haben zunächst definiert, welche Treueprogramm-Daten erfasst werden sollen (Schema) und wo sie in Adobe Experience Platform gespeichert werden sollen (Datensatz). Dann haben Sie den entsprechenden Quell-Connector konfiguriert, über den die Treueprogramm-Daten übertragen werden. Sie haben eine Verbindung in Customer Journey Analytics definiert, um die aufgenommenen Treueprogramm-Daten und andere Daten zu verwenden. Durch die Definition Ihrer Datenansicht konnten Sie festlegen, welche Dimension und Metriken verwendet werden sollen. Abschließend haben Sie Ihr erstes Projekt erstellt, in dem Ihre Daten visualisiert und analysiert wurden.
