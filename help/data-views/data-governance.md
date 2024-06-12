---
title: Beschriftungen und Richtlinien
description: Erfahren Sie, wie sich in Adobe Experience Platform definierte Datenbeschriftungen und Richtlinien auf Datenansichten und Berichte in Customer Journey Analytics auswirken.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 950c121e6c889e202f048d4a33e8fecde3cd9efe
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 67%

---

# Beschriftungen und Richtlinien

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) für einige oder alle Elemente im Datensatz. Sie können diese Beschriftungen und Richtlinien in Customer Journey Analytics anzeigen.

Die folgenden Beschriftungen sind für Customer Journey Analytics von besonderem Interesse:

* Die Beschriftung `C8` – **[!UICONTROL Keine Messung]**. Diese Beschriftung bedeutet, dass Daten nicht für Analysen auf den Websites oder in Anwendungen Ihres Unternehmens verwendet werden können.

* Die `C12` label - **[!UICONTROL Kein allgemeiner Datenexport]**. Auf diese Weise gekennzeichnete Schemafelder können nicht aus CJA exportiert oder heruntergeladen werden (über Reporting, Export, API usw.)

>[!NOTE]
>
>Datennutzungskennzeichnungen werden nicht automatisch in zugeordnete Datensätze übertragen. Sie können jedoch manuell hinzugefügt werden.

Die Beschriftung an sich bedeutet nicht, dass diese Datennutzungskennzeichnungen erzwungen werden. Dafür werden Richtlinien verwendet. Sie können Ihre Richtlinien mit dem [Experience Platform-Benutzeroberfläche](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) oder über die [Policy Service-API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) in Experience Platform.

In Customer Journey Analytics werden zwei von Adobe definierte Richtlinien angezeigt, die sich auf Reporting sowie Download/Freigabe auswirken:

* **[!UICONTROL Analytics erzwingen]**-Richtlinie
* **[!UICONTROL Download erzwingen]**-Richtlinie

## Anzeigen von Datenbeschriftungen in Datenansichten von Customer Journey Analytics

Datenbeschriftungen, die Sie oder andere Benutzer unter Experience Platform erstellt haben, werden an drei Stellen in der Benutzeroberfläche &quot;Datenansichten&quot;angezeigt:

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

Sie können überprüfen, ob eine Richtlinie (z. B. eine mit dem Namen &quot;Analytics erzwingen&quot;) aktiviert ist und ob diese Richtlinie die Verwendung bestimmter Customer Journey Analytics-Datenansichtselemente für Analysen blockiert.

Klicken Sie erneut auf das [!UICONTROL Filtersymbol] in der linken Leiste und klicken Sie unter **[!UICONTROL Data Governance]** auf **[!UICONTROL Richtlinien]**:

![Eingeschlossene Komponenten nach Liste gefiltert, mit ausgewählter Option „Analytics erzwingen“](assets/filter-policies.png)

Klicks **[!UICONTROL Anwenden]** , um zu sehen, welche Richtlinien aktiviert sind.

## Wie sich aktivierte Richtlinien auf Datenansichten auswirken

Wenn die Richtlinie **[!UICONTROL Analyse erzwingen]** aktiviert ist, können die Schemakomponenten mit bestimmten Datenbeschriftungen (z. B. C8) nicht zu Datenansichten hinzugefügt werden.

Diese Komponenten sind in der linken Leiste grau dargestellt [!UICONTROL Schemafelder] list:

![Ausgegraute Komponenten und die Richtlinienmeldung, dass Richtlinien auf dieses Feld angewendet wurden, um die Verwendung der Daten zu beschränken](assets/component-greyed.png)

Sie können auch keine Datensicht speichern, die gesperrte Felder enthält.

Gehen Sie bei der Anwendung von Zugriffs- und Data Governance-Beschriftungen auf Felder oder Feldergruppen in Experience Platform vorsichtig vor. Für diese Felder und Feldergruppen sind in Ihrer Datenansicht bereits Komponenten definiert. Möglicherweise wird dieses Dialogfeld angezeigt.

![Verletzung](assets/violation.png)

Sie müssen zunächst den Verstoß beheben (z. B. die Komponenten aus der Datenansicht entfernen).


>[!MORELIKETHIS]
>
>[Herunterladen sensibler Daten](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Was sind eingeschränkte Beschriftungen in Report Builder?](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


