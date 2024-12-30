---
description: Verwalten vorhandener Exporte
keywords: Analysis Workspace
title: Verwalten von Exporten
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 6f8a43acfba23d6faeff078873742315f1506699
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 4%

---

# Verwalten von Exporten

Nachdem Sie eine vollständige Tabelle exportiert haben, wie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben, sind die Exporte auf der Registerkarte [!UICONTROL Exporte] auf der Seite [!UICONTROL Exporte] verfügbar.

Sie können nur die von Ihnen erstellten Exporte sehen.

## Filtern und Suchen nach Exporten

Um die benötigten Informationen zu finden, können Sie entweder die Liste der Exporte filtern oder nach einem Export suchen.

### Filtern der Exportliste

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die [!UICONTROL **Exporte**] aus.

1. Wählen Sie das Symbol **Filter** aus.

   <!--add screenshot -->

   Sie können nach den folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Kontotyp**] | Der Kontotyp, mit dem der Export verknüpft ist. Die folgenden Kontotypen sind verfügbar: <ul><li>[!UICONTROL **AEP-Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3-Rollen-ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Status**] | Der Status des Exports Die folgenden Status sind verfügbar: <ul><li>[!UICONTROL **Aktiv**]: Gibt an, dass ein geplanter Export noch nicht abgelaufen ist oder dass ein einmaliger Export noch nicht abgeschlossen ist. </li><li>[!UICONTROL **Abgeschlossen**]: Gibt an, dass ein Export erfolgreich exportiert wurde. Für geplante Exporte bedeutet dies, dass der Zeitplan abgelaufen ist.</li><li>[!UICONTROL **Fehlgeschlagen**]<p>Die folgenden Situationen können zu einem fehlgeschlagenen Export führen. Bewegen Sie den Mauszeiger über [!UICONTROL **Status**] Fehlgeschlagen“, um Details zum Fehler anzuzeigen. <ul><li>Geplanter Exportablauf</li><li>Zeilenbeschränkung für geplanten Export erreicht </li></ul> </p></li></ul> |
   | [!UICONTROL **Häufigkeit**] | Wie oft der Export stattfindet. Die folgenden Häufigkeiten sind verfügbar: <ul><li>[!UICONTROL **Einmalig**]</li><li>[!UICONTROL **Täglich**]</li><li>[!UICONTROL **Wöchentlich**]</li><li>[!UICONTROL **Monatlich**]</li><li>[!UICONTROL **Jährlich**]</li></ul> |

   {style="table-layout:auto"}

### Nach Exporten suchen

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie die [!UICONTROL **Exporte**] aus.

1. Geben Sie im Suchfeld zunächst alle Informationen ein, die mit dem gesuchten Export verknüpft sind. Sie können nach Daten aus jeder in der Tabelle verfügbaren Spalte suchen.

## Bearbeiten eines Exports

Sie können die Eigenschaften, das Format, die Planung und die Standortinformationen eines Exports bearbeiten.

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Aktivieren [!UICONTROL **auf der Registerkarte**] Exporte“ das Kontrollkästchen neben dem Export, den Sie bearbeiten möchten.

   Diese Option ist nicht verfügbar, wenn mehrere Exporte ausgewählt werden.

1. Wählen Sie [!UICONTROL **Bearbeiten**] aus.

   Das [!UICONTROL **Exportieren der vollständigen Tabelle**] Dialogfeld wird angezeigt.

1. Aktualisieren Sie eine der verfügbaren Optionen. Informationen zu den einzelnen Optionen finden Sie unter [Exportieren von vollständigen Tabellen aus Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) in [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md).

## Duplizieren eines Exports

Ein vorhandener Export kann dupliziert werden.

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Aktivieren [!UICONTROL **auf der Registerkarte**] Exporte“ das Kontrollkästchen neben dem Export, den Sie duplizieren möchten.

   Diese Option ist nicht verfügbar, wenn mehrere Exporte ausgewählt werden.

1. Wählen Sie [!UICONTROL **Duplizieren**] aus.

   Es wird ein Duplikat des Exports erstellt. Der Name des neuen Exports entspricht dem Namen des ursprünglichen Exports, wobei _[!UICONTROL - Kopieren]_ an den Dateinamen angehängt wird.

1. (Optional) [Bearbeiten Sie den neuen Export](#edit-an-export) einschließlich des Dateinamens und aller anderen Eigenschaften, die Sie ändern möchten.

## Manuelles Starten eines Exports

Sie können den Export manuell initiieren, entweder für einen geplanten Export oder einen einmaligen Export, der zuvor abgeschlossen wurde.

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Aktivieren [!UICONTROL **auf der Registerkarte**] Exporte“ das Kontrollkästchen neben dem Export, den Sie ausführen möchten.

   Diese Option ist nicht verfügbar, wenn mehrere Exporte ausgewählt werden.

1. Wählen Sie [!UICONTROL **Jetzt exportieren**].

## Markieren eines Exports

Wenn Sie Tags auf einen Export anwenden, können Sie diese Tags in der Spalte [!UICONTROL Tags] auf der Seite [!UICONTROL Exporte] anzeigen. Weitere Informationen finden [ unter ](#configure-columns)Konfigurieren von Spalten“.

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Aktivieren Sie auf [!UICONTROL **Registerkarte**] das Kontrollkästchen neben einem oder mehreren Exporten, die Sie mit Tags versehen möchten.

1. Wählen Sie [!UICONTROL **Tags bearbeiten**] aus.

1. Geben [!UICONTROL **im Dialogfeld „Tag-**]&quot; den Namen eines Tags ein, um ein neues Tag zu erstellen, oder wählen Sie ein vorhandenes Tag aus dem Dropdown-Menü aus.

   Alle gemeinsamen Tags zwischen den ausgewählten Exporten werden im Tag-Dialogfeld angezeigt. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Wählen Sie [!UICONTROL **Tags anwenden**] aus.

## Löschen eines Exports

Sie können Exporte auf der Seite Exporte löschen. Geplante Exporte, die gelöscht werden, werden nicht mehr gesendet.

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Aktivieren [!UICONTROL **auf der Registerkarte**] Exporte“ das Kontrollkästchen neben einem oder mehreren Exporten, die Sie löschen möchten.

1. Klicken Sie [!UICONTROL **Löschen**] und wählen Sie dann [!UICONTROL **Löschen**], wenn die Bestätigungsmeldung angezeigt wird.

## Spalten auf der Seite [!UICONTROL Exporte] konfigurieren

Sie können Spalten auf der Registerkarte [!UICONTROL Exporte] hinzufügen oder entfernen, um zu konfigurieren, welche Informationen angezeigt werden.

Spaltenüberschrift auswählen, um die Exporte nach dieser Spalte zu sortieren. Standardmäßig werden Exporte nach Datum und Uhrzeit der letzten Änderung des Exports sortiert.

1. Wählen Sie beim Customer Journey Analytics [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**] aus.

1. Wählen Sie auf [!UICONTROL **Registerkarte**] das Symbol **Tabelle anpassen** (Tabelle ![) ](assets/customize-table-icon.png) oben rechts auf der Seite [!UICONTROL Exporte] aus.

   Die folgenden Spalten sind verfügbar:

   | Verfügbare Spalte | Beschreibung |
   |---------|----------|
   | Name | Der Name des Exports Benutzende geben Exporten bei ihrer Erstellung einen Namen, wie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben. |
   | ID | Die ID, die dem Export bei seiner Erstellung automatisch zugewiesen wird. <!-- True? --> |
   | Name der Datenansicht | Der Name der dem Export zugeordneten Datenansicht. Benutzerinnen und Benutzer können die Datenansicht auswählen, wenn sie den Export erstellen, wie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](/help/analysis-workspace/export/export-cloud.md) beschrieben. |
   | Status | Der Status des Exports Verfügbare Status sind [!UICONTROL Aktiv], [!UICONTROL Abgeschlossen] und [!UICONTROL Fehlgeschlagen].<p> **Hinweis:** Informationen zur Fehlerbehebung bei fehlgeschlagenen Exporten finden Sie unter [Fehlerbehebung bei fehlgeschlagenen Exporten](/help/components/exports/troubleshoot-exports.md).</p> |
   | Tags | Zeigt alle Tags an, die auf den Export angewendet wurden. Informationen zum Anwenden von Tags auf einen Export finden Sie unter [Taggen eines ](#tag-an-export)). |
   | Tabellengröße (zuletzt gesendet) | Die Größe des Exports beim letzten Versand. |
   | Erstellt von | Der Benutzer, der den Export erstellt hat. |
   | Erstellt | Datum und Uhrzeit der Erstellung des Exports <!-- true? --> |
   | Standort | Der Speicherort des Kontos, in das die Daten exportiert wurden. |
   | Konto | Das Konto, in das die Daten exportiert wurden. |
   | Häufigkeit | Die Häufigkeit, mit der der Export gesendet wird. Verfügbare Optionen sind [!UICONTROL Einmal], [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich nach Wochentag], [!UICONTROL Monatlich nach Tag des Monats], [!UICONTROL Jährlich nach Tag des Monats] und [!UICONTROL Jährlich nach spezifischem Datum]. |
   | Gesendet um | Die Zeit, zu der der Export gesendet wurde. |
   | Zuletzt gesendet | Das letzte Mal, dass der Export gesendet wurde. |
   | Zuletzt geändert | Das letzte Mal, dass der Export geändert wurde. Die Elemente auf der Seite Exporte werden standardmäßig nach dieser Spalte sortiert. |
   | Kontotyp | Der Typ des Cloud-Kontos, in das die Daten exportiert wurden. Verfügbare Kontotypen sind [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] und [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. Stellen Sie sicher, dass alle Spalten, die angezeigt werden sollen, ausgewählt sind. Ausgewählte Spalten werden auf der Seite Exporte angezeigt und enthalten die entsprechenden Informationen.
