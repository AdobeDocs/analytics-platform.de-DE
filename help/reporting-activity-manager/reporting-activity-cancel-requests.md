---
title: Abbrechen von Berichtsanforderungen im Reporting Activity Manager
description: Erfahren Sie, wie Sie Kapazitätsprobleme bei Spitzen während der Berichterstellung mit Reporting Activity Manager diagnostizieren und beheben können.
solution: Customer Journey Analytics
feature: Basics
exl-id: 87da2447-f114-432a-9f63-e660c2541d0f
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 12%

---

# Abbrechen von Berichtsanforderungen im Reporting Activity Manager

Die [!UICONTROL Reporting Activity Manager] ermöglicht es Administratoren, Berichtsanforderungen schnell zu diagnostizieren und abzubrechen, um Probleme mit der Berichtskapazität während Spitzenzeiten der Berichterstellung zu beheben.

Beachten Sie beim Abbrechen von Berichtsanforderungen Folgendes:

* Sie können bestimmte Anforderungen abbrechen, alle Anforderungen eines bestimmten Benutzers abbrechen oder alle Anforderungen im Zusammenhang mit einem bestimmten Projekt abbrechen.

* Wenn Sie Anforderungen abbrechen, können Sie auch nachfolgende Anforderungen für einen bestimmten Zeitraum einschränken.

  Wenn Sie eine nachfolgende Anforderung einschränken, wird die Aktion im [Auditprotokoll](/help/privacy/audit-log.md) mit dem Aktionsnamen EMBARGO.

* Sie können eine Anforderung nicht abbrechen, wenn die Variable [!UICONTROL **Benutzer**] -Spalte einer Anforderung wird als [!UICONTROL **Nicht erkannt**]. In diesem Fall bedeutet dies, dass sich der Benutzer in einem Anmeldeunternehmen befindet, für das Sie keine Administratorberechtigungen haben.

Weitere Informationen zum Reporting Activity Manager, einschließlich der wichtigsten Vorteile und Berechtigungsanforderungen, finden Sie unter [Übersicht über die Berichterstellung in Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md).

## Bestimmte Anforderungen abbrechen

Sie können einzelne Anforderungen abbrechen, die eine große Menge an Berichtskapazität beanspruchen. Wenn Sie eine Anforderung abbrechen, können Sie sie für einen bestimmten Zeitraum weiter einschränken.

1. Gehen Sie unter Customer Journey Analytics zu **[!UICONTROL Instrumente]** > **[!UICONTROL Reporting Activity Manager]**.

1. Wählen Sie die Verbindung aus, bei der Sie Berichtsanfragen abbrechen möchten. <!--double-check this step-->

   Weitere Informationen zu den auf dieser Seite verfügbaren Daten finden Sie unter [Berichtsaktivität im Reporting Activity Manager anzeigen](/help/reporting-activity-manager/reporting-activity.md).

1. Wählen Sie die [!UICONTROL **Anforderungen**] und wählen Sie dann eine oder mehrere Anforderungen aus.

   <!-- add screenshot -->

1. Auswählen [!UICONTROL **Anforderungen abbrechen**].

   Die [!UICONTROL **Abbrechen _x_ Berichtsanforderungen**] angezeigt.

1. Im Feld Abbruchsnachricht wird die Nachricht angezeigt, die Benutzern angezeigt wird, wenn ihre Anforderungen abgebrochen werden. Eine Standardnachricht wird bereitgestellt. Sie können die Standardnachricht aktualisieren, um zusätzliche Details anzugeben.

1. (Optional) So beschränken Sie zukünftige Anforderungen für einen bestimmten Zeitraum:

   1. Aktivieren Sie die Option zum [!UICONTROL **Einschränken nachfolgender Anforderungen**].

      ![Anfrage &quot;Abbrechen 1&quot;mit der Meldung Einschränken der nachfolgenden ausgewählten Anforderungen und Abbruch .](assets/restrict-subsequent-requests.png)

   1. Wählen Sie aus den folgenden Optionen:

      | Option | Funktion |
      |---------|----------|
      | [!UICONTROL **Benutzer und Projekt**] | Benutzende, die mit den ausgewählten Anfragen verknüpft sind, werden vorübergehend von der Ausführung von Berichtsanfragen für die ausgewählten Projekte ausgeschlossen. |
      | [!UICONTROL **Benutzer**] | Benutzende, die mit den ausgewählten Anträgen verknüpft sind, können vorübergehend keine weiteren Reporting-Anfragen stellen. |
      | [!UICONTROL **Projekt**] | Projekte, die mit den ausgewählten Anfragen verknüpft sind, werden vorübergehend von allen Reporting-Anfragen ausgeschlossen. |
      | [!UICONTROL **Eingeschränkt für**] | Wählen Sie aus, wie lange Anforderungen eingeschränkt sein sollen. Sie können zwischen 1 Minute (Standard), 5 Minuten, 10 Minuten, 15 Minuten oder 30 Minuten wählen. <!-- double-check this --><p>Sie können eine Beschränkung nicht frühzeitig entfernen, nachdem sie festgelegt wurde.</p> |

      {style="table-layout:auto"}

1. Auswählen [!UICONTROL **Mit Abbruch fortfahren**].

   In Analysis Workspace wird eine Benachrichtigung angezeigt, die Benutzer darüber informiert, dass die Anfrage abgebrochen wurde. Weitere Informationen dazu, wie dies in Analysis Workspace angezeigt wird, finden Sie unter [Erlebnis beim Zugriff auf einen abgebrochenen Bericht](#experience-when-users-access-a-cancelled-report).

## Abbrechen von Anforderungen durch den Benutzer

Sie können alle Anforderungen abbrechen, die mit einem oder mehreren Benutzern verknüpft sind. Beim Abbrechen von Anforderungen, die mit einem Benutzer verknüpft sind, können Sie die Anforderungen dieses Benutzers für einen bestimmten Zeitraum weiter einschränken.

1. Gehen Sie unter Customer Journey Analytics zu **[!UICONTROL Instrumente]** > **[!UICONTROL Reporting Activity Manager]**.

1. Wählen Sie die Verbindung aus, bei der Sie Berichtsanfragen abbrechen möchten. <!--double-check this step-->

   Weitere Informationen zu den auf dieser Seite verfügbaren Daten finden Sie unter [Berichtsaktivität im Reporting Activity Manager anzeigen](/help/reporting-activity-manager/reporting-activity.md).

1. Wählen Sie die [!UICONTROL **Benutzer**] und wählen Sie einen oder mehrere Benutzer aus.

   <!-- add screenshot -->

1. Auswählen [!UICONTROL **Anforderungen abbrechen**].

   Die [!UICONTROL **Abbrechen _x_ Berichtsanforderungen von x Benutzern**] angezeigt.

1. Im Feld Abbruchsnachricht wird die Nachricht angezeigt, die Benutzern angezeigt wird, wenn ihre Anforderungen abgebrochen werden. Eine Standardnachricht wird bereitgestellt. Sie können die Standardnachricht aktualisieren, um zusätzliche Details anzugeben.

1. (Optional) So beschränken Sie zukünftige Anforderungen für einen bestimmten Zeitraum:

   1. Aktivieren Sie die Option zum [!UICONTROL **Einschränken nachfolgender Anforderungen**]

      ![Anfrage &quot;Abbrechen 1&quot;mit der ausgewählten Option Folgende Anforderungen durch Benutzer beschränken .](assets/restrict-subsequent-requests-user.png)

   1. Wählen Sie aus den folgenden Optionen:

      | Option | Funktion |
      |---------|----------|
      | [!UICONTROL **Benutzer und Projekt**] | Ausgewählte Benutzende können vorübergehend keine Berichtsanfragen für die verknüpften Projekte stellen. <p>Dies ist die am wenigsten restriktive Option.</p> |
      | [!UICONTROL **Benutzer**] | Ausgewählte Benutzende können vorübergehend keine Berichtsanfragen stellen. |
      | [!UICONTROL **Projekt**] | Projekte, die mit den ausgewählten Benutzenden verbunden sind, werden von allen Berichtsanfragen ausgeschlossen, die von anderen Benutzenden gestellt werden. |
      | [!UICONTROL **Eingeschränkt für**] | Wählen Sie aus, wie lange Anforderungen eingeschränkt sein sollen. Sie können zwischen 1 Minute (Standard), 5 Minuten, 10 Minuten, 15 Minuten oder 30 Minuten wählen. <!--double-check this--> <p>Sie können eine Beschränkung nicht frühzeitig entfernen, nachdem sie festgelegt wurde.</p> |

      {style="table-layout:auto"}

1. Auswählen [!UICONTROL **Mit Abbruch fortfahren**].

   In Analysis Workspace wird eine Benachrichtigung angezeigt, die Benutzer darüber informiert, dass die Anfrage abgebrochen wurde. Weitere Informationen dazu, wie dies in Analysis Workspace angezeigt wird, finden Sie unter [Erlebnis beim Zugriff auf einen abgebrochenen Bericht](#experience-when-users-access-a-cancelled-report).

## Anforderungen nach Projekt abbrechen

Sie können alle Anforderungen abbrechen, die mit einem oder mehreren Projekten verknüpft sind. Beim Abbrechen von Anforderungen, die mit einem Projekt verknüpft sind, können Sie die mit diesem Projekt verknüpften Anforderungen für einen bestimmten Zeitraum weiter einschränken.

1. Gehen Sie unter Customer Journey Analytics zu **[!UICONTROL Instrumente]** > **[!UICONTROL Reporting Activity Manager]**.

1. Wählen Sie die Verbindung aus, bei der Sie Berichtsanfragen abbrechen möchten. <!--double-check this step-->

   Weitere Informationen zu den auf dieser Seite verfügbaren Daten finden Sie unter [Berichtsaktivität im Reporting Activity Manager anzeigen](/help/reporting-activity-manager/reporting-activity.md).

1. Wählen Sie die [!UICONTROL **Projekte**] und wählen Sie ein oder mehrere Projekte aus.

   <!-- add screenshot -->

1. Auswählen [!UICONTROL **Anforderungen abbrechen**].

   Die [!UICONTROL **Abbrechen _x_ Berichtsanforderungen aus x Projekten**] angezeigt.

1. Im Feld Abbruchsnachricht wird die Nachricht angezeigt, die Benutzern angezeigt wird, wenn ihre Anforderungen abgebrochen werden. Eine Standardnachricht wird bereitgestellt. Sie können die Standardnachricht aktualisieren, um zusätzliche Details anzugeben.

1. (Optional) So beschränken Sie zukünftige Anforderungen für einen bestimmten Zeitraum:

   1. Aktivieren Sie die Option zum [!UICONTROL **Einschränken nachfolgender Anforderungen**].

      ![Anfrage &quot;Abbrechen 1&quot;mit nachfolgenden Anforderungen nach Projekt beschränken](assets/restrict-subsequent-requests-project.png)

   1. Wählen Sie aus den folgenden Optionen:

      | Option | Funktion |
      |---------|----------|
      | [!UICONTROL **Benutzer und Projekt**] | Ausgewählte Projekte werden vorübergehend von allen Berichtsanfragen der verknüpften Benutzenden ausgeschlossen.<p>Dies ist die am wenigsten restriktive Option.</p> |
      | [!UICONTROL **Benutzer**] | Benutzende, die mit den ausgewählten Projekten verknüpft sind, können vorübergehend keine weiteren Berichtsanfragen stellen. |
      | [!UICONTROL **Projekt**] | Ausgewählte Projekte sind vorübergehend von jeglichen Berichtsanfragen eines Benutzers ausgeschlossen. |
      | [!UICONTROL **Eingeschränkt für**] | Wählen Sie aus, wie lange Anforderungen eingeschränkt sein sollen. Sie können zwischen 1 Minute (Standard), 5 Minuten, 10 Minuten, 15 Minuten oder 30 Minuten wählen. <!--double-check this--> <p>Sie können eine Beschränkung nicht frühzeitig entfernen, nachdem sie festgelegt wurde.</p> |

      {style="table-layout:auto"}

1. Auswählen [!UICONTROL **Mit Abbruch fortfahren**].

   In Analysis Workspace wird eine Benachrichtigung angezeigt, die Benutzer darüber informiert, dass die Anfrage abgebrochen wurde. Weitere Informationen dazu, wie dies in Analysis Workspace angezeigt wird, finden Sie unter [Erlebnis beim Zugriff auf einen abgebrochenen Bericht](#experience-when-users-access-a-cancelled-report).

## Anforderungen durch Anwendung abbrechen

Sie können alle Anforderungen abbrechen, die mit einer oder mehreren Anwendungen verknüpft sind. Beim Abbrechen von mit einer Anwendung verknüpften Anforderungen können Sie die mit dieser Anwendung verknüpften Anforderungen für einen bestimmten Zeitraum weiter einschränken.

Zu den Anwendungen gehören:

* Analysis Workspace-Benutzeroberfläche
* Geplante Projekte im Workspace
* Report Builder
* Builder-Benutzeroberflächen: Segment, berechnete Metriken, Anmerkungen, Audiences usw.
* API-Aufrufe von der 2.0-API
* Intelligente Warnhinweise
* Vollständiger Tabellenexport
* Für alle Links freigeben
* Geführte Analyse
* Jede andere Anwendung, die die Analytics-Reporting-Engine abfragt

So brechen Sie Anfragen nach Anwendung ab:

1. Gehen Sie unter Customer Journey Analytics zu **[!UICONTROL Instrumente]** > **[!UICONTROL Reporting Activity Manager]**.

1. Wählen Sie die Verbindung aus, bei der Sie Berichtsanfragen abbrechen möchten. <!--double-check this step-->

   Weitere Informationen zu den auf dieser Seite verfügbaren Daten finden Sie unter [Berichtsaktivität im Reporting Activity Manager anzeigen](/help/reporting-activity-manager/reporting-activity.md).

1. Wählen Sie die [!UICONTROL **Anwendungen**] und wählen Sie eine oder mehrere Anwendungen aus.

   <!-- add screenshot -->

1. Auswählen [!UICONTROL **Anforderungen abbrechen**].

   Die [!UICONTROL **Abbrechen _x_ Berichtsanforderungen aus x Projekten**] angezeigt.

1. Im Feld Abbruchsnachricht wird die Nachricht angezeigt, die Benutzern angezeigt wird, wenn ihre Anforderungen abgebrochen werden. Eine Standardnachricht wird bereitgestellt. Sie können die Standardnachricht aktualisieren, um zusätzliche Details anzugeben.

1. (Optional) So beschränken Sie zukünftige Anforderungen für einen bestimmten Zeitraum:

   1. Aktivieren Sie die Option zum [!UICONTROL **Einschränken nachfolgender Anforderungen**]

      ![Anfrage &quot;Abbrechen 1&quot;mit der ausgewählten Option Folgende Anforderungen durch Anwendung beschränken .](assets/restrict-subsequent-requests-application.png)

   1. Wählen Sie aus den folgenden Optionen:

      | Option | Funktion |
      |---------|----------|
      | [!UICONTROL **Benutzer und Projekt**] | Ausgewählte Anwendungen sind vorübergehend auf Berichterstellungsanforderungen der assoziierten Benutzer und Projekte beschränkt.<p>Dies ist die am wenigsten restriktive Option.</p> |
      | [!UICONTROL **Benutzer**] | Benutzer, die mit den ausgewählten Anwendungen verknüpft sind, können keine Berichterstellungsanfragen stellen. |
      | [!UICONTROL **Projekt**] | Projekte, die mit den ausgewählten Anwendungen verknüpft sind, sind auf alle Berichterstellungsanforderungen eines Benutzers beschränkt. |
      | [!UICONTROL **Eingeschränkt für**] | Wählen Sie aus, wie lange Anforderungen eingeschränkt sein sollen. Sie können zwischen 1 Minute (Standard), 5 Minuten, 10 Minuten, 15 Minuten oder 30 Minuten wählen. <!--double-check this--> <p>Sie können eine Beschränkung nicht frühzeitig entfernen, nachdem sie festgelegt wurde.</p> |

      {style="table-layout:auto"}

1. Auswählen [!UICONTROL **Mit Abbruch fortfahren**].

   In der Anwendung wird eine Benachrichtigung angezeigt (z. B. in Analysis Workspace), in der Benutzer darüber informiert werden, dass die Anfrage abgebrochen wurde. Weitere Informationen dazu, wie dies in Analysis Workspace angezeigt wird, finden Sie unter [Erlebnis beim Zugriff auf einen abgebrochenen Bericht](#experience-when-users-access-a-cancelled-report).

## Erlebnis beim Zugriff auf einen abgebrochenen Bericht

In Analysis Workspace sehen Benutzer die folgenden Meldungen, wenn sie versuchen, auf einen Bericht oder eine Visualisierung zuzugreifen, der bzw. die von einem Abbruch betroffen ist:

### Nachricht im Projekt

Wenn Benutzer versuchen, auf ein Projekt zuzugreifen, das von einem Abbruch betroffen ist, wird ihnen eine Meldung angezeigt, dass der Bericht vorübergehend eingeschränkt ist:

![Nachricht über die Projektabsage](assets/workspace-canceled-report.png)

### Meldung bei der Visualisierung

Wenn Benutzer versuchen, auf eine Visualisierung zuzugreifen, die von einem Abbruch betroffen ist, wird ihnen eine Meldung angezeigt, dass die Datenverarbeitung für den Bericht vorübergehend eingeschränkt ist:

![Meldung über den Abbruch einer Visualisierung](assets/workspace-cancelled-visualization.png)
