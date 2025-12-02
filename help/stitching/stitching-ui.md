---
title: Zuordnung
description: Erfahren Sie, wie Sie zusammengefügte Datensätze erstellen und verwalten
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Erstellen und Verwalten zugeordneter Datensätze

{{select-package}}

Durch das Zusammenfügen können Admins Identitäten mit Datensätzen zusammenfügen, die in Customer Journey Analytics verfügbar sind. Das Zusammenfügen von Datensätzen erhöht die Genauigkeit der Darstellung eines Profils, was letztendlich zu einer besseren Analyse und Berichterstellung führt.

Mit dem Zusammenfügungsprozess können Sie eine vorhandene **persistente ID** in einem Datensatz definieren. Ordnen Sie dann diese persistente Kennung für ein angegebenes Wiederholungsfenster (täglich, wöchentlich) mit der genauesten **Personen-ID** (Person oder authentifizierte Kennung) zu, die für diesen Datensatz verfügbar ist. Beispiele für Personenkennungen sind E-Mail-Adresse, Telefonnummer, CRM-ID oder andere im Diagramm gespeicherte Identitäten. Weitere Informationen [ Zusammenfügen finden ](overview.md) unter „Übersicht“.

## Erstellen

Um das Zusammenfügen zu initiieren, erstellen Sie einen oder mehrere zusammengefügte Datensätze. So erstellen Sie einen zusammengefügten Datensatz:

1. Wählen Sie **[!UICONTROL ** Zusammenfügen **]** aus **[!UICONTROL ** Daten-Management **]** in der oberen Leiste aus.

2. Wählen Sie im [!UICONTROL Zusammengefügte Datensätze] die Option **[!UICONTROL ** Zusammengefügten Datensatz erstellen **]** aus.

   Es wird ein Dialogfeld angezeigt, in dem Ihre Zuständigkeiten erläutert werden.

3. Wählen **[!UICONTROL ** Weiter **]**, wenn Sie diese Verantwortlichkeiten akzeptieren.

   >[!NOTE]
   >
   >    Wenn Sie **[!UICONTROL ** Abbrechen **]** auswählen, können Sie keinen zusammengefügten Datensatz erstellen.

4. Im Bildschirm [!UICONTROL Zusammengefügte Datensätze > Nicht benannter zusammengefügter Datensatz]:

   1. Definieren eines **[!UICONTROL ** Datensatznamens **]** und (optional) **[!UICONTROL ** Beschreibung **]**,

   2. Wählen Sie die Sandbox aus der **[!UICONTROL ** Sandbox **]**-Liste aus, in der der Ereignis-Datensatz gespeichert ist.

      ![Anfänglicher Erstellungsbildschirm](./assets/create-initial.png)

   3. Klicken Sie auf die **[!UICONTROL ** Quelldatensatz auswählen **]**.

      Im Popup[!UICONTROL Fenster „Einen Datensatz zum Zusammenfügen auswählen]:

      ![Einen Datensatz auswählen](./assets/select-one-dataset.png)

      - Wählen Sie einen Datensatz aus und wählen Sie **[!UICONTROL ** Auswählen **]**, um fortzufahren.

   4. Wählen Sie eine persistente Kennung aus der Liste **[!UICONTROL ** Persistente ID **]** aus.

   5. Wählen Sie eine Personenkennung aus der Liste **[!UICONTROL ** Vorübergehende ID **]** aus.

      Sie werden feststellen, dass ein Vorschaufenster angezeigt wird, um die Sättigungsraten (Anzahl der Male, wie oft es für jede der angegebenen Kennungen einen Wert über die Anzahl der Ereignisse gibt) der letzten sieben Tage zu berechnen. Wenn die Berechnung abgeschlossen ist, visualisiert das Bedienfeld mit Farben, ob die minimalen Bedingungen für das Zusammenfügen erfüllt sind (grün) oder nicht erfüllt sind (rot).

      ![Erstellen eines zusammengefügten Datensatzes mit Sättigungsraten](./assets/create-before-experimenting.png)

      Es gelten folgende Mindestbedingungen:

      - Sättigung der persistenten Kennung: Rate >= 95%

      - Sättigung der Personenkennung: Rate >= 5%

        Wenn die Mindestbedingungen erfüllt sind, können Sie mit Beispielwerten experimentieren.

      - Wählen Sie **[!UICONTROL ** Erstellen einer Demo mit zusammengefügten IDs **]** aus.

        Im Dialogfeld [!UICONTROL Experimentieren mit Beispielwerten] wird eine Tabelle mit Beispielwert für [!UICONTROL Zeitstempel], [!UICONTROL Persistente ID], [!UICONTROL Vorübergehende ID], [!UICONTROL Zusammengefügte ID (Live)], [!UICONTROL Zusammengefügte ID (1-Tages-Wiederholung)] und [!UICONTROL Zusammengefügte ID (7-Tages-Wiederholung)].

            ![Experimentieren mit Beispielwerten](./assets/experiment-sample-values.png)
            
            1.  Geben Sie einen Wert für die **[!UICONTROL **Persistente ID**]** ein.
            
            2.  Wählen Sie **[!UICONTROL **Zusammengefügte IDs aktualisieren**]**, um die Auswirkungen des Zusammenfügungsprozesses auf die Daten im Datensatz zu sehen.
            
            3.  Wählen Sie **[!UICONTROL **Close**]** aus, wenn Sie mit den Beispielwerten experimentiert haben.
        

        Zurück im Bildschirm [!UICONTROL Zusammengefügte Datensätze > _Datensatzname_]:

   6. Wählen Sie eine Option für die Häufigkeit und den Zeitraum der Wiederherstellung historischer Daten aus der Liste **[!UICONTROL ** Wiederholungsfenster **]** aus.

      Sie können zwischen dem Standardwert (**[!UICONTROL ** Tag, **]** oder **[!UICONTROL ** 7 Tage, wöchentlich **]** wählen.

   7. Wählen Sie einen Wert aus der Liste **[!UICONTROL ** Durchschnittliche Anzahl der täglichen Ereignisse **]** aus.

   8. Geben Sie einen Wert (zwischen `0` und `12`) in „Anzahl **[!UICONTROL ** Monate für die Aufstockung“ **]**.

   9. Wählen Sie **[!UICONTROL ** Speichern **]** aus, um den zusammengefügten Datensatz zu speichern und die Zusammenfügung zu starten.

## Status anzeigen

Sie können den Status der Zuordnung in der Liste [!UICONTROL Zusammengefügte Datensätze] anzeigen.

- Wählen Sie **[!UICONTROL ** Zusammenfügen **]** aus **[!UICONTROL ** Daten-Management **]** in der oberen Leiste aus.

  Es wird eine Liste von zugeordneten Datensätzen angezeigt, die jeweils mit [!UICONTROL Sandbox], [!UICONTROL Source-Datensatz], [!UICONTROL Status], [!UICONTROL Aufstockungsstatus], [!UICONTROL Inhaber] und [!UICONTROL Erstellt].

  ![Übersicht über zusammengefügte Datensätze](./assets/overview-stitched-datasetts.png)

  Mögliche Werte für [!UICONTROL Status] sind:

  | Wert | Erklärung |
  |-----|-----|
  | **[!UICONTROL ** In Warteschlange **]** | Die Anfrage wird empfangen und in Kürze verarbeitet. |
  | **[!UICONTROL ** Erstellung **]** in Bearbeitung | Ressourcen und neu zusammengefügter Datensatz werden erstellt. |
  | **[!UICONTROL ** Zusammenfügung in Bearbeitung **]** | Ressourcen und zugeordneter Datensatz sind vorhanden und die Zuordnung wird ausgeführt |
  | **[!UICONTROL ** Fehler **]** | Es gibt ein Problem beim Zusammenfügen. Möglicherweise hat sich ein Schema zwischen Quelldatensatz und zugeordnetem Datensatz geändert, das tägliche Volumen ist zu groß oder… (_**hier weitere Informationen benötigen…**_) |

  >[!INFO]
  >
  >    Wenn sich ein Status ändert, wird eine Benachrichtigung mit der Nachricht **[!UICONTROL ** Zugeordneter Datensatz _Name des Datensatzes_ gesendet, die in Status _Name des Status _**]**geändert wurde.


  Der [!UICONTROL Aufstockungsstatus] kann die folgenden Werte aufweisen: 0 %, 25 %, 50 %, 75 % oder 100 %.

  Sie können das Informationssymbol auswählen, um ein Popup mit weiteren Details zum ausgewählten zugeordneten Datensatz anzuzeigen.


## Löschen

>[!NOTE]
>
>Sie können nur Datensätze löschen, die den Status [!UICONTROL Zuordnung läuft], [!UICONTROL Fehler] oder [!UICONTROL In Warteschlange] haben.


So löschen Sie einen einzelnen zugeordneten Datensatz:

- Wählen Sie **[!UICONTROL **…**]** für den zusammengefügten Datensatz aus und wählen Sie **[!UICONTROL ** Löschen **]** aus dem Menü.

  ![Löschen eines zusammengefügten Datensatzes](./assets/delete-stitched-dataset.png)

So löschen Sie mehrere zusammengefügte Daten:

- Wählen Sie mehrere zusammengefügte Datensätze aus, indem Sie das Kontrollkästchen am Anfang jedes aufgelisteten Datensatzes aktivieren.

- Wählen Sie **[!UICONTROL **…**]** aus einem der ausgewählten zugeordneten Datensätze aus und wählen Sie **[!UICONTROL ** Löschen **]** aus dem Menü aus.
