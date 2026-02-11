---
title: Aktuelle Versionshinweise zu Customer Journey Analytics
description: Anzeigen der neuesten Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e98a1abbab4b954df5f7759879203c1d355fd50
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 34%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (Februar 2026)

**Letztes Update**: Donnerstag, 11. Februar 2026

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom Februar 2026. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion und Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ------- | ---- |
| **Überschreibungen der Kopfzeile** <p>In Content Analytics können Sie einen Kopfzeilennamen und einen geheimen Kopfzeilenwert angeben. Dieser [Header überschreibt die Konfiguration](/help/content-analytics/config/guided.md#header-overrides) stellt sicher, dass Content Analytics benutzerdefinierte HTTP-Header sendet, um alle implementierten Bot-Erkennungs- oder Gate-Traffic-Technologien zu umgehen.</p> |  | Dienstag, 2. Februar 2026 |
| **Mehrere Dimensionsspalten in eine Freiformtabelle einbeziehen**<p>Sie können jetzt bis zu 5 Dimensionsspalten in eine Freiformtabelle einbeziehen, sodass Sie mehrere Dimensionselemente nebeneinander anzeigen können. Jede Reihe von Dimensionselementen verhält sich wie ein einzelnes verkettetes Dimensionselement.</p><p>Sie können Filter, Sortierung, Aufschlüsselungen und mehr auf Freiformtabellen mit mehreren Dimensionsspalten anwenden, um eine tiefere und benutzerspezifischere Analyse zu erstellen.</p><p>Zuvor konnten Sie nur eine Dimensionsspalte in eine Freiformtabelle einbeziehen.</p><p>Weitere Informationen finden Sie unter [Mehrere Dimensionsspalten in eine Freiformtabelle einbeziehen](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | Donnerstag, 28. Januar 2026 | Donnerstag, 18. Februar 2026 |
| **Sortieren von Tabellen nach mehreren Spalten**<p>Sie können jetzt die Daten einer Freiformtabelle in Analysis Workspace nach mehreren Spalten sortieren, unabhängig davon, ob es sich um Dimensionen oder Metriken handelt.</p><p>Wenn Sie Daten für mehrere Spalten sortieren, werden die Daten nach der Priorität sortiert, die Sie jeder Spalte zuweisen. Die Prioritätsnummerierung wird neben dem Sortiersymbol angezeigt.</p><p>Weitere Informationen finden Sie unter [Filtern und Sortieren von Freiformtabellen](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | Donnerstag, 28. Januar 2026 | Donnerstag, 18. Februar 2026 |
| **Verbesserungen beim vollständigen Tabellenexport**<p>Der vollständige Tabellenexport umfasst die folgenden Verbesserungen:</p><p>Verbesserungen bei der Exportentwicklung und -konfiguration</p><ul><li>Erstellen Sie einen Export über die Seite Exporte . Zuvor war es nur möglich, einen Export aus Analysis Workspace zu erstellen, indem mit der rechten Maustaste auf die Tabelle geklickt wurde.</li><li>Fügen Sie beim Erstellen eines Exports ein neues Konto oder einen neuen Speicherort hinzu.</li><li>Automatisieren Sie die Erstellung von Dateinamen und die Ordnerplatzierung exportierter Dateien. Dadurch können Dateinamen vorhersehbar sein und logisch in Ordnern organisiert werden. Zuvor waren Dateinamen unvorhersehbar und wurden in einem Ordner gruppiert.</li><li>Unterstützung für den Export von Daten als Parquet-Dateien für verbesserte Data Warehouse-Kompatibilität. Zuvor wurden nur CSV und JSON unterstützt.</li></ul><p>Verbesserungen bei der Exportverwaltung</p><ul><li>Erneuern oder Abbrechen von einem oder mehreren Exporten auf der Seite Exporte .</li><li>Senden Sie einen oder mehrere Exporte erneut über die Seite „Protokolle“.</li><li>Senden Sie eine E-Mail an einzelne Benutzer oder Gruppen, wenn ein Export fehlschlägt oder bald abläuft.</li><li>Genauere Fehlermeldungen für fehlgeschlagene Exporte.</li></ul><p>Verbesserungen bei berechneten Metriken, Segmenten und Dimensionen</p><ul><li>Unterstützung für mehr berechnete Metrikfunktionen. Zuvor wurden nur einfache mathematische Funktionen unterstützt.</li><li>Segmente beim Erstellen eines Exports anwenden</li><li>Unterstützung für Dimensionen vom Typ „Double-Data“ für verbesserte Präzision.</li></ul><p>Administrative Verbesserungen</p><ul><li>Administratoren können jetzt alle Exporte und Protokolle anzeigen, unabhängig davon, wer sie erstellt hat.</li></ul><p>(Link zur Dokumentation folgt.)</p> | Donnerstag, 18. Februar 2026 | Donnerstag, 4. März 2026 |
| **Content Analytics: Miniaturansichten und Vorschauen von Streuvisualisierungen** <p>Wenn Sie eine Streuvisualisierung in Content Analytics anzeigen, wird jetzt eine Miniaturansicht des Assets angezeigt, wenn Sie den Mauszeiger über einen Punkt im Diagramm bewegen. Diese Miniaturansicht ermöglicht es Ihnen, schnell und einfach zu sehen, welcher Inhalt in dem Diagramm dargestellt wird.</p><p>(Link zur Dokumentation folgt.)</p> | Mittwoch, 17. Februar 2026 | Dienstag, 2. März 2026 |
| **Content Analytics: Miniaturansichten und Vorschauen von Balkenvisualisierungen** <p>Wenn Sie eine horizontale Balkenvisualisierung in Content Analytics anzeigen, wird jetzt eine Miniaturansicht des Assets angezeigt, wenn Sie den Mauszeiger über einen Balken im Diagramm bewegen. Diese Miniaturansicht ermöglicht es Ihnen, schnell und einfach zu sehen, welcher Inhalt in dem Diagramm dargestellt wird.</p><p>(Link zur Dokumentation folgt.)</p> | Dienstag, 23. Februar 2026 | Dienstag, 9. März 2026 |
| **Aktualisierung auf die Funktion Ungefährer Distinct Count**<p>Der HLL-probabilistische Algorithmus, der in der Funktion Ungefährer Distinct Count verwendet wird, wird bald aktualisiert. Die resultierende Ausgabe für Zahlen, die diese Funktion verwenden, kann sich wie folgt geringfügig von historischen Zahlen unterscheiden:<ul><li>Beim Zählen sehr kleiner Mengen eindeutiger Werte werden die Ergebnisse dahingehend verbessert, dass genaue Zählungen anstelle von Schätzungen verwendet werden.</li><li>Wenn Sie etwas Größeres zählen, behalten Zählschätzungen dieselbe Genauigkeit wie vor dieser Aktualisierung bei (Schätzungen sind innerhalb von 5 Prozent der exakten Zahl genau, 95 Prozent der Zeit).</li></ul><p>Weitere Informationen zur Funktion Ungefährer Distinct Count finden Sie unter [Ungefährer Distinct Count](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) unter [Erweiterte Funktionen](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | März 2026 |
| **Unterstützung für Datenspiegelung**  <p>Durch die Unterstützung modellbasierter Schemata und der Funktion zur Änderungsdatenerfassung (Change Data Capture, CDC) für bestimmte Quell-Connectoren in Experience Platform kann Customer Journey Analytics die [Datenspiegelungsfunktion](/help/data-mirror/data-mirror.md) von Data-Warehouse-Lösungen wie [!DNL Snowflake], [!DNL Azure Databricks] und [!DNL Google BigQuery] unterstützen.</p><p>Wenden Sie sich an Ihr Adobe-Accountteam, um Zugriff auf die Beta-Version anzufordern.</p> | Beta-Version: 24. September 2025 | TBD |
| **Streaming-Mediendienste: Unterstützung von Zeitplandaten** <p>Sie können jetzt Daten früherer Live-Streaming-Medieninhalte hochladen, um die Zuschauerzahlen einfacher und genauer verfolgen zu können.</p><p>Im Folgenden finden Sie Beispiele für Live-Inhalte, die mit dem Upload von Zeitplandaten unterstützt werden:</p><ul><li>FAST-Plattformen (Free Ad Supported TV)</li><li>Lokale Datenströme</li><li>Live-Sportübertragungen</li></ul><p>Durch das Hochladen von Zeitplandaten können Sie die Zuschauerzahlen für einzelne Programme verfolgen, die in dem von Ihnen in der Upload-Datei angegebenen Zeitraum gelaufen sind. Sie können sogar Zuschauerzahlen für bestimmte Themen oder Programmsegmente erfassen.</p><p>Diese Funktionen sind unabhängig davon verfügbar, wie Sie die Erfassung von Streaming-Medien implementiert haben.</p><p>Zuvor war es bei der Analyse von Live-Inhalten schwierig, eine bestimmte Sitzung genau mit bestimmten Programmen zu verknüpfen, und es war nicht möglich, eine bestimmte Sitzung mit einzelnen Themen oder Programmsegmenten zu verknüpfen.</p><p>Weitere Informationen finden Sie unter [Hochladen von Zeitplandaten zum Nachverfolgen von Live-Inhalten](https://experienceleague.adobe.com/de/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | &#x200B;29. Oktober 2025 | Erstes Halbjahr 2026<p>(Veröffentlichung ursprünglich für den 29. Oktober 2025 geplant)</p> |

## Fehlerbehebungen in Customer Journey Analytics

**Analysis Workspace**: AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428834, AN-306540, AN-426014, AN-427801
**Komponenten**:
**Content Analytics**:
**Geführte**:
**Exporte**: AN-422041, AN-421599, AN-422112
**Datenansichten**:
**Implementierung**:
**Report Builder**: AN-391415, AN-425125
**Reporting**: AN-425817, AN-424362, AN-425752, AN-425278, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Segmentierung**: AN-428905, AN-428232
**Terminierte Berichte**: AN-425484, AN-425137
**Freigegebene Metriken und Dimensionen**:
**Sonstige**: AN-428833, AN-425074


## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Entfernung von TLS 1.2 Cipher Suites** | Donnerstag, 11. Februar 2026 | Hinweis für Administratoren: Adobe plant, die Unterstützung für die folgenden TLS 1.2-Chiffrier-Suites von den Adobe-Datenerfassungs-Servern am 27. Mai 2026 einzustellen.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Bei den meisten Implementierungen ist keine Kundenaktion erforderlich. Diese Änderung betrifft in erster Linie Analytics-Daten, die von veralteten nativen Programmen gesendet werden, die veraltete TLS-Bibliotheken verwenden, sowie eine geringe Anzahl von Web-Besuchern in veralteten Browsern oder Betriebssystemen. Die Aufhebung der Unterstützung für diese Chiffrier-Suites erhöht die Sicherheit und stimmt Adobe mit modernen Verschlüsselungsstandards ab. Weniger als 0,1 % des Datenerfassungs-Traffics beruht derzeit auf diesen Chiffrier-Suites.</p> |

## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zur Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
