---
title: Scope-Komponenteneinstellungen
description: Konfigurieren des Umfangs einer Komponente für das Reporting über die Gesamtpopulation.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
source-git-commit: 9df4c8cff6c0c044902453e5fb8380fbb5c5ac2d
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 19%
---

# Einstellungen zum Umfang von Komponenten {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="Anwendungsbereich"
>abstract="Legen Sie fest, in welchem Umfang eine Komponente in Berichten verwendet wird. Sie können zwischen ereignisbasiert, profilbasiert oder gesamtbasiert auswählen."

Der Umfang einer Metrikkomponente bestimmt, wie die Komponente in Berichten verwendet wird.

| Anwendungsbereich | Beschreibung |
|---|---|
| Ereignisbasiert | Der Umfang der Metrikkomponente ist ereignisbasiert. |
| Auf Profil basierend | Der Umfang der Metrikkomponente ist profilbasiert. Wenn die Komponente in Berichten verwendet wird, gibt die Metrik die Population aus Ihren Profildaten zurück, unabhängig vom auf das Bedienfeld angewendeten Datumsbereich. Datumsfilter und Datumsbereichsvergleiche wirken sich nicht auf das Reporting dieser Metrik aus. |
| Auf Gesamtwert basierend | Der Umfang der Metrikkomponente ist profil- und ereignisbasiert. Wenn die Komponente in Berichten verwendet wird, gibt die Metrik die Population aus Ihren Profil- und Ereignisdaten zurück, unabhängig vom auf das Bedienfeld angewendeten Datumsbereich. Datumsfilter und Datumsbereichsvergleiche wirken sich nicht auf das Reporting dieser Metrik aus. |

