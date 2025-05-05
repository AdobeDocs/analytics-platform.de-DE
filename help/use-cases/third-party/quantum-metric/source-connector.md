---
title: Hinzufügen von Quantum Metric-Daten zu Customer Journey Analytics
description: Verwenden Sie Quantum Metric für die Datenerfassung von Journey und Verhaltensweisen der Benutzer und nutzen Sie dann CJA aus diesen erfassten Daten, um umfassendere Einblicke zu gewinnen.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Hinzufügen von Quantum Metric-Daten zu Customer Journey Analytics

>[!IMPORTANT]
>
>Der Quantum Metric-Quell-Connector ist derzeit noch nicht verfügbar.

CJA ermöglicht die Steuerung der QM-Daten zur Berichtszeit, die sequenzielle Datenanalyse, die Rich-Attribution und andere erweiterte Berichte.  QM kann entweder über den QM-Quell-Connector oder die Quantum Metrics Tags-Erweiterung an AEP gesendet werden.

## Schritt 1: Quantum Metric-Quell-Connector erstellen

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu [!UICONTROL Experience Platform] > [!UICONTROL Verbindungen] > [!UICONTROL Quellen].
1. Fügen Sie den Quantum Metric-Quell-Connector hinzu und befolgen Sie die Anweisungen bis zum Abschluss.

Weitere Informationen finden Sie unter {[&#128279;](https://experienceleague.adobe.com/de/docs/experience-platform/sources/home)}Adobe Experience Platform-Quell-Connectoren.

## Schritt 2: Erstellen einer Verbindung in Customer Journey Analytics

Beim Erstellen eines Quell-Connectors für Quantum-Metrikdaten wird automatisch ein Datensatz in Adobe Experience Platform erstellt. Fügen Sie diesen Datensatz zu einer neuen oder vorhandenen [Verbindung](/help/connections/overview.md) in Customer Journey Analytics hinzu.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Verbindungen]** optional unter **[!UICONTROL Daten-Management]** im oberen Menü aus.
1. Geben Sie der Verbindung einen Namen und fügen Sie den Quantum-Metrik-Datensatz zur Verbindung hinzu.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

>[!NOTE]
>Sie können Quantum Metric-Daten zwar derselben Verbindung wie die übrigen Customer Journey Analytics-Daten hinzufügen, diese Daten können jedoch ohne eine gemeinsame Personen-ID zwischen den beiden Datensätzen nicht zusammengeführt werden. Wenn dieses Verhalten erwünscht ist, empfiehlt Adobe, die [Tag-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/catalog/analytics/quantum-metric) anstelle des Quell-Connectors zu verwenden.

## Schritt 3: Erstellen einer Datenansicht in Customer Journey Analytics

Erstellen Sie eine [Datenansicht](/help/data-views/data-views.md) um Dimensions- und Metrikeinstellungen zu konfigurieren.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Datenansichten]** optional unter **[!UICONTROL Daten-Management]** im oberen Menü aus.
1. Wählen Sie die gewünschte Datenansicht aus oder erstellen Sie eine Datenansicht.
1. Suchen Sie die gewünschten Quantenmetrik -Dimensionen und -Metriken in der Liste Schemafelder auf der rechten Seite und ziehen Sie sie in den Bereich Dimensionen und Metriken in der Mitte.
1. Verwenden Sie den rechten Bereich, um jede gewünschte Dimension und Metrik zu konfigurieren.

## Schritt 4: Reporting und Analyse in Customer Journey Analytics starten

Nachdem die Daten nun in Customer Journey Analytics verfügbar sind, können Sie mit dem Reporting zu Daten beginnen.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Ziehen Sie eine beliebige Quantenmetrikdimension oder -metrik auf die Workspace-Arbeitsfläche, um die Daten zu analysieren.
