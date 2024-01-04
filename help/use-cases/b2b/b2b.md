---
title: Hinzufügen von Daten der Kontoebene als Lookup-Datensatz
description: Erfahren Sie, wie Sie kontobasierte Daten als Lookup-Datensatz zu Customer Journey Analytics hinzufügen.
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 73%

---

# Hinzufügen von Daten der Kontoebene als Lookup-Datensatz

Dieser Anwendungsfall für den B2B-Bereich zeigt auf, wie Sie festlegen können, dass Daten für Ihre Analysen nicht auf Personenebene verwendet werden, sondern auf Kontoebene. Analysen auf Kontoebene liefern Aufschluss über folgende Fragen:

* Welcher Unternehmensname ist diesem Konto zugehörig?
* Wie viele Mitarbeiter sind diesem Konto/diesem Unternehmen zugeordnet?
* Welche Rollen sind in diesem Konto vertreten?
* Wie schneidet dieses Konto in Bezug auf die Leistung einer bestimmten Marketing-Kampagne im Vergleich zu einem anderen Konto ab?
* Weisen bestimmte Rollen (z. B. IT-Experten) im einen Konto ein von einem anderen Konto abweichendes Verhalten auf?

Sie erreichen dies, indem Sie die Informationen auf Kontoebene als [Lookup](/help/getting-started/cja-glossary.md)-Datensatz eintragen.

Erstellen Sie zunächst ein Lookup-Schema in Adobe Experience Platform und dann einen Lookup-Tabellen-Datensatz, indem Sie CSV-basierte Kontodaten aufnehmen. Anschließend erstellen Sie eine Verbindung im Customer Journey Analytics (Customer Journey Analytics), die verschiedene Datensätze kombiniert, einschließlich des von Ihnen erstellten Lookup-Datensatzes. Wenn Sie dann eine Datenansicht erstellen, können Sie letztendlich alle diese Daten in Arbeitsbereich nutzen.

>[!NOTE]
>
>Lookup-Tabellen können eine Größe von bis zu 1 GB erreichen.

## 1. Erstellen eines Lookup-Schemas (Experience Platform)

Erstellen eines eigenen Schemas für die [Nachschlagen](/help/getting-started/cja-glossary.md) -Tabelle stellt sicher, dass der verwendete Datensatz in Customer Journey Analytics mit der richtigen Einrichtung (Datensatztyp) verfügbar ist. Als Best Practice empfiehlt sich die [Erstellung einer benutzerdefinierten Schemaklasse](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de#create-new-class) mit dem Namen „Lookup“, die keinerlei Elemente enthält. Diese kann dann für alle Lookup-Tabellen wiederverwendet werden.

![Dialogfeld &quot;Neue Klasse erstellen&quot;.](../assets/create-new-class.png)

## 2. Erstellen eines Lookup-Datensatzes (Experience Platform)

Nachdem dem Erstellen des Schemas müssen Sie daraus in Experience Platform einen Lookup-Datensatz erstellen. Dieser Lookup-Datensatz enthält Marketing-Informationen auf Kontoebene, wie z. B. Firmenname, Gesamtanzahl der Mitarbeiter, Domain-Name, Branche, zu der sie gehören, Jahresumsatz, ob es sich um aktuelle Kunden der Experience Platform handelt oder nicht, in welcher Verkaufsstufe sie sich befinden, welches Team innerhalb des Kontos Customer Journey Analytics verwendet usw.

1. Rufen Sie in Adobe Experience Platform **[!UICONTROL Daten-Management > Datensätze]** auf.
1. Klicken Sie auf **[!UICONTROL + Datensatz erstellen]**.
1. Klicken Sie auf **[!UICONTROL Erstellen eines Datensatzes aus einem Schema]**.
1. Wählen Sie die von Ihnen erstellte Lookup-Schemaklasse aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Geben Sie einen Namen für den Datensatz (in unserem Beispiel „B2B Info“) sowie eine Beschreibung ein.
1. Klicken Sie auf **[!UICONTROL Fertig stellen]**.

## 3. Erfassen von Daten in Experience Platform

Anweisungen zum [Zuordnen einer CSV-Datei zu einem XDM-Schema](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=de) können Ihnen helfen, wenn Sie eine CSV-Datei verwenden.

[Andere Methoden](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) sind auch verfügbar.

Je nach Größe der Lookup-Tabelle dauert die Aufnahme der Daten und die Erstellung der Lookup-Verbindung zwischen 2 und 4 Stunden.

## 4. Kombinieren der Datensätze in einer Verbindung (Customer Journey Analytics)

In diesem Beispiel werden drei Datensätze zu einer Customer Journey Analytics-Verbindung kombiniert:

| Datensatzname | Beschreibung | Adobe Experience Platform-Schemaklasse | Datensatzdetails |
| --- | --- | --- | --- |
| B2B Impressions | Umfasst Clickstream-Ereignisdaten auf Kontoebene. Beispiele für den Inhalt sind die E-Mail-ID einschließlich zugehöriger Konto-ID sowie der Marketing-Name für die Ausführung von Marketing-Anzeigen enthalten. Ebenfalls darin enthalten sind die pro Benutzer ermittelten Impressions für diese Anzeigen. | Basierend auf Schemaklasse „XDM ExperienceEvent“ | Verwenden Sie `emailID` als primäre Identität und weisen Sie als Namespace `Customer ID` zu. Dadurch wird sie in Customer Journey Analytics als die standardmäßige **[!UICONTROL Personen-ID]** angezeigt. ![Impressionen](../assets/impressions-mixins.png) |
| B2B Profile | Dieser Profildatensatz liefert nähere Informationen über die in einem Konto enthaltenen Benutzer, z. B. deren Position im Unternehmen, welchem Konto sie zugeordnet sind, ihr LinkedIn-Profil usw. | Basierend auf Schemaklasse „XDM Individual Profile“ | Auswählen `emailID` als primäre ID in diesem Schema. |
| B2B Info | Siehe &quot;Erstellen eines Lookup-Datensatzes&quot;oben. | B2BAccount (benutzerdefinierte Schemaklasse) | Die Beziehung zwischen `accountID` und der Datensatz &quot;B2B-Impressionen&quot;automatisch erstellt wurde, indem der Datensatz &quot;B2B Info&quot;wie in den folgenden Schritten beschrieben mit dem Datensatz &quot;B2B-Impressionen&quot;in Customer Journey Analytics verbunden wurde. ![Suche](../assets/lookup-mixins.png) |

Gehen Sie wie folgt vor, um die Datensätze zu kombinieren:

1. Rufen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Verbindungen]** auf.
1. Wählen Sie die Datensätze aus, die Sie kombinieren möchten (in unserem Beispiel die drei in den Schritten oben erstellten).
1. Wählen Sie für den B2B-Info-Datensatz den Schlüssel `accountID`, der in Ihrer Suchtabelle verwendet wird. Wählen Sie dann den dazu passenden Schlüssel (der zugehörigen Dimension), also ebenfalls `accountID` aus Ihrem Ereignisdatensatz aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Geben Sie einen Namen und eine Beschreibung für die Verbindung ein und konfigurieren Sie sie entsprechend [dieser Anweisungen](/help/connections/create-connection.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

## 5. Erstellen einer Datenschicht aus dieser Verbindung

Befolgen Sie die Anweisungen zum [Erstellen von Datenansichten](/help/data-views/create-dataview.md).

* Fügen Sie alle Komponenten (d. h. Dimensionen und Metriken) hinzu, die sie aus den Datensätzen benötigen.

## 6. Analysieren der Daten in Arbeitsbereich

Sie können jetzt Arbeitsbereich-Projekte auf Basis der Daten aus allen drei Datensätzen erstellen.

Diese können Ihnen beispielsweise Aufschluss über die Fragen aus der Einführung erhalten.

* Wenn Sie die emailID nach accountID aufschlüsseln, können Sie etwa feststellen, welchem Unternehmen eine E-Mail-ID zugehörig ist.
* Welche Mitarbeiter einer bestimmten Konto-ID zugeordnet sind, können Sie ebenfalls herausfinden.
* Oder auch, welcher Branche eine Konto-ID zugehörig ist?

![project-lookup2](assets/analyze.png)
