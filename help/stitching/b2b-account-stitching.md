---
title: B2B-Kontozuordnung
description: Erfahren Sie, wie die B2B-Kontozuordnung in Customer Journey Analytics Ereignisdatensätze mit Kontoinformationen anreichert und eine vollständige Journey-Analyse für Ihre B2B-Daten ermöglicht.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
source-git-commit: c444ee455da66fe6f4a95a362b21b50adc328a11
workflow-type: tm+mt
source-wordcount: 988
ht-degree: 2%

---

# B2B-Kontozuordnung

Die B2B-Kontozuordnung reichert Ihre Ereignisdatensätze mit Kontoinformationen an und ermöglicht eine vollständige Analyse auf der gesamten Kunden-Journey in Customer Journey Analytics. Wenn Ereignisse keine Konto-ID haben, die Customer Journey Analytics B2B edition für die Aufnahme benötigt, leitet die Kontozuordnung diese Informationen automatisch ab und fügt sie mithilfe eines von Ihnen bereitgestellten [Person-Konto-](#prerequisites)-Datensatzes hinzu.

Ohne Kontozuordnung wird jedes Ereignis, das keine Konto-ID enthält, während der Aufnahme gelöscht. Die Kontozuordnung beseitigt dieses Hindernis, indem das Konto, das mit der Person bei jedem Ereignis verknüpft ist, nachgeschlagen und die Konto-ID sowohl bei der Aufnahme als auch rückwirkend hinzugefügt wird.

>[!NOTE]
>
>Für die B2B-Kontozuordnung ist es erforderlich, dass die Funktion in Ihrer Umgebung verfügbar ist, bevor Sie die Funktion konfigurieren können.

Die Kontozuordnung führt die folgenden Vorgänge für Ihre Datensätze aus:

* **Identität der Person erhöhen**: Die Personen-ID für jedes Ereignis wird mithilfe des Identitätsdiagramms zu Ihrem gewünschten Identity-Namespace erhöht.
* **Fehlende Kontoinformationen hinzufügen**: Für Ereignisse, die eine Personen-ID enthalten, wird die [Zuordnung von Person zu Konto](#prerequisites) verwendet, um die Kontoinformationen abzuleiten und hinzuzufügen. Sämtliche Kontoinformationen über das Ereignis selbst werden als Fallback-Methode verwendet.

## Voraussetzungen

Bereiten Sie in Adobe Experience Platform die folgenden Datensätze vor, bevor Sie die B2B-Kontozuordnung aktivieren:

| Datensatz | Erforderlich | Beschreibung |
|---|---|---|
| **Person-Konto-Datensatz** | erforderlich | Ein Lookup-Datensatz (Datensatz, keine Zeitreihe), der mindestens eine Personen-ID (mit Namespace) und eine Konto-ID enthält. Diese IDs werden verwendet, um die Zuordnung von Person zu Konto abzuleiten. |

>[!IMPORTANT]
>
>Das Feld Personen-ID in Ihrem **[!UICONTROL Person-zu-Konto]**-Datensatz muss in Ihrem Schema als Identität markiert sein.

## Kontozuordnung aktivieren

Sie aktivieren und konfigurieren die B2B-Kontozuordnung auf Verbindungsebene und aktivieren dann die Kontozuordnung für einzelne Ereignisdatensätze innerhalb dieser Verbindung.

### B2B-Stitching-Einstellungen konfigurieren

1. Navigieren Sie in Customer Journey Analytics zu **[!UICONTROL Verbindungen]** und [eine neue Verbindung erstellen](/help/connections/create-connection.md#create-a-connection) oder [eine bestehende Verbindung bearbeiten](/help/connections/create-connection.md#edit-a-connection).

1. Legen **[!UICONTROL in]** Verbindungseinstellungen“ die **[!UICONTROL Primäre ID]** auf ![Building](/help/assets/icons/Building.svg)**[!UICONTROL Account]** fest.

1. Wählen Sie **[!UICONTROL B2B-Stitching-Konfiguration öffnen]**.

   ![B2B-Kontozuordnungskonfiguration](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >Eine zuvor konfigurierte B2B-Stitching-Konfiguration für eine nicht gespeicherte Verbindung wird mit &quot;**[!UICONTROL _Änderungen“_]**. Sie können **[!UICONTROL optionale Container]** für eine zuvor konfigurierte B2B-Stitching-Konfiguration nicht ändern.

1. Im Dialogfeld **[!UICONTROL B2B-Stitching-Konfiguration]**:

   ![B2B-Stitching-Konfiguration](assets/b2b-stitching-configuration.png)

   1. Konfigurieren Sie den **[!UICONTROL Person]**-Abschnitt:

      * Wählen Sie einen **[!UICONTROL Namespace für die Personenkennung]** aus, z. B **[!UICONTROL „E-Mail]**, auf den eine beliebige Personen-ID erhöht werden soll. Dieses Feld ist erforderlich.

   1. Konfigurieren Sie den **[!UICONTROL Konto]** unter **[!UICONTROL Person an Konto]**.

      | Feld | Erforderlich | Beschreibung |
      |---|:---:|---|
      | **[!UICONTROL Person-Konto-Datensatz]** | ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie die Suche (Datensatz oder Datensatz ohne Zeitreihe) aus, die Personen Konten zuordnet. |
      | **[!UICONTROL Personenfeld]** | ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie das Feld im Datensatz aus, das die Personen-ID enthält. Dieses Feld muss als Identität markiert werden und darf nicht mit dem Feld **[!UICONTROL Konto]** oder dem Feld **[!UICONTROL Startzeit]** identisch sein. |
      | **[!UICONTROL Kontofeld]** | ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie das Feld im Datensatz aus, das die Konto-ID enthält. Dieses Feld darf nicht mit dem Feld **[!UICONTROL Person]** oder dem Feld **[!UICONTROL Startzeit]** identisch sein. |
      | **Feld Startzeit** | | Wählen Sie ein Zeitstempelfeld aus, das angibt, wann die Person-Konto-Beziehung aktiv wurde. |

      >[!NOTE]
      >
      >Wenn beim Laden der Feldoptionen ein Fehler auftritt, werden die Dropdown-Menüs leer angezeigt und unter jedem betroffenen Feld wird eine Fehleranzeige angezeigt. Überprüfen Sie Ihr Datensatzschema und versuchen Sie es erneut.

   1. Wählen Sie **[!UICONTROL Speichern]** aus, um das Dialogfeld **[!UICONTROL B2B-Stitching-Konfiguration]** zu schließen und zu den Verbindungseinstellungen zurückzukehren.

   1. Die Anzeige **[!UICONTROL _Nicht gespeicherte Änderungen_]** wird neben der Schaltfläche **B2B-Stitching-Konfiguration öffnen** angezeigt, bis Sie die Verbindung [speichern](#save).


### B2B-Stitching für Ereignis-Datensätze aktivieren

Nachdem Sie die B2B-Zuordnung auf Verbindungsebene konfiguriert haben, müssen Sie die B2B-Kontozuordnung für jeden Ereignisdatensatz, den Sie zuordnen möchten, einzeln aktivieren.

1. Wählen Sie in den Verbindungseinstellungen **[!UICONTROL Datensätze hinzufügen]** oder öffnen Sie die Einstellungen für einen vorhandenen Ereignisdatensatz.<br/>Siehe [Hinzufügen von &#x200B;](/help/connections/create-connection.md#add-datasets)) oder [Bearbeiten eines &#x200B;](/help/connections/create-connection.md#edit-a-dataset)).

1. Aktivieren Sie für den spezifischen Ereignisdatensatz, für den Sie die B2B-Kontozuordnung konfigurieren möchten **[!UICONTROL „Person zu Kontozuordnung aktivieren]**.

>[!BEGINTABS]

>[!TAB ein]

Wenn **[!UICONTROL Zuordnung von Person zu Konto aktivieren]** **aktiviert**, haben Sie die B2B-Kontozuordnung für den Datensatz konfiguriert.

* Die Konfiguration einer Personen-ID ist erforderlich. Diese Personen-ID wird verwendet, um die Konto-ID basierend auf dem [Person-zu-Konto-Datensatz](#prerequisites) zu suchen.
* Die Konfiguration einer Konto-ID ist optional.

![B2B-Kontozuordnung im Ereignisdatensatz auf](assets/b2b-event-dataset-stitching-on.png)

>[!TAB Aus]

Wenn **[!UICONTROL Zuordnung von Person zu Konto aktivieren]** **Aus** ist, *Sie die B2B-Kontozuordnung für* Datensatz konfiguriert.

* Die Konfiguration einer Konto-ID ist erforderlich.
* Die Konfiguration einer Personen-ID ist optional.

![B2B-Kontozuordnung im Ereignisdatensatz deaktiviert](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### Speichern

Nachdem Sie die B2B-Stitching-Konfiguration konfiguriert und das Hinzufügen oder Bearbeiten von Datensätzen abgeschlossen haben, wählen Sie **[!UICONTROL Speichern]** aus, um die Verbindung zu speichern.

>[!IMPORTANT]
>
>Nachdem eine Verbindung gespeichert wurde, wird die B2B-Stitching-Konfiguration unveränderlich. Um Ihre Einstellungen nach dem Speichern anzuzeigen, wählen Sie **B2B-Stitching-Konfiguration öffnen**. Alle Felder werden schreibgeschützt angezeigt. Wenn der Datensatz, der für die Zuordnung [&#x200B; Person zu Konto verwendet wird](#prerequisites) in Experience Platform gelöscht wird, wird diese Verbindung ebenfalls gelöscht.

## Zeitplan für die Datenaktualisierung

Die Kontozuordnung leitet die Identitätszuordnung täglich von Ihrem [Person-Konto-Datensatz](#prerequisites) ab und verwendet diese Informationen, um Datensätze zu aktualisieren, die für die Zuordnung gemäß dem folgenden Zeitplan aktiviert sind:

| Wiederholung | Häufigkeit | Datenfenster |
|---|---|---|
| Kurzfristig | Wöchentlich | Letzte 7 Tage |
| Langfristig | Monatlich | Letzte 3 Monate |

## Datenschutz und Datenhygiene

Die Kontozuordnung berücksichtigt standardmäßige Datenschutz- und Hygieneanfragen für Personenidentitäten, im Einklang mit dem B2C-Zuordnungsverhalten. Wenn eine Personen-ID später über eine Datenschutz- oder Hygieneanfrage entfernt wird, wird die zugehörige Zuordnung, die mithilfe des Identitätsdiagramms durchgeführt wurde, umgekehrt.

B2B-Entitäten wie Konten, Konto-IDs und globale Konto-IDs, die durch Zuordnung zu Ereignissen hinzugefügt werden, werden nicht im Rahmen von Datenschutz- oder Hygieneanfragen entfernt. Diese Werte enthalten keine persönlich identifizierbaren Informationen, sodass keine gesetzliche Verpflichtung besteht, diese Werte zu entfernen.

>[!MORELIKETHIS]
>
>* [Stitching - Übersicht](overview.md)
>* [Konfigurieren einer Verbindung für B2B](../connections/create-connection.md)
>* [Häufig gestellte Fragen zum Zusammenfügen](faq.md)

