---
description: Erfahren Sie mehr über Metriktyp und Attribution
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 304b8d85767d89ee60a6fb37a128194f60ca89d4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 91%

---

# Metriktyp und Attribution

Sie können den Metriktyp und das [Attributionsmodell](#attribution-models) für eine Metrik in der Definition einer berechneten Metrik konfigurieren.

1. Wählen Sie in der Metrikkomponente ![Einstellung](/help/assets/icons/Setting.svg) aus.
1. Im Popup-Dialogfeld:

   ![Metriktyp und Attribution](assets/cm-type-alloc.png)

   * Geben Sie den **[!UICONTROL Metriktyp]** an:

     | Metriktyp | Definition |
     |---|---|
     | **[!UICONTROL Standard]** | Wenn eine Formel aus einer einzelnen Standardmetrik besteht, zeigt sie die gleichen Daten wie das nicht berechnete Metrikgegenstück an. Standardmetriken eignen sich zum Erstellen berechneter Metriken, die speziell für die einzelnen Zeileneinträge gelten. <p>Zum Beispiel teilt ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]** die Bestellungen für diesen spezifischen Zeileneintrag durch die Anzahl der Sitzungen für diesen Spezifischen Zeileneintrag. |
     | **[!UICONTROL Gesamtsumme]** | Verwenden Sie die **[!UICONTROL Gesamtsumme]** für den Berichtszeitraum in jedem Zeileneintrag. Wenn eine Formel aus einer einzelnen Gesamtsummenmetrik besteht, zeigt sie dieselbe Gesamtsummenzahl für jeden Zeileneintrag an. Gesamtsummenmetriken sind hilfreich, wenn Sie berechnete Metriken erstellen möchten, die mit den Gesamtdaten verglichen werden. <p>Zum Beispiel zeigt ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Bestellungen]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen insgesamt]** den Anteil der Bestellungen für alle Sitzungen und nicht nur die Sitzungen für den speziellen Zeileneintrag an. In diesem Beispiel geben Sie die **[!UICONTROL Gesamtsumme]** für die ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen]**-Metrik in Ihrer berechneten Metrik an, die sie automatisch in ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sitzungen insgesamt]** umwandelt. |

   * Geben Sie die **[!UICONTROL Attribution]** an.

      1. Sie haben folgende Möglichkeiten:

         * Deaktivieren Sie **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden]**, um das standardmäßige Spalten-Attributionsmodell Letztkontakt mit einem Lookback-Fenster von 30 Tagen zu verwenden.
         * Aktivieren Sie **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden]**. Im Dialogfeld **[!UICONTROL Attributionsmodell mit Spalten]**

            * Wählen Sie **[!UICONTROL Modell]** unter [Attributionsmodelle](#attribution-models) aus.
            * Wählen Sie einen **[!UICONTROL Container]** aus den Optionen [Container](#container) aus.
            * Wählen Sie ein **[!UICONTROL Lookback]** Fenster) unter den Optionen [Lookback-Fenster](#lookback-window) aus. Wenn Sie **[!UICONTROL Benutzerdefinierte Zeit]** auswählen, können Sie den Zeitraum in **[!UICONTROL Minute(n)]** bis zu **[!UICONTROL Quartal(en)]** definieren.

      1. Wählen Sie **[!UICONTROL Anwenden]**, um das nicht standardmäßige Attributionsmodell anzuwenden. Wählen Sie zum Abbrechen die Option „Abbrechen“ aus.

     Wenn Sie bereits ein nicht standardmäßiges Attributionsmodell definiert haben, wählen Sie **[!UICONTROL Bearbeiten]** aus, um die Auswahl zu ändern.

Siehe [Beispiel](#example) für ein Beispiel der Verwendung eines Attributionsmodells, eines Containers und eines Lookback-Fensters.


## Attributionsmodelle {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Nicht standardmäßiges Attributionsmodell verwenden"
>abstract="Aktivieren Sie ein nicht standardmäßiges Attributionsmodell für die ausgewählte Metrik."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modell"
>abstract="Wählen Sie ein Attributionsmodell für die Metrik aus."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Letztkontakt"
>abstract="Die Credits gehen zu 100 % an den letzten Dimensionswert, den eine Besucherin bzw. ein Besucher gesehen hat."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Erstkontakt"
>abstract="Die Credits gehen zu 100 % an den ersten Dimensionswert, den eine Besucherin bzw. ein Besucher gesehen hat."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="Die Credits werden gleichmäßig auf alle Dimensionswerte verteilt."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Beitrag"
>abstract="Die Credits gehen zu 100 % an jeden Dimensionswert, der von einer Besucherin oder einem Besucher gesehen wird.<br/>Spaltensummen werden erhöht."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Selber Kontakt"
>abstract="Die Credits werden nur für Dimensionswerte erteilt, die bei demselben Ereignis wie die Konversion auftreten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Selber Kontakt"
>abstract="Die Credits werden nur für Dimensionswerte erteilt, die bei demselben Ereignis wie die Konversion auftreten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U-Form"
>abstract="Die Credits gehen zu zu 40 % an die erste Dimension, zu 40 % an die letzte und zu 20 % an die mittlere."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J-Kurve"
>abstract="Die Credits gehen zu zu 60 % an den letzten Dimensionswert, zu 20 % an den ersten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J-Kurve"
>abstract="Die Credits gehen zu zu 60 % an den letzten Dimensionswert, zu 20 % an den ersten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="Umgekehrtes J"
>abstract="Die Credits gehen zu 60 % an den ersten Dimensionswert, zu 20 % an den letzten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="Umgekehrtes J"
>abstract="Die Credits gehen zu 60 % an den ersten Dimensionswert, zu 20 % an den letzten und zu 20 % an den mittleren."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Zeitverfall"
>abstract="Die Dimensionswerte, die einer Konversion zeitlich am nächsten sind, erhalten die meisten Credits."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Anpassen"
>abstract="Definieren Sie Ihre eigene positionsbasierte Attributionsgewichtung."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Anpassen"
>abstract="Definieren Sie Ihre eigene positionsbasierte Attributionsgewichtung."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmisch"
>abstract="Die Credits werden anhand eines statistischen Algorithmus dynamisch bestimmt."

{{attribution-models-details}}


## Container {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Container"
>abstract="Wählen Sie einen Container aus, um den gewünschten Umfang für die Attribution festzulegen."

{{attribution-container}}


## Lookback-Fenster {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Lookback-Fenster"
>abstract="Diese Einstellung bestimmt das Fenster der Datenattribution, das für jede Konversion angewendet wird."

{{attribution-lookback-window}}




## Beispiel

{{attribution-example}}

>[!MORELIKETHIS]
>
>[Attribution – Komponenteneinstellungen](/help/data-views/component-settings/attribution.md)
>&#x200B;>[Beitragsmetrik](participation-metric.md)
>

