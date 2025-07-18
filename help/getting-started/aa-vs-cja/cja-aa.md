---
title: Unterstützung der Customer Journey Analytics-Funktionen
description: Erfahren Sie mehr über Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 78fab62b4f28a85986b5d7c537d321049f929897
workflow-type: tm+mt
source-wordcount: '2653'
ht-degree: 97%

---

# Unterstützung der Customer Journey Analytics-Funktionen

In den folgenden Tabellen ist aufgeführt, welche Funktionen spezifisch für Customer Journey Analytics sind und welche Adobe Analytics-Funktionen in Customer Journey Analytics unterstützt, teilweise unterstützt bzw. nicht unterstützt werden. Diese Listen ändern sich im Laufe der Zeit, wenn Funktionen zu Customer Journey Analytics hinzugefügt werden.

## Adobe Customer Journey Analytics-spezifische Funktionen {#cja-not-aa}

In der folgenden Tabelle sind Funktionen aufgeführt, die in Customer Journey Analytics verfügbar sind, in Adobe Analytics jedoch nicht unterstützt werden.

| Funktion | Mehr Infos |
| --- | --- |
| **Möglichkeit zur Kombination von Datensätzen (z. B. Report Suites von Adobe Analytics)** | Mit Customer Journey Analytics können Sie [Daten aus mehreren Report Suites so kombinieren](/help/connections/combined-dataset.md), als bildeten sie eine einzige Report Suite in Adobe Analytics. |
| **Verarbeitung von Daten jeder Art** | Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des [Experience-Datenmodells (XDM)](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home) können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Adobe Analytics konzentriert sich hauptsächlich auf Web-basierte und Mobile-Analysedaten, wobei verschiedene Funktionen für den [Datenimport](https://experienceleague.adobe.com/de/docs/analytics/import/home) zur Verfügung stehen. |
| **B2B Edition** | [Customer Journey Analytics B2B edition](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition?lang=en) unterstützt B2B-Unternehmen bei der Abstimmung ihrer Marketing-, Vertriebs- und Produkt-Teams, indem es umsetzbare Account Insights bereitstellt, die das Umsatzwachstum fördern. Wenn das Konto in den Mittelpunkt des Datenmodells gestellt wird, konzentriert sich die gesamte Analyse auf die Konto-Journey. Durch das Hinzufügen einer neuen Ebene von Entitäten (Konten, Opportunities und Käufergruppen) zu Personen- und zeitbasierten Ereignissen erhalten Sie ein vollständiges Bild vom Lebenszyklus des B2B-Marketings und Umsatzes. |
| **BI-Erweiterung** | Die [BI-Erweiterung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) ermöglicht es Ihnen, Customer Journey Analytics direkt mit gängigen BI-Visualisierungs-Tools wie PowerBI oder Tableau zu verbinden. Durch die Verwendung dieser Erweiterung können Sie Ihre BI-Berichte exakt mit der Anzeige in Analysis Workspace und anderen Reporting-Schnittstellen von Customer Journey Analytics abstimmen. Mit dieser Erweiterung können Sie BI-Berichte für Customer Journey Analytics wesentlich einfacher abrufen, ohne Berichte/Metriken aus Rohdaten neu erstellen zu müssen. |
| **Content Analytics** | Mit [Content Analytics](https://experienceleague.adobe.com/de/docs/analytics-platform/using/content-analytics/content-analytics) können Marketing-Fachleute nachvollziehen, wie sich Inhalte auf die von einem Unternehmen definierten wichtigsten Leistungsindikatoren auswirken. Zusätzlich zu den Verhaltensdaten erfasst Content Analytics Daten darüber, wie Inhalte konsumiert werden und wie Inhalte die Auswirkungen steuern.  |
| **Geräteübergreifende Analyse** | Customer Journey Analytics unterstützt die nahtlose Kombination gerätespezifischer Datensätze aus nicht authentifizierten und authentifizierten Sitzungen. Customer Journey Analytics bietet die Möglichkeit, historische Daten auf bekannte Geräte aufzustocken. In Adobe Analytics ist diese Funktion auf eine einzige Report Suite und die Verwendung eines Gerätediagramms beschränkt. |
| **Data Insights Agent** | Der [Data Insights Agent](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai?lang=en), Teil des KI-Assistenten in Customer Journey Analytics, ist ein generativer KI-Konversationsagent. Sie verwendet Komponenten aus Ihrer Datenansicht und Ihren tatsächlichen Daten, um datenorientierte Fragen schnell und effizient zu beantworten, indem relevante Visualisierungen in Analysis Workspace erstellt werden. |
| **Verbesserungen bei Dimensionen** | Customer Journey Analytics bietet mehr Flexibilität bei der Verwendung von Dimensionen: <ul><li>**Benutzerdefinierte numerisch basierte Dimensionen**: [Erstellen Sie Ihre eigenen numerisch basierten Dimensionen innerhalb einer Datenansicht](/help/data-views/create-dataview.md#components).</li><li>**Sortieren von String-basierten Dimensionen**: [Sortieren Sie String-basierte Dimensionen alphabetisch in einer Freiformtabelle.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>In Adobe Analytics waren nur eine Handvoll eingebauter numerischer Dimensionen verfügbar, und eine Sortierung nach String-basierten Dimensionen war nicht möglich.</p> |
| **Abgeleitete Felder** | [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md) ermöglichen Umwandlungen zum Zeitpunkt der Berichtserstellung für Ihre Daten. Daten können dynamisch kombiniert, korrigiert oder erstellt werden. Diese Umwandlungen gelten rückwirkend für alle Berichte. |
| **Verbesserte Sicherheits- und Datenschutzoptionen – HIPAA-Fähigkeit** | Customer Journey Analytics ist HIPAA-fähig und bietet [zusätzliche Sicherheitsoptionen](/help/privacy/cmk.md) für die Einhaltung von Vorschriften. Adobe Analytics ist nicht HIPAA-fähig. |
| **Experimentanalyse** | Customer Journey Analytics kann [Lift und Konfidenz jedes Experiments aus jeder Datenquelle bewerten](/help/analysis-workspace/c-panels/experimentation.md), die als Teil einer Verbindung definiert wurde. Diese Auswertung ermöglicht Ihnen, die kausalen Zusammenhänge zwischen Kundeninteraktionen zu verstehen, die sich über alle Kanäle erstrecken. Analytics ist auf die Experimentanalyse über A4T beschränkt. |
| **Prognose** | Die [Prognose](/help/analysis-workspace/c-forecast/forecasting.md) ist eine KI/ML-Funktion, die eine statistische Prognose für zeitreihenbezogene Daten enthält, die auf den bereits in Customer Journey Analytics vorhandenen historischen Daten basiert. Prognosen können in Freiformtabellen und Liniendiagrammvisualisierungen angezeigt werden. |
| **Geführte Analyse** | Mit [geführten Analysen](/help/guided-analysis/overview.md) können Benutzende hochwertige Daten und Erkenntnisse zur Customer Journey mithilfe geführter Workflows selbst bereitstellen, die auf den kanalübergreifenden Daten von Customer Journey Analytics basieren. |
| **Intelligente Untertitel** | [Intelligente Untertitel](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) verwenden erweitertes maschinelles Lernen und generative KI, um wertvolle Einblicke in natürliche Sprachen für Workspace-Visualisierungen bereitzustellen. Intelligente Untertitel werden für die folgenden Visualisierungen unterstützt: Zeile, Mehrzeilig, Balken, Horizontalbalken, Ringdiagramm, Fläche, Fluss und Fallout. |
| **Journey-Arbeitsfläche** | Die [Journey-Arbeitsfläche](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas?lang=de) ist eine Visualisierung in Analysis Workspace, mit der Sie analysieren können, wie Benutzende eine definierte Journey durchlaufen oder aus dieser aussteigen. |
| **Produktnutzung** | [Produktnutzung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/tools/product-usage/usage-overview) zeigt Ihnen, wie Ihre Organisation Customer Journey Analytics verwendet. |
| **Umwandlungen zum Zeitpunkt der Berichterstellung** | [Datenansichten](/help/data-views/data-views.md) in Customer Journey Analytics ermöglichen eine Interpretation von Daten aus einer Verbindung. Sie können Daten ändern oder entfernen, ohne die Implementierung zu ändern. Verwenden Sie Teilzeichenfolgen, um Dimensionen zu bearbeiten. Erstellen Sie Metriken aus einem beliebigen Wert oder filtern Sie Teilereignisse. Alle diese Umwandlungen erfolgen zerstörungsfrei. Adobe Analytics bietet begrenzte Möglichkeiten durch Virtual Report Suites und benutzerdefinierte Sitzungslängen. |
| **Freigegebene Metriken und Dimensionen in allen Datenansichten** | Freigegebene Metriken ermöglichen die [Anwendung von Dimensions- und Metrikeinstellungen auf mehrere Datenansichten](/help/data-views/shared-metrics-dimensions/smd-overview.md). Änderungen an einer freigegebenen Dimension oder Metrik gelten für alle Instanzen dieser Dimension oder Metrik in allen anwendbaren Datenansichten.  |
| **SQL-Zugriff** | Mit der Data Distiller-Option kann Customer Journey Analytics die Einschränkungen in Bezug auf die per Backend-Verarbeitung von Adobe erfassten Daten aufheben. Sie können Ihre Daten mit SQL ändern, unternehmensspezifische Werte und Datensätze erstellen und Ihre Entdeckungsreise fortsetzen. Analytics unterstützt keinen SQL-Zugriff auf seine Daten. |
| **Zuordnung** | Die [Zuordnung](/help/stitching/overview.md) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die kanalübergreifende Analyse erhöht. Cross-Channel-Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics verarbeiten kann. Mit Cross-Channel-Analyse können Sie Berichte auf der Grundlage einer gemeinsamen Kennung (Personen-ID) nahtlos für mehrere Datensätze aus verschiedenen Kanälen kombinieren und ausführen. |
| **Vorlagen in Adobe Journey Optimizer** | Passen Sie die neue Berichterstellungsoberfläche in Adobe Journey Optimizer an, indem Sie eine [Vorlage](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/templates/create-templates?lang=de) in Customer Journey Analytics erstellen oder bearbeiten und anschließend die Vorlage speichern, damit sie auf der Seite „Berichte“ in Journey Optimizer verwendet wird.  |
| **Unbegrenzte Kundendimensionen und -metriken** | Customer Journey Analytics-Dimensionen sind unbegrenzt. Werte können Zahlen, Texte, Objekte und Listen aufweisen oder aus einer Kombination dieser Elemente bestehen. Dimensionen können verschachtelt oder hierarchisch aufgebaut sein. <br/>Im Gegensatz dazu unterstützt Adobe Analytics maximal 75 Props und 250 eVars. |
| **Unbegrenzte eindeutige Werte** | Customer Journey Analytics unterstützt unbegrenzt eindeutige Werte oder Dimensionselemente, über die innerhalb einer Dimension berichtet werden kann.<p>Es gibt keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md), sodass eindeutige Werte angezeigt und gezählt werden können.</p><p>Durch diesen Ansatz werden Reporting- und Analysebeschränkungen aufgehoben, die bei einer umfangreichen Adobe Analytics-Implementierung bestehen können, was zu Kennzeichnungen [!UICONTROL Geringer Datenverkehr] führen kann.</p><p>In Customer Journey Analytics kann die Kennzeichnung [!UICONTROL Eindeutige Werte überschritten] angezeigt werden. Allerdings geschieht dies wesentlich seltener und kann durch die Anwendung eines Segments auf die Daten verhindert werden.</p> |

## Vollständig unterstützte Adobe Analytics-Funktionen/-Komponenten {#full-support}

| Adobe Analytics-Funktion | Hinweise zur Customer Journey Analytics-Unterstützung |
| --- | --- |
| **Anomalieerkennung** | Vollständige Unterstützung |
| **Asset-Übertragung** | Vollständige Unterstützung |
| **Attributionsfunktionen** | Vollständige Unterstützung |
| **Bot-Erkennung** | [Vollständige Unterstützung](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/bot-detection) |
| **Berechnete Metriken** | Vollständige Unterstützung. Vorhandene berechnete Metriken im herkömmlichen Analysis Workspace werden nicht nach Customer Journey Analytics portiert. |
| **Kalenderereignisse** | Vollständige Unterstützung. Kalenderereignisse wurden bisher als [Anmerkungen](/help/components/annotations/overview.md) in Workspace implementiert. |
| **CSV-Download** | Vollständige Unterstützung |
| **Benutzerdefinierte Kalender** | Vollständige Unterstützung |
| **Datumsvergleiche** | Vollständige Unterstützung |
| **Datumsbereiche** | Alle Datumsbereichsfunktionen werden unterstützt. |
| **Dimensionen** | Vollständige Unterstützung. Customer Journey Analytics verwendet XDM und unterstützt unbegrenzte Dimensionen. Customer Journey Analytics ist nicht an benutzerdefinierte eVars oder Eigenschaften des herkömmlichen Adobe Analytics-Tools gebunden. |
| **DSGVO-Löschung** | Vollständige Unterstützung; beachten Sie, dass die DSGVO jetzt in Abstimmung mit [!UICONTROL Adobe Experience Platform] gehandhabt wird. Customer Journey Analytics übernimmt alle Datenänderungen, die [!UICONTROL Experience Platform] an den zugrunde liegenden Datensätzen vornimmt. |
| **Reporting über Steigerung und Konfidenz** | Vollständige Unterstützung über das [Bedienfeld „Experimentierung“](/help/analysis-workspace/c-panels/experimentation.md) |
| **Listenvariablen/Listeneigenschaften** | Vollständige Unterstützung. Customer Journey Analytics nutzt XDM und unterstützt unbegrenzte Zeichenfolgen-Arrays, die ähnlich wie listVars verwendet werden können. |
| **Merchandising-eVars** | Vollständige Unterstützung über [Bindungsdimensionen und Bindungsmetriken](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Metriken** | Vollständige Unterstützung; Customer Journey Analytics nutzt das Experience-Datenmodell (XDM), unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse von Adobe Analytics gebunden. Beachten Sie, dass einige Standardmetriken in Adobe Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| **Migration von Projekten, Segmenten und berechneten Metriken von Adobe Analytics zu Customer Journey Analytics** | Vollständige Unterstützung.  |
| **Mobile Scorecard/Dashboards** | Vollständige Unterstützung |
| **Bedienfelder** | Vollständige Unterstützung für die folgenden Bedienfelder: Leeres Bedienfeld, „Attribution“, „Freiform“, „Quick Insights“ und „Nächstes oder vorheriges Element“. |
| **PDF-Export** | Vollständige Unterstützung |
| **Projektkuration** | Vollständige Unterstützung |
| **Projektverknüpfung** | Vollständige Unterstützung |
| **Produktvorlagen** | Enthält [vorkonfigurierte Vorlagen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/templates/use-templates) und [Firmenvorlagen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/templates/create-templates#access-a-company-template). |
| **Berichtszeitverarbeitung** | Vollständige Unterstützung; Customer Journey Analytics verlässt sich ausschließlich auf die Berichtszeitverarbeitung. |
| **Zugriff auf Reporting-API** | Vollständige Unterstützung; verfügbar über die [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/). |
| **Geplante Berichte/Projekte** | Vollständige Unterstützung |
| **Segmente** | Vollständige Unterstützung. Segmente werden in Customer Journey Analytics zuvor *Filter* genannt. |
| **Streaming Media Collection** | Streaming-Mediendaten sind über den Analytics-Quell-Connector als Teil des Bedienfelds „Gleichzeitige Medienbetrachter“ und des Bedienfelds „Bei Medienwiedergabe verbrachte Zeit“ in Workspace verfügbar. |
| **Datenquellen auf Zusammenfassungsebene** | Vollständige Unterstützung |
| **Virtual Report Suites** | Vollständige Unterstützung. [Datenansichten](/help/data-views/create-dataview.md) sind das Customer Journey Analytics-Äquivalent zu Report Suites in Adobe Analytics. |
| **Kuratierung von Virtual Report Suite-Komponenten** | Vollständige Unterstützung. Die Komponentenkuratierung ist Teil der Datenansichtsfunktion. |
| **Geräte-, Browser-, Referrer-, Technologie-Dimensionen** | Unterstützt sowohl für Datensätze, die auf dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/analytics) basieren, als auch für Datensätze, die vom Web SDK generiert werden. Weitere Informationen finden Sie in der [Dokumentation zu über ADC unterstützten Analytics-Variablen](https://experienceleague.adobe.com/de/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Wenn Sie die Datenerfassung mithilfe des Experience Platform Web SDK verwenden, werden Gerät und Dimensionen, die auf der Gerätesuche basieren, derzeit nicht unterstützt. Eine künftige Unterstützung ist geplant. Informationen zum Hinzufügen der Geräte- und Browser-Suche zu Ihrem Web SDK-Datenstrom finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure) |

## Auf neue Art unterstützt {#new-support}

| Funktion | Hinweise |
| --- | --- |
| **Advertising Cloud** | Sie können [historische Daten für AMO-IDs und EF-IDs zur Verwendung in Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/advertising/integrations/analytics/planning/rvars-to-evars) erfassen. |
| **Warnhinweise** | Die [Verwendung von Warnhinweisen in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. <p>Aufgrund des Zeitpunkts der Datenerfassung in Customer Journey Analytics sind stündliche Warnhinweise jedoch nicht verfügbar. In Customer Journey Analytics können tägliche, wöchentliche oder monatliche Warnhinweise konfiguriert werden.</p> |
| **Analytics for Target (A4T)** | Die [Integration zwischen Adobe Customer Journey Analytics und Target](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja) bietet Ihrem Optimierungsprogramm leistungsstarke Tools für Analysen und Zeitersparnisse. |
| **Zielgruppenveröffentlichung** | Wird unterstützt, sofern diese Funktion mit den Adobe-Produkten Customer Data Platform oder Journey Optimizer lizenziert wurde. [Zielgruppenveröffentlichung](/help/components/audiences/audiences-overview.md) sendet Zielgruppen an das Echtzeit-Kundenprofil in Experience Platform. |
| **Klassifizierungen** | Lookup-Datensätze entsprechen den Klassifizierungen in Adobe Analytics. In Analytics verwendete Klassifizierungen können mit dem Quell-Connector für Analytics-Klassifizierungen in Experience Platform und Customer Journey Analytics importiert werden. Suchdatensätze können auch direkt in Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| **Classification Rule Builder** | Unterstützt mit Verwendung von [Teilzeichenfolgen](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Verwendet zum Zeitpunkt der Berichtserstellung Zeichenfolgenmanipulationen anstelle von Lookup-Datensätzen. |
| **Benutzerdefinierte Sitzungslänge** | Die Sitzungslänge kann über [Sitzungseinstellungen](../../data-views/create-dataview.md#session-settings) in einer Datenansicht konfiguriert werden. Siehe [Komponenteneinstellungen](../../data-views/session-settings.md) für weitere Informationen. <br/>Die Handhabung mobiler Hintergrundereignisse wird über das Adobe Experience Platform Mobile SDK unterstützt. Siehe [Lebenszyklus für Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) für weitere Informationen. |
| **Währungsumrechnung** | Unterstützt im Rahmen der [Formatierung einer Metrikkomponente](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/component-settings/format) in einer Datenansicht. |
| **Kundenattribute** | Profildatensätze entsprechen der Kundenattribution. Profildatensätze werden nicht automatisch aus Experience Cloud importiert, sondern müssen in Experience Platform hochgeladen werden, damit sie in Customer Journey Analytics verfügbar sind. |
| **Daten-Feeds** | Der Datenexport der ersten Generation von Datensätzen ist über die [Experience Platform Data Access-API](https://experienceleague.adobe.com/de/docs/experience-platform/data-access/api) und [Experience Platform-Ziele](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/ui/activate/export-datasets) verfügbar. Diese Optionen ermöglichen den Export aller im Experience Platform Data Lake erfassten oder aufgenommenen Daten auf Ereignis-/Zeilenebene. Spalten zur Nachbearbeitung von Daten sind nicht verfügbar, da Post-Spalten zur Abfragezeit berechnet werden. Der Export von Post-Spalten ist über das Reporting verfügbar. |
| **Data Warehouse-Reporting** | [Der vollständige Tabellenexport von Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) ist die Weiterentwicklung von Data Warehouse-Berichten in Adobe Analytics, mit vielen neuen, häufig angeforderten Funktionen, die heute nicht in Data Warehouse verfügbar sind. |
| **Dimensionen und Metriken zu Eintritten, Ausstiege und Verweildauer** | Unterstützt (Eintritte und Austritte werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |
| **eVar-Persistenzeinstellungen** | eVars sind nicht mehr Teil von Customer Journey Analytics. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dimensionen, die innerhalb von Datenansichten festgelegt werden, sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| **Geo-Segmentierungsdimensionen** | [Vollständige Unterstützung](https://experienceleague.adobe.com/de/docs/experience-platform/datastreams/configure) |
| **Grafikbasierte Zuordnung** | Durch die [grafikbasierte Zuordnung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/overview#graph-based-stitching) können Sie die Leistungsfähigkeit des Identitätsdiagramms in [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/de/docs/experience-platform/identity/home) nutzen, um Datensätze auf ihre bevorzugte Identität zu bringen. |
| **Warnhinweise** | Die Verwendung von [Warnhinweisen](/help/components/c-intelligent-alerts/intelligent-alerts.md) in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch [wichtige Unterschiede](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/alerts/alerts-feature-comparison). |
| **IP-Verschleierung** | Für Customer Journey Analytics-Kundinnen und -Kunden, die den Analytics-Quell-Connector verwenden, um Daten aus Adobe Analytics in Customer Journey Analytics zu übernehmen: Die in Adobe Analytics vorgenommenen Einstellungen zur IP-Verschleierung werden auf Ihre Customer Journey Analytics-Daten übertragen. Sie können diese Einstellungen nach Bedarf in Adobe Analytics steuern.<p>Für Customer Journey Analytics-Kundinnen oder -Kunden, die das Experience Platform Web SDK verwenden, um Daten direkt in Platform und Customer Journey Analytics aufzufüllen. Sie können die Datenvorbereitung für die Datenerfassung in Platform verwenden, um Regeln zu konfigurieren, die die IP-Adresse basierend auf den Anforderungen Ihres Unternehmens verschleiern. |
| **Marketing-Kanäle** | Bei Verwendung des Analytics-Quell-Connectors fließen Marketing-Kanal-Daten über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Marketing-Kanäle von Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels). <br/>Bei Web SDK-Implementierungen werden berichtszeitbezogene Verarbeitungsregeln für Marketing-Kanäle über [abgeleitete Felder](../../data-views/derived-fields/derived-fields.md) unterstützt. |
| **Persistenz von Merchandising-Variablen** | Vollständige Unterstützung über [Bindungsdimensionen und Bindungsmetriken](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Deduplizierung einer Metrik** | Für Metriken in Datenansichten konfiguriert. Die Metrik-Deduplizierung erfolgt auf Personen- oder Sitzungsebene und nicht auf Datensatz-, Datenansichts- oder Verbindungsebene. |
| **Reporting über neue bzw. wiederholte Sitzungen** | Erfolgte bislang über die Dimension „Anzahl der Besuche“. Neue und wiederholte Sitzungen werden [mit einem 13-monatigen Lookback-Fenster](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases) unterstützt. |
| **Verarbeitungsregeln, VISTA-Regeln, Verarbeitungsregeln für Marketing-Kanäle** | Wird über die Datenvorbereitungsfunktionen von Adobe Experience Platform und [abgeleitete Felder](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-dataviews/derived-fields) sowohl für Web SDK-basierte Datensätze als auch für Daten vom Analytics-Quell-Connector unterstützt. |
| **Variable „products“** | In Experience Platform können Benutzende ein Array von Objekten in einem Datensatzschema verwenden, um diesen Anwendungsfall zu erfüllen. In Customer Journey Analytics können Kundinnen und Kunden eine beliebige Anzahl von Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf eine einzelne Variable beschränkt. |
| **Projektfreigabe** | Die Projektfreigabe wird nur zwischen Benutzenden von Customer Journey Analytics unterstützt. Es gibt keine Projektfreigabe zwischen Customer Journey Analytics und dem herkömmlichen Analysis Workspace. |
| **Report Builder** | Unterstützt mit einem neuen Office 365-Plug-in für Microsoft Excel. |
| **Benutzerberechtigungen/Datenzugriffssteuerung** | Customer Journey Analytics unterscheidet zwischen Produktadmins, Produktprofiladmins und Benutzenden von [Adobe Admin Console](https://experienceleague.adobe.com/de/docs/core-services/interface/administration/admin-tool-experience-cloud). Nur Produktadmins können Verbindungen, Projekte, Segmente oder berechnete Metriken, die von anderen Benutzenden erstellt wurden, erstellen, aktualisieren und löschen. Produktadmins und Produktprofiladmins können Datenansichten bearbeiten. Zusätzliche Benutzerberechtigungen sind für Vorgänge wie das Erstellen von berechneten Metriken, Segmenten oder Anmerkungen verfügbar. |
| **Visualisierungen** | Mit Ausnahme der Zuordnungsvisualisierung werden alle Workspace-Visualisierungen unterstützt. |
| **Geräte-/kanalübergreifendes Stitching** | Wird für Ereignisdatensätze unterstützt, die Identitätsinformationen enthalten. Siehe [Zuordnung](../../stitching/overview.md). |

## Teilweise Unterstützung {#partial}

| Funktion | Hinweise |
| --- | --- |
| **Workspace-Panels** | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“ und „Analytics for Target“ (A4T) werden nicht unterstützt. |

## Keine Unterstützung, aber geplant {#planned}

| Funktion | Hinweise |
| --- | --- |
| **Echtzeit-Reporting** | Unterstützung ist geplant. |
| **Transaktions-ID-Datenquellen** | Unterstützung ist geplant. |

## Keine Unterstützung, noch nicht geplant {#not-planned}

| Funktion | Hinweise |
| --- | --- |
| **Activity Map** | Unterstützung ist noch nicht geplant. |
| **Beitragsanalyse** | Unterstützung ist noch nicht geplant. |

## Keine Unterstützung geplant {#never}

* Benutzermetriken mit Cross-Device Coop
* Trigger
