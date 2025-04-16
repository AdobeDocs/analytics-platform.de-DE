---
description: Lassen Sie sich Warnhinweise anzeigen, wenn Projektkomponenten bestimmte Schwellenwerte erreichen.
title: Erstellen von Warnhinweisen
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 95%

---

# Erstellen von Warnhinweisen {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Zeitgranularität"
>abstract="Zeitgranularität bezieht sich sowohl darauf, wie oft der Warnhinweis überprüft wird, als auch darauf, was eingeschlossen wird"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Die Verwendung von Warnhinweisen mit Anomalieerkennung (auch als _intelligente Warnhinweise_ bezeichnet) ist nur für Organisationen mit einem Customer Journey Analytics Prime- oder Ultimate-Paket verfügbar.

Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, sich über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigen zu lassen. Je nach Customer Journey Analytics-Paket können Sie auch Warnhinweise verwenden, die basierend auf Schwellenwerten für Anomalien ausgelöst werden.

Weitere Übersichtsinformationen zu Warnhinweisen finden Sie unter [Überblick über Warnhinweise](/help/components/c-intelligent-alerts/intelligent-alerts.md).

So erstellen Sie einen Warnhinweis:

1. Wählen Sie in Customer Journey Analytics <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> **[!UICONTROL Komponenten]** > **[!UICONTROL Warnhinweise]** aus. Wählen Sie im [Warnhinweis-Manager](alert-manager.md) die Option ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Hinzufügen]** aus, um einen neuen Warnhinweis zu erstellen, oder wählen Sie einen der aufgelisteten Warnhinweise aus, um einen vorhandenen Warnhinweis zu ändern.

   Die Benutzeroberfläche des [Warnhinweis-Generators](#alert-builder) wird angezeigt.

1. Wählen Sie **[!UICONTROL Speichern]** aus, um den Warnhinweis zu speichern. Wählen Sie **[!UICONTROL Speichern unter]** aus, um eine Kopie des Warnhinweises zu speichern.


## Warnhinweis-Generator

Die Benutzeroberfläche der Warnhinweiserstellung ist denjenigen bekannt, die in Customer Journey Analytics Segmente oder berechnete Metriken erstellt haben:

![](assets/alert-builder.png)

Geben Sie die folgenden Details im Warnhinweis-Generator für einen Warnhinweis an:

| Element | Beschreibung |
|---------|----------|
| **[!UICONTROL Titel]** | Geben Sie einen Namen für den Warnhinweis an. Der Warnhinweisname könnte den Namen des Berichts oder den Schwellenwert einer Metrik enthalten. |
| **[!UICONTROL Beschreibung (optional)]** | Geben Sie eine Beschreibung für den Warnhinweis an. |
| **[!UICONTROL Zeitgranularität]** | Wählen Sie aus, wie oft die Metrik überprüft werden soll: täglich, wöchentlich oder monatlich.<p><b>Hinweis:</b>Bei Datenansichten mit einem benutzerdefinierten Kalender wird eine monatliche Granularität im Warnhinweis-Generator nicht unterstützt.<!--true?--></p> |
| **[!UICONTROL Empfänger]** | Geben Sie an, wo der Warnhinweis hingeschickt werden soll. Ein Warnhinweis kann an einen Analyse-Benutzer, eine Analyse-Gruppe, eine E-Mail-Adresse oder eine Telefonnummer gesendet werden.<p><b>Wichtig:</b>Die Telefonnummer muss über ein vorangestelltes Pluszeichen („+“) und eine [Landesvorwahl](https://countrycode.org/) verfügen.</p><p>Die E-Mail, die eine Person erhält, nachdem ein Warnhinweis ausgelöst wird, sieht in etwa so aus:</p><p>![Warninweis-E-Mail](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Ablaufdatum]** | Legen Sie Datum und Uhrzeit fest, zu denen der Warnhinweis ablaufen soll. |
| **[!UICONTROL Verzögerung]** | Die Zeit, die erforderlich ist, bevor Daten vollständig sind und für die Berichterstellung in Customer Journey Analytics zur Verfügung stehen, variiert je nach Organisation und liegt in der Regel 3 bis 9 Stunden nach der Datenereigniszeit. Damit Warnhinweise genau sind, müssen Ereignisdaten für einen bestimmten Ereignisbereich vollständig sein. Das bedeutet, dass Adobe für den angegebenen Ereignisbereich keine Ereignisdaten mehr erhält.<p>Um diese Verzögerung bei der Aufnahmezeit zu berücksichtigen, haben Warnhinweise standardmäßig eine Verzögerung von 9 Stunden, bevor sie gesendet werden.</p><p>Sie können die Standardverzögerung von 9 Stunden auf einen Wert zwischen 0 und 24 Stunden anpassen. Wenn Sie die Verzögerung jedoch auf weniger als 9 Stunden verkürzen, kann dies bedeuten, dass für Berichte unvollständige Daten vorliegen, was zu ungenauen Warnhinweisinformationen führt.</p><p>Beachten Sie beim Verkürzen der Verzögerungszeit Folgendes:</p><ul><li>**Kennen Sie den Unterschied zwischen Datenverfügbarkeit und Datenvollständigkeit**: Während einige Daten möglicherweise früher für Berichte verfügbar sind, werden alle Batch-Daten erst nach einem Zeitraum von 3 bis 9 Stunden in einen Platform-Datensatz aufgenommen. Damit Warnhinweise korrekt sind, muss die Datenaufnahme vollständig sein, wobei alle Batch-Daten im Datensatz verfügbar sein müssen.</li><li>**Bestimmen Sie, wie lange es dauert, bis Ihre Daten vollständig und im Datensatz verfügbar sind**: Die Datenaufnahmezeiten variieren je nach Organisation. Stellen Sie sicher, dass die von Ihnen gewählte Verzögerungszeit für die Bereitstellung von Warnhinweisen genauso lang oder kürzer ist als die Zeit, die benötigt wird, bis die Batch-Daten im Platform-Datensatz verfügbar sind<!--add link? -->.</li><p>**Tipp:** Am genauesten können Sie ermitteln, wie viel Zeit erforderlich ist, damit alle Batch-Daten vollständig sind und in den Platform-Datensatz aufgenommen werden, wenn Sie sich dabei vom Data-Engineering-Team Ihrer Organisation helfen lassen.</p><p>Alternativ können Sie sich einen Überblick darüber verschaffen, wie lange es dauert, bis die Batch-Bereitstellung in Ihrer Organisation im Platform-Datensatz verfügbar ist, indem Sie die folgende Freiformtabelle in Analysis Workspace erstellen:</p><ol><li>Fügen Sie in einer Freiformtabelle in Analysis Workspace eine Metrik [!UICONTROL **Ereignisse**] und eine Dimension [!UICONTROL **Tag**] hinzu.</li><li>Schlüsseln Sie die Dimension [!UICONTROL **Tag**] mithilfe einer Dimension [!UICONTROL **Stunden**] auf.<p>Stunden ohne Daten werden mit dem Wert „0“ angezeigt.</p></li></ol><li>**Berücksichtigen Sie mögliche Fehler in Ihren Berechnungen**: Wenn Sie die standardmäßige Verzögerungszeit verringern, sollten Sie sie so konfigurieren, dass die Verzögerung mindestens eine Stunde länger ist als die von Ihrer Organisation für eine vollständige Datenaufnahme benötigte Zeit. Wenn es beispielsweise eine Verzögerung von 3 Stunden gibt, bevor Ihre Datenaufnahme abgeschlossen ist, sollten Sie die Verzögerung auf 4 Stunden festlegen.</li></ul><p>Weitere Informationen finden Sie unter [Unterschiedliche Datenaufnahmezeiten in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) im Artikel [Warnhinweise – Funktionsvergleich: Customer Journey Analytics und Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Einen Warnhinweis senden, wenn]** | [!UICONTROL **Auslösen einer dieser Metriken**]: Ziehen Sie Metriken (einschließlich berechneter Metriken) per Drag-and-Drop hierher, um Trigger für den Warnhinweis zu erstellen.<p>Wenn nicht alle Metriken, Dimensionen oder Segmente des Warnhinweises mit der aktuell ausgewählten Datenansicht kompatibel sind, wird die Meldung **Inkompatible Komponenten** angezeigt.</p><p>Legen Sie den Schwellenwert fest, den die Metrik überschreiten muss, damit ein Warnhinweis ausgegeben wird. Sie können diesen Wert auf einen Schwellenwert und anschließend auf eine der folgenden Bedingungen setzen:</p><ul><li>Anomalie vorhanden</li><li>Anomalie liegt über erwartetem Wert</li><li>Anomalie liegt unter erwartetem Wert</li><li>ist größer oder gleich</li><li>ist kleiner oder gleich</li><li>ändert sich um</li><li>Sie können einen Schwellenwert von 90 %, 95 %, 99 %, 99,75 % und 99,9 % festlegen.</li></ul><p>[!UICONTROL **Mit allen diesen Segmenten**]: Ziehen Sie Segmente oder Dimensionen per Drag-and-Drop, um Segmente hinzuzufügen. Wenn Sie zum Beispiel ein Segment vom Typ „Nur Mobilgeräte“ hinzufügen, würde die Regel nur für Mobilgeräte ausgelöst werden. Sie können zusätzliche Segmente mithilfe einer AND-Anweisung hinzufügen. Per Klick auf das Zahnrad-Symbol können Sie AND- oder OR-Regeln hinzufügen.</p><p>Beispiele finden Sie unter [Warnhinweise – Anwendungsfälle](/help/components/c-intelligent-alerts/alerts-use-cases.md).</p> |
| **[!UICONTROL Vorschau]** | Die interaktive Warnhinweisvorschau zeigt Ihnen basierend auf Daten aus der Vergangenheit, wie oft damit zu rechnen ist, dass ein Warnhinweis ausgelöst wird.<p>Beispiel: Wenn Sie die Zeitgranularität auf „Stündlich“ festlegen, kann Ihnen die Vorschau verraten, dass der Warnhinweis zu einer bestimmten Metrik während der letzten 30 oder 31 Tage x-mal ausgelöst worden wäre.</p><p>Wenn Sie der Ansicht sind, dass Warnhinweise zu oft ausgelöst werden würden, können Sie den Schwellenwert unter [Warnhinweise verwalten](/help/components/c-intelligent-alerts/alert-manager.md) anpassen.</p><p>![](assets/alert-preview.png){width="50%"}</p> |
