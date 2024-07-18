---
title: Stitching
description: Erfahren Sie, wie Sie zugeordnete Datensätze erstellen und verwalten
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Erstellen und Verwalten von zugeordneten Datensätzen

{{select-package}}

Die Zuordnung ermöglicht es Administratoren, Identitäten in Datensätzen zu verknüpfen, die in Customer Journey Analytics verfügbar sind. Die Zuordnung von Datensätzen erhöht die Genauigkeit der Darstellung eines Profils, was letztendlich zu einer besseren Analyse und Berichterstellung führt.

Mit dem Stitching-Prozess können Sie eine vorhandene **beständige ID** in einem Datensatz definieren. Ordnen Sie dann diese beständige Kennung für ein bestimmtes Wiederholungsfenster (täglich, wöchentlich) mit der genauesten für diesen Datensatz verfügbaren **vorübergehenden ID** (Person oder authentifizierte Kennung) zu. Beispiele für vorübergehende Identifikatoren sind E-Mail-, Telefonnummer-, CRM-ID- oder andere im Diagramm gespeicherte Identitäten. Weitere Informationen zum Stitching finden Sie unter [Übersicht](overview.md) .

## Erstellen

Um das Stitching zu starten, erstellen Sie einen oder mehrere zugeordnete Datensätze. So erstellen Sie einen zugeordneten Datensatz:

1. Wählen Sie in der oberen Leiste **[!UICONTROL ** Data Management **]** die Option **[!UICONTROL ** Stitching **]** aus.

2. Wählen Sie im Bildschirm [!UICONTROL Zugeordnete Datensätze] die Option **[!UICONTROL ** Zusammengeführten Datensatz erstellen **]**.

   Sie werden aufgefordert, einen Dialog zu führen, in dem Ihre Verantwortlichkeiten erläutert werden.

3. Wählen Sie **[!UICONTROL ** Weiter **]** aus, wenn Sie diese Verantwortung übernehmen.

   >[!NOTE]
   >
   >    Wenn Sie **[!UICONTROL ** Abbrechen **]** auswählen, können Sie keinen zugewiesenen Datensatz erstellen.

4. Im Bildschirm [!UICONTROL Zugeordnete Datensätze > Nicht benannter zugeordneter Datensatz] :

   1. Definieren Sie einen **[!UICONTROL ** Datensatznamen **]** und (optional) **[!UICONTROL ** Beschreibung **]**,

   2. Wählen Sie die Sandbox aus der Liste **[!UICONTROL ** Sandbox **]** aus, in der der Ereignis-Datensatz gespeichert ist.

      ![Erstellungsbildschirm beim ersten Versuch](./assets/create-initial.png)

   3. Wählen Sie die Schaltfläche **[!UICONTROL ** Quelldatensatz auswählen **]** aus.

      Wählen Sie im Popup-Fenster [!UICONTROL Einen Datensatz zum Zuordnen von ] aus:

      ![Einen Datensatz auswählen](./assets/select-one-dataset.png)

      - Wählen Sie einen Datensatz aus und wählen Sie **[!UICONTROL ** Auswählen **]** , um fortzufahren.

   4. Wählen Sie eine beständige Kennung aus der Liste **[!UICONTROL ** Beständige ID **]** aus.

   5. Wählen Sie eine vorübergehende Kennung aus der Liste **[!UICONTROL ** Verlaufs-ID **]** aus.

      Beachten Sie, dass ein Vorschaufenster erscheint, um die Sättigungsraten (wie oft es einen Wert für jeden angegebenen Bezeichner über die Anzahl der Ereignisse gibt) für die letzten sieben Tage zu berechnen. Nach Abschluss der Berechnung visualisiert das Bedienfeld mit Farben, ob die Mindestbedingungen für das Stitching erfüllt sind (grün) oder nicht (rot).

      ![Erstellen Sie einen zugewiesenen Datensatz mit Staturraten](./assets/create-before-experimenting.png)

      Die Mindestbedingungen sind:

      - dauerhafte Sättigung der Kennungen: Rate >= 95 %

      - Sättigung der vorübergehenden Kennung: Rate >= 5 %

        Wenn die Mindestbedingungen erfüllt sind, können Sie mit Beispielwerten experimentieren.

      - Wählen Sie &quot;**[!UICONTROL ** Erstellen von demo-zugeordneten IDs **]**&quot;.

        Im Dialogfeld [!UICONTROL Experiment mit Beispielwerten] wird eine Tabelle mit Beispielwerten für [!UICONTROL timestamp], [!UICONTROL persistent ID], [!UICONTROL Übergangskennung], [!UICONTROL Zugeordnete ID (Live)], [!UICONTROL Zugeordnete ID (1-Tage-Wiederholung)] und [!UICONTROL zugeordnete ID angezeigt (7-Tage-Wiederholung)].

            ![Experimentieren mit Beispielwerten](./assets/experiment-sample-values.png)
            
            1.  Geben Sie einen Wert für **[!UICONTROL **Persistente ID**]** ein.
            
            2.  Wählen Sie **[!UICONTROL **Zugeordnete IDs aktualisieren**]**, um die Auswirkungen des Zuordnungsprozesses auf die Daten im Datensatz anzuzeigen.
            
            3.  Wählen Sie **[!UICONTROL **Close**]**, wenn Sie mit dem Experimentieren mit Beispielwerten fertig sind.
        

        Zurück im Bildschirm [!UICONTROL Zugeordnete Datensätze > _Datensatzname_] :

   6. Wählen Sie eine Option für die Häufigkeit und den Zeitraum der Wiederherstellung historischer Daten aus der Liste **[!UICONTROL ** Fenster erneut wiedergeben **]** aus.

      Sie können zwischen dem Standardwert **[!UICONTROL ** Vorheriger Tag, Tag **]** oder **[!UICONTROL ** Vorherige 7 Tage, Wöchentlich **]** wählen.

   7. Wählen Sie einen Wert aus der Liste **[!UICONTROL ** Durchschnittliche Anzahl der täglichen Ereignisse **]** aus.

   8. Geben Sie einen Wert (zwischen `0` und `12`) in **[!UICONTROL ** Anzahl der Monate ein, die aufgestockt werden sollen **]**.

   9. Wählen Sie **[!UICONTROL ** Speichern **]** aus, um den zugewiesenen Datensatz zu speichern und die Zuordnung zu starten.

## Status anzeigen

Sie können den Status der Zuordnung in der Liste [!UICONTROL Zugeordnete Datensätze] anzeigen.

- Wählen Sie in der oberen Leiste **[!UICONTROL ** Data Management **]** die Option **[!UICONTROL ** Stitching **]** aus.

  Es wird eine Liste mit zugewiesenen Datensätzen angezeigt, die jeweils mit [!UICONTROL Sandbox], [!UICONTROL Source-Datensatz], [!UICONTROL Status], [!UICONTROL Aufstockungsstatus], [!UICONTROL Inhaber] und [!UICONTROL Erstellungsdatum] identifiziert werden.

  ![Überblick über zugeordnete Datensätze](./assets/overview-stitched-datasetts.png)

  Mögliche Werte für [!UICONTROL Status] sind:

  | Wert | Erklärung |
  |-----|-----|
  | **[!UICONTROL ** In Warteschlange **]** | Die Anfrage wird empfangen und bald verarbeitet. |
  | **[!UICONTROL ** Erstellung **]** in Bearbeitung | Ressourcen und neu zugeordnete Datensätze werden derzeit erstellt. |
  | **[!UICONTROL ** Laufende Stitching **]** | Ressourcen und zugeordneter Datensatz sind vorhanden und die Zuordnung wird durchgeführt |
  | **[!UICONTROL ** Fehler **]** | Beim Stitching tritt ein Problem auf. Vielleicht hat sich ein Schema zwischen Quelldatensatz und zugeordnetem Datensatz geändert, das tägliche Volumen ist zu groß oder ... (_**benötigen hier weitere Informationen...**_) |

  >[!INFO]
  >
  >    Wenn sich ein Status ändert, wird eine Benachrichtigung mit der Meldung **[!UICONTROL ** Zugeordneter Datensatz _Name des Datensatzes_ gesendet, die in den Status _Name des Status _**]**geändert wurde.


  Der [!UICONTROL Aufstockungsstatus] kann die folgenden Werte aufweisen: 0 %, 25 %, 50 %, 75 % oder 100 %.

  Sie können auf das Informationssymbol klicken, um ein Popup mit weiteren Details zum ausgewählten zugeordneten Datensatz anzuzeigen.


## Löschen

>[!NOTE]
>
>Sie können nur Datensätze löschen, die den Status [!UICONTROL Laufende Zuordnung], [!UICONTROL Fehler] oder [!UICONTROL In Warteschlange] aufweisen.


So löschen Sie einen einzelnen zugeordneten Datensatz:

- Wählen Sie **[!UICONTROL **...**]** für den zugeordneten Datensatz und dann **[!UICONTROL ** Löschen **]** aus dem Menü aus.

  ![Einen zugeordneten Datensatz löschen](./assets/delete-stitched-dataset.png)

So löschen Sie mehrere zugeordnete Daten:

- Wählen Sie mehrere zugeordnete Datensätze mithilfe des Kontrollkästchens am Anfang jedes aufgelisteten Datensatzes aus.

- Wählen Sie **[!UICONTROL **...**]** aus einem der ausgewählten zugeordneten Datensätze und wählen Sie im Menü die Option **[!UICONTROL ** Löschen **]** aus.
