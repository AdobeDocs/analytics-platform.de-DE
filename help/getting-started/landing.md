---
description: Erläutert die Funktionen der neuen Landingpage.
title: Landingpage von Customer Journey Analytics
role: User, Admin
feature: Basics
exl-id: 65c7bc26-7160-4bba-b764-5b0fa8686fca
source-git-commit: 0fb09e9a7d23c88fb3d18f39816dfae32b131469
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 100%

---

# Landingpage von Customer Journey Analytics

Auf der Landingpage für Customer Journey Analytics finden Sie [!DNL Analysis Workspace] und eine Startseite für Projekt-Manager sowie einen Lernabschnitt, der Ihnen hilft, Customer-Journey-Daten besser zu verwalten.

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

Die Customer Journey Analytics-Landingpage besteht aus den folgenden Unterregisterkarten: „Projekte“ und „Lernen“.

**[!UICONTROL Projekte]** sind benutzerdefinierte Entwürfe, die aus Datenkomponenten, Tabellen und Visualisierungen bestehen, die von Ihnen erstellt oder einer anderen Person für Sie erstellt und freigegeben wurden. [!UICONTROL Projekte] beziehen sich auch auf leere Projekte und leere mobile Scorecards.

Die Registarkarte **[!UICONTROL Lernen]** enthält praktische Video-Touren und Tutorials sowie Links zur Dokumentation.

## Navigieren Sie zur Registerkarte [!UICONTROL Projekte] {#navigate-projects}

[!UICONTROL Projekte] fungieren als Startseite von [!UICONTROL Arbeitsbereich]. Auf der Registerkarte „Projekte“ werden der Unternehmensordner, alle von Ihnen erstellten persönlichen Ordner sowie Ihre Projekte und mobilen Scorecards angezeigt. Auf dieser Seite können Sie Ordner, Projekte und mobile Scorecards anzeigen, erstellen und ändern. Weitere Informationen finden Sie unter [Über Ordner in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

![Landing (alle)](assets/landing-all2.png)

**[!UICONTROL Projekte]** sind benutzerdefinierte Entwürfe, die Datenkomponenten, Tabellen und Visualisierungen enthalten, die von Ihnen erstellt oder die von einer anderen Person erstellt und für Sie freigegeben wurden. [!UICONTROL Projekte] beziehen sich auch auf leere Projekte und leere mobile Scorecards.

>[!NOTE]
>
>Einige der folgenden Einstellungen bleiben während der aktuellen und den nachfolgenden Sitzungen bestehen. Hierzu zählen die Registerkarte, die Filter und die Spalten, die ausgewählt wurden, sowie die Sortierrichtung der Spalte. Suchergebnisse sind nicht persistent.

### Anpassen von Tabellenspalten

Um die Spaltenbreiten anzupassen, ziehen Sie den vertikalen Balken, der die einzelnen Spalten trennt.

Um Spalten zur Projektliste hinzuzufügen oder daraus zu entfernen, klicken Sie oben rechts auf das Spaltensymbol (![Landing (alle)](assets/select-column.png)) und wählen Sie dann Spaltentitel aus bzw. entfernen Sie die Auswahl.

Die verfügbaren Spalten sind:

| Spaltenname | Beschreibung |
|---------|----------|
| [!UICONTROL **Name**] | Der Name des Projekts. |
| [!UICONTROL **Typ**] | Gibt an, ob es sich bei diesem Typ um ein Analysis Workspace-Projekt, eine mobile Scorecard oder einen Ordner handelt. |
| [!UICONTROL **Tags**] | Taggt Projekte, um sie in Gruppen einzuteilen. |
| [!UICONTROL **Geplant**] | Wählen Sie [!UICONTROL Ein], wenn ein Projekt geplant ist, oder [!UICONTROL Aus], wenn dies nicht der Fall ist. Wenn Sie auf den [!UICONTROL Ein]-Link klicken, können Sie Informationen zum geplanten Projekt anzeigen. Sie können auch [den Projektplan bearbeiten](/help/analysis-workspace/export/t-schedule-report.md), wenn Sie Projektinhaber sind. |
| [!UICONTROL **Projektrolle**] | Gibt die Projektrollen an: ob Sie Projekteigentümer sind und ob Sie berechtigt sind, das Projekt zu bearbeiten oder zu duplizieren. |
| [!UICONTROL **Report Suite**] | Gibt die Report Suites an, die mit dem Projekt verknüpft sind.<br>Tabellen und Visualisierungen innerhalb eines Bedienfelds erhalten Daten von der oben rechts im Bedienfeld ausgewählten Report Suite. Von der Report Suite hängt auch ab, welche Komponenten in der linken Leiste verfügbar sind. In einem Projekt können Sie je nach Anwendungsfällen Ihrer Analyse eine oder viele Report Suites verwenden. Die Liste der Report Suites ist nach Relevanz sortiert. Adobe definiert die Relevanz anhand der Häufigkeit der kürzlichen Verwendung der Suite durch die aktuelle Benutzerin bzw. den aktuellen Benutzer und der Häufigkeit der Verwendung der Suite innerhalb der Organisation. |
| [!UICONTROL **Inhaber**] | Die Person, die das Projekt erstellt hat. |
| [!UICONTROL **Freigegeben für**] | Zeigt an, für wen das Projekt derzeit freigegeben ist. |
| [!UICONTROL **Zuletzt geändert**] | Datum und Uhrzeit der letzten Änderung des Projekts. |
| [!UICONTROL **Zuletzt geöffnet**] | Identifiziert das Datum, an dem ein Projekt zuletzt von der Person geöffnet wurde, die sich gerade die Seite „Projekte“ ansieht. |
| [!UICONTROL **Zuletzt verwendet**] | Hilft bei der Feststellung, ob ein Projekt für Benutzende in Ihrer Organisation nützlich ist, indem der Zeitpunkt (Datum und Uhrzeit) angezeigt wird, zu dem das Projekt das letzte Mal von einer Person innerhalb der Organisation geöffnet wurde.<p>Beachten Sie Folgendes beim Anzeigen dieser Option:</p><ul><li>Nutzungsinformationen sind ab September 2023 verfügbar.</li><li>Diese Spalte steht nur Systemadmins zur Verfügung.</li></ul> |
| [!UICONTROL **Projekt-ID**] | Kann zum Debugging von Projekten verwendet werden. |
| [!UICONTROL **Längster Datumsbereich**] | Längere Datumsbereiche erhöhen die Komplexität von Projekten und können die Verarbeitungs- und Ladezeiten erhöhen. |
| [!UICONTROL **Anzahl der Abfragen**] | Die Gesamtzahl der Anfragen, die an Analytics beim Laden des Projekts gesendet wurden. Eine höhere Anzahl von Projektabfragen erhöht die Komplexität eines Projekts und somit auch die Verarbeitungs- und Ladezeiten. Diese Daten sind erst verfügbar, nachdem ein Projekt geladen oder ein geplantes Projekt gesendet wurde. |
| [!UICONTROL **Ort**] | Zeigt den Ordner an, in dem sich das Projekt befindet. |

### Andere Benutzeroberflächenelemente auf der Seite „Projekte“

| UI-Element | Definition |
| --- | --- |
| Voreinstellungen bearbeiten | Ermöglicht es Ihnen, [!UICONTROL Tutorials anzuzeigen] und [Benutzereinstellungen zu bearbeiten](/help/analysis-workspace/user-preferences.md). |
| [!UICONTROL Neu erstellen] | Öffnet das Projekt-Modal, in dem Sie ein Analysis Workspace-Projekt oder eine mobile Scorecard erstellen oder eine Unternehmensvorlage öffnen können. |
| [!UICONTROL Weniger anzeigen<br> Mehr anzeigen] | Blendet das Banner ein oder aus: ![Oberes Banner](assets/top-banner.png) |
| [!UICONTROL Analysis Workspace-Projekt] | Erstellt ein leeres [Analysis Workspace-Projekt](/help/analysis-workspace/home.md), das Sie anpassen und weiterverwenden können. |
| [!UICONTROL Mobile Scorecard] | Erstellt eine leere [mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=de), die Sie anpassen und weiterverwenden können. |
| [!UICONTROL Schulungs-Tutorial öffnen] | Öffnet das Analysis Workspace-Tutorial, das Sie Schritt für Schritt durch die Erstellung eines neuen Projekts führt. |
| [!UICONTROL Versionshinweise öffnen] | Öffnet den Abschnitt „Adobe Analytics“ der neuesten Versionshinweise zu Adobe Experience Cloud. |
| Filtersymbol | Ermöglicht das Filtern nach Tags, Report Suites, Eigentümern, Typen und anderen Kriterien („Meine“, „Für mich freigegeben“, „Favoriten“ und „Genehmigt“) |
| Suchleiste | Durchsucht alle Spalten in der Tabelle. |
| Auswahlfeld | Wählt ein oder mehrere Projekte aus, um die Projektverwaltungsaktionen anzuzeigen, die Sie ausführen können: **Löschen**, **Freigeben**, **Umbenennen**, **Kopieren**, **Loslösen**, **Nach oben**, **Nach unten**, **Taggen**, **Genehmigen**, **CSV exportieren** und **Verschieben nach**. Sie sind möglicherweise nicht berechtigt, alle aufgeführten Aktionen durchzuführen. |
| [!UICONTROL Favoriten] | Fügt neben einem Projekt oder Ordner einen Stern hinzu, der als Filter verwendet werden kann. |
| [!UICONTROL Name] | Der Name des Projekts. |
| Anheften-Symbol | Fixiert Elemente so, dass sie immer oben in der Liste angezeigt werden. Sie können die Reihenfolge aber anpassen, indem Sie Elemente nach oben oder unten verschieben. Verwenden Sie das Optionsmenü mit den Auslassungspunkten und wählen Sie in der Liste **Nach oben** oder **Nach unten** aus. |
| Infosymbol (i) | Zeigt die folgenden Informationen zu einem Projekt an: Typ, Projektrolle, Eigentümer, Beschreibung und für wen es freigegeben ist. Es zeigt auch an, wer dieses Projekt [bearbeiten oder duplizieren](/help/analysis-workspace/curate-share/share-projects.md) kann. |
| Auslassungspunkte (...) | Zeigt die Projektverwaltungsaktionen an, die Sie ausführen können: **Löschen**, **Freigeben**, **Umbenennen**, **Kopieren**, **Loslösen**, **Nach oben**, **Nach unten**, **Taggen**, **Genehmigen**, **CSV exportieren** und **Verschieben nach**. Sie sind möglicherweise nicht berechtigt, alle aufgeführten Aktionen durchzuführen. |
| ANZEIGEN: Ordner und Projekte oder alle Projekte | Ändert die Anzeigeeinstellung der Tabelle, sodass Ordner und Projekte entsprechend Ihrer Ordnerorganisation **oder** alle Projekte in einer ungeordneten Liste angezeigt werden. |
| &lt; (Schaltfläche „Zurück“) | Hiermit gelangen Sie in einem Analysis Workspace-Projekt oder einem Bericht zu Ihrer letzten Landingpage-Konfiguration zurück. Die Seitenkonfiguration, die Sie beim Verlassen der Landingpage hatten, bleibt bis zur Rückkehr erhalten. |

## Verwenden der Registerkarte „Lernen“ {#navigate-learning}

Die Seite „Lernen“ enthält praktische Video-Touren und Tutorials sowie Links zur Dokumentation.

Auf der Seite „Lernen“ in Customer Journey Analytics erfahren Sie mehr über:

* CJA-Funktionen und -Anwendungsfälle auf der Ebene für Anfängerinnen bzw. Anfänger, ein mittleres Niveau oder für Fortgeschrittene
* den nahtlosen Übergang von Adobe Analytics zu CJA

### Zugreifen auf die Seite „Lernen“

1. Wählen Sie in Customer Journey Analytics [!UICONTROL **Workspace**] > [!UICONTROL **Lernen**] aus.

### Funktionen der Seite „Lernen“

* **Inhalt filtern:** Mit dem Filtersymbol in der linken Leiste können Sie Lerninhalte nach Erlebnisebene („Anfängerinnen und Anfänger“, „Mittleres Niveau“ oder „Fortgeschrittene“) und nach Inhaltstyp („Dokument“, „Video“ oder „Touren und Tutorials“) filtern.
* **Fortschritt verfolgen:** Nachdem Sie ein Inhaltselement ausgewählt haben, wird das Tag **[!UICONTROL Angesehen]** angezeigt. Mit diesem Tag können Sie Ihren Fortschritt durch den Lerninhalt verfolgen. Sie können das Tag **[!UICONTROL Angesehen]** auswählen, um es aus einem Inhaltselement zu entfernen.
* **Zusätzliche Inhalte anzeigen:** Wählen Sie beim Anzeigen eines Videos die Schaltfläche **[!UICONTROL Weitere Informationen]** aus, um zugehörige Dokumentationsinhalte zu Experience League anzuzeigen. Wählen Sie auf der Seite „Lernen“ eine der folgenden Optionen aus, um weitere Inhalte anzuzeigen:
   * **[!UICONTROL YouTube besuchen]:** Zeigen Sie die vollständige YouTube-Wiedergabeliste von Analysis Workspace an.
   * [!UICONTROL **Experience League besuchen**]: Zeigen Sie die vollständige CJA-Dokumentation zu Experience League an.
* **Grundlagen für neue Benutzende:** Neuen Benutzenden wird die Tour [!UICONTROL Workspace-Grundlagen] empfohlen. Diese Tour führt Sie direkt zu Workspace und durch die gängigsten Aktionen. Diese Tour kann auch jederzeit in Workspace über das QuickInfo-Popup in der Kopfzeile des Bedienfelds neu gestartet werden.

## Einrichten einer Landingpage {#set-landing}

Benutzer können ihre bevorzugte Landingpage festlegen.

1. Gehen Sie zu Analytics > [!UICONTROL Komponenten] > [!UICONTROL Voreinstellungen] > [!UICONTROL Allgemein].
1. Überprüfen Sie, welche Landingpage Sie bevorzugen:

   ![Landingpage festlegen](assets/landing-pref.png)

## Häufig gestellte Fragen zu Landingpages {#landing-faq}

| Frage | Antwort |
| --- | --- |
| Wird die Arbeit, die ich in der Benutzeroberfläche des Beta-Programms verrichte, in die Produktionsumgebung des [!UICONTROL Arbeitsbereichs] übertragen? | Ja, alle in der Beta-Version durchgeführten Arbeiten werden in das alte/aktuelle [!UICONTROL Arbeitsbereich]-Erlebnis übernommen. |
| Gibt es eine maximale Anzahl von Projekten, die ich anheften kann? | Nein, es gibt keine Begrenzung für die Anzahl der Projekte, die Sie anheften können. |
| Können Administratoren diese neue Landingpage für ihre Benutzer festlegen? | Nein, Administratoren können die neue Landingpage nicht im Namen von Benutzern festlegen. Die einzelnen Benutzer müssen den Umschalter selbst aktivieren. |
<!-- | Are all reports that currently exist in [!DNL Reports & Analytics] still available? | No, the following reports were phased out, based on overall usage data: <ul><li>Any custom eVars/props/events/classifications<li>My Recommended Reports</li><li>Hourly/Daily/Weekly/Monthly/Quarterly/Yearly unique visitors</li><li>DailyWeekly/Monthly/Quarterly/Yearly unique customers</li><li>Action name depth</li><li>Action name summary</li><li>Add dashboard</li><li>Age</li><li>Audio support</li><li>Billing information</li><li>Clicks to page</li><li>Color depth</li><li>Cookie support</li><li>Cookies</li><li>Connection types</li><li>Creative elements</li><li>Credit card type</li><li>Cross sell</li><li>Custom event funnels</li><li>Custom links</li><li>Customer ID</li><li>Day of week</li><li>Entry action name</li><li>Exit action name</li><li>Exit links</li><li>Fallout</li><li>File downloads</li><li>Find in store</li><li>Full paths</li><li>Gender</li><li>Hit ype VISTA rule</li><li>Image support</li><li>Java</li><li>JavaScript</li><li>JavaScript version</li><li>Manage bookmarks</li><li>Manage dashboards</li><li>Monitor color depth</li><li>Monitor resolutions</li><li>Newsletter signups</li><li>Next action name</li><li>Next action name flow</li><li>Null searches</li><li>Operating system</li><li>Order review</li><li>Page of day</li><li>Pages not found</li><li>Pathfinder</li><li>Path length</li><li>Previous action name</li><li>Previous action name flow</li><li>Product activity</li><li>Product cost</li><li>Product department</li><li>Product inventory category</li><li>Product name</li><li>Product reviews</li><li>Product season</li><li>Product shares</li><li>Product zooms</li><li>Reload</li><li>Searches</li><li>Servers</li><li>Single page visits</li><li>Shipping information</li><li>Site hierarchy</li><li>Social mentions</li><li>Time of day</li><li>Time spent on action name</li><li>Video support</li><li>Visitor state</li></ul> | -->
