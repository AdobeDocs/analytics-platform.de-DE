---
title: Konfigurieren von Experience Platform
description: Erfahren Sie, wie Sie Schemas und Datensätze für Experience Platform Data Mirror für Customer Journey Analytics konfigurieren
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 3%

---

# Konfigurieren von Experience Platform

{{release-limited-testing}}

Experience Platform Data Mirror für Customer Journey Analytics erfordert die ordnungsgemäße Konfiguration mehrerer Experience Platform-Komponenten:

* Schema
* Datensatz
* Quell-Connector

Im Folgenden finden Sie Details, die Sie bei der Konfiguration jeder dieser Komponenten berücksichtigen sollten.

## Schema

Sie müssen ein [modellbasiertes Schema“ erstellen](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/model-based){target="_blank"} das die native Data Warehouse-Tabelle modelliert, die Sie spiegeln möchten. Stellen Sie beim Erstellen des modellbasierten Schemas sicher, dass die folgenden Anforderungen erfüllt sind:

* Wenn Sie nach dem Typ des modellbasierten Schemas gefragt werden, stellen Sie sicher, dass Sie die manuelle Option auswählen.
* Wählen Sie das entsprechende Schema für den Datentyp aus. Beachten Sie, dass Experience Platform Data Mirror hauptsächlich für Zeitreihendaten (z. B. Ereignisdaten) verwendet wird.

* Definieren der Felder in Ihrem Schema und ihrer Attribute
* Konfigurieren Sie die erforderlichen Attribute für Felder in einem modellbasierten Schema:

   * Primärschlüssel
   * Versionskennung
   * Zeitstempelkennung (für Zeitreihendaten).

## Datensatz

Sie können einen Datensatz für Ihr Schema im Voraus einrichten oder einen Datensatz erstellen, wenn Sie Ihren Quell-Connector einrichten.
Wenn Sie einen Datensatz im Voraus erstellen oder einen Datensatz auswählen, stellen Sie sicher, dass die Daten ein modellbasiertes ([) verwenden](#schema) das Sie zuvor erstellt haben.


## Quell-Connector

Um den Quell-Connector für die unterstützten nativen Data Warehouse-Lösungen einzurichten, verwenden Sie den Quell-Workflow, der Sie durch die Einrichtung führt. Dieser Workflow besteht aus den folgenden Schritten:

### Authentifizierung

Informationen zur Authentifizierung für die unterstützte Data Warehouse-native Lösung finden Sie in der entsprechenden Experience Platform-Dokumentation:

* [Azure-Datenblöcke](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/databases/snowflake)


### Daten auswählen

Nachdem Sie erfolgreich eine Verbindung zu Ihrer nativen Data Warehouse-Lösung hergestellt haben, wählen Sie die Tabelle aus der nativen Data Warehouse-Lösung aus, die Sie für die Datenspiegelung verwenden möchten. Nach der Auswahl wird eine Vorschau des Inhalts der Daten angezeigt.


### Datenflussdetails

Stellen Sie sicher, dass Sie die Änderungsdatenerfassung aktivieren. Es wird ein Informationsfenster angezeigt, in dem die Anforderungen für die Änderungsdatenerfassung erläutert werden.

Geben Sie einen neuen oder vorhandenen Datensatz an, der auf dem zuvor erstellten modellbasierten Schema basiert. Geben Sie andere Optionen in der Oberfläche Datenflussdetails an und wählen Sie sie aus.


### Zuordnen

Ordnen Sie die Felder der Tabelle in der nativen Data Warehouse-Lösung den Feldern zu, die Sie für das modellbasierte Schema angegeben haben.


### Zeitplan

Definieren Sie einen Zeitplan für die Spiegelung der Daten aus der Tabelle in der nativen Data Warehouse-Lösung in den Datensatz in Experience Platform.


### Überprüfung

Überprüfen Sie die Einstellungen für den Quell-Connector zur nativen Data Warehouse-Lösung, die die Datenspiegelung und die Datenerfassung unterstützt.


Nachdem Sie die Einrichtung des Quell-Connectors abgeschlossen haben, wird ein Datenfluss erstellt. Ab diesem Zeitpunkt werden Datenänderungen (Einfügungen, Aktualisierungen, Löschungen) in der nativen Data Warehouse-Lösung in den angegebenen Datensatz gespiegelt.


>[!MORELIKETHIS]
>
>[Data Mirror-Schnellstartanleitung: Spiegeln und Verwenden modellbasierter Daten](model-based.md)
>&#x200B;>[Data Mirror (Dokumentation zu Experience Platform)](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/data-mirror/overview)
>&#x200B;>[Modellbasierte Schemata (Dokumentation zu Experience Platform)](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/model-based)
