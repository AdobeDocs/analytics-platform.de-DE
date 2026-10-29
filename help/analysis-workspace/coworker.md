---
title: Analysieren und Erstellen von Workspace-Projekten mit einem Kollegen
description: Verwenden Sie das produktinterne Erlebnis für Kollegen, um das geöffnete Projekt zusammenzufassen, Erkenntnisse zu finden und Bedienfelder, Tabellen und Segmente aus Eingabeaufforderungen in natürlicher Sprache zu erstellen.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 88e67c92fc170b340149c9ab73ad5eea2122da2b
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 1%
---
# Verwenden des produktinternen Erlebnisses für Kollegen

>[!AVAILABILITY]
>
>Die in diesem Abschnitt beschriebenen Funktionen befinden sich in der eingeschränkten Testphase der Version und sind möglicherweise noch nicht in Ihrer Umgebung verfügbar. Darüber hinaus verwendet Coworker generative KI, was zu ungenauen oder unerwarteten Ergebnissen führen kann. Überprüfen Sie die Antworten der Kollegen und alle Änderungen, die sie an Ihrem Projekt vornehmen, bevor Sie sie bearbeiten oder das Projekt freigeben.

Das produktinterne Erlebnis für Kollegen ist in einem Chat-Panel auf der rechten Seite von Analysis Workspace verfügbar. Coworker verwendet das geöffnete Projekt als Kontext, sodass Sie nach Ihrer Analyse fragen oder ein Coworker das Projekt erstellen lassen kann, ohne zu erklären, was es enthält.

## Kollegen in Workspace verstehen

### Voraussetzungen

* **Mitarbeiter ist für Ihr Unternehmen aktiviert**: Das produktinterne Erlebnis für Mitarbeiter ist standardmäßig deaktiviert. Ein Customer Journey Analytics-Administrator muss sie für das Unternehmen aktivieren, bevor Benutzer darauf zugreifen können.

  Wenn Sie in Workspace nicht auf einen Mitarbeiter zugreifen können, wenden Sie sich an Ihren Administrator. Weitere Informationen finden Sie unter [IMS-Organisationsvoreinstellungen](/help/analysis-workspace/user-preferences.md#ims-organization-preferences). <!-- need to update this section with the new toggle -->

* **Datenansichtszugriff**: Der -Mitarbeiter verwendet Ihre bestehenden Analysis Workspace- und Datenansichtsberechtigungen. Es kann nicht auf Daten oder Komponenten zugreifen, auf die Sie noch keinen Zugriff haben.

<!--
FOLLOW-UP: Coworker permissions are still being finalized. The Coworker permission name below is a placeholder. Confirm the name, category, and Admin Console steps with the SME.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Coworker]** permission determines access to Coworker. A [product profile administrator](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) must add this permission to your product profile. For more information, see [Access control](/help/technotes/access-control.md#access-control).

-->

### Wählen Sie zwischen Coworker in Workspace und der Coworker-Anwendung

Das produktinterne Erlebnis für Mitarbeiter verfügt über viele Funktionen wie das [CX Enterprise Coworker-Programm](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat) einschließlich der Fähigkeiten, auf die Sie Zugriff haben. Es gibt jedoch wichtige Unterschiede, die bestimmen, wann Sie eine verwenden können:

| | Produktinternes Erlebnis für Mitarbeiter | Partneranwendung |
| --- | --- | --- |
| **Verwendung** | Sie möchten ein Projekt erstellen, das Sie beibehalten, für andere Benutzer freigeben oder im Laufe der Zeit aktualisieren möchten. | Sie wollen eine schnelle Antwort. Bei Bedarf können Sie die Analyse später in ein Workspace-Projekt umwandeln. |
| **Kontext** | Projektorientiert<p>Verwendet das geöffnete Workspace-Projekt als Ausgangspunkt. Sie können auf Bereiche, Tabellen und Komponenten verweisen, die sich bereits im Projekt befinden, und auf diese aufbauen.</p> | Datenansichtsorientiert<p>Verwendet die Datenansichten, auf die Sie Zugriff haben, oder diejenigen, die Sie als Voreinstellung im Arbeitsspeicher des Kollegen festgelegt haben. In der Eingabeaufforderung wird beschrieben, was analysiert werden soll.</p> |
| **Typischer Benutzer** | Analysten, die Analysen in Workspace erstellen und validieren. | Business-Anwender, die Antworten wünschen, ohne auf Workspace zugreifen oder es lernen zu müssen. |
| **Ausgabe** | Coworker fügt Bedienfelder, Tabellen und Komponenten direkt zum Workspace-Projekt hinzu. <p>Gegebenenfalls antwortet er auch im Chat.</p> | Antworten und Analysen werden im Gespräch bereitgestellt, mit der Option, in Analysis Workspace zu öffnen. |

### Was Sie mit einem Kollegen tun können

#### Fragen zum offenen Projekt stellen

Sie können Fragen an Kollegen stellen wie:

* Fassen Sie das Projekt zusammen.
* Finden Sie Einblicke und markieren Sie Anomalien in den Daten.
* Führen Sie eine Ursachenanalyse für ein Bedienfeld aus.
* Erklären Sie, wie Sie etwas in Analysis Workspace tun, z. B. ein Liniendiagramm hinzufügen oder Tabellenzellen basierend auf ihren Werten einfärben.
* Eine Komponente zu erklären, z. B. eine Metrik oder Dimension.

Weitere Informationen finden Sie unter [Fragen zu einem Projekt stellen](#ask-questions-about-a-project).

#### Erstellen und Bearbeiten des geöffneten Projekts

Sie können Kollegen bitten, beispielsweise folgende Aufgaben auszuführen:

* Erstellen Sie ein Freiform-Bedienfeld mit den Dimensionen, Metriken und dem Datumsbereich, die Sie angeben.
* Fügen Sie dem Projekt Bedienfelder hinzu. Coworker fügt neue Bereiche hinzu, ohne die vorhandenen Bereiche zu überschreiben.
* Tabellen aufschlüsseln oder Vergleichsspalten hinzufügen.
* Ändern des Datumsbereichs oder des Visualisierungstyps eines Bedienfelds, z. B. Ändern einer Tabelle in ein Liniendiagramm.
* Umbenennen eines Bereichs.
* Vorhandenes Segment anhand des Namens anwenden, ein Segment aus einer einfachen Beschreibung erstellen oder ein Segment kopieren und seine Logik ändern.
* Erstellen Sie Datumsbereiche und einfache berechnete Metriken.
* Fügen Sie dem Projekt Beschreibungen oder eine Textvisualisierung hinzu, die Einblicke enthält.
* Erstellen Sie ein Projekt mit mehreren Bedienfeldern oder kopieren Sie ein Projekt und passen Sie es für eine andere Zielgruppe oder Region an.
* Speichern Sie das Projekt.

Weitere Informationen finden Sie unter [Aktualisieren eines Projekts](#update-a-project).

### Wenn ein Kollege das Projekt oder die Antworten im Chat aktualisiert

Ein Mitarbeiter entscheidet, ob er im Chat-Panel antwortet oder das Projekt je nach Fragen ändert. Weitere Informationen finden Sie unter [Aktualisieren eines Projekts](#update-a-project) und [Fragen zu einem Projekt stellen](#ask-questions-about-a-project).

Sie können auch explizit angeben, was Ihre Kollegen tun sollen. Sie können zum Beispiel Phrasen wie _im Chat_ oder _sagen Sie mir_ verwenden, um eine Antwort im Chat-Bereich zu erhalten, oder Phrasen wie _Zum Projekt hinzufügen_ oder _in dieser Tabelle_, um das Projekt zu aktualisieren.

## Verwenden von Coworker mit Ihren Projekten

Kollegen können alle Bedienfelder und Tabellen im geöffneten Projekt sehen. Sie können Ihre Kollegen bitten, Fragen zum Projekt zu beantworten oder sie bei der Aktualisierung zu unterstützen.

>[!TIP]
>
>Sie können die Zusammenarbeit jederzeit unterbrechen oder das Projekt aktualisieren:
>
>* **Aufgabe steuern oder anhalten**: Während der Kollege arbeitet, drücken Sie **Umschalt+Eingabe**, um ihm mehr Richtung zu geben, oder drücken Sie **Esc**, um sie anzuhalten.
>
>* **Nehmen Sie Aktualisierungen an einem Projekt in Workspace vor**: Wenn Sie das Projekt bearbeiten, während der -Mitarbeiter arbeitet, erkennt der -Mitarbeiter Ihre Änderungen.

### Aktualisieren eines Projekts

Wenn Sie einen Mitarbeiter bitten, im Projekt etwas zu erstellen oder zu bearbeiten, aktualisiert der Mitarbeiter das Projekt entsprechend. Dazu gehören Anfragen, die mit Wörtern wie _Hinzufügen_, _Erstellen_, _Bearbeiten_, _Aufschlüsselung_, _Ändern_ und _Vergleichen_ beginnen. Beispielsweise können Sie Kollegen bitten, Bereiche und Tabellen hinzuzufügen, Daten aufzuschlüsseln oder Segmente zu erstellen.

1. Öffnen Sie in Customer Journey Analytics ein vorhandenes Workspace-Projekt oder erstellen Sie ein neues Projekt.

1. Wählen Sie das **Mitarbeiter**-Symbol ![Mitarbeiter fragen](/help/assets/icons/coworker.svg) in der oberen rechten Ecke der Kopfzeile aus, um das Bedienfeld für den Mitarbeiter-Chat zu öffnen.

1. Beschreiben Sie im Chat-Panel, was Sie von einem Kollegen erwarten.

   In der folgenden Tabelle sind Beispielaufforderungen aufgeführt.

   | Eingabeaufforderung | Was ein Kollege tut |
   | --- | --- |
   | _Anzeigen der Sitzungen nach Seite für den letzten Monat_ | Fügt ein neues Freiform-Bedienfeld mit der angegebenen Dimension, Metrik und dem angegebenen Datumsbereich hinzu. Vorhandene Bedienfelder werden nicht überschrieben. |
   | _Diese Tabelle nach Gerät aufschlüsseln_ | Fügt der referenzierten Tabelle die Aufschlüsselung hinzu. |
   | _Fügen Sie in dieser Tabelle einen Vergleich mit dem letzten Monat hinzu_ | Fügt der referenzierten Tabelle eine Vergleichsspalte hinzu. |
   | _Ändern Sie den Datumsbereich dieses Bedienfelds in „Letzter Monat“_ | Aktualisiert den Datumsbereich des Bedienfelds. |
   | _Ändern Sie diese Tabelle in ein Liniendiagramm_ | Ändert den Visualisierungstyp des Bedienfelds. |
   | _Benennen Sie dieses Bedienfeld in „Leistung für Mobilgeräte“ um_ | Benennt das Bedienfeld um. |
   | _Wenden Sie das Segment „Mobile-Benutzer“ auf dieses Bedienfeld an_ | Wendet das vorhandene Segment auf das Bedienfeld an. Der Mitarbeiter kennt die Segmentdefinition nicht. Stellen Sie daher sicher, dass das Segment das enthält, was Sie erwarten. |
   | _Erstellen Sie ein Segment für Besucher aus Kanada_ | Erstellt das Segment und fügt es dem Projekt hinzu. Das Segment wird nach dem Aktualisieren der Seite in der Komponentenliste angezeigt. |
   | _Kopieren Sie das Segment „Canada Visitors“ und ändern Sie es in „Visitors from Mexico“_ | Erstellt eine Kopie des Segments mit der aktualisierten Logik und fügt es dem Projekt hinzu. |
   | _Erstellen Sie einen Datumsbereich für die letzten 6 Wochen_ | Erstellt den Datumsbereich. Der Datumsbereich wird ohne Aktualisierung in der Komponentenliste angezeigt. |
   | _Erstellen einer berechneten Metrik für den Umsatz pro Sitzung_ | Erstellt die berechnete Metrik. Mitarbeiter können einfache berechnete Metriken erstellen. |
   | _Fügen Sie diesem Bedienfeld eine Beschreibung hinzu, die den Rückgang der Besuche erklärt_ | Fügt dem Bedienfeld die Beschreibung hinzu. |
   | _Fügen Sie eine Textvisualisierung mit den wichtigsten Erkenntnissen hinzu_ | Fügt eine Textvisualisierung hinzu, die die Einblicke zum Projekt enthält. |
   | _Erstellen Sie ein Projekt mit Bedienfeldern für Traffic, Konversion und Umsatz_ | Erstellt ein Projekt mit einem Bedienfeld für jeden Bereich, den Sie beschreiben. |
   | _Kopieren Sie dieses Projekt und passen Sie es für die Region EMEA an_ | Erstellt eine Kopie des Projekts und passt sie für die angegebene Region an. |
   | _Speichern Sie das Projekt_ | Speichert das Projekt. |
   | _Machen Sie die hinzugefügte Aufschlüsselung rückgängig_ | Macht die angegebene Änderung rückgängig. |
   | _Löschen der alten Bedienfelder_ | Listet die Bereiche auf, die gelöscht werden sollen, und wartet auf Ihre Bestätigung, bevor sie gelöscht werden. |

1. Überprüfen Sie die Änderungen, die ein Mitarbeiter am Projekt vorgenommen hat. Weitere Informationen finden Sie unter [Überprüfen der Ergebnisse von ](#verify-coworker-results).

### Fragen zu einem Projekt stellen

Wenn Sie Fragen zu einem Projekt stellen, antwortet der Mitarbeiter im Chat-Bedienfeld. Dazu gehören Anfragen wie _Erläutern_, _Zusammenfassen_, _Diskutieren_ und _Erzählen Sie mir mehr_. Ergebnisse aus der Ursachenanalyse und ähnliche Fähigkeiten bleiben ebenfalls im Chat-Panel, bis Sie Ihren Kollegen bitten, sie zum Projekt hinzuzufügen.

1. Öffnen Sie in Customer Journey Analytics ein vorhandenes Workspace-Projekt oder erstellen Sie ein neues Projekt.

1. Wählen Sie das **Mitarbeiter**-Symbol ![Mitarbeiter fragen](/help/assets/icons/coworker.svg) in der oberen rechten Ecke der Kopfzeile aus, um das Bedienfeld für den Mitarbeiter-Chat zu öffnen.

1. Beschreiben Sie im Chat-Panel, was Sie von einem Kollegen erwarten.

   In der folgenden Tabelle sind Beispielaufforderungen aufgeführt.

   | Eingabeaufforderung | Was ein Kollege tut |
   | --- | --- |
   | _Dieses Projekt zusammenfassen_ | Bietet eine Zusammenfassung im Chatbereich und Angebote, um sie als Textvisualisierung zum Projekt hinzuzufügen. |
   | _Einblicke in dieses Projekt erhalten_ | Bietet Einblicke in den Chat-Bereich und Angebote, um die Ergebnisse zum Projekt hinzuzufügen. |
   | _Markieren Sie alle Anomalien in diesem Bedienfeld_ | Beschreibt die Anomalien im Chatbereich. Wenn Sie einen Kollegen bitten, Anomalien in einer Visualisierung anzuzeigen, werden die Anomalien möglicherweise nicht angezeigt. Siehe [Aktuelle Einschränkungen](#current-limitations). |
   | _Führen Sie eine Ursachenanalyse zum Rückgang der mobilen Besuche durch_ | Stellt die Analyse im Chat-Bedienfeld bereit und bietet die Möglichkeit, die Ergebnisse zum Projekt hinzuzufügen. |
   | _Wie färbe ich Zellen basierend auf ihren Werten?_ | Erklärt die Schritte im Chatbedienfeld. |
   | _Erläuterung der Metrik „Absprungrate“_ | Erklärt die Komponente im Chatbedienfeld. Die Erklärung kommt nicht aus dem [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md). Die Unterstützung für Datenwörterbuchdefinitionen ist für eine künftige Version geplant. |

1. Überprüfen Sie die Antwort von Coworker. Weitere Informationen finden Sie unter [Überprüfen der Ergebnisse von ](#verify-coworker-results).

## Überprüfen der Ergebnisse der Mitarbeiter

Ein Mitarbeiter hilft Ihnen, die Genauigkeit der Ergebnisse zu überprüfen. Beachten Sie bei der Überprüfung Folgendes:

* **Coworker zeigt seine Arbeit**: Die Segmente, Metriken und Filter, die Coworker zur Beantwortung einer Frage verwendet, werden dem Projekt hinzugefügt, damit Sie sie überprüfen können.

* **Klärende Fragen**: Wenn eine Anfrage vage ist oder mit mehr als einer Komponente übereinstimmt, stellt ein Mitarbeiter eine klärende Frage oder schlägt Optionen zur Auswahl vor. Wenn beispielsweise mehr als eine Metrik mit dem von Ihnen verwendeten Namen übereinstimmt, schlägt ein Mitarbeiter die entsprechenden Metriken vor.

* **Hinweise zur Datenqualität**: Die Antworten von Coworker enthalten Hinweise zur Datenqualität. Wenn Sie beispielsweise einen Monat, der gerade erst begonnen hat, mit einem vollständigen Monat vergleichen, teilt Ihnen Coworker mit, dass der Vergleich auf partiellen Daten basiert.

## Aktuelle Einschränkungen

Das produktinterne Erlebnis für Mitarbeiter hat die folgenden Einschränkungen:

* **Segmentdefinitionen**: Wenn Sie nach Namen auf ein Segment verweisen, kennt der -Mitarbeiter die Definition des Segments nicht. Ein Mitarbeiter kann anhand seines Namens ableiten, was das Segment enthält. Überprüfen Sie die Segmentdefinition, bevor Sie sich auf die Ergebnisse verlassen.

* **Datenwörterbuch**: Der Kollege ist nicht mit dem [Datenwörterbuch](/help/components/data-dictionary/data-dictionary-overview.md) verbunden. Er kann nicht die Definitionen im Datenwörterbuch verwenden, um Metriken und Dimensionen zu erklären.

* **Genehmigte Komponenten**: Der -Kollege gibt genehmigten Komponenten keine Priorität vor ähnlichen Komponenten.

* **Bedienfelder kopieren**: Ein Mitarbeiter kann ein Bedienfeld nicht kopieren oder duplizieren.

* **Neue Segmente in der Komponentenliste**: Segmente, die Coworker erstellt, werden erst in der Komponentenliste in der linken Leiste angezeigt, wenn Sie die Seite aktualisieren. Datumsbereiche, die von Coworker erstellt werden, werden ohne Aktualisierung angezeigt.

* **Anomalieerkennung**: Wenn Sie einen Kollegen bitten, Anomalien in einer Visualisierung anzuzeigen, werden die Anomalien möglicherweise nicht angezeigt.

* **Konversationsverlauf**: Konversationen werden für jeden Benutzer und nicht mit dem Projekt gespeichert. Andere Benutzer, die das Projekt öffnen, können Ihre Unterhaltung mit einem Kollegen nicht sehen. Um den Kontext für andere Benutzer freizugeben, fügen Sie ihn den Beschreibungen der Bedienfelder im Projekt hinzu.

* **Mehrere Browser-Registerkarten**: Wenn Sie dieselbe Konversation in mehr als einer Browser-Registerkarte öffnen, verliert der Mitarbeiter möglicherweise den Überblick darüber, woran er arbeitet.

* **Sprachen außer Englisch**: In Datenansichten, in denen eine andere Sprache als Englisch verwendet wird, verwendet ein Mitarbeiter in seinen Antworten möglicherweise eine Mischung aus Englisch und der Sprache der Datenansicht.


