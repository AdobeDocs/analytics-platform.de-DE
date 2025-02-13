---
description: Adobe bietet verschiedene berechnete Metriken, die Sie verwenden können. Auf dieser Seite werden diese Metriken und ihre Verwendungszwecke aufgelistet.
title: Vorlagen für berechnete Metriken
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d13f980d1fbae3f608bf64587f59dc22c3fac9ce
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 6%

---

# Vorlagen für berechnete Metriken

Customer Journey Analytics bietet die folgenden Vorlagen für berechnete Metriken, um die häufigsten Anwendungsfälle abzudecken. Diese von Adobe definierten berechneten Metriken werden durch ein kleines ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)-Logo gekennzeichnet. Um schnell nach diesen Metriken zu filtern, wählen Sie ![Beschriftung](/help/assets/icons/Label.svg) **[!UICONTROL Adobe-]** im [Komponentenfilter](/help/components/overview.md#filter) aus.

| Name der berechneten Metrik | description<br/>Formula |
|---------|----------|
| **[!UICONTROL Sitzungsstartrate]** | Der Prozentsatz, zu dem ein Dimensionselement beim ersten Ereignis einer Sitzung aufgetreten ist.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die Standardkomponente[ in ](/help/data-views/component-reference.md)Datenansicht[ einbeziehen](/help/data-views/create-dataview.md).</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungsstarts** ![Trennen](/help/assets/icons/Divide.svg)![ Ereignis](/help/assets/icons/Event.svg)**** Sitzungen **)** |
| **[!UICONTROL Aufgewendete Zeit pro Person]** | Die durchschnittliche Zeit, die eine Person mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [!UICONTROL Besuchszeit (Sekunden)] ([) ](/help/data-views/component-reference.md) Ihrer [Datenansicht](/help/data-views/create-dataview.md). Der Filter Letztes Ereignis der Sitzung ausschließen wird auf die Metrik Personen angewendet. Der Filter schließt das letzte Ereignis jeder Sitzung in einem Datensatz aus. Dieser Ausschluss kann Ihnen dabei helfen, das Benutzerverhalten zu analysieren, das zu einem Ereignis oder einer Aktion führt, z. B. einem Kauf oder einer Formularübermittlung, während die endgültige Aktion selbst ausgeschlossen wird.</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Besuchszeit (Sekunden)** Trennen](/help/assets/icons/Divide.svg)![ ](/help/assets/icons/Segmentation.svg) Segmentieren **** Letztes Ereignis der Sitzung ausschließen(![](/help/assets/icons/Event.svg) Ereignis **![Personen ) )** |
| **[!UICONTROL Sitzungen pro Person]** | Die durchschnittliche Anzahl der Sitzungen pro Person.<p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungen** ![Trennen](/help/assets/icons/Divide.svg)![ Ereignis](/help/assets/icons/Event.svg)**Personen****)** |
| **[!UICONTROL Aufgewendete Zeit pro Sitzung]** | Die durchschnittliche Zeit, die eine Person pro Sitzung mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [!UICONTROL Besuchszeit (Sekunden)] ([) ](/help/data-views/component-reference.md) Ihrer [Datenansicht](/help/data-views/create-dataview.md). Der Filter Letztes Ereignis der Sitzung ausschließen wird auf die Metrik Sitzungen angewendet. Der Filter schließt das letzte Ereignis jeder Sitzung in einem Datensatz aus. Dieser Ausschluss kann Ihnen dabei helfen, das Benutzerverhalten zu analysieren, das zu einem Ereignis oder einer Aktion führt, z. B. einem Kauf oder einer Formularübermittlung, während die endgültige Aktion selbst ausgeschlossen wird.</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Besuchszeit (Sekunden)** Trennen](/help/assets/icons/Divide.svg)![ ](/help/assets/icons/Segmentation.svg) Segmentierung **** Letztes Ereignis der Sitzung ausschließen(![](/help/assets/icons/Event.svg) Ereignis **![Sitzungen ) )** |
| **[!UICONTROL Sitzungsendrate]** | Der Prozentsatz, zu dem ein Dimensionselement beim letzten Ereignis einer Sitzung aufgetreten ist. <p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die Standardkomponente[ in ](/help/data-views/component-reference.md)Datenansicht[ einbeziehen](/help/data-views/create-dataview.md).</p>Zusammenfassung: **(** ![Ereignis](/help/assets/icons/Event.svg) **Sitzungsende**![Trennen](/help/assets/icons/Divide.svg)![ Ereignis](/help/assets/icons/Event.svg)**** Sitzungen **)** |
| **[!UICONTROL Websitzungen]** | Die Anzahl der Sitzungen, die auf der Website stattgefunden haben. |
| **[!UICONTROL Abschlussrate der Umfrage]** | Die Rate, mit der Personen eine Umfrage abgeschlossen haben, nachdem sie sie gestartet haben. |
| **[!UICONTROL Multi-Channel-Sitzungsrate]** | Das Verhältnis der Sitzungen, die stattfanden und mehrere Kanäle enthielten (z. B. Web-Traffic und mobiler Traffic), im Vergleich zu denen, die nur einen einzigen Kanal enthielten. |
| **[!UICONTROL Multi-Channel-Personenrate]** | Das Verhältnis der Personen, die an mehreren Kanälen teilgenommen haben, im Vergleich zu denen, die nur an einem einzigen Kanal teilgenommen haben. |
| **[!UICONTROL Mobile-App-Sitzungen]** | Die Anzahl der Sitzungen, die in der Mobile App aufgetreten sind. |
| **[!UICONTROL Web- und App-Cross-Channel-Sitzungen]** | Die Anzahl der aufgetretenen Sitzungen, die sowohl Webtraffic als auch mobilen Traffic umfassten. |
| **[!UICONTROL Anrufkosten]** | Die Gesamtkosten für Callcenter-Anrufe. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Durchschnittliche Anrufdauer]** | Die durchschnittliche Dauer von Anrufen an das Callcenter. |
| **[!UICONTROL Durchschnittliche Kosten pro Anruf]** | Die durchschnittlichen Kosten von Anrufen an das Callcenter. |
| **[!UICONTROL Durchschnittliche Punktzahl für Anrufumfragen]** | Die durchschnittliche Umfragepunktzahl bei Anrufen im Callcenter. |

{style="table-layout:auto"}
