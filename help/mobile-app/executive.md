---
description: Anleitung zur Verwendung der Dashboard-Scorecards.
title: Handbuch zu Analytics-Dashboards
feature: Analytics Dashboards
role: User
exl-id: 12901a76-cb88-45a5-81e9-59fb310328be
solution: Customer Journey Analytics
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 73%

---

# Schnellstarthandbuch für ausführende Benutzer

Im Folgenden finden Sie Informationen zu Best Practices für die Verwendung und Anzeige von Analytics-Dashboards.


>[!BEGINSHADEBOX]

Unter ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Unterstützung von Führungskräften beim Zugriff auf mobile Scorecards](https://video.tv.adobe.com/v/3444845?captions=ger){target="_blank"} finden Sie ein Demovideo.

>[!ENDSHADEBOX]

Dieses Handbuch soll ausführenden Benutzern helfen, die Scorecards in den Analytics-Dashboards zu lesen und zu interpretieren. Das Programm ermöglicht es ausführenden Benutzern, eine umfassende Darstellung wichtiger Zusammenfassungsdaten schnell und einfach auf ihren eigenen Mobilgeräten anzuzeigen.

## Dashboards auf Ihrem Gerät einrichten

Um die Dashboards effektiv zu nutzen, bitten Sie Ihren Scorecard-Kurator bei der Einrichtung der App um Hilfe. Dieser Abschnitt enthält Informationen, die Ihnen helfen, die App zusammen mit Ihrem Kurator einzurichten.

### Zugriff erhalten

Um auf Scorecards in Dashboards zuzugreifen, stellen Sie Folgendes sicher:

* Sie haben gültige Anmeldeinformationen für Customer Journey Analytics.
* Ihr Kurator hat mobile Scorecards korrekt erstellt und für Sie freigegeben.

### Herunterladen und Installieren von Dashboards

Um die App herunterzuladen und zu installieren, führen Sie die Schritte entsprechend dem Betriebssystem auf Ihrem Gerät aus.

>[!NOTE]
>
>Obwohl die Mobile App im App Store Adobe Analytics Dashboard heißt, kann sie auch mit Customer Journey Analytics Mobile Scorecards verwendet werden.

**Für ausführende Benutzer mit iOS-Geräten:**

Klicken Sie auf den folgenden Link (er ist auch in Customer Journey Analytics unter **[!UICONTROL Tools]** > **[!UICONTROL Analytics-Dashboards (Mobile App)]** verfügbar) und befolgen Sie die Anweisungen zum Herunterladen, Installieren und Öffnen der App:

[iOS-Link](https://apple.co/2zXq0aN)

**Für ausführende Benutzer mit Android-Geräten:**

Klicken Sie auf den folgenden Link (er ist auch in Customer Journey Analytics unter **[!UICONTROL Tools]** > **[!UICONTROL Analytics-Dashboards (Mobile App)]** verfügbar) und befolgen Sie die Anweisungen zum Herunterladen, Installieren und Öffnen der App:

[Android-Link](https://bit.ly/2LM38Oo)

Nach dem Herunterladen und der Installation können sich ausführende Benutzer mit ihren bestehenden Customer Journey Analytics-Anmeldedaten bei der App anmelden.

![Begrüßungsbildschirm der Customer Journey Analytics-App](assets/welcome.png)

## Verwenden von Dashboards {#use-dashboards}

So verwenden Sie Dashboards:

1. Melden Sie sich bei der Mobile App an. Der Anmeldebildschirm wird beim Start der Dashboards angezeigt. Befolgen Sie die Eingabeaufforderungen mit Ihren bestehenden Customer Journey Analytics-Anmeldedaten. Adobe und Enterprise/Federated IDs werden unterstützt.

   ![Anmeldesequenz](assets/signseq.png)

1. Wählen Sie ein Unternehmen aus. Nach der Anmeldung bei den Dashboards wird der Bildschirm **[!UICONTROL Organisation auswählen]** angezeigt. Auf diesem Bildschirm werden die Unternehmensanmeldungen angezeigt, die Sie verwenden können. Tippen Sie auf den Firmennamen, der der für Sie freigegebenen Scorecard zugeordnet ist.

   Die Scorecard-Liste zeigt alle Scorecards an, die für Sie freigegeben wurden.

1. Tippen Sie auf die Scorecard, die Sie anzeigen möchten.

   Wenn Sie unter einer Anmeldung Zugriff auf mehr als eine Organisation haben, sind alle Scorecards Ihrer Organisation in der Scorecard-Liste verfügbar.

   Sie können die Scorecard-Liste nach Scorecard-Titel, Organisationsname oder Zuletzt angezeigt sortieren. Sie können sogar nach einer bestimmten Scorecard suchen.

   ![Unternehmen auswählen](assets/mobile-home-screen.png)

   Wenn Sie sich anmelden und eine Meldung darüber erhalten, dass nichts freigegeben wurde, überprüfen Sie Folgendes zusammen mit Ihrem Kurator:

   * Sie können sich bei der richtigen Customer Journey Analytics-Sandbox anmelden.
   * Die Scorecard wurde für Sie freigegeben.

   ![Nichts freigegeben](assets/nothing.png)

1. Untersuchen Sie, wie die Kacheln in der Scorecard angezeigt werden. (Die erste Scorecard wird im Dunkelmodus angezeigt. Weitere Informationen finden Sie unter **[!UICONTROL Voreinstellungen]** weiter unten).

   ![Erklärte Kacheln](assets/newexplain.png)

   Zusätzliche Informationen zu Kacheln:

   * Die Granularität der Sparklines hängt von der Länge des Datumsbereichs ab:

      * Für einen Tag wird ein stündlicher Trend angezeigt.
      * Für mehr als einen Tag und weniger als ein Jahr wird ein täglicher Trend angezeigt.
      * Für ein Jahr oder mehr wird ein wöchentlicher Trend angezeigt.

   * Die Formel für die Änderung des Prozentwerts ist: Gesamtwert der Metrik (aktueller Datumsbereich) – Gesamtwert der Metrik (Vergleichsdatumsbereich) / Gesamtwert der Metrik (Vergleichsdatumsbereich).

   * Sie können den Anzeigebereich nach unten ziehen, um die Scorecard zu aktualisieren.

   Das folgende Beispiel einer Scorecard wird im normalen Modus angezeigt:

   ![Beispiel-Scorecard](assets/intro_scorecard.png)

1. Tippen Sie auf eine Kachel, um zu sehen, wie eine detaillierte Aufschlüsselung für die Kachel funktioniert.

   ![Aufschlüsselungsansicht](assets/sparkline.png)


1. So ändern Sie Datumsbereiche für Ihre Scorecard:

   ![Datum ändern](assets/changedate.png)

   * Sie können die Datumsbereiche auch in der oben gezeigten Aufschlüsselungsansicht auf dieselbe Weise ändern.

   * Je nachdem, auf welches Intervall Sie tippen (**Tag**, **Woche**, **Monat** oder **Jahr**), sehen Sie zwei Optionen für Datumsbereiche – entweder den aktuellen oder den unmittelbar vorhergehenden Zeitraum. Tippen Sie auf eine dieser beiden Optionen, um den ersten Bereich auszuwählen. Tippen Sie in der Liste unter **[!UICONTROL VERGLEICHEN MIT]** auf eine der angezeigten Optionen, um die Daten in diesem Zeitraum mit dem ersten von Ihnen ausgewählten Datumsbereich zu vergleichen. Tippen Sie oben rechts im Bildschirm auf **[!UICONTROL Fertig]**. Das Feld **[!UICONTROL Datumsbereiche]** und die Scorecard-Kacheln werden mit den neuen Vergleichsdaten aus den von Ihnen ausgewählten neuen Bereichen aktualisiert.

1. Um ein Segment auf Ihre Scorecard anzuwenden, tippen Sie auf das Dropdown-Menü „Segment“ und wählen Sie ein Segment aus, das von Ihrem Kurator konfiguriert wurde. [Segmente](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=de) in der App funktionieren genauso wie in Workspace.

   ![Segment](assets/segment_filter.png)

1. [!UICONTROL Scorecard]-Aktualisierungen abrufen. Wenn eine [!UICONTROL Scorecard] nicht alle Metriken oder Aufschlüsselungen enthält, die für Sie von Interesse sein könnten, wenden Sie sich an Ihr Customer Journey Analytics-Team, damit die Scorecard aktualisiert wird. Nach der Aktualisierung können Sie die Karte auf dem Bildschirm nach unten ziehen, um sie zu aktualisieren und die kürzlich hinzugefügten Daten zu laden.

1. So hinterlassen Sie Feedback zu dieser App:

   1. Tippen Sie auf das Einstellungssymbol oben recht im App-Bildschirm.
   2. Tippen Sie auf dem Bildschirm **[!UICONTROL Einstellungen]** auf die Option **[!UICONTROL Feedback]**.
   3. Tippen Sie, um die Optionen zum Hinterlassen von Feedback anzuzeigen.

      ![Einstellungsbildschirm](assets/settings.png)

1. Um die Voreinstellungen zu ändern, tippen Sie auf die Option **[!UICONTROL Voreinstellungen]** oben. In den Voreinstellungen können Sie die biometrische Anmeldung aktivieren oder Sie können die App wie folgt für den Dunkelmodus einstellen:

   ![Dunkelmodus](assets/darkmode.png)


**So melden Sie einen Fehler:**

Tippen Sie auf die Option und wählen Sie eine Unterkategorie für den Fehler aus. Geben Sie im Formular zur Meldung eines Fehlers im obersten Feld Ihre E-Mail-Adresse und im Feld darunter eine Beschreibung des Fehlers an. Ein Screenshot Ihrer Kontoinformationen wird automatisch an die Nachricht angehängt. Sie können den Screenshot jedoch löschen, indem Sie auf das **X** im Bild des Anhangs tippen. Außerdem können Sie eine Bildschirmaufzeichnung erstellen, weitere Screenshots hinzufügen oder Dateien anhängen. Um den Bericht zu senden, tippen Sie auf das Papierfliegersymbol oben rechts im Formular.

![Fehler melden](assets/newbug.png)

**So schlagen Sie eine Verbesserung vor**:

Tippen Sie auf die Option und wählen Sie eine Unterkategorie für den Vorschlag aus. Geben Sie im Vorschlagsformular im obersten Feld Ihre E-Mail-Adresse und im Feld darunter eine Beschreibung des Fehlers an. Ein Screenshot Ihrer Kontoinformationen wird automatisch an die Nachricht angehängt. Sie können den Screenshot jedoch löschen, indem Sie auf das **X** im Bild des Anhangs tippen. Außerdem können Sie eine Bildschirmaufzeichnung erstellen, weitere Screenshots hinzufügen oder Dateien anhängen. Um den Vorschlag zu senden, tippen Sie auf das Papierfliegersymbol oben rechts im Formular.

**So stellen Sie eine Frage:**

Tippen Sie auf die Option und geben Sie im obersten Feld Ihre E-Mail-Adresse und im Feld darunter Ihre Frage an. Ein Screenshot wird automatisch an die Nachricht angehängt. Sie können den Screenshot jedoch löschen, indem Sie auf das **X** im Bild des Anhangs tippen. Außerdem können Sie eine Bildschirmaufzeichnung erstellen, weitere Screenshots hinzufügen oder Dateien anhängen. Um die Frage zu senden, tippen Sie auf das Papierfliegersymbol oben rechts im Formular.

## Glossar

| Begriff | Definition |
|--- |--- |
| Verbraucher | Führungskraft, die Schlüsselmetriken und Einblicke aus Customer Journey Analytics auf einem Mobilgerät anzeigt |
| Kurator | Person, die mit der Datenerfassung und -auswertung vertraut ist, Einblicke aus Customer Journey Analytics erlangt und verteilt und die von Verbrauchern anzuzeigenden Scorecards konfiguriert |
| Kuratierung | Der Vorgang der Erstellung oder Bearbeitung einer mobilen Scorecard mit relevanten Metriken, Dimensionen und anderen Komponenten für den Verbraucher |
| Scorecard | Eine Ansicht der Dashboards mit einer oder mehreren Kacheln |
| Kachel | Wiedergabe einer Metrik in einer Scorecard-Ansicht |
| Aufschlüsselung | Eine sekundäre Ansicht, die durch Tippen auf eine Kachel in der Scorecard zugänglich ist. Diese Ansicht erweitert die auf der Kachel dargestellte Metrik und zeigt optional Informationen über zusätzliche Aufschlüsselungsdimensionen an |
| Datumsbereich | Der primäre Datumsbereich für die Berichterstellung über die Dashboards |
| Vergleichsdatumsbereich | Der Datumsbereich, der mit dem primären Datumsbereich verglichen wird |
