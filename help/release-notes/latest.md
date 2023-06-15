---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13ea4060bd5ca0a4b5b749b6e104edea26248a02
workflow-type: tm+mt
source-wordcount: '1283'
ht-degree: 61%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (Juni 2023)

**Letzte Aktualisierung**: 15. Juni 2023

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Die Highlights der Version {#highlights}

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligente Beschriftungen** | Anreicherung des Geschichtenerzählens für Benutzer mit natürlichen Sprachzusammenfassungen eines [!UICONTROL Linie] Visualisierung. [Weitere Informationen](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17. Mai 2023 | 1. Juni 2023 |
| **Link-Freigabe für Projekte (keine Anmeldung erforderlich)** | Sie können jetzt schreibgeschützte Links zu Analysis Workspace-Projekten für Personen freigeben, die keinen Zugriff auf Adobe Analytics haben. Sie können Dinge mit Personen außerhalb Ihrer Organisation oder mit Personen innerhalb Ihrer Organisation teilen, die nicht für Adobe Analytics vorgesehen sind. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=de#share-public-link) <p>Diese Funktion ist standardmäßig aktiviert und kann von Systemadmins deaktiviert werden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=de#company-preferences)</p> | 3. Mai 2023 | 6. Juni 2023 |
| **Abgeleitete Felder** | Dies stellt die erste Version abgeleiteter Felder dar. Mit einem abgeleiteten Feld können Sie mithilfe eines anpassbaren Regel-Builders spontan (häufig komplexe) Datenmanipulationen definieren. Sie können das abgeleitete Feld als Komponente (Metrik oder Dimension) in Datenansichten weiter definieren und dann das abgeleitete Feld als Komponente in Workspace verwenden.<p>Diese Version unterstützt eine Vorlage für Marketing-Kanäle und die folgenden Funktionen:</p><ul><li>Verketten</li><li>Fall wenn</li><li>Suchen und Ersetzen</li><li>Nachschlagen</li><li>URL-Parsen</li></ul> <p>[Weitere Informationen](/help/data-views/derived-fields/derived-fields.md)</p> | 10. Mai 2023 | 14. Juni 2023 |
| **Zugriff von PowerBI und Tableau auf CJA-Datenansichten** | Der SQL Connector Customer Journey Analytics (CJA) ermöglicht SQL-Zugriff auf Datenansichten, die Sie in CJA definiert haben. Data Engineers und Analysten, die mit Power BI, Tableau oder anderen Tools für Business Intelligence und Visualisierung vertraut sind, können jetzt Berichte und Dashboards auf der Basis derselben Datenansichten erstellen, die CJA-Benutzer für ihre Analysis Workspace-Projekte verwenden. [Weitere Informationen](/help/data-views/sql-connector.md) |  | 30. Juni 2023 |
| **Experience Edge-Geo-Suche** | Sie können Berichte mit Geolocation-Daten in CJA erstellen, sobald die Experience Edge Geo Lookups für Ihren Datastream aktiviert sind. |  | 30. Juni 2023 |
| **Erweiterte Suchunterstützung für Profil- und Suchdaten** | Sie können Lookup-Datensätze nicht nur zu Ereignis-Datensätzen, sondern auch zu Profil- und Lookup-Datensätzen hinzufügen. | 21. Juni 2023 | 12. Juli 2023 |
| **Unterstützung für Währungskonversionen** | Die Währungsumrechnung wird im Rahmen der Formatierung einer Metrikkomponente in einer Datenansicht unterstützt. [Weitere Informationen](../data-views/component-settings/format.md#currency) | 7. Juni 2023 | 21. Juni 2023 |

{style="table-layout:auto"}

## Weitere neue Funktionen und Updates {#other-new}

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer-Datenansichten** | CJA-Administratoren haben Zugriff auf einige zusätzliche Datenansichten in CJA mit dem Titel &quot;AJO-Datenansicht (Sandbox-Name)&quot;. Diese Datenansichten werden verwendet, um die Berichte in Adobe Journey Optimizer (AJO) zu optimieren. Sie können auch verwendet werden, um eine tiefere Analyse von AJO-Aktivitäten in CJA durchzuführen. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). | | 25. Mai 2023 |
| **Aufstockung für Nicht-Produktions-Sandboxes** | Beim Erstellen eines Analytics Source Connector-Datenflusses in einer Nicht-Produktions-Sandbox ist die Aufstockung in Nicht-Produktions-Sandboxes auf 3 Monate beschränkt. Für Produktions-Sandboxes bleibt sie bei 13 Monaten. | Nicht angegeben | 26. April 2023 |
| **Link-Freigabe für Projekte (keine Anmeldung erforderlich)** | Sie können jetzt schreibgeschützte Links zu Analysis Workspace-Projekten für Personen freigeben, die keinen Zugriff auf Adobe Analytics haben. Sie können Dinge mit Personen außerhalb Ihrer Organisation oder mit Personen innerhalb Ihrer Organisation teilen, die nicht für Adobe Analytics vorgesehen sind. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=de#share-public-link) <p>Diese Funktion ist standardmäßig aktiviert und kann von Systemadmins deaktiviert werden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3. Mai 2023 | 6. Juni 2023 |
| **Aktualisierter Startbildschirm für die Analytics-Dashboards-App (Mobile App)** | Mit dem neuen aktualisierten Startbildschirm können Sie alle Ihre Scorecards in einer konsolidierten Scorecard-Liste anzeigen.  Wenn Sie unter einer Anmeldung Zugriff auf mehr als eine Organisation haben, stehen alle Scorecards Ihrer Organisation in einer einzigen Liste zur Verfügung. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | Nicht angegeben | 10. Mai 2023 |
| **Report Builder für CJA – Datenansicht aus Zelle auswählen** | Mit dieser Funktion können Benutzerinnen oder Benutzer die Datenansicht für einen Datenblock aus einer Zelle auswählen. Dies ist hilfreich, wenn Sie eine Arbeitsmappe erstellen und mehrere Datenansichten haben, die eine ähnliche Datenerstellung aufweisen, und eine Arbeitsmappe mehrmals mit verschiedenen Datenansichten wiederverwenden möchten. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=de) | Nicht angegeben | 24. Mai 2023 |
| **Aktualisierte Lernseite für CJA** | Der Tab Lernen auf der Landingpage für Customer Journey Analytics enthält jetzt CJA-spezifische Inhalte, einschließlich Inhalt, der auf die Umstellung von Adobe Analytics auf CJA ausgerichtet ist.<p>Die folgenden zusätzlichen Verbesserungen sind auch auf der Registerkarte Lernen verfügbar:</p><ul><li>Verbessertes Design, das mehr Lerninhalte auf einer Seite mit verbesserter Navigation anzeigt</li><li>Möglichkeit zur Personalisierung von Lerninhalten nach Erlebnisebene (Einstieg, Fortgeschrittene und Fortgeschrittene)</li></ul><p>Zuvor enthielt die Registerkarte &quot;Lernen&quot;in CJA identische Informationen wie die Registerkarte &quot;Lernen&quot;in Adobe Analytics.</p> [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | Nicht angegeben | 30. Juni 2023 |
| **Sortieren von Komponenten in Analysis Workspace** | <p>Bei der Anzeige von Komponenten in der linken Leiste oder im Datenwörterbuch in Analysis Workspace ist jetzt eine neue Sortieroption verfügbar. Sie können Komponenten nach „Empfohlen“ (die am häufigsten verwendeten), „Alphabetisch“ oder „Kategorie“ (Typ) sortieren.</p><p>Zuvor war es nur möglich, Komponenten zu suchen oder zu filtern. [Weitere Informationen](/help/components/overview.md)</p> | Nicht angegeben | 7. Juni 2023 |
| **Löschen von Zeilen, die dynamische Dimensionen enthalten, aus einer Freiformtabelle** | In einer Freiformtabelle in Analysis Workspace können Sie jetzt mithilfe des Symbols „x“ schnell bestimmte Zeilen löschen, die dynamische Dimensionen enthalten. Dabei wird automatisch die Filterregel &quot;Elemente immer ausschließen&quot;angewendet.<p>Zuvor bestand die einzige Möglichkeit zum Löschen von Zeilen, die dynamische Dimensionen enthielten, darin, manuell eine Regel im Filterdialogfeld zu erstellen. [Weitere Informationen](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | Nicht angegeben | 17. Mai 2023 |
| **Neue Schaltfläche zum Hinzufügen einer Visualisierung in einem Bedienfeld** | Unten in jedem Bedienfeld in Analysis Workspace ist jetzt eine neue Schaltfläche verfügbar, mit der Sie schnell eine Visualisierung hinzufügen können. <p>Zuvor bestand die einzige Methode zum Hinzufügen einer Visualisierung zu einem Bedienfeld darin, eine Visualisierung aus der linken Leiste zu ziehen, eine vorhandene Visualisierung zu duplizieren oder zu kopieren oder ein leeres Bedienfeld zu erstellen. [Weitere Informationen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | Nicht angegeben | 17. Mai 2023 |
| **Deep-Linking (Mobile App)** | Ermöglicht Benutzerinnen und Benutzern das Senden von Links zu Scorecards, die sie direkt zum Scorecard-Projekt in der App führen. Dies erleichtert die Freigabe von Projekten und eine stärkere Interaktion mit weniger technischen Zielgruppen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | Nicht angegeben | 17. Mai 2023 |
| **Intelligente Beschriftungen** | Anreicherung des Geschichtenerzählens für Benutzer mit natürlichen Sprachzusammenfassungen eines [!UICONTROL Linie] Visualisierung. [Weitere Informationen](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17. Mai 2023 | 1. Juni 2023 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-318343; AN-319453

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| Nicht angegeben | nicht angegeben | Nicht angegeben |

## Mitteilungen über das Ende der Nutzungsdauer (EOL) {#eol}

| Ende der Nutzungsdauer eines Produkts oder einer Funktion | Datum hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Migration zu Adobe IO OAuth Server-zu-Server-Anmeldeinformationen** | 11. Mai 2023 | Adobe Analytics-API-, CJA-API- und Livestream-Kunden, die Adobe IO JWT-Anmeldeinformationen verwenden, müssen mithilfe von **1. Januar 2025**. Adobe IO lässt die Erstellung neuer JWT-Anmeldeinformationen ab dem 1. Mai 2024 nicht zu. Kunden, die JWT verwenden, müssen eine neue OAuth-Server-zu-Server-Berechtigung erstellen oder ihre vorhandenen JWT-Anmeldedaten in eine OAuth-Server-zu-Server-Berechtigung migrieren. Kunden müssen außerdem ihre Clientanwendungen aktualisieren, um die neuen OAuth Server-to-Server-Anmeldeinformationen zu verwenden. <ul><li>[Migration von JWT-Anmeldedaten (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Verwenden der neuen OAuth-Server-zu-Server-Anmeldeinformationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Häufig gestellte Fragen (FAQ)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
