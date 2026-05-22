---
title: Überlegungen zu Data Mirror
description: Machen Sie sich mit weiteren Überlegungen vertraut, die Sie bei der Synchronisierung von Daten zwischen nativen Data Warehouse-Lösungen und Customer Journey Analytics berücksichtigen sollten.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 832
ht-degree: 1%

---

# Überlegungen zu Experience Platform Data Mirror

In diesem Artikel werden Faktoren beschrieben, die Sie beim Einrichten von Data Mirror-Datensätzen berücksichtigen sollten.

## Neue Spalte in Quelltabelle

Wenn eine neue Spalte zu einer Quelltabelle in einem CDC-fähigen gespiegelten Datensatz hinzugefügt wird, kann diese Änderung Trigger-Aktualisierungen für alle vorhandenen Zeilen bewirken. Diese Aktualisierungen werden als Änderungen über die CDC verarbeitet, die:

* Kann sich aus fortschreitender Perspektive wie eine vollständige Tabellenumschreibung verhalten.
* Kann das Aufnahmevolumen erheblich erhöhen, was dazu führen kann, dass die Aktualisierung Ihre Aufnahmeberechtigung überschreitet.

Die empfohlene Strategie für Spalten in der Quelltabelle:

* Stellen Sie sicher, dass alle relevanten Spalten anfänglich definiert sind.
* Ordnen Sie zunächst alle Spalten zu, die Sie benötigen.

Wenn Sie eine neue Spalte hinzufügen möchten, gibt es zwei Optionen, je nachdem, ob eine rückwirkende Aufstockung erforderlich ist:

* Rückwirkende Aufstockung:

   * Entfernt den aktuellen Datensatz.
   * Konfigurieren Sie den Connector erneut mit der aktualisierten Spalte.

  Dadurch wird sichergestellt, dass die Daten effizienter und schneller aufgestockt werden.

* Keine rückwirkende Aufstockung:

   * Fügen Sie die Spalte in der Quelltabelle hinzu.
   * Fügen Sie die Spalte im Zieldatensatzschema hinzu.
   * Aktualisieren Sie die Zuordnung, um das neue Feld (Spalte) aus der Quelltabelle in den Zieldatensatz einzuschließen.

Diese Strategie:

* Vermeidet kostspielige Schemaentwicklung später (Massenaktualisierungen beim Hinzufügen von Spalten).
* Das Änderungsvolumen ist vorhersehbarer als beim späteren Hinzufügen oder Ändern von Spalten.
* Hilft bei der Begrenzung potenzieller Berechnungskosten auf der Seite der externen Datenbank, da das Data Warehouse die neue Spalte möglicherweise als Aktualisierung für alle Zeilen interpretiert.


## Privacy Service

Datenschutzanfragen müssen auf die gleiche Weise verarbeitet werden wie heute bei nicht relationalen Schemata, da Datenschutzanfragen keine Rolle bei der Datenstruktur spielen.

Daten, die von einem externen relationalen Schema gespiegelt werden, werden Teil des Adobe-Ökosystems und können in diesem Ökosystem gemeinsam genutzt werden, z. B. über die Veröffentlichung von Customer Journey Analytics-Zielgruppen. Durch die Übermittlung einer Datenschutzanfrage wird sichergestellt, dass Identitäten und zugehörige Daten im gesamten Adobe-Ökosystem ordnungsgemäß verarbeitet werden.

Daher sollten Datenschutzanfragen nicht auf den gespiegelten Datensatz beschränkt sein, sondern auch Aktualisierungen der Quelldaten in der externen Datenbank umfassen.

## Hygieneverhalten

Der Hygiene-Service arbeitet mit *primären Identitäten*, aber gespiegelte Tabellen in der externen Datenbank haben *Primärschlüssel* keine primären Identitäten.

Der Unterschied zwischen Primäridentitäten und Primärschlüsseln hat zur Folge, dass Löschvorgänge im Rahmen der Hygiene nicht direkt für diese relationalen Tabellen ausgeführt werden können. Daher müssen Sie:

* Löschen Sie Daten in ihren eigenen Quelltabellen innerhalb der Data Warehouse-Lösung und stellen Sie sicher, dass die Löschvorgänge über CDC (oder die Spalte für manuelle Änderungen) laufen.
* Senden Sie Hygiene- und Datenschutzanfragen an Adobe für alle nachgelagerten XDM-basierten Datensätze mit Identitätsinformationen (z. B. Customer Journey Analytics-Ansichten, Real-Time Customer Data Platform-Datensätze, Adobe Journey Optimizer-spezifische Datensätze usw.).

Der Unterschied zwischen primärer Identität und primärem Schlüssel führt zu einem Modell der gemeinsamen Verantwortung:

* Adobe verarbeitet die Hygiene, wenn Identitäten vorhanden sind.
* Als Kunde sind Sie dafür verantwortlich, Ihre eigenen Hygieneprozesse in der Quelldatenbank mit den an Adobe gesendeten Hygieneanfragen abzustimmen.

## Governance-Unterschiede

In XDM [Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition) und zugrunde liegenden Konzepten wie [Feldergruppen](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition#field-group) propagiert ein definiertes [Feld](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition#field) innerhalb einer Feldergruppe seine Kennzeichnungen über alle Datensätze hinweg, in denen die Feldergruppe verwendet wird. Beispiel: Ein E-Mail-Feld, das in einer `identities` Feldergruppe `emailID` wird, ist für alle Datensätze, in denen die `identities` verwendet wird, gleich beschriftet.

In einem relationalen Schema ist ein Spaltenname unabhängig. Eine Spalte mit dem Namen `email` in Tabelle `customers` ist unabhängig von einer Spalte mit dem Namen `email` in einer `prospects` und unterscheidet sich von dieser Spalte. Dieses Verhalten bedeutet, dass Kennzeichnungen (wie DULE-Nutzungskennzeichnungen, Richtlinien) einzeln auf die Felder in den gespiegelten Datensätzen angewendet werden müssen. Auf der Grundlage des obigen Beispiels müssen Sie Kennzeichnungen sowohl auf das `email` Feld im `customers` Datensatz als auch auf das `email` Feld im `prospects` Datensatz anwenden.

Der Unterschied bei der Governance hat folgende Auswirkungen:

* Mehr manuelle Governance und Konfiguration arbeiten für Sie als Kunde.
* Möglicherweise benötigen Sie eine explizite Anleitung, sodass Sie nicht davon ausgehen, dass eine einmalige Kennzeichnung über Feldergruppen für eine ordnungsgemäße Governance ausreicht.

## Zuordnung

Relationale Schemata haben hinsichtlich des Zusammenfügens die folgenden Einschränkungen:

* Diagrammbasiertes Stitching wird teilweise unterstützt. Relationale Schemata können nicht für das Profil bzw. den Beitrag zum Diagramm aktiviert werden.
* Feldbasiertes Stitching wird vollständig unterstützt.


## Systemschlüssel und -felder

Die folgenden Überlegungen gelten für Systemschlüssel und -felder:

* Primärschlüssel, Versionsdeskriptor und Zeitstempeldeskriptor müssen Felder auf Stammebene im relationalen XDM-Schema sein. Verwenden Sie [Feldzuordnung](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) während der Aufnahme, um diese Anforderung zu unterstützen.
* Sie können die entsprechenden Quellfelder während der [Zuordnungsphase](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) auslassen.
