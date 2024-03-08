---
title: Stitching-Übersicht
description: Übersicht über das Stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 18%

---

# Stitching-Übersicht

Die Identitätszuordnung (oder einfach das Stitching) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die kanalübergreifende Analyse erhöht. Die kanalübergreifende Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics handhaben kann. So können Sie Berichte auf Basis einer gemeinsamen Kennung (Personen-ID) nahtlos kombinieren und für mehrere Datensätze aus verschiedenen Kanälen ausführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit der kanalübergreifenden Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die sie ursprünglich geklickt haben.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Customer Journey Analytics-Verbindung sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere verfügen Web- oder mobile-basierte Erlebnisdatensätze häufig nicht über tatsächliche Personen-ID-Informationen für alle Ereignisse.

Die Zuordnung ermöglicht die Neuzuordnung von Identitäten in den Zeilen eines Datensatzes und stellt sicher, dass die Personen-ID (zugeordnete ID) für jedes Ereignis verfügbar ist. Beim Zuordnen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um den allgemeinen vorübergehenden ID-Wert zu ermitteln, der als zugeordnete ID verwendet werden kann. Diese Neuzuweisung ermöglicht die Auflösung verschiedener Datensätze zu einer einzigen zugeordneten ID, die auf der Personenebene und nicht auf der Geräte- oder Cookie-Ebene analysiert werden kann.

Sie profitieren von einer kanalübergreifenden Analyse, wenn Sie einen oder mehrere Ihrer zugeordneten Datensätze mit anderen Datensätzen, z. B. Callcenter-Daten, kombinieren, um Ihre Customer Journey Analytics-Verbindung zu definieren. Dabei wird davon ausgegangen, dass diese anderen Datensätze bereits in jeder Zeile eine Personen-ID enthalten, die der zugeordneten ID ähnelt.


## Voraussetzungen

{{select-package}}

>[!IMPORTANT]
>
>Wenn nicht alle Voraussetzungen erfüllt sind, kann die Durchführung einer kanalübergreifenden Analyse fehlschlagen.

Stellen Sie vor der Verwendung von Stitching sicher, dass Ihr Unternehmen wie folgt vorbereitet ist:

* Importieren Sie die gewünschten Daten in Adobe Experience Platform:

   * Informationen zu Adobe Analytics-Daten finden Sie unter [Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) und [Aufnehmen von Daten](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) in der Adobe Experience Platform-Dokumentation.

* Der Ereignisdatensatz in Adobe Experience Platform, auf den Sie die Zuordnung anwenden möchten, muss zwei Spalten enthalten, die die Identifizierung von Besuchern erleichtern:

   * Eine **beständige ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics-AppMeasurement-Bibliothek generiert wurde, oder eine ECID, die vom Adobe Experience Cloud Identity-Dienst generiert wurde.
   * Eine **vorübergehende ID**, eine Kennung, die nur in einigen Zeilen vorhanden ist. Beispiel: ein/e gehashte/r Benutzername oder E-Mail-Adresse, wenn sich ein Besucher authentifiziert. Sie können praktisch jede beliebige Kennung verwenden. Beim Zuordnen werden in diesem Feld die tatsächlichen Personen-ID-Informationen gespeichert. Für optimale Zuordnungsergebnisse sollte für jede beständige ID mindestens einmal innerhalb der Ereignisse des Datensatzes eine vorübergehende ID gesendet werden. Wenn Sie diesen Datensatz in eine Customer Journey Analytics-Verbindung einschließen möchten, sollten die anderen Datensätze ebenfalls eine ähnliche gemeinsame Kennung aufweisen.

  Beide Spalten (beständige ID und vorübergehende ID) müssen als Identitätsfeld mit einem Identitäts-Namespace im Schema definiert werden, der dem Datensatz zugrunde liegt, den Sie zuordnen möchten. Bei Verwendung der Identitätszusammenfügung in Real-time Customer Data Platform mithilfe des [identityMap-Feldergruppe](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#identity)müssen Sie weiterhin Identitätsfelder mit einem Identitäts-Namespace hinzufügen, da die in diesem Abschnitt besprochene Zuordnung von Customer Journey Analytics die Feldergruppe identityMap nicht unterstützt. Legen Sie beim Hinzufügen eines Identitätsfelds zum Schema und bei Verwendung der Identitätszuordnungsfeldgruppe das zusätzliche Identitätsfeld nicht als primäre Identität fest, da dies die für die Real-time Customer Data Platform verwendete Feldgruppe identityMap stört.

* Die Zuordnung umfasst das Zusammenführen authentifizierter und nicht authentifizierter Benutzerdaten. Stellen Sie sicher, dass Sie die geltenden Gesetze und Vorschriften einhalten, einschließlich der Erlangung der erforderlichen Endbenutzerberechtigungen, bevor Sie die Zuordnung für einen Ereignis-Datensatz aktivieren. Siehe [Identitätsfelder in der Benutzeroberfläche definieren](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#) für weitere Informationen.


## Stitching verwenden

Sobald Ihr Unternehmen alle Voraussetzungen erfüllt und die [Einschränkungen](#limitations)können Sie die folgenden Schritte ausführen, um die Stitching-Funktion in Customer Journey Analytics zu verwenden:

### Support anfordern

1. Wenden Sie sich mit den folgenden Informationen an den Adobe-Support:

   * Eine Anfrage zum Aktivieren der Zuordnung.
   * Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten.
   * Der Spaltenname der beständigen ID für den gewünschten Datensatz (Kennung, die in jeder Zeile angezeigt wird).
   * Der Spaltenname der vorübergehenden ID für den gewünschten Datensatz (die Personenkennung, die auch als Verknüpfung zwischen Datensätzen im Kontext einer Verbindung dient).
   * Ihre Voreinstellung für die Häufigkeit der [Wiederholungen](explained.md) und die Lookback-Länge. Zu den verfügbaren Optionen gehören eine Wiederholung pro Woche mit einem 7-tägigen Lookback-Fenster oder eine tägliche Wiederholung mit einem 1-tägigen Lookback-Fenster.
   * Sandbox-Name.


2. Der Adobe-Kundensupport arbeitet mit Adobe-Engineering zusammen, um das Stitching nach Erhalt Ihrer Anfrage zu aktivieren. Nach der Aktivierung wird in Adobe Experience Platform ein neuer neu zugewiesener Datensatz mit einer neuen Spalte für die zugeordnete ID angezeigt. Der Adobe-Kundensupport kann die ID des neuen Datensatzes angeben.

3. Nach der ersten Aktivierung bietet Adobe eine Aufstockung der zugewiesenen Daten, die 60 Tage zurückreicht.

4. Wenn Sie den neuen zugeordneten Datensatz in einer kanalübergreifenden Analyse verwenden möchten, müssen Sie ihn zu einem [connection](../connections/overview.md) in Customer Journey Analytics zusammen mit allen anderen erforderlichen Datensätzen. Wählen Sie für jeden Datensatz die korrekte Personen-ID.

5. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Datenansicht eingerichtet ist, können Sie Ihre Customer Journey Analytics-Berichtsanalyse kanalübergreifend und geräteübergreifend ausführen.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Einschränkungen

>[!IMPORTANT]
>
>* Wenden Sie alle Änderungen, die Sie an dem Schema des globalen Ereignis-Datensatzes vornehmen, auch auf das neue zugeordnete Datensatzschema an, da es andernfalls den zugewiesenen Datensatz beschädigt.
>
>* Wenn Sie den Quelldatensatz entfernen, stoppt der zugeordnete Datensatz die Verarbeitung und wird vom System entfernt.
>
>* Datennutzungsbezeichnungen werden nicht automatisch in das zugeordnete Datensatzschema übertragen. Wenn Sie Datennutzungsbezeichnungen auf das Quelldatensatzschema angewendet haben, müssen Sie diese Datennutzungsbezeichnungen manuell auf das zugeordnete Datensatzschema anwenden. Siehe [Verwalten von Datennutzungsbezeichnungen in Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=de) für weitere Informationen.

Das Stitching ist eine innovative und zuverlässige Funktion, die jedoch Einschränkungen hinsichtlich der Verwendung aufweist.

* Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
* Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
* Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
* Beim Stitching wird das für das Stitching verwendete Feld in keiner Weise umgewandelt. Beim Zuordnen wird der Wert im angegebenen Feld verwendet, da er im nicht zugeordneten Datensatz im Data Lake vorhanden ist. Beim Zuordnen wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise manchmal das Wort &quot;Bob&quot;im Feld erscheint und manchmal das Wort &quot;BOB&quot;erscheint, werden diese IDs als zwei separate Personen behandelt.
* Beim Stitching wird zwischen Groß- und Kleinschreibung unterschieden. Für Datensätze, die über den Analytics-Quell-Connector generiert werden, empfiehlt Adobe die Überprüfung aller VISTA-Regeln oder Verarbeitungsregeln, die für das vorübergehende ID-Feld gelten. Diese Überprüfung stellt sicher, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die vorübergehende ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
* Beim Stitching werden keine Felder kombiniert oder verkettet.
* Das Feld für die vorübergehende ID sollte einen einzelnen ID-Typ enthalten ( IDs aus einem einzelnen Namespace). Das Feld für die vorübergehende ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
* Wenn mehrere Ereignisse mit demselben Zeitstempel für dieselbe beständige ID auftreten, aber unterschiedliche Werte im Feld der vorübergehenden ID vorhanden sind, wird bei der Zuordnung die ID basierend auf der alphabetischen Reihenfolge ausgewählt. Wenn also eine beständige ID A zwei Ereignisse mit demselben Zeitstempel aufweist und eines der Ereignisse &quot;Bob&quot;und das andere &quot;Ann&quot;angibt, wählt &quot;Zuordnen&quot;Ann.
* Wenn ein Gerät von mehreren Personen gemeinsam genutzt wird und die Gesamtzahl der Übergänge zwischen Benutzern 50.000 überschreitet, stoppt Customer Journey Analytics die Zuordnung von Daten für dieses Gerät.
* Seien Sie vorsichtig bei Szenarien, in denen die vorübergehenden IDs Platzhalterwerte enthalten, z. B. &quot;Nicht definiert&quot;. Siehe [FAQs](faq.md) für weitere Informationen.

Verwechseln Sie nicht das Stitching mit:

* Die Zusammenführung von zwei oder mehr Datensätzen. Die Zuordnung gilt nur für einen Datensatz. Die Zusammenführung von Datensätzen erfolgt durch Einrichten einer Customer Journey Analytics-Verbindung und Auswählen derselben Personen-ID für die ausgewählten Datensätze in der Verbindung.

* Der Join zweier Datensätze. Unter Customer Journey Analytics wird häufig ein Join für Suchen oder Klassifizierungen in Analysis Workspace verwendet. Obwohl das Stitching die Join-Funktion verwendet, umfasst der Prozess selbst mehr als nur Joins.
