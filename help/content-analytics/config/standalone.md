---
title: Content Analytics konfigurieren (eigenständig)
description: Führt Sie durch die erforderlichen Schritte zum Konfigurieren von Content Analytics (eigenständig)
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 81e7488a91a99456cd950d367d9ff16ec7c1cb5a
workflow-type: tm+mt
source-wordcount: '1810'
ht-degree: 7%

---


# Eigenständige Konfiguration

>[!IMPORTANT]
>
>Dieses Konfigurationshandbuch richtet sich an Kunden, die das eigenständige Adobe Content Analytics-Paket lizenziert haben. Das Handbuch setzt voraus, dass Sie Customer Journey Analytics oder eine andere Experience Platform-Anwendung, die über die Funktionen und Möglichkeiten von Content Analytics hinausgeht, nicht verwendet haben bzw. planen, diese zu verwenden. Siehe [Konfigurieren von Content Analytics](configuration.md), wenn Sie Content Analytics als Teil einer bestehenden Customer Journey Analytics-Implementierung konfigurieren und verwenden möchten.
>

Diese Konfiguration führt Sie durch die Verwaltung, Konfiguration und Einrichtung aller Anwendungen, die für eine funktionierende (eigenständige **Content Analytics-** erforderlich sind. Diese Schritte bestehen aus:

1. **Konfigurieren Sie die Zugriffssteuerung und Berechtigungen** um die Content Analytics-Konfiguration und -Implementierung zu unterstützen.
1. **Richten Sie ein Schema und einen** ein, um das Modell (Schema) der Daten zu definieren, aus denen Sie Inhaltsanalyseeinblicke erfassen möchten, und um festzulegen, wo diese Daten (Datensatz) erfasst werden sollen.
1. **Einrichten eines Datenstroms**, um zu konfigurieren, wie Ihre erfassten Daten an den Datensatz weitergeleitet werden.
1. **Website-Tags verwenden** um Regeln und Datenelemente entsprechend den Daten in Ihrer Datenschicht auf Ihrer Website zu konfigurieren und sicherzustellen, dass Daten an den konfigurierten Datenstrom gesendet werden.
1. **Bereitstellen** in einer Testumgebung **und validieren** die Datenerfassung vor der Veröffentlichung in einer Produktionsumgebung.
1. **Richten Sie eine Verbindung** Ihrem Datensatz ein.
1. **Einrichten einer Datenansicht** um Metriken und Dimensionen zu definieren.
1. **Konfigurieren und Implementieren von Content Analytics**.
1. **Einrichten eines Projekts** um Ihre Content Analytics-Berichte und -Visualisierungen zu erstellen.

## Konfigurieren von Zugriffssteuerung und Berechtigungen

In diesem Abschnitt wird dokumentiert, welchen Zugriff Sie auf Produkte und Produktprofile benötigen und welche Berechtigungen zum Konfigurieren und Einrichten der eigenständigen Content Analytics erforderlich sind. Obwohl Sie nur an der Funktionalität von Content Analytics interessiert sind, benötigen Sie dennoch Zugriff und Berechtigungen für andere Experience Platform-Produkte, damit diese Funktion ordnungsgemäß funktioniert.

### Zugriffssteuerung

Die Zugriffssteuerung bestimmt, ob Sie Zugriff auf ein Experience Platform-Produkt haben.

Sie benötigen entweder einen System- oder einen Produktadministrator, um Sie als Administrator für ein Produkt oder ein Produktprofil hinzuzufügen. Ein Produktadministrator kann Sie nur als Administrator für das verwaltete Produkt (Profil) hinzufügen. Ein Systemadministrator kann Produktadministratoren zu jedem Produkt (Profil) hinzufügen.

>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Verwalten von Benutzern für ein Produktprofil](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} finden Sie ein Demovideo.


>[!ENDSHADEBOX]

Sie müssen Produktadministrator für die folgenden Produkte und Produktprofile für die eigenständige Content Analytics sein:

* Adobe Experience Platform
   * AEP-Default-All-Users (das Standardprofil für den Zugriff auf die Produktions-Sandbox)

* Adobe Experience Platform – Datenerfassung
   * Standardzugriff auf alle Datenerfassungen

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics (benutzerdefiniert)
   * Customer Journey Analytics (oder ein anderes standardmäßig bereitgestelltes Produktprofil)

Sie definieren den Produktadministratorzugriff über die Admin Console:

1. Zugriff auf [Admin Console](https://adminconsole.adobe.com).
1. Wählen Sie **[!UICONTROL Produkte]** aus.
1. Wählen Sie das spezifische Produkt aus.
1. Wählen Sie die Registerkarte **[!UICONTROL Administratoren]** aus.
1. Wählen **[!UICONTROL Administrator hinzufügen]** aus, um einen Administrator zum Produkt hinzuzufügen.
1. Geben Sie eine oder mehrere E-Mail- oder Benutzernamen im Dialogfeld **[!UICONTROL Produktadministratoren hinzufügen]** ein. Wählen Sie zum Speichern **[!UICONTROL Speichern]** aus.


Sie definieren den Produktprofil-Administratorzugriff über die Admin Console:

1. Zugriff auf [Admin Console](https://adminconsole.adobe.com).
1. Wählen Sie **[!UICONTROL Produkte]** aus.
1. Wählen Sie das spezifische Produkt aus. Stellen Sie sicher, dass Sie bereits Produktadministratorzugriff haben.
1. Wählen Sie **[!UICONTROL Produktprofile]** aus.
1. Wählen Sie das spezifische Produktprofil aus.
1. Wählen Sie die Registerkarte **[!UICONTROL Administratoren]** aus.
1. Wählen **[!UICONTROL Administrator hinzufügen]** aus, um dem Produktprofil einen Administrator hinzuzufügen.
1. Geben Sie eine oder mehrere E-Mail- oder Benutzernamen im Dialogfeld **[!UICONTROL Produktprofil-Administratoren hinzufügen]** ein. Wählen Sie zum Speichern **[!UICONTROL Speichern]** aus.


### Berechtigungen

Berechtigungen definieren, was Sie in einem Produkt tun können, sobald Sie Zugriff auf das Produkt haben.

Berechtigungen für Experience Platform definieren Sie in der [!UICONTROL Berechtigungen] und verwenden Sie die attributbasierte Zugriffssteuerung. Für Customer Journey Analytics definieren Sie Berechtigungen über die [!UICONTROL Admin Console].

#### Experience Platform

Die [!UICONTROL Berechtigungen] in Experience Platform basiert auf der Definition einer Rolle. Eine Rolle ist eine Sammlung von ressourcenbasierten Berechtigungen. In einer neuen bereitgestellten Umgebung sind zwei Standardrollen verfügbar: **[!UICONTROL Standardproduktion - Zugriff auf alle]**) und **[!UICONTROL Sandbox-]**.

Für Content Analytics müssen Sie überprüfen, ob diesen Rollen die folgenden Ressourcen und zugehörigen Berechtigungen hinzugefügt wurden:

* Standard-Zugriffsrolle für Produktion und alle

   * Datenerfassung
      * Anzeigen von Datenströmen
      * Verwalten von Datenströmen

   * Daten-Management
      * Anzeigen von Datensätzen
      * Verwalten von Datensätzen

   * Datenmodellierung
      * Anzeigen von Schemata
      * Verwalten von Schemata
      * Verwalten von Identitätsmetadaten


* Sandbox-Administratorrolle

   * Sandboxes
      * prod
      * (jede andere Sandbox, die Sie für Content Analytics verwenden möchten)

   * Sandbox-Verwaltung
      * Verwalten von Paketen
      * Verwalten von Sandboxes
      * Sandbox zurücksetzen
      * Sandbox anzeigen


In der Benutzeroberfläche „Berechtigungen“ können Sie sowohl Rollen als auch zugehörige Berechtigungen überprüfen. und welche Benutzenden zur Rolle gehören.

1. Zugriff auf Experience Platform für Ihr Unternehmen.
1. Wählen Sie im Begrüßungsbildschirm unter **[!UICONTROL Schnellzugriff]** die Option **[!UICONTROL Alle anzeigen]** aus.
1. Aktivieren Sie die Pin ![PinOn](/help/assets/icons/PinOn.svg) für **[!UICONTROL Berechtigungen]**, sodass **[!UICONTROL Berechtigungen]** in **[!UICONTROL Schnellzugriff]** für die zukünftige Verwendung verfügbar wird.
1. Wählen Sie **[!UICONTROL Berechtigungen]** aus.
1. Wählen Sie ![Benutzer](/help/assets/icons/User.svg) **[!UICONTROL Rollen]** aus.
1. Wählen Sie die spezifische Rolle aus, die Sie verifizieren möchten (z. B. **[!UICONTROL Standardproduktion - Alle]**). Wählen Sie **[!UICONTROL Alle anzeigen]** aus, um alle Berechtigungen anzuzeigen.
1. Im Bildschirm **[!UICONTROL Details]**:
   1. Überprüfen Sie die **[!UICONTROL Ressourcen]**, die unter **[!UICONTROL Berechtigungen]** aufgeführt sind.
   1. Überprüfen Sie die Sandbox-Namen in **[!UICONTROL Sandboxes]**.

   Um Aktualisierungen vorzunehmen, wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) **[!UICONTROL Bearbeiten]**.
   1. Um eine fehlende Ressource hinzuzufügen, wählen Sie **[!UICONTROL Ressourcenname]** ![Hinzufügen](/help/assets/icons/Add.svg) in der linken **[!UICONTROL Ressourcen]** > **[!UICONTROL Adobe Experience Platform]** aus.
   1. Um eine fehlende Berechtigung hinzuzufügen, wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) in der Ressource aus, der im Hauptbedienfeld die Berechtigung fehlt, und wählen Sie die fehlende Berechtigung aus.

      ![Benutzeroberfläche für Berechtigungen](/help/content-analytics/assets/aep-permissions-ui.png)

   Klicken Sie **[!UICONTROL Speichern]**, um alle Aktualisierungen zu speichern.

1. Im Bildschirm Benutzer oder Benutzergruppen :
   1. Überprüfen Sie, ob die richtigen einzelnen Benutzer oder Benutzergruppen Teil dieser Rolle sind.
      1. Wählen Sie ![UserAdd](/help/assets/icons/UserAdd.svg) Add Users in Users hinzufügen aus, um individuelle Benutzer hinzuzufügen, die Sie in Admin Console definiert haben.
      1. Wählen Sie ![Hinzufügen](/help/assets/icons/Add.svg) Gruppen in Benutzergruppen hinzufügen aus, um Benutzergruppen hinzuzufügen, die Sie in Admin Console definiert haben.


#### Customer Journey Analytics

Customer Journey Analytics unterstützt keine attributbasierte Zugriffssteuerung. Um Berechtigungen festzulegen, verwenden Sie die Admin Console.

Für Content Analytics müssen Sie überprüfen, ob die folgenden Customer Journey Analytics-Produktprofilberechtigungen enthalten sind:

* Datenansichten
   * Alle verfügbaren Datenansichten.

* Reporting-Tools
   * Zugriff auf geführte Analysen?
   * Erstellung berechneter Metriken
   * Erstellung von Segmenten
   * Lab-Zugriff?
   * Anmerkungserstellung
   * Zielgruppenerstellung?
   * Zielgruppenansicht?
   * Zugriff auf Audit-Protokolle
   * Projekt-Links für alle freigeben
   * Prognose
   * KI-Assistent: Produktkenntnisse
   * Data Insights Agent
   * Intelligente Beschriftungen
   * Daten-Storytelling?

* Tools für die Datenansicht
   * Vollständiger Tabellenexport?
   * CJA BI-Erweiterung?

So überprüfen und aktualisieren Sie diese Berechtigungen für Customer Journey Analytics:

1. Zugriff auf [Admin Console](https://adminconsole.adobe.com).
1. Wählen Sie **[!UICONTROL Produkte]** aus.
1. Wählen Sie das **[!UICONTROL Customer Journey Analytics]**-Produkt aus.
1. Wählen Sie **[!UICONTROL Produktprofile]** aus.
1. Wählen Sie das standardmäßig bereitgestellte Produktprofil aus, das für Customer Journey Analytics verfügbar ist. Beispiel: **[!UICONTROL Customer Journey Analytics]**.
1. Wählen Sie im Bildschirm Produktprofil die Option **[!UICONTROL Berechtigungen]** aus.
1. Wählen Sie eine der ![Bearbeiten](/help/assets/icons/Edit.svg)-Schaltflächen aus, um die Berechtigungen zu bearbeiten. Im Dialogfeld **[!UICONTROL Berechtigungen für Customer Journey Analytics bearbeiten]**:

   ![Benutzeroberfläche für CJA-Berechtigungen](../assets/cja-permissions-ui.png)

   1. Wählen Sie **[!UICONTROL Datenansichten]** und aktivieren Sie **[!UICONTROL Automatisch einschließen: Ein]**. Dieser Umschalter stellt sicher, dass alle Datenansichten automatisch Teil der **[!UICONTROL Enthaltene Berechtigungselemente“]**.
   1. Wählen Sie **[!UICONTROL Reporting-Tools]** aus und stellen Sie sicher, dass alle oben aufgeführten Berechtigungen Teil der **[!UICONTROL Enthaltene Berechtigungselemente“]**.
   1. Wählen Sie **[!UICONTROL Datenansichts-Tools]** aus und stellen Sie sicher, dass alle oben aufgeführten Berechtigungen Teil der **[!UICONTROL Enthaltene Berechtigungselemente“]**.

   Wählen Sie **[!UICONTROL Speichern]** aus.


## Einrichten von Schema und Datensatz

Um Daten auf Ihrer Website zu erfassen, die Content Analytics Insights unterliegen, müssen Sie zunächst definieren, welche Art von Daten Sie erfassen möchten. Und auch wie diese Daten gespeichert werden. Beide Konzepte werden unter [Einrichten eines Schemas und Datensatzes](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) in der Schnellstartanleitung [Daten über Adobe Experience Platform Web SDK &#x200B;](/help/data-ingestion/aepwebsdk.md).


## Einrichten eines Datenstroms

Sie haben definiert, welche Daten erfasst werden sollen und wie diese Daten gespeichert werden. Der nächste Schritt besteht darin, sicherzustellen, dass die auf Ihrer Website erfassten Daten an den Datensatz weitergeleitet werden. Sie müssen einen Datenstrom einrichten und konfigurieren. Weitere Informationen finden Sie unter [Einrichten eines Datenstroms](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) in der Schnellstartanleitung [Aufnehmen von Daten über die Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Verwenden von Tags

Sie haben definiert, welche Daten erfasst werden sollen (Schema), wie diese Daten gespeichert werden (Datensatz) und wie die auf Ihrer Website erfassten Daten an den Datensatz (Datenstrom) weitergeleitet werden. Als nächsten Schritt müssen Sie Ihre Website taggen , um Regeln und Datenelemente mit den Daten in Ihrer Datenschicht auf Ihrer Website zu konfigurieren. Durch das Tagging Ihrer Website wird sichergestellt, dass Daten an den konfigurierten Datenstrom gesendet werden. Das Tagging Ihrer Website mithilfe von Tags wird unter [Verwenden von Tags](/help/data-ingestion/aepwebsdk.md#use-tags) in der Schnellstartanleitung [Daten über die Adobe Experience Platform Web SDK &#x200B;](/help/data-ingestion/aepwebsdk.md).


## Bereitstellen und validieren

Sie können den Code jetzt auf der Entwicklungsversion Ihrer Website im Tag `<head>` bereitstellen. Nach der Bereitstellung beginnt Ihre Website mit der Datenerfassung in Adobe Experience Platform. Diese Daten unterliegen dann Content Analytics.

Validieren Sie Ihre Implementierung, korrigieren Sie sie bei Bedarf und stellen Sie sie mithilfe der Publishing-Workflow-Funktion von Tags in Ihrer Staging- und Produktionsumgebung bereit


## Richten Sie eine Verbindung zu Ihrem Datensatz ein.

Um über die erfassten Daten zu berichten und diese Daten für Content Analytics zu konfigurieren, müssen Sie in Customer Journey Analytics eine Verbindung einrichten. Die Verbindung stellt eine Verbindung zum Datensatz her, der die erfassten Daten enthält. Wie eine Verbindung eingerichtet wird, wird unter [Einrichten einer Verbindung](../../data-ingestion/aepwebsdk.md#set-up-a-connection) in der Schnellstartanleitung [Daten über Adobe Experience Platform Web SDK &#x200B;](/help/data-ingestion/aepwebsdk.md).


## Einrichten einer Datenansicht

Der letzte Schritt vor dem Konfigurieren von Content Analytics besteht darin, eine Datenansicht zu definieren. Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie die aus einer Verbindung stammenden Daten interpretiert werden sollen. Mit einer Datenansicht können Sie Metriken und Dimensionen aus den Daten eines oder mehrerer Datensätze definieren, mit denen Customer Journey Analytics verbunden ist. Wie Sie eine Datenansicht einrichten, wird unter [Einrichten einer Datenansicht](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) in der Schnellstartanleitung [Aufnehmen von Daten über die Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) erläutert.


## Konfigurieren von Content Analytics

Sie haben jetzt alle Voraussetzungen, um Content Analytics zu konfigurieren.

### Geführte Konfiguration

Verwenden Sie den [Konfigurationsassistenten](guided.md) und wählen Sie die Datenansicht aus, die Sie im Rahmen des Schritts [Einrichten einer &#x200B;](#set-up-a-data-view)&quot; erstellt haben. Durch diese Auswahl wird sichergestellt, dass Content Analytics zusätzlich zu den auf Ihrer Website erfassten Daten konfiguriert und implementiert wird.

Beachten Sie, dass der Assistent Geführte Konfiguration die folgenden zusätzlichen spezifischen Content Analytics-Objekte konfiguriert:

* **Datensatz**, der automatisch für Content Analytics-Ereignisse eingerichtet wird. Dieser Datensatz verwendet ein bestimmtes Content Analytics-Schema, das bereits erstellt und verfügbar ist.
* **Datastream** der automatisch zum Streamen von Content Analytics-Ereignissen in den Content Analytics-Datensatz eingerichtet wird.
* **Tags-Eigenschaft** die automatisch eingerichtet und mit der Content Analytics-Erweiterung konfiguriert wird. Diese Tags-Eigenschaft stellt sicher, dass Ihre Website Content Analytics-Daten an den Content Analytics-Datenstrom und den Content Analytics-Datensatz sendet.

  >[!IMPORTANT]
  >
  >Stellen Sie sicher, dass Sie im Assistenten die Option zum Erstellen einer neuen Tag[Eigenschaft im Schritt &quot;](guided.md#new-configuration-1)&quot; auswählen.
  >



### Manuelle Konfiguration

Um Content Analytics für Ihre Website zu implementieren, müssen Sie die Content Analytics Tags-Eigenschaft [manuell) &#x200B;](manual.md).


## Einrichten eines Projekts

Richten Sie in Customer Journey Analytics ein Projekt ein, um Ihre [Content Analytics-Berichte und -Visualisierungen zu erstellen](/help/content-analytics/report/report.md). Alternativ können Sie eine [Content Analytics-Vorlage verwenden](/help/content-analytics/report/report.md#template) um zu beginnen.






