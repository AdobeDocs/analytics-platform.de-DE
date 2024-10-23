---
title: Erstellen von Anmerkungen
description: Erstellen von Anmerkungen in Workspace.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 24%

---

# Erstellen von Anmerkungen

Standardmäßig können nur Administratoren Anmerkungen erstellen. Benutzer haben Berechtigungen zum Anzeigen von Anmerkungen, ähnlich wie beim Anzeigen anderer Komponenten durch Benutzer (z. B. Filter, berechnete Metriken usw.).

Administratoren können Benutzern über die Admin Console jedoch die Berechtigung **[!UICONTROL Anmerkungserstellung]** für die **[!UICONTROL Berichterstellungs-Tools]** in den **[!UICONTROL Berechtigungen zum Bearbeiten des CJA Workspace-Zugriffs]** erteilen. Weitere Informationen finden Sie unter [Zugriffskontrolle auf Benutzerebene](/help/technotes/access-control.md#user-level-access) .

Sie können Anmerkungen wie folgt erstellen:

![Erstellen einer Anmerkung](assets/create-annotation.png)

* ?? Wählen Sie in der Hauptbenutzeroberfläche **[!UICONTROL Komponenten]** und dann **[!UICONTROL Anmerkungen]** aus. Wählen Sie ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] aus dem Manager [[!UICONTROL Annotations]](/help/components/annotations/manage-annotations.md).
* ?? Wählen Sie in einem Workspace-Projekt im Kontextmenü einer Visualisierung **[!UICONTROL Anmerkung aus Auswahl erstellen]** aus.
* ?? Wählen Sie in einem Workspace-Projekt im Kontextmenü eines Liniendiagramms die Option **[!UICONTROL Auswahl kommentieren]**.
* ??Wählen Sie in einem Workspace-Projekt **[!UICONTROL Komponenten]** aus dem Menü und dann **[!UICONTROL Anmerkung erstellen]**.
* ?? Verwenden Sie in einem Workspace-Projekt die Tastenkombination **[!UICONTROL Strg+Umschalt+o]** (Windows) oder **[!UICONTROL Umschalt+Befehl+o]** (macOS).

Um die Anmerkung zu definieren, verwenden Sie den [[!UICONTROL Anmerkungs-Builder]](#annotation-builder):

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Anmerkungsgenerator {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="Anmerkungsdetails"
>abstract="Mit Anmerkungen können Sie Ihrer Organisation kontextbezogene Datennuancen und Einblicke effektiv übermitteln. Durch sie können Sie Kalenderereignisse an bestimmte Dimensionen/Metriken binden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="Umfang"
>abstract="Mit dem Umfang können Sie anpassen, welche Daten kommentiert werden. Berechnete Metriken und Segmente übernehmen auf Komponenten angewendete Anmerkungen, die in ihren Definitionen verwendet werden, nicht automatisch. Sie können neue berechnete Metriken zum Bereich des Umfangs einer vorhandenen Anmerkung hinzufügen. Neue Segmente erfordern eine neue Anmerkung."

<!-- markdownlint-enable MD034 -->


Das Dialogfeld **[!UICONTROL Anmerkungs-Builder]** wird zum Erstellen neuer oder Bearbeiten vorhandener Anmerkungen verwendet. Das Dialogfeld trägt den Titel **[!UICONTROL Neue Anmerkung]** oder **[!UICONTROL Anmerkung bearbeiten]** für Anmerkungen, die Sie über den Manager [[!UICONTROL Anmerkungen] erstellen oder verwalten.](/help/components/annotations/manage-annotations.md)


>[!BEGINTABS]

>[!TAB Anmerkungs-Builder]

![Fenster „Anmerkungsdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/annotation-builder.png)

>[!TAB Anmerkung erstellen/bearbeiten]

![Fenster „Anmerkungsdetails“ mit Feldern und Optionen, die im nächsten Abschnitt beschrieben werden.](assets/create-edit-annotation.png)

>[!ENDTABS]

1. Geben Sie die folgenden Details an (![Erforderlich](/help/assets/icons/Required.svg) ist erforderlich):

   | Element | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Datenansicht]** | Sie können die Datenansicht für die Anmerkung auswählen. Die von Ihnen definierte Anmerkung ist in den Workspace-Projekten auf der Grundlage der ausgewählten Datenansicht als Anmerkung verfügbar. Diese Auswahl wird überschrieben, wenn Sie [!UICONTROL Auf alle Datenansichten anwenden] aktiviert haben. |
   | **[!UICONTROL Projektspezifische Anmerkungen]** | Ein Informationsfeld, mit dem erklärt wird, dass die von Ihnen erstellte Anmerkung nur im Workspace-Projekt sichtbar ist, an dem Sie arbeiten. Aktivieren Sie **[!UICONTROL Diese Anmerkung für alle Projekte verfügbar machen]** , um die Anmerkung für alle Projekte sichtbar zu machen. Dieses Informationsfeld ist nur sichtbar, wenn Sie eine Anmerkung in einem Workspace-Projekt erstellen. |
   | **[!UICONTROL Titel]** ![Erforderlich](/help/assets/icons/Required.svg) | Nennen Sie die Anmerkung, z. B. `Needs further investigation`. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine Beschreibung für die Anmerkung ein, z. B. `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Tags]** | Organisieren Sie die Anmerkung, indem Sie ein oder mehrere Tags erstellen oder anwenden. Beginnen Sie mit der Eingabe, um vorhandene Tags zu finden, die Sie auswählen können. Oder drücken Sie die **[!UICONTROL Eingabetaste]** , um ein neues Tag hinzuzufügen. Wählen Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg) aus, um ein Tag zu entfernen. |
   | **[!UICONTROL Angewendetes Datum]** ![Erforderlich](/help/assets/icons/Required.svg) | Wählen Sie das Datum oder den Datumsbereich aus, das bzw. der vorhanden sein muss, damit die Anmerkung sichtbar ist. Wenn Sie eine Anmerkung mit der Verknüpfung erstellen, wird standardmäßig ein Datumsbereich für den Tag verwendet. Wenn Sie eine Anmerkung mithilfe einer Auswahl in einer Visualisierung erstellen, wird standardmäßig der Datumsbereich für die Anmerkung basierend auf dem Bereich verwendet, zu dem die Visualisierung gehört. |
   | **[!UICONTROL Farbe]** | Wenden Sie eine Farbe auf die Anmerkung an. Die Anmerkung wird im Projekt mit der ausgewählten Farbe angezeigt. Mit Farben können Sie Anmerkungen kategorisieren, z. B. Feiertage, externe Ereignisse, Tracking-Probleme usw. |
   | **[!UICONTROL Anwendungsbereich]** | Ziehen Sie Metriken per Drag-and-Drop aus dem Komponentenbereich, in dem die Anmerkung Trigger wird. Zum Beispiel Personen, Sitzungen und Ereignisse. Ziehen Sie dann beliebige Dimensionen oder Filter aus dem Komponentenbereich, die als Filter fungieren, um zu bestimmen, ob die Anmerkung angezeigt werden soll oder nicht. Wenn Sie keinen Bereich angeben, gilt die Anmerkung für alle Ihre Daten. <br/>Sie haben zwei Optionen:<ul><li>**[!UICONTROL Jede dieser Metriken ist vorhanden]**: Ziehen Sie per Drag-and-Drop bis zu 10 Metriken in den Trigger der anzuzeigenden Anmerkung.<br/>Beispielsweise hat die Umsatzmetrik die Erfassung von Daten für einen bestimmten Datumsbereich beendet. Ziehen Sie die Metrik Umsatz in dieses Feld.</li><li>**[!UICONTROL Mit all diesen Filtern]**: Ziehen Sie bis zu 10 Dimensionen oder Filter in den Arbeitsbereich, um zu filtern, ob die Anmerkung angezeigt wird.</li></ul><p><p>**Hinweis:** Jede Anmerkung, die auf eine Komponente angewendet wird, die anschließend als Teil einer berechneten Metrik oder Filterdefinition verwendet wird, übernimmt die Anmerkung NICHT automatisch. Die gewünschte berechnete Kennzahl muss auch dem Abschnitt „Umfang“ hinzugefügt werden, damit die Anmerkung angezeigt wird. Für jeden Filter, den Sie mit denselben Informationen kommentieren möchten, sollte jedoch eine neue Anmerkung erstellt werden. Sie wenden beispielsweise eine Anmerkung auf [!UICONTROL Bestellungen] an einem bestimmten Tag an. Anschließend verwenden Sie [!UICONTROL Bestellungen] in einer berechneten Metrik für denselben Datumsbereich. Die neue berechnete Metrik zeigt die Anmerkung für Bestellungen nicht automatisch an. Fügen Sie außerdem die berechnete Metrik zum Bereich hinzu, damit die Anmerkung angezeigt wird. |
   | **[!UICONTROL Auf alle Datenansichten anwenden]** | Standardmäßig gilt die Anmerkung für die ursprüngliche Datenansicht. Wenn Sie dieses Kontrollkästchen aktivieren, können Sie die Anmerkung für alle Datenansichten im Unternehmen gelten lassen. |

   {style="table-layout:auto"}

1. Auswählen
   * **[!UICONTROL Speichern]** zum Speichern der Anmerkung.
   * **[!UICONTROL Speichern unter]** , um eine Kopie der Anmerkung zu speichern.
   * **[!UICONTROL Löschen]** , um eine Anmerkung zu löschen.
   * **[!UICONTROL Abbrechen]** , um alle Änderungen abzubrechen, die Sie an einer Anmerkung vorgenommen haben, oder um die Erstellung einer neuen Anmerkung abzubrechen.
