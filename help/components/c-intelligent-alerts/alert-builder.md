---
description: Lassen Sie sich Warnhinweise anzeigen, wenn Projektkomponenten bestimmte Schwellenwerte erreichen.
title: Erstellen von Warnhinweisen
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: a757ea4fc9bf8b13a8ce3001cf8639245d213e1c
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 21%

---

# Erstellen von Warnhinweisen {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_alerts_timegranularity"
>title="Zeitgranularität"
>abstract="Zeitgranularität bezieht sich sowohl darauf, wie oft der Warnhinweis überprüft wird, als auch darauf, was eingeschlossen wird"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Die Verwendung von Warnhinweisen mit Anomalieerkennung (auch _intelligente Warnhinweise_ genannt) ist nur für Unternehmen mit einem Customer Journey Analytics Prime- oder Ultimate-Paket verfügbar.

Warnhinweise in Customer Journey Analytics ermöglichen die Benachrichtigung anhand geänderter Prozentsätze oder bestimmter Datenpunkte. Je nach Customer Journey Analytics-Paket können Sie auch Warnhinweise verwenden, die auf der Grundlage von Anomalie-Schwellenwerten ausgelöst werden.

Weitere Übersichtsinformationen zu Warnhinweisen finden Sie unter [Warnhinweise - Übersicht](/help/components/c-intelligent-alerts/intelligent-alerts.md).

So erstellen Sie einen Warnhinweis:

1. Wählen Sie <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> in Customer Journey Analytics **[!UICONTROL Komponenten]** > **[!UICONTROL Warnhinweise]** aus. Wählen [Warnhinweis-Manager](alert-manager.md) die Option ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Hinzufügen]**, um einen neuen Warnhinweis zu erstellen, oder wählen Sie einen der aufgelisteten Warnhinweise aus, um einen vorhandenen Warnhinweis zu ändern.

   Die [Warnhinweiserstellung](#alert-builder) wird angezeigt.

1. Wählen Sie **[!UICONTROL Speichern]**, um den Warnhinweis zu speichern. Wählen **[!UICONTROL Speichern unter]**, um eine Kopie des Warnhinweises zu speichern.


## Warnhinweiserstellung

Die Benutzeroberfläche der Warnhinweiserstellung ist denjenigen bekannt, die Filter oder berechnete Metriken im Customer Journey Analytics erstellt haben:

![](assets/alert-builder.png)

Geben Sie die folgenden Details in der Warnhinweiserstellung für einen Warnhinweis an:

| Element | Beschreibung |
|---------|----------|
| **[!UICONTROL Titel]** | Geben Sie einen Namen für den Warnhinweis an. Der Warnhinweisname könnte den Namen des Berichts oder den Schwellenwert einer Metrik enthalten. |
| **[!UICONTROL Beschreibung (optional)]** | Geben Sie eine Beschreibung für den Warnhinweis an. |
| **[!UICONTROL Zeitgranularität]** | Wählen Sie aus, wie oft die Metrik überprüft werden soll: täglich, wöchentlich oder monatlich.<p><b>Hinweis</b>Für Datenansichten mit einem benutzerdefinierten Kalender wird die monatliche Granularität im Warnhinweiserstellung nicht unterstützt.<!--true?--></p> |
| **[!UICONTROL Empfänger]** | Geben Sie an, wo der Warnhinweis hingeschickt werden soll. Ein Warnhinweis kann an einen Analyse-Benutzer, eine Analyse-Gruppe, eine E-Mail-Adresse oder eine Telefonnummer gesendet werden.<p><b>Wichtig:</b>Vor der Telefonnummer müssen ein &quot;+&quot; und eine [Ländercode“ angegeben ](https://countrycode.org/).</p><p>Die E-Mail, die ein Benutzer erhält, nachdem ein Warnhinweis ausgelöst wurde, sieht in etwa wie folgt aus:</p><p>![Warnungs-E-Mail](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Ablaufdatum]** | Datum und Uhrzeit festlegen, zu der der Warnhinweis ablaufen soll. |
| **[!UICONTROL Verzögerung]** | Die Zeit, die erforderlich ist, bevor die Daten abgeschlossen sind und für die Meldung im Customer Journey Analytics zur Verfügung stehen, variiert je nach Unternehmen und liegt in der Regel zwischen 3 und 9 Stunden nach der Datenereigniszeit. Damit Warnhinweise genau sind, müssen Ereignisdaten für einen bestimmten Ereignisbereich vollständig sein. Das bedeutet, dass Adobe für den angegebenen Ereignisbereich keine Ereignisdaten mehr erhält.<p>Um diese Verzögerung bei der Aufnahmezeit zu berücksichtigen, haben Warnhinweise standardmäßig eine Verzögerung von 9 Stunden, bevor sie gesendet werden.</p><p>Sie können die Standardverzögerung von 9 Stunden auf einen Wert zwischen 0 und 24 Stunden anpassen. Wenn Sie die Verzögerung jedoch auf unter 9 Stunden verkürzen, kann dies bedeuten, dass Sie unvollständige Daten melden, was zu ungenauen Warnhinweisinformationen führt.</p><p>Beachten Sie beim Verringern der Verzögerungszeit Folgendes:</p><ul><li>**Datenverfügbarkeit im Vergleich zur Datenvollständigkeit verstehen**: Während einige Daten möglicherweise früher für Berichte verfügbar sind, werden alle Batch-Daten erst nach einem Zeitraum von 3 bis 9 Stunden in einen Platform-Datensatz aufgenommen. Damit Warnhinweise korrekt sind, muss die Datenaufnahme vollständig sein, wobei alle Batch-Daten im Datensatz verfügbar sein müssen.</li><li>**Bestimmen Sie, wie lange es dauert, bis Ihre Daten vollständig und im Datensatz verfügbar sind**: Die Datenaufnahmezeiten variieren je nach Organisation. Stellen Sie sicher, dass die von Ihnen gewählte Verzögerungszeit für die Bereitstellung von Warnhinweisen dieselbe oder kürzer ist als die Zeit, die benötigt wird, bis die Batch-Daten im Platform-Datensatz verfügbar sind<!--add link? -->.</li><p>**Tipp:** Die genaueste Methode, um zu ermitteln, wie viel Zeit erforderlich ist, damit alle Batch-Daten vollständig und in den Platform-Datensatz aufgenommen werden, besteht darin, die Dateningenieure in Ihrem Unternehmen zu konsultieren.</p><p>Alternativ können Sie sich einen Überblick darüber verschaffen, wie lange es dauert, bis der Batch-Versand in Ihrer Organisation im Platform-Datensatz verfügbar ist, indem Sie die folgende Freiformtabelle in Analysis Workspace erstellen:</p><ol><li>Fügen Sie in einer Freiformtabelle in Analysis Workspace eine Metrik [!UICONTROL **Ereignisse**] und eine Dimension [!UICONTROL **Tag**] hinzu.</li><li>Schlüsseln Sie die Dimension [!UICONTROL **Tag**] mithilfe einer Dimension [!UICONTROL **Stunden**] auf.<p>Stunden ohne Daten werden als 0 angezeigt.</p></li></ol><li>**Berücksichtigung von Fehlern in Ihren Berechnungen**: Wenn Sie die standardmäßige Verzögerungszeit verringern, empfehlen wir, die Verzögerung für mindestens eine Stunde länger zu konfigurieren, als Ihre Organisation für die Vollständigkeit der Datenaufnahme benötigt. Wenn es beispielsweise eine Verzögerung von 3 Stunden gibt, bevor Ihre Datenaufnahme abgeschlossen ist, sollten Sie die Verzögerung auf 4 Stunden festlegen.</li></ul><p>Weitere Informationen finden Sie unter [Datenaufnahmezeiten variieren je nach Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) im Artikel [Warnhinweise - Funktionsvergleich: Customer Journey Analytics und Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Warnhinweis senden, wenn]** | [!UICONTROL **Trigger einer dieser Metriken**]: Ziehen Sie Metriken (einschließlich berechneter Metriken) per Drag-and-Drop hierher, um Trigger für den Warnhinweis zu erstellen.<p>Eine **Meldung „Inkompatible Komponenten** wird angezeigt, wenn nicht alle Metriken, Dimensionen oder Segmente im Warnhinweis mit der aktuell ausgewählten Datenansicht kompatibel sind.</p><p>Legen Sie den Schwellenwert fest, den die Metrik überschreiten muss, damit ein Warnhinweis ausgegeben wird. Sie können diesen Wert auf einen Schwellenwert und anschließend auf eine der folgenden Bedingungen setzen:</p><ul><li>Anomalie vorhanden</li><li>Anomalie liegt über erwartetem Wert</li><li>Anomalie liegt unter erwartetem Wert</li><li>ist größer oder gleich</li><li>ist kleiner oder gleich</li><li>ändert sich um</li><li>Sie können einen Schwellenwert von 90 %, 95 %, 99 %, 99,75 % und 99,9 % festlegen.</li></ul><p>[!UICONTROL **Mit allen diesen Filtern**]: Ziehen Sie Segmente oder Dimensionen per Drag-and-Drop, um Filter hinzuzufügen. Wenn Sie beispielsweise das Segment „Nur Mobilgeräte“ hinzufügen, bedeutet dies, dass die Regel-Trigger nur für Mobilgeräte gelten. Mit einer AND-Anweisung können Sie zusätzliche Filter hinzufügen. Per Klick auf das Zahnrad-Symbol können Sie AND- oder OR-Regeln hinzufügen.</p><p>Siehe [Warnhinweise - Anwendungsfälle](/help/components/c-intelligent-alerts/alerts-use-cases.md), z. B. Anwendungsfälle.</p> |
| **[!UICONTROL Vorschau]** | Die interaktive Warnhinweisvorschau zeigt Ihnen basierend auf Daten aus der Vergangenheit, wie oft damit zu rechnen ist, dass ein Warnhinweis ausgelöst wird.<p>Beispiel: Wenn Sie die Zeitgranularität auf „Stündlich“ festlegen, kann Ihnen die Vorschau verraten, dass der Warnhinweis zu einer bestimmten Metrik während der letzten 30 oder 31 Tage x-mal ausgelöst worden wäre.</p><p>Wenn Sie feststellen, dass zu viele Warnhinweise ausgelöst worden wären, können Sie den Schwellenwert im Abschnitt [Verwalten von Warnhinweisen](/help/components/c-intelligent-alerts/alert-manager.md) anpassen.</p><p>![](assets/alert-preview.png){width="50%"}</p> |
