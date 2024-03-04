---
title: Erstellen oder Bearbeiten einer Verbindung
description: Beschreibt, wie in Customer Journey Analytics eine Verbindung zu einem Experience Platform-Datensatz erstellt oder bearbeitet wird.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 2be283e0abd32229be1921b106d166f47fb410a8
workflow-type: tm+mt
source-wordcount: '2763'
ht-degree: 98%

---

# Erstellen oder Bearbeiten einer Verbindung

Beim Workflow für die Erstellung und Bearbeitung von Verbindungen können alle Einstellungen zur Datensatz- und Verbindungskonfiguration mit einem unterstützenden Workflow zentral auf dem Bildschirm durchgeführt werden. Sie haben Möglichkeiten zur präzisen Auswahl, Konfiguration und Prüfung von Datensätzen mit wichtigen Informationen wie Datensatztyp, Größe, Schema, Datensatz-ID, Batch-Status, Aufstockungsstatus, Personen-IDs und vieles mehr, um das Risiko einer falschen Verbindungskonfiguration zu verringern. Im Folgenden finden Sie einen Überblick über die Funktionen:

* Sie können bei der Erstellung der Verbindung ein rollierendes Fenster zur Datenaufbewahrung aktivieren.
* Sie können Datensätze zu einer Verbindung hinzufügen und daraus entfernen. (Wenn Sie einen Datensatz entfernen, wird er aus der Verbindung entfernt und wirkt sich auf alle zugehörigen Datenansichten und zugrunde liegenden Analysis Workspace-Projekte aus.)
* Sie können für einzelne Datensätze Aufstockungsdaten aktivieren und anfordern.
* Sie können Datensätze bearbeiten, z. B. um eine weitere Aufstockung anzufordern.
* Sie können für einzelne Datensätze vorhandene Daten importieren.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Voraussetzungen

Sie müssen über die **Auswählen** -Paket, um einer Verbindung eine unbegrenzte Anzahl von Ereignis-Datensätzen hinzuzufügen. Die **Stiftung** -Paket ist auf einen Ereignis-Datensatz beschränkt. Sie können einer Verbindung eine unbegrenzte Anzahl von Profil- oder Lookup-Datensätzen hinzufügen. Wenden Sie sich an Ihr Admin-Team, wenn Sie sich nicht sicher sind, welches Customer Journey Analytics-Paket Sie besitzen.

## Erstellen und Konfigurieren der Verbindung {#create-connection}

1. Klicken Sie in Customer Journey Analytics auf die Registerkarte **[!UICONTROL Verbindungen]**.
1. Klicken Sie auf **[!UICONTROL Neue Verbindung erstellen]**.

   ![Unbenannte Verbindungseinstellungen](assets/create-conn1.png)

1. Konfigurieren Sie die Verbindungseinstellungen.

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Name der Verbindung]** | Geben Sie einen eindeutigen Namen für die Verbindung ein. |
   | **[!UICONTROL Beschreibung der Verbindung]** | Beschreiben Sie den Zweck dieser Verbindung. |
   | **[!UICONTROL Sandbox]** | Wählen Sie eine Sandbox in Experience Platform aus, die die Datensätze enthält, zu denen Sie eine Verbindung herstellen möchten.<p>Adobe Experience Platform bietet [Sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de) bereit, die eine einzelne Platform-Instanz in separate virtuelle Umgebungen aufteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu erleichtern. Sie können sich Sandboxes als „Datensilos“ vorstellen. Sandboxes dienen der Steuerung des Zugriffs auf Datensätze.<p>Nachdem Sie die Sandbox ausgewählt haben, werden in der linken Leiste alle Datensätze in der Sandbox angezeigt, aus denen Sie Daten abrufen können. |
   | **[!UICONTROL Rollierendes Datenfenster aktivieren]** | Wenn diese Option aktiviert ist, können Sie auf Verbindungsebene die Customer Journey Analytics-Datenspeicherung als rollierendes Fenster in Monaten (z. B. 1 Monat, 3 Monate und 6 Monate) definieren.<p>Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung jedoch Profil- oder Suchdatensätze enthält (neben einem oder mehreren Ereignisdatensätzen), werden diese Daten über denselben Zeitraum gespeichert.<p> Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.<p>Wenn Sie die Standardeinstellung unverändert (d. h. deaktiviert) lassen, wird die Aufbewahrungsdauer durch die Datenspeicherungseinstellung von Adobe Experience Platform ersetzt. Wenn also in Experience Platform Daten von einem Zeitraum von 25 Monaten enthalten sind, erhält Customer Journey Analytics durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in Customer Journey Analytics die verbleibenden 15 Monate beibehalten. |
   | **[!UICONTROL Hinzufügen von Datensätzen]** (siehe unten) | Fügen Sie Datensätze hinzu, wenn in Ihrer Datensatzliste keine Datensätze erscheinen. |
   | **[!UICONTROL Datensatzname]** | Wählen Sie einen oder mehrere Datensätze aus, die Sie nach Customer Journey Analytics übertragen möchten, und klicken Sie auf **[!UICONTROL Hinzufügen]**.<p>(Wenn Sie viele Datensätze zur Auswahl haben, können Sie mithilfe der Suchleiste „Datensätze suchen“ über der Liste der Datensätze nach den richtigen suchen.) |
   | **[!UICONTROL Zuletzt aktualisiert]** | Nur für Ereignis-Datensätze wird diese Einstellung automatisch auf das Standard-Zeitstempelfeld von Ereignis-basierten Schemas in Experience Platform gesetzt. „K. A.“ bedeutet, dass dieser Datensatz keine Daten enthält. |
   | **[!UICONTROL Schema]** | Das [Schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=de), auf dessen Grundlage der Datensatz in Adobe Experience Platform erstellt wurde. |
   | **[!UICONTROL Typ des Datensatzes]** | Customer Journey Analytics legt für jeden Datensatz, den Sie dieser Verbindung hinzugefügt haben, automatisch den Datensatztyp anhand der eingehenden Daten fest. Es gibt 3 verschiedene Datensatztypen: Ereignis-, Profil- und Such-Daten. Eine Erläuterung der Datensatztypen finden Sie in der unten stehenden Tabelle. |
   | **[!UICONTROL Personen-ID]** | Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>WICHTIG: Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. In [diesem Videos](https://www.youtube.com/watch?v=G_ttmGl_LRU) sehen Sie, wie Sie eine Identität in Experience Platform definieren. |
   | **[!UICONTROL Schlüssel]** | Nur für Lookup-Datensätze (z. B. _id). |
   | **[!UICONTROL Übereinstimmender Schlüssel]** | Nur für Lookup-Datensätze (z. B. _id). |
   | **[!UICONTROL Neue Daten importieren]** | Auf „Ein“ oder „Aus“ einstellen. |
   | **[!UICONTROL Aufstockungsdaten]** | Sie können die Aufstockung der Daten in einem Datensatz basierend auf Ereignis-Zeitstempeln anfordern. So können Sie beispielsweise eine Aufstockung der Daten der letzten sieben Tage anfordern, die richtige Personen-ID konfigurieren und Ihre Verbindung auf die korrekte Konfiguration testen. Wenn alle Einstellungen korrekt sind, können Sie alle verbleibenden Daten mühelos aufstocken.<p>Darüber hinaus können Sie den Import neuer Daten nach Datensatz aktivieren. Beispielsweise können Sie den Import neuer Daten ausschließlich für die Suche aktivieren. |
   | **[!UICONTROL Aufstockungsstatus]** | Gibt an, ob Aufstockungsdaten verarbeitet werden. |

   {style="table-layout:auto"}

## Hinzufügen und Konfigurieren von Datensätzen {#add-dataset}

Mit dem neuen Workflow können Sie beim Erstellen einer Verbindung einen Experience Platform-Datensatz hinzufügen.

1. Wählen Sie im Dialogfeld „Verbindungseinstellungen“ die Option **[!UICONTROL Datensätze hinzufügen]** aus.

2. Wählen Sie im Schritt [!UICONTROL Datensätze auswählen] einen oder mehrere Datensätze aus und klicken Sie auf **[!UICONTROL Weiter]**. Mindestens ein Ereignisdatensatz muss Teil der Verbindung sein.
   * Um die für die Liste der Datensätze angezeigten Spalten zu ändern, wählen Sie ![Spalteneinstellungen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) aus und wählen Sie die Spalten aus, die im Dialogfeld [!UICONTROL Tabelle anpassen] angezeigt werden sollen.
   * Um nach einem bestimmten Datensatz zu suchen, verwenden Sie das ![Suchfeld](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Um die ausgewählten Datensätze ein- oder auszublenden, wählen Sie ![Auswählen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg), **[!UICONTROL Ausgewählte ausblenden]** oder **[!UICONTROL Ausgewählte anzeigen]** aus.
   * Um einen Datensatz aus der Liste der ausgewählten Datensätze zu entfernen, verwenden Sie ![Schließen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Um alle ausgewählten Datensätze zu entfernen, wählen Sie **[!UICONTROL Alle löschen]**.

   ![Auswählen von Datensätzen](assets/select-datasets.png)

3. Konfigurieren Sie nun die Datensätze einzeln.

   ![Konfigurieren von Datensätzen](assets/add-dataset.png)

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Personen-ID]** | Nur für Ereignis- und Profildatensätze verfügbar. Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten aus. Diese Identitäten wurden im Datensatzschema in Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie weiter unten.<p>Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. In diesem Videos sehen Sie, wie Sie eine Identität in Experience Platform definieren. |
   | **[!UICONTROL Zeitstempel]** | Nur für Ereignis-Datensätze wird diese Einstellung automatisch auf das Standard-Zeitstempelfeld von Ereignis-basierten Schemas in Experience Platform gesetzt. |
   | **[!UICONTROL Schlüssel]** | Nur für Lookup-Datensätze verfügbar. Der für einen Lookup-Datensatz zu verwendende Schlüssel. |
   | **[!UICONTROL Passender Schlüssel]** | Nur für Lookup-Datensätze verfügbar. Der passende Schlüssel, der in einem der Ereignisdatensätze hinzugefügt werden soll. Wenn diese Liste leer ist, haben Sie wahrscheinlich keinen Ereignisdatensatz hinzugefügt oder konfiguriert. |
   | **[!UICONTROL Datenquellentyp]** | Wählen Sie einen Datenquellentyp aus. <br/>Hierzu gehören: <ul><li>[!UICONTROL Web-Daten]</li><li>[!UICONTROL App-Daten]</li><li>[!UICONTROL PoS-Daten]</li><li>[!UICONTROL CRM-Daten]</li><li>[!UICONTROL Umfragedaten]</li><li>[!UICONTROL Callcenter-Daten]</li><li>[!UICONTROL Produktdaten]</li><li> [!UICONTROL Kontodaten]</li><li> [!UICONTROL Transaktionsdaten]</li><li>[!UICONTROL Kunden-Feedback-Daten]</li><li> [!UICONTROL Sonstige]</li></ul>Dieses Feld wird verwendet, um sich einen Überblick über die verwendeten Datenquellen zu verschaffen. |
   | **[!UICONTROL Neue Daten importieren]** | Wählen Sie diese Option aus, wenn Sie eine fortlaufende Verbindung herstellen möchten. Damit fließen alle neuen Daten-Batches, die zu den Datensätzen in dieser Verbindung hinzugefügt werden, automatisch in Workspace ein. Kann auf [!UICONTROL Ein] oder [!UICONTROL Aus] eingestellt werden. |
   | **[!UICONTROL Aufstockung des Datensatzes]** | Wählen Sie **[!UICONTROL Aufstockung anfordern]** aus, um eine Aufstockung mit historischen Daten durchzuführen.<ul><li>Sie können jeden Datensatz einzeln aufstocken.</li><li>Neue Daten, die einem Datensatz in der Verbindung hinzugefügt werden, werden priorisiert, sodass diese neuen Daten die geringste Latenz aufweisen.</li><li>Alle (historischen) Aufstockungsdaten werden langsamer importiert. Die Latenz hängt von der vorhandenen Anzahl historischer Daten ab.</li><li>Der Analytics-Quell-Connector importiert Daten aus bis zu 13 Monaten (unabhängig von ihrer Größe) für Produktions-Sandboxes. Die Aufstockung in Nicht-Produktions-Sandboxes ist dagegen auf 3 Monate beschränkt.</li></ul> |
   | **[!UICONTROL Aufstockungsstatus]** | Mögliche Statusindikatoren sind:<ul><li>Erfolgreich</li><li>X Aufstockung(en) werden verarbeitet</li><li>Aus</li></ul> |
   | **[!UICONTROL Datensatz-ID]** | Diese ID wird automatisch generiert. |
   | **[!UICONTROL Beschreibung]** | Die Beschreibung, die diesem Datensatz bei seiner Erstellung gegeben wurde. |
   | **[!UICONTROL Datensatzgröße]** | Die Größe des Datensatzes. |
   | **[!UICONTROL Schema]** | Das Schema, auf dessen Grundlage der Datensatz in Adobe Experience Platform erstellt wurde. |
   | **[!UICONTROL Datensatz]** | Der Name des Datensatzes. |
   | **[!UICONTROL Vorschau: *Datensatzname *]** | Vorschau des Datensatzes mit Spalten für Datum, persönlicher ID und Kennung. |
   | **[!UICONTROL Entfernen]** | Sie können den Datensatz löschen oder entfernen und die Personen-ID ändern, ohne die gesamte Verbindung zu löschen. Durch Löschen oder Entfernen reduzieren sich die Kosten für die Datenaufnahme sowie der aufwändige Prozess der Neuerstellung der gesamten Verbindung und der zugehörigen Datenansichten. |

   {style="table-layout:auto"}

## Verbindungsvorschau {#preview}

Um die von Ihnen erstellte Verbindung in der Vorschau anzuzeigen, klicken Sie auf **[!UICONTROL Verbindungsvorschau]** im Dialogfeld „Verbindungseinstellungen“.

![Verbindungsvorschau](assets/create-conn4.png)

Diese Vorschau enthält einige Spalten zur Verbindungskonfiguration. Welche Spaltentypen angezeigt werden, hängt von Ihren individuellen Datensätzen ab.

## Datensatztypen {#dataset-types}

[!UICONTROL Customer Journey Analytics] legt für jeden Datensatz, den Sie dieser Verbindung hinzufügen, automatisch den Datensatztyp anhand der eingehenden Daten fest.

>[!IMPORTANT]
>
>Sie müssen mindestens einen Ereignisdatensatz als Teil einer Verbindung hinzufügen.

Es gibt drei verschiedene Datensatztypen: [!UICONTROL Ereignisdaten], [!UICONTROL Profildaten] und [!UICONTROL Suchdaten].

| Typ des Datensatzes | Beschreibung | Zeitstempel | Schema | Personen-ID |
|---|---|---|---|---|
| **[!UICONTROL Ereignis]** | Daten, die zeitliche Ereignis darstellen (z. B. Web-Besuche, Interaktionen, Transaktionen, PoS-Daten, Umfragedaten und Ad-Impression-Daten). Dies können beispielsweise typische Clickstream-Daten mit einer Kunden-ID oder einer Cookie-ID und einem Zeitstempel sein. Bei Ereignisdaten können Sie entscheiden, welche ID als Personen-ID verwendet wird. | Wird automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in [!UICONTROL Experience Platform] gesetzt. | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Zeitreihen“ basiert. Beispiele sind „XDM-Erlebnisereignis“ oder „XDM-Entscheidungsereignis“. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jedes in Experience Platform definierte Datensatzschema kann ein eigener Satz von einer oder mehreren Identitäten definiert und mit einem Identity-Namespace verknüpft werden. Jede dieser Identitäten kann als Personen-ID verwendet werden. Beispiele sind Cookie-ID, zugeordnete ID, Benutzer-ID und Trackingcode. |
| **[!UICONTROL Suche]** | Sie können nun Datensätze als Suchvorgänge von Feldern in allen Datensatztypen hinzufügen: Profil-, Such- und Ereignisdatensätze. (Letztere wurden immer unterstützt.) Diese zusätzliche Funktion erweitert die Fähigkeit von CJA, komplexe Datenmodelle, einschließlich B2B-CDP, zu unterstützen.  Diese Daten werden verwendet, um nach Werten oder Schlüsseln in Ihren Ereignis-, Profil- oder Suchdaten zu suchen. Sie können bis zu zwei Ebenen von Suchvorgängen hinzufügen. (Beachten Sie Folgendes: [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md) können nicht als übereinstimmende Schlüssel für Suchvorgänge in Verbindungen verwendet werden.) Beispielsweise können Sie Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten den Produktnamen zuordnen. Ein Beispiel hierfür ist der [Anwendungsfall B2B](/help/use-cases/b2b/b2b.md). | Nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Eintrag“ basiert, mit Ausnahme der Klasse „XDM-Individuelles Profil“. | Nicht angegeben |
| **[!UICONTROL Profil]** | Daten, die auf Personen, Benutzende oder Kundinnen bzw. Kunden in den [!UICONTROL Ereignisdaten] angewendet werden. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen. | Nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf der Klasse „XDM-Individuelles Profil“ basiert. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jeden in [!DNL Experience Platform] definierten Datensatz ist ein eigener Satz von einer oder mehreren definierten Personen-IDs definiert, z. B. Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw.<br>![Personen-ID ](assets/person-id.png)**Hinweis**: Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, wird dies in der Berichterstellung berücksichtigt. Um Datensätze wirklich zusammenzuführen, müssen Sie dieselbe Personen-ID verwenden. |

{style="table-layout:auto"}

## Verwenden von numerischen Feldern als Suchschlüssel und Nachschlagewerte {#numeric}

Diese Suchfunktion ist nützlich, wenn Sie ein numerisches Feld, z. B. Kosten oder Marge, zu einem zeichenfolgenbasierten Schlüsselfeld hinzufügen möchten. Numerische Werte können als Schlüssel oder als Werte in die Suche einbezogen werden. In Ihrem Lookup-Schema können numerische Werte mit z. B. Ihren Produktnamen, COGS, Kampagnen-Marketing-Kosten oder Margen verknüpft sein. Im Folgenden finden Sie ein Beispiel für ein Lookup-Schema in Adobe Experience Platform:

![Lookup-Schema](assets/schema.png)

Es wird jetzt unterstützt, dass diese Werte als Metriken oder Dimensionen in Customer Journey Analytics-Berichte eingefügt werden können. Wenn Sie Ihre Verbindung einrichten und Lookup-Datensätze abrufen, können Sie die Datensätze bearbeiten, um die [!UICONTROL Schlüssel] und [!UICONTROL Übereinstimmungsschlüssel] auszuwählen:

![Datensatz bearbeiten](assets/lookup-dataset.png)

Wenn Sie eine Datenansicht einrichten, die auf dieser Verbindung basiert, fügen Sie die numerischen Werte als Komponenten zur Datenansicht hinzu. Jedes Projekt, das auf dieser Datenansicht basiert, kann dann über diese numerischen Werte berichten.

## Identity Map als Personen-ID verwenden {#id-map}

In Customer Journey Analytics kann die Identity Map für ihre Personen-ID verwendet werden. Identity Map ist eine Zuordnungs-Datenstruktur, mit der Schlüssel-/Wert-Paare hochgeladen werden können. Die Schlüssel sind Identity-Namespaces und der Wert ist eine Struktur, die den Identitätswert enthält. Die Identity Map ist für jede hochgeladene Zeile/jedes hochgeladene Ereignis vorhanden und wird für jede Zeile entsprechend aufgefüllt.

Die Identity Map ist für jeden Datensatz verfügbar, der ein auf der [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de)-Klasse basierendes Schema verwendet. Wenn Sie einen solchen Datensatz für eine Customer Journey Analytics-Verbindung auswählen, können Sie entweder ein Feld als primäre ID oder die Identity Map auswählen:

![](assets/idmap1.png)

Wenn Sie Identity Map auswählen, erhalten Sie zwei zusätzliche Konfigurationsoptionen:

| Option | Beschreibung |
|---|---|
| **[!UICONTROL Primären ID-Namespace verwenden]** | Mit dieser Option wird Customer Journey Analytics angewiesen, zeilenweise nach der Identität in der Identity Map zu suchen, die mit dem Attribut „primary=true“ markiert ist, und diese als Personen-ID für die entsprechende Zeile zu verwenden. Diese Identität ist der Primärschlüssel, der in Experience Platform für die Partitionierung verwendet wird. Sie ist auch der Hauptkandidat für die Customer Journey Analytics-Personen-ID (je nachdem, wie der Datensatz in einer Customer Journey Analytics-Verbindung konfiguriert ist). |
| **[!UICONTROL Namespace]** | (Diese Option ist nur verfügbar, wenn Sie den primären Identity-Namespace nicht verwenden.) Identity-Namespaces sind eine Komponente des [Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=de) und dienen als Indikatoren für den Kontext, auf den sich eine Identität bezieht. Wenn Sie einen Namespace angeben, sucht Customer Journey Analytics in der Identity Map jeder Zeile nach diesem Namespace-Schlüssel und verwendet die Identität unter diesem Namespace als Personen-ID für die entsprechende Zeile. Da Customer Journey Analytics nicht alle Zeilen in einem Datensatz durchsuchen kann, um festzustellen, welche Namespaces vorhanden sind, werden alle möglichen Namespaces in der Dropdown-Liste angezeigt. Sie müssen wissen, welche Namespaces in den Daten angegeben sind. Diese Namespaces werden nicht automatisch erkannt. |

{style="table-layout:auto"}

### Identity Map-Randfälle {#id-map-edge}

In dieser Tabelle werden die beiden Konfigurationsoptionen angezeigt, wenn Randfälle vorhanden sind, und wie sie behandelt werden:

| Option | In der Identity Map sind keine IDs vorhanden | Mehrere IDs, keine als primär markiert | Es wurden mehrere IDs als primär markiert | Einzelne ID, als primär markiert oder nicht | Ungültiger Namespace mit einer als primär markierten ID |
|---|---|---|---|---|---|
| **[!UICONTROL Primären ID-Namespace verwenden] aktiviert** | Die Zeile wird von Customer Journey Analytics ignoriert. | Die Zeile wird von Customer Journey Analytics ignoriert, da keine primäre ID angegeben wurde. | Alle unter allen Namespaces als primär markierten IDs werden in eine Liste extrahiert. Sie werden dann alphabetisch sortiert. Bei dieser neuen Sortierung wird der erste Namespace mit seiner ersten ID als Personen-ID verwendet. | Die einzelne ID wird als Personen-ID verwendet. | Obwohl der Namespace möglicherweise ungültig ist (nicht in Adobe Experience Platform vorhanden), verwendet Customer Journey Analytics die primäre ID unter diesem Namespace als Personen-ID. |
| **[!UICONTROL Spezifischer Identity Map-Namespace] ausgewählt** | Die Zeile wird von Customer Journey Analytics ignoriert. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namespace werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. (Bei der Erstellung der Verbindung kann nur ein gültiger Namespace ausgewählt werden. Daher ist es nicht möglich, einen ungültigen Namespace/eine ungültige ID als Personen-ID zu verwenden.) |

{style="table-layout:auto"}

## Berechnen der durchschnittlichen Anzahl von täglichen Ereignissen {#average-number}

Diese Berechnung wird für jeden Datensatz in der Verbindung durchgeführt.

1. Wechseln Sie zu [Adobe Experience Platform-Abfrage-Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de) und erstellen Sie eine Abfrage.

   Die Abfrage würde wie folgt aussehen: 

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   In diesem Beispiel ist „analytics_demo_data“ der Name des Datensatzes.

2. Um alle in Adobe Experience Platform vorhandenen Datensätze anzuzeigen, führen Sie die Abfrage `Show Tables` durch.
