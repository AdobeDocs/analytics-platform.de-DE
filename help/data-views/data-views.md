---
title: Datenansichten - Übersicht
description: Erfahren Sie, wie eine Datenansicht angibt, wie Sie Datenelemente in der Customer Journey Analytics-Verbindung interpretieren möchten, z. B. Metriken, Dimensionen, Sitzungen usw.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/WNPt241AppdCZVtsYmyLM2mRa2nqvrfYFbIP6K5NR1U
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: c38ed341-fab2-46df-9d72-88d8166edebbid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1124
ht-degree: 88%

---

# Überblick über Datenansichten

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer [Verbindung](/help/connections/create-connection.md) interpretiert werden. Darin werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

>[!NOTE]
>
>Alle Einstellungen, die Sie in einer Datenansicht auswählen oder ändern, sind rückwirkend und nicht zerstörerisch. Das heißt, dass sie Ihre zugrunde liegenden Daten nicht dauerhaft ändern.

Sie können verschiedene Datenansichten für die gleiche Verbindung mit sehr unterschiedlichen Komponentensätzen (Dimensionen/Metriken) erstellen. Oder erstellen Sie Datenansichten mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. Beispielsweise könnten Sie eine Datenansicht haben, in der alle Dimensionen auf [!UICONTROL Letztkontakt] eingestellt sind, und gleichzeitig eine andere Datenansicht (basierend auf demselben Datensatz), in der alle Dimensionen auf [!UICONTROL Erstkontakt] eingestellt sind.

Arbeitsbereich-Projekte in Customer Journey Analytics basieren auf Datenansichten.

>[!IMPORTANT]
>
>Zu einer Datenansicht können bis zu 5.000 Metriken und 5.000 Dimensionen hinzugefügt werden.

## Datenansichten – Funktionen {#capabilities}

Mit Datenansichten können Sie die Schemaelement-Einstellungen spontan ändern, ohne dass das Schema in Adobe Experience Platform geändert oder Ihre Customer Journey Analytics-Umgebung erneut implementiert werden muss.

* Sie können eine Komponente von einer Metrik in eine Dimension ändern und umgekehrt. Sie können Metriken aus Zeichenfolgenfeldern oder Dimensionen aus numerischen Feldern erstellen. Diese Funktionalität erleichtert Ihnen das Leben, da Sie nicht für jede gewünschte Metrik ein numerisches Feld in Ihrem XDM-Schema erstellen müssen. Stattdessen können Sie sie spontan im Dialog „Dateiansichten“ erstellen. Im Folgenden finden Sie einige Beispiele:
   * **Erstellen Sie eine oder mehrere Metriken und/oder Dimensionen aus einem einzigen Schemafeld**. Es ist eine Eins-zu-viele-Beziehung. Sie können beispielsweise eine oder mehrere Umsatzmetriken und/oder eine oder mehrere Umsatzdimensionen aus einem einzigen Schemafeld erstellen.
   * **Verwenden Sie ein Zeichenfolgenfeld als Metrik**: Wenn Sie ein Schema in Experience Platform mit einem Datensatz füllen, wissen Sie möglicherweise nicht schon gleich zu Beginn, welche Schema-Elemente Sie benötigen. Beispielsweise war Ihnen vielleicht noch nicht bewusst, dass Sie eine Metrik für *Fehler auf einer Seite* benötigen. Daher haben Sie kein numerisches Schema-Element für diesen Zweck erstellt. Durch Verwendung eines Zeichenfolgen-Elements als Metrik können Sie jetzt mithilfe der Einstellungen für Datenansichten festlegen, dass jede Zeichenfolge, die das Wort `error` enthält, als Metrik verwendet werden kann.
   * **Verwenden Sie ein numerisches Feld als Dimension**. Wenn Sie beispielsweise die Umsatzmetrik aus der Umsatzdimension abrufen möchten, zeigt die Umsatzdimension jeden Wert als Dimensionselement und die Anzahl der Instanzen für jedes Dimensionselement als Metrik an.

* Sie können mehrere Metriken mit verschiedenen Attributionsmodellen oder unterschiedlichen Lookback-Fenstern aus demselben Schemafeld erstellen.

* Sie können die ID einer Komponente bearbeiten, um Kompatibilität zwischen verschiedenen Datenansichten zu erreichen. Die Komponenten-ID wird von der Reporting-API zur Identifizierung einer bestimmten Metrik oder Dimension verwendet. Da Sie beliebig viele Metriken oder Dimensionen aus einem XDM-Feld erstellen können, haben Sie die Möglichkeit, eine eigene Komponenten-ID zu definieren. Daher ist eine Metrik, die Sie in einem Workspace-Projekt verwenden, für alle Datenansichten (und die API) kompatibel verwendbar. Dies gilt, selbst wenn die Metriken auf völlig unterschiedlichen Feldern von verschiedenen Verbindungen, Datenansichten oder von einem anderen Schema in XDM basieren.

* Sie können den Anzeigenamen der Komponente festlegen, der in Analysis Workspace angezeigt wird. Standardmäßig wird dieser Name vom Anzeigenamen des Schemas übernommen, Sie können ihn jetzt jedoch für diese spezifische Ansicht überschreiben.

* Sie können weitere schemabezogene Informationen zu Komponenten anzeigen, z. B.:

   * von welchem Datensatztyp („Ereignis“, „Profil“, „Lookup“, „Zusammenfassung“) die Komponente stammt
   * welcher Schematyp (Zeichenfolge, Ganzzahl usw.) es stammt aus und
   * wie der Schemapfad (das XDM-Feld, auf dem sie basiert) lautet

* Sie können eine Komponente taggen, um die Suche nach ihr in Workspace zu erleichtern.

* Sie können eine Komponente in Berichten ausblenden. Für einige Metrik- und Dimensionseinstellungen ist eine zweite Metrik oder Dimension für die Konfiguration erforderlich (beispielsweise für metrische Deduplizierung oder Kauf-Deduplizierung). Durch das Ausblenden einer Komponente können Sie eine Komponente definieren, die in den Einstellungen einer anderen Komponente verwendet werden kann, ohne in Berichten aufzutauchen.

* Sie können Formatierungen auf eine Metrik anwenden, beispielsweise zur Darstellung von Dezimalstellen, Uhrzeiten, Prozentwerten oder Währungen, zur Angabe der Dezimalstellen, zur grünen oder roten Darstellung von Aufwärtstrends oder zur Festlegung der Währungsoptionen.

* Sie können eine Metrik oder Dimension auf Basis nur einiger Werte im Schemafeld erstellen. Wenn Sie beispielsweise eine Metrik für „Fehler“ haben möchten, können Sie eine Metrik aus dem Feld „Seitenname“ erstellen, aber nur Seiten einschließen, die das Wort `error` enthalten. Die auf diese Weise erstellte Fehlermetrik unterstützt Segmente und kann in berechnete Metriken eingefügt sowie für Attribution, Fluss, Fallout usw. verwendet werden.

* Bei Dimensionen können Sie automatisch nur bestimmte Werte in einem bestimmten Feld ein- oder ausschließen. Wenn beispielsweise eine Entwicklerin oder ein Entwickler einen falschen `dev mistake`-Wert an ein Feld gesendet hat, können Sie ihn mithilfe einer Ausschlussregel einfach aus Berichten ausschließen. Die Dimension verhält sich so, als hätte es den falschen Wert in den Daten niemals gegeben.

* Sie können Ihre Container in einer Datenansicht umbenennen und diese umbenannten Container in einem beliebigen Workspace-Projekt platzieren, das auf dieser Datenansicht basiert.

* Sie können die Data Insights Agent für eine Datenansicht aktivieren oder deaktivieren.

## Voraussetzungen für die Datenansicht {#prerequisites}

* Bevor Sie Datenansichten erstellen können, müssen Sie [eine oder mehrere Verbindungen zu Experience Platform-Datensätzen einrichten](/help/connections/create-connection.md).
* Zum Erstellen oder Verwalten einer Datenansicht benötigen Sie einen [Berechtigungssatz in Adobe Admin Console](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-overview).
* Wenn Sie den [Adobe Analytics-Quell-Connector](/help/data-ingestion/analytics.md) verwenden oder über Adobe Analytics-Kenntnisse verfügen, möchten Sie möglicherweise wissen, in welcher Beziehung die Felder in Ihren Schemata und Datensätzen zu ihren Adobe Analytics-Gegenstücken stehen. Weitere Informationen finden Sie unter [Zuordnung von Analytics-Feldern](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics).

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

Wenn Sie [Datenansicht löschen](/help/data-views/manage-dataviews.md#delete-data-views) in [!UICONTROL Customer Journey Analytics], zeigt eine Fehlermeldung an, dass alle [!UICONTROL Workspace]-Projekte, die von dieser gelöschten Datenansicht abhängig sind, nicht mehr funktionieren.

## Nächste Schritte

* [Erstellen von Datenansichten](/help/data-views/create-dataview.md)
* [Datenansichten verwalten](/help/data-views/manage-dataviews.md)
* [Anwendungsfälle von Datenansichten](/help/use-cases/data-views/data-views-usecases.md)
