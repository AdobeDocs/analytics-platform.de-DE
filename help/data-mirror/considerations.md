---
title: Überlegungen zu Data Mirror
description: Machen Sie sich mit weiteren Überlegungen vertraut, die Sie bei der Synchronisierung von Daten zwischen nativen Data Warehouse-Lösungen und Customer Journey Analytics berücksichtigen sollten.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 19351a7155eda77d1768b486c7e39dcf7cdba935
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Überlegungen zu Experience Platform Data Mirror

In diesem Artikel werden Faktoren beschrieben, die Sie beim Einrichten von Data Mirror-Datensätzen berücksichtigen sollten.

## Neue Spalte in Quelltabelle

Wenn eine neue Spalte zu einer Quelltabelle in einem CDC-fähigen gespiegelten Datensatz hinzugefügt wird, kann diese Änderung Trigger-Aktualisierungen für alle vorhandenen Zeilen bewirken. Diese Aktualisierungen werden als Änderungen über die CDC verarbeitet, die:

* Kann sich aus Kostensicht wie eine vollständige Tabellenumschreibung verhalten.
* Kann das Aufnahmevolumen erheblich erhöhen, insbesondere bei zukünftigen *(*) (Zusammenführungsvorgänge könnten beispielsweise mit höheren Sätzen belastet werden).

Die empfohlene Strategie für Spalten in der Quelltabelle:

* Stellen Sie sicher, dass die meisten, wenn nicht alle relevanten Spalten anfänglich definiert werden.
* Ordnen Sie zunächst alle Spalten zu, die Sie benötigen.

Diese Strategie:

* Vermeidet kostspielige Schemaentwicklung später (Massenaktualisierungen beim Hinzufügen von Spalten).
* Das Änderungsvolumen ist vorhersehbarer als beim späteren Hinzufügen oder Ändern von Spalten.
* Auf der Seite der externen Datenbank könnten zusätzliche Rechenkosten anfallen, da das Data Warehouse möglicherweise alle Spalten als Aktualisierungen interpretiert.

Gehen Sie wie folgt vor, um neue Spalten in externen Data Warehouse-Tabellen zu verarbeiten:

1. Erstellen Sie ein neues Schema mit der hinzugefügten Spalte.
1. Konfigurieren Sie einen neuen Quell-Connector , der die Daten einbringt.
1. Laden Sie die Aufstockung ordnungsgemäß.
1. CDC-Änderungen künftig verwenden.

Dieser Ansatz minimiert die Auswirkungen auf beiden Seiten.

## Privacy Service

Datenschutzanfragen müssen auf die gleiche Weise verarbeitet werden wie heute bei nicht relationalen Schemata, da Datenschutzanfragen keine Rolle bei der Datenstruktur spielen.

Daten, die in einem Datensatz aus externen Daten gespiegelt werden, die auf einem relationalen Schema basieren, werden Teil des Adobe-Ökosystems und können auf viele Arten freigegeben werden. Zum Beispiel durch Zielgruppenveröffentlichung.

Daher sollten Datenschutzanfragen nicht auf den gespiegelten Datensatz beschränkt sein, sondern auch Aktualisierungen der Quelldaten in der externen Datenbank umfassen.

## Hygieneverhalten

Der Hygiene-Service arbeitet mit *primären Identitäten*, aber gespiegelte Tabellen in der externen Datenbank haben *Primärschlüssel* keine primären Identitäten.

Der Unterschied zwischen Primäridentitäten und Primärschlüsseln hat zur Folge, dass Löschvorgänge im Rahmen der Hygiene nicht direkt für die relationalen Tabellen ausgeführt werden können. Daher müssen Sie:

* Löschen Sie Daten in ihren eigenen Quelltabellen innerhalb der Data Warehouse-Lösung und stellen Sie sicher, dass die Löschvorgänge über CDC (oder die Spalte für manuelle Änderungen) laufen.
* Senden Sie Hygiene- und Datenschutzanfragen an Adobe für alle nachgelagerten XDM-basierten Datensätze mit Identitätsinformationen (z. B. Customer Journey Analytics-Ansichten, Real-Time Customer Data Platform-Datensätze, Adobe Journey Optimizer-spezifische Datensätze usw.).

Der Unterschied zwischen primärer Identität und primärem Schlüssel führt zu einem Modell der gemeinsamen Verantwortung:

* Adobe verarbeitet die Hygiene, wenn Identitäten vorhanden sind.
* Als Kunde sind Sie dafür verantwortlich, Ihre eigenen Hygieneprozesse in der Quelldatenbank an die Hygieneanfragen anzupassen, die an Adobe gesendet werden.

## Governance-Unterschiede

In XDM [Schemata](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition) und zugrunde liegenden Konzepten wie [Feldergruppen](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition#field-group) propagiert ein definiertes [Feld](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition#field) innerhalb einer Feldergruppe seine Kennzeichnungen über alle Datensätze hinweg, in denen die Feldergruppe verwendet wird. Beispiel: Ein E-Mail-Feld, das in einer `identities` Feldergruppe `emailID` wird, ist für alle Datensätze, in denen die `identities` verwendet wird, gleich beschriftet.

In einem relationalen Schema ist ein Spaltenname unabhängig. Eine Spalte mit dem Namen `email` in Tabelle `customers` ist unabhängig von einer Spalte mit dem Namen `email` in einer `prospects` und unterscheidet sich von dieser Spalte. Dieses Verhalten bedeutet, dass Kennzeichnungen (wie DULE-Nutzungskennzeichnungen, Richtlinien) einzeln auf die Felder in den gespiegelten Datensätzen angewendet werden müssen. Auf der Grundlage des obigen Beispiels müssen Sie Kennzeichnungen sowohl auf das `email` Feld im `customers` Datensatz als auch auf das `email` Feld im `prospects` Datensatz anwenden.

Der Unterschied bei der Governance hat folgende Auswirkungen:

* Mehr manuelle Governance und Konfiguration arbeiten für Sie als Kunde.
* Möglicherweise benötigen Sie eine explizite Anleitung, sodass Sie nicht davon ausgehen, dass eine einmalige Kennzeichnung über Feldergruppen für eine ordnungsgemäße Governance ausreicht.
