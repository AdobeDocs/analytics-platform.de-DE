---
title: Übersicht über Datenansichten
description: Eine Datenansicht gibt an, wie Datenelemente in der Customer Journey Analytics-Verbindung zu interpretieren sind, beispielsweise Metriken, Dimensionen, Sitzungen usw.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: c1e6279d8e2f0b31a82c2588fce8b3c2e614e440
workflow-type: ht
source-wordcount: '1106'
ht-degree: 100%

---

# Übersicht über die Datenansichten

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer [Verbindung](/help/connections/create-connection.md) interpretiert werden. Es werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

>[!NOTE]
>
>Alle Einstellungen, die Sie in einer Datenansicht auswählen oder ändern, sind rückwirkend und nicht zerstörerisch. Das heißt, dass sie Ihre zugrunde liegenden Daten nicht dauerhaft ändern.

Sie können verschiedene Datenansichten für die gleiche Verbindung mit sehr unterschiedlichen Komponentensätzen (Dimensionen/Metriken) erstellen. Außerdem können Sie Datenansichten mit unterschiedlichen Einstellungen für Besuchs-Timeout, Zuordnung usw. erstellen. Beispielsweise könnten Sie eine Datenansicht haben, in der alle Dimensionen auf [!UICONTROL Letztkontakt] eingestellt sind, und gleichzeitig eine andere Datenansicht (basierend auf demselben Datensatz), in der alle Dimensionen auf [!UICONTROL Erstkontakt] eingestellt sind.

Arbeitsbereich-Projekte in Customer Journey Analytics basieren auf Datenansichten.

>[!IMPORTANT]
>
>Zu einer Datenansicht können bis zu 5.000 Metriken und 5.000 Dimensionen hinzugefügt werden.

## Datenansichten – Funktionen {#capabilities}

Mit Datenansichten können Sie die Schemaelement-Einstellungen spontan ändern, ohne dass das Schema in Adobe Experience Platform geändert oder Ihre Customer Journey Analytics-Umgebung erneut implementiert werden muss.

* **Sie können eine Komponente von einer Metrik in eine Dimension ändern und umgekehrt**. Sie können Metriken aus Zeichenfolgenfeldern oder Dimensionen aus numerischen Feldern erstellen. Dies erleichtert Ihnen das Leben, da Sie nicht für jede gewünschte Metrik ein numerisches Feld in Ihrem XDM-Schema erstellen müssen. Stattdessen können Sie sie spontan im Dialog „Dateiansichten“ erstellen. Im Folgenden finden Sie einige Beispiele:
   * **Erstellen Sie eine oder mehrere Dimensionen und/oder eine Dimension aus einem Schema-Feld**. Es ist eine Eins-zu-viele-Beziehung. Sie können beispielsweise eine oder mehrere Umsatzmetriken und/oder eine oder mehrere Umsatzdimensionen aus einem einzigen Schemafeld erstellen.
   * **Verwenden Sie ein Zeichenfolgenfeld als Metrik**: Wenn Sie ein Schema in Experience Platform mit einem Datensatz füllen, wissen Sie möglicherweise nicht schon gleich zu Beginn, welche Schema-Elemente Sie benötigen. Beispielsweise war Ihnen noch nicht bewusst, dass Sie eine Metrik für „Fehler auf einer Seite“ benötigen. Daher haben Sie kein numerisches Schema-Element für diesen Zweck erstellt. Durch Verwendung eines Zeichenfolgen-Elements als Metrik können Sie jetzt mithilfe der Einstellungen für Datenansichten festlegen, dass jede Zeichenfolge, die das Wort „Fehler“ enthält, als Metrik verwendet werden kann.
   * **Verwenden eines numerischen Felds als Dimension**: Wenn Sie beispielsweise die Umsatzmetrik aus der Umsatzdimension ziehen möchten, zeigt die Umsatzdimension jeden Wert als Dimensionselement an (100 $, 175 $, 1.000 $ usw.) und die Anzahl der Instanzen für jedes Dimensionselement. Umsatz als Metrik verhält sich wie immer.

* **Sie können mehrere Metriken mit verschiedenen Zuordnungsmodellen oder mit unterschiedlichen Lookback-Fenstern** aus demselben Schemafeld erstellen.

* **Sie können die ID einer Komponente bearbeiten**. Dies wird zur Kompatibilität zwischen verschiedenen Datenansichten verwendet. Die Komponenten-ID wird von der Reporting-API zur Identifizierung einer bestimmten Metrik oder Dimension verwendet. Da Sie beliebig viele Metriken oder Dimensionen aus einem XDM-Feld erstellen können, haben Sie die Möglichkeit, Ihre eigene Komponenten-ID zu definieren. Daher kann eine Metrik, die Sie in einem Arbeitsbereich-Projekt verwenden, über Datenansichten (und die API) hinweg kompatibel sein, auch wenn sie auf völlig unterschiedlichen Feldern aus unterschiedlichen Verbindungen oder Datenansichten oder aus einem anderen XDM-Schema basiert.

* **Sie können den Anzeigenamen der Komponente festlegen, der in Analysis Workspace angezeigt wird**. Standardmäßig wird dieser Name vom Anzeigenamen des Schemas übernommen, Sie können ihn jetzt jedoch für diese spezifische Ansicht überschreiben.

* **Sie können weitere Schema-bezogene Informationen zu Komponenten sehen**, beispielsweise von welchem Datensatztyp (Ereignis, Profil, Suche) sie stammen, von welchem Schema-Typ (String, Integer usw.) sie stammen und was der zugehörige Schema-Pfad ist (das XDM-Feld, auf dem sie basieren).

* **Sie können eine Komponente taggen**, um die Suche nach ihr in Arbeitsbereich zu erleichtern.

* **Sie können eine Komponente in Berichten ausblenden**. Für einige Metrik- und Dimensionseinstellungen ist eine zweite Metrik oder Dimension für die Konfiguration erforderlich (beispielsweise für metrische Deduplizierung oder Kauf-Deduplizierung). Auf diese Weise können Sie eine Metrik oder Dimension definieren, die in den Einstellungen einer anderen Metrik oder Dimension verwendet werden kann, ohne dass sie direkt in Berichten auftaucht (beispielsweise eine Kauf-ID).

* **Sie können Formatierungen auf eine Metrik anwenden**, beispielsweise zur Darstellung von Dezimalstellen, Uhrzeiten, Prozentwerten oder Währungen, zur Anzeige der Dezimalstellen, zur grünen oder roten Darstellung von Aufwärtstrends oder zum Festlegen der Währungsoptionen.

* Sie können **eine Metrik oder Dimension nur auf Basis einiger Werte im Schemafeld erstellen**. Wenn Sie beispielsweise eine Metrik für „Fehler“ wünschen, können Sie eine Metrik aus dem Feld „Seitenname“ erstellen, aber nur Seiten einschließen, die das Wort „Fehler“ enthalten. Die auf dieser Grundlage erstellte Fehlermetrik wird von Filtern unterstützt, kann in berechnete Metriken eingefügt werden und funktioniert mit Attribution, Fluss, Fallout usw.

* Bei Dimensionen können Sie **automatisch nur bestimmte Werte in einem bestimmten Feld ein- oder ausschließen**. Wenn ein Entwickler beispielsweise einen falschen Wert von `dev mistake` in ein Feld gesendet hat, können Sie ihn mithilfe einer Ausschlussregel problemlos vom Bericht ausschließen und der Wert wird sich so verhalten, als ob er nie in den Daten vorhanden gewesen wäre.

* Sie können **Ihre Container in einer Datenansicht umbenennen** und diese umbenannten Container in jedem Arbeitsbereich-Projekt platzieren, das auf dieser Datenansicht basiert.

## Voraussetzungen für die Datenansicht {#prerequisites}

* Bevor Sie Datenansichten erstellen können, müssen Sie [eine oder mehrere Verbindungen zu Experience Platform-Datensätzen einrichten](/help/connections/create-connection.md).
* Zum Erstellen oder Verwalten einer Datenansicht benötigen Sie einen [Berechtigungssatz in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de#admin-access-permissions).
* Wenn Sie [Adobe Analytics Source Connector](/help/data-ingestion/analytics.md) verwenden oder über Adobe Analytics-Kenntnisse verfügen, möchten Sie möglicherweise wissen, wie Felder in Ihren Schemata und Datensätzen, die Teil der Verbindung sind, mit ihren Adobe Analytics-Gegenstücken verknüpft sind. Weitere Informationen finden Sie unter [Zuordnung von Analytics-Feldern](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de).

## Einstellungen für die Datenansicht, die Sie in Arbeitsbereich überschreiben können {#settings-override}

Einige Einstellungen für die Datenansicht können in Analysis Workspace auf Projektebene überschrieben werden, andere nicht.

* [!UICONTROL Lookback-Fenster]
* Attribution von Metriken
* Ob Benutzer den Zeileneintrag [!UICONTROL Kein Wert] in einem Bericht sehen

## Einstellungen für die Datenansicht, die Sie in Arbeitsbereich nicht überschreiben können {#settings-no-override}

* [!UICONTROL Typ der Komponente]
* Formatierung von Metriken
* Name der Datenansicht
* Zuweisung von Dimensionen

## Löschen von Datenansichten {#delete}

Wenn Sie eine Datenansicht in [!UICONTROL Customer Journey Analytics] löschen, wird eine Fehlermeldung angezeigt, die besagt, dass alle [!UICONTROL Arbeitsbereich]-Projekte, die von dieser gelöschten Datenansicht abhängig sind, nicht mehr funktionieren.

## Nächste Schritte

* [Erstellen von Datenansichten](/help/data-views/create-dataview.md)
* [Anwendungsfälle von Datenansichten](/help/use-cases/data-views/data-views-usecases.md)
