---
title: Unterstützung der Customer Journey Analytics-Funktion
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 1cf7ae6635f51f0ca06cbc235032525e3d9b3fec
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 99%

---

# Unterstützung der Customer Journey Analytics-Funktion

In den folgenden Tabellen ist aufgeführt, welche Funktionen spezifisch für Customer Journey Analytics sind und welche Adobe Analytics-Funktionen in Customer Journey Analytics unterstützt, teilweise unterstützt oder nicht unterstützt werden. Diese Listen ändern sich im Laufe der Zeit, wenn Funktionen zu Customer Journey Analytics hinzugefügt werden.

## Adobe Customer Journey Analytics-spezifische Funktionen {#cja-not-aa}

In der folgenden Tabelle sind Funktionen aufgeführt, die in Customer Journey Analytics verfügbar sind, in Adobe Analytics jedoch nicht unterstützt werden.

| Funktion | Mehr Infos |
| --- | --- |
| **Möglichkeit zur Kombination von Datensätzen (z. B. Report Suites von Adobe Analytics)** | Mit Customer Journey Analytics können Sie [Daten aus mehreren Report Suites so kombinieren](/help/connections/combined-dataset.md), als bildeten sie eine einzige Report Suite in Adobe Analytics. |
| **Verarbeitung von Daten jeder Art** | Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des [Experience-Datenmodells (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Adobe Analytics konzentriert sich hauptsächlich auf Web-basierte und Mobile-Analysedaten, wobei verschiedene Funktionen für den [Datenimport](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=de) zur Verfügung stehen. |
| **Geräteübergreifende Analyse** | Customer Journey Analytics unterstützt die nahtlose Kombination gerätespezifischer Datensätze aus nicht authentifizierten und authentifizierten Sitzungen. Customer Journey Analytics bietet die Möglichkeit, historische Daten auf bekannte Geräte aufzustocken. In Adobe Analytics ist diese Funktion auf eine einzige Report Suite und die Verwendung eines Gerätediagramms beschränkt. |
| **Verbesserungen bei Dimensionen** | Customer Journey Analytics bietet mehr Flexibilität bei der Verwendung von Dimensionen: <ul><li>**Benutzerdefinierte numerisch basierte Dimensionen**: [Erstellen Sie Ihre eigenen numerisch basierten Dimensionen innerhalb einer Datenansicht](/help/data-views/create-dataview.md#components).</li><li>**Sortieren von String-basierten Dimensionen**: [Sortieren Sie String-basierte Dimensionen alphabetisch in einer Freiformtabelle.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>In Adobe Analytics waren nur eine Handvoll eingebauter numerischer Dimensionen verfügbar, und eine Sortierung nach String-basierten Dimensionen war nicht möglich.</p> |
| **Abgeleitete Felder** | [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md) ermöglichen Umwandlungen zum Zeitpunkt der Berichtserstellung für Ihre Daten. Daten können dynamisch kombiniert, korrigiert oder erstellt werden. Diese Umwandlungen gelten rückwirkend für alle Berichte. |
| **Verbesserte Sicherheits- und Datenschutzoptionen – HIPAA-Fähigkeit** | Customer Journey Analytics ist HIPAA-fähig und bietet [zusätzliche Sicherheitsoptionen](/help/privacy/cmk.md) für die Einhaltung von Vorschriften. Adobe Analytics ist nicht HIPAA-fähig. |
| **Experimentanalyse** | Customer Journey Analytics kann [Lift und Konfidenz jedes Experiments aus jeder Datenquelle bewerten](/help/analysis-workspace/c-panels/experimentation.md), die als Teil einer Verbindung definiert wurde. Diese Auswertung ermöglicht Ihnen, die kausalen Zusammenhänge zwischen Kundeninteraktionen zu verstehen, die sich über alle Kanäle erstrecken. Analytics ist auf die Experimentanalyse über A4T beschränkt. |
| **Prognose** | Die [Prognose](/help/analysis-workspace/c-forecast/forecasting.md) ist eine KI/ML-Funktion, die eine statistische Prognose für zeitreihenbezogene Daten enthält, die auf den bereits in Customer Journey Analytics vorhandenen historischen Daten basiert. Prognosen können in Freiformtabellen und Liniendiagrammvisualisierungen angezeigt werden. |
| **Geführte Analyse** | Mit [geführten Analysen](/help/guided-analysis/overview.md) können Benutzende hochwertige Daten und Erkenntnisse zur Customer Journey mithilfe geführter Workflows selbst bereitstellen, die auf den kanalübergreifenden Daten von Customer Journey Analytics basieren. |
| **Intelligente Untertitel** | Intelligente Untertitel verwenden fortschrittliches maschinelles Lernen und generative KI, um wertvolle Einblicke in natürliche Sprachen für Workspace-Visualisierungen bereitzustellen. Die erste Version bietet automatisch generierte Einblicke für die Visualisierung [Linie](/help/analysis-workspace/visualizations/line.md). |
| **Umwandlungen zum Zeitpunkt der Berichtserstellung** | [Datenansichten](/help/data-views/data-views.md) in Customer Journey Analytics ermöglichen eine weiter gehende Interpretation von Daten aus einer Verbindung. Sie können Daten ändern oder entfernen, ohne Ihre Implementierung zu ändern, Teilzeichenfolgen verwenden, um Dimensionen zu bearbeiten, Metriken aus beliebigen Werten erstellen oder Teilereignisse filtern. Alle diese Umwandlungen erfolgen zerstörungsfrei. Adobe Analytics bietet begrenzte Möglichkeiten durch Virtual Report Suites und benutzerdefinierte Sitzungslängen. |
| **BI-Erweiterung** | Die [BI-Erweiterung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) ermöglicht Ihnen, CJA direkt mit gängigen BI-Visualisierungs-Tools wie PowerBI oder Tableau zu verbinden. Durch die Verwendung dieser Erweiterung können Sie Ihre BI-Berichte exakt mit der Anzeige in Analysis Workspace und anderen CJA-Reporting-Schnittstellen abstimmen. Auf diese Weise können Sie BI-Berichte für CJA wesentlich einfacher abrufen, ohne Berichte/Metriken aus Rohdaten neu erstell zu müssen. |
| **SQL-Zugriff** | Mit der Data Distiller-Option kann Customer Journey Analytics die Einschränkungen in Bezug auf die per Backend-Verarbeitung von Adobe erfassten Daten aufheben. Sie können Ihre Daten mit SQL ändern, unternehmensspezifische Werte und Datensätze erstellen und Ihre Entdeckungsreise fortsetzen. Analytics unterstützt keinen SQL-Zugriff auf seine Daten. |
| **Zuordnung** | Die [Zuordnung](/help/stitching/overview.md) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die kanalübergreifende Analyse erhöht. Die kanalübergreifende Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics handhaben kann. So können Sie Berichte auf Basis einer gemeinsamen Kennung (Personen-ID) nahtlos kombinieren und für mehrere Datensätze aus verschiedenen Kanälen ausführen. |
| **Unbegrenzte Kundendimensionen und -metriken** | Customer Journey Analytics-Dimensionen sind unbegrenzt. Werte können Zahlen, Texte, Objekte und Listen aufweisen oder aus einer Kombination dieser Elemente bestehen. Dimensionen können verschachtelt oder hierarchisch aufgebaut sein. <br/>Im Gegensatz dazu unterstützt Adobe Analytics maximal 75 Props und 250 eVars. |
| **Unbegrenzte eindeutige Werte** | Customer Journey Analytics unterstützt unbegrenzt eindeutige Werte oder Dimensionselemente, über die innerhalb einer Dimension berichtet werden kann.<p>Es gibt keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md), sodass eindeutige Werte angezeigt und gezählt werden können.</p><p>Durch diesen Ansatz werden Reporting- und Analysebeschränkungen aufgehoben, die bei einer umfangreichen Adobe Analytics-Implementierung bestehen können, was zu Kennzeichnungen [!UICONTROL Geringer Datenverkehr] führen kann.</p><p>In Customer Journey Analytics kann eine Kennzeichnung [!UICONTROL Eindeutige Werte überschritten] angezeigt werden, allerdings geschieht dies wesentlich seltener und kann durch die Anwendung eines Filters oder Segments auf die Daten verhindert werden.</p> |

## Vollständig unterstützte Adobe Analytics-Funktionen/-Komponenten {#full-support}

| Adobe Analytics-Funktion | Hinweise zur Unterstützung |
| --- | --- |
| **Anomalieerkennung** | Vollständige Unterstützung |
| **Attribution IQ** | Vollständige Unterstützung |
| **Bot-Erkennung** | [Vollständige Unterstützung](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=de) |
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
| **Merchandising-eVars** | Vollständige Unterstützung über [Bindungsdimensionen und Bindungsmetriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| **Metriken** | Vollständige Unterstützung; Customer Journey Analytics nutzt das Experience-Datenmodell (XDM), unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse von Adobe Analytics gebunden. Beachten Sie, dass einige Standardmetriken in Adobe Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| **Migration von Projekten, Filtern und berechneten Metriken von Adobe Analytics zu Customer Journey Analytics** | Vollständige Unterstützung.  |
| **Mobile Scorecard/Dashboards** | Vollständige Unterstützung |
| **Bedienfelder** | Vollständige Unterstützung für die folgenden Bedienfelder: Leeres Bedienfeld, „Attribution“, „Freiform“, „Quick Insights“ und „Nächstes oder vorheriges Element“. |
| **PDF-Export** | Vollständige Unterstützung |
| **Projektkuration** | Vollständige Unterstützung |
| **Projektverknüpfung** | Vollständige Unterstützung |
| **Berichtszeitverarbeitung** | Vollständige Unterstützung; Customer Journey Analytics verlässt sich ausschließlich auf die Verarbeitung zum Zeitpunkt der Berichtserstellung. |
| **Zugriff auf Reporting-API** | Vollständige Unterstützung; verfügbar über die [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/). |
| **Geplante Berichte/Projekte** | Vollständige Unterstützung |
| **Segmente** | Vollständige Unterstützung. Jetzt „Filter“ genannt. Beachten Sie, dass keine vorhandenen Segmente im herkömmlichen Analysis Workspace nach Customer Journey Analytics portiert werden. |
| **Streaming Media Collection-Add-on** | Streaming-Mediendaten sind über den Analytics-Quell-Connector als Teil des Bedienfelds „Gleichzeitige Medienbetrachter“ und des Bedienfelds „Bei Medienwiedergabe verbrachte Zeit“ in Workspace verfügbar. |
| **Datenquellen auf Zusammenfassungsebene** | Vollständige Unterstützung |
| **Virtual Report Suites** | Vollständige Unterstützung. Jetzt [Datenansichten](/help/data-views/create-dataview.md) genannt. |
| **Kuratierung von Virtual Report Suite-Komponenten** | Vollständige Unterstützung. Jetzt Teil der Datenansichten. |
| **Geräte-, Browser-, Referrer-, Technologie-Dimensionen** | Unterstützt sowohl für Datensätze, die auf dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) basieren, als auch für Datensätze, die vom Web SDK generiert werden. Weitere Informationen finden Sie in der [Dokumentation zu über ADC unterstützten Analytics-Variablen](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de). Wenn Sie die Datenerfassung mithilfe des Experience Platform Web SDK verwenden, werden Gerät und Dimensionen, die auf der Gerätesuche basieren, derzeit nicht unterstützt. Eine künftige Unterstützung ist geplant. Informationen zum Hinzufügen der Geräte- und Browser-Suche zu Ihrem Web SDK-Datenstrom finden Sie in [dieser Dokumentation](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=de) |

## Auf neue Art unterstützt {#new-support}

| Funktion | Hinweise |
| --- | --- |
| **Advertising Cloud** | Sie können [ historische Daten für AMO-IDs und EF-IDs zur Verwendung in Adobe Customer Journey Analytics erfassen](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/planning/rvars-to-evars) |
| **Warnhinweise** | Die [Verwendung von Warnhinweisen in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. <p>Aufgrund des Zeitpunkts der Datenerfassung in Customer Journey Analytics sind stündliche Warnhinweise jedoch nicht verfügbar. In Customer Journey Analytics können tägliche, wöchentliche oder monatliche Warnhinweise konfiguriert werden.</p> |
| **Analytics for Target (A4T)** | Die [Integration zwischen Adobe Customer Journey Analytics und Target](https://experienceleague.adobe.com/de/docs/target/using/integrate/cja/target-reporting-in-cja) bietet Ihrem Optimierungsprogramm leistungsstarke Tools für Analysen und Zeitersparnisse. |
| **Zielgruppenveröffentlichung** | Wird unterstützt, sofern diese Funktion mit den Adobe-Produkten Customer Data Platform oder Journey Optimizer lizenziert wurde. [Zielgruppenveröffentlichung](/help/components/audiences/audiences-overview.md) sendet Zielgruppen an das Echtzeit-Kundenprofil in Experience Platform. |
| **Klassifizierungen** | Jetzt „Lookup-Datensätze“ genannt. In Analytics verwendete Klassifizierungen können mit dem Quell-Connector für Analytics-Klassifizierungen in Experience Platform und Customer Journey Analytics importiert werden. Suchdatensätze können auch direkt in Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| **Classification Rule Builder** | Unterstützt mit Verwendung von [Teilzeichenfolgen](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Verwendet zum Zeitpunkt der Berichtserstellung Zeichenfolgenmanipulationen anstelle von Lookup-Datensätzen. |
| **Benutzerdefinierte Sitzungslänge** | Die Sitzungslänge kann über [Sitzungseinstellungen](../../data-views/create-dataview.md#session-settings) in einer Datenansicht konfiguriert werden. Siehe [Komponenteneinstellungen](../../data-views/session-settings.md) für weitere Informationen. <br/>Die Handhabung mobiler Hintergrundereignisse wird über das Adobe Experience Platform Mobile SDK unterstützt. Siehe [Lebenszyklus für Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) für weitere Informationen. |
| **Währungsumrechnung** | Unterstützt im Rahmen der [Formatierung einer Metrikkomponente](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=de#currency) in einer Datenansicht. |
| **Kundenattribute** | Jetzt „Profildatensätze“ genannt. Sie werden nicht automatisch aus Experience Cloud importiert, sondern müssen in Experience Platform hochgeladen werden, damit sie in Customer Journey Analytics verfügbar sind. |
| **Daten-Feeds** | Der Datenexport der ersten Generation von Datensätzen ist über die [Experience Platform Data Access-API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=de) und [Experience Platform-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de) verfügbar. Diese Optionen ermöglichen den Export aller im Experience Platform Data Lake erfassten oder aufgenommenen Daten auf Ereignis-/Zeilenebene. Spalten zur Nachbearbeitung von Daten sind nicht verfügbar, da Post-Spalten zur Abfragezeit berechnet werden. Der Export von Post-Spalten ist über das Reporting verfügbar. |
| **Data Warehouse-Reporting** | [Der vollständige Tabellenexport von Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) ist die Weiterentwicklung von Data Warehouse-Berichten in Adobe Analytics, mit vielen neuen, häufig angeforderten Funktionen, die heute nicht in Data Warehouse verfügbar sind. |
| **Dimensionen und Metriken zu Eintritten, Ausstiege und Verweildauer** | Unterstützt (Eintritte und Austritte werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |
| **eVar-Persistenzeinstellungen** | eVars sind nicht mehr Teil von Customer Journey Analytics. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dimensionen, die innerhalb von Datenansichten festgelegt werden, sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| **Geosegmentations-Dimensionen** | [Vollständige Unterstützung](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=de) |
| **Grafikbasierte Zuordnung** | Durch die [grafikbasierte Zuordnung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/overview#graph-based-stitching) können Sie die Leistungsfähigkeit des Identitätsdiagramms in [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/de/docs/experience-platform/identity/home) nutzen, um Datensätze auf ihre bevorzugte Identität zu bringen. |
| **Warnhinweise** | Die Verwendung von [Warnhinweisen](/help/components/c-intelligent-alerts/intelligent-alerts.md) in Customer Journey Analytics ist nahezu identisch mit der Verwendung von Warnhinweisen in Adobe Analytics. Es gibt jedoch [wichtige Unterschiede](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/alerts/alerts-feature-comparison). |
| **IP-Verschleierung** | Für Customer Journey Analytics-Kundinnen und -Kunden, die den Analytics-Quell-Connector verwenden, um Daten aus Adobe Analytics in Customer Journey Analytics zu übernehmen: Die in Adobe Analytics vorgenommenen Einstellungen zur IP-Verschleierung werden auf Ihre Customer Journey Analytics-Daten übertragen. Sie können diese Einstellungen nach Bedarf in Adobe Analytics steuern.<p>Für Customer Journey Analytics-Kundinnen oder -Kunden, die das Experience Platform Web SDK verwenden, um Daten direkt in Platform und Customer Journey Analytics aufzufüllen. Sie können die Datenvorbereitung für die Datenerfassung in Platform verwenden, um Regeln zu konfigurieren, die die IP-Adresse basierend auf den Anforderungen Ihres Unternehmens verschleiern. |
| **Marketing-Kanäle** | Bei Verwendung des Analytics-Quell-Connectors fließen Marketing-Kanal-Daten über diesen Connector in Customer Journey Analytics. Regeln für Marketing-Kanäle werden im herkömmlichen Adobe Analytics-Tool konfiguriert, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Marketing-Kanäle von Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=de). <br/>Bei Web SDK-Implementierungen werden berichtszeitbezogene Verarbeitungsregeln für Marketing-Kanäle über [abgeleitete Felder](../../data-views/derived-fields/derived-fields.md) unterstützt. |
| **Persistenz von Merchandising-Variablen** | Vollständige Unterstützung über [Bindungsdimensionen und Bindungsmetriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| **Deduplizierung einer Metrik** | Nun für Metriken in Datenansichten konfiguriert. Die Metrik-Deduplizierung erfolgt auf Personen- oder Sitzungsebene und nicht auf Datensatz-, Datenansichts- oder Verbindungsebene. |
| **Reporting über neue bzw. wiederholte Sitzungen** | Erfolgte bislang über die Dimension „Anzahl der Besuche“. Neue und wiederholte Sitzungen werden [mit einem 13-monatigen Lookback-Fenster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=de) unterstützt. |
| **Verarbeitungsregeln, VISTA-Regeln, Verarbeitungsregeln für Marketing-Kanäle** | Wird über die Datenvorbereitungsfunktionen von Adobe Experience Platform und [abgeleitete Felder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=de) sowohl für Web SDK-basierte Datensätze als auch für Daten vom Analytics-Quell-Connector unterstützt. |
| **Variable „products“** | In Experience Platform können Benutzende ein Array von Objekten in einem Datensatzschema verwenden, um diesen Anwendungsfall zu erfüllen. In Customer Journey Analytics können Kundinnen und Kunden eine beliebige Anzahl von Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf eine einzelne Variable beschränkt. |
| **Projektfreigabe** | Die Projektfreigabe wird nur zwischen Benutzenden von Customer Journey Analytics unterstützt. Es gibt keine Projektfreigabe zwischen Customer Journey Analytics und dem herkömmlichen Analysis Workspace. |
| **Report Builder** | Unterstützt mit einem neuen Office 365-Plug-in für Excel. |
| **Benutzerberechtigungen/Datenzugriffssteuerung** | Customer Journey Analytics unterscheidet zwischen Produktadmins, Produktprofiladmins und Benutzenden von [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=de). Nur Produktadmins können von anderen Benutzenden erstellte Verbindungen, Projekte, Filter oder berechnete Metriken erstellen/aktualisieren/löschen, während Produktadmins und Produktprofiladmins Datenansichten bearbeiten können. Zusätzliche Benutzerberechtigungen sind für Vorgänge wie das Erstellen von berechneten Metriken, Filtern oder Anmerkungen verfügbar. |
| **Visualisierungen** | Mit Ausnahme der Zuordnungsvisualisierung werden alle Workspace-Visualisierungen unterstützt. |
| **Geräte-/kanalübergreifendes Stitching** | Wird für Ereignisdatensätze unterstützt, die Identitätsinformationen enthalten. Siehe [Zuordnung](../../stitching/overview.md). |

## Teilweise Unterstützung {#partial}

| Funktion | Hinweise |
| --- | --- |
| **Bedienfelder** | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“ und „Analytics for Target“ (A4T) werden nicht unterstützt. |

## Keine Unterstützung, aber geplant {#planned}

| Funktion | Hinweise |
| --- | --- |
| **Beitragsanalyse** | Unterstützung ist geplant. |
| **Projektvorlagen** | Unterstützung ist geplant. |
| **Echtzeit-Reporting** | Unterstützung ist geplant. |
| **Segment IQ** | Unterstützung ist geplant. |
| **Transaktions-ID-Datenquellen** | Unterstützung ist geplant. |

## Keine Unterstützung, noch nicht geplant {#not-planned}

| Funktion | Hinweise |
| --- | --- |
| **Activity Map** | Unterstützung ist noch nicht geplant. |

## Keine Unterstützung geplant {#never}

* Benutzermetriken mit Cross-Device Coop
