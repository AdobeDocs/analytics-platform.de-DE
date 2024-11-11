---
title: Hinzufügen der XDM-Datenerfassungslogik zu Ihrem Tag
description: Erfahren Sie, wie Sie Ihrem Tag eine XDM-Datenerfassungslogik hinzufügen
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 48%

---

# Hinzufügen der XDM-Datenerfassungslogik zu Ihrem Tag

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Nachdem Sie [das Tag erstellt und die Web SDK-Erweiterung hinzugefügt haben](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), müssen Sie es mit Datenelementen und Regeln konfigurieren, je nachdem, wie Sie Ihre Site verfolgen und Daten an Adobe Experience Platform senden möchten. Nachdem Sie Datenelemente und Regeln für Ihr Tag konfiguriert haben, können Sie es erstellen und veröffentlichen.

## Datenelemente konfigurieren

Datenelemente sind die Bausteine Ihres Datenwörterbuchs (oder Ihrer Data Map). Verwenden Sie Datenelemente zum Erfassen, Organisieren und Bereitstellen von Daten in Marketing- und Werbe-Tools. Datenelemente richten Sie in Ihren Tags ein, die aus Ihrer Datenschicht lesen und zur Bereitstellung von Daten in Adobe Experience Platform verwendet werden können.

Es gibt verschiedene Arten von Datenelementen. Richten Sie zunächst ein Datenelement ein, um den Seitennamen zu erfassen, den Personen auf Ihrer Site anzeigen. Richten Sie dann ein Datenelement ein, das auf die Experience Cloud-ID verweist. Definieren Sie abschließend ein XDM-Objektdatenelement.

### Datenelement &quot;Seitenname&quot;

Gehen Sie folgendermaßen vor, um ein Datenelement für den Seitennamen zu definieren:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

1. Geben Sie im Dialogfeld [!UICONTROL Datenelement erstellen] die folgenden Informationen an:

   * **[!UICONTROL Name]**: Der Name Ihres Datenelements. Zum Beispiel `Page Name`.

   * **[!UICONTROL Erweiterung]**: Wählen Sie **[!UICONTROL Core]** aus der Liste aus.

   * **[!UICONTROL Datenelementtyp]**: Wählen Sie **[!UICONTROL Seiteninformationen]** aus der Liste aus.

   * **[!UICONTROL Attribut]**: Wählen Sie **[!UICONTROL Titel]** aus der Liste aus.

     ![Erstellen eines Datumselements mithilfe von Seiteninformationen](assets/create-dataelement-1.png)

     Alternativ hätten Sie zum Definieren des Datenelements auch den Wert einer Variablen Ihrer Datenschicht, z. B. `pageName`, und ein Datenelement vom Typ [!UICONTROL JavaScript-Variable] verwenden können.

     ![Erstellen eines Datenelements mit einer JavaScript-Variablen](assets/create-dataelement-2.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

   Sie möchten jetzt ein Datenelement einrichten, das auf die Experience Cloud-ID verweist, die automatisch vom Adobe Experience Platform Web SDK bereitgestellt und über die Experience Cloud ID Service-Erweiterung verfügbar ist.

1. Fahren Sie mit dem [ECID-Datenelement](#ecid-data-element) fort.

### ECID-Datenelement

Gehen Sie folgendermaßen vor, um ein ECID-Datenelement zu definieren:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

1. Geben Sie im Dialogfeld [!UICONTROL Datenelement erstellen] die folgenden Informationen an:

   * **[!UICONTROL Name]**: Der Name Ihres Datenelements. Zum Beispiel `ECID`.

   * **[!UICONTROL Erweiterung]**: Wählen Sie **[!UICONTROL Experience Cloud ID-Dienst]** aus der Liste aus.

   * **[!UICONTROL Datenelementtyp]**: Wählen Sie **[!UICONTROL ECID]** aus der Liste aus.

     ![ECID-Datenelement](assets/ecid-dataelement.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

1. Fahren Sie mit [XDM-Objektdatenelement](#xdm-object-data-element) fort.

### XDM-Objektdatenelement

Abschließend möchten Sie Ihre spezifischen Datenelemente dem zuvor definierten Schema zuordnen. Sie definieren ein weiteres Datenelement, das Ihrem XDM-Schema entspricht.

Gehen Sie folgendermaßen vor, um ein XDM-Objekt-Datenelement zu definieren:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Datenelemente]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Datenelement hinzufügen]** aus.

1. Geben Sie im Dialogfeld [!UICONTROL Datenelement erstellen] die folgenden Informationen an:

   * **[!UICONTROL Name]**: Der Name Ihres Datenelements. Zum Beispiel `XDM - Page View`.

   * **[!UICONTROL Erweiterung]**: Wählen Sie **[!UICONTROL Adobe Experience Platform Web SDK]** aus der Liste aus.

   * **[!UICONTROL Datenelementtyp]**: Wählen Sie **[!UICONTROL XDM-Objekt]** aus der Liste aus.

   * **[!UICONTROL Sandbox]**: Wählen Sie Ihre Sandbox aus der Liste aus.

   * **[!UICONTROL Schema]**: Wählen Sie Ihr Schema aus der Liste aus.

1. Ordnen Sie das Attribut `identification > core > ecid`, das in Ihrem Schema definiert ist, dem ECID-Datenelement zu. Wählen Sie das Zylindersymbol aus, um das ECID-Datenelement in der Liste der Datenelemente einfach auswählen zu können.

   ![ECID-Datenelement auswählen](assets/pick-ecid-dataelement.png)

   ![ECID-Datenelement zuordnen](assets/map-ecid.png)


1. Ordnen Sie das Attribut `web > webPageDetails > name`, das in Ihrem Schema definiert ist, dem Datenelement „Seitenname“ zu.

   ![Datenelement „Seitenname“ zuordnen](assets/map-pagename.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

1. Fahren Sie mit [Regeln konfigurieren](#configure-rules) fort.

## **Regeln konfigurieren**

Tags in Adobe Experience Platform folgen einem regelbasierten System. Sie suchen nach Benutzerinteraktionen und zugehörigen Daten. Wenn die in Ihren Regeln formulierten Kriterien erfüllt sind, löst die Regel die jeweils definierte Erweiterung, das Skript oder den Client-seitigen Code aus. Sie können mithilfe von Regeln Daten (wie ein XDM-Objekt) unter Verwendung der der Adobe Experience Platform Web SDK-Erweiterung an Adobe Experience Platform senden.

Gehen Sie folgendermaßen vor, um eine Regel zu definieren:

>[!NOTE]
>
>Die folgenden Schritte sind ein Beispiel für die Definition einer Regel, die XDM-Daten sendet, die Werte aus anderen Datenelementen enthalten, an Adobe Experience Platform.
>
>Sie können Regeln in Ihrem Tag auf unterschiedliche Weise verwenden, um (mithilfe Ihrer Datenelemente) Variablen zu bearbeiten.
>
>Weitere Informationen finden Sie unter [Regeln](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=de).

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Regeln]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Neue Regel erstellen]** aus.

1. Geben Sie im Dialogfeld [!UICONTROL Regel erstellen] die folgenden Informationen an:

   * **[!UICONTROL Name]**: Der Name der Regel. Zum Beispiel `Page View`.

   * **[!UICONTROL Ereignisse]**: Wählen Sie **[!UICONTROL + Hinzufügen]** aus. Geben Sie dann im Dialogfeld [!UICONTROL Ereigniskonfiguration] die folgenden Informationen an. Wenn Sie fertig sind, wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.

      * **[!UICONTROL Erweiterung]**: Wählen Sie **[!UICONTROL Core]** aus der Liste aus.

      * **[!UICONTROL Ereignistyp]**: Wählen Sie **[!UICONTROL Fenster geladen]** aus der Liste aus.

        ![Regel – Ereigniskonfiguration](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Aktionen]**: Wählen Sie **[!UICONTROL + Hinzufügen]** aus. Geben Sie dann im Dialogfeld [!UICONTROL Aktionskonfiguration] die folgenden Informationen an. Wenn Sie fertig sind, wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.

      * **[!UICONTROL Erweiterung]**: Wählen Sie **[!UICONTROL Adobe Experience Platform Web SDK]** aus der Liste aus.

      * **[!UICONTROL Aktionstyp]**: Wählen Sie **[!UICONTROL Ereignis senden]** aus der Liste aus.

      * **[!UICONTROL Typ]**: Wählen Sie **[!UICONTROL web.webpageDetails.pageViews]** aus der Liste aus.

      * **[!UICONTROL XDM data]**: Wählen Sie das Zylindersymbol und dann **[!UICONTROL XDM - Seitenansicht]** aus der Liste der Datenelemente.

        ![Regel – Aktionskonfiguration](assets/action-pageview-xdm.png)

        Ihre Regel sollte wie folgt aussehen:

        ![Regel erstellen](assets/rule-pageview.png)

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Tag erstellen und veröffentlichen

Nachdem Sie Datenelemente und Regeln definiert haben, müssen Sie Ihr Tag erstellen und veröffentlichen. Wenn Sie einen Bibliotheks-Build erstellen, müssen Sie ihn einer Umgebung zuweisen. Die Erweiterungen, Regeln und Datenelemente des Builds werden dann kompiliert und in die zugewiesene Umgebung eingefügt. Jede Umgebung bietet einen eindeutigen Einbettungs-Code, mit dem Sie den zugewiesenen Build in Ihre Website integrieren können.

Adobe Experience Platform-Tags unterstützen einfache, komplexe Veröffentlichungs-Workflows, die für Ihre Bereitstellung des Adobe Experience Platform Web SDK geeignet sind. Weitere Informationen finden Sie unter [Veröffentlichung – Überblick](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=de).

Gehen Sie folgendermaßen vor, um Ihr Tag zu erstellen und zu veröffentlichen:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei experience.adobe.com an.

1. Gehen Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Veröffentlichungsfluss]** in der linken Leiste aus.

1. Wählen Sie **[!UICONTROL Arbeitsbibliothek auswählen]**, gefolgt von **[!UICONTROL Bibliothek hinzufügen...]** aus.

1. Geben Sie im Dialogfeld [!UICONTROL Bibliothek erstellen] die folgenden Informationen an:

   * **[!UICONTROL Name]**: Der Name der Bibliothek.

   * **[!UICONTROL Umgebung]**: Wählen Sie **[!UICONTROL Entwicklung (Entwicklung)]** aus der Liste aus.

1. Wählen Sie **[!UICONTROL + Alle geänderten Ressourcen hinzufügen]** aus.

   ![Veröffentlichen – Bibliothek erstellen](assets/create-library-aep.png)

1. Wählen Sie **[!UICONTROL Speichern und in Entwicklung erstellen]** aus.

   Ihr -Tag wird gespeichert und für Ihre Entwicklungsumgebung erstellt. Ein grüner Punkt kennzeichnet eine erfolgreiche Erstellung Ihres Tags in Ihrer Entwicklungsumgebung.

1. Sie können **[!UICONTROL ...]** auswählen, um die Bibliothek neu zu erstellen oder in eine Staging- oder Produktionsumgebung zu verschieben.

   ![Veröffentlichen – Bibliothek erstellen](assets/build-library.png)

