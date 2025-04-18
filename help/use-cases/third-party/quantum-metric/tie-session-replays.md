---
title: Quantum Metric-Sitzungswiederholungen an Daten in Customer Journey Analytics binden
description: Quantum Metric-Sitzungswiederholungen mit CJA-Daten zum besseren Verständnis des „Warum“ hinter „dem Was“.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---

# Quantum Metric-Sitzungswiederholungen an Daten in Customer Journey Analytics binden

Durch die Verknüpfung von Quantum Metric-Sitzungswiederholungen mit CJA-Daten können Kunden das „Warum“ hinter „dem Was“ besser verstehen.  Workspace kann verwendet werden, um Sitzungen mit Reibung zu ermitteln. Anschließend können Sie auf per Hyperlink verknüpfte Sitzungs-IDs klicken, um die Sitzungswiederholung in Quantum Metric zu untersuchen.  Diese Daten ermöglichen die Anzeige des Verhaltens innerhalb einer Sitzung und ein besseres Verständnis dessen, was die Reibung der Verbraucher antreibt.  Durch Sitzungswiederholungen im Zusammenhang mit CJA können Sie wichtige Zusammenhänge im Kundenverhalten in Ihrem Erlebnis erfassen.

## Voraussetzungen

Bei diesen Schritten wird davon ausgegangen, dass Sie Tags in der Datenerfassung von Adobe Experience Platform verwenden. Wenn Ihr Unternehmen keine Tags verwendet, können Sie diese Datenerfassungsmethoden an eine manuelle Web SDK-Implementierung anpassen.

Weitere Informationen finden [ in der Dokumentation ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)Quantum Metric-Tag-Erweiterung“.

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

Jede Sitzungs-ID ist jetzt ein klickbarer Link. Weitere [ zum Hinzufügen von Hyperlinks zu Analysis Workspace-Dimensionselementen finden Sie unter ](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)Erstellen von Hyperlinks in einer Freiformtabelle“.

## Schritt 5: Sessions aus Customer Journey Analytics anzeigen

Nachdem Sie ein interessantes Segment gefunden haben, das Sie erneut untersuchen möchten, können Sie es auf das Bedienfeld anwenden, das Ihre Sitzungs-ID-Links enthält, und nach Segment filtern. Die Tabelle gibt alle Sitzungen in diesem Segment zurück, und Sie können auf eine beliebige Sitzung klicken, um sie in Quantum Metric weiter zu untersuchen.

Weitere Informationen finden [ unter „Das Enterprise Guide to Session Replay](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) auf Quantum Metric. Sie können sich auch an Ihren Kundenbetreuer von Quantum Metric wenden oder eine Anfrage über das [Quantum Metric Customer Request Portal) ](https://community.quantummetric.com/s/public-support-page).
