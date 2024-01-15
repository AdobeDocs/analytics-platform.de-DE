---
title: Überblick über die Cross-Channel-Analyse
description: Neuverknüpfung von Personen-IDs aus mehreren Datensätzen, um Personen zuzuordnen.
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 98%

---


# Überblick über die Cross-Channel-Analyse

**Journey IQ: Die Cross-Channel-Analyse** ist eine Funktion, mit der Sie die Personen-ID eines Datensatzes neu eingeben können. Dies ermöglicht eine nahtlose Kombination mehrerer Datensätze. Die kanalübergreifende Analyse untersucht Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen, um eine zugeordnete ID zu generieren. Mithilfe der Cross-Channel-Analyse können Sie Fragen beantworten wie beispielsweise:

* Wie viele Personen beginnen ihr Erlebnis auf einem Kanal und beenden es auf einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs auf einem Gerät zur Konversion auf einem anderen Gerät?
* Wie ändern sich meine Daten zur Wirksamkeit einer Kampagne, wenn ich geräteübergreifende Journeys berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit der Cross-Channel-Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die ursprünglich geklickt wurde.

## Voraussetzungen

>[!IMPORTANT]
>
>Werden nicht alle Voraussetzungen erfüllt, kann beim Kombinieren von Datensätzen unter Umständen keine Verbindung für die kanalübergreifende Analyse hergestellt werden oder die Ergebnisse fallen mangelhaft aus.

Bevor Sie die Cross-Channel-Analyse verwenden, sollten Sie sicherstellen, dass Ihr Unternehmen folgende Voraussetzungen erfüllt:

* Ein Datensatz in Adobe Experience Platform muss über zwei Spalten verfügen, mit denen Personen identifiziert werden können:
   * Eine **beständige ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Personen-ID, die von einer Adobe Analytics-AppMeasurement-Bibliothek generiert wurde.
   * Eine **vorübergehende ID**, eine Kennung, die nur in einigen Zeilen vorhanden ist. Beispielsweise ein gehashter Benutzername oder eine gehashte E-Mail-Adresse, wenn sich eine Person authentifiziert. Sie können praktisch jede beliebige Kennung verwenden, sofern sie mindestens einmal für dasselbe Ereignis als beständige ID vorkommt.
* Ein anderer Datensatz, beispielsweise Callcenter-Daten, der in jeder Zeile eine vorübergehende ID enthält. Diese Personen-ID muss ähnlich wie die vorübergehende ID in dem anderen Datensatz formatiert sein.
* Mit dieser Funktion können Sie Datensätze zuordnen und somit beispielsweise authentifizierte und nicht authentifizierte Benutzerdaten zusammenführen. Vergewissern Sie sich vor dem Zusammenführen von Datensätzen, dass Sie die geltenden Gesetze und Vorschriften einhalten, wie etwa das Einholen der erforderlichen Berechtigungen der Endanwender.

## Einschränkungen

>[!IMPORTANT]
>
>Jede Änderung des globalen Ereignis-Datensatz-Schemas muss auch im neuen Schema des zusammengefügten Datensatzes angewendet werden, da sie sonst den zusammengefügten Datensatz zerstört.
>
>Wenn Sie den Quelldatensatz entfernen, wird der zugeordnete Datensatz nicht weiter verarbeitet und vom System entfernt.

Die Cross-Channel-Analyse ist eine innovative und zuverlässige Funktion, deren Verwendung jedoch gewissen Einschränkungen unterliegt.

* Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
* Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
* Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
* Das geräteübergreifende private Diagramm wird nicht unterstützt.
* Die Cross-Channel-Analyse transformiert nicht das zum Verbinden verwendete Feld. Die feldbasierte Zuordnung verwendet den Wert im angegebenen Feld so, wie er im nicht zugewiesenen Datensatz innerhalb des Datensees vorhanden ist. Bei der Zuordnung wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise das Wort „Bob“ im Feld erscheint und manchmal das Wort „BOB“ angezeigt wird, werden diese als zwei separate Personen behandelt.
* Da bei der feldbasierten Zuordnung die Groß- und Kleinschreibung beachtet wird, empfiehlt Adobe für Analytics-Datensätze, die über den Analytics-Quell-Connector generiert werden, die Überprüfung aller VISTA-Regeln oder Verarbeitungsregeln, die für das Feld für die vorübergehende ID gelten, um sicherzustellen, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die vorübergehende ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
* Bei der feldbasierten Suche werden Felder nicht kombiniert oder verknüpft.
* Das Feld für die vorübergehende ID sollte nur einen ID-Typ enthalten (also IDs aus einem einzigen Namespace). Das Feld für die vorübergehende ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
* Wenn mehrere Ereignis mit demselben Zeitstempel für dieselbe permanente ID auftreten, jedoch unterschiedliche Werte im Feld für die vorübergehende ID vorliegen, wird die feldbasierte Zuordnung auf Grundlage der alphabetischen Reihenfolge gewählt. Wenn also eine permanente ID A zwei Ereignisse mit demselben Zeitstempel hat und eines der Ereignis „Bob“ und das andere „Ann“ angibt, wählt die feldbasierte Zuordnung „Ann“.
* Wenn ein Gerät von mehreren Personen gemeinsam genutzt wird und die Gesamtzahl der Transitionen aller Benutzer 50.000 überschreitet, stoppt die kanalübergreifende Analyse die Zuordnung von Daten für dieses Gerät.

## Aktivieren der Cross-Channel-Analyse

Sobald Ihre Organisation alle Anforderungen erfüllt und die Einschränkungen überblickt, können Sie die folgenden Schritte ausführen, um mit der Verwendung in Customer Journey Analytics zu beginnen.

1. Importieren Sie die gewünschten Daten in Adobe Experience Platform. Informationen zu Adobe Analytics-Daten finden Sie unter [Verwenden von Adobe Analytics-Report-Suite-Daten in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) und [Aufnehmen von Daten](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) in der Adobe Experience Platform-Dokumentation.
1. Wenden Sie sich mit den folgenden Informationen an den Adobe-Support:
   * Eine Anfrage zur Aktivierung der Cross-Channel-Analyse
   * Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten
   * Der Spaltenname der beständigen ID für den gewünschten Datensatz (Kennung, die in jeder Zeile erscheint)
   * Der Spaltenname der vorübergehenden ID für den gewünschten Datensatz (die Verbindung der Personenkennung zwischen Datensätzen)
   * Ihre Voreinstellung für die Häufigkeit der [Wiederholungen](replay.md) und die Lookback-Länge. Zu den verfügbaren Optionen gehören eine Wiederholung pro Woche mit einem 7-tägigen Lookback-Fenster oder eine tägliche Wiederholung mit einem 1-tägigen Lookback-Fenster.
   * Sandbox-Name.
1. Wenn Sie eine Anfrage bezüglich der Cross-Channel-Analyse an den Adobe-Support stellen, wird diese Funktion in Zusammenarbeit mit dem Engineering-Team von Adobe aktiviert. Nach der Aktivierung wird in Adobe Experience Platform ein neu verschlüsselter Datensatz angezeigt, der eine neue Spalte für die Personen-ID enthält. Der Adobe-Support stellt die neue Datensatz-ID und den Namen der Personen-ID-Spalte bereit.
1. Bei der erstmaligen Verwendung stellt Adobe eine Aufstockung der zugeordneten Daten bereit, die bis zum Beginn des Vormonats zurückreicht (bis zu 60 Tage). Um diese Aufstockung durchführen zu können, muss die vorübergehende ID in den nicht zugewiesenen Daten aus dem so weit zurückreichenden Zeitfenster vorhanden sein.
1. [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md) in Customer Journey Analytics unter Verwendung des neu generierten Datensatzes und anderer Datensätze, die Sie einbeziehen möchten. Wählen Sie für jeden Datensatz die korrekte Personen-ID.
1. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Datenansicht eingerichtet ist, erfolgt die Analyse in Customer Journey Analytics genau wie bei jeder anderen Customer Journey Analytics-Analyse, nur dass die Daten jetzt kanal- und geräteübergreifend verarbeitet werden.
