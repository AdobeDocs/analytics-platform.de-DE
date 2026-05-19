---
title: Sitzungseinstellungen
description: Erfahren Sie mehr über die Einstellungen in einer Datenansicht, mit denen Sie die Länge einer Sitzung definieren und den Trigger festlegen können, eine neue Sitzung einzuleiten
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
autotag-review: '2026-05-19T08:57:43.886Z'
TQID: 'https://experienceleague.adobe.com/79GGBxPwVb2uQytFBwgAP2QTd57VbjXuwQqq4oKGGUY'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 62%

---

# Sitzungseinstellungen {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="Datenvorschau"
>abstract="Vergleicht die Daten dieser Datenansicht mit den Daten der Verbindung. Der Prozentsatz der Vorschau basiert auf der Gesamtzahl in der Verbindung aus den **letzten 90 Tagen**.<br><br/>Wenn die Vorschau nicht geladen wird, wird Ihre Verbindung möglicherweise noch aufgestockt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


In Customer Journey Analytics können Sie eine Sitzung auf jede beliebige Art und Weise definieren, die der Interaktion von Personen mit Ihren digitalen Erlebnissen entspricht. Die Sitzungseinstellungen werden in einer Datenansicht konfiguriert.

Definitionen von Sitzungseinstellungen sind zerstörungsfrei und verändern die zugrunde liegenden Daten nicht. Sie können mehrere Datenansichten (jede mit ihrer spezifischen Definition von Sitzungseinstellungen) als Grundlage für Ihre Workspace-Projekte einrichten.

So definieren Sie den Kontext einer Sitzung innerhalb einer Datenansicht:

1. Wählen **[!UICONTROL Datenansichten]** optional unter **[!UICONTROL Datenverwaltung]** in der Hauptnavigation der Benutzeroberfläche von Customer Journey Analytics aus.

1. Erstellen Sie eine neue oder bearbeiten Sie eine vorhandene Datenansicht. Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](create-dataview.md).

1. Wählen Sie die Registerkarte **[!UICONTROL Einstellungen]** aus. Unter [!UICONTROL Sitzungseinstellungen]:

   1. Geben Sie einen Wert für ein **[!UICONTROL Sitzungs-Timeout]** in [!UICONTROL Minute(n)], [!UICONTROL Stunde(n)], [!UICONTROL Tag(en) ] oder [!UICONTROL Woche(n)] ein. Durch das Sitzungs-Timeout ist festgelegt, wie lange eine Sitzung inaktiv sein kann (es treten keine Ereignisse auf), bevor eine neue Sitzung gestartet wird.

      Verwenden Sie ein kurzes Sitzungs-Timeout (z. B. 30 Minuten), wenn Sie hauptsächlich Online-Interaktionen analysieren möchten. Wenn Sie beispielsweise analysieren, ob Profile, die Ihre Online-Store-Produktseiten besucht haben, Produkte zum Warenkorb hinzugefügt oder sogar online gekauft haben.

      Verwenden Sie einen langes Sitzungs-Timeout (z. B. 3 Monate), wenn Sie Online- und Offline-Daten kombinieren und analysieren möchten, ob Kundinnen bzw. Kunden, die eines oder mehrere Ihrer Produkte gekauft haben, innerhalb der ersten drei Monate nach dem Kauf Ihr Kontaktzentrum angerufen haben.

   1. Wählen Sie ein Segment aus dem Dropdown **[!UICONTROL Menü]** Segmente hinzufügen“ aus, wenn Sie eine Datenansicht segmentieren möchten. Alternativ können Sie ein Segment aus ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmente]** in den linken Bereich auf der **[!UICONTROL _Segment hier ablegen_]** ziehen.

      Es werden nur die Segmente aufgelistet, die freigegeben sind, auf die Sie Zugriff haben und die basierend auf den Komponenten, die Sie für die Datenansicht definiert haben, ausgewertet werden können.

   1. Wählen Sie eine Metrik aus dem **[!UICONTROL Neue Sitzung mit einer Metrik beginnen]** Dropdown-Menü . Alternativ können Sie eine Metrik aus ![Ereignis](/help/assets/icons/Event.svg) **[!UICONTROL Metriken]** im linken Bereich des **[!UICONTROL _Hier ablegen_]** ziehen. Die ausgewählte Metrik definiert den Beginn einer neuen Sitzung. Sie können mehr als eine Metrik definieren.

      Sie können eine beliebige Metrik verwenden, um eine neue Sitzung zu definieren. Angenommen, Sie möchten jedes Mal, wenn ein Profil Ihre Mobile App startet, eine neue Sitzung definieren. In **[!UICONTROL Datenansicht]** > **[!UICONTROL Komponenten]** definieren Sie eine Komponente des Typs Metrik namens **[!UICONTROL Launch]**, die auf einem **[!UICONTROL appInteraction]****[!UICONTROL Name]** Schemafeld basiert. Darüber hinaus geben Sie die Metrikkomponente **[!UICONTROL Launch]** an, damit der Wert nur gezählt wird, wenn der Wert `launch` entspricht.

      ![App-Interaktionsmetrik – Komponente „Starts“](assets/component-launches.png)

      Anschließend ziehen Sie per Drag-and-Drop oder wählen **[!UICONTROL die Metrik]** Launch“ als Metrik aus, um eine neue Sitzung zu definieren.

      ![Sitzungseinstellungen – Starts](assets/session-settings-launches-metric.png)



1. Wählen Sie **[!UICONTROL Speichern]** oder **[!UICONTROL Speichern und beenden]**, um die Definitionen der Sitzungseinstellungen zu speichern.
