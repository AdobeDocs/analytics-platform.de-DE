---
title: Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung
description: Erfahren Sie, wie Sie den Analytics-Quell-Connector-Datensatz zur Verbindung hinzufügen.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: 0a47796a8b673ef7074a4f9fe865ff59fcf50aab
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 27%

---

# Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

## Erfahren Sie, wie der Analytics-Quell-Connector historische Daten in Customer Journey Analytics integrieren kann.

Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics-Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten im Customer Journey Analytics verwendet werden.

Bei diesem Vorgang wird davon ausgegangen, dass Sie beim Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) ein XDM-Schema erstellen möchten, da Sie ein optimiertes Schema wünschen, das auf die Anforderungen Ihres Unternehmens und die von Ihnen verwendeten spezifischen Platform-Anwendungen zugeschnitten ist.[

Um den Analytics-Quell-Connector zu verwenden, um historische Daten in Customer Journey Analytics zu importieren, müssen Sie Folgendes tun:

1. [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Wenn Sie noch keinen Analytics-Quell-Connector haben, erstellen Sie den Analytics-Quell-Connector und ordnen Sie Felder Ihrem XDM-Schema zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).[

   Oder

   Wenn Sie bereits über einen Analytics-Quell-Connector verfügen, ordnen Sie Felder vom Quell-Connector Ihrem XDM-Schema zu ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).[

1. Fügen Sie den Analytics-Quell-Connector-Datensatz zur Verbindung hinzu, wie unten beschrieben.

## Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung

Nachdem Sie [einen Analytics-Quell-Connector für historische Daten erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), wird automatisch ein Datensatz für die Analytics-Daten erstellt.

Sie müssen diesen automatisch erstellten Datensatz zu derselben Verbindung hinzufügen, die Sie für Ihre Web SDK-Implementierung erstellt haben. Dadurch werden die Analytics-Daten in die gleiche Datenansicht in Customer Journey Analytics wie Ihre Web SDK-Daten aufgenommen.

So fügen Sie den automatisch erstellten Datensatz zu derselben Verbindung hinzu, die Sie für Ihre Web SDK-Implementierung erstellt haben:

1. Rufen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Verbindungen]** auf.

1. Wählen Sie die Verbindung aus, die Sie [für Ihre Web SDK-Implementierung erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Wählen Sie **[!UICONTROL Bearbeiten]** aus.

   ![Verbindung bearbeiten](assets/connection-add-dataset.png)

1. Wählen Sie oben rechts **[!UICONTROL Datensätze hinzufügen]** aus.

   ![Verbindung bearbeiten](assets/connection-add-dateset2.png)

1. Scrollen Sie zu dem Datensatz oder suchen Sie nach dem Datensatz, der automatisch beim Erstellen des Analytics-Quell-Connectors erstellt wurde.

   Der Name dieses Datensatzes ist der Name Ihrer Report Suite, gefolgt von `midValues`. Beispiel: `My report suite midValues`

1. Aktivieren Sie das Kontrollkästchen neben dem Datensatznamen und wählen Sie dann **[!UICONTROL Weiter]** aus.

   ![Verbindung bearbeiten](assets/connection-add-dataset3.png)

1. Geben Sie die folgenden Informationen an:

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Personen-ID]** | Nur für Ereignis- und Profildatensätze verfügbar. Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity). <p>Beim Wert für die ausgewählte Personen-ID wird zwischen Groß- und Kleinschreibung unterschieden. Beispielsweise sind `abc123` und `ABC123` zwei verschiedene Werte. |
   | **[!UICONTROL Zeitstempel]** | Nur für Ereignis- und Zusammenfassungsdatensätze wird diese Einstellung automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in Experience Platform gesetzt. |
   | **[!UICONTROL Zeitzone]** | Nur für Zusammenfassungsdaten verfügbar. Wählen Sie die entsprechende Zeitzone für die Zeitreihen-Zusammenfassungsdaten aus. |
   | **[!UICONTROL Datenquellentyp]** | Wählen Sie einen Datenquellentyp aus. <br/>Hierzu gehören: <ul><li>[!UICONTROL Web-Daten]</li><li>[!UICONTROL App-Daten]</li><li>[!UICONTROL PoS-Daten]</li><li>[!UICONTROL CRM-Daten]</li><li>[!UICONTROL Umfragedaten]</li><li>[!UICONTROL Callcenter-Daten]</li><li>[!UICONTROL Produktdaten]</li><li> [!UICONTROL Kontodaten]</li><li> [!UICONTROL Transaktionsdaten]</li><li>[!UICONTROL Kunden-Feedback-Daten]</li><li> [!UICONTROL Sonstige]</li></ul>Dieses Feld wird verwendet, um sich einen Überblick über die verwendeten Datenquellen zu verschaffen. |

   {style="table-layout:auto"}

1. Lassen Sie im Abschnitt **[!UICONTROL Neue Daten importieren]** die Option **[!UICONTROL Alle neuen Daten importieren]** deaktiviert.

   Da Sie den Analytics-Quell-Connector-Datensatz für historische Daten verwenden, möchten Sie keine zukünftigen Daten in diesen Datensatz übertragen.

1. Wählen Sie im Abschnitt **[!UICONTROL Aufstockung des Datensatzes]** die Option **[!UICONTROL Aufstockung anfordern]**.

1. Definieren Sie den Zeitraum, den die Aufstockung der Verbindung in Customer Journey Analytics einschließen soll, indem Sie das Start- und Enddatum eingeben oder das Kalendersymbol ![Kalender](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) auswählen.

   Seien Sie beim Festlegen der Datumswerte, die Sie für die Aufstockung anfordern, explizit. Abhängig von mehreren Faktoren können Sie einen der folgenden Schritte ausführen:

   * Wählen Sie ein Enddatum aus, das dem Datum entspricht, an dem Sie mit der ersten Datenerfassung mit Ihrer Web SDK-Implementierung begonnen haben.

   * Wählen Sie ein Enddatum, das kurz nach dem Datum liegt, an dem Sie mit der Datenerfassung mit Ihrer Web SDK-Implementierung begonnen haben, und verwenden Sie dann Datenansichtssegmente, um die überlappenden Daten herauszufiltern.

   * Wählen Sie ein Enddatum aus, das zu einer größeren Datenüberschneidung führt, und verwenden Sie dann Datenansichtssegmente, um die überlappenden Daten herauszufiltern.

     **Hinweis:** Diese Option würde zu höheren Kosten führen, da die Verbindung mehr Zeilen enthalten würde.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Wählen Sie **[!UICONTROL Aufstockung der Warteschlange]** aus.

1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** und dann **[!UICONTROL Speichern]** aus, um die Verbindung zu speichern.

1. (Bedingt) Wenn Sie Lookup-Datensätze verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn zu Ihrer Verbindung hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

   Dies ist nur erforderlich, wenn Sie dies bei der Konfiguration Ihrer Web SDK-Implementierung noch nicht getan haben.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
