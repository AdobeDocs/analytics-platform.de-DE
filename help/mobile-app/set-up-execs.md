---
description: Einrichten von Benutzern für die Verwendung der mobilen Adobe Analytics-Dashboard-App
title: Einrichten von Führungskräften für die Verwendung von Dashboards
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
source-git-commit: 9cffb57cc4a525c78ec171034adff0e02b936cbf
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 76%

---

# Einrichten von Führungskräften für die Verwendung von Dashboards

In einigen Fällen benötigen die ausführenden Benutzer möglicherweise zusätzliche Hilfe, um auf die App zuzugreifen und sie zu verwenden. Dieser Abschnitt enthält Informationen, die Kuratoren bei der Bereitstellung dieser Hilfe unterstützen.

## Sicherstellen, dass Mobile-App-Benutzer Zugriff auf Adobe Analytics haben

1. Richten Sie neue Benutzer in der [Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=de) ein.

1. Um Scorecards freigeben zu können, müssen Sie App-Benutzern Berechtigungen für den Zugriff auf Scorecard-Komponenten wie Analysis Workspace, die Datenansichten, auf denen Scorecards basieren, sowie Filter, Metriken und Dimensionen gewähren.

## Systemanforderungen von Mobile-App-Benutzern

Damit ausführende Benutzer Zugriff auf Ihre Scorecards in der Mobile App haben, müssen folgende Voraussetzungen gegeben sein:

* Auf den Geräten Ihrer Benutzer muss mindestens iOS-Version 10 oder Android-Version 4.4 (KitKat) installiert sein.
* Sie haben eine gültige Anmeldung bei Customer Journey Analytics.
* Sie haben die mobilen Scorecards für Ihre Benutzer korrekt erstellt und freigegeben.
* Ihre Benutzer müssen Zugriff auf die Komponenten haben, die die Scorecard enthält. Sie können bei der Freigabe Ihrer Scorecards eine Option auswählen, um **[!UICONTROL eingebettete Komponenten freizugeben]**.

## Ausführenden Benutzern helfen, die Mobile App herunterzuladen und zu installieren

>[!NOTE]
>
>Obwohl die mobile App im App Store den Namen Adobe Analytics-Dashboard trägt, kann die App gleichermaßen mit mobilen Customer Journey Analytics-Scorecards verwendet werden.

**Für ausführende Benutzer mit iOS-Geräten:**

Klicken Sie auf den folgenden Link (er ist auch im Customer Journey Analytics unter verfügbar). **[!UICONTROL Instrumente]** > **[!UICONTROL Analytics-Dashboards (mobile Opp)]**) und befolgen Sie die Anweisungen zum Herunterladen, Installieren und Öffnen der App:

`[iOS link](https://apple.co/2zXq0aN)`

**Für ausführende Benutzer mit Android-Geräten:**

Klicken Sie auf den folgenden Link (er ist auch im Customer Journey Analytics unter verfügbar). **[!UICONTROL Instrumente]** > **[!UICONTROL Analytics-Dashboards (mobile App)]**) und befolgen Sie die Anweisungen zum Herunterladen, Installieren und Öffnen der App:

`[Android link](https://bit.ly/2LM38Oo)`

Nach dem Herunterladen und Installieren können sich ausführende Benutzer mit ihren vorhandenen Customer Journey Analytics-Anmeldeinformationen bei der App anmelden. Wir unterstützen sowohl Adobe- als auch Enterprise/Federated IDs.

![Willkommensbildschirm der App](assets/welcome.png)

## Ausführenden Benutzern helfen, auf Ihre Scorecard zuzugreifen

1. Fordern Sie die ausführenden Benutzer auf, sich bei der Mobile App anzumelden.

   Der Bildschirm **[!UICONTROL Unternehmen auswählen]** wird angezeigt. Auf diesem Bildschirm werden die Unternehmensanmeldungen angezeigt, die der ausführende Benutzer verwenden kann.

1. Fordern Sie sie auf, den Namen der Unternehmensanmeldung oder die Experience Cloud-Organisation für die von Ihnen freigegebene Scorecard anzutippen.

   Die Scorecard-Liste zeigt alle Scorecards an, die für den ausführenden Benutzer mit dieser Unternehmensanmeldung freigegeben wurden.

1. Helfen Sie den Benutzern, diese Liste ggf. nach der **[!UICONTROL zuletzt geänderten Scorecard]** zu sortieren.

1. Fordern Sie sie auf, den Namen der Scorecard anzutippen, die angezeigt werden soll.

   ![Unternehmen auswählen](assets/accesscard.png)


### Scorecard-Benutzeroberfläche erläutern

Erklären Sie dem ausführenden Benutzer, wie die Kacheln in den von Ihnen freigegebenen Scorecards dargestellt werden.

![Kacheln erklären](assets/newexplain.png)

![Beispiel-Scorecard](assets/intro_scorecard.png)

Zusätzliche Informationen zu Kacheln:

* Die Granularität der Sparklines hängt von der Länge des Datumsbereichs ab:
* Für einen Tag wird ein stündlicher Trend angezeigt.
   * Für mehr als einen Tag und weniger als ein Jahr wird ein täglicher Trend angezeigt.
   * Für ein Jahr oder mehr wird ein wöchentlicher Trend angezeigt.
   * Die Formel für die Änderung des Prozentwerts ist: Gesamtwert der Metrik (aktueller Datumsbereich) – Gesamtwert der Metrik (Vergleichsdatumsbereich) / Gesamtwert der Metrik (Vergleichsdatumsbereich).
   * Sie können den Anzeigebereich nach unten ziehen, um die Scorecard zu aktualisieren.


1. Tippen Sie auf eine Kachel, um zu zeigen, wie eine detaillierte Aufschlüsselung für die Kachel funktioniert.

   ![Aufschlüsselungsansicht](assets/sparkline.png)

   * Tippen Sie auf einen beliebigen Punkt auf einer Sparkline, um Daten anzuzeigen, die diesem Punkt auf der Linie zugeordnet sind.

   * In einer Tabelle werden Daten zu den der Kachel hinzugefügten Dimensionen angezeigt. Tippen Sie auf den Abwärtspfeil, um Dimensionen auszuwählen. Wenn der Kachel keine Dimension hinzugefügt wurde, werden in der Tabelle Diagrammdaten angezeigt.

1. Um die Datumsbereiche für die Scorecard zu ändern, tippen Sie auf die Kopfzeile „Datum“ und wählen Sie die gewünschte Kombination aus Primär- und Vergleichsdatumsbereich aus.

   ![Datum ändern](assets/changedate.png)

## Mobile-App-Voreinstellungen ändern

Um die Voreinstellungen zu ändern, tippen Sie auf die Option **[!UICONTROL Voreinstellungen]** oben. In den Voreinstellungen können Sie die biometrische Anmeldung aktivieren oder Sie können die App wie folgt für den Dunkelmodus einstellen:

![Dunkelmodus](assets/darkmode.png)

## Fehlerbehebung

Wenn sich der ausführende Benutzer anmeldet und eine Meldung angezeigt wird, dass nichts freigegeben wurde, kann das folgende Gründe haben:

![Nichts freigegeben](assets/nothing.png)

* Der ausführende Benutzer hat möglicherweise die falsche Customer Journey Analytics-Sandbox ausgewählt oder
* eventuell wurde die Scorecard nicht für den ausführenden Benutzer freigegeben.

Vergewissern Sie sich, dass sich der ausführende Benutzer bei der Sandbox des richtigen Customer Journey Analytics anmelden kann und dass die Scorecard freigegeben wurde.
