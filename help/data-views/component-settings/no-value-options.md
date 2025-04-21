---
title: Komponenteneinstellungen für Optionen für keinen Wert
description: Bestimmen Sie, wie eine Dimension verarbeitet werden soll, wenn sie leer ist.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 58%

---

# Komponenteneinstellungen für Optionen für keinen Wert {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="Keine Wertoptionen"
>abstract="Konfigurieren Sie das Standardverhalten für ein Szenario, bei dem in einer Dimension kein Wert vorhanden ist."

<!-- markdownlint-enable MD034 -->


[!UICONTROL Keine Wertoptionen] ermöglichen es Ihnen zu bestimmen, wie Analysis Workspace Situationen handhabt, in denen ein Ereignis in einem Datensatz eine Metrik enthält, die Dimension jedoch keinen Wert enthielt. Sie können den Namen dieses Dimensionselements auswählen, es vollständig ausblenden oder es sogar als tatsächlichen Wert behandeln.

![Keine Wertoptionen](../assets/no-value-options.png)

## Einstellungen {#settings}

| Einstellung | Beschreibung |
| --- | --- |
| **[!UICONTROL Falls angezeigt, „Kein Wert“ abrufen]** | Ein Textfeld, mit dem Sie das Dimensionselement **[!UICONTROL Kein Wert]** in etwas anderes umbenennen können. |
| **[!UICONTROL Standardmäßig nicht „Kein Wert“ anzeigen]** | Zeigt diesen Wert im Reporting nicht an. Metrikereignisse, die nicht an diese Dimension gebunden sind, sind im Bericht nicht sichtbar. |
| **[!UICONTROL Standardmäßig „Kein Wert“ anzeigen]** | Zeigt diesen Wert im Reporting an. |
| **[!UICONTROL „Kein Wert“ als Wert behandeln]** | (Nicht unterstützt für numerische Dimensionen) Ersetzt leere Werte in den Daten durch den Text, den Sie unter „Wenn angezeigt[!UICONTROL  „Kein Wert“ aufrufen angegeben ]. Wenn Sie beispielsweise Mobilgerätetypen als Dimension haben, können Sie das Element **[!UICONTROL Kein Wert]** in „Desktop“ umbenennen. Beim Ändern dieses Felds in einen benutzerdefinierten Wert wird dieser benutzerdefinierte Wert als legitimer Zeichenfolgenwert behandelt. Wenn Sie also z. B. den Wert „Rot“ in dieses Feld eingeben, werden alle Instanzen der Zeichenfolge „Rot“, die in den Daten selbst vorkommen, auch unter demselben von Ihnen angegebenen Zeileneintrag erscheinen. |

## Unterstützung von „Kein Wert“ für numerische Dimensionen {#numeric}

Wenn Sie einen numerischen Wert als Dimension verwenden, können Sie

* Konfigurieren der Option „Kein Wert“ in einer Datenansicht. Beachten Sie, dass alle oben gezeigten Konfigurationseinstellungen unterstützt werden, mit Ausnahme von **[!UICONTROL Kein Wert als Wert behandeln]**.
* Verwenden Sie **[!UICONTROL Einschließen von „Kein Wert“]** für numerische Dimensionen in einer Freiformtabelle in Workspace.
* Verwenden Sie im Segment Builder die Operatoren **[!UICONTROL vorhanden]** oder **[!UICONTROL nicht vorhanden]** mit numerischen Dimensionen.


>[!MORELIKETHIS]
>
>Im Folgenden finden Sie einen verwandten Blog-Beitrag zum [Umgang mit „Kein Wert“ in Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).

