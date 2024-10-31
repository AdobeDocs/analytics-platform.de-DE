---
description: So stellen Sie Fragen zur Datenanalyse in der Customer Journey Analytics-Dokumentation
title: Assistent für Datenanalyse-KI im Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 1442aa9be5e6a6dc283ba559a2ff6c46de862425
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 3%

---


# Data Analysis AI Assistant in Customer Journey Analytics - Alpha

Der Data Analysis AI-Assistent ist ein intelligenter, kontextbezogener Konversationsagent, der Ihnen dabei hilft, Fragen zu Ihren Analysis Workspace-Daten in Customer Journey Analytics schneller und effizienter zu beantworten.

Der Assistent durchsucht alle Daten in einer Datenansicht, einschließlich der verschiedenen Metriktypen und Komponenten, und übersetzt Ihre Eingabeaufforderung in die richtige Dimension, Metrik und den richtigen Datumsbereich für diese Analyse. Anstatt sich mit den Datenansichtskomponenten vertraut zu machen und diese Komponenten zur Beantwortung Ihrer Frage per Drag-and-Drop in die beste Kombination zu ziehen, können Sie die Frage einfach in den AI-Assistenten eingeben.

## Funktionen für die Alpha-Version im Vergleich zum Umfang

In-Perimeter-Funktionen:

| Unterstützte Funktion | Beschreibung |
| --- | --- |
| Visualisierungen erstellen und aktualisieren | Erzeugt eine Freiformtabelle und die zugehörige Visualisierung (z. B. Linie, Balken, Ring usw.).<p>Beispiel: *Welchen Gewinn erzielen SKUs zwischen Februar und Mai?* |
| Unterstützte Visualisierungstypen | Visualisierungen für Linien-, Mehrzeilige-, Freiform-, Balken-, Donut-, Zusammenfassungsnummern |
| Out-of-Scope-Eingabeaufforderung | Wenn Sie eine Eingabeaufforderung senden, die nicht im Umfang vorhanden ist, z. B. &quot;dieses Projekt exportieren&quot;, antwortet der Assistent, indem er Ihnen mitteilt, dass die Frage außerhalb des Anwendungsbereichs liegt. |
| Klärung von Fragen | Wenn Sie eine Frage stellen, die nicht genügend Kontext für eine Antwort des KI-Assistenten bietet oder zu allgemein ist, antwortet der KI-Assistent mit einer Frage zur Klarstellung und/oder mit vorgeschlagenen Optionen. Beispiele: <p>**Komponenten**<ul><li>Metrik: *Welche &quot;Umsatz&quot;-Metrik haben Sie gemeint?*</li><li>Dimension: *Auf welche der folgenden &quot;Regionen&quot;möchten Sie sich konzentrieren?*</li><li>Filter: *Welchen &quot;Konto&quot;-Filter wollten Sie anwenden?*</li><li>Datumsbereich: *Mit &quot;Letzter Monat&quot;haben Sie den letzten vollen Monat oder die letzten 30 Tage gemeint?*</li></ul>**Dimension items**: Welchen &quot;Speichernamen&quot;haben Sie gemeint? (Beispiel: Store #5274, Store #2949 usw.) |
| Mehrfachumschaltung | Der AI-Assistent antwortet auf eine Eingabeaufforderung mit dem Kontext der vorherigen Aufforderung(en), sodass Benutzer Visualisierungen aktualisieren und Folgenachfragen stellen können. Beispiel: *Zeigen Sie mir stattdessen die Daten von März bis April.* |
| Feedback | <ul><li>Daumen nach oben</li><li>Nach unten</li><li>Markierung</li></ul> |

Out-of-Scope-Funktionen:

| Nicht unterstützte Funktion | Beschreibung |
| --- | --- |
| In-line-Zusammenfassung oder Antwort | Der KI-Assistent kann in der Chatleiste nicht mit einer zusammenfassenden Antwort auf eine Benutzeraufforderung linear antworten. Beispielhafte Eingabeaufforderungen außerhalb des Umfangs:<ul><li>*Geben Sie mir eine Zusammenfassung der Einblicke aus meiner letzten Eingabeaufforderung.*</li><li>*Fassen Sie die Highlights aus der Linienvisualisierung zusammen.*</li></ul> |
| Klärung von Fragen | Die Klärung von Fragen ist auf Komponenten und Dimensionselemente beschränkt. Der AI-Assistent kann keine Datenansichten, Visualisierungen, Datengranularität, Vergleich, Umfang usw. klären. Ohne Klarstellung von Fragen verwendet der Assistent standardmäßig das, was der Benutzer am ehesten verlangt. Wenn eine unerwartete Visualisierung oder Datengranularität zurückgegeben wird, kann der Benutzer dann die Funktion für Mehrfachwechsel/Aktualisierung verwenden, um die Visualisierung und die Daten anzupassen. |
| Workspace-Aktionen/-Funktionen | Der KI-Assistent kann für einen Benutzer in Workspace keine Aktionen durchführen, außer Visualisierungen zu erstellen und zu aktualisieren. Sie kann beispielsweise keine der folgenden Aktionen durchführen:<ul><li>Schaltflächen der Benutzeroberfläche für kontextbezogene Aktionen (zu Diagramm hinzufügen, neues Bedienfeld, neue Tabelle)</li><li>Freigeben</li><li>Exportieren</li><li>Download</li><li>Verwalten von Benutzereinstellungen</li><li>Kuratieren</li><li>Datenansicht verwalten</li><li>Analytics-Dashboards-App</li><li>Attribution</li></ul> |
| Nicht unterstützte Visualisierungstypen | <ul><li>Fluss</li><li>Fallout</li><li>Kohortentabelle</li><li>Bereich, Bereich gestapelt</li><li>Balken gestapelt</li><li>Horizontales Säulendiagramm</li><li>Kombination</li><li>Histogramm</li><li>Horizontalbalken, Horizontalbalken gestapelt</li><li>Zusammenfassung einer Schlüsselmetrik</li><li>Streuung</li><li>Zusammenfassende Änderung</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| Erläuterung und Überprüfung | Transparente Beschreibung oder Zitation, wie der KI-Assistent eine Antwort generiert hat, und eine Möglichkeit, die Richtigkeit der Antwort zu bestätigen. |

## Funktionszugriff in der Customer Journey Analytics-Benutzeroberfläche

[Brauchen wir diesen Abschnitt überhaupt für das Alpha?]

Die folgenden Parameter steuern den Zugriff auf die Funktion &quot;Data Analysis AI Assistant&quot;:

* **Lösungszugriff**: Der Data Analysis AI-Assistent steht Customer Journey Analytics Prime- und Ultimate-Kunden zur Verfügung. Es ist nicht in Adobe Analytics verfügbar.

Es ist auch in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP und zusätzlichen Experience Platform-Apps verfügbar.

* **Vertragszugriff**: Wenn Sie den KI-Assistenten nicht verwenden können, wenden Sie sich an den Administrator oder Adobe-Kundenbetreuer Ihres Unternehmens. Bevor Ihr Unternehmen Data Analysis AI Assistant verwenden kann, müssen Sie bestimmte GenAI-bezogene rechtliche Bedingungen akzeptieren.

* **Berechtigungen**: In der [!UICONTROL Adobe Admin Console] bestimmt die Berechtigung [!UICONTROL Berichterstellungs-Tools] **[!UICONTROL AI-Assistent: Datenanalyse]** den Zugriff auf dieses Tool. Ein [Produktprofiladministrator](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) muss die folgenden Schritte in der [!UICONTROL Admin Console] ausführen:
   1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Dienste]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]** .
   1. Wählen Sie den Titel des Produktprofils aus, für das Sie Zugriff auf [!UICONTROL AI Assistant: Product Knowledge] bereitstellen möchten.
   1. Wählen Sie im jeweiligen Produktprofil **[!UICONTROL Berechtigungen]** aus.
   1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um die **[!UICONTROL Berichterstellungs-Tools]** zu bearbeiten.
   1. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) aus, um **AI Assistant: Data Analysis** zu **[!UICONTROL Included permission items]** hinzuzufügen.

      ![Berechtigung hinzufügen](assets/ai-assistant-permissions.png).

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

Weitere Informationen finden Sie unter [Zugriffskontrolle](/help/technotes/access-control.md#access-control) .

## Access Data Analysis AI Assistant




## Data Analysis AI-Assistent verwenden

1. Navigieren Sie unter Customer Journey Analytics zur bereitgestellten Sandbox.

1. Öffnen Sie ein Workspace-Projekt.


## Beispieldatenanalyse - Eingabeaufforderungen

Im Folgenden finden Sie einige Beispiele dafür, wie der KI-Assistent auf Aufforderungen reagiert und die erwarteten Visualisierungen:



## Best Practices auffordern

TBD

## Erwartungen und Feedback zu Alpha-Tests

TB D

## Fragen und Kontakt

E-Mail `taylorb@adobe.com` (PM)
Fragen und Feedback im Alpha-Slack-Kanal senden




