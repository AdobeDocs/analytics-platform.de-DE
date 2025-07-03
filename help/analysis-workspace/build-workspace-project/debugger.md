---
description: Erfahren Sie, wie Sie mit dem Debugger Probleme mit Ihrem Projekt in Analysis Workspace beheben können.
keywords: Analysis Workspace
feature: Workspace Basics
title: Projekt-Debugger
role: User
source-git-commit: 4d902bab01c1c795cb7d852066128f6b9db0823a
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 3%

---

# Projekt-Debugger

Der Projekt-Debugger unterstützt Sie und den Adobe-Support bei der Fehlerbehebung bei Projekten in Analysis Workspace. Der Adobe-Support bittet Sie möglicherweise, den Debugger zu aktivieren, um Tickets zu beheben, die Sie beim Adobe-Support ausgelöst haben. Beispiele für Probleme sind die Ladezeit von Visualisierungen oder fehlerhafte Komponenten in Ihren Visualisierungen.

>[!NOTE]
>
>Um den Debugger verwenden zu können, benötigen Sie **Bearbeiten** oder **Kopieren** [Zugriff auf das Projekt](https://experienceleague.adobe.com/de/docs/experience-cloud-kcs/kbarticles/ka-25744).
>


## Debugger aktivieren

>[!IMPORTANT]
>
>Speichern Sie das Projekt, bevor Sie den Debugger aktivieren.
>

So aktivieren Sie den Debugger:

1. Wählen **[!UICONTROL Hilfe]** > **[!UICONTROL Debugger aktivieren]** aus dem Analysis Workspace-Projektmenü.
1. Wählen **&#x200B;**&#x200B;im Dialogfeld **[!UICONTROL Debugger aktivieren]** die Option OK aus.
1. Bestätigen Sie, wenn der Browser Sie auffordert, die Seite oder Site neu zu laden.


## Verwenden des Debuggers

Wenn Sie den Debugger aktiviert haben, verfügen alle Visualisierungen in Ihrem Projekt über ein zusätzliches ![-Symbol](/help/assets/icons/Bug.svg).

So verwenden Sie den Debugger für eine bestimmte Visualisierung:

1. Wählen ![ oben ](/help/assets/icons/Bug.svg) der Visualisierung „Bug“ aus.

   ![Debugger-Kontextmenü](assets/debugger-context-menu.png)

1. Wählen Sie die entsprechende Aktion aus dem Kontextmenü aus. Die verfügbaren Aktionen hängen von der Visualisierung ab und geben den Typ des Debuggens an, den Sie durchführen möchten. Wenn Sie beispielsweise &quot;**[!UICONTROL &quot; auswählen]** können Sie die Anomaliefunktion in der Visualisierung debuggen.
1. Wählen Sie im Untermenü einen Zeitstempel aus.
1. Ein **[!UICONTROL Oberon XML]**-Debugfenster wird mit Details zu den spezifischen Funktionen geöffnet, die von der Visualisierung ausgeführt werden. Unten finden Sie ein Beispiel für die Ausgabe einer Anomalieanforderung.

   ![Ausgabe-Debuganforderung](assets/debugger-oberon.png)

   Die Details sind:

   * **[!UICONTROL Zeitstempel der Anfrage]**
   * **[!UICONTROL Zeitstempel der Antwort]**
   * **[!UICONTROL Anfragezeit]**
   * **[!UICONTROL Warteschlangenzeit]**
   * **[!UICONTROL Server-Verarbeitungszeit]**
   * **[!UICONTROL Lookup Time]**
   * **[!UICONTROL Komplexität]**
   * **[!UICONTROL Monatsgrenzen]**
   * **[!UICONTROL Spalten]**
   * **[!UICONTROL Segmente]**
   * **[!UICONTROL XML]** **[!UICONTROL Request]** und **[!UICONTROL Response]**
   * **[!UICONTROL cURL-Anfrage]**
   * **[!UICONTROL JSON]** **[!UICONTROL Request]** und **[!UICONTROL Response]**

1. Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL Alle Felder in die Zwischenablage kopieren]**, um alle Debugging-Informationen in die Zwischenablage zu kopieren. Fügen Sie die Informationen in Ihren bevorzugten Editor oder Ihr bevorzugtes Tool ein. Die Informationen umfassen:

   * XML (Anfrage)
   * XML (Antwort)
   * JSON (Anfrage)
   * JSON (Antwort)
   * cURL-Anfrage

1. **&#x200B; Verwenden Sie ![Kopieren](/help/assets/icons/Copy.svg) &#x200B;** [!UICONTROL In Zwischenablage kopieren]d unter **[!UICONTROL cURL-]**, um die Anfrage in die Zwischenablage zu kopieren.
1. Bewegen Sie den Mauszeiger über einen der **[!UICONTROL Anfrage]** oder **[!UICONTROL Antwort]** Textbereiche, um ![Kopieren](/help/assets/icons/Copy.svg) **[!UICONTROL In Zwischenablage kopieren]** einzublenden und auszuwählen, um den Inhalt dieses Textbereichs (XML oder JSON) in die Zwischenablage zu kopieren.

1. Tauschen Sie alle kopierten Informationen und den von Adobe angeforderten Support aus, um die Visualisierungen in Ihrem Analysis Workspace-Projekt zu beheben.

1. Wählen Sie **[!UICONTROL Abbrechen]** aus, um das **[!UICONTROL Oberon XML]**-Debugfenster zu schließen und zum Projekt zurückzukehren.

Wiederholen Sie die obigen Schritte für jede andere Visualisierung, die Sie beheben möchten.

## Debugger deaktivieren

>[!IMPORTANT]
>
>Bevor Sie den Debugger deaktivieren, speichern Sie alle Änderungen, die Sie am Projekt vorgenommen haben, und möchten sie im Rahmen der Debugging-Übung beibehalten.
>

Deaktivieren des Debuggers:

1. Wählen **[!UICONTROL Hilfe]** > **[!UICONTROL Debugger deaktivieren]** aus dem Analysis Workspace-Projektmenü aus.
1. Wählen **&#x200B;**&#x200B;im Dialogfeld **[!UICONTROL Debugger deaktivieren]** die Option OK aus.
1. Bestätigen Sie, wenn der Browser Sie auffordert, die Seite oder Site neu zu laden.



