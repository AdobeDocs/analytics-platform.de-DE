---
title: Scope-Komponenteneinstellungen
description: Konfigurieren des Umfangs einer Komponente für das Reporting über die Gesamtpopulation.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
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

