---
title: Erfassen von Quantum Metric-Sitzungs-IDs in Customer Journey Analytics
description: Ändern Sie Ihre Implementierung, um Sitzungs-IDs einzuschließen, damit Sie sie in Customer Journey Analytics analysieren können.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: ae88ab16e85bd1274990f8c4d04771398293fe09
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Erfassen von Quantum Metric-Sitzungs-IDs in Customer Journey Analytics

Bei einigen Anwendungsfällen, z. B. [ von Quantum Metric](tie-session-replays.md)Sitzungswiederholungen oder [Verwenden von Quantum Metric-Heatmaps](heatmap.md) müssen Sie Ihre Implementierung ändern, um die Quantum Metric-Sitzungs-ID zu erfassen. Auf dieser Seite wird beschrieben, wie Sie diese Daten erfolgreich in Ihre vorhandene Implementierung integrieren können.

## Voraussetzungen:

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


