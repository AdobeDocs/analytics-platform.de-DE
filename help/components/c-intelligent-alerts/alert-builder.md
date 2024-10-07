---
description: Lassen Sie sich Warnhinweise anzeigen, wenn Projektkomponenten bestimmte Schwellenwerte erreichen.
title: Erstellen von Warnhinweisen
feature: Workspace Basics
role: User, Admin
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 19%

---

# Erstellen von Warnhinweisen {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_alerts_timegranularity"
>title="Zeitgranularität"
>abstract="Die Zeitgranularität bezieht sich sowohl darauf, wie oft der Warnhinweis überprüft wird, als auch darauf, was eingeschlossen wird."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Die Verwendung von Warnhinweisen mit Anomalieerkennung (auch _Intelligente Warnhinweise_ genannt) ist nur für Unternehmen mit einem Customer Journey Analytics Select-, Prime- oder Ultimate-Paket verfügbar.

Warnhinweise in Customer Journey Analytics ermöglichen es Ihnen, über geänderte Prozentsätze oder bestimmte Datenpunkte benachrichtigt zu werden. Je nach Customer Journey Analytics-Package können Sie auch Warnhinweise verwenden, die basierend auf Anomalieschwellen ausgelöst werden.

Detaillierte Übersichtsinformationen zu Warnhinweisen finden Sie unter [Warnhinweise - Übersicht](/help/components/c-intelligent-alerts/intelligent-alerts.md).

So erstellen Sie einen Warnhinweis:

1. Wählen Sie unter Customer Journey Analytics <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> **[!UICONTROL Komponenten]** > **[!UICONTROL Warnhinweise]** aus. Wählen Sie im Manager [Warnhinweise](alert-manager.md) die Option ![Kreis hinzufügen](/help/assets/icons/AddCircle.svg) **[!UICONTROL Hinzufügen]** aus, um einen neuen Warnhinweis zu erstellen, oder wählen Sie einen der aufgelisteten Warnhinweise aus, um einen vorhandenen Warnhinweis zu ändern.

   Die Benutzeroberfläche von [Alert Builder](#alert-builder) wird angezeigt.

1. Wählen Sie **[!UICONTROL Speichern]** aus, um den Warnhinweis zu speichern. Wählen Sie **[!UICONTROL Speichern unter]** aus, um eine Kopie des Warnhinweises zu speichern.


## Warnhinweiserstellung

Die Benutzeroberfläche der Warnhinweiserstellung ähnelt denen, die Filter oder berechnete Metriken in Customer Journey Analytics erstellt haben:

![](assets/alert-builder.png)

Geben Sie die folgenden Details im Warnhinweiserstellung für einen Warnhinweis an:

| Element | Beschreibung |
|---------|----------|
| **[!UICONTROL Titel]** | Geben Sie einen Namen für den Warnhinweis an. Der Warnhinweisname könnte den Namen des Berichts oder den Schwellenwert einer Metrik enthalten. |
| **[!UICONTROL Beschreibung (optional)]** | Geben Sie eine Beschreibung für den Warnhinweis an. |
| **[!UICONTROL Zeitgranularität]** | Wählen Sie aus, wie oft die Metrik überprüft werden soll: täglich, wöchentlich oder monatlich.<p><b>Hinweis:</b>Bei Datenansichten mit einem benutzerdefinierten Kalender wird die monatliche Granularität in der Warnhinweiserstellung nicht unterstützt.<!--true?--></p> |
| **[!UICONTROL Empfänger]** | Geben Sie an, wo der Warnhinweis hingeschickt werden soll. Ein Warnhinweis kann an einen Analyse-Benutzer, eine Analyse-Gruppe, eine E-Mail-Adresse oder eine Telefonnummer gesendet werden.<p><b>Wichtig:</b>Der Telefonnummer muss ein &quot;+&quot;- und ein &quot;[Ländercode](https://countrycode.org/)&quot; vorangestellt werden.</p><p>Die E-Mail, die ein Benutzer erhält, nachdem ein Warnhinweis ausgelöst wurde, sieht in etwa so aus:</p><p>![Warnhinweis-E-Mail](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Ablaufdatum]** | Legen Sie Datum und Uhrzeit für den Ablauf des Warnhinweises fest. |
| **[!UICONTROL Verzögerung]** | Die Zeit, die erforderlich ist, bevor die Daten vollständig sind und zur Berichterstattung auf der Customer Journey Analytics zur Verfügung stehen, variiert je nach Organisation, in der Regel zwischen 3 und 9 Stunden nach der Ereignis-Zeit. Damit Warnhinweise akkurat sind, müssen die Ereignisdaten für einen bestimmten Ereignisbereich vollständig sein, d. h. Adobe empfängt keine Ereignisdaten mehr für den angegebenen Ereignisbereich.<p>Um diese Verzögerung bei der Erfassungszeit zu berücksichtigen, dauert es standardmäßig neun Stunden, bis Warnhinweise gesendet werden.</p><p>Sie können die Standardverzögerung von 9 Stunden auf einen beliebigen Wert zwischen 0 und 24 Stunden einstellen. Eine Verringerung der Verzögerung auf unter 9 Stunden kann jedoch bedeuten, dass Sie über unvollständige Daten berichten, was zu ungenauen Warnhinweisinformationen führt.</p><p>Beachten Sie bei der Verkürzung der Verzögerungszeit Folgendes:</p><ul><li>**Datenverfügbarkeit und -vollständigkeit verstehen**: Auch wenn einige Daten möglicherweise bereits früher für Berichte verfügbar sind, werden alle Batch-Daten erst nach einem Zeitraum von 3 bis 9 Stunden in einen Platform-Datensatz aufgenommen. Damit Warnhinweise korrekt sind, muss die Datenerfassung abgeschlossen sein und alle Batch-Daten im Datensatz verfügbar sein.</li><li>**Bestimmen Sie, wie lange es dauert, bis Ihre Daten vollständig und im Datensatz verfügbar sind**: Die Datenerfassungszeiten unterscheiden sich je nach Organisation. Stellen Sie sicher, dass die von Ihnen für die Bereitstellung eines Warnhinweises gewählte Verzögerungszeit mit der Zeit übereinstimmt oder geringer ist, die benötigt wird, damit die Batch-Daten im Platform-Datensatz verfügbar sind<!--add link? -->.</li><p>**Tipp:** Die genaueste Möglichkeit, die Zeit zu kennen, die erforderlich ist, damit alle Batch-Daten vollständig sind und in den Platform-Datensatz aufgenommen werden, besteht darin, die Dateningenieure in Ihrer Organisation zu konsultieren.</p><p>Alternativ können Sie sich eine allgemeine Vorstellung davon verschaffen, wie lange es dauert, bis die Batch-Bereitstellung in Ihrem Unternehmen im Platform-Datensatz verfügbar ist, indem Sie die folgende Freiformtabelle in Analysis Workspace erstellen:</p><ol><li>Fügen Sie in einer Freiformtabelle in Analysis Workspace die Dimension [!UICONTROL **Ereignisse**] und die Dimension [!UICONTROL **Tag**] hinzu.</li><li>Schlüsseln Sie die Dimension [!UICONTROL **Tag**] mit der Dimension [!UICONTROL **Stunden**] auf.<p>Stunden ohne Daten werden als 0 angezeigt.</p></li></ol><li>**Fehler in Ihren Berechnungen berücksichtigen**: Wenn Sie die standardmäßige Verzögerungszeit verringern, empfehlen wir, die Verzögerung mindestens eine Stunde länger zu konfigurieren, als Ihr Unternehmen für die Vollständigkeit der Datenerfassung benötigt. Wenn es beispielsweise eine Verzögerung von 3 Stunden gibt, bevor die Datenerfassung abgeschlossen ist, sollten Sie die Verzögerung auf 4 Stunden setzen.</li></ul><p>Weitere Informationen finden Sie unter [Die Datenerfassungszeiten variieren in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) im Artikel [Warnhinweise-Funktionsvergleich: Customer Journey Analytics und Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Warnhinweis senden, wenn]** | [!UICONTROL **Jeder dieser Metriken Trigger**]: Ziehen Sie Metriken (einschließlich berechneter Metriken) hierher, um Trigger für den Warnhinweis zu erstellen.<p>Wenn nicht alle Metriken, Dimensionen oder Segmente im Warnhinweis mit der aktuell ausgewählten Datenansicht kompatibel sind, wird die Meldung **&quot;Nicht kompatible Komponenten&quot;** angezeigt.</p><p>Legen Sie den Schwellenwert fest, den die Metrik überschreiten muss, damit ein Warnhinweis ausgegeben wird. Sie können diesen Wert auf einen Schwellenwert und anschließend auf eine der folgenden Bedingungen setzen:</p><ul><li>Anomalie vorhanden</li><li>Anomalie liegt über erwartetem Wert</li><li>Anomalie liegt unter erwartetem Wert</li><li>ist größer oder gleich</li><li>ist kleiner oder gleich</li><li>ändert sich um</li><li>Sie können einen Schwellenwert von 90 %, 95 %, 99 %, 99,75 % und 99,9 % festlegen.</li></ul><p>[!UICONTROL **Mit all diesen Filtern**]: Ziehen Sie Segmente oder Dimensionen per Drag-and-Drop, um Filter hinzuzufügen. Wenn Sie beispielsweise das Segment &quot;Nur Mobilgeräte&quot;hinzufügen, würde die Regel nur für Mobilgeräte Trigger. Mithilfe einer AND-Anweisung können Sie weitere Filter hinzufügen. Per Klick auf das Zahnrad-Symbol können Sie AND- oder OR-Regeln hinzufügen.</p><p>Siehe [Warnhinweise - Anwendungsbeispiele](/help/components/c-intelligent-alerts/alerts-use-cases.md) .</p> |
| **[!UICONTROL Vorschau]** | Die interaktive Warnhinweisvorschau zeigt Ihnen basierend auf Daten aus der Vergangenheit, wie oft damit zu rechnen ist, dass ein Warnhinweis ausgelöst wird.<p>Beispiel: Wenn Sie die Zeitgranularität auf „Stündlich“ festlegen, kann Ihnen die Vorschau verraten, dass der Warnhinweis zu einer bestimmten Metrik während der letzten 30 oder 31 Tage x-mal ausgelöst worden wäre.</p><p>Wenn Sie feststellen, dass zu viele Warnhinweise ausgelöst worden wären, können Sie den Schwellenwert im Abschnitt [Warnhinweise verwalten](/help/components/c-intelligent-alerts/alert-manager.md) anpassen.</p><p>![](assets/alert-preview.png){width="50%"}</p> |

