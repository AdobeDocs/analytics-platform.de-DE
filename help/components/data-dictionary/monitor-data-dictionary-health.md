---
description: Administrierende sind für die Überwachung des Zustands des Datenwörterbuchs zuständig. Dazu gehört auch, ob Komponenten Daten erfassen, genehmigt worden sind, Beschreibungen enthalten und frei von Duplikaten sind.
title: Überwachen des Zustands des Datenwörterbuchs
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: b7493ad9283b5830c36b8e3ac942bf9295b693f8
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 88%

---

# Überwachen des Zustands des Datenwörterbuchs {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Datenwörterbuch"
>abstract="Wenn diese Option ausgewählt ist, wird die primäre Komponente für alle Benutzenden freigegeben, die Zugriff auf die duplizierten Komponenten haben (sowohl für die Verantwortlichen als auch für alle anderen Benutzenden, für die die Komponenten freigegeben sind). Diese Benutzenden können die primäre Komponente dann für zukünftige Projekte aus der Komponentenliste auswählen. Sie können die Komponente jedoch nicht bearbeiten, selbst wenn sie die Verantwortlichen einer duplizierten Komponente waren, die konsolidiert wurde. <br/>Diese Option ist nur verfügbar, wenn die primäre Komponente ein Segment, eine berechnete Metrik oder ein Datumsbereich ist. Metriken und Dimensionen sind stets für alle Benutzenden verfügbar.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="Primäre Komponente freigeben"
>abstract="Wenn diese Option ausgewählt ist, wird die primäre Komponente für alle Benutzenden freigegeben, die Zugriff auf die duplizierten Komponenten haben (sowohl für die Verantwortlichen als auch für alle anderen Benutzenden, für die die Komponenten freigegeben sind). Diese Benutzenden können die primäre Komponente dann für zukünftige Projekte aus der Komponentenliste auswählen. Sie können die Komponente jedoch nicht bearbeiten, selbst wenn sie die Verantwortlichen einer duplizierten Komponente waren, die konsolidiert wurde. <br/>Diese Option ist nur verfügbar, wenn die primäre Komponente ein Segment, eine berechnete Metrik oder ein Datumsbereich ist. Metriken und Dimensionen sind stets für alle Benutzenden verfügbar.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="Ersetzte Duplikate löschen"
>abstract="Wenn diese Option ausgewählt ist, stehen konsolidierte Duplikate nicht mehr zur Verwendung zur Verfügung. Deaktivieren Sie diese Option, wenn Duplikate weiterhin verfügbar sein sollen."

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics-Admins sind dafür verantwortlich, das Datenwörterbuch in einem guten Zustand zu halten.

## Eigenschaften eines Datenwörterbuchs in gutem Zustand

Ein Datenwörterbuch in gutem Zustand ist eines, in dem alle Komponenten:

* Verwendet werden und Daten erfassen

* Hilfreiche Beschreibungen enthalten, damit Benutzende wissen, wie sie am besten verwendet werden können

* Frei von unnötigen Duplikaten sind

* Vom Administrierenden genehmigt wurden

## Prüfen des Zustands des Datenwörterbuchs

So identifizieren Sie Probleme mit Ihrem Datenwörterbuch:

1. Öffnen Sie ein Projekt in Analysis Workspace.

1. Wählen Sie auf der linken Seite von Analysis Workspace das Symbol „Datenwörterbuch“ aus. (Alternative Möglichkeiten für den Zugriff auf das Datenwörterbuch sind unter „Zugriff auf das Datenwörterbuch“ in [Datenwörterbuch – Überblick](/help/components/data-dictionary/data-dictionary-overview.md) beschrieben.)

   Das Fenster „Datenwörterbuch“ wird angezeigt.

   ![Administratoransicht des Datenwörterbuchs mit Zustand des Wörterbuchs](assets/data-dictionary-admin.png)

1. Stellen Sie sicher, dass im Dropdown-Menü die richtige Datenansicht ausgewählt ist.

1. Wählen Sie auf der Registerkarte [!UICONTROL **Zustand des Wörterbuchs**] die Option [!UICONTROL **Ansicht**] neben einer der folgenden Optionen:

   * [!UICONTROL **Beschreibungen zu Komponenten fehlen**]

   * [!UICONTROL **Komponenten haben Duplikate**]

   * [!UICONTROL **Komponenten sind nicht mit Daten verbunden**]

   Je nach Auswahl wird das entsprechende Segment auf das Datenwörterbuch angewendet, und es werden nur die relevanten Komponenten angezeigt.

1. Bearbeiten Sie eine beliebige Komponente, um den Zustand des Datenwörterbuchs zu verbessern. Informationen zum Bearbeiten einer Komponente im Datenwörterbuch finden Sie unter [Bearbeiten von Komponenteneinträgen im Datenwörterbuch](/help/components/data-dictionary/edit-entries-data-dictionary.md).
