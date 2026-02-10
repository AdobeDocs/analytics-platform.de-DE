---
title: Beschriftungen und Richtlinien
description: Erfahren Sie, wie sich in Adobe Experience Platform definierte Datenbeschriftungen und Richtlinien auf Datenansichten und Berichte in Customer Journey Analytics auswirken.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 99%

---

# Beschriftungen und Richtlinien

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Label zur Datennutzung](https://experienceleague.adobe.com/de/docs/experience-platform/data-governance/labels/reference) für einige oder alle Elemente im Datensatz erstellen. Sie können diese Beschriftungen und Richtlinien in Customer Journey Analytics anzeigen.

Die folgenden Beschriftungen sind für Customer Journey Analytics von besonderem Interesse:

* Die Beschriftung `C8` – **[!UICONTROL Keine Messung]**. Diese Beschriftung bedeutet, dass Daten nicht für Analysen auf den Websites oder in Anwendungen Ihres Unternehmens verwendet werden können.

* Das Label `C12` – **[!UICONTROL Kein allgemeiner Datenexport]**. Auf diese Weise gekennzeichnete Schemafelder können nicht aus CJA exportiert oder heruntergeladen werden (über Reporting, Export, API usw.)

>[!NOTE]
>
>Datennutzungskennzeichnungen werden nicht automatisch in zugeordnete Datensätze übertragen. Sie können jedoch manuell hinzugefügt werden.

Die Beschriftung an sich bedeutet nicht, dass diese Datennutzungskennzeichnungen erzwungen werden. Dafür werden Richtlinien verwendet. Sie erstellen Ihre Richtlinien mithilfe der [Experience Platform-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-platform/data-governance/policies/user-guide) oder über die [Richtlinien-Service-API](https://experienceleague.adobe.com/de/docs/experience-platform/data-governance/api/overview) in Experience Platform.

Unter Experience Platform sind zwei von Adobe definierte Richtlinien verfügbar, die sich auf Customer Journey Analytics auswirken und Berichte und Datenexporte beeinflussen können:

* Die Richtlinie **[!UICONTROL Nutzungsanalyse und benutzerbasierte Messung beschränken]** mit dem Label `C8` und
* die Richtlinie **[!UICONTROL Datenexport beschränken]** mit dem Label `C12`.

## Anzeigen von Daten-Labeln in Datenansichten von Customer Journey Analytics

Daten-Label, die von Ihnen oder anderen Benutzenden in Experience Platform erstellt wurden, werden an drei Stellen in der Benutzeroberfläche der Datenansichten angezeigt:

| Standort | Beschreibung |
| --- | --- |
| Informationsschaltfläche in einem Schemafeld | Durch Klicken auf diese Schaltfläche wird angegeben, welche [!UICONTROL Datennutzungsbezeichnungen] derzeit auf ein Feld angewendet werden:<p>![](assets/data-label-left.png) |
| Rechte Leiste unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) | Alle [!UICONTROL Datennutzungsbezeichnungen] sind hier aufgeführt:<p>![](assets/data-label-right.png) |
| Hinzufügen von Datenbeschriftungen als Spalte | Sie können [!UICONTROL Datennutzungsbezeichnungen] als Spalte zu den [!UICONTROL Enthaltene Komponenten] Spalten in Datenansichten hinzufügen. Klicken Sie einfach auf das Symbol für die Spaltenauswahl und wählen Sie **[!UICONTROL Labels zur Datennutzung]** aus:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtern nach Data-Governance-Labels in Datenansichten

Wählen Sie im Editor für Datenansichten das Symbol [!UICONTROL Filter] in der linken Spur aus und filtern Sie die Komponenten der Datenansichten nach **[!UICONTROL Data Governance]** und dem Typ der **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Klicken **[!UICONTROL Anwenden]**, um zu sehen, an welche Komponenten Beschriftungen angehängt sind.

## Filtern nach Data Governance-Richtlinien in Datenansichten

Sie können überprüfen, ob eine Richtlinie (z. B. eine von Ihnen erstellte Richtlinie mit dem Namen **[!UICONTROL Analytics erzwingen]**) aktiviert ist. Außerdem können Sie überprüfen, ob diese Richtlinie die Verwendung bestimmter Datenansichtselemente von Customer Journey Analytics für Analysen oder Datenexporte blockiert.

Wählen Sie erneut das [!UICONTROL Filtersymbol] in der linken Leiste aus und klicken Sie unter **[!UICONTROL Data Governance]** auf **[!UICONTROL Richtlinien]**:

![Filtern Sie die eingeschlossenen Komponenten nach Liste mit ausgewählten Optionen „Nutzungsanalyse und benutzerbasierte Messung beschränken“](assets/filter-policies.png)

Klicken Sie auf **[!UICONTROL Anwenden]**, um zu sehen, welche Richtlinien aktiviert sind.

## Wie sich aktivierte Richtlinien auf Datenansichten auswirken

Wenn eine oder mehrere Richtlinien mit C8- oder C12-Labeln aktiviert sind, können Schemakomponenten, auf die bestimmte Daten-Label angewendet wurden, nicht zu Datenansichten hinzugefügt werden.

Diese Komponenten sind in der Liste [!UICONTROL Schemafelder] in der linken Leiste ausgegraut:

![Ausgegraute Komponenten und die Richtlinienmeldung, dass Richtlinien auf dieses Feld angewendet wurden, um die Verwendung der Daten zu beschränken](assets/component-greyed.png)

Sie können auch keine Datensicht speichern, die gesperrte Felder enthält.

Seien Sie vorsichtig, wenn Sie versuchen, Zugriffs- und-Data Governance-Labels (über Richtlinien) in Experience Platform auf Felder oder Feldergruppen anzuwenden, für die Sie in Ihrer Datenansicht bereits Komponenten definiert haben. Möglicherweise wird dieses Dialogfeld angezeigt.

![Verstoß](assets/violation.png)

Sie müssen zunächst den Verstoß beheben (z. B. die Komponenten aus der Datenansicht entfernen).


>[!MORELIKETHIS]
>
>[Herunterladen sensibler Daten](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Was sind eingeschränkte Beschriftungen in Report Builder?](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


