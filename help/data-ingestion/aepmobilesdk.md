---
title: Daten über das Adobe Experience Platform Mobile SDK erfassen
description: Erläuterung der Datenaufnahme in Customer Journey Analytics über das Adobe Experience Platform Mobile SDK und das Edge Network
solution: Customer Journey Analytics
feature: Basics
exl-id: fb48b031-e093-4490-b457-69dbb5debe8d
role: Admin
source-git-commit: f078bf7b9b9d87335f435db2bbba87b078412738
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 60%

---

# Daten über das Adobe Experience Platform Mobile SDK erfassen

In dieser Kurzanleitung wird erläutert, wie Sie mit dem Adobe Experience Platform Mobile SDK und Edge Network Tracking-Daten von Apps direkt in Adobe Experience Platform erfassen können. Verwenden Sie dann diese Daten im Customer Journey Analytics.

Gehen Sie dazu folgendermaßen vor:

- **Richten Sie ein Schema und einen Datensatz** in Adobe Experience Platform ein, um das Modell (Schema) der zu erfassenden Daten zu definieren und um festzulegen, wo die Daten (Datensatz) erfasst werden sollen.

- **Richten Sie einen Datenstrom ein**, um das Adobe Experience Platform Edge Network so zu konfigurieren, dass Ihre erfassten Daten an den in Adobe Experience Platform konfigurierten Datensatz weitergeleitet werden.

- **Verwenden Sie Tags** , um Regeln und Datenelemente einfach mit den Daten in Ihrer Mobile App zu konfigurieren. Sorgen Sie dann dafür, dass die Daten an den im Adobe Experience Platform Edge Network konfigurierten Datenstrom gesendet werden.

- **Stellen Sie die Daten bereit und validieren Sie sie**. Nutzen Sie eine Umgebung, in der Sie die Entwicklung von Tags iterieren können. Veröffentlichen Sie sie nach der Validierung in Ihrer Produktionsumgebung.

- **Richten Sie in Customer Journey Analytics eine Verbindung ein**. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Richten Sie in Customer Journey Analytics eine Datenansicht ein**, um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Richten Sie in Customer Journey Analytics ein Projekt ein**, um Berichte und Visualisierungen zu erstellen.

>[!NOTE]
>
>Diese Kurzanleitung ist eine vereinfachte Anleitung zur Aufnahme von Daten, die aus Ihrer Anwendung erfasst wurden, in Adobe Experience Platform und zur Verwendung in Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Artikel zu lesen, auf die verwiesen wird.


## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform aufzunehmen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform aufgenommenen Daten müssen einer standardmäßigen, denormalisierten Struktur entsprechen, damit sie von nachgelagerten Funktionen erkannt und genutzt werden können. Experience-Datenmodell (XDM) ist das Standard-Framework, das eine Struktur in Form von Schemas bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die erfassten Daten zu speichern und zu verwalten. Ein Datensatz ist ein Speicher- und Verwaltungskonstrukt für eine Datenerfassung (normalerweise eine Tabelle), die ein Schema (Spalten) und Felder (Zeilen) enthält.

Alle in Adobe Experience Platform aufgenommene Daten müssen einem vordefinierten Schema entsprechen, bevor sie als Datensatz gespeichert werden können.

### Einrichten eines Schemas

Sie möchten einige Mindestdaten aus Profilen verfolgen, die Ihre mobile App verwenden, z. B. den Namen der Szene und die Identifizierung.
Zunächst müssen Sie ein Schema definieren, das diese Daten modelliert.

Gehen Sie folgendermaßen vor, um das Schema einzurichten:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemata]** in [!UICONTROL DATEN-MANAGEMENT] aus.

1. Wählen Sie **[!UICONTROL Schema erstellen]** aus.
.
1. Im Schritt Klasse auswählen des Assistenten Schema erstellen :

   1. Wählen Sie **[!UICONTROL Erlebnisereignis]** aus.

      ![Erstellen eines Schemas](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Mit einem Erlebnisereignis-Schema wird das _Verhalten_ eines Profils modelliert (z. B. Name der Szene, Schaltfläche zum Hinzufügen zum Warenkorb). Das Schema „Individuelles Profil“ wird verwendet, um die _Attribute_ eines Profils zu modellieren (z. B. Name, E-Mail, Geschlecht).

   1. Klicken Sie auf **[!UICONTROL Weiter]**.


1. Im Schritt [!UICONTROL Name und Überprüfung] des Assistenten [!UICONTROL Schema erstellen]:

   1. Geben Sie einen **[!UICONTROL Anzeigenamen des Schemas]** und (optional) eine **[!UICONTROL Beschreibung]** ein.

      ![Benennen des Schemas](./assets/create-ee-schema-wizard-step-2.png)

   1. Wählen Sie **[!UICONTROL Beenden]** aus.

1. Auf der Registerkarte Struktur des Beispielschemas:

   1. Wählen Sie **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen] aus.

      ![Hinzufügen der Feldergruppe](./assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   1. Wählen Sie im Dialogfeld [!UICONTROL Feldergruppen hinzufügen] die Feldergruppe **[!UICONTROL AEP Mobile SDK ExperienceEvent]** aus der Liste.

      ![AEP Mobile Lifecycle Details fieldgroup](./assets/select-aepmobilesdk-experienceevent.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören, z. B. `application > name`.

      ![AEP Mobile Lifecycle Details fieldgroup preview](./assets/aepmobilesdk-experienceevent-preview.png)

      Wählen Sie **[!UICONTROL Zurück]** aus, um die Vorschau zu schließen.

   1. Wählen Sie **[!UICONTROL Feldergruppen hinzufügen]** aus.

1. Wählen Sie **[!UICONTROL +]** neben Ihrem Schemanamen im Bedienfeld [!UICONTROL Struktur] aus.

   ![Beispiel für die Schaltfläche zum Hinzufügen eines Feldes zum Schema](./assets/example-mobileschema-plus.png)

1. Geben Sie im Bedienfeld [!UICONTROL Feldeigenschaften] den Wert `identification` als den Wert [!UICONTROL Feldnamen], den Wert **[!UICONTROL Identifizierung]** als den Anzeigenamen [!UICONTROL 8} ein, wählen Sie **[!UICONTROL Objekt]** als den Wert [!UICONTROL Typ] und wählen Sie **[!UICONTROL ExperienceEvent Core v2.1]** als Feldergruppe. 6}.]

   >[!NOTE]
   >
   >Wenn diese Feldergruppe nicht verfügbar ist, suchen Sie nach einer anderen Feldergruppe, die Identitätsfelder enthält. Oder [erstellen Sie eine neue Feldergruppe](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) und [fügen Sie der Feldergruppe neue Identitätsfelder hinzu](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (z. B. `ecid`, `crmId` und andere, die Sie benötigen) und wählen Sie diese neue Feldergruppe aus.

   ![Identifizierungsobjekt](./assets/identification-field-mobile.png)

   Das Identifizierungsobjekt fügt Ihrem Schema Identifizierungsfunktionen hinzu. In diesem Fall möchten Sie Profile mithilfe Ihrer App mithilfe der Experience Cloud-ID und der E-Mail-Adresse identifizieren. Es gibt viele weitere Attribute, mit denen Sie die Identifizierung Ihrer Person verfolgen können (z. B. Kunden-ID, Treueprogramm-ID).

   Wählen Sie **[!UICONTROL Anwenden]** aus, um dieses Objekt zu Ihrem Schema hinzuzufügen.

1. Wählen Sie im soeben hinzugefügten Identifizierungsobjekt das Feld **[!UICONTROL ECID]** aus und danach im rechten Bedienfeld **[!UICONTROL Identität]** und **[!UICONTROL Primäre Identität]** sowie die Option **[!UICONTROL ECID]** in der Liste [!UICONTROL Identity-Namespace].

   ![Spezifizieren Sie die ECID als Identität](./assets/specify-identity-mobile.png)

   Sie spezifizieren die Experience Cloud-Identität als primäre Identität, die Adobe Experience Platform Identity Service verwenden kann, um das Verhalten von Profilen, die dieselbe ECID haben, zu kombinieren (Stitching).

   Wählen Sie **[!UICONTROL Anwenden]** aus. Daraufhin erscheint ein Fingerabdruck-Symbol im ECID-Attribut.

1. Wählen Sie das Feld **[!UICONTROL E-Mail]** im soeben hinzugefügten Identifizierungsobjekt aus und danach **[!UICONTROL Identität]** und **[!UICONTROL E-Mail]** in der Liste [!UICONTROL Identity-Namespace] im Bedienfeld [!UICONTROL Feldeigenschaften].

   ![Spezifizieren von E-Mail als Identität](./assets/specify-email-identity-mobile.png)

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

Sie haben ein Minimalschema erstellt, das die Daten modelliert, die Sie aus Ihrer Mobile App erfassen können. Mithilfe des Schemas können Profile anhand der Experience Cloud-Identität und -E-Mail-Adresse identifiziert werden. Durch Aktivierung des Schemas für das Profil stellen Sie sicher, dass aus Ihrer Mobile App erfasste Daten zum Echtzeit-Kundenprofil hinzugefügt werden.

Neben den Verhaltensdaten können Sie auch Profilattributdaten aus Ihrer Mobile App erfassen (z. B. Details zu Profilen, die einen Newsletter abonnieren).

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

Ein Datenstrom stellt die Server-seitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDKs werden Daten an das Adobe Experience Platform Edge Network gesendet. Es ist der Datastream, der bestimmt, an welche Dienste diese Daten weitergeleitet werden.

Bei der Einrichtung möchten Sie, dass die von der App erfassten Daten an Ihren Datensatz in Adobe Experience Platform gesendet werden.

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

Ihr Datastream ist jetzt so konfiguriert, dass die von Ihrer Mobile App erfassten Daten an Ihren Datensatz in Adobe Experience Platform weitergeleitet werden.

Weitere Informationen um Konfigurieren eines Datenstroms und zum Umgang mit sensiblen Daten finden Sie unter [Übersicht über Datenströme](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=de).



## Verwenden von Tags

Verwenden Sie die Funktion Tags in Adobe Experience Platform, um Code auf Ihrer Site zur Datenerfassung zu implementieren. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags bieten eine nahtlose Integration mit Adobe Experience Platform mithilfe der Adobe Experience Platform Mobile SDK-Erweiterung.

### Erstellen von Tags

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Tags]** in [!UICONTROL DATENERFASSUNG].

2. Wählen Sie **[!UICONTROL Neue Eigenschaft]** aus.

   Benennen Sie das Tag und wählen Sie **[!UICONTROL Mobil]** aus. Wählen Sie **[!UICONTROL Speichern]** aus, um fortzufahren.

   ![Erstellen einer Eigenschaft](./assets/create-mobile-property.png)

### Konfigurieren Ihres Tags

Nachdem Sie das Tag erstellt haben, müssen Sie es mit den richtigen Erweiterungen konfigurieren, Datenelemente und Regeln entsprechend dem gewünschten Tracking auf Ihrer Website konfigurieren und Daten an Adobe Experience Platform senden.

Wählen Sie zum Konfigurieren das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus.


#### **Erweiterungen**

Fügen Sie Ihrem -Tag die Adobe Platform Edge Network-Erweiterung hinzu, um sicherzustellen, dass Sie Daten an Adobe Experience Platform senden können (über Ihren Datenspeicher).

So erstellen und konfigurieren Sie die Adobe Experience Platform Mobile SDK-Erweiterung:

1. Wählen Sie in der linken Leiste **[!UICONTROL Erweiterungen]** aus. Sie sehen, dass die Mobile Core- und Profil-Erweiterungen bereits verfügbar sind.

1. Wählen Sie **[!UICONTROL Katalog]** in der oberen Leiste aus.

1. Suchen Sie nach der Erweiterung **[!UICONTROL Adobe Experience Platform Edge Network]** oder scrollen Sie zu ihr und wählen Sie im rechten Bereich die Option **[!UICONTROL Installieren]** aus, um sie zu installieren.

1. Wählen Sie Ihre Sandbox und Ihren zuvor erstellten Datenstrom für Ihre [!UICONTROL Produktionsumgebung] und (optional) Ihre [!UICONTROL Staging-Umgebung] und Ihre [!UICONTROL Entwicklungsumgebung] aus.

   ![Konfiguration der AEP Mobile SDK-Erweiterung](./assets/aepmobilesdk-extension-datastream.png)

1. Geben Sie Ihre **[!UICONTROL Edge Network-Domäne]** unter [!UICONTROL Domänenkonfiguration] ein. Verwenden Sie in der Regel `<organizationName>.data.adobedc.net`.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

Weitere Informationen finden Sie unter [Konfigurieren der Adobe Experience Platform Edge Network-Erweiterung](https://developer.adobe.com/client-sdks/documentation/edge-network) .

Außerdem möchten Sie die folgenden zusätzlichen Erweiterungen aus dem Katalog einrichten:

- Identität.
- AEP Assurance.
- Zustimmung.

Weitere Informationen zu Erweiterungen und deren Konfiguration finden Sie unter [Konfigurieren einer Tag-Eigenschaft](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html?lang=de) im Tutorial für mobile Apps für Experience Platform .

#### **Datenelemente**

Datenelemente sind die Bausteine Ihres Datenwörterbuchs (oder Ihrer Data Map). Verwenden Sie Datenelemente zum Erfassen, Organisieren und Bereitstellen von Daten in Marketing- und Werbe-Tools. Sie richten Datenelemente in Ihrem Tag ein, die aus Daten oder Ereignissen der mobilen App gelesen werden und zur Bereitstellung von Daten in Adobe Experience Platform verwendet werden können.

Sie möchten beispielsweise den Betreibernamen aus der App erfassen.

Definieren eines Trägernamendatenelements:

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

3. Im Dialog [!UICONTROL Datenelement erstellen]:

   - Benennen Sie Ihr Datenelement, z. B. `Carrier Name`.

   - Wählen Sie **[!UICONTROL Mobile Core]** aus der Liste [!UICONTROL Erweiterung] aus.

   - Wählen Sie **[!UICONTROL Betreibername]** aus der Liste [!UICONTROL Datenelementtyp] aus.


     ![Erstellen eines Datumselements mithilfe von Seiteninformationen](./assets/create-dataelement-mobile.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Sie können beliebig viele Datenelemente erstellen und in Regeln verwenden.


#### **Regeln**

Tags in Adobe Experience Platform folgen einem regelbasierten System. Sie suchen nach Benutzerinteraktionen und zugehörigen Daten. Wenn die in Ihren Regeln formulierten Kriterien erfüllt sind, löst die Regel die jeweils definierte Erweiterung, das Skript oder den Client-seitigen Code aus. Sie können mithilfe von Regeln Daten (wie ein XDM-Objekt) mithilfe der Adobe Experience Platform Edge Network-Erweiterung an Adobe Experience Platform senden.

Beispielsweise möchten Sie Ereignisdaten senden, wenn die mobile App verwendet wird (im Vordergrund) und die mobile App nicht verwendet wird (zurück in den Hintergrund gepusht).

Gehen Sie folgendermaßen vor, um eine Regel zu definieren:

1. Wählen Sie **[!UICONTROL Regeln]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Neue Regel erstellen]** aus.

3. Im Dialog [!UICONTROL Regel erstellen]:

   - Benennen Sie die Regel, beispielsweise mit `Application Status`.

   - Wählen Sie **[!UICONTROL + Hinzufügen]** unter [!UICONTROL Ereignisse] aus.

   - Im Dialog [!UICONTROL Ereigniskonfiguration]:

      - Wählen Sie **[!UICONTROL Mobile Core]** aus der Liste [!UICONTROL Erweiterung] aus.

      - Wählen Sie **[!UICONTROL Vordergrund]** aus der Liste [!UICONTROL Ereignistyp] aus.

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.

   - Klicken Sie auf ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) neben [!UICONTROL Mobile Core - Vordergrund].

      - Wählen Sie **[!UICONTROL Mobile Core]** aus der Liste [!UICONTROL Erweiterung] aus.

      - Wählen Sie **[!UICONTROL Hintergrund]** aus der Liste [!UICONTROL Ereignistyp] aus.

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.

   - Klicken Sie auf ![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) unterhalb von [!UICONTROL AKTIONEN] hinzufügen. Im Dialog [!UICONTROL Aktionskonfiguration]:

      - Wählen Sie **[!UICONTROL Adobe Experience Platform Edge Network]** aus der Liste [!UICONTROL Erweiterung] aus.

      - Wählen Sie **[!UICONTROL Ereignis an Edge Network weiterleiten]** aus der Liste [!UICONTROL Aktionstyp] aus.

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.

   - Ihre Regel sollte wie folgt aussehen:

     ![Regel erstellen](assets/rule-appstatus.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Das obige Beispiel ist nur ein Beispiel für die Definition einer Regel, die XDM-Daten mit Anwendungsstatus an das Adobe Edge-Netzwerk und Adobe Experience Platform sendet.

Sie können Regeln in Ihrem Tag auf unterschiedliche Weise verwenden, um (mithilfe Ihrer Datenelemente) Variablen zu bearbeiten.

Weitere Informationen finden Sie unter [Regeln](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/#configure-a-rule-to-forward-lifecycle-metrics-to-platform).

### Erstellen und Veröffentlichen Ihres Tags

Nachdem Sie Datenelemente und Regeln definiert haben, müssen Sie Ihr Tag erstellen und veröffentlichen. Wenn Sie einen Bibliotheks-Build erstellen, müssen Sie ihn einer Umgebung zuweisen. Die Erweiterungen, Regeln und Datenelemente des Builds werden dann kompiliert und in die zugewiesene Umgebung eingefügt. Jede Umgebung bietet einen eindeutigen Einbettungs-Code, mit dem Sie den zugewiesenen Build in Ihre Website integrieren können.

Gehen Sie folgendermaßen vor, um Ihr Tag zu erstellen und zu veröffentlichen:

1. Wählen Sie **[!UICONTROL Veröffentlichungsfluss]** in der linken Leiste aus.

2. Wählen Sie **[!UICONTROL Arbeitsbibliothek auswählen]**, gefolgt von **[!UICONTROL Bibliothek hinzufügen...]** aus.

3. Im Dialog [!UICONTROL Bibliothek erstellen]:

   - Benennen Sie die Bibliothek.

   - Wählen Sie **[!UICONTROL Entwicklung (development)]** in der Liste [!UICONTROL Umgebung] aus.

   - Wählen Sie **[!UICONTROL + Alle geänderten Ressourcen hinzufügen]** aus.

     ![Veröffentlichen – Bibliothek erstellen](./assets/build-library-mobile.png)

   - Wählen Sie **[!UICONTROL Speichern und in Entwicklung erstellen]** aus.

   Ihr -Tag wird gespeichert und für Ihre Entwicklungsumgebung erstellt. Ein grüner Punkt kennzeichnet eine erfolgreiche Erstellung Ihres Tags in Ihrer Entwicklungsumgebung.

4. Sie können **[!UICONTROL ...]** auswählen, um die Bibliothek neu zu erstellen oder in eine Staging- oder Produktionsumgebung zu verschieben.

Adobe Experience Platform-Tags unterstützen einfache, komplexe Veröffentlichungs-Workflows, die für Ihre Implementierung des Adobe Experience Platform-Edge Networks geeignet sind.

Weitere Informationen finden Sie unter [Veröffentlichung – Überblick](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).


### Abrufen des Tag-Codes

Schließlich müssen Sie Ihr Tag in der App verwenden, die Sie verfolgen möchten.

So erhalten Sie Code-Anweisungen, die erklären, wie Sie Ihre App einrichten und Ihr Tag in der App verwenden:

1. Wählen Sie **[!UICONTROL Umgebungen]** in der linken Leiste aus.

2. Wählen Sie in der Liste der Umgebungen die richtige Schaltfläche ![Box](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Box_18_N.svg) installieren .

   Wählen Sie im Dialogfeld [!UICONTROL Mobile-Installationsanweisungen] die entsprechende Plattform ([!UICONTROL iOS], [!UICONTROL Android]). Verwenden Sie dann die Schaltfläche ![Kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) neben allen relevanten Codefragmenten, die Sie zum Einrichten und Initialisieren Ihrer App verwenden möchten:

   ![Umgebung](./assets/environment-mobile.png)

3. Wählen Sie **[!UICONTROL Schließen]** aus.

Anstelle des Codes für die Entwicklungsumgebung hätten Sie eine andere Umgebung (Staging, Produktion) auswählen können, je nachdem, wo Sie das Adobe Experience Platform Mobile SDK bereitstellen.

Weitere Informationen finden Sie in [Umgebungen](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=de?).

## Bereitstellen und validieren

Sie können den Code jetzt in Ihrer mobilen App bereitstellen. Nach der Bereitstellung beginnt Ihre mobile App mit der Datenerfassung in Adobe Experience Platform.

Validieren Sie Ihre Implementierung, korrigieren Sie sie bei Bedarf und stellen Sie sie mithilfe der Publishing-Workflow-Funktion von Tags in Ihrer Staging- und Produktionsumgebung bereit.

Detailliertere Informationen finden Sie im Tutorial [Implementieren von Adobe Experience Cloud in Mobile Apps](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=de) .

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

   - Wählen Sie zuvor erstellte Datensätze und/oder andere relevante Datensätze aus, die Sie in Ihre Verbindung aufnehmen möchten (z. B. Daten zu Push-Tracking-Erlebnisereignissen und Push-Profildaten aus Adobe Journey Optimizer)

     ![Hinzufügen von Datensätzen](./assets/cja-connections-ajopush.png)

   - Wählen Sie **[!UICONTROL Weiter]** aus.

   Im Schritt [!UICONTROL Datensatzeinstellungen] in [!UICONTROL Datensätze hinzufügen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten aus, die im Datensatzschema in Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle in der Liste [!UICONTROL Datenquellentyp] aus. Wenn Sie **[!UICONTROL Sonstige]** angeben, fügen Sie eine Beschreibung für Ihre Datenquelle hinzu.

      - Definieren Sie **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Datensatz-Aufstockung vorhandener Daten]** entsprechend Ihren Anforderungen.

     ![Konfigurieren von Datensätzen](./assets/cja-connections-ajopushid.png)

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

   ![Datenansichtskomponenten](./assets/cja-dataview-2-mobile.png)

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

5. Um Ihren ersten Bericht zu erstellen, ziehen Sie Dimensionen und Metriken per Drag-and-Drop in die [!UICONTROL Freiformtabelle] im [!UICONTROL Bedienfeld] . Ziehen Sie beispielsweise `Events` als Metriken und `Push Title` als Dimension, aufgeschlüsselt nach `Event Type`, um einen Überblick über Ihre Push-Benachrichtigungen für Ihre mobile App und deren Ereignisse zu erhalten.

   ![Analysis Workspace – erster Bericht](./assets/cja-projects-5-mobile.png)

Weitere Informationen zum Erstellen von Projekten und zum Durchführen einer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern finden Sie unter [Analysis Workspace – Überblick](../analysis-workspace/home.md).

>[!SUCCESS]
>
>Sie haben jetzt alle Schritte ausgeführt. Sie haben zunächst definiert, welche Daten erfasst werden sollen (Schema) und wo sie in Adobe Experience Platform gespeichert werden sollen (Datensatz). Dann haben Sie einen Datenstrom im Edge Network konfiguriert, damit Daten an diesen Datensatz weitergeleitet werden können. Anschließend haben Sie Ihr Tag definiert und bereitgestellt, das die Erweiterungen (Adobe Experience Platform-Edge Network und andere), Datenelemente und Regeln enthält, um Daten aus Ihrer mobilen App zu erfassen und an Ihren Datastream zu senden. Sie haben eine Verbindung im Customer Journey Analytics definiert, um Ihre Mobile App-Push-Benachrichtigungs-Tracking-Daten und andere Daten zu verwenden. Mit Ihrer Datenansichtsdefinition können Sie angeben, welche Dimension und Metriken verwendet werden sollen, und schließlich haben Sie Ihre ersten Projektvisualisierungs- und -analysedaten erstellt.
