---
title: Komponenteneinstellungen
description: Anzeigen der wichtigsten Einstellungen für eine Datenansichtskomponente
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 1158064d46e09435ec2507c47e6e484306ac5a53
workflow-type: ht
source-wordcount: '570'
ht-degree: 100%

---

# Komponenteneinstellungen {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_settings"
>title="Komponenteneinstellungen"
>abstract="Zeigen Sie den Namen, die Beschreibung und andere Einstellungen einer Komponente an und konfigurieren Sie sie.<br/><br/>**Parameter **<br/>**Komponente in Berichten verbergen**: Wenn Sie dieses Kontrollkästchen aktivieren, wird diese Komponente bei der Berichterstellung für Benutzende ohne Administratorrechte ausgeblendet. Admins können weiterhin darauf zugreifen, indem sie in einem Workspace-Projekt **[!UICONTROL Alle Komponenten zeigen]** auswählen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_contextlabels"
>title="Kontext-Labels"
>abstract="Das Entfernen eines Kontext-Labels kann sich auf bestimmte Bedienfelder oder Berichte auswirken, bei denen die Komponente erforderlich ist."

<!-- markdownlint-enable MD034 -->


Die folgenden Informationen beschreiben die Einstellungen, die eine Datenansichtskomponente verwendet.

![Die in diesem Abschnitt beschriebenen Komponenteneinstellungen](../assets/component-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Typ der Komponente] | Erforderlich. Ermöglicht es Ihnen, eine Komponente von Metrik in Dimension zu ändern oder umgekehrt. Durch Änderung dieser Dropdown-Auswahl wird die Komponente in den entsprechenden eingeschlossenen Komponentenbereich verschoben. |
| [!UICONTROL Name der Komponente] | Erforderlich. Hier können Sie den benutzerfreundlichen Namen angeben, der in Analysis Workspace angezeigt wird. Sie können eine Komponente umbenennen, um ihr einen spezifischen Namen für die Datenansicht zu geben. |
| [!UICONTROL Beschreibung] | Optional, jedoch empfohlen. Stellt Informationen über die Komponente für andere Benutzer bereit. |
| [!UICONTROL Tags] | Optional. Ermöglicht das Taggen der Komponente mit benutzerdefinierten oder vordefinierten Tags zur einfacheren Suche/Filterung in der Analysis Workspace-Benutzeroberfläche. |
| [!UICONTROL Kontextbeschriftungen] | Optional. Eine Dropdown-Liste der verfügbaren systemdefinierten Beschriftungen, die auf eine Komponente angewendet werden können. Diese Labels können erforderlich sein, um einen Komponentensatz zu definieren, den Sie für Berichte zum Experimentieren mit dem [Bedienfeld „Experimentieren“](/help/analysis-workspace/c-panels/experimentation.md) in Analysis Workspace-Projekten verwenden können. Weitere Informationen finden Sie unter [Integrieren mit Journey Optimizer](/help/integrations/ajo.md#data-view) und [Zielgruppenberichte](/help/integrations/at.md). |
| [!UICONTROL Schemafeldname] | Der Name des Schemafelds. |
| [!UICONTROL Typ des Datensatzes] | Erforderlich. Ein nicht bearbeitbares Feld, das anzeigt, von welchem Datensatztyp (Ereignis, Suche oder Profil) die Komponente stammt. |
| [!UICONTROL Datensatz] | Ein nicht bearbeitbares Feld, das anzeigt, aus welchem Datensatz die Komponente stammt. Dieses Feld kann mehrere Datensätze enthalten. |
| [!UICONTROL Schema-Typ] | Ein nicht bearbeitbares Feld, das den Datentyp der Komponente anzeigt. Sie können zwar einen beliebigen unterstützten Schemafeldtyp in Platform verwenden, jedoch werden in Customer Journey Analytics nicht alle Feldtypen unterstützt. Die folgenden Datentypen werden unterstützt: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` und `Boolean`. In Such-Datensätzen ist derzeit nur der Schemadatentyp `String` erlaubt. |
| [!UICONTROL Komponenten-ID] | Erforderlich. Die [Customer Journey Analytics-API](https://adobe.io/cja-apis/docs) verwendet dieses Feld, um auf die Komponente zu verweisen. Jede Komponente in einer Datenansicht muss eindeutig sein. Adobe generiert automatisch eine ID für jede Komponente. Sie können jedoch auf das Bearbeitungssymbol klicken und die Komponenten-ID ändern. Durch das Ändern der Komponenten-ID werden alle vorhandenen Workspace-Projekte, die diese Komponente enthalten, beschädigt. Während jede Komponente eine eindeutige ID in einer Datenansicht benötigt, können Sie dieselbe Komponenten-ID in anderen Datenansichten verwenden. Wenn Sie dieselbe Komponenten-ID in anderen Datenansichten verwenden, können Sie Workspace-Projekte über Datenansichten hinweg kompatibel machen. <br/>Bei profil- und suchbasierten Komponenten verfügt die Komponenten-ID über ein ID-Präfix, das auf der Datensatz-ID basiert (z. B.: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Wenn Sie eine profil- oder suchbasierte Komponente wie `person.name.firstName` in Ihrem Workspace-Projekt wiederverwenden und diese Komponente in verschiedenen Datenansichten konfigurieren möchten, stellen Sie sicher, dass Sie die Komponenten-ID in Ihren Datenansichten eindeutig umbenennen (z. B.: `myUniqueID.person.name.firstName`). |
| [!UICONTROL Path] | Erforderlich. Ein nicht bearbeitbares Feld, das den Schema-Pfad anzeigt, von dem die Komponente stammt. |
| [!UICONTROL Beschriftungen zur Datennutzung] | Alle Datennutzungsbezeichnungen, die dieser Komponente in Adobe Experience Platform zugewiesen wurden. [Weitere Informationen](/help/data-views/data-governance.md). |
| [!UICONTROL Komponente in Reports verbergen] | Ermöglicht das Kuratieren der Komponente aus der Datenansicht für Benutzer ohne Administratorrechte. Administratoren können weiterhin darauf zugreifen, indem sie in einem Analysis Workspace-Projekt auf [!UICONTROL Alle Komponenten anzeigen] klicken. |

{style="table-layout:auto"}

Hier finden Sie ein Video zu Komponenteneinstellungen in Datenansichten:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
