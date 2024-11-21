---
title: Nutzung von Customer Journey Analytics anzeigen und verwalten
description: Zeigt zwei Methoden zur Schätzung der Nutzung und eine Methode zur Verwaltung.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 191d1b7a4b851e93a44487dad4794709cbbd0374
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 68%

---

# Nutzung von Customer Journey Analytics anzeigen und verwalten

Um Ihre Customer Journey Analytics-Nutzung anzuzeigen, können Sie mehrere Methoden verwenden:

* Addieren Sie die Ereignisdatenzeilen für jede Verbindung. Siehe [Schätzung der Verbindungsgröße](#estimate-connection-size) unten. Dies ist eine einfache Methode, um Ihre Ereigniszeilendaten pro Verbindung für einen bestimmten Zeitstempel anzuzeigen.

* Sie können Ihre Nutzung auf drei Arten anzeigen, von denen jede im Folgenden ausführlicher beschrieben wird:
   * Verwenden Sie Analysis Workspace, um Berichte zu den Ereignissen des letzten Monats zu erstellen.
   * Verwenden Sie Report Builder, um Berichte zu den Ereignissen des letzten Monats zu erstellen.
   * Verwenden Sie die Customer Journey Analytics-API, um einen automatisierten Bericht zu erstellen.

So verwalten Sie Ihre Customer Journey Analytics-Nutzung:

* Definieren Sie ein rollierendes Datenfenster.

## Schätzen der Verbindungsgröße {#estimate-size}

Möglicherweise benötigen Sie Informationen zur aktuellen Anzahl von Ereignisdatenzeilen in [!UICONTROL Customer Journey Analytics]. Gehen Sie **für jede der von Ihrem Unternehmen erstellten Verbindungen** wie folgt vor, um genaue Informationen zur Nutzung der Ereignisdatensätze (Datenzeilen) in Ihrem Unternehmen zu erhalten.

1. Rufen Sie in [!UICONTROL Customer Journey Analytics] den Tab **[!UICONTROL Verbindungen]** auf.

   Dadurch wird eine Liste aller Ihrer aktuellen Verbindungen angezeigt.

1. Klicken Sie auf einen Verbindungsnamen, um zum Verbindungs-Manager zu gelangen.

1. Addieren Sie die **[!UICONTROL verfügbaren Sätze von Ereignisdaten]** für jede Verbindung, die Ihr Unternehmen erstellt hat. (Je nach Größe Ihrer Verbindung kann es eine Weile dauern, bis die Anzahl angezeigt wird.)

   ![Verfügbare Aufzeichnungen von Ereignisdaten.](./assets/event-data.png)

   >[!CAUTION]
   >
   >   Diese Anzahl beinhaltet nur Ereignisdaten, nicht aber Profil- oder Lookup-Daten. Wenn Sie über Profil- und Lookup-Daten verfügen, ist die Anzahl etwas höher. Es gibt jedoch derzeit keine Möglichkeit, Berichte über die Nutzung von Profil- und Suchdaten in der Benutzeroberfläche zu erstellen.

1. Sobald Sie über die Summe aller Ereignisdatenzeilen verfügen, suchen Sie im Customer Journey Analytics-Vertrag, den Ihr Unternehmen mit Adobe unterzeichnet hat, nach der Berechtigung für „Datenzeilen“.

   Dadurch erhalten Sie die maximale Anzahl von Datenzeilen, die im Kundenauftrag genehmigt wurden. Wenn die Anzahl der Datenzeilen, die sich aus Schritt 3 ergaben, größer ist als diese Zahl, besteht eine Überschreitung des Limits.

1. Um dieses Problem zu beheben, haben Sie mehrere Möglichkeiten:

   * Ändern Sie Ihre [Datenspeicherungseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=de#set-rolling-window-for-connection-data-retention).
   * [Löschen Sie alle nicht verwendeten Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * [Löschen Sie einen Datensatz in Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * Wenden Sie sich an Ihr Adobe Account Team, um zusätzliche Kapazitäten zu lizenzieren.

## Erstellen eines Analysis Workspace-Projekts mit allen Ereignisdaten {#workspace-event-data}

Mit dieser Methode können Sie Ihre Nutzungsdaten sowie den Verlauf Ihrer Nutzung eingehender analysieren.

1. Bevor Sie ein Projekt in Analysis Workspace erstellen, [erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) für jede Ihrer Verbindungen, ohne Filter anzuwenden.

>[!WARNING]
>
>    Erstellen Sie keine neue Verbindung mit all Ihren Daten ausschließlich zum Zweck der Nutzungsmessung, da dadurch Ihre Nutzungswerte tatsächlich verdoppelt werden würden.

1. Erstellen Sie in Workspace neue Projekte auf der Basis der einzelnen Datenansichten und ziehen Sie alle Ereignisse (aus der Dropdownliste **[!UICONTROL Metriken]** ) bis zum ersten Freitag des Monats ein, beginnend mit dem ersten Tag Ihres aktuellen Customer Journey Analytics-Vertrags.

   ![ Freiformtabelle mit Ereignissen.](./assets/events-usage.png)

   Dadurch erhalten Sie eine gute Vorstellung davon, wie Ihre Nutzung von Monat zu Monat aussieht.

1. Je nach Bedarf können Sie eine Aufschlüsselung nach Datensatz durchführen usw.

## Erstellen eines Datenblocks in Report Builder {#arb}

Erstellen Sie in Report Builder für jede Datenansicht [einen Datenblock](/help/report-builder/create-a-data-block.md) und addieren Sie sie.

## Erstellen eines automatisierten Berichts in der Customer Journey Analytics-API {#api-report}

1. Verwenden Sie die [Customer Journey Analytics Reporting-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API), um einen Bericht zu allen Ereignisdaten auszuführen, **für jede Verbindung**. Richten Sie dies so ein, dass der Bericht folgendermaßen ausgeführt wird:

   * An jedem ersten Freitag eines jeden Monats
   * zurück zum ersten Tag Ihres aktuellen Customer Journey Analytics-Vertrags.

   Dadurch erhalten Sie eine gute Vorstellung davon, wie Ihre Nutzung von Monat zu Monat aussieht. Sie erhalten die Gesamtanzahl der Zeilen auf allen Ihren Customer Journey Analytics-Verbindungen.

1. Verwenden Sie Excel, um diesen Bericht weiter anzupassen.

## Verwalten der Nutzung durch Definieren eines rollierenden Datenfensters {#rolling}

Um Ihre Nutzung zu verwalten, können Sie mit der Benutzeroberfläche für [Verbindungen](/help/connections/create-connection.md) die Aufbewahrung von Customer Journey Analytics-Daten als rollierendes Fenster in Monaten (1 Monat, 3 Monate, 6 Monate usw.) auf Verbindlichkeitsebene definieren.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

Wenn Sie die Standardeinstellung unverändert, d. h. deaktiviert, lassen, wird die Aufbewahrungsdauer durch die Datenaufbewahrungseinstellung von Adobe Experience Platform ersetzt. Wenn Sie 25 Monate Daten im Experience Platform haben, erhält Customer Journey Analytics 25 Monate Daten durch Aufstockung. Wenn Sie in Platform 10 dieser Monate löschen, werden in Customer Journey Analytics die verbleibenden 15 Monate beibehalten.

Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung Profil- oder Lookup-Datensätze enthält, da sie mit Ereignis-Datensätzen verbunden sind, werden die Daten in Customer Journey Analytics basierend auf Ihren Datenaufbewahrungseinstellungen für die Ereignis-Datensatz-Zeitstempel beibehalten.

