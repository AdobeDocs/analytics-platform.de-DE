---
title: Richtlinien für abgeleitete Felder
description: Erfahren Sie mehr über Richtlinien zur Verwendung abgeleiteter Felder in Customer Journey Analytics, einschließlich Best Practices, Leitplanken und allgemeiner Fallstricke, um die Leistung und Datenkorrektur zu optimieren.
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
hide: true
source-git-commit: afb577bb72f2528c15acbc30794c900ea62b51b6
workflow-type: tm+mt
source-wordcount: '2655'
ht-degree: 1%

---


# Richtlinien für abgeleitete Felder

Mit [ (abgeleiteten ](./derived-fields.md)) können Sie Daten zur Abfragezeit transformieren, klassifizieren und anreichern, ohne die Quelldatensätze zu ändern. Diese Flexibilität kann zu Komplexität, Leistungsproblemen und Wartungsaufwand führen, wenn sie ohne Disziplin angewendet wird.

Dieser Artikel enthält Richtlinien (Best Practices, Leitplanken und allgemeine Fallstricke) für die Arbeit mit abgeleiteten Feldern. Die vorgesehene Zielgruppe sind Datenarchitekten, Produktadministratoren und Analysten, die Folgendes tun müssen:

* **Leistung optimieren** Identifizieren Sie Muster, die die Ausführung von Abfragen verlangsamen oder Systembeschränkungen erreichen, um das richtige Tool für den Auftrag auszuwählen:

   * [Abgeleitete Felder](./derived-fields.md)
   * [Datenansichtseinstellungen](/help/data-views/component-settings/overview.md)
   * [Datenvorbereitung](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home)
   * [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md)
   * [Datensätze nachschlagen](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)

* **Verbesserung der**: Erstellen Sie eine abgeleitete Feldlogik, die klar, modular und einfach zu aktualisieren ist.
* **Korrektheit sicherstellen**: Vermeiden Sie gängige logische Fehler bei der Klassifizierung, Attribution und Datenumwandlung.

Die Abschnitte in diesem Artikel sind nach Themen geordnet. Von übermäßig komplexen Regelketten bis hin zum Missbrauch von Funktionen wie [Lookup](./derived-fields.md#lookup), [Regex Replace](./derived-fields.md#regex-replace) und [Next oder Previous](./derived-fields.md#next-or-previous). Jeder Abschnitt enthält:

* **Muster** zu erkennen: Beobachtbare Signale in den abgeleiteten Felddefinitionen.
* **Risikodiagnose**: Warum dieses Muster problematisch ist. Mögliche Ursachen sind negative Auswirkungen auf **Leistung**, **Datenqualität** oder **Wartung**.
* **Recommendations**: Konkrete Schritte zur Refaktorierung oder Verbesserung der Implementierung.

Diese Richtlinien helfen Ihnen beim Erstellen effizienter, skalierbarer und semantisch korrekter Implementierungen in Customer Journey Analytics. Wenden Sie diese Richtlinien an, wenn Sie vorhandene Datenansichten prüfen, neue abgeleitete Felder entwerfen oder Governance-Tools erstellen.


## Von hoher Kardinalität abgeleitete Felder

In diesem Abschnitt werden Standardsegmente für Datenansichten erläutert, die auf abgeleitete Felder mit hoher Kardinalität verweisen.

### Muster

* Standardsegmente für Datenansichten, die auf ein abgeleitetes Feld verweisen, das auf einer Dimension mit hoher Kardinalität basiert (etwa eine Million oder mehr verschiedene Werte). Beispiel: vollständige Seiten-URL.
* Einfache Vorgänge wie [Kleinbuchstaben](./derived-fields.md#lowercase), [Trim](./derived-fields.md#trim) oder [Case Wenn](./derived-fields.md#case-when)-Prüfungen auf der Seiten-URL sind häufig teurer als dieselbe Logik in Feldern mit geringer Kardinalität, wie Seitenname, Site-Bereich oder URL-Gruppe.

### Risikodiagnose: Leistung

* Standardsegmente, die nach abgeleiteten Feldern filtern, die Seiten-URL oder andere Dimensionen mit hoher Kardinalität berühren, fügen jeder Abfrage für die Datenansicht Latenz hinzu.

### Empfehlungen

* Vermeiden Sie den direkten Verweis auf vollständige Seiten-URLs oder Komponenten mit ähnlich hoher Kardinalität in den Standardsegmenten der Datenansicht. Übertragen Sie umfangreiche URL-Logik (komplexe [Wenn](./derived-fields.md#case-when), [Regex ersetzen](./derived-fields.md#regex-replace), mehrere Zeichenfolgenfunktionen) nach vorn in [Datenvorbereitung](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home) oder [Lookup-Datensätze](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) sodass die resultierenden Klassifizierungen auf einfacheren Dimensionen mit niedrigerer Kardinalität landen.
* Bevorzugen Sie Schlüssel mit niedrigerer Kardinalität, z. B. normalisierte Seitennamen, Site-Bereiche oder vorklassifizierte URL-Gruppen.
* Überprüfen Sie regelmäßig vorhandene Standardsegmente und abgeleitete Felder der Datenansicht auf Verweise auf Dimensionen mit hoher Kardinalität (Seiten-URL, Kampagnen-IDs, rohe Abfragezeichenfolgen) und refaktorieren Sie zu normalisierten oder gruppierten Schlüsseln.

## Zu komplexe Wenn-Regelketten

In diesem Abschnitt werden überkomplexe Ketten von Wenn[Regeln ](./derived-fields.md#case-when).

Customer Journey Analytics erzwingt explizite [Funktions- und Operatorbeschränkungen](derived-fields.md#limitations) pro abgeleitetem Feld (z. B. maximale Anzahl von Operatoren, maximale Anzahl von Funktionen pro Typ). Überkomplexe Funktionen und Ketten innerhalb von Funktionen sind schwieriger zu pflegen und fehleranfälliger.

### Muster

* Sehr große [Wenn](./derived-fields.md#case-when)-Funktionen mit komplexen **[!UICONTROL If]**- und **[!UICONTROL Else If]**-Ketten:
   * Viele Bedingungen (z. B.: mehr als 20 Operatoren) oder tiefe Verschachtelung (mehr als 3 oder 4 Ebenen verschachtelter Logik [Case](./derived-fields.md#case-when) **[!UICONTROL If]** und **[!UICONTROL Else If]**).
   * Wiederholte Bedingungen im selben Feld mit unterschiedlichen Werten.
* Wiederholte Zeichenfolgen-Übereinstimmung mit Konstanten.

  +++ Beispiel

  ![Best Practices - Beispiel für die wiederholte, konstante Zeichenfolgenübereinstimmung](assets/best-practices-over-complex-case-when.png)

  +++


### Risikodiagnose: Leistung, Datenqualität, hohe Wartung

* Wartbarkeit und Fehlerrisiko: Logik, die als monolithischer Regelblock kodiert ist, ist schwer zu debuggen und zu aktualisieren.
* Potenzielle Leistung und Risiko begrenzen: Sie können (Benutzer- oder [) erreichen oder sich ihnen ](./derived-fields.md#limitations), insbesondere bei klassifizierungsähnlichen Mustern.

### Empfehlungen

* Aufspaltung in mehrere abgeleitete Felder. Trennen Sie beispielsweise *Kampagnennormalisierung* (Zuordnung inkonsistenter Kampagnenkennungen zu einem kanonischen Wert) von Kanal-Bucketing, anstatt alles in einer riesigen Regel zu kombinieren.
* Verwenden von Lookup-Datensätzen. Viele **[!UICONTROL Bedingungen _Wenn Wert_ Kriterium _Kriterium_ dann _Wert_ auf Wert]** werden besser als [Lookup-Datensatz](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) kombiniert mit der [Lookup](./derived-fields.md#lookup)-Funktion implementiert, anstatt lange [](./derived-fields.md#case-when) WennKetten zu verwenden.
* Verwenden Sie Komponentenfilter für Datenansichten. Wenn ein Teil der Logik einfach fehlerhafte Werte herausfiltert, verwenden Sie [Einschließen/Ausschließen](/help/data-views/component-settings/include-exclude-values.md) auf der Komponentenebene der Datenansicht, anstatt diese Logik in ein abgeleitetes Feld einzubetten.

## Falsche Verwendung

In diesem Abschnitt wird die falsche Verwendung abgeleiteter Felder erläutert. Insbesondere dort, wo Alternativen eine bessere Lösung sind.

>[!NOTE]
>
>Das Verschieben einer Logik aus einem abgeleiteten Feld in eine Komponenteneinstellung für die Datenansicht verbessert allein die Abfrageleistung nicht. Beide Ansätze kompilieren mit derselben zugrunde liegenden abgeleiteten Logik. Bei den Empfehlungen in diesem Abschnitt geht es um Klarheit, Governance und Wiederverwendung und nicht um Geschwindigkeit.

### Muster

* Ein abgeleitetes Feld repliziert ein Verhalten, das bereits in den Komponenteneinstellungen verfügbar ist:
   * Groß-/Kleinschreibung, Zuschneiden oder einfaches Filtern (z. B. ohne `unknown`, `undefined` oder `null`) ohne zusätzliche Komplexität.
   * Einfache Bucketing für Zahlenbereiche.

     +++ Beispiel

     ![Falsche Verwendung von einfachen Bucketing](assets/best-practices-wrong-usage.png)

     +++

     Verwenden Sie stattdessen [Wert-Bucketing](/help/data-views/component-settings/value-bucketing.md) für eine Dimension in Ihrer Datenansicht.
   * Persistenz- oder Attributionslogik, codiert mit [Nächste oder Vorherige](./derived-fields.md#next-or-previous) oder manueller Sequenzlogik, bei der die Einstellungen [ Datenansicht (Attribution](/help/data-views/component-settings/attribution.md) und [Gültigkeit](/help/data-views/component-settings/persistence.md) ausreichen würden.
   * Eine abgeleitete Metrik, die einfach eine vorhandene Metrik unter einer Bedingung zählt.

     +++ Beispiel

     ![Falsche Verwendung der bedingten Logik](assets/best-practices-wrong-usage-2.png)

     +++

     Dies repliziert, was eine gefilterte Metrik oder [Werte einschließen/ausschließen](/help/data-views/component-settings/include-exclude-values.md) erreichen könnte.

### Risikodiagnose: Datenqualität, hohe Wartung

* Redundante Komplexität: Abgeleitete Felder werden verwendet, wenn einfachere integrierte Datenansichtsfunktionen vorhanden sind.
* Governance-Risiko: Andere Benutzende verstehen möglicherweise nicht, warum ein abgeleitetes Feld anstelle einer nativen Einstellung vorhanden ist. Das Muster sorgt für mehr Durcheinander bei der Verwaltung abgeleiteter Felder.
* Reduzierte Wiederverwendbarkeit: Die Codierung von bedingten Flags als abgeleitete Felder erschwert die Wiederverwendung von Basismetriken mit verschiedenen Filtern in Projekten.

### Empfehlungen

* Kürzung/Kleinschreibung: Verwenden Sie die Komponenteneinstellungen [Teilzeichenfolge](/help/data-views/component-settings/substring.md) und [Verhalten](/help/data-views/component-settings/behavior.md), es sei denn, Sie benötigen kombinierte mehrstufige Transformationen.
* Werteausschluss: Verwenden Sie [Werte einschließen/ausschließen](/help/data-views/component-settings/include-exclude-values.md) für Metriken oder Dimensionswerte auf der Komponentenebene der Datenansicht, nicht in einem abgeleiteten Feld.
* Attribution und Persistenz: Vermeiden Sie die Simulation von Dimensionen in einem abgeleiteten Feld mit [Weiter oder Zurück](./derived-fields.md#next-or-previous) oder einer anderen sequenziellen Logik. Verwenden Sie die Einstellungen für [ Datenansicht ](/help/data-views/component-settings/attribution.md)Attribution[ und Persistenz](/help/data-views/component-settings/persistence.md) für Dimensionen.
* Numerische Bucketing: Das abgeleitete Feld bleibt numerisch und die Datenansicht kann oben eine Dimension mit Buckets erstellen statt Bereichsbeschriftungen in einer Wenn-Kette mit &quot;[&quot; ](./derived-fields.md#case-when).
* Bedingte Logik: Konvertiert eine einfache 0- oder 1-Flag-Logik in:
   * Die ursprüngliche Metrik mit der Filterlogik Werte einschließen oder ausschließen , wie sie in Analysis Workspace angewendet wird.
   * Eine gefilterte Metrik mithilfe der Konfiguration der Komponenteneinstellungen für die Datenansicht.

## Fehlklassifizierungen von Metriken und Dimensionen

In diesem Abschnitt wird die falsche Klassifizierung von Metriken und Dimensionen erläutert.

### Muster

* Ein abgeleitetes Feld erzeugt eindeutig:
   * Numerische Ausgaben (Anzahl, Verhältnis oder Arithmetik), aber die Komponente ist als Dimension konfiguriert.
   * Kategoriale Ausgaben (Bezeichnungen oder Zeichenfolgen), die Komponente ist jedoch als Metrik konfiguriert.
* Ein abgeleitetes Feld kodiert 0/1-Flags als Zeichenfolgen.

Customer Journey Analytics ermöglicht es, numerische Felder auf Datenansichtsebene zu Dimensionen und Zeichenfolgenfeldern zu Metriken zu zwingen. Eine falsche Ausrichtung kann jedoch zu verwirrenden Berichten führen.

### Risikodiagnose: Datenqualität

* Semantische Diskrepanz: Der Komponententyp stimmt nicht mit der Art des abgeleiteten Ergebnisses überein, was die korrekte Analyse oder Aggregation des Komponententyps erschwert.

### Empfehlungen

* Wenn die Ausgabe numerisch ist:
   * Legen Sie in der Datenansicht **[!UICONTROL Komponententyp]** Metrik) fest.
   * Wenn die Komponente eine Teilmengenmetrik darstellt (z. B. **[!UICONTROL Checkout-Seitenansichten]**), verwenden Sie in der Datenansicht eine gefilterte Metrik anstelle einer abgeleiteten Zeichenfolge plus einer berechneten Metrik.
* Wenn die Ausgabe eine Beschriftung ist:
   * Legen Sie den Komponententyp auf **[!UICONTROL Dimension fest]** konfigurieren Sie [Attribution](/help/data-views/component-settings/attribution.md) und [Persistenz](/help/data-views/component-settings/persistence.md) entsprechend.

## Fallstricke bei der Marketing-Kanal- und Kampagnenlogik

In diesem Abschnitt werden Fallstricke bei der Marketing-Kanal- und Kampagnenlogik erläutert.

>[!NOTE]
>
>Eine Vereinfachung im Vorfeld sollte in Betracht gezogen werden[ indem ](https://experienceleague.adobe.com/de/docs/experience-platform/data-prep/home)Datenvorbereitung“, [Lookup-Datensätze](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) oder abgeleitete Feldfunktionen wie [Klassifizieren](./derived-fields.md#classify) verwendet werden, um ähnliche Regeln für Marketing-Kanäle zu konsolidieren und die Anzahl der Operatoren in Ihrer Wenn[-Logik von ](./derived-fields.md#case-when) zu reduzieren. Beschränken Sie außerdem die Anzahl der Felder mit hoher Kardinalität, auf die in der Kanalklassifizierungslogik verwiesen wird (z. B.: viele verschiedene Abfrageparameterschlüssel), da diese Felder sowohl die Kardinalität als auch die Abfragekosten erhöhen.

### Muster

* Customer Journey Analytics-Marketing-Kanäle werden oft mithilfe abgeleiteter Felder implementiert.

   * Abgeleitete Felder, die Marketing-Kanal- oder Kampagnen-Bucketing basierend auf URL-Parametern, Referrer, Landingpage und mehr implementieren.
   * Verdächtige Reihenfolge: Es wird eine allgemeine Sammelregel angezeigt, bevor spezifischere Regeln angewendet werden.
   * Unvollständige Handhabung aller möglichen Optionen: Keine explizite Verzweigung für **[!UICONTROL Verweisende Domain ist nicht]** oder **[!UICONTROL Abfrageparameter ist nicht festgelegt]**.

### Risikodiagnose: Datenqualität

* Logischer Reihenfolgefehler: Spätere Regeln in der Kette, die möglicherweise bestimmte Kanäle überschreiben und zu falsch klassifiziertem Traffic führen.
* Falsche Kennzeichnung von direktem Traffic: Nicht übereinstimmender Traffic fällt in einen unbeabsichtigten Kanal oder wird als `Other` gekennzeichnet.

### Empfehlungen

* Reihenfolge der Priorität von oben nach unten erzwingen. Setzen Sie die stärksten Signale an erste Stelle (z. B. interne Domains, um Kampagnenparameter auszuschließen).
* Schließen Sie einen letzten expliziten Wert ein **[!UICONTROL andernfalls setzen Sie den Wert auf]**. Setzen Sie den Fallback auf **[!UICONTROL Kein Wert]**, um zu vermeiden, dass frühere Kanäle überschrieben werden. Legen Sie in diesem **[!UICONTROL -Schritt den Wert nicht auf]** Benutzerdefinierter Zeichenfolgenwert **[!UICONTROL und dann]** Benutzerdefinierter Zeichenfolgenwert) auf `Direct`, `None` oder `Unclassified` fest.
* Verwenden Sie Vorlagen. Verwenden Sie nach Möglichkeit die Vorlagen für von Marketing-Kanälen abgeleitete Felder. Oder stimmen Sie zumindest die Logik mit den von Adobe empfohlenen Best Practices für Marketing-Kanäle ab.

## Nicht normalisierte Zeichenfolgenschlüssel, die in Suchen verwendet werden

In diesem Abschnitt wird die Verwendung nicht normalisierter Zeichenfolgenschlüssel bei der Suche erläutert.

### Muster

* Eine [Lookup](./derived-fields.md#lookup)-Funktion über ein Ereignis- oder Profilfeld, das einen Lookup-Datensatz befüllt.
* Kein vorheriger [ (](./derived-fields.md#lowercase)), [Trim](./derived-fields.md#trim) oder [Regex Replace](./derived-fields.md#regex-replace) standardisiert den Schlüssel.
* Häufige Kandidaten: URL, Kampagnen-ID, E-Mail, Konto-ID.

### Risikodiagnose: Datenqualität, hohe Wartung

* Datenqualitätsrisiko: Suchvorgänge schlagen fehl, wenn sich die Schlüsselschreibung oder der Leerraum von der Suchtabelle unterscheidet, was zu Werten *keine Übereinstimmung* und Berichtslücken führt.

### Empfehlungen

* Fügen Sie die Funktionen [Kleinbuchstaben](./derived-fields.md#lowercase) und [Trim](./derived-fields.md#trim) vor der [Lookup](./derived-fields.md#lookup)-Funktion hinzu, es sei denn, es gibt einen dokumentierten Grund, Ober- oder Kleinbuchstaben beizubehalten.
* Wenn bereits mehrere Transformationen verkettet sind, überprüfen Sie deren Reihenfolge: zuerst normalisieren und dann nachschlagen.

## Regex-Missbrauch oder -Überschreitung

In diesem Abschnitt wird der Missbrauch oder die Überdehnung der Regex-Funktionalität für abgeleitete Felder erläutert.

### Muster

* [Regex ersetzen](./derived-fields.md#regex-replace) oder regex-basierte Bedingungen verwenden sehr breite Muster, bei denen einfachere [Wenn](./derived-fields.md#case-when)-Funktionen mit **[!UICONTROL Enthält]** oder **[!UICONTROL Beginnt mit]** eine einfachere und bessere Alternative sind.

  +++ Beispiel

  ![Best Practices - Regex ersetzen 1](assets/best-practices-regex-replace-1.png)

  ![Best Practices - Regex ersetzen 1](assets/best-practices-regex-replace-2.png)

  +++

* Mehrere Regex-Bedingungen überschneiden sich oder stehen im Konflikt.
* Starke Regex-Nutzung zum Parsen von URLs, anstatt die Funktion [URL Parse](./derived-fields.md#url-parse) zu verwenden.

### Risikodiagnose: Leistung, Datenqualität, hohe Wartung

* Leistungs- und Wartungsrisiken: Komplexe Regex-Muster sind schwieriger zu debuggen und können langsamer sein.
* Richtigkeitsrisiko: Zu breite Regex kann unbeabsichtigte Werte erfassen.

### Empfehlungen

* URL[Parse](./derived-fields.md#url-parse) für Standard-URL-Elemente (Domain, Pfad, Abfrageparameter) anstelle von [Regex-Ersetzung](./derived-fields.md#regex-replace).
* Verwenden Sie für einfache Musterprüfungen [case When](./derived-fields.md#case-when) mit **[!UICONTROL Contains]**, **[!UICONTROL Beginnt mit]** oder **[!UICONTROL Endet mit]** Logik anstelle von regulären Ausdrücken mit [Regex Replace](./derived-fields.md#regex-replace).
* Markieren Sie reguläre Ausdrücke, die mehrere verschachtelte Gruppen oder Alternativen für einfache Muster verwenden. Oder reguläre Ausdrücke, die Sie mit abgeleiteten Feld-Zeichenfolgen-Funktionen ersetzen können.

## Logik des Stils für berechnete Metriken in abgeleiteten Feldern

In diesem Abschnitt wird die Verwendung der Logik eines berechneten Stils in einem abgeleiteten Feld erläutert.

>[!NOTE]
>
>Abgeleitete Felder werden vor der Aggregation auf Ereignisebene (Zeile) ausgewertet, während berechnete Analysis Workspace-Metriken bereits aggregierte Werte verwenden. Verhältnisse, Durchschnittswerte und Berechnungen im eigenen Stil können daher zu unterschiedlichen Ergebnissen führen, je nachdem, ob diese Berechnungen als abgeleitetes Feld oder als berechnete Metrik implementiert werden. Wir müssen abwägen, wo die Arithmetik wohnt, denn die Bewertung verändert die Antwort.

### Muster

* Reine Arithmetik für numerische Felder innerhalb eines abgeleiteten Felds (Summe, Subtraktion, Division), das wie eine berechnete Metrik aussieht.

  +++ Beispiele

  ![Best Practices - Gewinnberechnung](assets/best-practices-profit.png)

  ![Best Practices - Bestellungen pro Impression](assets/best-practices-orders-impressions.png).

  +++

* Keine Verwendung von Zeichenfolgenmanipulation oder Klassifizierung; die Logik ist rein numerisch.

### Risikodiagnose: Datenqualität

* Governance- und Design-Frage: Die Arithmetik kann besser platziert werden als:
   * Eine abgeleitete Feldmetrik (wenn Sie möchten, dass das abgeleitete Feld für alle Benutzer als gesteuerte Standardmetrik dient).
   * Eine berechnete Metrik in Analysis Workspace (wenn die berechnete Metrik analysespezifisch ist).

### Empfehlungen

* Wenn das arithmetische Ergebnis allgemein für Benutzer und Projekte nützlich ist, behalten Sie das Ergebnis als abgeleitete Feldmetrik bei. Stellen Sie sicher, dass der Komponententyp Metrik ist und die Formatierung (Währung, Prozentsatz) auf Datenansichtsebene konfiguriert ist.
* Wenn das Ergebnis nischenspezifisch oder analystenspezifisch ist, verschieben Sie das Ergebnis in eine berechnete Metrik und vereinfachen Sie die Datenansicht.

## Übermäßige Nutzung der nächsten oder vorherigen oder sequenziellen Funktionen

In diesem Abschnitt wird die übermäßige Verwendung von [Weiter oder Zurück](./derived-fields.md#next-or-previous) oder sequenziellen Funktionen erläutert.

### Muster

* Ein abgeleitetes Feld verwendet [Weiter oder Zurück](./derived-fields.md#next-or-previous) Funktionen mehrmals (nahe an der dokumentierten Anzahl der einzelnen Felder).
* [Weiter oder Zurück](./derived-fields.md#next-or-previous) wird verwendet, um eine Persistenz-ähnliche Logik zu implementieren (z. B.: eine Kampagne fortführen), anstatt die Datenansichts-Persistenz zu verwenden.

### Risikodiagnose: Datenqualität, hohe Wartung

* Komplexität und Fragilität: Umfangreiche sequenzielle Logik ist schwieriger zu argumentieren und kann abbrechen, wenn Sitzungsregeln oder Änderungen angeordnet werden.
* Redundanz mit Attribution oder Persistenz: Einige Anwendungsfälle (z. B. die Attribution des Letztkontaktkanals in einer Sitzung) werden besser durch die Attributionseinstellungen der Datenansicht abgedeckt.

### Empfehlungen

* Verwenden Sie bei Mustern, die der Standardattribution ähneln[ die Einstellungen für Dimension Attribution](/help/data-views/component-settings/attribution.md) und [Persistenz](/help/data-views/component-settings/persistence.md) in der Datenansicht, anstatt sie mit &quot;[&quot; oder „Zurück](./derived-fields.md#next-or-previous) zu simulieren.
* Reservieren Sie [Nächste oder Vorherige](./derived-fields.md#next-or-previous) für erweiterte mehrstufige Pfade oder funnel-Kennzeichnungen, die eine Attribution allein nicht erreichen kann (z. B.: Kanalsequenzverkettung).

## Sitzungs- und Personenkontext werden ignoriert

In diesem Abschnitt wird beschrieben, wie Kontext auf Sitzungs- und Personenebene beim Definieren eines abgeleiteten Felds ignoriert werden.

>[!NOTE]
>
>In einigen Fällen kann ein Segment, das auf Sitzungs- oder Personenebene in Analysis Workspace erfasst wird, das Verhalten einfacher modellieren als ein abgeleitetes Feld. Erwägen Sie bei Bedarf die Verwendung von Segmenten anstelle von komplexen, über den Umfang hinweg abgeleiteten Feldern.

### Muster

* Ein abgeleitetes Feld setzt implizit eine bestimmte [Container-Ebene](/help/getting-started/cja-b2b-concepts-features.md#containers) voraus (Ereignis, Sitzung oder Person), aber:

   * Das abgeleitete Feld verweist nicht auf Attribute auf Sitzungs- oder Personenebene.
   * Die Sitzungseinstellungen der Datenansicht stehen im Konflikt mit der beabsichtigten Logik.

### Risikodiagnose: Datenqualität

* Konzeptuelle Diskrepanz: Die Semantik abgeleiteter Felder stimmt möglicherweise nicht mit der von Analysten erwarteten Aggregationsebene überein (z. B.: ein personabasiertes Feld, das sich mit jedem Ereignis ändern kann).

### Empfehlungen

* Wenn die Logik auf Sitzungsebene ausgeführt werden soll, überprüfen Sie, ob [Sitzungseinstellungen](/help/data-views/session-settings.md) ordnungsgemäß konfiguriert sind, und erwägen Sie die Verwendung von Komponenten im Sitzungsbereich oder einer Zusammenfassung in Analysis Workspace oder in einem [integrierten BI-Tool](/help/data-views/bi-extension.md).
* Wenn die Logik auf Personenebene erstellt werden soll, verwenden Sie Profildatensätze oder Lookup-Datensätze und verweisen Sie in abgeleiteten Feldern auf diese Datensätze.
* Prüfen Sie, ob ein Segment in Analysis Workspace für eine Sitzung oder für eine Person dasselbe Ergebnis einfacher erreichen würde als ein abgeleitetes Feld.

## Erreichbarkeit oder Annäherung an dokumentierte Funktionsgrenzen

In diesem Abschnitt werden die Auswirkungen beschrieben, die sich ergeben, wenn die dokumentierten Funktionsbeschränkungen für abgeleitete Felder erreicht oder sich ihnen nähert.

>[!NOTE]
>
>Verringern Sie die Abhängigkeit von Feldern mit hoher Kardinalität in komplexen abgeleiteten Feldern, wo möglich (z. B.: Verwenden normalisierter Schlüssel oder gruppierter Klassifizierungen), um sowohl die Abfragekosten als auch die Wahrscheinlichkeit zu begrenzen, dass [ (Benutzer- oder Funktionsbeschränkungen](./derived-fields.md#limitations) erreicht werden.

Customer Journey Analytics [Dokumente](./derived-fields.md#limitations) maximale Funktionen und Operatoren pro abgeleitetem Feld, einschließlich Einschränkungen pro Funktionstyp ([Lookup](./derived-fields.md#lookup), [Date Math](./derived-fields.md#date-math), [Deduplicate](./derived-fields.md#deduplicate), [Math](./derived-fields.md#math), [Split](./derived-fields.md#split), [URL Parse](./derived-fields.md#url-parse) und mehr).

### Muster

* Ein abgeleitetes Feld verwendet viele [Lookup](./derived-fields.md#lookup), [Math](./derived-fields.md#math)-Vorgänge, [Split](./derived-fields.md#split) oder andere Funktionen.
* Die Anzahl der Operatoren liegt nahe an den [dokumentierten ](./derived-fields.md#limitations)) (z. B.: mehr als 70 % - 80 % der zulässigen Zählungen).

### Risikodiagnose: Leistung, hohe Wartung

* Skalierbarkeitsrisiko: Zukünftige Ergänzungen können fehlschlagen oder sich unerwartet verhalten, wenn das Feld seine Funktionsgrenze erreicht.

### Empfehlungen

* Proaktiv kennzeichnen, wenn die Nutzung einen Schwellenwert überschreitet (z. B. > 70 % einer Funktion oder eines Benutzerlimits).
* Teilen Sie die Logik in mehrere abgeleitete Felder auf, die miteinander verkettet sind (z. B. ein abgeleitetes Feld A, das einen Lookup-Schlüssel normalisiert, und ein abgeleitetes Feld Band normalize_key und dann Lookup_label).
* Verwenden Sie die externe Datenvorbereitung für einen Lookup-Datensatz, in dem besonders große Klassifizierungen erforderlich sind.

## Datenansichtsspezifische Optimierungsregeln

In diesem Abschnitt werden datenansichtsspezifische Optimierungsregeln für abgeleitete Felder erläutert.

Überprüfen Sie auch die Konfiguration der Datenansicht für jede abgeleitete Komponente.

### Muster

* Eine abgeleitete Dimension verfügt über eine Standardattribution (z. B. „Letztkontakt mit Sitzungsablauf„), aber der abgeleitete Feldname bedeutet eine andere Semantik (z. B.: `First Campaign of Visit`, `Original Source`).


### Risikodiagnose: Datenqualität

* Semantische Diskrepanz: Die Beschriftung der Dimension deutet auf ein anderes [Attribution](/help/data-views/component-settings/attribution.md) oder [Expiration](/help/data-views/component-settings/persistence.md)-Verhalten hin (z. B. Erstkontakt oder Originalquelle) als das, was tatsächlich konfiguriert ist.
* Diese Diskrepanz erhöht das Risiko, dass Analysten Berichte falsch interpretieren oder Komponenten vergleichen, die nach Namen ähnlich aussehen, aber verschiedene Attributionsmodelle verwenden.

### Empfehlungen

* Passen Sie das [Zuordnungsmodell und die Gültigkeit](/help/data-views/component-settings/persistence.md) auf dieser Dimension an, um Name und Verhalten auszurichten. Beispielsweise sollte eine abgeleitete Felddimension mit dem Namen `Original Source` die Attribution Erstkontakt verwenden, wobei der Ablauf auf Person festgelegt ist.
