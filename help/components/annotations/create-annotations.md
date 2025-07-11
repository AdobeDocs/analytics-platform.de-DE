---
title: Erstellen von Anmerkungen
description: Erfahren Sie, wie Sie in Analysis Workspace Anmerkungen erstellen.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 79%

---

# Erstellen von Anmerkungen

Standardmäßig können nur Admins Anmerkungen erstellen. Benutzer haben die Berechtigung, Anmerkungen anzuzeigen, ähnlich wie Benutzer andere Komponenten anzeigen (z. B. Segmente, berechnete Metriken usw.).

Admins können Benutzenden über die Admin Console jedoch die Berechtigung **[!UICONTROL Anmerkungserstellung]** für **[!UICONTROL Reporting-Tools]** unter **[!UICONTROL Berechtigungen für CJA Workspace-Zugriff bearbeiten]** erteilen. Weitere Informationen finden Sie unter [Zugriffskontrolle auf Benutzerebene](/help/technotes/access-control.md#user-level-access).

Sie können Anmerkungen wie folgt erstellen:

![Erstellen einer Anmerkung](assets/create-annotation.png)

* **A**. Wählen Sie in der Hauptbenutzeroberfläche die Option **[!UICONTROL Komponenten]** und dann **[!UICONTROL Anmerkungen]** aus. Wählen Sie ![Hinzufügen](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Hinzufügen]**] im [[!UICONTROL Anmerkungs]-Manager](/help/components/annotations/manage-annotations.md) aus.
* **B**. Wählen Sie in einem Workspace-Projekt aus dem Kontextmenü einer Visualisierung die Option **[!UICONTROL Anmerkung aus Auswahl erstellen]** aus.
* **C**. Wählen Sie in einem Workspace-Projekt aus dem Kontextmenü eines Liniendiagramms die Option **[!UICONTROL Auswahl mit Anmerkungen versehen]** aus.
* **D**. Wählen Sie in einem Workspace-Projekt aus dem Menü die Option **[!UICONTROL Komponenten]** und dann **[!UICONTROL Anmerkung erstellen]** aus.
* **E**.  Verwenden Sie in einem Workspace-Projekt den Tastaturbefehl **[!UICONTROL Strg+Umschalt+O]** (Windows) bzw. **[!UICONTROL Umschalt+Befehlstaste+O]** (macOS).

Um die Anmerkung zu definieren, verwenden Sie den [[!UICONTROL Anmerkungsgenerator]](#annotation-builder).

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Anmerkungserstellung {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_details"
>title="Anmerkungsdetails"
>abstract="Mit Anmerkungen können Sie Ihrer Organisation kontextbezogene Datennuancen und Erkenntnisse effektiv übermitteln. Durch Anmerkungen können Sie Kalenderereignisse an bestimmte Dimensionen und Metriken binden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_scope"
>title="Anwendungsbereich"
>abstract="Mit dem Umfang können Sie anpassen, welche Daten kommentiert werden. Berechnete Metriken und Segmente übernehmen nicht automatisch Anmerkungen, die auf die in ihren Definitionen verwendeten Komponenten angewendet werden. Sie können zu einer vorhandenen Anmerkung im Abschnitt „Umfang“ neue berechnete Metriken hinzufügen. Neue Segmente erfordern eine neue Anmerkung."

<!-- markdownlint-enable MD034 -->


Das Dialogfeld **[!UICONTROL Anmerkungserstellung]** wird zum Erstellen neuer oder Bearbeiten vorhandener Anmerkungen verwendet. Das Dialogfeld hat den Titel **[!UICONTROL Neue Anmerkung]** oder **[!UICONTROL Anmerkung bearbeiten]** für Anmerkungen, die Sie über den [[!UICONTROL Anmerkungs]-Manager erstellen oder verwalten.](/help/components/annotations/manage-annotations.md)


>[!BEGINTABS]

>[!TAB Anmerkungserstellung]

![Fenster „Anmerkungsdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/annotation-builder.png){zoomable="yes"}

>[!TAB  Anmerkung bearbeiten]

![Fenster „Anmerkungsdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/create-edit-annotation.png){zoomable="yes"}

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) bedeutet erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für die Anmerkung auswählen. Die von Ihnen definierte Anmerkung ist in den Workspace-Projekten auf Grundlage der ausgewählten Datenansicht als Anmerkung verfügbar. Diese Auswahl wird überschrieben, wenn Sie [!UICONTROL Auf alle Datenansichten anwenden] aktiviert haben. |
   | **[!UICONTROL Projektspezifische Anmerkungen]** | Ein Informationsfeld, mit dem erklärt wird, dass die von Ihnen erstellte Anmerkung nur im Workspace-Projekt sichtbar ist, an dem Sie arbeiten. Aktivieren Sie **[!UICONTROL Anmerkung für alle Projekte verfügbar machen]**, um die Anmerkung für alle Projekte sichtbar zu machen. Dieses Informationsfeld ist nur sichtbar, wenn Sie eine Anmerkung in einem Workspace-Projekt erstellen. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Benennen Sie die Regel, beispielsweise mit `Needs further investigation`. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für die Anmerkung ein, z. B. `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Tags]** | Organisieren Sie die Anmerkung, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um nach vorhandenen Tags zu suchen, die Sie auswählen können. Oder drücken Sie die **[!UICONTROL Eingabetaste]**, um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Anwendungsdatum]** ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie das Datum oder den Datumsbereich aus, das bzw. der vorhanden sein muss, damit die Anmerkung sichtbar ist. Wenn Sie eine Anmerkung mithilfe des Tastaturbefehls erstellen, gibt die Anmerkung standardmäßig einen Datumsbereich für nur diesen Tag vor. Wenn Sie eine Anmerkung mit einer Auswahl in einer Visualisierung erstellen, wird die Anmerkung standardmäßig auf den Datumsbereich basierend auf dem Datumsbereich für das Bedienfeld, zu dem die Visualisierung gehört, gesetzt. |
   | **[!UICONTROL Farbe]** | Wenden Sie eine Farbe auf die Anmerkung an. Die Anmerkung wird im Projekt mit der ausgewählten Farbe angezeigt. Mit Farben können Sie Anmerkungen kategorisieren, z. B. Feiertage, externe Ereignisse, Tracking-Probleme usw. |
   | **[!UICONTROL Anwendungsbereich]** | Ziehen Sie die Metriken, die die Anmerkung auslösen, per Drag-and-Drop aus dem Panel mit den Komponenten in das entsprechende Feld. Zum Beispiel „Personen“, „Sitzungen“ und „Ereignisse“. Ziehen Sie dann alle Dimensionen oder Segmente, die als Segmente dienen, per Drag-and-Drop aus dem Komponentenbereich, um zu bestimmen, ob die Anmerkung angezeigt werden soll oder nicht. Wenn Sie keinen Bereich angeben, gilt die Anmerkung für alle Ihre Daten. <br/>Es gibt zwei Optionen:<ul><li>**[!UICONTROL Zumindest eine dieser Metriken ist vorhanden]**: Ziehen Sie per Drag-and-Drop bis zu 10 Metriken in das Feld, die jeweils auslösen sollen, dass die Anmerkung angezeigt wird.<br/>Die Umsatzmetrik hat beispielsweise die Erfassung von Daten für einen bestimmten Datumsbereich eingestellt. Ziehen Sie die Umsatzmetrik in dieses Feld.</li><li>**[!UICONTROL Mit allen diesen Segmenten]**: Ziehen Sie bis zu 10 Dimensionen oder Segmente per Drag-and-Drop in dieses Segment, unabhängig davon, ob die Anmerkung angezeigt wird.</li></ul><p><p>**Hinweis:** Anmerkungen, die auf eine Komponente angewendet werden, die anschließend als Teil einer berechneten Metrik oder Segmentdefinition verwendet wird, übernehmen die Anmerkung NICHT automatisch. Die gewünschte berechnete Kennzahl muss auch dem Abschnitt „Umfang“ hinzugefügt werden, damit die Anmerkung angezeigt wird. Es sollte jedoch eine neue Anmerkung für jedes Segment erstellt werden, das mit denselben Informationen versehen werden soll. Beispiel: Sie wenden eine Anmerkung auf [!UICONTROL Bestellungen] an einem bestimmten Tag an. Anschließend verwenden Sie [!UICONTROL Bestellungen] in einer berechneten Metrik für denselben Datumsbereich. Die neue berechnete Metrik zeigt die Anmerkung für Bestellungen nicht automatisch an. Fügen Sie die berechnete Metrik außerdem zum Abschnitt „Umfang“ hinzu, damit die Anmerkung angezeigt wird. |
   | **[!UICONTROL Auf alle Datenansichten anwenden]** | Standardmäßig gilt die Anmerkung für die ursprüngliche Datenansicht. Wenn Sie dieses Kontrollkästchen aktivieren, können Sie die Anmerkung für alle Datenansichten im Unternehmen gelten lassen. |

   {style="table-layout:auto"}

1. Auswählen
   * **[!UICONTROL Speichern]**: Speichert die Anmerkung.
   * **[!UICONTROL Speichern unter]**: Speichert eine Kopie der Anmerkung.
   * **[!UICONTROL Löschen]**: Löscht eine Anmerkung.
   * **[!UICONTROL Abbrechen]**: Bricht alle Änderungen ab, die Sie an einer Anmerkung vorgenommen haben, oder bricht die Erstellung einer neuen Anmerkung ab.
