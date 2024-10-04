---
description: Erläutert, welche Faktoren die Konsistenz von Metriken und die Anzahl der Zielgruppenzugehörigkeiten zwischen Real-time Customer Data Platform (Real-Time CDP) und Customer Journey Analytics beeinflussen.
title: Konsistenz von Metriken und Zielgruppenzugehörigkeit
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 97%

---


# Konsistenz von Metriken und Zielgruppenzugehörigkeit

In realen Szenarien kann die Konsistenz von Metriken und die Anzahl der Zielgruppenmitgliedschaften zwischen Real-Time Customer Data Platform (Real-Time CDP) und Customer Journey Analytics nicht garantiert werden.  In diesem Dokument wird erläutert, warum.

Beim Vergleich der Anzahl der Zielgruppenzugehörigkeiten zwischen Real-Time CDP und Customer Journey Analytics ist es wichtig, die verschiedenen Ziele dieser beiden Tools zu beachten.  Die Real-Time CDP verwendet Kundenprofildaten, um digitale Erlebnisse auf Einzelpersonen auszurichten, während Customer Journey Analytics Benutzenden dabei hilft, Muster in wichtigen Geschäftsmetriken und Segmenten zu verstehen.  Während die Veröffentlichung der Zielgruppe von Customer Journey Analytics in der Real-Time CDP denen, die diese Tools verwenden, das einfache und native „Aktivieren“ einer Erkenntnis ermöglicht, indem sie die in Customer Journey Analytics gewonnenen Erkenntnisse nutzen, dienen diese Tools dennoch grundlegend verschiedenen Zwecken.

## Unterschiede in Identitätskonfigurationen

Die Real-Time CDP und Customer Journey Analytics verwenden heutzutage nicht dieselbe Definition einer Person.  Die Real-Time CDP beruht ausschließlich auf den Informationen im [Identitätsdiagramm](https://experienceleague.adobe.com/de/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs) um ein zusammengeführtes Profil zu erstellen.

Customer Journey Analytics kann für die Verwendung von [Stitching](../stitching/overview.md) konfiguriert werden, womit IDs aus Datensätzen im Data Lake extrahiert werden und benutzerdefinierte Logik anwendet wird, um sie miteinander zu verknüpfen.

Künftig wird Customer Journey Analytics Identitätsdiagramme verwenden können.

## Unterschiede bei der Datensatzkonfiguration

Sie können einige Daten in die Real-Time CDP aufnehmen und einige in Customer Journey Analytics verwenden. Kundinnen und Kunden entscheiden sich häufig dafür, mehr historische Daten in Customer Journey Analytics einzufügen, als für die Real-Time CDP relevant ist.  Andere Datensätze sind möglicherweise eher für die Real-Time CDP relevant als für Customer Journey Analytics.

## Unterschiede bei der Verarbeitungskonfiguration

Customer Journey Analytics ermöglicht eine umfangreiche Datenmodifikation zum Zeitpunkt der Abfrage, z. B. die Kombination von Feldern, die Aufteilung von Feldern und andere Manipulationen wie Ein-/Ausschlüsse, Unterzeichenfolgen, Deduplizierung von Werten, Sitzungserstellung und Filterung auf Zeilenebene.

Die Real-Time CDP bietet verschiedene Tools zur Datenmanipulation. Sie verwendet [Zusammenführungsrichtlinien](https://experienceleague.adobe.com/de/docs/experience-platform/profile/merge-policies/overview), um zu bestimmen, welche Daten priorisiert werden und welche Daten kombiniert werden, um eine einheitliche Sicht auf eine Person zu schaffen.

## Unterschiede bei TTL (Time to Live) und Datenaufnahme

Selbst wenn die Datensätze in der Real-Time CDP und in Customer Journey Analytics identisch sind, behält die Real-Time CDP möglicherweise nur ein sehr begrenztes Zeitfenster des Verlaufs bei.  Im Gegensatz dazu verfügt Customer Journey Analytics wahrscheinlich über Daten aus mehreren Jahren.  Weitere Unterschiede:

* Kundinnen und Kunden von Customer Journey Analytics und Real-Time CDP können benutzerdefinierte Aufbewahrungsfenster für Daten festlegen, und zwar unabhängig voneinander.

* Die Real-Time CDP und Customer Journey Analytics haben unterschiedliche Logiken für die Aufnahme von Daten.  Customer Journey Analytics ignoriert Datensätze ohne Personen-ID oder Zeitstempel und begrenzt die Anzahl der Datensätze, die ein einzelnes Profil/eine einzelne Person aufweisen kann, streng.

* Kundinnen und Kunden der Real-Time CDP erhalten 7 Tage Zugriff auf Daten im Data Lake, in erster Linie mit dem Ziel, das Onboarding von Daten in Profile und Ad-hoc-Abfragen zu erleichtern.

* Für Kundinnen und Kunden von Customer Journey Analytics gibt es keine TTLs für die Daten im Data Lake. Wer Customer Journey Analytics verwendet, kann jedoch beim Erstellen einer Verbindung selbst ein benutzerdefiniertes Aufbewahrungsfenster in Customer Journey Analytics festlegen.

* Der Profilspeicher in der Real-Time CDP ermöglicht kundenkonfigurierbare TTLs. Kunden können diese TTL in diejenigen Werte ändern, die sie benötigen, um innerhalb ihrer Lizenzberechtigungen zu bleiben.

## Unterschiede in der Datenaufnahmelatenz

Customer Journey Analytics verfügt noch nicht über die Echtzeitfunktionen von Real-Time CDP. Daher unterliegt die Customer Journey Analytics-Berichterstellung einer gewissen Latenz, bevor Daten für die Berichterstellung oder Zielgruppenerstellung verfügbar sind.  Real-Time CDP verarbeitet Daten über verschiedene Systeme mit unterschiedlichen Latenzzeiten.
