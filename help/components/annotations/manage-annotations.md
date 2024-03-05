---
title: Verwalten von Anmerkungen
description: Verwalten von Anmerkungen in Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '692'
ht-degree: 100%

---

# Verwalten von Anmerkungen

Die Anmerkungsverwaltung ([!UICONTROL Komponenten] > [!UICONTROL Anmerkungen]) bietet viele Möglichkeiten zum Verwalten von Anmerkungen, z. B. Freigeben, Filtern, Markieren, Genehmigen, Kopieren, Löschen und Markieren als Favorit.

Die [!UICONTROL Anmerkungsverwaltung] zeigt Ihnen alle Anmerkungen an, die Ihnen gehören und für alle Ihre Projekte gelten und die für Sie freigegeben wurden.

>[!NOTE]
>
>[!UICONTROL Anmerkungen], die Sie nur für ein bestimmtes Projekt erstellt haben, werden nicht in der Anmerkungsverwaltung angezeigt.

## Benutzeroberfläche der Anmerkungsverwaltung

![Anmerkungsoptionen wie das Freigeben, Tagging oder Kopieren, die im nächsten Abschnitt beschrieben werden.](assets/annotation-mgr.png)

| UI-Element | Beschreibung |
| --- | --- | 
| [!UICONTROL Titel und Beschreibung] | Werden durch den Anmerkungsgenerator bereitgestellt. Klicken Sie auf den Titel-Link, um den Titel und die Beschreibung zu bearbeiten. Dadurch gelangen Sie zurück zum Anmerkungsgenerator. |
| [!UICONTROL Datenansicht] | Die Datenansicht(en), für die diese Anmerkung gilt. |
| [!UICONTROL Inhaber] | Zeigt an, wer Inhaber der Anmerkung ist. Wenn Sie kein Administrator sind, können Sie nur Anmerkungen sehen, deren Inhaber Sie sind, sowie Anmerkungen, die für Sie freigegeben wurden. |
| [!UICONTROL Angewendeter Datumsbereich] | Das Datum oder der Datumsbereich, für das bzw. den diese Anmerkung gilt. |
| [!UICONTROL Freigegeben für] | Listet auf, für wie viele Einzelpersonen oder Gruppen Sie die Anmerkung freigegeben haben. Klicken Sie hier, um weitere Details anzuzeigen. |
| [!UICONTROL Änderungsdatum] | Zeigt das Datum und die Uhrzeit der letzten Änderung der Anmerkung an. |

{style="table-layout:auto"}

## Bearbeiten von Anmerkungen

Sie können eine Anmerkung bearbeiten, indem Sie Datumsbereiche, Farben oder den Umfang anpassen. Sie können ebenfalls festlegen, ob die Anmerkung für alle Datenansichten oder Projekte gilt oder nicht. Anmerkungen können auf zwei Arten bearbeitet werden:

* Bewegen Sie in einem Liniendiagramm den Mauszeiger über die Anmerkung und klicken Sie im Popover auf das Stiftsymbol.

* Klicken Sie in der [!UICONTROL Anmerkungsverwaltung] auf den Titel der Anmerkung.

Beide dieser Optionen bringen Sie zum Anmerkungsgenerator zurück. Dort können Sie die erforderlichen Anpassungen vornehmen und die neue Version speichern.

## Freigeben von Anmerkungen

Beachten Sie Folgendes beim Freigeben von Anmerkungen oder Arbeiten mit Anmerkungen, die für Sie freigegeben wurden:

* Angenommen, Sie erstellen ein Projekt mit nur projektbezogenen Anmerkungen und geben das Projekt dann für einen anderen Benutzer frei. Diese Anmerkungen werden angezeigt, können jedoch von niemandem bearbeitet oder gelöscht werden, für den Sie das Projekt freigeben.

* Wenn Sie eine Anmerkung speichern und direkt für einen Benutzer freigeben, kann dieser die Anmerkung nur bearbeiten/löschen, wenn er über Administratorrechte verfügt.

* Also: Wenn das Projekt für Sie freigegeben wurde, wird es nur in diesem Projekt angezeigt. Wenn die Anmerkung direkt für Sie freigegeben wird, wird sie in allen Projekten angezeigt, in denen diese Anmerkung angezeigt werden kann.

## Anmerkungen und Zeitzonen

Alle Anmerkungen werden mit einem Zeitstempel erstellt, jedoch ohne Stunden- oder Zeitzoneninformationen. Zum Zeitpunkt der Berichterstellung wird immer die Zeitzone der Datenansicht des Bedienfelds angewendet. Daher wird eine für den 1. Weihnachtsfeiertag erstellte Anmerkung immer am 25. Dezember erstellt, unabhängig davon, in welcher Datenansichts-Zeitzone Sie sich befinden.

Ein weiteres Beispiel ist der Neujahrstag. Zu Beginn des neuen Jahres werden jede Stunde von einer anderen Zeitzone Feuerwerke ausgelöst. Um 22:00 Uhr US Mountain Time werden an der US-Ostküste Feuerwerke ausgelöst, weil es dort bereits 24:00 Uhr Eastern Time ist.

## Sonstige Aktionen mit Anmerkungen

Mit der Anmerkungsverwaltung können Administratoren Anmerkungen bearbeiten, hinzufügen, taggen, löschen, umbenennen, genehmigen, kopieren, exportieren und filtern. Dies ist für Nicht-Admin-Benutzer nicht sichtbar.

Wählen Sie einfach eine oder mehrere der Anmerkungen aus, und die Task-Leiste wird angezeigt.

| Aufgabe | Beschreibung |
| --- | --- |
| Hinzufügen | Sie gelangen zum Anmerkungsgenerator, in dem Sie neue Anmerkungen erstellen können. |
| Tag | Alle Benutzer können Tags für Anmerkungen erstellen und ein oder mehrere Tags auf eine Anmerkung anwenden. Sie sehen Tags jedoch nur für die Filter, deren Inhaberin bzw. Inhaber Sie sind. Welche Arten von Tags sollten Sie erstellen? Hier finden Sie einige Vorschläge für nützliche Tags:<ul><li>Auf Teamnamen basierende Tags wie Social Marketing, Mobile Marketing</li><li>Projekt-Tags (Analyse-Tags) wie Entrypage-Analyse</li><li>Kategorie-Tags: Männer, Region</li><li>Workflow-Tags: Kuratiert für (einen bestimmten Geschäftsbereich), Genehmigt</li></ul> |
| Löschen | Durch das Löschen einer Anmerkung wird sie aus jedem Projekt in Ihrer Organisation entfernt. |
| Umbenennen | Beim Umbenennen einer Anmerkung wird sie in allen Projekten, auf die sie angewendet wurde, umbenannt. |
| Kopieren | Erstellt eine eigenständige Kopie mit einer eigenen neuen Anmerkungs-ID, jedoch mit demselben Namen und derselben Definition. |
| In CSV exportieren | Exportiert die Anmerkungsdefinition in eine CSV-Datei. |
| Filter (linke Leiste) | Filtern Sie nach Tags, Datenansicht, Inhaberinnen bzw. Inhabern und anderen Filtern („Meine“, „Genehmigt“, „Favoriten“, „Für mich freigegeben“ und „Alle anzeigen“). |

{style="table-layout:auto"}
