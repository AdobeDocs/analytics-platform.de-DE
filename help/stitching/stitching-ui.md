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
ht-degree: 0%

---

# Erstellen und Verwalten von zugeordneten Datensätzen

{{select-package}}

Die Zuordnung ermöglicht es Administratoren, Identitäten in Datensätzen zu verknüpfen, die in Customer Journey Analytics verfügbar sind. Die Zuordnung von Datensätzen erhöht die Genauigkeit der Darstellung eines Profils, was letztendlich zu einer besseren Analyse und Berichterstellung führt.

Mit dem Stitching-Prozess können Sie eine vorhandene **beständige ID** in einem Datensatz. Ordnen Sie dann diese beständige Kennung für ein bestimmtes Wiederholungsfenster (täglich, wöchentlich) mit der präzisesten **vorübergehende ID** (Person oder authentifizierte Kennung), die für diesen Datensatz verfügbar ist. Beispiele für vorübergehende Identifikatoren sind E-Mail-, Telefonnummer-, CRM-ID- oder andere im Diagramm gespeicherte Identitäten. Siehe [Übersicht](overview.md) für weitere Informationen zum Stitching.

## Erstellen

Um das Stitching zu starten, erstellen Sie einen oder mehrere zugeordnete Datensätze. So erstellen Sie einen zugeordneten Datensatz:

1. Auswählen **[!UICONTROL ** Stitching **]** von **[!UICONTROL ** Data Management **]** in der oberen Leiste.

2. Im [!UICONTROL Zugeordnete Datensätze] Bildschirm, auswählen **[!UICONTROL ** Erstellen eines zugeordneten Datensatzes **]**.

   Sie werden aufgefordert, einen Dialog zu führen, in dem Ihre Verantwortlichkeiten erläutert werden.

3. Auswählen **[!UICONTROL ** Weiter **]** wenn Sie diese Verantwortung übernehmen.

   >[!NOTE]
   >
   >    Wenn Sie **[!UICONTROL ** Abbrechen **]**, können Sie keinen zugeordneten Datensatz erstellen.

4. Im [!UICONTROL Zugeordnete Datensätze > Nicht benannter zugeordneter Datensatz] screen:

   1. Definieren Sie eine **[!UICONTROL ** Datensatzname **]** und (optional) **[!UICONTROL ** Beschreibung **]**,

   2. Wählen Sie die Sandbox aus dem **[!UICONTROL ** Sandbox **]** Liste, in der der Ereignis-Datensatz gespeichert wird.

      ![Erstellungsbildschirm beim ersten Versuch](./assets/create-initial.png)

   3. Wählen Sie die **[!UICONTROL ** Quelldatensatz auswählen **]** Schaltfläche.

      Im [!UICONTROL Datensatz auswählen, der zugeordnet werden soll] Popup-Fenster:

      ![Datensatz auswählen](./assets/select-one-dataset.png)

      - Datensatz auswählen und auswählen **[!UICONTROL ** Auswählen **]** , um fortzufahren.

   4. Wählen Sie eine persistente Kennung aus der **[!UICONTROL ** Persistente ID **]** Liste.

   5. Wählen Sie eine vorübergehende Kennung aus der **[!UICONTROL ** Verlaufs-ID **]** Liste.

      Beachten Sie, dass ein Vorschaufenster erscheint, um die Sättigungsraten (wie oft es einen Wert für jeden angegebenen Bezeichner über die Anzahl der Ereignisse gibt) für die letzten sieben Tage zu berechnen. Nach Abschluss der Berechnung visualisiert das Bedienfeld mit Farben, ob die Mindestbedingungen für das Stitching erfüllt sind (grün) oder nicht (rot).

      ![Erstellen von zusammengeführten Datensätzen mit Statusraten](./assets/create-before-experimenting.png)

      Die Mindestbedingungen sind:

      - dauerhafte Sättigung der Kennungen: Rate >= 95 %

      - Sättigung der vorübergehenden Kennung: Rate >= 5 %

        Wenn die Mindestbedingungen erfüllt sind, können Sie mit Beispielwerten experimentieren.

      - Auswählen **[!UICONTROL ** Erstellen von demo-zugeordneten IDs **]**.

        Im [!UICONTROL Experimentieren mit Beispielwerten] Dialogfeld wird eine Tabelle mit Beispielwert für [!UICONTROL timestamp], [!UICONTROL Persistente ID], [!UICONTROL Verlaufs-ID], [!UICONTROL Zugeordnete ID (Live)], [!UICONTROL Zugeordnete ID (1-Tage-Wiederholung)], und [!UICONTROL Zugeordnete ID (7-Tage-Wiederholung)].

            ![Experimentieren mit Beispielwerten](./assets/experiment-sample-values.png)
            
            1.  Geben Sie einen Wert für ** ein.[!UICONTROL **Persistente ID**]**.
            
            2.  Wählen Sie **[!UICONTROL **Zugeordnete IDs aktualisieren**]** um die Auswirkungen des Stitching-Prozesses auf die Daten im Datensatz zu sehen.
            
            3.  Wählen Sie **[!UICONTROL **Close**]** wenn Sie mit dem Experimentieren mit Beispielwerten fertig sind.
        

        Zurück im [!UICONTROL Zugewiesene Datensätze > _Datensatzname_] screen:

   6. Wählen Sie eine Option für die Häufigkeit und den Zeitraum der Wiederherstellung von historischen Daten aus dem **[!UICONTROL ** Wiederholungsfenster **]** Liste.

      Sie können zwischen dem Standardwert **[!UICONTROL ** Vorheriger Tag, täglich **]** oder **[!UICONTROL ** Vorherige 7 Tage, wöchentlich **]**.

   7. Wählen Sie einen Wert aus dem **[!UICONTROL ** Durchschnittliche Anzahl der täglichen Ereignisse **]** Liste.

   8. Wert eingeben (zwischen `0` und `12`) in **[!UICONTROL ** Anzahl der aufzustockenden Monate **]**.

   9. Auswählen **[!UICONTROL ** Speichern **]** , um Ihren zugeordneten Datensatz zu speichern und die Zuordnung zu starten.

## Status anzeigen

Sie können den Status des Stitching im [!UICONTROL Zugeordnete Datensätze] Liste.

- Auswählen **[!UICONTROL ** Stitching **]** von **[!UICONTROL ** Data Management **]** in der oberen Leiste.

  Es wird eine Liste von zugeordneten Datensätzen angezeigt, die jeweils mit [!UICONTROL Sandbox], [!UICONTROL Quelldatensatz], [!UICONTROL Status], [!UICONTROL Aufstockungsstatus], [!UICONTROL Inhaber], und [!UICONTROL Erstellungsdatum].

  ![Übersicht über zugeordnete Datensätze](./assets/overview-stitched-datasetts.png)

  Mögliche Werte für [!UICONTROL Status] sind:

  | Wert | Erklärung |
  |-----|-----|
  | **[!UICONTROL ** In Warteschlange **]** | Die Anfrage wird empfangen und bald verarbeitet. |
  | **[!UICONTROL ** Erstellung **]** Gestartet | Ressourcen und neu zugeordnete Datensätze werden derzeit erstellt. |
  | **[!UICONTROL ** Laufende Zuordnung **]** | Ressourcen und zugeordneter Datensatz sind vorhanden und die Zuordnung wird durchgeführt |
  | **[!UICONTROL ** Fehler **]** | Beim Stitching tritt ein Problem auf. Vielleicht hat sich ein Schema zwischen Quelldatensatz und zugeordnetem Datensatz geändert, das tägliche Volumen ist zu groß oder ... (_**Weitere Informationen finden Sie hier ...**_) |

  >[!INFO]
  >
  >    Bei jeder Statusänderung wird eine Benachrichtigung mit der Nachricht gesendet **[!UICONTROL ** Zugewiesener Datensatz _Name des Datensatzes_ hat sich in den Status geändert _Statusname _**]**.


  Die [!UICONTROL Aufstockungsstatus] kann die folgenden Werte aufweisen: 0 %, 25 %, 50 %, 75 % oder 100 %.

  Sie können auf das Informationssymbol klicken, um ein Popup mit weiteren Details zum ausgewählten zugeordneten Datensatz anzuzeigen.


## Löschen

>[!NOTE]
>
>Sie können nur Datensätze mit dem Status löschen [!UICONTROL Laufende Zuordnung], [!UICONTROL Fehler]oder [!UICONTROL In Warteschlange].


So löschen Sie einen einzelnen zugeordneten Datensatz:

- Auswählen **[!UICONTROL **...**]** für den zugeordneten Datensatz und wählen Sie **[!UICONTROL ** Löschen **]** aus dem Menü.

  ![Zugewiesenen Datensatz löschen](./assets/delete-stitched-dataset.png)

So löschen Sie mehrere zugeordnete Daten:

- Wählen Sie mehrere zugeordnete Datensätze mithilfe des Kontrollkästchens am Anfang jedes aufgelisteten Datensatzes aus.

- Auswählen **[!UICONTROL **...**]** aus einem der ausgewählten zugeordneten Datensätze und wählen Sie **[!UICONTROL ** Löschen **]** aus dem Menü.
