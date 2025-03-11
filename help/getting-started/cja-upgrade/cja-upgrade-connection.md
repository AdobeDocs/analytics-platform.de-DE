---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 22d3e7b8-4a4d-48a8-a98d-5172a9876286
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1629'
ht-degree: 94%

---

# Erstellen und Konfigurieren einer Verbindung für Customer Journey Analytics {#upgrade-create-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-connection"
>title="Erstellen einer Verbindung in Customer Journey Analytics"
>abstract="Mithilfe einer Verbindung können Sie Daten aus Adobe Experience Platform in ein für Customer Journey Analytics-Berichte optimiertes Format übersetzen. Die Erstellung einer Verbindung in Customer Journey Analytics ist unkompliziert und dauert nur wenige Minuten."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

In den folgenden Informationen wird erläutert, wie Sie eine Verbindung erstellen und konfigurieren und wie Sie der erstellten Verbindung Experience Platform-Datensätze hinzufügen. Weitere Informationen zum Erstellen und Konfigurieren einer Verbindung finden Sie unter [Erstellen oder Bearbeiten einer Verbindung](/help/connections/create-connection.md).

## Erstellen und Konfigurieren der Verbindung {#create-connection}

1. Rufen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Verbindungen]** auf.
1. Wählen Sie **[!UICONTROL Neue Verbindung erstellen]** aus.

   ![Unbenannte Verbindungseinstellungen](assets/create-conn1.png)

1. Konfigurieren Sie die Verbindungseinstellungen.

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Name der Verbindung]** | Geben Sie einen eindeutigen Namen für die Verbindung ein. |
   | **[!UICONTROL Beschreibung der Verbindung]** | Beschreiben Sie den Zweck dieser Verbindung. |
   | **[!UICONTROL Sandbox]** | Wählen Sie eine Sandbox in Experience Platform aus, die die Datensätze enthält, zu denen Sie eine Verbindung herstellen möchten.<p>Adobe Experience Platform bietet [Sandboxes](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home) bereit, die eine einzelne Platform-Instanz in separate virtuelle Umgebungen aufteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu erleichtern. Sie können sich Sandboxes als „Datensilos“ vorstellen. Sandboxes dienen der Steuerung des Zugriffs auf Datensätze.<p>Nachdem Sie die Sandbox ausgewählt haben, werden in der linken Leiste alle Datensätze in der Sandbox angezeigt, aus denen Sie Daten abrufen können. |
   | **[!UICONTROL Rollierendes Datenfenster aktivieren]** | Wenn diese Option aktiviert ist, können Sie auf Verbindungsebene die Customer Journey Analytics-Datenspeicherung als rollierendes Fenster in Monaten (z. B. 1 Monat, 3 Monate und 6 Monate) definieren.<p>Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung jedoch Profil- oder Suchdatensätze enthält (neben einem oder mehreren Ereignisdatensätzen), werden diese Daten über denselben Zeitraum gespeichert.<p> Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.<p>Wenn Sie die Standardeinstellung unverändert (d. h. deaktiviert) lassen, hat die Adobe Experience Platform-Einstellung zur Datenspeicherung Vorrang vor der Aufbewahrungsfrist. Wenn also in Experience Platform Daten von einem Zeitraum von 25 Monaten enthalten sind, erhält Customer Journey Analytics durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in Customer Journey Analytics die verbleibenden 15 Monate beibehalten. |
   | **[!UICONTROL Hinzufügen von Datensätzen]** (siehe unten) | Fügen Sie Datensätze hinzu, wenn in Ihrer Datensatzliste keine Datensätze erscheinen. |
   | **[!UICONTROL Datensatzname]** | Wählen Sie einen oder mehrere Datensätze für die Customer Journey Analytics-Übertragung und dann die Option **[!UICONTROL Hinzufügen]** aus.<p>(Wenn Sie viele Datensätze zur Auswahl haben, können Sie mithilfe der Suchleiste „Datensätze suchen“ über der Liste der Datensätze nach den richtigen suchen.) |
   | **[!UICONTROL Zuletzt aktualisiert]** | Nur für Ereignis-Datensätze wird diese Einstellung automatisch auf das Standard-Zeitstempelfeld von Ereignis-basierten Schemas in Experience Platform gesetzt. „K. A.“ bedeutet, dass dieser Datensatz keine Daten enthält. |
   | **[!UICONTROL Anzahl der Datensätze]** | Die Gesamtzahl der Einträge im Vormonat für den Datensatz in Experience Platform. |
   | **[!UICONTROL Schema]** | Das [Schema](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/schema/composition), auf dessen Grundlage der Datensatz in Adobe Experience Platform erstellt wurde. |
   | **[!UICONTROL Typ des Datensatzes]** | Customer Journey Analytics legt für jeden Datensatz, den Sie dieser Verbindung hinzugefügt haben, automatisch den Datensatztyp anhand der eingehenden Daten fest. Es gibt 3 verschiedene Datensatztypen: Ereignis-, Profil- und Such-Daten. Eine Erläuterung der Datensatztypen finden Sie in der unten stehenden Tabelle. |
   | **[!UICONTROL Granularität]** | Die Granularität der Daten im Datensatz; gilt nur für Zusammenfassungsdatensätze. |
   | **[!UICONTROL Datenquellentyp]** | Der Datenquellentyp des Datensatzes. Gilt nicht für Zusammenfassungsdatensätze. |
   | **[!UICONTROL Personen-ID]** | Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>WICHTIG: Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. In [diesem Videos](https://www.youtube.com/watch?v=G_ttmGl_LRU) sehen Sie, wie Sie eine Identität in Experience Platform definieren. |
   | **[!UICONTROL Schlüssel]** | Nur für Lookup-Datensätze (z. B. _id). |
   | **[!UICONTROL Übereinstimmender Schlüssel]** | Nur für Lookup-Datensätze (z. B. _id). |
   | **[!UICONTROL Neue Daten importieren]** | Auf „Ein“ oder „Aus“ einstellen. |
   | **[!UICONTROL Aufstockungsdaten]** | Sie können die Aufstockung der Daten in einem Datensatz anfordern. Zum Beispiel können Sie anfragen, die Daten der letzten sieben Tage aufzustocken. Konfigurieren Sie den Datensatz ordnungsgemäß und testen Sie Ihre Verbindung. Wenn alle Einstellungen korrekt sind, können Sie alle verbleibenden Daten mühelos aufstocken.<p>Darüber hinaus können Sie den Import neuer Daten nach Datensatz aktivieren. |
   | **[!UICONTROL Aufstockungsstatus]** | Dieser Status gibt an, ob Aufstockungsdaten verarbeitet werden. |

   {style="table-layout:auto"}

## Hinzufügen und Konfigurieren von Datensätzen {#add-dataset}

Sie können beim Erstellen einer Verbindung einen Experience Platform-Datensatz hinzufügen.

1. Wählen Sie im Dialogfeld „Verbindungseinstellungen“ die Option **[!UICONTROL Datensätze hinzufügen]** aus.

1. Im Schritt [!UICONTROL Auswählen von Datensätzen] wird eine Liste der Experience Platform-Datensätze angezeigt.

   ![Auswählen von Datensätzen](assets/select-datasets.png)

   Für jeden Datensatz zeigt die Liste Folgendes an:

   | Spalte | Beschreibung |
   |---|---|
   | Datensatz | Der Name des Datensatzes. Wählen Sie den Namen aus, um zum Datensatz in Experience Platform weitergeleitet zu werden. Wählen Sie ![Informationen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) aus, um ein Popup-Fenster mit weiteren Details zum Datensatz anzuzeigen. Sie können **[!UICONTROL In Platform bearbeiten]** auswählen, um den Datensatz direkt in Experience Platform zu bearbeiten. |
   | Typ des Datensatzes | Der Typ des Datensatzes: „Ereignis“, „Profil“, „Suche“ oder „Lookup“. |
   | Anzahl der Einträge | Die Gesamtzahl der Einträge im Vormonat für den Datensatz in Experience Platform. |
   | Schema | Das Schema für den Datensatz. Wählen Sie den Namen aus, um zum Schema in Experience Platform weitergeleitet zu werden. |
   | Letzter Batch | Der Status des letzten Batches, der in Experience Platform aufgenommen wurde. Weitere Informationen finden Sie unter [Batch-Status](https://experienceleague.adobe.com/de/docs/experience-platform/ingestion/batch/troubleshooting#batch-states). |
   | Datensatz-ID | Die ID des Datensatzes. |
   | Zuletzt aktualisiert | Der Zeitstempel für die letzte Aktualisierung des Datensatzes. |


1. Wählen Sie einen oder mehrere Datensätze und anschließend die Option **[!UICONTROL Weiter]** aus. Mindestens ein Ereignisdatensatz muss Teil der Verbindung sein.
   * Um die für die Liste der Datensätze angezeigten Spalten zu ändern, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus und wählen Sie die Spalten aus, die im Dialogfeld [!UICONTROL Tabelle anpassen] angezeigt werden sollen.
   * Um nach einem bestimmten Datensatz zu suchen, verwenden Sie das ![Suchfeld](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Um die ausgewählten Datensätze ein- oder auszublenden, wählen Sie ![Auswählen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg), **[!UICONTROL Ausgewählte ausblenden]** oder **[!UICONTROL Ausgewählte anzeigen]** aus.
   * Um einen Datensatz aus der Liste der ausgewählten Datensätze zu entfernen, verwenden Sie ![Schließen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Um alle ausgewählten Datensätze zu entfernen, wählen Sie **[!UICONTROL Alle löschen]**.




1. Konfigurieren Sie nun die Datensätze einzeln.

   ![Konfigurieren von Datensätzen](assets/add-dataset.png)

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Personen-ID]** | Nur für Ereignis- und Profildatensätze verfügbar. Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. Weitere Informationen finden Sie unter [Definieren von Identitätsfeldern in der Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/fields/identity). <p>Beim Wert für die ausgewählte Personen-ID wird zwischen Groß- und Kleinschreibung unterschieden. Beispielsweise sind `abc123` und `ABC123` zwei verschiedene Werte. |
   | **[!UICONTROL Zeitstempel]** | Nur für Ereignis- und Zusammenfassungsdatensätze wird diese Einstellung automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in Experience Platform gesetzt. |
   | **[!UICONTROL Schlüssel]** | Nur für Lookup-Datensätze verfügbar. Der für einen Lookup-Datensatz zu verwendende Schlüssel. |
   | **[!UICONTROL Passender Schlüssel]** | Nur für Lookup-Datensätze verfügbar. Der passende Schlüssel, der in einem der Ereignisdatensätze hinzugefügt werden soll. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen Ereignisdatensatz hinzugefügt oder konfiguriert. |
   | **[!UICONTROL Zeitzone]** | Nur für Zusammenfassungsdaten verfügbar. Wählen Sie die entsprechende Zeitzone für die Zeitreihen-Zusammenfassungsdaten aus. |
   | **[!UICONTROL Datenquellentyp]** | Wählen Sie einen Datenquellentyp aus. <br/>Hierzu gehören: <ul><li>[!UICONTROL Web-Daten]</li><li>[!UICONTROL App-Daten]</li><li>[!UICONTROL PoS-Daten]</li><li>[!UICONTROL CRM-Daten]</li><li>[!UICONTROL Umfragedaten]</li><li>[!UICONTROL Callcenter-Daten]</li><li>[!UICONTROL Produktdaten]</li><li> [!UICONTROL Kontodaten]</li><li> [!UICONTROL Transaktionsdaten]</li><li>[!UICONTROL Kunden-Feedback-Daten]</li><li> [!UICONTROL Sonstige]</li></ul>Dieses Feld wird verwendet, um sich einen Überblick über die verwendeten Datenquellen zu verschaffen. |
   | **[!UICONTROL Importieren neuer Daten]** | Aktivieren Sie diese Option, wenn eine fortlaufende Verbindung hergestellt werden soll. Mit einer fortlaufenden Verbindung sind neue Daten-Batches, die den Datensätzen hinzugefügt werden, automatisch in Workspace verfügbar. |
   | **[!UICONTROL Aufstockung des Datensatzes]** | Aktivieren Sie **[!UICONTROL Aufstockung aller vorhandenen Daten]**, um sicherzustellen, dass alle vorhandenen Daten aufgestockt werden.<br/><br/>Wählen Sie **[!UICONTROL Aufstockung anfordern]** aus, um eine Aufstockung mit historischen Daten für einen bestimmten Zeitraum durchzuführen. Sie können bis zu 10 Aufstockungszeiträume für Datensätze definieren.<ol><li>Definieren Sie den Zeitraum durch Eingabe von Start- und Enddaten oder Auswahl von Datumsangaben mithilfe des ![Kalenders](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Wählen Sie **[!UICONTROL Aufstockung in Warteschlange stellen]** aus, um die Aufstockung der Liste hinzuzufügen, oder **[!UICONTROL Abbrechen]**, um den Vorgang abzubrechen.</li></ol>Wählen Sie für jeden Eintrag ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) aus, um den Zeitraum zu bearbeiten, oder ![Löschen](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg), um den Eintrag zu löschen.<br/><br/>Bei Aufstockungen:<ul><li>Sie können jeden Datensatz einzeln aufstocken.</li><li>Neue Daten, die einem Datensatz in der Verbindung hinzugefügt werden, werden priorisiert, sodass diese neuen Daten die geringste Latenz aufweisen.</li><li>Alle (historischen) Aufstockungsdaten werden langsamer importiert. Die Menge historischer Daten beeinflusst die Latenz.</li><li>Der Analytics-Quell-Connector importiert Daten aus bis zu 13 Monaten (unabhängig von ihrer Größe) für Produktions-Sandboxes. Die Aufstockung in Nicht-Produktions-Sandboxes ist dagegen auf 3 Monate beschränkt.</li></ul> |
   | **[!UICONTROL Datensatz transformieren]** | Für bestimmte B2B-Lookup-Datensätze können Sie die Umwandlung eines Datensatzes für ordnungsgemäße B2B-Personenbasierte Reporting-Szenarien aktivieren. |
   | **[!UICONTROL Aufstockungsstatus]** | Mögliche Statusindikatoren sind:<ul><li>Erfolgreich</li><li>X Aufstockung(en) werden verarbeitet</li><li>Aus</li></ul> |
   | **[!UICONTROL Datensatz-ID]** | Diese ID wird automatisch generiert. |
   | **[!UICONTROL Beschreibung]** | Die Beschreibung, die diesem Datensatz bei seiner Erstellung gegeben wurde. |
   | **[!UICONTROL Datensatzgröße]** | Die Größe des Datensatzes. |
   | **[!UICONTROL Schema]** | Das Schema, auf dessen Grundlage der Datensatz in Adobe Experience Platform erstellt wurde. |
   | **[!UICONTROL Datensatz]** | Der Name des Datensatzes. |
   | **[!UICONTROL Vorschau: *Datensatzname *]** | Vorschau des Datensatzes mit Spalten für Datum, persönlicher ID und Kennung. |
   | **[!UICONTROL Entfernen]** | Sie können den Datensatz löschen oder entfernen und die Personen-ID ändern, ohne die gesamte Verbindung zu löschen. Durch Löschen oder Entfernen reduzieren sich die Kosten für die Datenaufnahme sowie der aufwändige Prozess der Neuerstellung der gesamten Verbindung und der zugehörigen Datenansichten. |

   {style="table-layout:auto"}

{{upgrade-final-step}}
