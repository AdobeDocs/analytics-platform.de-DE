---
title: Komponenteneinstellungen für Optionen für keinen Wert
description: Bestimmen Sie, wie eine Dimension verarbeitet werden soll, wenn sie leer ist.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: ht
source-wordcount: '227'
ht-degree: 100%

---

# Komponenteneinstellungen für Optionen für keinen Wert

Mit Optionen für keinen Wert können Sie festlegen, wie Analysis Workspace Situationen handhabt, in denen ein Ereignis in einem Datensatz eine Metrik enthält, die Dimension jedoch keinen Wert enthielt. Sie können den Namen dieses Dimensionselements auswählen, es vollständig ausblenden oder es sogar als tatsächlichen Wert behandeln.

![Keine Wertoptionen](../assets/no-value-options.png)

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Falls angezeigt, „Kein Wert“ abrufen] | Ein Textfeld, mit dem Sie das Dimensionselement **[!UICONTROL Kein Wert]** in etwas anderes umbenennen können. |
| [!UICONTROL Standardmäßig nicht „Kein Wert“ anzeigen] | Zeigt diesen Wert im Reporting nicht an. Metrikereignisse, die nicht an diese Dimension gebunden sind, sind im Bericht nicht sichtbar. |
| [!UICONTROL Standardmäßig „Kein Wert“ anzeigen] | Zeigt diesen Wert im Reporting an. |
| [!UICONTROL „Kein Wert“ als Wert behandeln] | Ersetzt leere Werte in den Daten durch den Text, den Sie unter [!UICONTROL Falls angezeigt, „Kein Wert“ abrufen] angegeben haben. Wenn Sie beispielsweise Mobilgerätetypen als Dimension haben, können Sie das Element **[!UICONTROL Kein Wert]** in „Desktop“ umbenennen. Beim Ändern dieses Felds in einen benutzerdefinierten Wert wird dieser benutzerdefinierte Wert als legitimer Zeichenfolgenwert behandelt. Wenn Sie also z. B. den Wert „Rot“ in dieses Feld eingeben, werden alle Instanzen der Zeichenfolge „Rot“, die in den Daten selbst vorkommen, auch unter demselben von Ihnen angegebenen Zeileneintrag erscheinen. |

{style=&quot;table-layout:auto&quot;}
