---
title: B2B-Personen-Konto-Zuordnung
description: Erfahren Sie, wie die Zuordnung von B2B-Personen zu Konten in Customer Journey Analytics Ereignisdatensätze mit Kontoinformationen anreichert und eine vollständige Journey-Analyse für Ihre B2B-Daten ermöglicht.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a971b268208ec49b5ccd84b11543263ff3a1abea
workflow-type: tm+mt
source-wordcount: 2100
ht-degree: 15%

---

# B2B-Person mit Kontenzuordnung

Die B2B-Personen-Konto-Zuordnung reichert Ihre Ereignisdatensätze mit Account-Identitäten an und ermöglicht eine vollständige Analyse auf der gesamten Kunden-Journey in Customer Journey Analytics. Wenn Ereignisse keine Konto-ID haben, die Customer Journey Analytics B2B edition für die Aufnahme benötigt, leitet die Personen-Konto-Zuordnung diese Informationen automatisch ab und fügt sie mithilfe eines von Ihnen bereitgestellten [Person-Konto-Zuordnung](#prerequisites)Datensatzes hinzu.

Ohne Personen-Konto-Zuordnung wird jedes Ereignis, das keine Konto-ID enthält, während der Aufnahme gelöscht. Die Personen-zu-Konto-Zuordnung löst diese Einschränkung, indem das mit der Person verknüpfte Konto bei jedem Ereignis nachgeschlagen und die Konto-ID sowohl bei der Aufnahme als auch rückwirkend hinzugefügt wird.

>[!NOTE]
>
>Für die B2B-Personen-Konto-Zuordnung müssen Sie in Ihrer Umgebung über die Berechtigung für die [Customer Journey Analytics](/help/getting-started/cja-b2b-edition.md)B2B edition verfügen, bevor Sie die Funktion konfigurieren können.

Die Zuordnung von Person zu Konto führt die folgenden Vorgänge für Ihre Datensätze aus:

* **Personenidentität erhöhen**: Ähnlich wie beim [B2C-Stitching-](/help/stitching/overview.md) konfigurieren Sie ein Feld, das persistente Personen-IDs enthält. Mithilfe des Identitätsdiagramms wird die persistente Personen-ID für jedes Ereignis aus dem konfigurierten Namespace der Personenkennung zu einer Personen-ID hochgestuft.
* **Fehlende Kontoidentitäten hinzufügen**: Nachdem Sie die Personen-ID-Informationen für ein Ereignis abgerufen haben, wird die [Personen-Konto-Zuordnung](#prerequisites) verwendet, um die Kontoidentitätsinformationen abzuleiten und hinzuzufügen. Jede Kontoidentität, die für das Ereignis selbst verfügbar ist, wird als Fallback-Methode verwendet.“

## Funktionsweise der B2B-Person-Konto-Zuordnung

Um zu veranschaulichen, wie die B2B-Kontozuordnung funktioniert, wird der unten dargestellte Datensatz als Ausgangspunkt verwendet.

### Basisereignis-Datensatz

In Customer Journey Analytics B2B edition werden Ereignisse ohne Konto-ID in diesem nicht zugeordneten Beispielereignisdatensatz ignoriert und nicht aufgenommen (![DeleteOutline](/help/assets/icons/DeleteOutline.svg)).

| Aktion | Zeitstempel | Dauerhafte ID | Konto-ID | Personen-ID | Ereignistyp |
|:---:|--:|--|---|---|---|
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 1/3/25 | 1234 | Adobe | matt@adobe.com | Page view |
| ![FilterDelete](/help/assets/icons/DeleteOutline.svg) | 1/3/25 | 5678 |  | | |
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 3/4/25 | 9012 | Allgegenwart | cory@sky.com |  |
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 3/7/25 | 4321 | Himmel | emily@sky.com | Callcenter |
| ![FilterDelete](/help/assets/icons/DeleteOutline.svg) | 5/5/25 | 6106 | | carmen@adobe.com |  |
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 6/1/25 | 8989 | Allgegenwart | cassidy@ubiquity.com | |
| ![FilterDelete](/help/assets/icons/DeleteOutline.svg) | 6/2/25 | 1111 |  | | |

Die Zuordnung von B2B-Personen zu Konten verhindert, dass Ereignisse ignoriert und nicht aufgenommen werden, indem die folgenden Vorgänge verwendet werden:

* [Personenidentitäten &#x200B;](#elevate-person-identities).
* [Fügen Sie fehlende Kontoidentitäten hinzu](#add-missing-account-identitiers).


### Personenidentitäten erhöhen

+++ Details

Um die Zuordnung von B2B-Personen zu Konten zu unterstützen, stellen Sie einen Datensatz für die Zuordnung von Personen zu Konten bereit. Beispiel:

| CRM-ID | Konto-ID |
|---|---|
| 12HSD123 | Adobe |
| F82JSD32 | Himmel |
| HG2023M2 | Himmel |
| B978BBW9 | Allgegenwart |
| FS453GHI | Adobe |

Dieser Datensatz für die Zuordnung von Person zu Konto wird durch diagrammbasiertes Stitching erhöht. Sie stellen beispielsweise E-Mail als zu verwendenden Namespace bereit. Das Ergebnis ist ein aktualisierter Datensatz für die Zuordnung von Personen zu Konten mit erhöhten Personen-IDs.

| CRM-ID | Erhöhte Personen-ID | Konto-ID |
|---|---|---|
| 12HSD123 | matt@adobe.com | Adobe |
| F82JSD32 | emily@sky.com | Himmel |
| HG2023M2 | cory@sky.com | Himmel |
| B978BBW9 | cassidy@ubiquity.com | Allgegenwart |
| FS453GHI | carmen@adobe.com | Adobe |

Die diagrammbasierte Zuordnung wird auch verwendet, um die Personen-IDs im Erlebnisereignis-Datensatz zu erhöhen. Siehe zum Beispiel den aktualisierten Wert für **emily@adobe.com**.

Die diagrammbasierte Zuordnung wird auch verwendet, um die Personen-IDs im Erlebnisereignis-Datensatz zu erhöhen. Sie konfigurieren beispielsweise das Feld „Persistent ID“ (ECID), das als persistente Personen-ID verwendet werden soll, wenn Sie [Stitching für den Datensatz aktivieren](#enable-b2b-stitching-on-event-datasets). Basierend auf `5678` als ECID-Wert und `emily@adobe.com` als E-Mail-Wert, wird `emily@adobe.com` für das zugehörige Ereignis als erhöhte Personen-ID festgelegt.

| Zeitstempel | Dauerhafte ID | Ursprüngliche Konto-ID | Ursprüngliche Personen-ID | Erhöhte Personen-ID |
|--|--|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | matt@adobe.com |
| 1/3/25 | 5678 |  | | **emily@adobe.com** |
| 3/4/25 | 9012 | Allgegenwart | cory@sky.com | cory@sky.com |
| 3/7/25 | 4321 | Himmel | emily@sky.com | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | carmen@adobe.com |
| 6/1/25 | 8989 | Allgegenwart | cassidy@ubiquity.com | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 111 | 111 |


+++

### Hinzufügen fehlender Kontokennungen

+++ Details

Der Personen-Konto-Datensatz wird erneut verwendet, um die Konto-IDs im Erlebnisereignis-Datensatz zu erhöhen. Siehe zum Beispiel den zusätzlichen Wert **Sky** für emily@sky.com und **Adobe** für carmen@adobe.com. Und der aktualisierte Wert **Sky** (von Ubiquity) für cory@sky.com.

| Zeitstempel | Dauerhafte ID | Ursprüngliche Konto-ID | Ursprüngliche Personen-ID | Erhöhte Konto-ID | Erhöhte Personen-ID |
|---|---|---|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | Adobe | matt@adobe.com |
| 1/3/25 | 5678 | | | **Sky** | **emily@sky.com** |
| 3/4/25 | 9012 | Allgegenwart | cory@sky.com | **Sky** | cory@sky.com |
| 3/7/25 | 4321 | Himmel | emily@sky.com | Himmel | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | **Adobe** | carmen@adobe.com |
| 6/1/25 | 8989 | Allgegenwart | cassidy@ubiquity.com | Allgegenwart | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 1111 |  | 1111 |

+++

### Ergebnis

Dieses Beispiel zeigt, wie die B2B-Kontozuordnung Ihre Erlebnisereignisdaten mit fehlenden Personenkennungen oder fehlenden und falschen Kontokennungen aktualisiert, basierend auf dem von Ihnen als Eingabe angegebenen Datensatz für die Zuordnung von Person zu Konto.


## Voraussetzungen

Bereiten Sie in Adobe Experience Platform die folgenden Datensätze vor, bevor Sie die B2B-Kontozuordnung aktivieren:

| Datensatz | Erforderlich | Beschreibung |
|---|---|---|
| **Person-Konto-Datensatz** | erforderlich | Ein Lookup-Datensatz (Datensatz, keine Zeitreihe), der mindestens eine Personen-ID (mit Namespace) und eine Konto-ID enthält. Diese IDs werden verwendet, um die Zuordnung von Person zu Konto abzuleiten. |

>[!IMPORTANT]
>
>Das Feld Personen-ID in Ihrem **[!UICONTROL Person-zu-Konto]**-Datensatz muss in Ihrem Schema als Identität markiert sein.

## Aktivieren der Person-zu-Konto-Zuordnung {#enable-account-stitching}

Sie aktivieren und konfigurieren das B2B-Stitching zunächst auf Verbindungsebene. Wenn die B2B-Zuordnung für eine Verbindung konfiguriert ist, können Sie die Personen-Account-Zuordnung für einzelne Ereignis-Datensätze innerhalb dieser Verbindung aktivieren.

### Konfigurieren der Einstellungen für die B2B-Person-Kontozuordnung {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="Konfigurieren der B2B-Kontozuordnung"
>abstract="Wählen Sie **[!UICONTROL B2B-Zuordnungskonfiguration öffnen]** aus, um die B2B-Kontozuordnung zu konfigurieren. Wenn die Verbindung noch nicht gespeichert wurde, wird die Konfiguration mit **[!UICONTROL _Nicht gespeicherte Änderungen_]** gekennzeichnet."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="Namespace der Personenkennung"
>abstract="Wählen Sie den relevantesten Personen-Identity-Namespace für Ihr Reporting aus. Zum Beispiel E-Mail. Für alle Ereignisdatensätze mit aktivierter Zuordnung **[!UICONTROL Person zu Konto]** ist die persistente Personen-ID in diesen Namespace der Personenkennung erhöht."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="Person zu Kontodatensatz"
>abstract="Wählen Sie den Lookup-Datensatz aus, der Personen-IDs Konto-IDs zuordnet."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="Personen-ID"
>abstract="Wählen Sie das Feld im Datensatz aus, das Personen-IDs enthält. Der Namespace dieses Feldes kann sich vom ausgewählten Namespace der Personenkennung unterscheiden oder mit diesem identisch sein. Wenn sie sich unterscheiden, müssen die beiden Namespaces im Identitätsdiagramm verknüpft werden."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="Konto-ID"
>abstract="Wählen Sie das Feld im Datensatz aus, das die eindeutigen Werte der Kontokennung enthält. Die Konto-ID-Informationen werden in den Zeilen aller Ereignis-Datensätze verfügbar gemacht, wobei die Zuordnung **[!UICONTROL Person zu Konto]** aktiviert ist."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="Startzeit"
>abstract="Wählen Sie ein Zeitstempelfeld aus, das angibt, wann die Person-Konto-Beziehung aktiv wurde."


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_mapping_creation_time"
>title="Erstellungszeit der Zuordnung"
>abstract="Wählen Sie optional das Feld aus, das das Datum und die Uhrzeit darstellt, zu der die Zuordnung von Person zu Konto erstellt wurde. Nützlich für Szenarien, in denen eine Person im Laufe der Zeit mehrere Konten wechselt."


1. Navigieren Sie in Customer Journey Analytics zu **[!UICONTROL Verbindungen]** und [erstellen Sie eine neue Verbindung](/help/connections/create-connection.md#create-a-connection).

1. Legen **[!UICONTROL in]** Verbindungseinstellungen“ die **[!UICONTROL Primäre ID]** auf ![Building](/help/assets/icons/Building.svg)**[!UICONTROL Account]** fest.

1. Wählen Sie unbedingt die **[!UICONTROL optionalen Container]** aus, die Sie in Ihrer B2B-Verbindung verwenden möchten. Sie können die Auswahl dieser Container nicht mehr ändern, nachdem Sie eine B2B-Person in der Konfiguration der Kontozuordnung gespeichert haben.

1. Wählen Sie **[!UICONTROL B2B-Stitching-Konfiguration öffnen]**.

   ![B2B-Kontozuordnungskonfiguration](../assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >Eine zuvor konfigurierte B2B-Person zur Kontozuordnungskonfiguration für eine nicht gespeicherte Verbindung wird mit &quot;**[!UICONTROL _Änderungen“_]**. Sie können **[!UICONTROL optionalen Container]** für eine zuvor konfigurierte B2B-Person nicht in die Konfiguration der Kontozuordnung ändern.

1. Im Dialogfeld **[!UICONTROL B2B-Stitching-Konfiguration]**:

   ![B2B-Person-Konto-Stitching-Konfiguration](../assets/b2b-stitching-configuration.png)

   1. Konfigurieren Sie den **[!UICONTROL Person]**-Abschnitt:

      * Wählen Sie den Identity-Namespace der relevantesten Person für Ihre Berichte aus, z. B. E-Mail. Für alle Ereignisdatensätze mit aktivierter Zuordnung von Person zu Konto ist die persistente Personen-ID in diesen Namespace der Personenkennung erhöht. Dieses Feld ist erforderlich.

   1. Konfigurieren Sie den **[!UICONTROL Konto]** unter **[!UICONTROL Person an Konto]**.

      | Feld | Erforderlich | Beschreibung |
      |---|:---:|---|
      | **[!UICONTROL Person-Konto-Datensatz]** | ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie die Suche (Datensatz oder Datensatz ohne Zeitreihe) aus, die Personen Konten zuordnet. |
      | **[!UICONTROL Personen-ID]** | ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie das Feld im Datensatz aus, das die Personen-ID enthält. Dieses Feld muss als Identität markiert werden und darf nicht mit dem Feld **[!UICONTROL Konto-ID]** oder dem Feld **[!UICONTROL Startzeit]** identisch sein. |
      | **[!UICONTROL Konto-ID]** | ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie das Feld im Datensatz aus, das die Konto-ID enthält. Dieses Feld darf nicht mit dem Feld **[!UICONTROL Personen-ID]** oder dem Feld **[!UICONTROL Startzeit]** identisch sein. |
      | **Erstellungszeit der Zuordnung** | | Wählen Sie optional das Feld aus, das das Datum und die Uhrzeit darstellt, zu der die Zuordnung von Person zu Konto erstellt wurde. Nützlich für Szenarien, in denen eine Person im Laufe der Zeit mehrere Konten wechselt.<br/><br/>**Beispiel** (wenn **update_date**-Feld ausgewählt ist):<table><thead><tr><th>update_date</th><th>Person</th><th>account</th></tr></thead><tbody><tr><td>20260401</td><td>a@b.com</td><td>Apple</td></tr><tr><td>20260501</td><td>a@b.com</td><td>Adobe</td></tr></tbody></table><ul><li>Für alle Ereignisse mit einem Zeitstempel im Feld **[!UICONTROL update_date]** vor dem 1. Mai 2026 wird a@b.com Apple zugeordnet.</li><li>Für alle Ereignisse mit einem Zeitstempel im Feld **[!UICONTROL update_date]** ab dem 1. Mai 2026 wird a@b.com Adobe zugeordnet.</li></ul>Wenn keine Zuordnungszeit angegeben wird, wird das lexikografische erste Konto verwendet. Derselbe Algorithmus wird auch verwendet, wenn zwei verschiedene Kontonamen exakt denselben **[!UICONTROL update_date]**-Wert haben und eine Erstellungszeit für die Zuordnung angegeben ist. |

      >[!NOTE]
      >
      >Wenn beim Laden der Feldoptionen ein Fehler auftritt, werden die Dropdown-Menüs leer angezeigt und unter jedem betroffenen Feld wird eine Fehleranzeige angezeigt. Überprüfen Sie Ihr Datensatzschema und versuchen Sie es erneut.

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um das Dialogfeld **[!UICONTROL B2B-Stitching-Konfiguration]** zu schließen und zu den Verbindungseinstellungen zurückzukehren.

   1. Die Anzeige **[!UICONTROL _Nicht gespeicherte Änderungen_]** wird neben der Schaltfläche **B2B-Stitching-Konfiguration öffnen** angezeigt, bis Sie die Verbindung [speichern](#save).

### B2B-Person für die Kontozuordnung in Ereignis-Datensätzen aktivieren


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="Aktivieren der Person-zu-Konto-Zuordnung"
>abstract="Wenn aktiviert, verwendet dieser Datensatz die B2B-Zuordnung von Person zu Konto. Die **[!UICONTROL Persistent Person ID]**-Werte werden auf die Werte aus dem konfigurierten **[!UICONTROL Personen-ID-Namespace]** erhöht und dann verwendet, um die Konto-ID basierend auf dem Personen-Konto-Datensatz zu suchen.<br/>Wenn deaktiviert, verwendet dieser Datensatz keine B2B-Person zur Kontozuordnung und Sie müssen stattdessen eine erforderliche **[!UICONTROL Konto-ID]** auswählen."
>additional-url="https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/b2b-account-stitching#configure-b2b-stitching-settings" text="Konfigurieren der Einstellungen für die B2B-Person-Kontozuordnung"

Nachdem Sie die B2B-Person für die Kontozuordnung auf der Verbindungsebene konfiguriert haben, müssen Sie die B2B-Person für die Kontozuordnung einzeln für jeden Ereignisdatensatz aktivieren, den Sie zuordnen möchten.

1. Wählen Sie in den Verbindungseinstellungen **[!UICONTROL Datensätze hinzufügen]** oder öffnen Sie die Einstellungen für einen vorhandenen Ereignisdatensatz.<br/>Siehe [Hinzufügen von &#x200B;](/help/connections/create-connection.md#add-datasets)) oder [Bearbeiten eines &#x200B;](/help/connections/create-connection.md#edit-a-dataset)).

1. Aktivieren Sie für den spezifischen Ereignisdatensatz, für den Sie die B2B-Kontozuordnung konfigurieren möchten **[!UICONTROL „Person zu Kontozuordnung aktivieren]**.

>[!BEGINTABS]

>[!TAB ein]

Wenn **[!UICONTROL Zuordnung von Person zu Konto aktivieren]** **aktiviert**, haben Sie die B2B-Kontozuordnung für den Datensatz konfiguriert.

* Die Konfiguration einer Personen-ID ist erforderlich. Diese Personen-ID wird verwendet, um die Konto-ID basierend auf dem [Person-zu-Konto-Datensatz](#prerequisites) nachzuschlagen.
* Die Konfiguration einer Konto-ID ist optional.

![B2B-Kontozuordnung im Ereignisdatensatz auf](../assets/b2b-event-dataset-stitching-on.png)

>[!TAB Aus]

Wenn **[!UICONTROL Zuordnung von Person zu Konto aktivieren]** **Aus** ist, *Sie die B2B-Kontozuordnung für* Datensatz konfiguriert.

* Die Konfiguration einer Konto-ID ist erforderlich.
* Die Konfiguration einer Personen-ID ist optional.

![B2B-Kontozuordnung im Ereignisdatensatz deaktiviert](../assets/b2b-event-dataset-stitching-off.png)

>[!ENDTABS]


### Speichern

Nachdem Sie die Konfiguration der B2B-Person für die Kontozuordnung konfiguriert und das Hinzufügen oder Bearbeiten von Datensätzen abgeschlossen haben, wählen Sie **[!UICONTROL Speichern]** aus, um die Verbindung zu speichern.

>[!IMPORTANT]
>
>Sobald eine Verbindung gespeichert wurde, wird die Konfiguration der B2B-Person-Konto-Zuordnung unveränderlich. Um Ihre Einstellungen nach dem Speichern anzuzeigen, wählen Sie **B2B-Stitching-Konfiguration öffnen**. Alle Felder befinden sich in einem schreibgeschützten Zustand. Wenn außerdem der Datensatz, der für die [Personen-Konto-Zuordnung](#prerequisites) in Experience Platform verwendet wird, gelöscht wird, wird die Zuordnungskonfiguration gelöscht und die Verbindung geht in einen ungültigen Status über, der mit einer Warnmeldung in der Benutzeroberfläche signalisiert wird.

## Zeitplan für die Datenaktualisierung

Die Kontozuordnung leitet die Identitätszuordnung täglich von Ihrem [Person-Konto-Datensatz](#prerequisites) ab und verwendet diese Informationen, um Datensätze zu aktualisieren, die für die kurz- und langfristige Zuordnung gemäß dem folgenden Zeitplan aktiviert sind:

| Wiederholung | Häufigkeit | Datenfenster |
|---|---|---|
| Kurzfristig | Wöchentlich | Letzte 7 Tage |
| Langfristig | Monatlich | Letzte 3 Monate (Prime-Paket)<br/>Letzte 6 Monate (Ultimate-Paket) |

## Datenschutz und Datenhygiene

Die Kontozuordnung berücksichtigt standardmäßige Datenschutz- und Hygieneanfragen für Personenidentitäten, im Einklang mit dem B2C-Zuordnungsverhalten. Wenn eine Personen-ID später über eine Datenschutz- oder Hygieneanfrage entfernt wird, wird die zugehörige Zuordnung, die mithilfe des Identitätsdiagramms durchgeführt wurde, umgekehrt.

B2B-Entitäten wie Konten, Konto-IDs und globale Konto-IDs, die durch Zuordnung zu Ereignissen hinzugefügt wurden, werden bei Datenschutz- oder Hygieneanfragen nicht entfernt. Diese Werte enthalten keine persönlich identifizierbaren Informationen, sodass keine gesetzliche Verpflichtung besteht, diese Werte zu entfernen.

>[!MORELIKETHIS]
>
>* [Stitching - Übersicht](../overview.md)
>* [Konfigurieren einer Verbindung für B2B](/help/connections/create-connection.md)
>* [Häufig gestellte Fragen zum Zusammenfügen](../faq.md)

