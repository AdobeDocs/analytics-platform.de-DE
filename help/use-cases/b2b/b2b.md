---
title: Hinzufügen von Kontodaten als Lookup-Datensatz
description: Erfahren Sie, wie Sie Kontodaten als Lookup-Datensatz zu Customer Journey Analytics hinzufügen.
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 36%

---

# Hinzufügen von Kontodaten als Lookup-Datensatz

In diesem B2B-Anwendungsfall erfahren Sie, wie Sie Kontodaten zu einer Analyse auf Personen- und Ereignisebene hinzufügen. Beim Hinzufügen von Kontodaten können Sie Fragen beantworten, z. B.:

* Welcher Unternehmensname ist diesem Konto zugehörig?
* Welche Rollen sind in diesem Konto vertreten?
* Weisen bestimmte Rollen (z. B. IT-Experten) im einen Konto ein von einem anderen Konto abweichendes Verhalten auf?

Um Kontodateninformationen hinzuzufügen, fügen Sie einen [Lookup](/help/technotes/glossary.md) -Datensatz hinzu und verwenden ihn, der diese Informationen enthält.

Folgende Schritte sind erforderlich:

1. [Erstellen Sie ein Lookup-Schema](#create-lookup-schema) im Experience Platform.
1. [Erstellen Sie einen Lookup-Datensatz](#create-lookup-dataset) in Experience Platform, mit dem Sie CSV-basierte Kontodaten erfassen können.
1. [Kombinieren von Datensätzen in einer Verbindung](#combine-datasets-in-a-connection) in Customer Journey Analytics, einschließlich des von Ihnen erstellten Lookup-Datensatzes.
1. [Erstellen Sie eine Datenansicht](#create-a-data-view-from-this-connection) im Customer Journey Analytics.
1. [Analysieren Sie diese Daten](#analyze-the-data-in-workspace) in Workspace auf Customer Journey Analytics.

>[!NOTE]
>
>Lookup-Tabellen können eine Größe von bis zu 1 GB erreichen.
>

## Suchschema erstellen

Wenn Sie ein eigenes Schema für die [Nachschlagetabelle](/help/technotes/glossary.md) erstellen, stellt dieses Schema sicher, dass der verwendete Datensatz in Customer Journey Analytics mit der richtigen Einrichtung (Datensatztyp) verfügbar ist. Es empfiehlt sich, [eine benutzerdefinierte Schemaklasse](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) zu erstellen, die für alle Suchtabellen wiederverwendet werden kann.

![Erstellen Sie das Dialogfeld &quot;Neue Klasse&quot;.](../assets/create-new-class.png)

## Suchdatensatz erstellen

Nachdem das Schema erstellt wurde, müssen Sie einen Lookup-Datensatz erstellen, der auf diesem Schema basiert, in Experience Platform. Dieser Lookup-Datensatz enthält die Kontoinformationen. Beispiel: Firmenname, Gesamtzahl der Mitarbeiter, Domänenname, Branche des Unternehmens, Jahresumsatz und mehr. Stellen Sie sicher, dass die Daten eine Personen-ID enthalten, die mit der in den Ereignisdaten verwendeten Personen-ID abgeglichen werden kann.

1. Navigieren Sie unter Experience Platform zu **[!UICONTROL Datenverwaltung > Datensätze]**.
1. Klicken Sie auf **[!UICONTROL + Datensatz erstellen]**.
1. Klicken Sie auf **[!UICONTROL Erstellen eines Datensatzes aus einem Schema]**.
1. Wählen Sie die von Ihnen erstellte Lookup-Schema-Klasse aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Benennen Sie den Datensatz (z. B. `B2B Info`) und geben Sie eine Beschreibung ein.
1. Klicken Sie auf **[!UICONTROL Fertig stellen]**.

## Daten erfassen

Anweisungen zum [Zuordnen einer CSV-Datei zu einem XDM-Schema](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) können Ihnen helfen, wenn Sie eine CSV-Datei verwenden.

[Andere Methoden](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) sind auch verfügbar.

Je nach Größe der Lookup-Tabelle dauert die Aufnahme der Daten und die Erstellung der Lookup-Verbindung zwischen 2 und 4 Stunden.

## Datensätze in einer Verbindung kombinieren

In diesem Beispiel werden 3 Datensätze zu einer Customer Journey Analytics-Verbindung kombiniert:

| Datensatzname | Beschreibung | Adobe Experience Platform-Schemaklasse | Datensatzdetails |
| --- | --- | --- | --- |
| B2B Impressions | Umfasst Clickstream-Ereignisdaten auf Kontoebene. Beispiele für den Inhalt sind die E-Mail-ID einschließlich zugehöriger Konto-ID sowie der Marketing-Name für die Ausführung von Marketing-Anzeigen enthalten. Sie enthält auch die Impressionen für diese Anzeigen pro Benutzer. | Basiert auf der XDM ExperienceEvent-Schemaklasse | Verwenden Sie `emailID` als primäre Identität und weisen Sie als Namespace `Customer ID` zu. Daher wird sie als standardmäßige **[!UICONTROL Personen-ID]** im Customer Journey Analytics angezeigt. ![Impressionen](../assets/impressions-mixins.png) |
| B2B Profile | Dieser Profildatensatz liefert nähere Informationen über die in einem Konto enthaltenen Benutzer, z. B. deren Position im Unternehmen, welchem Konto sie zugeordnet sind, ihr LinkedIn-Profil usw. | Basierend auf Schemaklasse „XDM Individual Profile“ | Wählen Sie `emailID` als primäre ID in diesem Schema aus. |
| B2B Info | Siehe &quot;Erstellen eines Lookup-Datensatzes&quot;oben. | B2B-Konto (benutzerdefinierte Lookup-Schemaklasse) | Die Beziehung zwischen `accountID` und dem Datensatz &quot;B2B Impressions&quot;wird automatisch erstellt, wenn Sie den Datensatz &quot;B2B Info&quot;mit dem Datensatz &quot;B2B Impressions&quot;in Customer Journey Analytics verbinden, wie in den folgenden Schritten beschrieben. ![Suche](../assets/lookup-mixins.png) |

Gehen Sie wie folgt vor, um die Datensätze zu kombinieren:

1. Rufen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Verbindungen]** auf.
1. Wählen Sie die Datensätze aus, die Sie kombinieren möchten.
1. Wählen Sie für den Datensatz &quot;B2B Info&quot;den Schlüssel aus, der in Ihrer Suchtabelle verwendet wird (z. B. `personKey.sourceKey`). Wählen Sie dann den entsprechenden Schlüssel (entsprechende Dimension), auch in Ihrem Ereignis-Datensatz (z. B. p`ersonKey.sourceKey`).
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Geben Sie einen Namen und eine Beschreibung für die Verbindung ein und konfigurieren Sie sie entsprechend [dieser Anweisungen](/help/connections/create-connection.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Erstellen einer Datenansicht aus dieser Verbindung

Befolgen Sie die Anweisungen unter [Erstellen von Datenansichten](/help/data-views/create-dataview.md).

* Fügen Sie alle Komponenten (Dimensionen und Metriken) hinzu, die Sie aus den Datensätzen benötigen. Stellen Sie sicher, dass Sie diese Metriken für Metriken, die für die Überzählung dedupliziert werden müssen, entsprechend konfigurieren (siehe Einstellungen der Metrik-Deduplizierungskomponente ](/help/data-views/component-settings/metric-deduplication.md)). [ Beispiele für solche Metriken sind die Anzahl der Mitarbeiter oder der Umsatz.

## Analysieren der Daten in Workspace

Sie können jetzt Workspace-Projekte auf Basis der Daten aus allen drei Datensätzen erstellen.

Diese können Ihnen beispielsweise Aufschluss über die Fragen aus der Einführung erhalten.

* Wenn Sie die emailID nach accountID aufschlüsseln, können Sie etwa feststellen, welchem Unternehmen eine E-Mail-ID zugehörig ist.
* Welche Mitarbeiter einer bestimmten Konto-ID zugeordnet sind, können Sie ebenfalls herausfinden.
* Oder auch, welcher Branche eine Konto-ID zugehörig ist?

>[!MORELIKETHIS]
>
>Weitere Informationen finden Sie unter [Ein Beispiel für ein B2B-Projekt](example.md) .

