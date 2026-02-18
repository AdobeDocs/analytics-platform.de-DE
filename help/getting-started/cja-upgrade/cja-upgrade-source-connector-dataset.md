---
title: Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung
description: Erfahren Sie, wie Sie den Datensatz des Analytics-Quell-Connectors zur Verbindung hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 92%

---

# Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="Hinzufügen des Datensatzes des Analytics-Quell-Connectors zur Verbindung"
>abstract="Nachdem sich nun historische Daten aus Ihrer Analytics Report Suite in Adobe Experience Platform befinden, fügen Sie diesen Datensatz zu Ihrer bestehenden Verbindung hinzu, die Sie beim ersten Konfigurieren von Customer Journey Analytics erstellt haben. Sobald dieser Schritt abgeschlossen ist, stehen historische Daten in Customer Journey Analytics zur Verfügung.<br><br>Das Hinzufügen eines Datensatzes zu einer Verbindung in Customer Journey Analytics ist unkompliziert und dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Informationen zum Import historischer Daten in Customer Journey Analytics mit dem Analytics-Quell-Connector

Sie können den Analytics-Quell-Connector verwenden, um Adobe Analytics Report Suite-Daten in Adobe Experience Platform zu importieren. Diese Daten können dann als historische Daten in Customer Journey Analytics genutzt werden.

Bei diesem Prozess wird davon ausgegangen, dass Sie [beim Upgrade auf Customer Journey Analytics ein XDM-Schema erstellen](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), da Sie sich ein optimiertes Schema wünschen, das auf die Anforderungen Ihrer Organisation und die von Ihnen verwendeten spezifischen Platform-Anwendungen zugeschnitten ist.

Um mit dem Analytics-Quell-Connector historische Daten in Customer Journey Analytics zu importieren, ist Folgendes erforderlich:

1. [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Wenn Sie noch nicht über einen Analytics-Quell-Connector verfügen, [erstellen Sie den Analytics-Quell-Connector und ordnen Sie Ihrem XDM-Schema Felder zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Oder

   Wenn Sie bereits über einen Analytics-Quell-Connector verfügen, [ordnen Sie Ihrem XDM-Schema Felder aus dem Quell-Connector zu](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. Fügen Sie den Datensatz des Analytics-Quell-Connectors wie unten beschrieben zur Verbindung hinzu.

## Hinzufügen des Analytics-Quell-Connector-Datensatzes zur Verbindung

Nachdem Sie [einen Analytics-Quell-Connector für historische Daten erstellt](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md) haben, wird automatisch ein Datensatz für die Analytics-Daten erstellt.

Sie müssen diesen automatisch erstellten Datensatz zu derselben Verbindung hinzufügen, die Sie für Ihre Web-SDK-Implementierung erstellt haben. Dadurch werden die Analytics-Daten in Customer Journey Analytics in dieselbe Datenansicht wie die Web-SDK-Daten eingefügt.

So fügen Sie den automatisch erstellten Datensatz zu derselben Verbindung hinzu, die Sie für Ihre Web-SDK-Implementierung erstellt haben:

1. Wählen Sie in Customer Journey Analytics **[!UICONTROL Verbindungen]**, optional unter **[!UICONTROL Datenverwaltung]** im oberen Menü aus.

1. Wählen Sie die Verbindung aus, die Sie [für Ihre Web-SDK-Implementierung erstellt haben](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Wählen Sie **[!UICONTROL Bearbeiten]** aus.

   ![Verbindung bearbeiten](assets/connection-add-dataset.png)

1. Wählen oben rechts **[!UICONTROL Datensätze hinzufügen]** aus.

   ![Verbindung bearbeiten](assets/connection-add-dateset2.png)

1. Scrollen Sie zu oder suchen Sie nach dem Datensatz, der beim Erstellen des Analytics-Quell-Connectors automatisch erstellt wurde.

   Der Name dieses Datensatzes ist der Name Ihrer Report Suite, gefolgt von `midValues`. Beispiel: `My report suite midValues`

1. Wählen Sie das Kontrollkästchen neben dem Datensatznamen aus und klicken Sie dann auf **[!UICONTROL Weiter]**.

   ![Verbindung bearbeiten](assets/connection-add-dataset3.png)

1. Geben Sie die folgenden Informationen an:

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Personen-ID]** | Nur für Ereignis- und Profildatensätze verfügbar. Wählen Sie eine Personen-ID aus dem Dropdown-Menü der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity). <p>Beim Wert für die ausgewählte Personen-ID wird zwischen Groß- und Kleinschreibung unterschieden. Beispielsweise sind `abc123` und `ABC123` zwei verschiedene Werte. |
   | **[!UICONTROL Zeitstempel]** | Nur für Ereignis- und Zusammenfassungsdatensätze wird diese Einstellung automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in Experience Platform gesetzt. |
   | **[!UICONTROL Zeitzone]** | Nur für Zusammenfassungsdaten verfügbar. Wählen Sie die entsprechende Zeitzone für die Zeitreihen-Zusammenfassungsdaten aus. |
   | **[!UICONTROL Datenquellentyp]** | Wählen Sie einen Datenquellentyp aus. <br/>Hierzu gehören: <ul><li>[!UICONTROL Web-Daten]</li><li>[!UICONTROL App-Daten]</li><li>[!UICONTROL PoS-Daten]</li><li>[!UICONTROL CRM-Daten]</li><li>[!UICONTROL Umfragedaten]</li><li>[!UICONTROL Callcenter-Daten]</li><li>[!UICONTROL Produktdaten]</li><li> [!UICONTROL Kontodaten]</li><li> [!UICONTROL Transaktionsdaten]</li><li>[!UICONTROL Kunden-Feedback-Daten]</li><li> [!UICONTROL Sonstige]</li></ul>Dieses Feld wird verwendet, um sich einen Überblick über die verwendeten Datenquellen zu verschaffen. |

   {style="table-layout:auto"}

1. Lassen Sie im Abschnitt **[!UICONTROL Neue Daten importieren]** die Option **[!UICONTROL Alle neuen Daten importieren]** deaktiviert.

   Da Sie den Analytics-Quell-Connector-Datensatz für historische Daten verwenden, sollten Sie keine zukünftigen Daten einbeziehen, die in diesem Datensatz erfasst werden.

1. Wählen Sie im Abschnitt **[!UICONTROL Aufstockung des Datensatzes]** die Option **[!UICONTROL Aufstockung anfordern]** aus.

1. Definieren Sie den Zeitraum, den die Aufstockung der Verbindung in Customer Journey Analytics einschließen soll, indem Sie das Start- und Enddatum eingeben oder das Kalendersymbol ![Calendar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) auswählen.

   Seien Sie explizit beim Angeben der Daten, die Sie für die Aufstockung amfragen. Abhängig von verschiedenen Faktoren können Sie einen der folgenden Schritte ausführen:

   * Wählen Sie ein Enddatum aus, das dem Datum entspricht, an dem Sie mit der Datenerfassung mit Ihrer Web-SDK-Implementierung begonnen haben.

   * Wählen Sie ein Enddatum aus, das kurz nach dem Datum liegt, an dem Sie zum ersten Mal Daten mit Ihrer Web SDK-Implementierung erfasst haben, und segmentieren Sie dann die sich überschneidenden Daten mithilfe von Datenansichtssegmenten.

   * Wählen Sie ein Enddatum aus, das zu einer größeren Datenüberschneidung führt, und segmentieren Sie dann die sich überschneidenden Daten mithilfe von Datenansichtssegmenten.

     **Hinweis:** Diese Option würde zu höheren Kosten führen, da es mehr Zeilen in der Verbindung gäbe.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the segment. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Wählen Sie **[!UICONTROL Aufstockung in Warteschlange stellen]** aus.

1. Wählen Sie **[!UICONTROL Datensätze hinzufügen]** und dann **[!UICONTROL Speichern]** aus, um die Verbindung zu speichern.

1. (Bedingt) Wenn Sie Lookup-Datensätze verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn Ihrer Verbindung hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

   Dies ist nur erforderlich, wenn Sie dies nicht bereits bei der Konfiguration Ihrer Web-SDK-Implementierung getan haben.

{{upgrade-final-step}}
