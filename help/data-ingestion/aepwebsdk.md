---
title: Daten über das Adobe Experience Platform Web SDK erfassen
description: Erläuterung der Datenaufnahme in Customer Journey Analytics über das Adobe Experience Platform Web SDK und das Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: 0b595e9e-0dcf-4c70-ac6d-5a2322824328
role: Admin
source-git-commit: 1ded359997c4915f1b5ea6237aceb4d3d922b3a9
workflow-type: tm+mt
source-wordcount: '3546'
ht-degree: 83%

---

# Daten über das Adobe Experience Platform Web SDK erfassen

In dieser Kurzanleitung wird erklärt, wie Sie Website-Tracking-Daten mithilfe des Adobe Experience Platform Web SDK und Edge Network direkt in Adobe Experience Platform aufnehmen und dann in Customer Journey Analytics verwenden können.

Gehen Sie dazu folgendermaßen vor:

- **Richten Sie ein Schema und einen Datensatz** in Adobe Experience Platform ein, um das Modell (Schema) der zu erfassenden Daten zu definieren und um festzulegen, wo die Daten (Datensatz) erfasst werden sollen.

- **Richten Sie einen Datenstrom ein**, um das Adobe Experience Platform Edge Network so zu konfigurieren, dass Ihre erfassten Daten an den in Adobe Experience Platform konfigurierten Datensatz weitergeleitet werden.

- **Verwenden Sie Tags**, um Regeln und Datenelemente einfach entsprechend den Daten in Ihrer Datenschicht auf Ihrer Website zu konfigurieren. Sorgen Sie dann dafür, dass die Daten an den im Adobe Experience Platform Edge Network konfigurierten Datenstrom gesendet werden.

- **Stellen Sie die Daten bereit und validieren Sie sie**. Nutzen Sie eine Umgebung, in der Sie die Entwicklung von Tags iterieren können. Veröffentlichen Sie sie nach der Validierung in Ihrer Produktionsumgebung.

- **Richten Sie in Customer Journey Analytics eine Verbindung ein**. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Richten Sie in Customer Journey Analytics eine Datenansicht ein**, um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Richten Sie in Customer Journey Analytics ein Projekt ein**, um Berichte und Visualisierungen zu erstellen.

>[!NOTE]
>
> Dieses Schnellstarthandbuch ist eine vereinfachte Anleitung zur Erfassung von Daten, die von Ihrer Site in Adobe Experience Platform erfasst wurden, und zur Verwendung in Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Artikel zu lesen, auf die verwiesen wird.


## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform zu erfassen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform aufgenommenen Daten müssen einer standardmäßigen, denormalisierten Struktur entsprechen, damit sie von nachgelagerten Funktionen erkannt und genutzt werden können. Das Experience-Datenmodell (XDM) ist das Standard-Framework, das diese Struktur in Form von Schemata bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die erfassten Daten zu speichern und zu verwalten. Ein Datensatz ist ein Speicher- und Verwaltungskonstrukt für eine Datenerfassung (normalerweise eine Tabelle), die ein Schema (Spalten) und Felder (Zeilen) enthält.

Alle in Adobe Experience Platform aufgenommene Daten müssen einem vordefinierten Schema entsprechen, bevor sie als Datensatz gespeichert werden können.

### Einrichten eines Schemas

Angenommen, Sie möchten einige Daten von Profilen tracken, die Ihre Website besuchen, z. B. Seitenname und Identifizierung.
Zunächst müssen Sie ein Schema definieren, das diese Daten modelliert.

Gehen Sie folgendermaßen vor, um das Schema einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemata]** in [!UICONTROL DATEN-MANAGEMENT] aus.

1. Auswählen **[!UICONTROL Schema erstellen]**. .
1. Im Schritt Klasse auswählen des Assistenten Schema erstellen :

   1. Auswählen **[!UICONTROL Erlebnisereignis]**.

      ![Erstellen eines Schemas zur Hervorhebung eines Erlebnisereignisses](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Ein Erlebnisereignis-Schema wird zum Modellieren der _Verhalten_ eines Profils (wie Name der Szene, Schaltfläche zum Hinzufügen zum Warenkorb). Das Schema „Individuelles Profil“ wird verwendet, um die _Attribute_ eines Profils zu modellieren (z. B. Name, E-Mail, Geschlecht).

   1. Klicken Sie auf **[!UICONTROL Weiter]**.


1. Im [!UICONTROL Name und Überprüfungsschritt] des [!UICONTROL Schema erstellen] Assistent:

   1. Geben Sie einen **[!UICONTROL Anzeigename des Schemas]** für Ihr Schema und (optional) a **[!UICONTROL Beschreibung]**.

      ![Schema-Fenster mit Namen für Schemafelder erstellen](./assets/create-ee-schema-wizard-step-2.png)

   1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Auf der Registerkarte Struktur des Beispielschemas:

   1. Wählen Sie **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen] aus.

      ![Hinzufügen der Feldergruppe](./assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   1. Wählen Sie im Dialog [!UICONTROL Feldergruppen hinzufügen] die Feldergruppe **[!UICONTROL AEP Web SDK ExperienceEvent]** aus der Liste aus.

      ![Die Feldergruppe „AEP Web SDK ExperienceEvent“](./assets/select-aepwebsdk-experienceevent.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören, z. B. `web > webPageDetails > name`.

      ![Vorschau der Feldergruppe „AEP Web SDK ExperienceEvent“](./assets/aepwebsdk-experiencevent-preview.png)

      Wählen Sie **[!UICONTROL Zurück]** aus, um die Vorschau zu schließen.

   1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL +]** neben Ihrem Schemanamen im Bedienfeld [!UICONTROL Struktur] aus.

   ![Beispiel für die Schaltfläche zum Hinzufügen eines Feldes zum Schema](./assets/example-schema-plus.png)

1. Geben Sie im Bedienfeld [!UICONTROL Feldeigenschaften] als Namen `Identification` und als [!UICONTROL Anzeigename]**[!UICONTROL Identifikation]** ein, wählen Sie als [!UICONTROL Typ] **[!UICONTROL Objekt]** und als [!UICONTROL Feldergruppe] **[!UICONTROL ExperienceEvent Core v2.1]** aus.

   >[!NOTE]
   >
   >Wenn diese Feldergruppe nicht verfügbar ist, suchen Sie nach einer anderen Feldergruppe, die Identitätsfelder enthält. Oder [eine neue Feldergruppe erstellen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) und [Hinzufügen neuer Identitätsfelder](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (like `ecid`, `crmId`und andere erforderliche Elemente) zur Feldergruppe hinzu und wählen Sie diese neue Feldergruppe aus.

   ![Identifizierungsobjekt](./assets/identification-field.png)

   Das Identifizierungsobjekt fügt Ihrem Schema Identifizierungsfunktionen hinzu. In Ihrem Fall möchten Sie Profile, die Ihre Site besuchen, mithilfe der Experience Cloud-ID und der E-Mail-Adresse identifizieren. Es gibt viele weitere Attribute, mit denen Sie die Identifizierung Ihrer Person verfolgen können (z. B. Kunden-ID, Treueprogramm-ID).

   Wählen Sie **[!UICONTROL Anwenden]** aus, um dieses Objekt zu Ihrem Schema hinzuzufügen.

1. Wählen Sie im soeben hinzugefügten Identifizierungsobjekt das Feld **[!UICONTROL ECID]** aus und danach im rechten Bedienfeld **[!UICONTROL Identität]** und **[!UICONTROL Primäre Identität]** sowie die Option **[!UICONTROL ECID]** in der Liste [!UICONTROL Identity-Namespace].

   ![Spezifizieren Sie die ECID als Identität](./assets/specify-identity.png)

   Sie spezifizieren die Experience Cloud-Identität als primäre Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen, die dieselbe ECID haben, zu kombinieren (Stitching).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im ECID-Attribut.

1. Wählen Sie das Feld **[!UICONTROL E-Mail]** im soeben hinzugefügten Identifizierungsobjekt aus und danach **[!UICONTROL Identität]** und **[!UICONTROL E-Mail]** in der Liste [!UICONTROL Identity-Namespace] im Bedienfeld [!UICONTROL Feldeigenschaften].

   ![Spezifizieren von E-Mail als Identität](./assets/specify-email-identity.png)

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

Sie haben ein Minimalschema erstellt, das die Daten modelliert, die Sie auf Ihrer Website erfassen können. Mithilfe des Schemas können Profile anhand der Experience Cloud-Identität und -E-Mail-Adresse identifiziert werden. Durch die Aktivierung des Schemas für das Profil können die auf Ihrer Website erfassten Daten zum Echtzeit-Kundenprofil hinzugefügt werden.

Neben den Verhaltensdaten können Sie auch Profilattributdaten auf Ihrer Website erfassen (z. B. Details zu Profilen, die einen Newsletter abonnieren).

Um diese Profildaten zu erfassen, gehen Sie folgendermaßen vor:

- Erstellen Sie ein Schema basierend auf der Klasse „XDM Individual Profile“.

- Fügen Sie die Feldergruppe „Profile Core v2“ zum Schema hinzu.

- Fügen Sie ein Identifizierungsobjekt hinzu, das auf der Feldergruppe „Profile Core v2“ basiert.

- Definieren Sie die Experience Cloud-ID als primäre Kennung und die E-Mail als Kennung.

- Aktivieren Sie dieses Schema für das Profil

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

   ![Aktivieren eines Schemas für ein Profil](./assets/aepwebsdk-dataset-profile.png)

Im [Handbuch zur Datensatz-Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) können Sie nachlesen, wie ein Datensatz angezeigt, in der Vorschau angesehen, erstellt und gelöscht werden kann und wie ein Datensatz für das Echtzeit-Kundenprofil aktiviert wird.

## Einrichten eines Datenstroms

Ein Datenstrom stellt die Server-seitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDKs werden Daten an das Adobe Experience Platform Edge Network gesendet. Es ist der Datastream, der bestimmt, an welche Dienste diese Daten weitergeleitet werden.

Im vorliegenden Beispiel möchten Sie, dass die auf der Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform gesendet werden.

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

Ihr Datenstrom ist jetzt so konfiguriert, dass die auf Ihrer Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform weitergeleitet werden.

Weitere Informationen um Konfigurieren eines Datenstroms und zum Umgang mit sensiblen Daten finden Sie unter [Übersicht über Datenströme](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=de).



## Verwenden von Tags

Um Code auf Ihrer Site zu implementieren, um tatsächlich Daten zu erfassen, verwenden Sie die Funktion Tags in Adobe Experience Platform . Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags ermöglichen die nahtlose Integration mit Adobe Experience Platform über die Adobe Experience Platform Web SDK-Erweiterung.

### Erstellen von Tags

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Tags]** in [!UICONTROL DATENERFASSUNG].

2. Wählen Sie **[!UICONTROL Neue Eigenschaft]** aus.

   Benennen Sie das Tag, wählen Sie **[!UICONTROL Web]** aus und geben Sie einen Domain-Namen ein. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren.

   ![Erstellen einer Eigenschaft](./assets/create-property.png)

### Konfigurieren Ihres Tags

Nachdem Sie das Tag erstellt haben, müssen Sie es mit den richtigen Erweiterungen konfigurieren und Datenelemente und Regeln entsprechend der gewünschten Verfolgung Ihrer Site konfigurieren und Daten an Adobe Experience Platform senden.

Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.


#### **Erweiterungen**

Um sicherzustellen, dass Sie Daten an Adobe Experience Platform (über Ihren Datastream) senden können, fügen Sie Ihrem -Tag die Adobe Platform Web SDK-Erweiterung hinzu.

Gehen Sie folgendermaßen vor, um die Adobe Experience Platform Web SDK-Erweiterung zu erstellen und zu konfigurieren:

1. Wählen Sie **[!UICONTROL Erweiterungen]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Katalog]** in der oberen Leiste aus.

3. Suchen Sie nach der Adobe Experience Platform Web SDK-Erweiterung oder scrollen Sie zu ihr und wählen Sie **[!UICONTROL Installieren]** aus, um sie zu installieren.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Wählen Sie Ihre Sandbox und Ihren zuvor erstellten Datenstrom für Ihre [!UICONTROL Produktionsumgebung] und (optional) Ihre [!UICONTROL Staging-Umgebung] und Ihre [!UICONTROL Entwicklungsumgebung] aus.

   ![Konfigurieren der AEP Web SDK-Erweiterung](./assets/aepwebsk-extension-datastreams.png)

   Wählen Sie **[!UICONTROL Speichern]** aus.

Weitere Informationen finden Sie unter [Konfigurieren der Adobe Experience Platform Web SDK-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html).

Das Web SDK enthält die [!UICONTROL Adobe Experience Cloud ID-Dienst] nativ verwenden, sodass Sie die ID-Diensterweiterung nicht zu Ihrem -Tag hinzufügen müssen.

#### **Datenelemente**

Datenelemente sind die Bausteine Ihres Datenwörterbuchs (oder Ihrer Data Map). Verwenden Sie Datenelemente zum Erfassen, Organisieren und Bereitstellen von Daten in Marketing- und Werbe-Tools. Datenelemente richten Sie in Ihren Tags ein, die aus Ihrer Datenschicht lesen und zur Bereitstellung von Daten in Adobe Experience Platform verwendet werden können.

Es gibt verschiedene Arten von Datenelementen. Sie richten zunächst ein Datenelement ein, um den Seitennamen zu erfassen, den Personen auf Ihrer Site anzeigen.

Gehen Sie folgendermaßen vor, um ein Datenelement für den Seitennamen zu definieren:

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

3. Im Dialog [!UICONTROL Datenelement erstellen]:

   - Benennen Sie Ihr Datenelement, z. B. `Page Name`.

   - Wählen Sie **[!UICONTROL Core]** in der Liste [!UICONTROL Erweiterung] aus.

   - Wählen Sie **[!UICONTROL Seiteninformationen]** in der Liste [!UICONTROL Datenelementtyp] aus.

   - Wählen Sie **[!UICONTROL Titel]** in der Liste [!UICONTROL Attribut] aus.

     ![Erstellen eines Datumselements mithilfe von Seiteninformationen](./assets/create-dataelement-1.png)

     Alternativ hätten Sie zum Definieren des Datenelements auch den Wert einer Variablen Ihrer Datenschicht, z. B. `pageName`, und ein Datenelement vom Typ [!UICONTROL JavaScript-Variable] verwenden können.

     ![Erstellen eines Datenelements mit einer JavaScript-Variablen](./assets/create-dataelement-2.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Sie möchten jetzt ein Datenelement einrichten, das auf die Experience Cloud-ID verweist, die automatisch vom Adobe Experience Platform Web SDK bereitgestellt und über die Experience Cloud ID Service-Erweiterung verfügbar ist.

Gehen Sie folgendermaßen vor, um ein ECID-Datenelement zu definieren:

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

3. Im Dialog [!UICONTROL Datenelement erstellen]:

   - Benennen Sie Ihr Datenelement, z. B. `ECID`.

   - Wählen Sie **[!UICONTROL Experience Cloud ID Service]** in der Liste [!UICONTROL Erweiterung] aus.

   - Wählen Sie **[!UICONTROL ECID]** in der Liste [!UICONTROL Datenelementtyp].

     ![ECID-Datenelement](./assets/ecid-dataelement.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Abschließend möchten Sie Ihre spezifischen Datenelemente dem zuvor definierten Schema zuordnen. Sie definieren ein weiteres Datenelement, das Ihrem XDM-Schema entspricht.

Gehen Sie folgendermaßen vor, um ein XDM-Objekt-Datenelement zu definieren:

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

3. Im Dialog [!UICONTROL Datenelement erstellen]:

   - Benennen Sie Ihr Datenelement, z. B. `XDM - Page View`.

   - Wählen Sie **[!UICONTROL Adobe Experience Platform Web SDK]** in der Liste [!UICONTROL Erweiterung] aus.

   - Wählen Sie **[!UICONTROL XDM-Objekt]** in der Liste [!UICONTROL Datenelementtyp] aus.

   - Wählen Sie Ihre Sandbox in der Liste [!UICONTROL Sandbox] aus.

   - Wählen Sie Ihr Schema in der Liste [!UICONTROL Schema] aus.

   - Ordnen Sie das Attribut `identification > core > ecid`, das in Ihrem Schema definiert ist, dem ECID-Datenelement zu. Wählen Sie das Zylindersymbol aus, um das ECID-Datenelement in der Liste der Datenelemente einfach auswählen zu können.

     ![ECID-Datenelement auswählen](./assets/pick-ecid-dataelement.png)

     ![ECID-Datenelement zuordnen](./assets/map-ecid.png)


   - Ordnen Sie das Attribut `web > webPageDetails > name`, das in Ihrem Schema definiert ist, dem Datenelement „Seitenname“ zu.

     ![Datenelement „Seitenname“ zuordnen](./assets/map-pagename.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.


#### **Regeln**

Tags in Adobe Experience Platform folgen einem regelbasierten System. Sie suchen nach Benutzerinteraktionen und zugehörigen Daten. Wenn die in Ihren Regeln formulierten Kriterien erfüllt sind, löst die Regel die jeweils definierte Erweiterung, das Skript oder den Client-seitigen Code aus. Sie können mithilfe von Regeln Daten (wie ein XDM-Objekt) unter Verwendung der der Adobe Experience Platform Web SDK-Erweiterung an Adobe Experience Platform senden.

Gehen Sie folgendermaßen vor, um eine Regel zu definieren:

1. Wählen Sie **[!UICONTROL Regeln]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Neue Regel erstellen]** aus.

3. Im Dialog [!UICONTROL Regel erstellen]:

   - Benennen Sie die Regel, beispielsweise mit `Page View`.

   - Wählen Sie **[!UICONTROL + Hinzufügen]** unter [!UICONTROL Ereignisse] aus.

   - Im Dialog [!UICONTROL Ereigniskonfiguration]:

      - Wählen Sie **[!UICONTROL Core]** in der Liste [!UICONTROL Erweiterung] aus.

      - Wählen Sie **[!UICONTROL Fenster geladen]** in der Liste [!UICONTROL Ereignistyp] aus.

        ![Regel – Ereigniskonfiguration](./assets/event-windowloaded-pageview.png)

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.



   - Wählen Sie **[!UICONTROL + Hinzufügen]** unter [!UICONTROL Aktionen] aus.

   - Im Dialog [!UICONTROL Aktionskonfiguration]:

      - Wählen Sie **[!UICONTROL Adobe Experience Platform Web SDK]** in der Liste [!UICONTROL Erweiterung] aus.

      - Wählen Sie **[!UICONTROL Ereignis senden]** in der Liste [!UICONTROL Aktionstyp] aus.

      - Wählen Sie **[!UICONTROL web.webpagedetails.pageViews]** in der Liste [!UICONTROL Typ] aus.

      - Wählen Sie das Zylindersymbol neben [!UICONTROL XDM-Daten] und dann **[!UICONTROL XDM – Seitenansicht]** in der Liste der Datenelemente aus

     ![Regel – Aktionskonfiguration](./assets/action-pageview-xdm.png)

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.

   - Ihre Regel sollte wie folgt aussehen:

     ![Regel erstellen](assets/rule-pageview.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Das obige Beispiel ist nur ein Beispiel für die Definition einer Regel, die XDM-Daten sendet, die Werte aus anderen Datenelementen enthalten, an Adobe Experience Platform.

Sie können Regeln in Ihrem Tag auf unterschiedliche Weise verwenden, um (mithilfe Ihrer Datenelemente) Variablen zu bearbeiten.

Weitere Informationen finden Sie unter [Regeln](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=de).

### Erstellen und Veröffentlichen Ihres Tags

Nachdem Sie Datenelemente und Regeln definiert haben, müssen Sie Ihr Tag erstellen und veröffentlichen. Wenn Sie einen Bibliotheks-Build erstellen, müssen Sie ihn einer Umgebung zuweisen. Die Erweiterungen, Regeln und Datenelemente des Builds werden dann kompiliert und in die zugewiesene Umgebung eingefügt. Jede Umgebung bietet einen eindeutigen Einbettungs-Code, mit dem Sie den zugewiesenen Build in Ihre Website integrieren können.

Gehen Sie folgendermaßen vor, um Ihr Tag zu erstellen und zu veröffentlichen:

1. Wählen Sie **[!UICONTROL Veröffentlichungsfluss]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Arbeitsbibliothek auswählen]**, gefolgt von **[!UICONTROL Bibliothek hinzufügen...]** aus.

3. Im Dialog [!UICONTROL Bibliothek erstellen]:

   - Benennen Sie die Bibliothek.

   - Wählen Sie **[!UICONTROL Entwicklung (development)]** in der Liste [!UICONTROL Umgebung] aus.

   - Wählen Sie **[!UICONTROL + Alle geänderten Ressourcen hinzufügen]** aus.

     ![Veröffentlichen – Bibliothek erstellen](./assets/create-library-aep.png)

   - Wählen Sie **[!UICONTROL Speichern und in Entwicklung erstellen]** aus.

   Ihr -Tag wird gespeichert und für Ihre Entwicklungsumgebung erstellt. Ein grüner Punkt kennzeichnet eine erfolgreiche Erstellung Ihres Tags in Ihrer Entwicklungsumgebung.

4. Sie können **[!UICONTROL ...]** auswählen, um die Bibliothek neu zu erstellen oder in eine Staging- oder Produktionsumgebung zu verschieben.

   ![Veröffentlichen – Bibliothek erstellen](./assets/build-library.png)

Adobe Experience Platform-Tags unterstützen einfache bis komplexe Veröffentlichungs-Workflows, die auch Ihre Bereitstellung des Adobe Experience Platform Web SDK umfassen.

Weitere Informationen finden Sie unter [Veröffentlichung – Überblick](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=de).


### Abrufen des Tag-Codes

Schließlich müssen Sie Ihr Tag auf der Website installieren, die Sie verfolgen möchten. Dies bedeutet, dass Sie Code in das Kopfzeilen-Tag der Vorlage Ihrer Website einfügen.

Gehen Sie folgendermaßen vor, um Code abzurufen, der auf Ihr Tag verweist:

1. Wählen Sie **[!UICONTROL Umgebungen]** in der linken Leiste aus.

2. Wählen Sie in der Umgebungsliste die jeweilige Installieren-Schaltfläche (Kästchen) aus.

   Wählen Sie im Dialog [!UICONTROL Web-Installationsanleitung] die Schaltfläche „Kopieren“ neben dem Skriptcode aus, der wie folgt aussehen sollte:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Umgebung](./assets/environment.png)

3. Wählen Sie **[!UICONTROL Schließen]** aus.

Anstelle des Codes für die Entwicklungsumgebung hätten Sie auch eine andere Umgebung (Staging, Produktion) auswählen können, je nachdem, wo Sie das Adobe Experience Platform Web SDK bereitstellen möchten.

Weitere Informationen finden Sie in [Umgebungen](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=de?).

## Bereitstellen und validieren

Sie können den Code jetzt auf der Entwicklungsversion Ihrer Website im Tag `<head>` bereitstellen. Nach der Bereitstellung beginnt Ihre Website mit der Datenerfassung in Adobe Experience Platform.

Validieren Sie Ihre Implementierung, korrigieren Sie sie bei Bedarf und stellen Sie sie mithilfe der Publishing-Workflow-Funktion von Tags in Ihrer Staging- und Produktionsumgebung bereit.

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

   - Wählen Sie den zuvor erstellten Datensatz aus (`Example dataset`) und etwaige andere Datensätze, die Sie in Ihre Verbindung einschließen möchten.

     ![Hinzufügen von Datensätzen](./assets/cja-connections-2b.png)

   - Wählen Sie **[!UICONTROL Weiter]** aus.

   Im Schritt [!UICONTROL Datensatzeinstellungen] in [!UICONTROL Datensätze hinzufügen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle in der Liste [!UICONTROL Datenquellentyp] aus. Wenn Sie **[!UICONTROL Sonstige]** angeben, fügen Sie eine Beschreibung für Ihre Datenquelle hinzu.

      - Definieren Sie **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Datensatz-Aufstockung vorhandener Daten]** entsprechend Ihren Anforderungen.

     ![Konfigurieren von Datensätzen](./assets/cja-connections-3b.png)

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

5. Um Ihren ersten Bericht zu erstellen, ziehen Sie Dimensionen und Metriken per Drag-and-Drop in die [!UICONTROL Freiformtabelle] im [!UICONTROL Bedienfeld]. Ziehen Sie beispielsweise `Program Points Balance` und `Page View` als Metriken sowie `email` als Dimension auf die Tabelle, um einen kurzen Überblick über die Profile zu erhalten, die Ihre Website besucht haben und Mitglieder des Treueprogramms sind, mit dem Treuepunkte gesammelt werden.

   ![Analysis Workspace – erster Bericht](./assets/cja-projects-5.png)

Weitere Informationen zum Erstellen von Projekten und zum Durchführen einer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern finden Sie unter [Analysis Workspace – Überblick](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Sie haben jetzt alle Schritte ausgeführt. Definieren Sie zunächst, welche Daten (Schema) erfasst werden sollen und wo sie (Datensatz) in Adobe Experience Platform gespeichert werden sollen. Anschließend haben Sie einen Datenspeicher im Edge Network konfiguriert, um sicherzustellen, dass Daten an diesen Datensatz weitergeleitet werden können. Anschließend haben Sie Ihr Tag definiert und bereitgestellt. Dieses enthält die Erweiterungen (Adobe Experience Platform Web SDK, Experience Cloud ID Service), Datenelemente und Regeln, anhand derer Daten auf Ihrer Website erfasst und an Ihren Datenstrom weitergeleitet werden. Sie haben eine Verbindung in Customer Journey Analytics definiert, um Ihre Website-Tracking-Daten und andere Daten zu verwenden. Durch die Definition Ihrer Datenansicht konnten Sie festlegen, welche Dimension und Metriken verwendet werden sollen. Abschließend haben Sie Ihr erstes Projekt erstellt, in dem Ihre Daten visualisiert und analysiert wurden.
