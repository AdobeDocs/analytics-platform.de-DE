---
title: Hinzufügen von Quantum Metric Friction-Ereignissen zu Customer Journey Analytics
description: Fügen Sie den Verhaltensdaten von Customer Journey Analytics erfasste Friktionsereignisse der Quantum-Metrik hinzu, um den Einblicken in CJA Tiefe zu verleihen.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 1%

---

# Hinzufügen von Quantum Metric Friction-Ereignissen zu Customer Journey Analytics

Die Quantum-Metrik erfasst Friktionsereignisse wie Langsamkeit beim Laden der Seite, Seitenladefehler, Wutklicks und mehr. Diese Ereignisse können als komplementäre Ereignisse auf der Benutzer-Journey an Customer Journey Analytics übergeben werden. Mit diesen kombinierten Daten können Sie die Auswirkungen von Reibung auf nachgelagerte Metriken besser verstehen.

## Voraussetzungen:

Dieser Anwendungsfall hat zwei Anforderungen:

* Sie müssen über eine Berechtigung für das **Dev Ops**-Paket von Quantum Metric verfügen.
* Sie müssen Tags in der Adobe Experience Platform-Datenerfassung verwenden.

## Schritt 1: Erstellen Sie ein Schemafeld für Quantum Metric-Reibungsereignisse

Dieser Anwendungsfall erfordert ein dediziertes Schemafeld, an das Daten gesendet werden. Sie können dieses Feld an einer beliebigen Stelle in Ihrem Schema erstellen und nach Belieben benennen. Beispielwerte werden bereitgestellt, wenn Ihr Unternehmen keine Voreinstellung für Name oder Speicherort hat.

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie **[!UICONTROL Datenerfassung]** > **[!UICONTROL Schemata]**.
1. Wählen Sie das gewünschte Schema aus der Liste aus.
1. Wählen Sie das ![Feldsymbol hinzufügen](/help/assets/icons/AddCircle.svg) neben dem gewünschten Objekt aus. Beispiel: neben `Implementation Details`.
1. Geben Sie auf der rechten Seite den gewünschten [!UICONTROL Name] ein. Zum Beispiel `qmErrorName`.
1. Geben Sie den gewünschten [!UICONTROL Anzeigenamen] ein. Zum Beispiel `Quantum Metric error name`.
1. Wählen Sie [!UICONTROL Typ] als **[!UICONTROL Zeichenfolge]**.
1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Schritt 2: Erfassen von Reibungsereignissen mit der Quantum Metric-Tag-Erweiterung

Anweisungen [&#x200B; Einrichten Ihrer Tags für das Einschließen von Quantenmetrikdaten finden Sie unter &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/destinations/catalog/analytics/quantum-metric)Quantum Metric-Erweiterung“ im Adobe Experience Platform Destinations-Handbuch. Durch die Verwendung dieser Erweiterung werden mehr Zeilen in einen vorhandenen Datensatz übergeben.

Verwenden Sie Tags in der Adobe Experience Platform-Datenerfassung, um den Namen des Reibungsereignisses manuell festzulegen, sodass es in das XDM-Objekt aufgenommen und analysiert werden kann. Eine Möglichkeit, dies zu tun, besteht im benutzerdefinierten Code der Regel:

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

Fügen Sie dann das dynamisch festgelegte Datenelement zu Ihrem XDM-Objekt hinzu:

![Screenshot mit dem Quantenmetrik-Fehlernamen](assets/error-name.png)

## Schritt 3: Hinzufügen einer oder mehrerer Dimensionen und Metriken zur Datenansicht in Customer Journey Analytics

Bearbeiten Sie die vorhandene Datenansicht, um die Sitzungs-ID als verfügbare Dimension in Customer Journey Analytics hinzuzufügen.

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen **[!UICONTROL Datenansichten]** optional unter **[!UICONTROL Daten-Management]** im oberen Menü aus.
1. Wählen Sie die gewünschte vorhandene Datenansicht aus.
1. Suchen Sie die Liste Quantum Metric Friction Event Field auf der linken Seite und ziehen Sie sie in den Bereich Metriken in der Mitte.
1. Legen Sie im rechten Bereich die Einstellung [Werte einschließen/ausschließen](/help/data-views/component-settings/include-exclude-values.md) auf die gewünschten Reibungsereignisse fest, die Sie verfolgen möchten. Sie können derselben Metrik mehrere Reibungsereignisse hinzufügen, um sie zu kombinieren. Sie können auch eine weitere Kopie des Felds Reibungsereignisse in den Bereich Metriken ziehen, um andere Reibungsereignisse als separate Metrik zu verfolgen.
1. Nachdem Sie alle gewünschten Dimensionen und Metriken erstellt haben, klicken Sie auf **[!UICONTROL Speichern]**.
1. Eine vollständige Liste der Fehlerereignisse finden Sie in der Dokumentation zu Ihrer Quantum-Metrik. Wenn Sie weitere Fragen haben, wenden Sie sich an Ihren Kundenbetreuer von Quantum Metric oder senden Sie eine Anfrage über das [Quantum Metric Customer Request Portal](https://community.quantummetric.com/s/public-support-page).

## Schritt 4: Verwenden Sie die Dimension und Metriken für den Rest Ihrer Daten in Analysis Workspace.

Wenn Quantum Metric Friction-Ereignisdaten zusammen mit den anderen Besucherdaten erfasst werden, können Sie sie genau wie jede andere Dimension oder Metrik in Customer Journey Analytics verwenden.

1. Melden Sie sich bei &quot;[.adobe.com“ &#x200B;](https://experience.adobe.com).
1. Navigieren Sie zu Customer Journey Analytics und wählen Sie **[!UICONTROL Workspace]** im oberen Menü.
1. Wählen Sie ein vorhandenes Projekt aus oder erstellen Sie ein Projekt.
1. Erstellen Sie eine [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Ziehen Sie die gewünschten Dimensionen und Metriken zur Analyse auf die Workspace-Arbeitsfläche.

![Reibungsdiagramm](assets/friction-graph.png)

Zu den möglichen Analyseideen gehören:

* Trend von Reibungsereignisdaten im Zeitverlauf
* Fügen Sie in einer Fallout- oder funnel-Visualisierung Customer Journey Analytics-Ereignisse als einige Schritte und Quantenmetrik-Reibungsereignisse als andere hinzu. Dieser Bericht zeigt an, wo Besucherinnen und Besucher am häufigsten in Schwierigkeiten geraten.
* Erstellen und Anwenden eines Segments für Besucher, die Reibungsereignisse für eine tiefer gehende Analyse erleben
