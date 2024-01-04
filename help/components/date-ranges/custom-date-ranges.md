---
description: Erstellen Sie benutzerdefinierte Datumsbereiche in Analysis Workspace und speichern Sie sie als Zeitkomponenten.
keywords: Analysis Workspace
title: Erstellen von benutzerdefinierten Datumsbereichen
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 85%

---

# Erstellen von benutzerdefinierten Datumsbereichen

Erstellen Sie benutzerdefinierte Datumsbereiche in Analysis Workspace und speichern Sie sie als Zeitkomponenten.

**[!UICONTROL Komponenten]** > **[!UICONTROL Neuer Datumsbereich]**

Ein Datumsbereich wird auf der Bereichsebene angewendet. Klicken Sie, um einen Datumsbereich zu Ihrem Projekt hinzuzufügen, auf **Bedienfelder** > *`<select panel>`* und legen Sie einen neuen Datumsbereich fest.

## Datumsbereich für „Vor zwei Monaten“ 

Der folgende benutzerdefinierte Datumsbereich zeigt den Bereich vor zwei Monaten mit einer Visualisierung der Zusammenfassungsänderung, die eine Trend-Entwicklung anzeigt.

![Datumsbereich-Builder mit Rollierenden Datumswerten für den Zeitraum vor zwei Monaten](assets/date-range-two-months-ago.png)

Der benutzerdefinierte Datumsbereich wird in Ihrem Projekt oben auf dem Komponentenbereich für den [!UICONTROL Datumsbereich] angezeigt:

![Bereich der Datumsbereich-Komponente mit Pfeil, der auf vor zwei Monaten zeigt.](assets/date-range-panel-two-months-ago.png)

Sie können diesen benutzerdefinierten Datumsbereich auf eine Spalte neben einem benutzerdefinierten, monatlichen rollierenden Datumsbereich ziehen und die Voreinstellung für den letzten Monat für den Vergleich nutzen. Fügen Sie eine Visualisierung der Sammeländerung hinzu und wählen Sie die Gesamtsummen der einzelnen Spalten aus, um eine Trendentwicklung zu zeigen:

![Zusammenfassende Veränderung, die 14,45 % aufwies und stieg.](assets/date-range-two-months-table.png)

## Verwenden eines 7-Tage-Datumsbereichs

Ein Datumsbereich wird auf der Bereichsebene angewendet. Klicken Sie, um einen Datumsbereich zu Ihrem Projekt hinzuzufügen, auf **Aktionen** > **Bereich hinzufügen** und geben Sie einen neuen Datumsbereich an.

Im Datumsbereich-Builder können Sie einen benutzerdefinierten Datumsbereich erstellen, der zusammen mit anderen Datumsbereichen im Komponentenbereich angezeigt wird.

Sie können z. B. einen Datumsbereich erstellen, der ein rollierendes Zeitfenster von 7 Tagen anzeigt, das vor einer Woche endet:

![Datumsbereich-Builder mit einem Datumsbereich, der ein 7-tägiges Rollierungsfenster angibt.](assets/create_date_range.png)

Verwenden Sie *`rolling daily`*.

* Die Starteinstellung lautet *`current day minus 14 days`*.

* Die Endeinstellung lautet *`current day minus 7 days`*.

Dieser Datumsbereich kann eine Komponente sein, die Sie auf eine beliebige Freiformtabelle ziehen können.
