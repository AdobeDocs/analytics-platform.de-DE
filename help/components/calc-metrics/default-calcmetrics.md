---
description: Adobe bietet verschiedene berechnete Metriken, die Sie verwenden können. Auf dieser Seite werden diese Metriken und die vorgesehenen Verwendungszwecke aufgelistet.
title: Berechnete Metrikvorlagen
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 8%

---

# Berechnete Metrikvorlagen

Customer Journey Analytics bietet die folgenden Vorlagen für berechnete Metriken, die die häufigsten Anwendungsfälle abdecken. Diese von der Adobe definierten berechneten Metriken werden durch ein kleines ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) -Logo gekennzeichnet. Um diese Metriken schnell zu filtern, wählen Sie ![Beschriftung](/help/assets/icons/Label.svg) **[!UICONTROL Adobe-Vorlage]** im [Komponentenfilter](/help/components/overview.md#filter) aus.

| Name der berechneten Metrik | Beschreibung<br/>Formel |
|---------|----------|
| **[!UICONTROL Sitzungsstartrate]** | Der Prozentsatz, zu dem ein Dimensionselement beim ersten Ereignis einer Sitzung aufgetreten ist.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [!UICONTROL Sitzungsstarts] [Standardkomponente](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen.</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungsstarts** ![divide](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg) **Sitzungen** **)** |
| **[!UICONTROL Besuchszeit pro Person]** | Die durchschnittliche Zeit, die eine Person mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die Standardkomponente [!UICONTROL Besuchszeit (Sekunden)] [ ](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen. Der Filter Letztes Sitzungsereignis ausschließen wird auf die Metrik für Personen angewendet. Der Filter schließt das letzte Ereignis jeder Sitzung in einem Datensatz aus. Dieser Ausschluss kann Ihnen dabei helfen, das Benutzerverhalten zu analysieren, das zu einem Ereignis oder einer Aktion führt, z. B. einem Kauf oder einer Formularübermittlung, während die endgültige Aktion selbst ausgeschlossen wird.</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Besuchszeit (Sekunden)** ![Aufteilen](/help/assets/icons/Divide.svg) ![Segmentierung](/help/assets/icons/Segmentation.svg) **Letztes Sitzungsereignis ausschließen(** ![Ereignis](/help/assets/icons/Event.svg) **Personen )** |
| **[!UICONTROL Sitzungen pro Person]** | Die durchschnittliche Anzahl von Sitzungen pro Person.<p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungen** ![teilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg) **Personen** **)** |
| **[!UICONTROL Zeit pro Sitzung]** | Die durchschnittliche Zeit, die eine Person pro Sitzung mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die Standardkomponente [!UICONTROL Besuchszeit (Sekunden)] [ ](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen. Der Filter Letztes Sitzungsereignis ausschließen wird auf die Metrik Sitzungen angewendet. Der Filter schließt das letzte Ereignis jeder Sitzung in einem Datensatz aus. Dieser Ausschluss kann Ihnen dabei helfen, das Benutzerverhalten zu analysieren, das zu einem Ereignis oder einer Aktion führt, z. B. einem Kauf oder einer Formularübermittlung, während die endgültige Aktion selbst ausgeschlossen wird.</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Besuchszeit (Sekunden)** ![Aufteilen](/help/assets/icons/Divide.svg) ![Segmentierung](/help/assets/icons/Segmentation.svg) **Letztes Sitzungsereignis ausschließen(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungen )** |
| **[!UICONTROL Sitzungsendrate]** | Der Prozentsatz, zu dem ein Dimensionselement beim letzten Ereignis einer Sitzung aufgetreten ist. <p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [!UICONTROL Sitzungsende] [Standardkomponente](/help/data-views/component-reference.md) in Ihre [Datenansicht](/help/data-views/create-dataview.md) aufnehmen.</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungsende** ![teilen](/help/assets/icons/Divide.svg) ![Ereignis](/help/assets/icons/Event.svg) **Sitzungen** **)** |

{style="table-layout:auto"}
