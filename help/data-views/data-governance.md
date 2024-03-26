---
title: Beschriftungen und Richtlinien
description: Erfahren Sie, wie sich in Adobe Experience Platform definierte Datenbeschriftungen und Richtlinien auf Datenansichten und Berichte in Customer Journey Analytics auswirken.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '493'
ht-degree: 100%

---

# Beschriftungen und Richtlinien

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Datennutzungskennzeichnungen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=de) für einige oder alle Elemente im Datensatz erstellen. Sie können diese Beschriftungen und Richtlinien in Customer Journey Analytics anzeigen.

Die folgenden Beschriftungen sind für Customer Journey Analytics von besonderem Interesse:

* Die Beschriftung `C8` – **[!UICONTROL Keine Messung]**. Diese Beschriftung bedeutet, dass Daten nicht für Analysen auf den Websites oder in Anwendungen Ihres Unternehmens verwendet werden können.

* Die Beschriftung `C12` – **[!UICONTROL Kein allgemeiner Datenexport]**. Auf diese Weise gekennzeichnete Schemafelder können nicht aus CJA exportiert oder heruntergeladen werden (über Reporting, Export, API usw.)

>[!NOTE]
>
>Datennutzungskennzeichnungen werden nicht automatisch in zugeordnete Datensätze übertragen. Sie können jedoch manuell hinzugefügt werden.

Die Beschriftung an sich bedeutet nicht, dass diese Datennutzungskennzeichnungen erzwungen werden. Dafür werden Richtlinien verwendet. Sie erstellen Ihre Richtlinien mithilfe der [Experience Platform-Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=de) oder über die [Richtlinien-Service-API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=de) in Experience Platform.

In Customer Journey Analytics werden zwei von Adobe definierte Richtlinien angezeigt, die sich auf Reporting sowie Download/Freigabe auswirken:

* **[!UICONTROL Analytics erzwingen]**-Richtlinie
* **[!UICONTROL Download erzwingen]**-Richtlinie

## Anzeigen von Datenbeschriftungen in Datenansichten von Customer Journey Analytics

Datenbeschriftungen, die in Experience Platform erstellt wurden, werden an drei Stellen in der Benutzeroberfläche der Datenansichten angezeigt:

| Standort | Beschreibung |
| --- | --- |
| Informationsschaltfläche in einem Schemafeld | Durch Klicken auf diese Schaltfläche wird angegeben, welche [!UICONTROL Datennutzungsbezeichnungen] derzeit auf ein Feld angewendet werden:<p>![](assets/data-label-left.png) |
| Rechte Leiste unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) | Alle [!UICONTROL Datennutzungsbezeichnungen] sind hier aufgeführt:<p>![](assets/data-label-right.png) |
| Hinzufügen von Datenbeschriftungen als Spalte | Sie können [!UICONTROL Datennutzungsbezeichnungen] als Spalte zu den [!UICONTROL Enthaltene Komponenten] Spalten in Datenansichten hinzufügen. Klicken Sie einfach auf das Symbol für die Spaltenauswahl und wählen Sie **[!UICONTROL Datennutzungsbezeichnungen]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtern nach Data Governance-Beschriftungen in Datenansichten

Klicken Sie im Editor für Datenansichten auf das Symbol [!UICONTROL Filter] in der linken Spur und filtern Sie die Komponenten der Datenansichten nach **[!UICONTROL Data Governance]** und dem Typ der **[!UICONTROL Beschriftung]**:

![](assets/filter-labels.png)

Klicken **[!UICONTROL Anwenden]**, um zu sehen, an welche Komponenten Beschriftungen angehängt sind.

## Filtern nach Data Governance-Richtlinien in Datenansichten

Sie können überprüfen, ob eine Richtlinie aktiviert ist, die die Verwendung bestimmter Datenansichtselemente von Customer Journey Analytics für Analyse- oder Exportzwecke blockiert.

Klicken Sie erneut auf das [!UICONTROL Filtersymbol] in der linken Leiste und klicken Sie unter **[!UICONTROL Data Governance]** auf **[!UICONTROL Richtlinien]**:

![Eingeschlossene Komponenten nach Liste gefiltert, mit ausgewählter Option „Analytics erzwingen“](assets/filter-policies.png)

Klicken Sie auf **[!UICONTROL Anwenden]**, um zu sehen, welche Richtlinien aktiviert sind.

## Wie sich aktivierte Richtlinien auf Datenansichten auswirken

Wenn die Richtlinie **[!UICONTROL Analyse erzwingen]** aktiviert ist, können die Schemakomponenten mit bestimmten Datenbeschriftungen (z. B. C8) nicht zu Datenansichten hinzugefügt werden.

Diese Komponenten sind in der Liste [!UICONTROL Schemafelder] in der linken Leiste ausgegraut:

![Ausgegraute Komponenten und die Richtlinienmeldung, dass Richtlinien auf dieses Feld angewendet wurden, um die Verwendung der Daten zu beschränken](assets/component-greyed.png)

Sie können auch keine Datensicht speichern, die gesperrte Felder enthält.

>[!MORELIKETHIS]
>[Herunterladen sensibler Daten](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>[Was sind eingeschränkte Beschriftungen in Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=de)


