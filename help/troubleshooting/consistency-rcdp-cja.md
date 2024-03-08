---
description: Erläutert, welche Faktoren die Konsistenz von Metriken und die Anzahl der Zielgruppenzugehörigkeiten zwischen Real-time Customer Data Platform (Echtzeit-Kundendatenplattform) und Customer Journey Analytics beeinflussen.
title: Konsistenz von Metriken und Zählungen der Zielgruppenzugehörigkeit zwischen Echtzeit-Kundendatenplattform und Customer Journey Analytics
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 23%

---


# Konsistenz der Metriken und Anzahl der Zielgruppenzugehörigkeiten zwischen der Echtzeit-Kundendatenplattform und Adobe Customer Journey Analytics

In realen Szenarien kann die Konsistenz von Metriken und die Anzahl der Zielgruppenmitgliedschaften in Real-time Customer Data Platform (Echtzeit-Kundendatenplattform) und Customer Journey Analytics nicht garantiert werden. In diesem Dokument wird erläutert, warum.

Beim Vergleich der Anzahl der Zielgruppenzugehörigkeiten zwischen der Echtzeit-Kundendatenplattform und der Customer Journey Analytics ist es wichtig, die unterschiedlichen Ziele dieser beiden Tools zu beachten. Die Echtzeit-Kundendatenplattform nutzt Kundenprofildaten, um digitale Erlebnisse für einzelne Kunden auszurichten, während Customer Journey Analytics dazu dient, Benutzern dabei zu helfen, Muster in wichtigen Geschäftsmetriken und Segmenten zu verstehen. Während die Publikationsveröffentlichung von der Customer Journey Analytics in die Echtzeit-Kundendatenplattform es einem Anwender dieser Tools ermöglicht, einen Einblick einfach und nativ zu &quot;aktivieren&quot;, indem er die in der Customer Journey Analytics gewonnenen Erkenntnisse nutzt, dienen diese Tools dennoch grundlegend anderen Zwecken.

## Unterschiede in Identitätskonfigurationen

Die Echtzeit-Kundendatenplattform und die Customer Journey Analytics haben heute nicht die gleiche Definition wie eine Person. Die Real-Time CDP beruht ausschließlich auf den Informationen im [Identitätsdiagramm](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html) um ein zusammengeführtes Profil zu erstellen.

Customer Journey Analytics kann für die Verwendung konfiguriert werden [Stitching](../stitching/overview.md) , das IDs aus Datensätzen im Data Lake extrahiert und benutzerdefinierte Logik anwendet, um sie miteinander zu verknüpfen.

Künftig kann Customer Journey Analytics Identitätsdiagramme verwenden.

## Unterschiede bei der Datensatzkonfiguration

Sie können einige Daten in die Echtzeit-Kundendatenplattform aufnehmen und einige in die Customer Journey Analytics. Häufig entscheiden sich Kunden dafür, mehr historische Daten in die Customer Journey Analytics einzufügen, als für die Echtzeit-Kundendatenplattform relevant ist. Andere Datensätze können für die Echtzeit-Kundendatenplattform relevanter sein als für Customer Journey Analytics.

## Unterschiede bei der Verarbeitungskonfiguration

Customer Journey Analytics ermöglicht eine umfangreiche Datenmodifizierung zum Zeitpunkt der Abfrage, z. B. die Kombination von Feldern, die Aufteilung von Feldern und andere Manipulationen wie Ein-/Ausschlüsse, Unterzeichenfolgen, Wertdeduplizierung, Sitzungserstellung und Filterung auf Zeilenebene.

Die Real-Time CDP bietet verschiedene Tools zur Datenmanipulation. Sie verwendet [Zusammenführungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html), um zu bestimmen, welche Daten priorisiert werden und welche Daten kombiniert werden, um eine einheitliche Sicht auf eine Person zu schaffen.

## Unterschiede bei TTL (Time to Live) und Datenaufnahme

Selbst wenn die Datensätze in der Echtzeit-Kundendatenplattform und in der Customer Journey Analytics identisch sind, behält die Echtzeit-Kundendatenplattform möglicherweise nur ein sehr begrenztes Zeitfenster für die Geschichte bei. Im Gegensatz dazu verfügt Customer Journey Analytics wahrscheinlich über Daten aus Jahren. Zusätzlich:

* Customer Journey Analytics- und Echtzeit-Kundendatenplattform können benutzerdefinierte Aufbewahrungsfenster für Daten festlegen, unabhängig voneinander.

* Die Echtzeit-Kundendatenplattform und das Customer Journey Analytics haben unterschiedliche Logiken für die Aufnahme von Daten. Customer Journey Analytics ignoriert Datensätze ohne Personen-ID oder Zeitstempel und begrenzt die Anzahl der Datensätze, die ein einzelnes Profil/eine Person aufweisen kann, stark.

* Kunden der Real-Time CDP erhalten 7 Tage Zugriff auf Daten im Data Lake, um in erster Linie das Onboarding von Daten in Profile und Ad-hoc-Abfragen zu erleichtern.

* Es gibt keine TTLs für die Daten im See für Customer Journey Analytics-Kunden. Customer Journey Analytics-Benutzer können jedoch beim Erstellen einer Verbindung selbst ein benutzerdefiniertes Aufbewahrungsfenster in Customer Journey Analytics festlegen.

* Der Profilspeicher in der Real-Time CDP ermöglicht kundenkonfigurierbare TTLs. Kunden können diese TTL in diejenigen Werte ändern, die sie benötigen, um innerhalb ihrer Lizenzberechtigungen zu bleiben.

## Unterschiede in der Datenaufnahmelatenz

Customer Journey Analytics verfügt noch nicht über die Echtzeitfunktionen der Echtzeit-Kundendatenplattform. Daher beinhaltet die Customer Journey Analytics-Berichterstellung eine gewisse Latenz, bevor Daten für die Berichterstellung oder Zielgruppenerstellung verfügbar sind. Real-Time CDP verarbeitet Daten über verschiedene Systeme mit unterschiedlichen Latenzzeiten.
