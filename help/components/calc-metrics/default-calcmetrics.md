---
description: Adobe bietet verschiedene berechnete Metriken, die Sie verwenden können. Auf dieser Seite sind diese Metriken und ihre Verwendungszwecke aufgelistet.
title: Vorlagen für berechnete Metriken
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
TQID: https://experienceleague.adobe.com/-jngIXgXeFZZkfL5jSHLuX8ZmcWU5rIfLqb26ovn6QY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 83%

---

# Vorlagen für berechnete Metriken

Customer Journey Analytics bietet die folgenden Vorlagen für berechnete Metriken, um die häufigsten Anwendungsfälle abzudecken. Diese von Adobe definierten berechneten Metriken werden durch ein kleines ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)-Logo gekennzeichnet. Um diese Metriken schnell zu filtern, wählen Sie ![Beschriftung](/help/assets/icons/Label.svg) **[!UICONTROL Adobe-]** im [Komponentenfilter](/help/components/overview.md#filter) aus.

| Name der berechneten Metrik | Formel-<br/>beschreibung |
|---------|----------|
| **[!UICONTROL Sitzungsanfangsrate]** | Der Prozentsatz, zu dem ein Dimensionselement im ersten Ereignis einer Sitzung aufgetreten ist.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [Standardkomponente](/help/data-views/component-reference.md) [!UICONTROL Sitzung beginnt] in Ihrer[Datenansicht](/help/data-views/create-dataview.md) einbeziehen.</p>Zusammenfassung: **(** ![Event](/help/assets/icons/Event.svg) **Sitzung beginnt** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sitzungen** **)** |
| **[!UICONTROL Aufgewendete Zeit pro Person]** | Die durchschnittliche Zeit, die eine Person mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [Standardkomponente](/help/data-views/component-reference.md) [!UICONTROL Aufgewendete Zeit (Sekunden)] in Ihrer[Datenansicht](/help/data-views/create-dataview.md) einbeziehen. Das letzte Ereignis der Sitzung mit dem Segmentausschluss wird auf die Metrik „Personen“ angewendet. Das Segment schließt das letzte Ereignis jeder Sitzung in einem Datensatz aus. Dieser Ausschluss kann dabei helfen, das Benutzerverhalten zu analysieren, das zu einem Ereignis oder einer Aktion führt, z. B. einem Kauf oder einer Formularübermittlung, während die endgültige Aktion selbst ausgeschlossen wird.</p>Zusammenfassung: **(** ![Event](/help/assets/icons/Event.svg) **Aufgewendete Zeit (Sekunden)** ![Divide](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Letztes Ereignis der Sitzung ausschließen(** ![Event](/help/assets/icons/Event.svg) **Personen ) )** |
| **[!UICONTROL Sitzungen pro Person]** | Die durchschnittliche Anzahl der Sitzungen pro Person.<p>Zusammenfassung: **(** ![Event](/help/assets/icons/Event.svg) **Sitzungen** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Personen** **)** |
| **[!UICONTROL Aufgewendete Zeit pro Sitzung]** | Die durchschnittliche Zeit, die eine Person pro Sitzung mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [Standardkomponente](/help/data-views/component-reference.md) [!UICONTROL Aufgewendete Zeit (Sekunden)] in Ihrer[Datenansicht](/help/data-views/create-dataview.md) einbeziehen. Das Segment Ausschließen des letzten Ereignisses einer Sitzung wird auf die Metrik Sitzungen angewendet. Das Segment schließt das letzte Ereignis jeder Sitzung in einem Datensatz aus. Dieser Ausschluss kann dabei helfen, das Benutzerverhalten zu analysieren, das zu einem Ereignis oder einer Aktion führt, z. B. einem Kauf oder einer Formularübermittlung, während die endgültige Aktion selbst ausgeschlossen wird.</p>Zusammenfassung: **(** ![Event](/help/assets/icons/Event.svg) **Aufgewendete Zeit (Sekunden)** ![Divide](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Letztes Ereignis der Sitzung ausschließen(** ![Event](/help/assets/icons/Event.svg) **Sitzungen ) )** |
| **[!UICONTROL Sitzungsendrate]** | Der Prozentsatz, zu dem ein Dimensionselement im letzten Ereignis einer Sitzung aufgetreten ist. <p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die [Standardkomponente](/help/data-views/component-reference.md) [!UICONTROL Sitzung endet] in Ihrer[Datenansicht](/help/data-views/create-dataview.md) einbeziehen.</p>Zusammenfassung: **(** ![Event](/help/assets/icons/Event.svg) **Sitzung endet** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **Sitzungen** **)** |
| **[!UICONTROL Web-Sitzungen]** | Die Anzahl der Sitzungen, die auf der Website stattgefunden haben. |
| **[!UICONTROL Abschlussrate der Umfrage]** | Die Rate, mit der Personen eine Umfrage abgeschlossen haben, nachdem sie sie gestartet haben. |
| **[!UICONTROL Rate der Sitzungen in mehreren Kanälen]** | Das Verhältnis der Sitzungen mit mehreren Kanälen (z. B. Webtraffic und mobiler Traffic) im Vergleich zu denen mit nur einem einzigen. |
| **[!UICONTROL Rate der Personen mit mehreren Kanälen]** | Das Verhältnis der Personen, die an mehreren Kanälen teilgenommen haben, im Vergleich zu denen, die nur an einem einzigen Kanal teilgenommen haben. |
| **[!UICONTROL App-Sitzungen]** | Die Anzahl der Sitzungen in der App. |
| **[!UICONTROL Kanalübergreifende Web- und App-Sitzungen]** | Die Anzahl der Sitzungen mit Webtraffic und mobilem Traffic. |
| **[!UICONTROL Anrufkosten]** | Die Gesamtkosten für Callcenter-Anrufe. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Durchschnittliche Anrufdauer]** | Die durchschnittliche Dauer von Anrufen beim Callcenter. |
| **[!UICONTROL Durchschnittliche Kosten pro Anruf]** | Die durchschnittlichen Kosten von Anrufen beim Callcenter. |
| **[!UICONTROL Durchschnittliches Ergebnis der Anrufumfrage]** | Das durchschnittliche Umfrageergebnis bezüglich Anrufen beim Callcenter. |

{style="table-layout:auto"}
