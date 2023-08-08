---
title: Unterstützung der Customer Journey Analytics-Funktion
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 264b5a3d3793ab6531f570d83cbd4fd96bfbd67a
workflow-type: tm+mt
source-wordcount: '2089'
ht-degree: 97%

---

# Unterstützte Funktionen in Adobe Customer Journey Analytics

In den folgenden Tabellen ist aufgeführt, welche Adobe Analytics-Funktionen in Customer Journey Analytics unterstützt, teilweise unterstützt oder nicht unterstützt werden und welche Funktionen von Customer Journey Analytics in Adobe Analytics nicht unterstützt werden oder nicht verfügbar sind. Diese Listen ändern sich im Laufe der Zeit, wenn Funktionen zu Customer Journey Analytics hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten {#full-support}

| Adobe Analytics-Funktion | Hinweise zur Unterstützung |
| --- | --- |
| Anomalieerkennung | Vollständige Unterstützung. |
| Attribution IQ | Vollständige Unterstützung. |
| Berechnete Metriken | Vollständige Unterstützung. Vorhandene berechnete Metriken im herkömmlichen Analysis Workspace werden nicht nach Customer Journey Analytics portiert. |
| Kalenderereignisse | Vollständige Unterstützung. Kalenderereignisse wurden bisher als [Anmerkungen](/help/components/annotations/overview.md) in Workspace implementiert. |
| CSV-Download | Vollständige Unterstützung. |
| Benutzerdefinierte Kalender | Vollständige Unterstützung. |
| Datumsvergleiche | Vollständige Unterstützung. |
| Datumsbereiche | Alle Datumsbereichsfunktionen werden unterstützt. |
| Dimensionen | Vollständige Unterstützung. Customer Journey Analytics verwendet XDM und unterstützt unbegrenzte Dimensionen. Customer Journey Analytics ist nicht an benutzerdefinierte eVars oder Eigenschaften des herkömmlichen Adobe Analytics-Tools gebunden. |
| Löschung gemäß der DSGVO | Vollständige Unterstützung; beachten Sie, dass die DSGVO jetzt in Abstimmung mit [!UICONTROL Adobe Experience Platform] gehandhabt wird. Customer Journey Analytics übernimmt alle Datenänderungen, die [!UICONTROL Experience Platform] an den zugrunde liegenden Datensätzen vornimmt. |
| Reporting über Anstieg und Konfidenz | Vollständige Unterstützung über das [Experimentier-Bedienfeld](/help/analysis-workspace/c-panels/experimentation.md) |
| Listenvariablen/Listen-Props | Vollständige Unterstützung. Customer Journey Analytics nutzt XDM und unterstützt unbegrenzte Zeichenfolgen-Arrays, die ähnlich wie listVars verwendet werden können. |
| Merchandising-eVars | Vollständige Unterstützung über [Binding-Dimensionen und Binding-Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| Metriken | Vollständige Unterstützung; Customer Journey Analytics nutzt das Experience-Datenmodell (XDM), unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse von Adobe Analytics gebunden. Beachten Sie, dass einige Standardmetriken in Adobe Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Mobile Scorecard/Dashboards | Vollständige Unterstützung. |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. |
| PDF-Export | Vollständige Unterstützung. |
| Projektkuration | Vollständige Unterstützung. |
| Projektverknüpfung | Vollständige Unterstützung. |
| Berichtszeitverarbeitung | Vollständige Unterstützung; Customer Journey Analytics verlässt sich ausschließlich auf die Verarbeitung zum Zeitpunkt der Berichtserstellung. |
| Zugriff auf die Reporting-API | Vollständige Unterstützung; verfügbar über die [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/). |
| Terminierte Berichte/Projekte | Vollständige Unterstützung. |
| Segmente | Vollständige Unterstützung. Jetzt „Filter“ genannt. Beachten Sie, dass keine vorhandenen Segmente im herkömmlichen Analysis Workspace nach Customer Journey Analytics portiert werden. |
| Virtual Report Suites | Vollständige Unterstützung; jetzt [Datenansichten](/help/data-views/create-dataview.md) genannt. |
| Komponentenkuratierung in Virtual Report Suites | Vollständige Unterstützung. Jetzt Teil der Datenansichten. |
| Streamen von Media Analytics | Mediendaten sind über den Analytics-Quell-Connector als Teil des Bedienfelds „Gleichzeitige Medienbetrachter“ und des Bedienfelds „Bei Medienwiedergabe verbrachte Zeit“ in Workspace verfügbar. |

{style="table-layout:auto"}

## Auf neue Art unterstützt {#new-support}

| Funktion | Hinweise |
| --- | --- |
| Zielgruppenveröffentlichung (Segment-Publishing) | Wird unterstützt, sofern diese Funktion mit den Adobe-Produkten Customer Data Platform oder Journey Optimizer lizenziert wurde. [Zielgruppenveröffentlichung](/help/components/audiences/audiences-overview.md) sendet Zielgruppen an das Echtzeit-Kundenprofil in Experience Platform. |
| Classifications | Jetzt „Lookup-Datensätze“ genannt. In Analytics verwendete Klassifizierungen können mit dem Quell-Connector für Analytics-Klassifizierungen in Experience Platform und Customer Journey Analytics importiert werden. Suchdatensätze können auch direkt in Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| Classification Rule Builder | Unterstützt mit Verwendung von [Teilzeichenfolgen](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Verwendet zum Zeitpunkt der Berichtserstellung Zeichenfolgenmanipulationen anstelle von Lookup-Datensätzen. |
| Benutzerdefinierte Anpassung von Sitzungen | Die benutzerdefinierte Sitzungserstellung kann über die [Sitzungseinstellungen](../../data-views/create-dataview.md#session-settings) in einer Datenansicht. Siehe  [Kontextbezogene Sitzungen](../../data-views/context-aware-sessions.md) für weitere Informationen. <br/>Die Verarbeitung mobiler Hintergrundereignisse wird über das Adobe Experience Platform Mobile SDK unterstützt. Siehe [Lebenszyklus für Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) für weitere Informationen. |
| Währungsumrechnung | Unterstützt im Rahmen der [Formatierung einer Metrikkomponente](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=de#currency) in einer Datenansicht. |
| Persistenz von Merchandising-Variablen | Vollständige Unterstützung über [Binding-Dimensionen und Binding-Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| Kundenattribute | Jetzt „Profildatensätze“ genannt. Sie werden nicht automatisch aus Experience Cloud importiert, sondern müssen in Experience Platform hochgeladen werden, damit sie in Customer Journey Analytics verfügbar sind. |
| Daten-Feeds | Der Datenexport der ersten Generation von Datensätzen ist über die [Experience Platform Data Access-API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=de) und [Experience Platform-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de) verfügbar. Diese Optionen ermöglichen den Export aller im Experience Platform Data Lake erfassten oder aufgenommenen Daten auf Ereignis-/Zeilenebene. Nachbearbeitungsprozess-Datenspalten sind nicht verfügbar, da Post-Spalten zur Abfragezeit berechnet werden. Der Export von Post-Spalten ist über das Reporting verfügbar. |
| Deduplizierung von Metriken | Nun für Metriken in Datenansichten konfiguriert. Die Metrik-Deduplizierung erfolgt auf Personen- oder Sitzungsebene und nicht auf Datensatz-, Datenansichts- oder Verbindungsebene. |
| Dimensionen und Metriken zu Eintritten, Austritten und aufgewendeter Zeit | Unterstützt (Eintritte und Austritte werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von Customer Journey Analytics. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dimensionen, die innerhalb von Datenansichten festgelegt werden, sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| IP-Verschleierung | Für Customer Journey Analytics-Kundinnen und -Kunden, die den Analytics-Quell-Connector verwenden, um Daten aus Adobe Analytics in Customer Journey Analytics zu übernehmen: Die in Adobe Analytics vorgenommenen Einstellungen zur IP-Verschleierung werden auf Ihre Customer Journey Analytics-Daten übertragen. Sie können diese Einstellungen nach Bedarf in Adobe Analytics steuern.<p>Für Customer Journey Analytics-Kundinnen oder -Kunden, die das Experience Platform Web SDK verwenden, um Daten direkt in Platform und Customer Journey Analytics aufzufüllen. Sie können die Datenvorbereitung für die Datenerfassung in Platform verwenden, um Regeln zu konfigurieren, die die IP-Adresse basierend auf den Anforderungen Ihres Unternehmens verschleiern. |
| Reporting über neue und wiederholte Sitzungen | Erfolgte bislang über die Dimension „Anzahl der Besuche“. Neue und wiederholte Sitzungen werden [mit einem 13-monatigen Lookback-Fenster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=de) unterstützt. |
| Produktvariable | In Experience Platform können Benutzer ein Array mit Objekttypfeldern in einem Datensatzschema verwenden, um die Anforderungen dieses Anwendungsfalls zu erfüllen. In Customer Journey Analytics können Kundinnen und Kunden eine beliebige Anzahl von Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf eine einzelne Variable beschränkt. |
| Projektfreigabe | Die Projektfreigabe wird nur zwischen Benutzenden von Customer Journey Analytics unterstützt. Es gibt keine Projektfreigabe zwischen Customer Journey Analytics und dem herkömmlichen Analysis Workspace. |
| Visualisierungen | Alle Visualisierungen mit Ausnahme der Zuordnungsvisualisierung werden unterstützt. |
| Report Builder (Excel-Plug-in) | Unterstützt mit einem neuen Office 365-Plug-in für Excel. |
| Benutzerberechtigungen/Datenzugriffssteuerung | Customer Journey Analytics unterscheidet zwischen [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=de)-Produktadmins, -Produktprofiladmins und -Benutzenden. Nur Produktadmins können von anderen Benutzenden erstellte Verbindungen, Projekte, Filter oder berechnete Metriken erstellen/aktualisieren/löschen, während Produktadmins und Produktprofiladmins Datenansichten bearbeiten können. Zusätzliche Benutzerberechtigungen sind für Vorgänge wie das Erstellen von berechneten Metriken, Filtern oder Anmerkungen verfügbar. |
| Verarbeitungsregeln, VISTA-Regeln, Verarbeitungsregeln für Marketing-Kanäle | Wird über die Adobe Experience Platform-Datenvorbereitungsfunktionen sowohl für Web SDK-basierte Datensätze als auch für Daten vom Analytics-Source-Connector unterstützt. |
| Marketing-Kanäle | Bei Verwendung des Analytics-Quell-Connectors fließen Marketing-Kanal-Daten über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie in der [Dokumentation zu Marketing-Kanälen von Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=de). <br/>Bei Web SDK-Implementierungen werden berichtszeitbezogene Verarbeitungsregeln für Marketing-Kanäle über [abgeleitete Felder](../../data-views/derived-fields/derived-fields.md) unterstützt. |

{style="table-layout:auto"}

## Teilweise Unterstützung {#partial}

| Funktion | Hinweise |
| --- | --- |
| Geräteübergreifende/kanalübergreifende Zuordnung | Unterstützt bei Datensätzen, die direkt Identitätsinformationen enthalten (auch als „feldbasiertes“ Stitching bezeichnet). Diagrammbasiertes Stitching wird noch nicht unterstützt, ist aber in Planung. Siehe [Zuordnung](../../stitching/overview.md). |
| Bot-Filterung | Bei Datensätzen, die auf dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) basieren, wird die Bot-Filterung angewendet. Die allgemeine Bot-Filterlogik für andere Datensätze wird weder von [!UICONTROL Experience Platform] noch von Customer Journey Analytics ausgeführt. |
| Dimensionen: Gerät, Browser, Referrer, Technologie | Unterstützt für [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de)-basierte Datensätze. Weitere Informationen finden Sie in der [Dokumentation, welche Analytics-Variablen über ADC unterstützt werden](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de).<p>Wenn Sie die Experience Platform Web SDK-Datenerfassung verwenden, werden Gerät und Dimensionen, die auf der Gerätesuche basieren, derzeit nicht unterstützt. Eine künftige Unterstützung ist geplant. |
| GeoSegmentation-Dimensionen | Alle in Adobe Analytics erfassten Daten zu GeoSegmentation/Geografie fließen über den [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) in Customer Journey Analytics. Implementierungen, die nicht den Analytics-Quell-Connector verwenden, aber für die digitale Datenerfassung auf das Experience Platform Web SDK angewiesen sind, können den [Service für Experience Edge-Geo-Suchen](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=de) nutzen. |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“ und „Analytics for Target“ (A4T) werden nicht unterstützt. |
| Verarbeitungsregeln | Auf Datensätze, die auf dem Analytics-Quell-Connector basieren, werden weiterhin Verarbeitungsregeln angewendet. [Datenvorbereitungsfunktionen in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) können auch als Ersatz für Verarbeitungsregeln für Daten verwendet werden, die direkt an Platform übermittelt werden. |
| A4T | Teilweise Unterstützung wird über Felder im [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) bereitgestellt. Die Unterstützung von A4T-gerechten Namen für die Zielgruppenaktivitäten und -erfahrungen ist geplant. |

{style="table-layout:auto"}

## Keine Unterstützung, aber geplant {#planned}

| Funktion | Hinweise |
| --- | --- |
| Warnhinweise | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Data Warehouse-Reporting | Die Unterstützung über die Analysis Workspace-Oberfläche ist geplant. Der [[!UICONTROL Abfrage-Service]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de>) von Adobe Experience Platform bietet auch eine Schnittstelle für diese Anwendungsfälle in Customer Journey Analytics. |
| ID-Zuordnung über Gerätediagramm | Unterstützung ist geplant. |
| Projektvorlagen | Unterstützung ist geplant. |
| Echtzeitberichterstellung | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Transaktions-ID-Datenquellen | Unterstützung ist geplant. |
| Migrieren von Projekten/Filtern/berechneten Metriken von Adobe Analytics nach Customer Journey Analytics | Unterstützung ist geplant. |
| Datenquellen auf Zusammenfassungsebene | Unterstützung ist geplant. |

{style="table-layout:auto"}

## Keine Unterstützung, noch nicht geplant {#not-planned}

| Funktion | Hinweise |
| --- | --- |
| Activity Map | Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Unterstützung ist noch nicht geplant. |

{style="table-layout:auto"}

## Nie unterstützt {#never}

* Benutzermetriken mit Cross-Device Coop
* Reports &amp; Analytics-Dashboards
* Reports &amp; Analytics-Lesezeichen
* Reports &amp; Analytics-Zielgruppen

## Adobe Customer Journey Analytics-Funktionen sind in Adobe Analytics nicht verfügbar {#cja-not-aa}

In der folgenden Tabelle sind Funktionen aufgeführt, die in Customer Journey Analytics verfügbar sind, in Adobe Analytics jedoch nicht unterstützt werden.

| Funktion | Mehr Infos |
| --- | --- |
| Verarbeitung von Daten jeder Art | Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des [Experience-Datenmodells (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Adobe Analytics konzentriert sich hauptsächlich auf Web-basierte und Mobile-Analysedaten, wobei verschiedene Funktionen für den [Datenimport](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=de) zur Verfügung stehen. |
| Unbegrenzte Dimensionen und Metriken für Kundinnen und Kunden | Customer Journey Analytics-Dimensionen sind unbegrenzt. Werte können Zahlen, Texte, Objekte und Listen aufweisen oder aus einer Kombination dieser Elemente bestehen. Dimensionen können verschachtelt oder hierarchisch aufgebaut sein. Analytics unterstützt maximal 75 Eigenschaften und 250 eVars. |
| Unbegrenzte Kardinalität/eindeutige Werte | Customer Journey Analytics unterstützt unbegrenzte eindeutige Werte oder Dimensionselemente, über die innerhalb einer Dimension berichtet werden kann. Adobe Analytics ist auf 500.000 eindeutige Werte begrenzt. Durch die unbegrenzten eindeutigen Werte oder Dimensionen werden die Reporting- und Analysebeschränkungen aufgehoben, die derzeit bei einer umfangreichen Analytics-Implementierung bestehen. |
| Umwandlungen zum Zeitpunkt der Berichtserstellung | Mit Umwandlungen zum Zeitpunkt der Berichtserstellung (besser bekannt als Datenansichten) in Customer Journey Analytics können Sie Daten aus einer Verbindung weitergehend interpretieren. Sie können Daten ohne erneute Implementierung ändern oder entfernen, mithilfe von Teilzeichenfolgen Dimensionen bearbeiten, Metriken aus einem beliebigen Wert erstellen und Teilereignisse filtern. Jedwede Umwandlung erfolgt zerstörungsfrei. Adobe Analytics bietet eingeschränkte Funktionen durch Virtual Report Suites und Anpassung von Sitzungen. |
| Experimentanalyse | Customer Journey Analytics kann Lift und Konfidenz jedes Experiments aus jeder Datenquelle bewerten, die als Teil einer Verbindung definiert wurde. Diese Auswertung ermöglicht Ihnen, die kausalen Zusammenhänge zwischen Kundeninteraktionen zu verstehen, die sich über alle Kanäle erstrecken. Analytics ist auf eine experimentelle Analyse durch die Analytics for Target(A4T)-Integration beschränkt. |
| Geräteübergreifende Analyse | Customer Journey Analytics unterstützt die nahtlose Kombination gerätespezifischer Datensätze aus nicht authentifizierten und authentifizierten Sitzungen. Customer Journey Analytics bietet die Möglichkeit, historische Daten auf bekannte Geräte aufzustocken. In Analytics ist diese Funktion auf eine einzige Report Suite und die Verwendung eines Gerätediagramms beschränkt. |
| SQL-Zugriff | Mit der Data Distiller-Option kann Customer Journey Analytics die Einschränkungen in Bezug auf die per Backend-Verarbeitung von Adobe erfassten Daten aufheben. Sie können Ihre Daten mit SQL ändern, unternehmensspezifische Werte und Datensätze erstellen und Ihre Entdeckungsreise fortsetzen. Analytics unterstützt keinen SQL-Zugriff auf seine Daten. |
| Verbesserte Sicherheits- und Datenschutzoptionen – HIPAA-Fähigkeit | Customer Journey Analytics ist HIPAA-fähig und bietet zusätzliche Sicherheitsoptionen für die Einhaltung von Vorschriften. Adobe Analytics ist nicht HIPAA-fähig. |

{style="table-layout:auto"}
