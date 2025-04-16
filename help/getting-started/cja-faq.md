---
title: FAQ zu Customer Journey Analytics
description: Customer Journey Analytics – häufig gestellte Fragen.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 13f2bdb9753c0f4252262c595061ed9b54c38a3c
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 99%

---

# Häufig gestellte Fragen

Adobe Customer Journey Analytics ist das Analyseprodukt der nächsten Generation. Dieser Artikel gibt Antworten auf häufig gestellte Fragen zu Customer Journey Analytics. Weitere Informationen finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Voraussetzungen {#prerequisites}

+++**Benötige ich [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] für [!UICONTROL Customer Journey Analytics]?**

Nein, [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] sind für [!UICONTROL Customer Journey Analytics] nicht erforderlich. Sie werden aktuell noch nicht unterstützt.

+++


+++**Benötige ich eine [!UICONTROL Experience Cloud ID] (ECID) für [!UICONTROL Customer Journey Analytics]?**

Nein, [!UICONTROL Customer Journey Analytics] unterstützt alle IDs in einem Datensatz, unabhängig davon, ob es sich um eine [!UICONTROL ECID] oder eine andere ID handelt.

+++


+++**Wie gehe ich vor, wenn ich meine Daten vor [!UICONTROL Customer Journey Analytics] einem ETL-Prozess (Extract, Transform, Load) unterziehen muss?**

Customer Journey Analytics enthält Funktionen zur [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=de), mit denen Ihre Daten transformiert werden, bevor sie in den Data Lake von Adobe Experience Platform überschrieben werden. Wenn Sie einen ETL-Prozess benötigen, nachdem die Daten aufgenommen wurden, stehen Ihnen über den [Abfrage-Service von Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=de#queries) einige begrenzte Optionen zur Verfügung. Hierfür können jedoch zusätzliche Gebühren anfallen.

+++


## 2. Zuordnen von Daten {#stitching}

+++**Kann [!UICONTROL Customer Journey Analytics] Daten über Geräte oder über Datensätze hinweg zusammenfügen?**

Ja. [!UICONTROL Customer Journey Analytics] verfügt über eine [Zuordnungsfunktion](../stitching/overview.md), die innerhalb eines Datensatzes für authentifizierte und nicht authentifizierte Ereignissen verwendet werden kann. Diese Zuordnung ermöglicht die Auflösung verschiedener Datensätze zu einer einzelnen zugeordneten ID für geräteübergreifende Analysen auf Personenebene.
Wenn eine gemeinsame Namespace-ID (Personen-ID) datensatzübergreifend in einer [Verbindung](/help/connections/overview.md) verwendet wird, können Sie außerdem die Analyse für eine nahtlose Kombination mehrerer auf Personenebene zugeordneter Datensätze ausführen.

+++


+++**Wird das Zusammenfügen von anonymen Verhaltens- mit authentifizierten Verhaltensdaten unterstützt?**

Ja. Bei der [Zuordnung](../stitching/overview.md) werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um eine zugeordnete ID zu generieren.

+++


+++**Wie funktioniert die „Wiederholung“ bei der Zuordnungsfunktion?**

Die Zuordnungsfunktion „wiederholt“ Daten basierend auf eindeutigen Kennungen, die sie gelernt hat. Bei der Wiederholung werden zunächst nicht authentifizierte Ereignisse von Geräten zugeordnet, die in der Zwischenzeit identifiziert wurden. [Weitere Informationen](../stitching/overview.md)

+++


+++**Wie funktioniert die Zuordnung historischer Daten (Aufstockung)?**

Nach der ersten Aktivierung bietet Adobe eine Aufstockung von zugeordneten Daten, die so weit zurückreichen, wie Sie es auswählen (bis zu maximal 25 Monate, abhängig vom Customer Journey Analytics-Paket, auf das Sie Anspruch haben). Um diese Aufstockung durchführen zu können, muss die vorübergehende ID in den nicht zusammengefügten Daten aus dem so weit zurückreichenden Zeitfenster vorhanden sein. [Weitere Informationen](../stitching/overview.md)

+++


+++**Welches Verhalten wird bei nicht zugeordneten Profildatensätzen erwartet?**

**Beispielszenario**: Sie können zwei Datensätze in eine Customer Journey Analytics-Verbindung einbinden, indem Sie `CRMid` als Personen-ID verwenden. Einer ist ein Web-Ereignis-Datensatz mit `CRMid` in allen Datensätzen. Der andere Datensatz ist ein CRM-Profildatensatz. 40 % des CRM-Datensatzes verfügen über `CRMid`, das im Web-Ereignis-Datensatz vorhanden ist. Die anderen 60 % sind im Web-Ereignis-Datensatz nicht vorhanden. Erscheinen diese Datensätze im Reporting in Analysis Workspace?<p> **Antwort**: Profilzeilen, für die keine Ereignisse verknüpft sind, werden in Customer Journey Analytics gespeichert. Sie können sie jedoch erst dann in Analysis Workspace sehen, wenn ein mit dieser ID verknüpftes Ereignis angezeigt wird.

+++

## 3. Daten in [!UICONTROL Customer Journey Analytics] einbringen {#ingest}

+++**Kann ich Daten aus verschiedenen [!UICONTROL Adobe Experience Platform]-Sandboxen in einer [!UICONTROL Customer Journey Analytics]-Verbindung kombinieren?**

Nein, Sie können nicht über Sandboxes hinweg auf Daten zugreifen. Sie können nur Datensätze kombinieren, die sich innerhalb derselben Sandbox befinden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#select-sandbox-and-datasets)

+++


+++**Wie werden in [!UICONTROL Customer Journey Analytics] Online-Daten mit Offline-Daten verbunden?**

Solange die Personen-ID zwischen den Datensätzen übereinstimmt, kann [!UICONTROL Customer Journey Analytics] Filter, Attribution, Fluss, Fallout usw. datensatzübergreifend verbinden.

+++


+++**Wie integriere ich meine Offline-Daten in [!UICONTROL Customer Journey Analytics]?**

Mit Ihrer Berechtigung zur Nutzung von Customer Journey Analytics können Sie Daten in Experience Platform aufnehmen. Sie können dann zu diesen Daten und Datenansichten in [!UICONTROL Customer Journey Analytics] Verbindungen herstellen, um in Analysis Workspace Berichte zu generieren. Das Datenerfassungs-Team von Experience Platform bietet bei Bedarf Empfehlungen oder eine Beratung für Sie an.

+++


+++**Wie integriere ich [!UICONTROL Adobe Analytics]-Daten in [!UICONTROL Customer Journey Analytics]?**

[!UICONTROL Adobe Analytics]-Daten können über den [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) mit Experience Platform verbunden werden. Die meisten [!UICONTROL Adobe Analytics]-Felder werden im XDM-Format übermittelt, andere Felder sind aber noch nicht verfügbar.

+++


+++**Wie lange dauert es, bis Datensatzelemente in einer Datenansicht zusammengefasst sind?**

Ein paar Stunden für eine erste Ansicht und ein paar Tage, um die Daten der letzten 13 Monate aufzustocken.

+++


+++**Sind PII-Daten notwendig, um Verbindungen zwischen den Daten herzustellen?**

Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hash einer Kunden-ID, bei der es sich nicht um personenbezogene Daten handelt.

+++


+++**Welche Beschränkungen gibt es für die Aufnahme vergangener oder künftiger Daten/Zeitstempel in Customer Journey Analytics-Ereignisdatensätze?**

* Für vergangene Daten/Zeitstempel: bis zu zehn Jahre alte Ereignisdaten.
* Für zukünftige Daten/Zeitstempel: Ereignisdaten (prädiktiv) bis zu einem Monat in der Zukunft.

+++


## 4. Latenzaspekte {#latency}

>[!NOTE]
>
>In Customer Journey Analytics gibt es keine feste Datengröße. Daher kann Adobe sich nicht auf eine standardmäßige Aufnahmezeit festlegen. Adobe arbeitet aktiv daran, diese Latenzen durch neue Updates und Aufnahmeoptimierung zu reduzieren.

* Live-Daten oder -Ereignisse: Werden innerhalb von 90 Minuten verarbeitet und aufgenommen, sobald Daten in Adobe Experience Platform verfügbar sind. (Batch-Größe > 50 Millionen Zeilen: länger als 90 Minuten.) Wenn die Zuordnung aktiviert ist, kann die Aufnahme bis zu 4 Stunden dauern. Weitere Informationen finden Sie unter [Leitlinien](https://experienceleague.adobe.com/de/docs/analytics-platform/using/technotes/guardrails).
* Kleine Aufstockungen: Innerhalb von sieben Tagen
* Große Aufstockungen: Innerhalb von 30 Tagen

Adobe hat kürzlich die Verarbeitung von Daten in Customer Journey Analytics geändert:

* Ereignisdaten für den „aktuellen“ Tag werden als Live-Daten gestreamt. Alle Daten mit einer Ereigniszeit vor 11:59:59 pm (23:59:59 Uhr) am Vortag werden als Aufstockung behandelt.
* Alle Ereignisdaten mit einem Zeitstempel, der älter als 24 Stunden ist (auch wenn sie sich im gleichen Batch wie neuere Daten befinden) werden als Aufstockung betrachtet und mit einer niedrigeren Priorität aufgenommen.

## 5. Festlegen eines rollierenden Fensters für die Speicherung von [!UICONTROL Verbindungsdaten] {#data-retention}

Mit der Einstellung [**[!UICONTROL Rollierendes Datenfenster aktivieren ]**](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#create-connection) können Sie die Customer Journey Analytics-Datenspeicherung als rollierendes Fenster in Monaten (drei Monate, sechs Monate usw.) definieren. Sie wird auf einer [!UICONTROL Verbindungs]-Ebene, nicht auf einer [!UICONTROL Datensatz]-Ebene festgelegt. Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine Datenspeicherungseinstellung, da keine entsprechenden Zeitstempel vorhanden sind.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

## 6. Auswirkungen des Löschens von Datenkomponenten {#deletion}

Beim Löschen von Daten sollten Sie sich über sechs Komponententypen Gedanken machen: Sandbox, Schema, Datensatz, Verbindung, Datenansicht und Workspace-Projekt. Im Folgenden sind einige Szenarien für das Löschen der jeweiligen Komponenten aufgeführt:

| Aktion | Auswirkung |
| --- | --- |
| Löschen einer Sandbox in [!UICONTROL Adobe Experience Platform] | Durch das Löschen einer Sandbox wird der Datenfluss aller [!UICONTROL Customer Journey Analytics]-Verbindungen zu Datensätzen in dieser Sandbox angehalten. Verbindungen, Datenansichten, Metriken und Dimensionen, die sich auf diese gelöschte Sandbox beziehen, werden ebenfalls gelöscht. | |
| Löschen eines Schemas in [!UICONTROL Adobe Experience Platform], aber nicht der mit diesem Schema verbundenen Datensätze | [!UICONTROL Adobe Experience Platform] erlaubt nicht das Löschen von [!UICONTROL Schemata], denen ein oder mehrere [!UICONTROL Datensätze] zugeordnet sind. Ein Administrator mit den entsprechenden Berechtigungen kann jedoch zuerst die Datensätze und dann das Schema löschen. |
| Löschen eines Datensatzes im Data Lake von [!UICONTROL Adobe Experience Platform] | Durch das Löschen eines Datensatzes im Adobe Experience Platform Data Lake wird der Datenfluss von diesem Datensatz zu allen Customer Journey Analytics-Verbindungen, die diesen Datensatz umfassen, angehalten. Daten aus diesem Datensatz werden automatisch aus den zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| Löschen eines Datensatzes in [!UICONTROL Customer Journey Analytics] | Wenden Sie sich an Ihr Adobe-Accountteam, um den Prozess zum Löschen eines Datensatzes innerhalb einer gespeicherten Verbindung zu starten. |
| Löschen eines Batches aus einem Datensatz (in [!UICONTROL Adobe Experience Platform]) | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Batch aus allen Customer Journey Analytics-Verbindungen entfernt, die diesen Batch enthalten. Customer Journey Analytics wird über das Löschen von Batches in [!UICONTROL Adobe Experience Platform] benachrichtigt. |
| Löschen eines Batches, **während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird | Wenn nur ein Batch im Datensatz vorhanden ist, erscheinen keine Daten oder Teildaten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn das Datensatz beispielsweise fünf Batches enthält und drei davon bereits aufgenommen wurden, als der Datensatz gelöscht wurde, erscheinen die Daten aus diesen drei Batches in [!UICONTROL Customer Journey Analytics]. |
| Löschen einer Verbindung in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist auf Folgendes hin:<ul><li>Alle für die gelöschte Verbindung erstellten Datenansichten werden nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul> |
| Löschen einer Datenansicht in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist darauf hin, dass dann alle Workspace-Projekte, die von dieser gelöschten Datenansicht abhängen, nicht mehr funktionieren. |

## 7. Überlegungen zum Zusammenführen von Report Suites in Customer Journey Analytics {#merge-reportsuite}

Wenn Sie planen, Adobe Analytics-Daten über den [Adobe Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) zu erfassen, sollten Sie diese Auswirkungen beim Zusammenführen von zwei oder mehr Adobe Analytics-Report Suites berücksichtigen.

| Problem | Hinweis |
| --- | --- |
| Variablen | Variablen wie [!UICONTROL eVars] werden möglicherweise nicht in allen Report Suites angezeigt. Beispielsweise kann eVar1 in Report Suite 1 auf **[!UICONTROL Seite]** verweisen. In Report Suite 2 kann eVar1 auf **[!UICONTROL Interne Kampagne]** verweisen, was zu gemischten und ungenauen Berichten führt. |
| Zahlen für [!UICONTROL Sitzungen] und [!UICONTROL Personen] | Sie werden über Report Suites hinweg dedupliziert. Daher stimmen die Zahlen möglicherweise nicht überein. |
| Deduplizierung einer Metrik | Dedupliziert Instanzen einer Metrik (z. B. [!UICONTROL Bestellungen]), wenn mehrere Zeilen dieselbe Transaktions-ID aufweisen (z. B. [!UICONTROL Kauf-ID]). Dadurch wird verhindert, dass Schlüsselmetriken zu häufig gezählt werden. Daher sind die Summen von Metriken wie [!UICONTROL Bestellungen] möglicherweise nicht über Report Suites hinweg korrekt. |
| Währung | Die Währungsumrechnung wird in Customer Journey Analytics noch nicht unterstützt. Wenn die Report Suites, die Sie zusammenführen möchten, unterschiedliche Basiswährungen verwenden, können Probleme auftreten. |
| [!UICONTROL Persistenz] | [Persistenz](../data-views/component-settings/persistence.md) erstreckt sich über Report Suites hinweg, was sich auf [!UICONTROL Filter], [!UICONTROL Attribution] usw. auswirkt. Zahlen werden möglicherweise nicht richtig addiert. |
| [!UICONTROL Klassifizierungen] | [!UICONTROL Klassifizierungen] werden beim Zusammenführen von Report Suites nicht automatisch dedupliziert. Wenn Sie mehrere Klassifizierungsdateien in einem einzigen [!UICONTROL Suchdatensatz] kombinieren, können Probleme auftreten. |

## 8. [!UICONTROL Adobe Analytics]-Komponenten

+++**Kann ich [!UICONTROL Zielgruppen] von [!DNL Customer Journey Analytics] für Experience Platform Real-Time CDP oder andere Experience Cloud-Anwendungen freigeben/veröffentlichen?**

Sie können in Customer Journey Analytics identifizierte [Zielgruppen erstellen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/audiences/publish) und im Echtzeit-Kundenprofil in Adobe Experience Platform veröffentlichen, um sie zum Targeting und zur Personalisierung zu verwenden.

+++

+++**Was ist mit meiner alten [!UICONTROL eVar]-Einstellung passiert?**

[!UICONTROL eVars], [!UICONTROL Eigenschaften] und [!UICONTROL Ereignisse] im Sinne von Adobe Analytics existieren in [!UICONTROL Customer Journey Analytics] nicht mehr. Es gibt unbegrenzt viele Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet.

+++

+++**Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz?**

[!UICONTROL Customer Journey Analytics] verwendet alle diese Einstellungen zum Zeitpunkt der Berichtserstellung. Diese Einstellungen sind nun in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Nun sind mehrere Versionen verfügbar, wenn Sie mehrere Datenansichten verwenden.

+++

+++**Was passiert mit Ihren vorhandenen Segmenten/berechneten Metriken?**

[!UICONTROL Customer Journey Analytics] verwendet keine eVars, Eigenschaften oder Ereignisse mehr, sondern nutzt stattdessen ein beliebiges Adobe Experience Platform-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind.

+++

+++**Wie werden in [!UICONTROL Customer Journey Analytics] `Uniques Exceeded`-Einschränkungen behandelt?**

In [!UICONTROL Customer Journey Analytics] gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen.

+++

+++**Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu [!UICONTROL Customer Journey Analytics] wechseln?**

Das hängt von Ihrem Anwendungsfall ab. Bitte wenden Sie sich an Ihr Adobe-Accountteam. Möglicherweise eignen sich Ihre aktuellen Anwendungsfälle gut für Customer Journey Analytics!

+++

## 9. Schätzen der Verbindungsgröße {#estimate-size}

Siehe [Verwendung von Verbindungen](/help/connections/manage-connections.md#usage).

## 10. Über die Limits bei der Verwendung {#overage}

Nutzungsbeschränkungen werden von Adobe regelmäßig überwacht und durchgesetzt. „Datenzeilen“ sind die täglichen durchschnittlichen Datenzeilen, die innerhalb von Customer Journey Analytics für die Analyse verfügbar sind.

Gehen wir beispielsweise davon aus, Ihr Vertrag berechtigt Sie zu einer Million Datenzeilen. Angenommen, Sie laden am 1. Tag der Verwendung von Customer Journey Analytics zwei Millionen Datenzeilen hoch. Am 2. Tag löschen Sie 1 Million Zeilen und halten Ihre Nutzung für den Rest Ihrer Lizenzlaufzeit auf diesem festgelegten Maximum (d. h. eine Million Datenzeilen). Abhängig von Ihren Vertragsbedingungen können Ihnen für Tag 1 anteilige zusätzliche Nutzungsgebühren entstehen, da Sie die Lizenzberechtigung für „Datenzeilen“ überschritten haben.

## 11. Diskrepanzen bei Daten erkennen {#discrepancies}

In einigen Fällen kann es vorkommen, dass die Gesamtanzahl der von Ihrer Verbindung erfassten Ereignisse sich von der Anzahl der Zeilen im Datensatz in [!UICONTROL Adobe Experience Platform] unterscheidet. In diesem Beispiel enthält der Datensatz „B2B Impression“ 7650 Zeilen, der Datensatz enthält jedoch 3830 Zeilen in [!UICONTROL Adobe Experience Platform]. Es kann mehrere Gründe für Diskrepanzen geben. Die folgenden Schritte können für die Diagnose hilfreich sein:

1. Schlüsseln Sie diese Dimension nach **[!UICONTROL Platform-Datensatz-ID]** auf. Sie werden feststellen, dass es zwei Datensätze mit derselben Größe, aber unterschiedlichen **[!UICONTROL Platform-Datensatz-IDs]** gibt. Jeder Datensatz enthält 3.825 Einträge. Das bedeutet, dass [!UICONTROL Customer Journey Analytics] fünf Datensätze aufgrund fehlender Personen-IDs oder fehlender Zeitstempel ignoriert hat:

   ![Aufschlüsselung](assets/data-size2.png)

1. Wenn Sie außerdem in [!UICONTROL Adobe Experience Platform] nachsehen, gibt es keinen Datensatz mit der ID „5f21c12b732044194bffc1d0“, d. h. jemand hat diesen Datensatz aus [!UICONTROL Adobe Experience Platform] gelöscht, als die erste Verbindung erstellt wurde. Später wurde er erneut zu Customer Journey Analytics hinzugefügt. Es wurde jedoch eine andere [!UICONTROL Platform-Datensatz-ID] von [!UICONTROL Adobe Experience Platform] generiert.

Weitere Informationen über die [Implikationen beim Löschen von Datensätzen und Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components) erhalten Sie in [!UICONTROL Customer Journey Analytics] und [!UICONTROL Adobe Experience Platform].


## 12. Regionale Datenerfassung

Adobe Experience Cloud verwendet die regionale Datenerfassung (Regional Data Collection, RDC), damit Interaktionen zwischen Ihren Besuchenden und Adobe- und Nicht-Adobe-Lösungen so nahe wie möglich an Ihren Besuchenden stattfinden. Sobald Daten regional in einem Datenerfassungszentrum (DCC, auch als Edge-Site bezeichnet, Teil des Platform Edge-Netzwerks) erfasst wurden, werden sie über eine sichere Verbindung zu den relevanten Lösungen weitergeleitet, die auf der Konfiguration Ihres Datenstroms und/oder der Ereignisweiterleitung basieren.

![Datenfluss mithilfe von Edge-Netzwerken](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png?lang=de)

Der regionale Datenerfassungsprozess umfasst die folgenden Schritte:

1. DNS löst den Hostnamen der Sammlung automatisch in die IP-Adresse des Datenerfassungszentrums auf, das den Besuchenden am nächsten liegt.
1. Die Besucherin oder der Besucher sendet die Daten an diesen Ort.
1. Die Daten werden sofort über eine sichere Verbindung an die Lösungen weitergeleitet, die durch die Konfiguration der Datenspeicherung oder Ereignisweiterleitung definiert wurden.

Die Verwendung der regionalen Datenerfassung bietet verschiedene Vorteile:

* **Leistung**: Mit der RDC verbinden sich Ihre Besuchenden mit dem nächstgelegenen DCC. Diese Optimierung bietet die schnellste Reaktionszeit, was zu einem genaueren Tracking und schnelleren Ladezeiten führt.
* **Redundanz**: Bei einer Unterbrechung der Kommunikation zwischen dem DCC und Ihrem DPC speichert die RDC-Infrastruktur von Adobe die Daten lokal und leitet sie dann an das DPC weiter, sobald die Kommunikation wiederhergestellt ist.

RDC enthält derzeit die folgenden Speicherorte (kann sich ändern):


| RDC-Typ | Data Collection Centers |
| --- | --- |
| Global (Standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapur, Tokio, Sydney |
| Nur Amerika | Oregon, Virginia |
| Nur Europa | Irland, Paris |
| Nur Asien | Mumbai, Singapur, Tokio, Sydney |

{style="table-layout:auto"}

Wenn die Daten das regionale Rechenzentrum erreichen, bestimmt die Konfiguration des Datenspeichers, wie die Daten weitergeleitet werden.

Für Customer Journey Analytics werden Datensätze von Adobe Experience Platform benötigt. Ihre Datenstrom-/Ereignisweiterleitungskonfiguration erfordert daher, dass der Adobe Experience Platform-Dienst die Daten vom regionalen Rechenzentrum an das Rechenzentrum weiterleitet, in dem sich Ihre Adobe Experience Platform-Instanz befindet. Customer Journey Analytics und die zugehörigen unterstützenden Dienste und Infrastrukturen werden in derselben Adobe Experience Platform-Instanz bereitgestellt.


Weitere Informationen über den Datenerfassungsprozess außerhalb von Adobe Experience Platform Edge Network und der entsprechenden regionalen Rechenzentren finden Sie unter [Datenerfassung – Übersicht](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html?lang=de).
