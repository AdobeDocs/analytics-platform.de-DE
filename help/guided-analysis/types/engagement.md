---
title: Interaktionsanalyse
description: Erfahren Sie mehr über Umfang und Tiefe der Funktionsinteraktion.
feature: Adobe Product Analytics, Guided Analysis
keywords: Produktanalysen
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 6%

---

# Analyse [!UICONTROL Interaktion] {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Interaktion"
>abstract="Erfahren Sie mehr über Umfang und Tiefe der Funktionsinteraktion."

<!-- markdownlint-enable MD034 -->


Die ![EngagementGraph](/help/assets/icons/EngagementGraph.svg)**[!UICONTROL Engagement]**-Analyse bietet Einblicke in die Häufigkeit der Verwendung einer Funktion im Vergleich zur Häufigkeit ihrer Verwendung. Diese Analyse funktioniert am besten, wenn mehrere Funktionen miteinander verglichen werden. Es hilft, Investitionsentscheidungen zu fördern, indem es versteht, was Ihr Kern, Ihre Leistung, einmalige und fragwürdige Funktionen sind.

Funktionen, die oben in dieser Visualisierung dargestellt werden, zeigen, dass sie häufig von interaktiven Benutzern verwendet werden. Funktionen, die rechts neben dieser Visualisierung dargestellt werden, zeigen, dass sie bei Ihren aktiven Benutzern weithin verwendet werden. Die mediane Häufigkeit, mit der ein Feature verwendet wird, teilt das Diagramm horizontal. Der mittlere Prozentsatz aktiver Benutzer teilt das Diagramm vertikal. Die Medianwerte werden basierend auf den in der Abfrage ausgewählten Ereignissen und nicht auf allen Daten berechnet.

* Funktionen oben links in der Matrix sind Ihre **Power**-Funktionen. Sie werden nicht weithin verwendet, werden aber häufig von interaktiven Benutzern verwendet.
* Funktionen oben rechts in der Matrix sind Ihre **wirkungsvollen) Funktionen** sie werden häufig verwendet und sind weit verbreitet.
* Funktionen in der unteren linken Ecke der Matrix sind Ihre **Low Impact**-Funktionen; sie werden nicht häufig verwendet oder sind nicht weit verbreitet.
* Funktionen in der rechten unteren Ecke der Matrix sind Ihre **einmaligen**. Sie werden häufig verwendet, aber nicht häufig verwendet.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)


## Anwendungsfälle

Anwendungsfälle für diese Analyse sind:

* **Interaktion nach Funktion**: Sie können eine direkte Korrelation zwischen der Interaktion und der Akzeptanz einer bestimmten Funktion herstellen. Wenn Sie wissen, welche Funktionen am häufigsten verwendet werden, können Sie feststellen, in welche Funktionen Sie weiter investieren müssen.
* **Entdecken Sie nicht ausgelastete Funktionen**: Funktionen mit wenig aktiven Benutzern, aber hoher Auslastung können auf eine leistungsstarke Funktion hinweisen, eine, die nützlich ist, aber von der breiteren Bevölkerung nicht entdeckt oder verwendet wird. Erwägen, die Auffindbarkeit dieser Funktionen zu verbessern, damit sie von mehr Benutzenden genutzt werden können.
* **Beliebte Funktionen verbessern**: Funktionen mit vielen aktiven Benutzern, aber geringer Nutzung können darauf hinweisen, dass eine Funktion häufig angefordert, aber nicht ausreichend genutzt wird. Diese Situationen bieten die Möglichkeit, von Ihren Benutzern mehr darüber zu erfahren, welche Verbesserungen die Funktion für sie wertvoller machen würden.
* **Funktionsbasierte Segmente erstellen**: Auf diese Weise wird die Funktionsnutzung angezeigt, um zusätzliche Analysemöglichkeiten zu eröffnen. Erstellen Sie ein Segment für einen beliebigen Punkt im Diagramm, um weiter in diese Benutzergruppe einzutauchen und diese Erkenntnisse auf Ihre Benutzerinteraktionsstrategie anzuwenden.
* **Funktionsübernahme durch A/B** Tests: Vergleichen Sie die Nutzung mehrerer Funktionen durch verschiedene Benutzergruppen. Fügen Sie Segmente in der Abfrageleiste hinzu, um den Unterschied bei der Funktionsnutzung zwischen wichtigen Benutzergruppen zu ermitteln.

## Benutzeroberfläche

Siehe [Schnittstelle](../overview.md#interface) für einen Überblick über die Oberfläche der geführten Analyse. Die folgenden Einstellungen sind für diese Analyse spezifisch:

### Abfrageleiste

Mit der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Ereignisse]**: Die Ereignisse, die Sie messen möchten. Jedes Ereignis stellt die Verwendung einer bestimmten Funktion dar und wird als Punkt innerhalb der Matrix angezeigt. Sie können bis zu zehn Ereignisse einbeziehen. Der Median wird anhand der ausgewählten Ereignisse berechnet.
* **[!UICONTROL Wird gezählt als]**: Entlang der X-Achse können Sie den durchschnittlichen Prozentsatz der täglichen, wöchentlichen, monatlichen oder vierteljährlichen aktiven Benutzenden messen. Die Y-Achse passt die durchschnittlichen Zeiten pro Benutzerin bzw. Benutzer basierend auf der Auswahl der X-Achse automatisch an.
* **[!UICONTROL Segmente]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der grafisch dargestellten Punkte im Diagramm und in den Tabellenzeilen. Sie können bis zu drei Segmente einschließen.

>[!TIP]
>
>Wenn mehrere Ereignisse die Verwendung einer einzelnen Funktion darstellen, können Sie ein neues Ereignis ableiten, das die Funktion in Datenansichten darstellt.

### Diagrammeinstellungen

Die [!UICONTROL Interaktion]-Analyse bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Mediane]**: Legen Sie fest, wo die Mittellinien angezeigt werden und wie die grafisch dargestellten Punkte mit diesen Medianen in Beziehung stehen.
   * **[!UICONTROL Standard]**: Zeigt den absoluten Wert der Nutzung und Interaktion.
   * **[!UICONTROL Normalisiert]**: Zeigt relative Änderungen aus jedem Median an.
* **[!UICONTROL Top-Ereignisse überlagern]**: Sehen Sie sich an, wie sich Ihre Ereignisse im Vergleich zu den 20 wichtigsten Ereignissen verhalten, basierend auf der Neuigkeit und Relevanz von Unternehmen und Benutzern (derselbe Algorithmus wird auf die Ereignisauswahl in der Abfrageleiste angewendet).

### Zeitvergleich

{{apply-time-comparison}}

### Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, nach der Sie Trenddaten anzeigen möchten. Diese Analyse behandelt [!UICONTROL Intervall] ähnlich wie [!UICONTROL Zählt als] in der Abfrageleiste. Stündlich aktive Benutzer werden nicht unterstützt.
* **[!UICONTROL Date]**: Das Start- und Enddatum. Rollierende Datumsbereichsvorgaben und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Sie können auch den Kalenderselektor verwenden, um einen festen Datumsbereich auszuwählen.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
