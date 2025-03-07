---
title: Erfassen von Quantum Metric-Sitzungs-IDs in Customer Journey Analytics
description: Ändern Sie Ihre Implementierung, um Sitzungs-IDs einzuschließen, damit Sie sie in Customer Journey Analytics analysieren können.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Erfassen von Quantum Metric-Sitzungs-IDs in Customer Journey Analytics

Bei einigen Anwendungsfällen, z. B. [ von Quantum Metric](tie-session-replays.md)Sitzungswiederholungen oder [Verwenden von Quantum Metric-Heatmaps](heatmap.md) müssen Sie Ihre Implementierung ändern, um die Quantum Metric-Sitzungs-ID zu erfassen. Auf dieser Seite wird beschrieben, wie Sie diese Daten erfolgreich in Ihre vorhandene Implementierung integrieren können.

Bei diesen Schritten wird davon ausgegangen, dass Sie Tags in der Datenerfassung von Adobe Experience Platform verwenden. Wenn Ihr Unternehmen keine Tags verwendet, können Sie diese Datenerfassungsmethoden an eine manuelle Web SDK-Implementierung anpassen.

## Schritt 1: Erfassen Sie die Quantum Metric-Sitzungs-ID mithilfe der Quantum Metric Tags-Erweiterung

Führen Sie diese Schritte aus, um die Quantum Metric-Sitzungs-ID an die Daten anzuhängen, die Sie an Adobe Experience Platform senden.

1. Verwenden Sie die Quantum Metric-Erweiterung in der Tags-Benutzeroberfläche, um Daten an Quantum Metric zu senden.
1. Erstellen Sie vier Datenelemente:
   1. Eine, die die Sitzungs-ID der Quantum-Metrik aus dem Cookie von Quantum Metric mit dem Namen `QuantumMetricSessionID` erfasst
   1. Eine, die die Quantum Metric-Sitzungs-ID aus `localStorage` extrahiert. Manchmal wird dieses Datenelement schneller geladen als das Cookie, das im anderen Datenelement gesetzt ist.
   1. Verwenden Sie den Datenelement-Assistenten oder die benutzerdefinierte JavaScript, um den `s` aus dem `localStorage` Datenelement zu extrahieren.
   1. Eine, die Logik verwendet, um zunächst nach dem Cookie-Datenelement zu suchen und es an einen XDM-Objektpfad zurückzugeben, falls vorhanden. Wenn nicht definiert, versuchen Sie, das extrahierte Datenelement `localStorage` zu überprüfen.
1. Senden Sie das endgültige Quantum Metric-Sitzungs-ID-Datenelement an das XDM-Objekt, das bei jedem Ereignis gesendet wird.

>[!NOTE]
>Manchmal läuft Web SDK schneller als der Quantum-Metrik-Code. In diesen Fällen wird die Sitzungs-ID beim nachfolgenden Treffer gesendet. Wenn ein Besucher abspringt, wird die Sitzungs-ID in diesen Instanzen nicht erfasst.

Weitere Informationen finden [ in der Dokumentation ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)Quantum Metric-Tag-Erweiterung“.

## Schritt 2: Bestätigen der eingeschlossenen Datensatzfelder

Vergewissern Sie sich, dass die Datensätze in Ihrer Verbindung jetzt die Quantum Metric-Sitzungs-ID im gewünschten Datensatz haben.

## Schritt 3: Quantum Metric-Sitzungs-ID als verfügbare Dimension hinzufügen

Bearbeiten Sie die vorhandene Datenansicht, um die Sitzungs-ID als verfügbare Dimension in Customer Journey Analytics hinzuzufügen.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Datenansichten]** im oberen Menü aus.
1. Wählen Sie die gewünschte vorhandene Datenansicht aus.
1. Suchen Sie die Liste Quantum Metric Session ID Field auf der linken Seite und ziehen Sie sie in den Bereich „Dimensionen“ in der Mitte.
1. Legen Sie im rechten Bereich die Einstellung [Persistenz](/help/data-views/component-settings/persistence.md) auf „Sitzung“ fest.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Schritt 4: Konfigurieren von Workspace für die Sitzungs-ID-Dimension

Erstellen Sie eine Freiformtabelle in Workspace und konfigurieren Sie sie so, dass Sitzungs-ID-Werte direkte Links zu Quantum Metric sind.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Ziehen Sie die Dimension Sitzungs-ID auf die Workspace-Arbeitsfläche.
1. Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift der Dimension und wählen Sie **[!UICONTROL Hyperlinks für alle Dimensionselemente erstellen]** aus.
1. Wählen Sie **[!UICONTROL Benutzerdefinierte URL erstellen]** aus.
1. Fügen Sie die folgende URL-Struktur ein:

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

Jede Sitzungs-ID ist jetzt ein klickbarer Link. Diese Links führen Sie zu Quantum Metric in einer neuen Registerkarte, wo Sie diese bestimmte Sitzung detaillierter analysieren können. Weitere [ zum Hinzufügen von Hyperlinks zu Analysis Workspace-Dimensionselementen finden Sie unter ](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)Erstellen von Hyperlinks in einer Freiformtabelle“.
