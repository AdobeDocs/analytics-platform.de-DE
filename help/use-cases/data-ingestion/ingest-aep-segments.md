---
title: Adobe Experience Platform-Zielgruppen in Customer Journey Analytics erfassen
description: Erläutert, wie Adobe Experience Platform-Zielgruppen für weitere Analysen in Customer Journey Analytics aufgenommen werden.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 50%

---

# Adobe Experience Platform-Zielgruppen in Adobe Customer Journey Analytics erfassen

In diesem Anwendungsbeispiel wird eine vorläufige, manuelle Methode zur Einbindung von Adobe Experience Platform (Adobe Experience Platform)-Zielgruppen in Customer Journey Analytics untersucht. Diese Zielgruppen wurden möglicherweise im Adobe Experience Platform Segment Builder, in Adobe Audience Manager oder anderen Tools erstellt und sind im Echtzeit-Kundenprofil (RTCP) gespeichert. Die Zielgruppen bestehen aus einer Reihe von Profil-IDs und den entsprechenden Attributen/Ereignissen/etc. und wir möchten sie zur Analyse in Customer Journey Analytics Workspace einbringen.

## Voraussetzungen

* Zugriff auf Adobe Experience Platform (Adobe Experience Platform), insbesondere Echtzeit-Kundenprofil.
* Zugriff zum Erstellen/Verwalten von Adobe Experience Platform-Schemata und -Datensätzen.
* Zugriff auf Adobe Experience Platform Query Service (und die Möglichkeit, SQL zu schreiben) oder ein anderes Tool, um einige leichte Umwandlungen durchzuführen.
* Zugriff auf Customer Journey Analytics. Sie müssen ein Customer Journey Analytics-Produktadministrator sein, um Customer Journey Analytics-Verbindungen und Datenansichten erstellen/ändern zu können.
* Möglichkeit zur Verwendung der Adobe-APIs (Segmentierung, optional andere)

## Schritt 1: Wählen Sie Zielgruppen im Echtzeit-Kundenprofil aus {#audience}

[Das Echtzeit-Kundenprofil von Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) bietet eine ganzheitliche Sicht auf jeden einzelnen Kunden, indem es Daten aus verschiedenen Kanälen, einschließlich Online-, Offline-, CRM- und Drittanbieterdaten, kombiniert.

Wahrscheinlich haben Sie bereits Zielgruppen im Echtzeit-Kundenprofil, die aus verschiedenen Quellen stammen. Wählen Sie eine oder mehrere Zielgruppen für die Aufnahme in Customer Journey Analytics aus.

## Schritt 2: Erstellen Sie einen Profilvereinigungsdatensatz für den Export

Um die Zielgruppe in einen Datensatz zu exportieren, der schließlich zu einer Verbindung in Customer Journey Analytics hinzugefügt werden kann, müssen Sie einen Datensatz erstellen, dessen Schema ein Profil ist [Vereinigungsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=de#understanding-union-schemas).

Vereinigungsschemas bestehen aus mehreren Schemas, die dieselbe Klasse haben und für ein Profil aktiviert wurden. Im Vereinigungsschema können Sie eine Zusammenführung aller Felder sehen, die in Schemas enthalten sind, die dieselbe Klasse haben. Das Echtzeit-Kundenprofil verwendet das Vereinigungsschema, um eine ganzheitliche Ansicht jedes einzelnen Kunden zu erstellen.

## Schritt 3: Exportieren Sie eine Zielgruppe über einen API-Aufruf in den Profilvereinigungsdatensatz  {#export}

Bevor Sie eine Zielgruppe in Customer Journey Analytics importieren können, müssen Sie sie in einen Adobe Experience Platform-Datensatz exportieren. Dies kann nur mit der Segmentierungs-API und insbesondere mit dem [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=de) geschehen.

Sie können einen Exportauftrag mit der Zielgruppen-ID Ihrer Wahl erstellen und die Ergebnisse in den Adobe Experience Platform-Datensatz der Profilunion verschieben, den Sie in Schritt 2 erstellt haben. Obwohl Sie verschiedene Attribute/Ereignisse für die Zielgruppe exportieren können, müssen Sie nur das spezifische Feld für die Profil-ID exportieren, das mit dem Feld für die Personen-ID übereinstimmt, das in der von Ihnen verwendeten Customer Journey Analytics-Verbindung verwendet wird (siehe unten in Schritt 5).

## Schritt 4: Bearbeiten Sie die Exportausgabe

Die Ergebnisse des Exportvorgangs müssen in einen separaten Profildatensatz umgewandelt werden, damit sie in Customer Journey Analytics aufgenommen werden können.  Diese Umwandlung kann mit [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de)oder ein anderes Transformationstool Ihrer Wahl. Für die Berichterstellung in Customer Journey Analytics benötigen wir nur die Profil-ID (die mit der Personen-ID in Customer Journey Analytics übereinstimmt) und eine oder mehrere Zielgruppen-ID(s).

Der standardmäßige Exportvorgang enthält jedoch zusätzliche Daten. Daher müssen Sie diese Ausgabe bearbeiten, um irrelevante Daten zu entfernen und einige Dinge umzustellen.  Außerdem müssen Sie zuerst ein Schema/einen Datensatz erstellen, bevor Sie die umgewandelten Daten hinzufügen.

Im Folgenden finden Sie ein Beispiel für die Exportausgabe im Profilvereinigungsdatensatz **vor** der Bearbeitung:

![Nicht bearbeitete Ausgabe](../assets/export-unedited.png)

Beachten Sie Folgendes:

* Die Zielgruppen-ID ist unter `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` vorhanden.
* Der Status muss „realized“ oder „entered“, darf aber nicht „exited“ sein.

Dies ist das Format des Profildatensatzes, den Sie an Customer Journey Analytics senden können.

![Bearbeitete Ausgabe](../assets/export-edited.png)

Folgende Datenelemente müssen vorhanden sein:

* Zeichenfolgenfeld `_aresprodvalidation`: Bezieht sich auf Ihre Organisations-ID. Ihre wird anders lauten.
* Zeichenfolgenfeld `personID`: Dies ist das standardmäßige XDM-Schemafeld in Profildatensätzen, das die Person identifiziert. Verwenden Sie die Profil-ID vom Export.
* Zeichenfolgenfeld `audienceMembershipId`: Die Zielgruppen-ID vom Export. HINWEIS: Dieses Feld kann beliebig benannt werden (in Ihrem eigenen Schema).
* Fügen Sie einen Anzeigenamen für die Zielgruppe hinzu (`audienceMembershipIdName`), z. B.

  ![Anzeigename der Zielgruppe](../assets/audience-name.png)

* Fügen Sie bei Bedarf weitere Zielgruppen-Metadaten hinzu.

## Schritt 5: Diesen Profildatensatz zu einer bestehenden Verbindung in Customer Journey Analytics hinzufügen

Sie könnten [eine neue Verbindung erstellen](/help/connections/create-connection.md), aber die meisten Kunden möchten den Profildatensatz zu einer vorhandenen Verbindung hinzufügen. Die Zielgruppen-IDs &quot;ergänzen&quot;die vorhandenen Daten im Customer Journey Analytics.

## Schritt 6: Ändern der Datenansicht einer vorhandenen (oder neuen) Customer Journey Analytics

Fügen Sie `audienceMembershipId`, `audienceMembershipIdName` und `personID` zur Datenansicht hinzu.

## Schritt 7: Erstellen Sie einen Bericht in Workspace

Sie können jetzt Berichte zu `audienceMembershipId`, `audienceMembershipIdName` und `personID` in Workspace erstellen.

## Weitere Hinweise

* Sie sollten diesen Vorgang regelmäßig durchführen, damit die Zielgruppendaten im Customer Journey Analytics ständig aktualisiert werden.
* Sie können mehrere Zielgruppen in einer Customer Journey Analytics-Verbindung importieren. Dies erhöht zwar die Komplexität des Prozesses, es ist jedoch möglich. Damit dies funktioniert, müssen Sie einige Änderungen am obigen Prozess vornehmen:
   1. Führen Sie diesen Prozess für jede gewünschte Zielgruppe in Ihrer Zielgruppensammlung innerhalb des Echtzeit-Kundenprofis aus.
   1. Customer Journey Analytics unterstützt Arrays/Objekt-Arrays in Profildatensätzen. Es wird empfohlen, für audienceMembershipId oder audienceMembershipIdName ein [Array von Objekten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=de) zu verwenden.
   1. Erstellen Sie in Ihrer Datenansicht eine neue Dimension mithilfe der Teilzeichenfolgenumwandlung des `audienceMembershipId`-Felds, um die Zeichenfolge mit kommagetrennten Werten in ein Array zu konvertieren. HINWEIS: Derzeit besteht für das Array eine Beschränkung von 10 Werten.
   1. Sie können jetzt Berichte zu dieser neuen Dimension erstellen `audienceMembershipIds` in Customer Journey Analytics Workspace.
