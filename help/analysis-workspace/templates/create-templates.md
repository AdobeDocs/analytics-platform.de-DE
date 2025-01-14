---
description: Eine Übersicht über die Verwendung von Standardvorlagen in Analysis Workspace.
title: Verwenden von Vorlagen
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: c5c05e17ad3b3e2bbf643d47bd58cde5ac2de0cb
workflow-type: tm+mt
source-wordcount: '1599'
ht-degree: 2%

---

# Erstellen und Verwalten von Vorlagen

Administratoren können Vorlagen erstellen und für andere Benutzer in ihrem angemeldeten Unternehmen speichern, um sie zu verwenden.

Personen im angemeldeten Unternehmen können diese Unternehmensvorlagen verwenden, wie unter &quot;[ verwenden](/help/analysis-workspace/templates/use-templates.md) beschrieben.

## Erstellen einer Vorlage

So erstellen Sie eine neue Vorlage, die von Personen in Ihrem Anmeldeunternehmen verwendet werden kann:

1. Erstellen Sie in Analysis Workspace ein Projekt für den gewünschten Status.

1. Wählen Sie [!UICONTROL **Projekt**] > **[!UICONTROL Als Vorlage speichern…]**.

   ![Unternehmensvorlage](assets/company-template-save.png)

1. Geben Sie im Dialogfeld [!UICONTROL Als Vorlage speichern] folgende Informationen ein:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Name]** | Geben Sie einen beschreibenden Namen für die Vorlage an. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine kurze Beschreibung für die Vorlage an, die ihre Verwendungszwecke beschreibt. |
   | **[!UICONTROL Warum diese Vorlage verwenden]** | Geben Sie eine kurze Erklärung ab, um Personen in der Organisation darüber zu informieren, wie diese Vorlage verwendet werden könnte. Diese Erklärung wird auf der Vorschauseite der Vorlage angezeigt. |
   | **[!UICONTROL Kanäle]** | Wählen Sie alle Kanäle aus, die auf diese Vorlage zutreffen. Sie können mehrere Kanäle auswählen: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-Channel]**, **[!UICONTROL Callcenter]** und **[!UICONTROL In-Store]**.<p>Die von Ihnen ausgewählten Auswahlmöglichkeiten bestimmen, wo die Vorlage angezeigt wird und welche Filter für Benutzer gelten, die über die Seite „Organisationsvorlagen“ darauf zugreifen.</p> |
   | **[!UICONTROL Anwendungsbeispiele]** | Wählen Sie alle Anwendungsfälle aus, die für diese Vorlage gelten. Sie können mehrere Anwendungsfälle auswählen: **[!UICONTROL Interaktion]**, **[!UICONTROL Konversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Akquise]** und **[!UICONTROL Journey Optimizer]**. <p>Die ausgewählten Auswahlen bestimmen den Speicherort der Vorlage auf der Seite „Organisationsvorlagen“. Benutzer können zur Vorlage navigieren oder die Liste nach Anwendungsfall filtern. </p><p>**Hinweis:** Die Option **[!UICONTROL Journey Optimizer]** ist nur verfügbar, wenn Journey Optimizer-Daten in der Datenansicht vorhanden sind, die Sie auf Customer Journey Analytics verwenden. Wenn Sie **[!UICONTROL Journey Optimizer]** auswählen, ist die Vorlage für die Verwendung in Adobe Journey Optimizer verfügbar. In Journey Optimizer ist auf der Seite **[!UICONTROL Berichte“ ein Dropdown]** Menü verfügbar, über das Benutzende diese Vorlage oder die Standardvorlage auswählen können. Weitere Informationen finden Sie unter [Erste Schritte mit der aktualisierten Berichterstellung](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) in der Dokumentation zu Journey Optimizer. |
   | **[!UICONTROL Journey Optimizer-Aktivitätstyp]** | Wählen Sie den Journey Optimizer-Aktivitätstyp aus, der mit dieser Vorlage verknüpft werden soll **[!UICONTROL (Kampagnen]**, **[!UICONTROL Journey]**, **[!UICONTROL Landingpages]**, **[!UICONTROL Berichte]** oder **[!UICONTROL Abonnements]**. <p>Lassen Sie dieses Feld leer, wenn diese Vorlage mit allen Aktivitätstypen verknüpft werden soll.</p><p>Dieses Feld wird nur angezeigt, wenn **[!UICONTROL Journey Optimizer]** im Feld **[!UICONTROL Anwendungsfälle]** ausgewählt ist.</p> |
   | **[!UICONTROL Journey Optimizer-Aktivität]** | Wählen Sie die Journey Optimizer-Aktivität aus, die mit dieser Vorlage verknüpft werden soll. <p>Lassen Sie dieses Feld leer, wenn diese Vorlage mit allen Aktivitäten des ausgewählten Aktivitätstyps verknüpft werden soll.</p><p>Dieses Feld wird nur angezeigt, wenn **[!UICONTROL Journey Optimizer]** im Feld **[!UICONTROL Anwendungsfälle]** ausgewählt ist.</p> |
   | **[!UICONTROL Tags]** | Geben Sie alle Tags an, die Sie auf die Vorlage anwenden möchten. Benutzer können die Liste der Vorlagen nach den von Ihnen hinzugefügten Tags filtern. |

1. Wählen Sie [!UICONTROL **Als Vorlage speichern**].

Informationen dazu, wie Benutzer ein Projekt basierend auf einer Vorlage erstellen können, finden Sie unter [Erstellen eines Projekts basierend auf einer Vorlage](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) in [Verwenden von Vorlagen](/help/analysis-workspace/templates/use-templates.md).

## Bearbeiten oder Löschen einer Vorlage

Admins können Unternehmensvorlagen bearbeiten oder löschen.

1. Wählen Sie in Analysis Workspace die Registerkarte [!UICONTROL **Workspace**] und dann in der ]**Leiste unter**[!UICONTROL  Vorlagen die Option **[!UICONTROL _login_company_name _templates]**.

1. Wenn Sie Vorlagen in einer Spaltenansicht anzeigen ![Spaltenansichtssymbol](assets/column-view-icon.png):

   1. Wählen Sie zur Vorlage, die Sie bearbeiten oder löschen möchten, das Infosymbol neben dem Vorlagennamen aus.

      ![Informationen zur Unternehmensvorlage](assets/company-template-info.png)

   1. Wählen Sie **[!UICONTROL Vorschau]** aus.

   1. Wählen Sie das Symbol Mehr und dann **[!UICONTROL Bearbeiten]** oder **[!UICONTROL Löschen]**.

      ![Vorlage bearbeiten oder löschen](assets/company-template-edit-delete.png)

1. Wenn Sie Vorlagen in einer Kartenansicht anzeigen ![Kartenansichtssymbol](assets/card-view-icon.png):

   1. Suchen Sie die Vorlage, die Sie bearbeiten oder löschen möchten.

      ![Kartenansicht der Unternehmensvorlage](assets/company-template-cards.png)

   1. Bewegen Sie den Mauszeiger über die Vorlage und wählen Sie dann **[!UICONTROL Vorschau]** aus.

   1. Wählen Sie das Symbol Mehr und dann **[!UICONTROL Bearbeiten]** oder **[!UICONTROL Löschen]**.

      ![Bearbeiten oder Löschen der Karte „Unternehmensvorlage“](assets/company-template-card-edit-delete.png)

1. Wenn Sie eine Vorlage bearbeiten, nehmen Sie die gewünschten Änderungen vor und klicken Sie auf [!UICONTROL **Projekt**] > **[!UICONTROL Als Vorlage speichern…]**.

   ![Unternehmensvorlage](assets/company-template-save.png)

1. Geben Sie im Dialogfeld [!UICONTROL Als Vorlage speichern] folgende Informationen ein:

   | Feld | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Name]** | Geben Sie einen beschreibenden Namen für die Vorlage an. |
   | **[!UICONTROL Beschreibung]** | Geben Sie eine kurze Beschreibung für die Vorlage an, die ihre Verwendungszwecke beschreibt. |
   | **[!UICONTROL Warum diese Vorlage verwenden]** | Geben Sie eine kurze Erklärung ab, um Personen in der Organisation darüber zu informieren, wie diese Vorlage verwendet werden könnte. Diese Erklärung wird auf der Vorschauseite der Vorlage angezeigt. |
   | **[!UICONTROL Kanäle]** | Wählen Sie alle Kanäle aus, die auf diese Vorlage zutreffen. Sie können mehrere Kanäle auswählen: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-Channel]**, **[!UICONTROL Callcenter]** und **[!UICONTROL In-Store]**. Wenn keine Kanäle ausgewählt sind, ist die Vorlage in allen Kanälen enthalten.<p>Die von Ihnen ausgewählten Auswahlmöglichkeiten bestimmen, wo die Vorlage angezeigt wird und welche Filter für Benutzer gelten, die über die Seite „Organisationsvorlagen“ darauf zugreifen.</p> |
   | **[!UICONTROL Anwendungsbeispiele]** | Wählen Sie alle Anwendungsfälle aus, die für diese Vorlage gelten. Sie können mehrere Anwendungsfälle auswählen: **[!UICONTROL Interaktion]**, **[!UICONTROL Konversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Akquise]** und **[!UICONTROL Journey Optimizer]**. <p>Die ausgewählten Auswahlen bestimmen den Speicherort der Vorlage auf der Seite „Organisationsvorlagen“. Benutzer können zur Vorlage navigieren oder die Liste nach Anwendungsfall filtern. </p><p>**Hinweis:** Auswahl von **[!UICONTROL Journey Optimizer]** macht die Vorlage auch in Adobe Journey Optimizer verfügbar. In Journey Optimizer ist auf der Seite **[!UICONTROL Berichte“ ein Dropdown]** Menü verfügbar, über das Benutzende diese Vorlage oder die Standardvorlage auswählen können. Weitere Informationen finden Sie unter [Erste Schritte mit der aktualisierten Berichterstellung](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) in der Dokumentation zu Journey Optimizer. |
   | **[!UICONTROL Journey Optimizer-Aktivitätstyp]** | Wählen Sie den Journey Optimizer-Aktivitätstyp aus, der mit dieser Vorlage verknüpft werden soll **[!UICONTROL (Kampagnen]**, **[!UICONTROL Journey]**, **[!UICONTROL Landingpages]**, **[!UICONTROL Berichte]** oder **[!UICONTROL Abonnements]**. <p>Lassen Sie dieses Feld leer, wenn diese Vorlage mit allen Aktivitätstypen verknüpft werden soll.</p><p>Dieses Feld wird nur angezeigt, wenn **[!UICONTROL Journey Optimizer]** im Feld **[!UICONTROL Anwendungsfälle]** ausgewählt ist.</p> |
   | **[!UICONTROL Journey Optimizer-Aktivität]** | Wählen Sie die Journey Optimizer-Aktivität aus, die mit dieser Vorlage verknüpft werden soll. <p>Lassen Sie dieses Feld leer, wenn diese Vorlage mit allen Aktivitäten des ausgewählten Aktivitätstyps verknüpft werden soll.</p><p>Dieses Feld wird nur angezeigt, wenn **[!UICONTROL Journey Optimizer]** im Feld **[!UICONTROL Anwendungsfälle]** ausgewählt ist.</p> |
   | **[!UICONTROL Tags]** | Geben Sie alle Tags an, die Sie auf die Vorlage anwenden möchten. Benutzer können die Liste der Vorlagen nach den von Ihnen hinzugefügten Tags filtern. |

1. Wählen Sie [!UICONTROL **Als Vorlage speichern**].

## Vorlagen umbenennen, taggen oder genehmigen

Administratoren können Unternehmensvorlagen umbenennen, taggen und genehmigen.

1. Wählen Sie in Analysis Workspace die Registerkarte [!UICONTROL **Workspace**] und dann in der linken Leiste **[!UICONTROL Projekte]** aus.

1. Wählen Sie das Filtersymbol aus, um die Liste der Projekte zu filtern.

1. Wählen Sie in der Filterleiste **SONSTIGE FILTER** und wählen Sie dann **Unternehmensvorlagen**.

   Eine Liste der Unternehmensvorlagen wird angezeigt. Alle regulären Projekte werden nicht angezeigt, es sei denn, sie sind angeheftet.

   Unternehmensvorlagen können durch das Symbol ![Vorlagen“ identifiziert werden](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) das dem Vorlagennamen vorangestellt ist.

   ![Anzeigen von Filtern für Unternehmensvorlagen](assets/company-templates-filter.png)

1. Klicken Sie auf das Auslassungssymbol **…** neben einer Vorlage, um die verfügbaren Optionen anzuzeigen.

   ![Aktionen für Unternehmensvorlagen](assets/company-templates-actions.png)

1. Wählen Sie **[!UICONTROL Umbenennen]**, **[!UICONTROL Taggen]** oder **[!UICONTROL Genehmigen]** aus.

   Sie können auch eine Vorlage löschen oder eine Vorlage löschen, wie unter [ oder Vorlagen löschen beschrieben](#edit-or-delete-templates).

1. (Optional) Um zur regulären Ansicht zurückzukehren, heben Sie in der Filterleiste die Auswahl von **[!UICONTROL Unternehmensvorlagen]** auf.

## Hinzufügen fehlender Komponenten zur Datenansicht für eine bestimmte Vorlage

Standardmäßig können einige Vorlagen, die von Adobe bereitgestellt werden, nicht verwendet werden, da sie Komponenten enthalten, die sich nicht in Ihrer Datenansicht befinden.

Für jede fehlende Komponente ist eine entsprechende Kontextbeschriftung in Ihrer Datenansicht verfügbar. Sie müssen entweder die entsprechende Kontextbeschriftung zu einer Komponente hinzufügen, die sich bereits in Ihrer Datenansicht befindet, oder Sie müssen Ihrer Datenansicht eine neue Komponente hinzufügen und ihr die Kontextbeschriftung hinzufügen.

Hinzufügen fehlender Komponenten zu einer Vorlage:

1. Wählen Sie in Analysis Workspace die Registerkarte [!UICONTROL **Workspace**] und wählen Sie dann unter **[!UICONTROL Vorlagen]** in der linken Leiste **[!UICONTROL Adobe-Vorlagen]**.

1. Wählen Sie das Filtersymbol aus, um die Liste der Vorlagen zu filtern.

1. Wählen Sie **[!UICONTROL Nicht einsatzbereit]** aus, um Vorlagen anzuzeigen, für die Komponenten erforderlich sind, die sich nicht in Ihrer Datenansicht befinden.

   ![Verwenden Sie eine Vorlage, der Komponenten fehlen](assets/template-not-ready.png)

1. Suchen Sie eine Vorlage, die noch nicht für die Verwendung mit Ihrer Datenansicht bereit ist.

1. Führen Sie einen der folgenden Schritte aus:

   * **Wenn Sie Vorlagen in einer Spaltenansicht anzeigen** (![)](assets/column-view-icon.png):

      1. Wechseln Sie zu der Vorlage, die noch nicht für die Verwendung mit Ihrer Datenansicht bereit ist, und wählen Sie dann das Informationssymbol neben dem Vorlagennamen aus.

         ![Informationen zur Unternehmensvorlage](assets/company-template-info.png)

      1. Wählen Sie **[!UICONTROL Vorschau]** aus.

         ![Vorlagenvorschau-Seite](assets/template-preview.png)

   * **Wenn Sie Vorlagen in einer Kartenansicht anzeigen** (![)](assets/card-view-icon.png):

      1. Suchen Sie die Vorlage, die noch nicht für Ihre Datenansicht verwendet werden kann.

         ![Kartenansicht der Unternehmensvorlage](assets/company-template-cards.png)

      1. Bewegen Sie den Mauszeiger über die Vorlage und wählen Sie dann **[!UICONTROL Vorschau]** aus.

         ![Vorlagenvorschau-Seite](assets/template-preview.png)

1. Im Abschnitt **[!UICONTROL Fehlende Komponenten]** wird eine Liste der Komponenten angezeigt, die in der Datenansicht fehlen. Wählen Sie **[!UICONTROL Diese Komponenten zur Datenansicht hinzufügen]** aus.

   Die Konfigurationsseite für die Datenansicht wird in einer neuen Registerkarte angezeigt.

1. Wählen Sie die **[!UICONTROL Komponenten]** für die Datenansicht aus.

   ![Registerkarte „Komponenten der Datenansicht“](assets/template-dataview.png)

1. Führen Sie für jede Komponente, die in der Vorlage als fehlend aufgelistet wurde, einen der folgenden Schritte auf der Registerkarte **[!UICONTROL Komponenten]** aus:

   * Wählen Sie **[!UICONTROL Abschnitt „Enthaltene Komponenten]** eine Komponente aus, die bereits in der Datenansicht enthalten ist, die Sie für die fehlende Komponente verwenden möchten.

   * Fügen Sie der Datenansicht eine neue Komponente hinzu, die Sie für die fehlende Komponente verwenden möchten, und wählen Sie dann die Komponente aus.

     Um eine neue Komponente zur Datenansicht hinzuzufügen, durchsuchen Sie die Liste der Schemafelder und ziehen Sie sie in den Abschnitt **[!UICONTROL Enthaltene Komponenten]**.

1. Suchen Sie bei ausgewählter Komponente das **[!UICONTROL Kontextbeschriftungen]** Dropdown-Menü in der rechten Spalte.

   ![Registerkarte „Komponenten der Datenansicht“](assets/template-dataview-context-label.png)

1. Wählen **[!UICONTROL im Dropdown]** Menü Kontextbeschriftungen die Kontextbeschriftung aus, die denselben Namen wie die fehlende Komponente hat.

1. Wählen Sie **[!UICONTROL Speichern und fortfahren]** aus.

1. Wiederholen Sie für jede fehlende Komponente den Prozess des Hinzufügens der entsprechenden Kontextbeschriftung zu einer Komponente in der Datenansicht.


## Zugriff auf eine Unternehmensvorlage

Wie bei Vorlagen, die vom Adobe bereitgestellt werden, können Benutzende in der Organisation auf Vorlagen zugreifen, die Administratoren erstellen.

Informationen zum Zugriff auf eine Unternehmensvorlage finden Sie unter [Zugriff auf und Ausführen einer Vorlage](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) unter [Verwenden von Vorlagen](/help/analysis-workspace/templates/use-templates.md).
