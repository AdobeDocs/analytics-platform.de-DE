---
title: Hinzufügen von Quantum Metric-Daten zu Customer Journey Analytics
description: Verwenden Sie Quantum Metric für die Datenerfassung von Journey und Verhaltensweisen der Benutzer und nutzen Sie dann CJA aus diesen erfassten Daten, um umfassendere Einblicke zu gewinnen.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
TQID: https://experienceleague.adobe.com/LLrYpPlbagFAIeuD9TMgA3E8lrcUrMxMSWLC-8SiiIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 942cc774812d4a6b3b7f45df837ff9277e8f9b46
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 4%

---

# Hinzufügen von Quantum Metric-Daten zu Customer Journey Analytics

>[!IMPORTANT]
>
>Der Quantum Metric-Quell-Connector ist derzeit noch nicht verfügbar.

CJA ermöglicht die Steuerung der QM-Daten zur Berichtszeit, die sequenzielle Datenanalyse, die Rich-Attribution und andere erweiterte Berichte.  QM kann entweder über den QM-Quell-Connector oder die Quantum Metrics Tags-Erweiterung an AEP gesendet werden.

## Schritt 1: Quantum Metric-Quell-Connector erstellen

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie zu [!UICONTROL Experience Platform] > [!UICONTROL Verbindungen] > [!UICONTROL Quellen].
1. Fügen Sie den Quantum Metric-Quell-Connector hinzu und befolgen Sie die Anweisungen bis zum Abschluss.

Weitere Informationen finden Sie unter {[&#128279;](https://experienceleague.adobe.com/de/docs/experience-platform/sources/home)}Adobe Experience Platform-Quell-Connectoren.

## Schritt 2: Erstellen einer Verbindung in Customer Journey Analytics

Beim Erstellen eines Quell-Connectors für Quantum-Metrikdaten wird automatisch ein Datensatz in Adobe Experience Platform erstellt. Fügen Sie diesen Datensatz zu einer neuen oder vorhandenen [Verbindung](/help/connections/overview.md) in Customer Journey Analytics hinzu.

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Verbindungen]** optional unter **[!UICONTROL Daten-Management]** im oberen Menü aus.
1. Geben Sie der Verbindung einen Namen und fügen Sie den Quantum-Metrik-Datensatz zur Verbindung hinzu.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

>[!NOTE]
>Sie können Quantum Metric-Daten zwar derselben Verbindung wie die übrigen Customer Journey Analytics-Daten hinzufügen, diese Daten können jedoch ohne eine gemeinsame Personen-ID zwischen den beiden Datensätzen nicht zusammengeführt werden. Wenn dieses Verhalten erwünscht ist, empfiehlt Adobe, die [Tag-Erweiterung](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/catalog/analytics/quantum-metric) anstelle des Quell-Connectors zu verwenden.

## Schritt 3: Erstellen einer Datenansicht in Customer Journey Analytics

Erstellen Sie eine [Datenansicht](/help/data-views/data-views.md) um Dimensions- und Metrikeinstellungen zu konfigurieren.

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Datenansichten]** optional unter **[!UICONTROL Daten-Management]** im oberen Menü aus.
1. Wählen Sie die gewünschte Datenansicht aus oder erstellen Sie eine Datenansicht.
1. Suchen Sie die gewünschten Quantenmetrik -Dimensionen und -Metriken in der Liste Schemafelder auf der rechten Seite und ziehen Sie sie in den Bereich Dimensionen und Metriken in der Mitte.
1. Verwenden Sie den rechten Bereich, um jede gewünschte Dimension und Metrik zu konfigurieren.

## Schritt 4: Reporting und Analyse in Customer Journey Analytics starten

Nachdem die Daten nun in Customer Journey Analytics verfügbar sind, können Sie mit dem Reporting zu Daten beginnen.

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Ziehen Sie eine beliebige Quantenmetrikdimension oder -metrik auf die Workspace-Arbeitsfläche, um die Daten zu analysieren.
