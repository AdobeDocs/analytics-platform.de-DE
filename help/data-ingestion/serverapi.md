---
title: Daten über die Adobe Experience Platform Edge Network Server-API erfassen
description: Erfahren Sie, wie Sie Daten über die Adobe Experience Platform Edge Network Server-API und das Edge Network in Customer Journey Analytics aufnehmen.
solution: Customer Journey Analytics
feature: Basics
exl-id: 6bfb7254-5bb7-45c6-86a2-0651a0d222fa
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 59%

---

# Daten über die Adobe Experience Platform Edge Network Server-API erfassen

In dieser Kurzanleitung wird erläutert, wie Sie Tracking-Daten von Geräten wie IoT-Geräten, Set-Top-Boxen, Spielekonsolen und Desktop-Anwendungen direkt über die Adobe Experience Platform Edge Network Server API und das Edge Network in Adobe Experience Platform erfassen können. Verwenden Sie dann diese Daten im Customer Journey Analytics.

Dazu müssen Sie:

- **Richten Sie ein Schema und einen Datensatz** in Adobe Experience Platform ein, um das Modell (Schema) der zu erfassenden Daten zu definieren und um festzulegen, wo die Daten (Datensatz) erfasst werden sollen.

- **Richten Sie einen Datenstrom ein**, um das Adobe Experience Platform Edge Network so zu konfigurieren, dass Ihre erfassten Daten an den in Adobe Experience Platform konfigurierten Datensatz weitergeleitet werden.

- **Verwenden der Server-API** , um Daten direkt von Ihrer Anwendung oder Ihrem Spiel zu senden, das auf einem Desktop, einer Spielekonsole, einem IoT-Gerät oder einer Set-Top-Box ausgeführt wird.

- **Stellen Sie die Daten bereit und validieren Sie sie**. Sie verfügen über eine Umgebung, in der Sie Ihre Entwicklung iterieren können. Sobald alles validiert wurde, veröffentlichen Sie es live in Ihrer Produktionsumgebung.

- **Richten Sie in Customer Journey Analytics eine Verbindung ein**. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Richten Sie in Customer Journey Analytics eine Datenansicht ein**, um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Richten Sie in Customer Journey Analytics ein Projekt ein**, um Berichte und Visualisierungen zu erstellen.

>[!NOTE]
>
>Diese Schnellstartanleitung ist eine vereinfachte Anleitung zur Erfassung von Daten, die von einer Anwendung oder einem Spiel erfasst wurden, die auf einem IoT-Gerät, einer Set-Top-Box, einer Spielkonsole oder einem Desktop ausgeführt wird, in Adobe Experience Platform und zur Verwendung in Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Artikel zu lesen, auf die verwiesen wird.


## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform zu erfassen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform aufgenommenen Daten müssen einer standardmäßigen, denormalisierten Struktur entsprechen, damit sie von nachgelagerten Funktionen erkannt und genutzt werden können. Experience-Datenmodell (XDM) ist das Standard-Framework, das eine Struktur in Form von Schemas bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die erfassten Daten zu speichern und zu verwalten. Ein Datensatz ist ein Speicher- und Verwaltungskonstrukt für eine Datenerfassung (normalerweise eine Tabelle), die ein Schema (Spalten) und Felder (Zeilen) enthält.

Alle in Adobe Experience Platform aufgenommene Daten müssen einem vordefinierten Schema entsprechen, bevor sie als Datensatz gespeichert werden können.

### Einrichten eines Schemas

Sie möchten einige minimale Daten aus Profilen verfolgen, die Ihr Spiel auf einer Konsole spielen, z. B. Identifikation, Bewertungen, Fortschritt und andere Informationen.
Zunächst müssen Sie ein Schema definieren, das diese Daten modelliert.

Gehen Sie folgendermaßen vor, um das Schema einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemata]** in [!UICONTROL DATEN-MANAGEMENT] aus.

1. Auswählen **[!UICONTROL Schema erstellen]**. .
1. Im Schritt Klasse auswählen des Assistenten Schema erstellen :

   1. Auswählen **[!UICONTROL Erlebnisereignis]**.

      ![Erstellen eines Schemas](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ein Erlebnisereignis-Schema wird zum Modellieren der _Verhalten_ eines Profils (wie Name der Szene, Schaltfläche zum Hinzufügen zum Warenkorb). Das Schema „Individuelles Profil“ wird verwendet, um die _Attribute_ eines Profils zu modellieren (z. B. Name, E-Mail, Geschlecht).

   1. Klicken Sie auf **[!UICONTROL Weiter]**.


1. Im [!UICONTROL Name und Überprüfungsschritt] des [!UICONTROL Schema erstellen] Assistent:

   1. Geben Sie einen **[!UICONTROL Anzeigename des Schemas]** für Ihr Schema und (optional) a **[!UICONTROL Beschreibung]**.

      ![Benennen des Schemas](./assets/create-ee-schema-wizard-step-2.png)

   1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Auf der Registerkarte Struktur des Beispielschemas:

   1. Wählen Sie **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen] aus.

      ![Hinzufügen der Feldergruppe](./assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   1. Im [!UICONTROL Feldergruppen hinzufügen] wählen Sie das **[!UICONTROL Blende Licht]** Feldergruppe aus der Liste. Diese Feldgruppe wird erstellt, um den Benutzerfortschritt beim Spielen eines fiktiven Spiels mit dem Titel Blinding Light auf einer Konsole zu verfolgen.

      ![Feldgruppe &quot;Blinding Light&quot;](assets/schema-fieldgroup-blindinglight.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören, z. B. `scores > afterMatch`.

      ![Vorschau der hellen Feldgruppe anzeigen](assets/schema-fieldgroup-blindinglight-preview.png)

      Wählen Sie **[!UICONTROL Zurück]** aus, um die Vorschau zu schließen.

   1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Auswählen **[!UICONTROL +]** neben Ihrem Schemanamen.

   ![Beispiel für die Schaltfläche zum Hinzufügen eines Feldes zum Schema](./assets/example-gamingschema-plus.png)

1. Im [!UICONTROL Feldeigenschaften] Bereich, eingeben `identification` als [!UICONTROL Feldname], **[!UICONTROL Bezeichnung]** als [!UICONTROL Anzeigename]auswählen **[!UICONTROL Objekt]** als [!UICONTROL Typ] und wählen **[!UICONTROL ExperienceEvent Core v2.1]** als [!UICONTROL Feldergruppe].

   >[!NOTE]
   >
   >Wenn diese Feldergruppe nicht verfügbar ist, suchen Sie nach einer anderen Feldergruppe, die Identitätsfelder enthält. Oder [eine neue Feldergruppe erstellen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) und [Hinzufügen neuer Identitätsfelder](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (like `ecid`, `crmId`und andere erforderliche Elemente) zur Feldergruppe hinzu und wählen Sie diese neue Feldergruppe aus.

   ![Identifizierungsobjekt](./assets/identification-field-gaming.png)

   Das Identifizierungsobjekt fügt Ihrem Schema Identifizierungsfunktionen hinzu. In Ihrem Fall möchten Sie Profile, die Ihr Spiel spielen, mithilfe der Experience Cloud-ID und der E-Mail-Adresse identifizieren, die sie für die Anmeldung bei der Spielkonsole verwenden. Es gibt viele weitere Attribute, mit denen Sie die Identifizierung Ihrer Person verfolgen können.

   Wählen Sie **[!UICONTROL Anwenden]** aus, um dieses Objekt zu Ihrem Schema hinzuzufügen.

1. Wählen Sie im soeben hinzugefügten Identifizierungsobjekt das Feld **[!UICONTROL ECID]** aus und danach im rechten Bedienfeld **[!UICONTROL Identität]** und **[!UICONTROL Primäre Identität]** sowie die Option **[!UICONTROL ECID]** in der Liste [!UICONTROL Identity-Namespace].

   ![Spezifizieren Sie die ECID als Identität](./assets/specify-identity-gaming.png)

   Sie spezifizieren die Experience Cloud-Identität als primäre Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen, die dieselbe ECID haben, zu kombinieren (Stitching).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im ECID-Attribut.

1. Wählen Sie das Feld **[!UICONTROL E-Mail]** im soeben hinzugefügten Identifizierungsobjekt aus und danach **[!UICONTROL Identität]** und **[!UICONTROL E-Mail]** in der Liste [!UICONTROL Identity-Namespace] im Bedienfeld [!UICONTROL Feldeigenschaften].

   ![Spezifizieren von E-Mail als Identität](./assets/specify-email-identity-gaming.png)

   Sie spezifizieren die E-Mail-Adresse als weitere Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen zu kombinieren (Stitching).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im E-Mail-Attribut.

   Wählen Sie **[!UICONTROL Speichern]** aus.

1. Wählen Sie das Stammelement Ihres Schemas aus, das den Namen des Schemas trägt, und wählen Sie dann den Umschalter **[!UICONTROL Profil]** aus.

   Sie werden aufgefordert, das Schema für das Profil zu aktivieren. Nach der Aktivierung werden Daten, die auf der Basis dieses Schemas in Datensätze aufgenommen werden, zum Echtzeit-Kundenprofil hinzugefügt.

   Weitere Informationen finden Sie im Abschnitt [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile).

   >[!IMPORTANT]
   >
   >    Nachdem Sie ein für ein Profil aktiviertes Schema gespeichert haben, kann es für das Profil nicht mehr deaktiviert werden.

   ![Aktivieren eines Schemas für ein Profil](./assets/enable-for-profile.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus, um Ihr Schema zu speichern.

Sie haben ein Minimalschema erstellt, das die Daten, die Sie aus Ihrem Spiel erfassen können, modelliert. Mithilfe des Schemas können Profile anhand der Experience Cloud-Identität und -E-Mail-Adresse identifiziert werden. Durch Aktivierung des Schemas für das Profil stellen Sie sicher, dass aus Ihrem Konsolenspiel erfasste Daten dem Echtzeit-Kundenprofil hinzugefügt werden.

Neben den Verhaltensdaten können Sie auch Profilattributdaten aus Ihrer Konsole erfassen (z. B. Details zu in der Konsole signierten Profilen).

Um Profildaten zu erfassen, gehen Sie folgendermaßen vor:

- Erstellen Sie ein Schema basierend auf der Klasse „XDM Individual Profile“.

- Fügen Sie die Feldergruppe „Profile Core v2“ zum Schema hinzu.

- Fügen Sie ein Identifizierungsobjekt hinzu, das auf der Feldergruppe „Profile Core v2“ basiert.

- Definieren Sie die Experience Cloud-ID als primäre Kennung und die E-Mail als Kennung.

- Aktivieren Sie dieses Schema für das Profil

Weitere Informationen zum Hinzufügen und Entfernen von Feldergruppen und einzelnen Feldern zu einem Schema finden Sie unter [Erstellen und Bearbeiten von Schemata über die Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=de).

### Erstellen eines Datensatzes

Mit Ihrem Schema haben Sie Ihr Datenmodell definiert. Jetzt müssen Sie das Konstrukt definieren, um diese Daten mithilfe von Datensätzen zu speichern und zu verwalten.

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

   ![Aktivieren eines Schemas für ein Profil](./assets/aepwebsdk-dataset-profile.png)

Im [Handbuch zur Datensatz-Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) können Sie nachlesen, wie ein Datensatz angezeigt, in der Vorschau angesehen, erstellt und gelöscht werden kann und wie ein Datensatz für das Echtzeit-Kundenprofil aktiviert wird.

## Einrichten eines Datenstroms

Ein Datastream stellt die serverseitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs und der Adobe Experience Platform Edge Network Server-API dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDKs und Edge Network Server-APIs werden Daten an das Adobe Experience Platform Edge Network gesendet. Es ist der Datastream, der bestimmt, an welche Dienste diese Daten weitergeleitet werden.

In Ihrem Setup möchten Sie, dass die Daten, die Sie aus dem Spiel sammeln, an Ihren Datensatz in Adobe Experience Platform gesendet werden.

Gehen Sie folgendermaßen vor, um einen Datenstrom einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche die Option **[!UICONTROL Datenströme]** in [!UICONTROL DATENERFASSUNG] in der linken Leiste.

2. Wählen Sie **[!UICONTROL Neuer Datenstrom]** aus.

3. Benennen und beschreiben Sie Ihren Datenstrom. Wählen Sie Ihr Schema in der Liste [!UICONTROL Ereignisschema] aus.

   ![Neuer Datenstrom](./assets/new-datastream.png)

4. Wählen Sie **[!UICONTROL Speichern]** aus.

5. Wählen Sie **[!UICONTROL Service hinzufügen]** aus.

6. Im Bildschirm [!UICONTROL Service hinzufügen]:

   1. Wählen Sie **[!UICONTROL Adobe Experience Platform]** in der Liste [!UICONTROL Service] aus.

   2. Achten Sie darauf, dass **[!UICONTROL Aktiviert]** ausgewählt ist.

   3. Wählen Sie Ihren Datensatz aus der Liste [!UICONTROL Ereignisdatensatz] aus.

      ![Datenstrom-AEP-Service](./assets/datastream-aep-service.png)

   4. Lassen Sie die anderen Einstellungen unverändert und wählen Sie **[!UICONTROL Speichern]** aus, um den Datenstrom zu speichern.

Ihr Datenspeicher ist jetzt so konfiguriert, dass die von Ihrem Spiel erfassten Daten an Ihren Datensatz in Adobe Experience Platform weitergeleitet werden.

Weitere Informationen um Konfigurieren eines Datenstroms und zum Umgang mit sensiblen Daten finden Sie unter [Übersicht über Datenströme](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=de).

## Verwenden der Edge Network Server-API

Bei der Entwicklung Ihres Spiels können Sie gegebenenfalls relevante Aufrufe zur Adobe Experience Platform Edge Network Server-API hinzufügen.

Um beispielsweise die Punktzahl des Players zu aktualisieren, würden Sie Folgendes verwenden:

```
curl -X POST "https://server.adobedc.net/ee/v2/interact?dataStreamId={DATASTREAM_ID}"
-H "Authorization: Bearer {TOKEN}"
-H "x-gw-ims-org-id: {ORG_ID}"
-H "x-api-key: {API_KEY}"
-H "Content-Type: application/json"
-d '{
   "event": {
      "xdm": {
         "identityMap": {
            "Email_LC_SHA256": [
               {
                  "id": "0c7e6a405862e402eb76a70f8a26fc732d07c32931e9fae9ab1582911d2e8a3b",
                  "primary": true
               }
            ]
         },
         "eventType": "game.scoreUpdate",
         "{sandbox}": {
            "scores": {
               "afterMatch": 132391",
            }
         },
         "timestamp": "2021-08-09T14:09:20.859Z"
      }
   }
}'
```

In der Beispielanfrage zur POST `{DATASTREAM_ID}` verweist auf die Kennung des zuvor konfigurierten Beispiel-Datastreams. `{sandbox}` ist der eindeutige Name Ihrer Sandbox, der den Pfad zur benutzerdefinierten Feldergruppe &quot;Blinding Light&quot;angibt.

Siehe [Interaktive Datenerfassung](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=de) und [Nicht interaktive Datenerfassung](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html) Weitere Informationen zur Verwendung der Edge Network Server-API.

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

   - Wählen Sie zuvor erstellte Datensätze und/oder andere relevante Datensätze aus, die Sie in Ihre Verbindung aufnehmen möchten

   - Wählen Sie **[!UICONTROL Weiter]** aus.

   Im Schritt [!UICONTROL Datensatzeinstellungen] in [!UICONTROL Datensätze hinzufügen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle in der Liste [!UICONTROL Datenquellentyp] aus. Wenn Sie **[!UICONTROL Sonstige]** angeben, fügen Sie eine Beschreibung für Ihre Datenquelle hinzu.

      - Definieren Sie **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Datensatz-Aufstockung vorhandener Daten]** entsprechend Ihren Anforderungen.

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

5. Um Ihren ersten Bericht zu erstellen, ziehen Sie Dimensionen und Metriken per Drag-and-Drop in die [!UICONTROL Freiformtabelle] im [!UICONTROL Bedienfeld].

Weitere Informationen zum Erstellen von Projekten und zum Durchführen einer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern finden Sie unter [Analysis Workspace – Überblick](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Sie haben jetzt alle Schritte ausgeführt. Definieren Sie zunächst, welche Daten (Schema) erfasst werden sollen und wo sie (Datensatz) in Adobe Experience Platform gespeichert werden sollen. Sie haben einen Datenspeicher im Edge-Netzwerk konfiguriert, um sicherzustellen, dass Daten an diesen Datensatz weitergeleitet werden können. Anschließend haben Sie die Edge Network Server-API verwendet, um diese Daten an Ihren Datastream zu senden. Sie haben eine Verbindung im Customer Journey Analytics definiert, um Ihre Spieldaten und andere Daten zu verwenden. Mit Ihrer Datenansichtsdefinition können Sie festlegen, welche Dimension und Metriken verwendet werden sollen. Schließlich haben Sie Ihre ersten Projektvisualisierungen und -analysen für Ihre Spieldaten erstellt.
