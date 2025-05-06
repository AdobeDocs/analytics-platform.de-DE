---
title: Quantum Metric-Sitzungswiederholungen an Daten in Customer Journey Analytics binden
description: Quantum Metric-Sitzungswiederholungen mit CJA-Daten zum besseren Verständnis des „Warum“ hinter „dem Was“.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 2%

---

# Quantum Metric-Sitzungswiederholungen an Daten in Customer Journey Analytics binden

Durch die Verknüpfung von Quantum Metric-Sitzungswiederholungen mit CJA-Daten können Kunden das „Warum“ hinter „dem Was“ besser verstehen.  Workspace kann verwendet werden, um Sitzungen mit Reibung zu ermitteln. Anschließend können Sie auf per Hyperlink verknüpfte Sitzungs-IDs klicken, um die Sitzungswiederholung in Quantum Metric zu untersuchen.  Diese Daten ermöglichen die Anzeige des Verhaltens innerhalb einer Sitzung und ein besseres Verständnis dessen, was die Reibung der Verbraucher antreibt.  Durch Sitzungswiederholungen im Zusammenhang mit CJA können Sie wichtige Zusammenhänge im Kundenverhalten in Ihrem Erlebnis erfassen.

## Voraussetzungen

Bei diesen Schritten wird davon ausgegangen, dass Sie Tags in der Datenerfassung von Adobe Experience Platform verwenden. Wenn Ihr Unternehmen keine Tags verwendet, können Sie diese Datenerfassungsmethoden an eine manuelle Web SDK-Implementierung anpassen.

Weitere Informationen finden [ in der Dokumentation ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)Quantum Metric-Tag-Erweiterung“.

## Schritt 1: Erstellen Sie ein Schemafeld für die Quantum Metric-Sitzungs-ID

Dieser Anwendungsfall erfordert ein dediziertes Schemafeld, an das Daten gesendet werden. Sie können dieses Feld an einer beliebigen Stelle in Ihrem Schema erstellen und nach Belieben benennen. Beispielwerte werden bereitgestellt, wenn Ihr Unternehmen keine Voreinstellung für Name oder Speicherort hat.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie **[!UICONTROL Datenerfassung]** > **[!UICONTROL Schemata]**.
1. Wählen Sie das gewünschte Schema aus der Liste aus.
1. Wählen Sie das ![Feldsymbol hinzufügen](/help/assets/icons/AddCircle.svg) neben dem gewünschten Objekt aus. Beispiel: neben `Implementation Details`.
1. Geben Sie auf der rechten Seite den gewünschten [!UICONTROL Name] ein. Zum Beispiel `qmSessionId`.
1. Geben Sie den gewünschten [!UICONTROL Anzeigenamen] ein. Zum Beispiel `Quantum Metric session ID`.
1. Wählen Sie [!UICONTROL Typ] als **[!UICONTROL Zeichenfolge]**.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Schritt 2: Erfassen Sie die Quantum Metric-Sitzungs-ID mithilfe der Quantum Metric-Tag-Erweiterung

Führen Sie diese Schritte aus, um die Quantum Metric-Sitzungs-ID an die Daten anzuhängen, die Sie an Adobe Experience Platform senden.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.
1. Wählen Sie die gewünschte Tag-Eigenschaft aus.
1. Wählen Sie **[!UICONTROL Datenelemente]** und dann **[!UICONTROL Datenelement hinzufügen]** aus.
1. Stellen Sie die folgenden Einstellungen ein:
   * **[!UICONTROL Name]**: `Quantum Metric session ID`
   * **[!UICONTROL Erweiterung]**: [!UICONTROL Core]
   * **[!UICONTROL Datenelementtyp]**: [!UICONTROL Benutzerdefinierter Code]
1. Klicken Sie auf **[!UICONTROL Editor öffnen]** und fügen Sie den folgenden Code ein:

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Schritt 3: Zuordnen des Datenelements zum gewünschten XDM-Schemafeld

Nachdem das Datenelement nun über Logik zum Abrufen des gewünschten Werts verfügt, ordnen Sie das Datenelement dem XDM-Objekt zu.

1. Wählen Sie in der Tag-Eigenschaft **[!UICONTROL Datenelemente]** aus und wählen Sie dann das Datenelement aus, in dem sich Ihr XDM-Objekt befindet.
1. Navigieren Sie in der rechten Spalte dieses Datenelements zu dem Pfad, der beim Erstellen des Schemafelds festgelegt wurde.
1. Legen Sie den Wert auf den Namen des Datenelements fest, das von Prozentzeichen umgeben ist. Zum Beispiel `%Quantum Metric session ID%`.
1. Wählen Sie **[!UICONTROL Speichern]** aus.
1. Fügen Sie eine Bibliothek hinzu und veröffentlichen Sie Ihre Änderungen dann in der Produktionsumgebung.

Wenn Ihr XDM-Objekt bereits in einer Konfiguration für die Aktion „Ereignis senden“ enthalten ist, werden Ihnen bei der Veröffentlichung der Änderungen Daten angezeigt.

>[!NOTE]
>
>Manchmal läuft Web SDK schneller als der Quantum-Metrik-Code. In diesen Fällen wird die Sitzungs-ID beim nachfolgenden Treffer gesendet. Wenn ein Besucher abspringt, wird die Sitzungs-ID in diesen Instanzen nicht erfasst.

## Schritt 3: Quantum Metric-Sitzungs-ID als verfügbare Dimension hinzufügen

Sobald die oben genannten Änderungen in Ihrer Implementierung veröffentlicht wurden, bearbeiten Sie Ihre bestehende Datenansicht, um die Sitzungs-ID als verfügbare Dimension in Customer Journey Analytics hinzuzufügen.

1. Melden Sie sich bei &quot;[.adobe.com“ ](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Datenansichten]** im oberen Menü aus.
1. Wählen Sie die gewünschte vorhandene Datenansicht aus.
1. Suchen Sie das Feld Quantum Metric-Sitzungs-ID auf der linken Seite und ziehen Sie es in den Bereich „Dimensionen“ in der Mitte.
1. Legen Sie im rechten Bereich die Einstellung [Persistenz](/help/data-views/component-settings/persistence.md) auf `Session` fest.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Schritt 4: Konfigurieren von Analysis Workspace für die Sitzungs-ID-Dimension

Erstellen Sie eine Freiformtabelle in Workspace und konfigurieren Sie sie so, dass die Sitzungs-ID-Werte direkt mit der Quantum-Metrik verknüpft sind.

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

![Sitzungswiederholung](assets/session-replay.png)

## Schritt 5: Sessions aus Customer Journey Analytics anzeigen

Sobald Sie ein interessantes Segment gefunden haben, das Sie erneut durchsuchen möchten, können Sie es auf das Bedienfeld anwenden, das Ihre Sitzungs-ID-Links enthält. Die Tabelle gibt alle Sitzungen in diesem Segment zurück, und Sie können auf eine beliebige Sitzung klicken, um sie in Quantum Metric weiter zu untersuchen.

Weitere Informationen finden [ unter „Das Enterprise Guide to Session Replay](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) auf Quantum Metric. Sie können sich auch an Ihren Kundenbetreuer von Quantum Metric wenden oder eine Anfrage über das [Quantum Metric Customer Request Portal) ](https://community.quantummetric.com/s/public-support-page).
