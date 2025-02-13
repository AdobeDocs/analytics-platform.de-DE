---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 806bcaa72479c3e871e12fd1c4802bac97eda439
workflow-type: ht
source-wordcount: '702'
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Januar 2025)

**Letzte Aktualisierung:** 22. Januar 2025

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 23. Oktober 2024 bis zum 30. Januar 2025. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Das Erlebnis zur Nutzung von Verbindungen wurde aktualisiert** | Die Registerkarte **[!UICONTROL Nutzung]** unter „Verbindung“ bietet jetzt erweiterte Visualisierungen für diese Arten von berichtsfähigen Zeilen: Kern-, aufgenommene und historische Daten. Sie können die Nutzungsdaten auch nach Verbindung, Datensatz, Sandbox oder Tag anzeigen und aufschlüsseln. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | 15. Januar 2025 |
| **API zum Migrieren von Adobe Analytics-Projekten und allen enthaltenen Komponenten zu Customer Journey Analytics** | Es ist jetzt eine API für die Migration Ihrer Adobe Analytics-Projekte und enthaltenen Komponenten zu Customer Journey Analytics verfügbar. Zuvor war die Migration von Projekten und Komponenten nur über die Benutzeroberfläche verfügbar. [Weitere Infos](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs). Wählen Sie im Dropdown-Menü **APIS für CJA-Migration** aus. |  | 15. Januar 2025 |
| **Verwendung benutzerdefinierter Vorlagen aus Customer Journey Analytics auf der Seite „Berichte“ in Journey Optimizer** | Sie können jetzt die neue Berichterstellungsoberfläche in Adobe Journey Optimizer anpassen, indem Sie eine Vorlage in Customer Journey Analytics erstellen oder bearbeiten und anschließend die Vorlage speichern, die auf der Seite „Berichte“ in Journey Optimizer verwendet werden soll. Zuvor konnte die neue Berichterstellungsoberfläche in Adobe Journey Optimizer nicht angepasst werden. <p>Weitere Informationen finden Sie unter „Erstellen einer Vorlage“ oder „Bearbeiten oder Löschen einer Vorlage“ in [Erstellen und Verwalten von Vorlagen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/templates/create-templates).  |  | 15. Januar 2025 |
| **Vorlagen in Analysis Workspace** | In Customer Journey Analytics sind jetzt Vorlagen verfügbar.<ul><li>**Vorkonfigurierte Vorlagen**: Es ist eine große Auswahl vordefinierter Vorlagen verfügbar. Mithilfe dieser Vorlagen erhalten Sie schnelle Einblicke in die gängigsten Berichtsszenarien. Vorkonfigurierte Vorlagen können unverändert verwendet werden. Sie können aber auch als Ausgangspunkt für ein Projekt verwendet werden, das dann besser an einen bestimmten Zweck angepasst werden kann. [Weitere Informationen](/help/analysis-workspace/templates/use-templates.md)</li><li>**Firmenvorlagen**: Admins können Firmenvorlagen erstellen, um die Anforderungen von Anwendungsszenarien zu erfüllen, die für ihre jeweilige Organisation spezifisch sind. Von Admins erstellte Firmenvorlagen stehen Benutzenden in ihrer Organisation zur Verfügung. [Weitere Informationen](/help/analysis-workspace/templates/create-templates.md)</li></ul> | 15. Januar | 30. Januar 2025 |
| **Produktnutzung** | Erfahren Sie, wie Ihr Unternehmen Customer Journey Analytics verwendet. Durch die Aktivierung dieser Funktion wird ein Datensatz in Adobe Experience Platform erstellt, der Daten erfasst, wenn Personen in Ihrem Unternehmen Analysis Workspace verwenden. Eine Verbindung und eine Datenansicht werden ebenfalls automatisch erstellt, sodass Sie auf verschiedene Dimensionen zugreifen können, darunter die Top-Projekttypen, die aktivsten Benutzenden und die beliebtesten in Projekten verwendeten Komponenten. [Weitere Informationen](/help/tools/product-usage/usage-overview.md) | 23. Oktober 2024 | 22. Januar 2025 |
| **Intelligente Beschriftungen v2** | Intelligente Beschriftungen werden jetzt für die folgenden Visualisierungen unterstützt: Mehrzeilig, Balken, Horizontalbalken, Ringdiagramme, Fläche, Fluss und Fallout. Sie können auswählen, ob alle intelligenten Beschriftungen gleichzeitig in einer erweiterten Ansicht angezeigt werden sollen, oder Sie können einzelne intelligente Beschriftungen einzeln anzeigen. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 22. Januar 2025 |
| **Hinzufügen geführter Analysen zu Projekten von „Geführte Analyse“ aus** | Ermöglicht das Hinzufügen geführter Analysen zu Workspace-Projekten von „Geführte Analyse“ aus. Sie können geführte Analysen auch direkt in Analysis Workspace hinzufügen. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/guided-analysis/overview) |  | 22. Januar 2025 |
| **Mediensammlung: Adobe Source Connector-Aktualisierungen für neues Berichterstellungs-XDM** | Der Analytics Source Connector ordnet Streaming-Mediendaten in Adobe Analytics automatisch den Feldern zu, die vom Web SDK verwendet werden. Derzeit werden die Daten sowohl den alten als auch den neuen Speicherorten zugeordnet, in Zukunft wird jedoch nur der neue Speicherort verwendet. (Link zur Dokumentation folgt) |  | 30. Januar 2025 |

## Fehlerbehebungen in Customer Journey Analytics

Warnhinweise: AN-363263; AN-364880; AN-365029; AN-365960
Zielgruppen: AN-362564; AN-363254;
Datenaufnahme: AN-362359; AN-362751
Datenansichten: AN-362089; AN-365213; AN-365770; AN-366171; AN-366681
Abgeleitete Felder: AN-359711; AN-362496
Exportspeicherorte: AN-363999
Vollständiger Tabellenexport: AN-363055
Report Builder: AN-362937
Workspace: AN-359012; AN-359145; AN-359914; AN-361455; AN-361934; AN-362469; AN-363460; AN-364714; AN-364918; AN-366277;


## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| -/- | | |

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2024](/help/release-notes/2024.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
