---
title: Übersicht über Datenansichten
description: Eine Datenansicht gibt an, wie Sie Datenelemente der Customer Journey Analytics-Verbindung, wie Metriken, Dimensionen, Sitzungen usw., interpretieren möchten.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0e4e4621abe02c022981e458282543908b2396c2
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 43%

---

# Übersicht über die Datenansichten

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer [Verbindung](/help/connections/create-connection.md) interpretiert werden. Es werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

>[!NOTE]
>
>Alle Einstellungen, die Sie in einer Datenansicht auswählen oder ändern, sind rückwirkend und nicht zerstörerisch. Mit anderen Worten, sie ändern Ihre zugrunde liegenden Daten nicht dauerhaft.

Sie können verschiedene Datenansichten für die gleiche Verbindung mit sehr unterschiedlichen Komponentensätzen (Dimensionen/Metriken) erstellen. Oder erstellen Sie Datenansichten mit unterschiedlichen Einstellungen für Besuchstimeout, Attribution usw. Beispielsweise könnten Sie eine Datenansicht haben, in der alle Dimensionen auf [!UICONTROL Letztkontakt] eingestellt sind, und gleichzeitig eine andere Datenansicht (basierend auf demselben Datensatz), in der alle Dimensionen auf [!UICONTROL Erstkontakt] eingestellt sind.

Arbeitsbereich-Projekte in Customer Journey Analytics basieren auf Datenansichten.

>[!IMPORTANT]
>
>Zu einer Datenansicht können bis zu 5.000 Metriken und 5.000 Dimensionen hinzugefügt werden.

## Datenansichten – Funktionen {#capabilities}

Mit Datenansichten können Sie die Schemaelement-Einstellungen spontan ändern, ohne dass das Schema in Adobe Experience Platform geändert oder Ihre Customer Journey Analytics-Umgebung erneut implementiert werden muss.

* Sie können eine Komponente von einer Metrik in eine Dimension ändern und umgekehrt. Sie können Metriken aus Zeichenfolgenfeldern oder Dimensionen aus numerischen Feldern erstellen. Diese Funktion erleichtert Ihnen das Leben, da Sie nicht für jede gewünschte Metrik ein numerisches Feld in Ihrem XDM-Schema erstellen müssen. Stattdessen können Sie sie spontan im Dialog „Dateiansichten“ erstellen. Im Folgenden finden Sie einige Beispiele:
   * **Erstellen Sie eine oder mehrere Dimensionen und/oder eine Dimension aus einem Schema-Feld**. Es ist eine Eins-zu-viele-Beziehung. Sie können beispielsweise eine oder mehrere Umsatzmetriken und/oder eine oder mehrere Umsatzdimensionen aus einem einzigen Schemafeld erstellen.
   * **Verwenden Sie ein Zeichenfolgenfeld als Metrik**: Wenn Sie ein Schema in Experience Platform mit einem Datensatz füllen, wissen Sie möglicherweise nicht schon gleich zu Beginn, welche Schema-Elemente Sie benötigen. Sie haben beispielsweise möglicherweise nicht erkannt, dass Sie eine Metrik für *Fehler auf einer Seite* benötigen. Daher haben Sie kein numerisches Schema-Element für diesen Zweck erstellt. Durch die Verwendung eines Zeichenfolgenelements als Metrik können Sie jetzt mithilfe der Datenansichtseinstellungen festlegen, dass eine Zeichenfolge, die das Wort `error` enthält, immer als Metrik verwendet werden kann.
   * **Numerisches Feld als Dimension verwenden**: Wenn Sie beispielsweise die Umsatzmetrik aus der Umsatzdimension ziehen möchten, zeigt die Umsatzdimension jeden Wert als Dimensionselement an. Und die Anzahl der Instanzen für jedes Dimensionselement als Metrik.

* Sie können mehrere Metriken mit verschiedenen Attributionsmodellen oder verschiedenen Lookback-Fenstern aus demselben Schemafeld erstellen.

* Sie können die ID einer Komponente bearbeiten, um die Kompatibilität zwischen Datenansichten zu gewährleisten. Die Komponenten-ID wird von der Reporting-API zur Identifizierung einer bestimmten Metrik oder Dimension verwendet. Da Sie beliebig viele Metriken oder Dimensionen aus einem XDM-Feld erstellen können, können Sie Ihre eigene Komponenten-ID definieren. Daher kann eine Metrik, die Sie in einem Workspace-Projekt verwenden, kompatibel für alle Datenansichten (und die API) verwendet werden. Selbst wenn die Metriken auf völlig unterschiedlichen Feldern von verschiedenen Verbindungen, Datenansichten oder von einem anderen Schema in XDM basieren.

* Sie können den Anzeigenamen der Komponente angeben, der in Analysis Workspace angezeigt wird. Standardmäßig wird dieser Name vom Anzeigenamen des Schemas übernommen, Sie können ihn jetzt jedoch für diese spezifische Ansicht überschreiben.

* Sie können weitere schemabezogene Informationen zu Komponenten anzeigen. Beispiel:

   * welcher Datensatztyp (Ereignis, Profil, Suche, Zusammenfassung) von der Komponente stammt,
   * welcher Schementyp (Zeichenfolge, Ganzzahl usw.) sie stammt aus und
   * den Schemapfad (das XDM-Feld, auf dem es basiert).

* Sie können eine Komponente taggen, um die Suche in Workspace zu vereinfachen.

* Sie können eine Komponente in Berichten ausblenden. Für einige Metrik- und Dimensionseinstellungen ist eine zweite Metrik oder Dimension für die Konfiguration erforderlich (beispielsweise für metrische Deduplizierung oder Kauf-Deduplizierung). Durch das Ausblenden einer Komponente können Sie eine Komponente definieren, die in den Einstellungen einer anderen Komponente verwendet werden kann, ohne in Berichten verfügbar zu sein.

* Sie können eine Metrik formatieren, z. B. Dezimalzahl, Zeit, Prozent oder Währung anzeigen, Dezimalstellen angeben, Aufwärtstrend grün oder rot anzeigen und Währungsoptionen festlegen.

* Sie können eine Metrik oder Dimension erstellen, die nur auf einigen Werten im Schemafeld basiert. Wenn Sie beispielsweise eine Fehlermetrik wünschen, können Sie eine Metrik aus dem Feld &quot;Seitenname&quot;erstellen, aber nur Seiten einschließen, die das Wort &quot;`error`&quot; enthalten. Die auf diese Weise erstellte Fehlermetrik unterstützt Filter, kann in berechnete Metriken eingefügt werden und funktioniert mit Attribution, Fluss, Fallout usw.

* Bei Dimensionen können Sie automatisch nur bestimmte Werte innerhalb eines bestimmten Felds ein- oder ausschließen. Wenn beispielsweise ein Entwickler einen falschen Wert von `dev mistake` in ein Feld sendet, können Sie ihn mithilfe einer Ausschlussregel einfach von der Berichterstellung ausschließen. Die Dimension verhält sich so, als gäbe es in den Daten keinen falschen Wert.

* Sie können Ihre Container in einer Datenansicht umbenennen und diese umbenannten Container in jedem Workspace-Projekt platzieren, das auf dieser Datenansicht basiert.

## Voraussetzungen für die Datenansicht {#prerequisites}

* Bevor Sie Datenansichten erstellen können, müssen Sie [eine oder mehrere Verbindungen zu Experience Platform-Datensätzen einrichten](/help/connections/create-connection.md).
* Zum Erstellen oder Verwalten einer Datenansicht benötigen Sie einen [Berechtigungssatz in Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview).
* Wenn Sie den [Adobe Analytics-Quell-Connector](/help/data-ingestion/analytics.md) verwenden oder über Kenntnisse im Adobe Analytics-Hintergrund verfügen, möchten Sie möglicherweise wissen, wie die Felder in Ihren Schemas und Datensätzen mit den Adobe Analytics-Gegenstücken zusammenhängen. Weitere Informationen finden Sie unter [Zuordnung von Analytics-Feldern](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics).

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

Wenn Sie eine Datenansicht in [!UICONTROL Customer Journey Analytics] löschen, zeigt eine Fehlermeldung an, dass alle [!UICONTROL Workspace]-Projekte, die von dieser gelöschten Datenansicht abhängig sind, nicht mehr funktionieren.

## Nächste Schritte

* [Erstellen von Datenansichten](/help/data-views/create-dataview.md)
* [Anwendungsfälle von Datenansichten](/help/use-cases/data-views/data-views-usecases.md)
