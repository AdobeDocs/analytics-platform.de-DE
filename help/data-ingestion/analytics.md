---
title: Aufnehmen und Verwenden von Daten aus Adobe Analytics
description: Erläuterung der Datenaufnahme aus Adobe Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 81%

---

# Aufnehmen und Verwenden von Daten aus Adobe Analytics

In dieser Kurzanleitung wird erläutert, wie Sie die von Adobe Analytics erfassten Daten in Customer Journey Analytics verwenden können.

>[!PREREQUISITES]
>
>Sie besitzen eine Lizenz für Adobe Analytics auf einer oder mehreren Ihrer Websites und Adobe Analytics ist dort mithilfe einer der dokumentierten Methoden bereitgestellt:
>
>- [Implementierung von Analytics mithilfe Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html)
>
>- [Implementierung von Analytics mithilfe der Adobe Analytics-Erweiterung](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=de)
>
>- [Implementierung von Analytics mithilfe von JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=de)

Gehen Sie dazu folgendermaßen vor:

- **Richten Sie in Adobe Experience Platform einen Adobe Analytics-Quell-Connector ein**. Der Quell-Connector übernimmt die Aufnahme Ihrer aktuellen Adobe Analytics-Daten in einen Datensatz in Adobe Experience Platform.

- **Richten Sie in Customer Journey Analytics eine Verbindung ein**. Die Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Richten Sie in Customer Journey Analytics eine Datenansicht ein**, um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Richten Sie in Customer Journey Analytics ein Projekt ein**, um Berichte und Visualisierungen zu erstellen.


>[!NOTE]
>
>Dieses Schnellstarthandbuch ist eine vereinfachte Anleitung zur Erfassung von Daten mithilfe des Adobe Analytics-Quell-Connectors und zur Verwendung dieser Daten im Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Artikel zu lesen, auf die verwiesen wird.


## Einrichten eines Adobe Analytics-Quell-Connectors

Mit dem Adobe Analytics-Quell-Connector können Sie Daten von Adobe Analytics-Report-Suites in Adobe Experience Platform importieren.

Gehen Sie folgendermaßen vor, um einen Adobe Analytics-Quell-Connector zu erstellen:

1. Wählen Sie in der Platform-Benutzeroberfläche die Option **[!UICONTROL Quellen]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Adobe-Anwendungen]** aus der Liste der [!UICONTROL KATEGORIEN] aus.

3. Wählen Sie in der Adobe Analytics-Kachel **[!UICONTROL Einrichten]** oder **[!UICONTROL Daten hinzufügen]** aus.

   ![Adobe Experience Platform-Fenster mit ausgewählten Quellen zusammen mit Adobe-Anwendungen und hervorgehobenen Daten hinzufügen](./assets/sources-overview.png).

4. Wählen Sie **[!UICONTROL Report Suite]** aus. Wählen Sie in der Liste der Report Suites die gewünschte Report Suite aus.

   ![Adobe Experience Platform-Fenster mit der Report Suites-Liste](./assets/report-suites.png)

   Klicken Sie auf **[!UICONTROL Weiter]**.

5. Wählen Sie **[!UICONTROL Standardschema]** als [!UICONTROL Zielschema] aus. Adobe Experience Platform erstellt automatisch das Schema und den entsprechenden Datensatz, um alle Standardfelder aus der ausgewählten Adobe Analytics-Report-Suite zuzuordnen.

   ![Adobe Experience Platform-Fenster mit ausgewähltem Standardschema](./assets/default-schema.png)

   Wählen Sie **[!UICONTROL Weiter]** aus.

6. Benennen Sie den Datenfluss und geben Sie (optional) eine Beschreibung ein.

   ![Adobe Experience Platform-Fenster, das den Detailabschnitt des Datenflusses hervorhebt](./assets/dataflow-detail.png)

   Wählen Sie **[!UICONTROL Weiter]** aus.

7. Überprüfen Sie die Verbindung und wählen Sie **[!UICONTROL Beenden]**.

   ![Adobe Experience Platform-Fenster, das die Abschnitte Verbinden und Datentyp zur Überprüfung hervorhebt](./assets/review.png)


Nachdem die Verbindung erstellt wurde, wird der Datenfluss automatisch erstellt, um einen Datensatz mit den Adobe Analytics-Daten aus Ihrer Report Suite zu füllen. Der Datenfluss erfasst bis zu 13 Monate historischer Daten für Produktions-Sandboxes. Die Aufstockung in Nicht-Produktions-Sandboxes ist auf drei Monate beschränkt.

Wenn die erste Aufnahme abgeschlossen ist, können Ihre Adobe Analytics-Report-Suite-Daten von Customer Journey Analytics verwendet werden.

Ein umfassendes Tutorial finden Sie unter [Erstellen eines Adobe Analytics-Quell-Connectors in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de).


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

   - Wählen Sie den automatisch vom Adobe Analytics-Quell-Connector erstellten Datensatz sowie alle anderen Datensätze aus, die in Ihre Verbindung eingeschlossen werden sollen.

     ![Datensatzfenster hinzufügen](./assets/cja-connections-2a.png)

   - Wählen Sie **[!UICONTROL Weiter]** aus.

   Im Schritt [!UICONTROL Datensatzeinstellungen] in [!UICONTROL Datensätze hinzufügen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle in der Liste [!UICONTROL Datenquellentyp] aus. Wenn Sie **[!UICONTROL Sonstige]** angeben, fügen Sie eine Beschreibung für Ihre Datenquelle hinzu.

      - Definieren Sie **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Datensatz-Aufstockung vorhandener Daten]** entsprechend Ihren Anforderungen.

     ![Konfigurieren von Datensätzen](./assets/cja-connections-3a.png)

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
>Sie haben jetzt alle Schritte ausgeführt. Nach der Einrichtung des Adobe Analytics-Datenquellen-Connectors und der Konfiguration dieses Connectors für Ihre Report Suite werden Ihre Adobe Analytics-Daten automatisch in Adobe Experience Platform hochgeladen. Sie haben eine Verbindung im Customer Journey Analytics definiert, um die erfassten Adobe Analytics-Daten und andere Daten zu verwenden. Durch die Definition Ihrer Datenansicht konnten Sie festlegen, welche Dimension und Metriken verwendet werden sollen. Abschließend haben Sie Ihr erstes Projekt erstellt, in dem Ihre Daten visualisiert und analysiert wurden.

