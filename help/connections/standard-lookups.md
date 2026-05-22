---
title: Hinzufügen von Standardsuchen zu Ihren Datensätzen
description: Erfahren Sie, wie Sie mit Standardsuchen die Berichterstellung in Customer Journey Analytics um nützliche Dimensionen erweitern können.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
feature: Connections
role: Admin
TQID: https://experienceleague.adobe.com/QSgHLiPoLQyr0DzEvWfSt535YR6Kch-XhWUyPXOO6gU
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 42%

---

# Hinzufügen von Standardsuchen zu Ihren Datensätzen

>[!IMPORTANT]
>
>Standardsuchen sind nur für Analytics-Quell-Connector-Datenquellen in Customer Journey Analytics verfügbar. Sie können sie mit standardmäßigen Adobe Analytics-Implementierungen, mit dem [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) oder mit den Datenerfassungs-APIs von Experience Platform verwenden.
>

Anhand von Standardsuchen (auch als von Adobe bereitgestellte Suchen bekannt) kann Customer Journey Analytics Berichte zu bestimmten Dimensionen/Attributen erstellen, die nicht für sich genommen, aber bei der Verknüpfung mit anderen Daten nützlich sind. Dies können beispielsweise Attribute von Smartphones oder Tablets und Attribute von Betriebssystem- und Browser-Dimensionen wie etwa die Versionsnummern von Browsern sein. Eine „Standardsuche“ ähnelt einem Lookup-Datensatz. Standardsuchen sind auf alle CX Enterprise-Organisationen anwendbar. Sie werden automatisch auf alle Ereignis-Datensätze angewendet, die bestimmte XDM-Schemafelder enthalten (die jeweiligen Felder finden Sie unten). Für jeden Schemaspeicherort, den Adobe klassifiziert, ist ein Standardsuchdatensatz vorhanden.

Im herkömmlichen Adobe Analytics werden diese Dimensionen eigenständig angezeigt. In Customer Journey Analytics hingegen müssen Sie diese Dimensionen beim Erstellen von Datenansichten aktiv einbeziehen. Im Verbindungs-Workflow wählen Sie einen Datensatz aus, der mit einem Schlüssel für die Standardsuche gekennzeichnet ist. In der Datenansichts-Benutzeroberfläche werden automatisch alle Dimensionen der Standardsuche einbezogen, die für Berichte verfügbar sind. Die Lookup-Dateien werden automatisch aktualisiert und stehen für alle Regionen und Accounts zur Verfügung. Sie werden in regionsspezifischen Organisationen gespeichert, die dem Kunden zugeordnet sind.

## Verwenden von Standardsuchen mit Analytics Source Connector-Datensätzen

Datensätze für die Standardsuche werden zum Zeitpunkt der Berichterstellung automatisch angewendet. Wenn Sie den Analytics-Quell-Connector verwenden und eine Dimension einbringen, für die Adobe eine Standardsuche bereitstellt, wird diese Standardsuche automatisch angewendet. Wenn ein Ereignis-Datensatz XDM-Felder enthält, können Standardsuchen darauf angewendet werden.

<!--
### Specific IDs that need to be populated

The following IDs need to be populated in the specific XDM mixins for this functionality to work:

* Environment Details Mixin – device/typeID value populated - Must match Device Atlas IDs and will populate device data.
* Adobe Analytics ExperienceEvent Template Mixin or Adobe Analytics ExperienceEvent Full Extension Mixin with analytics/environment/browserIDStr and analytics/environment/operatingSystemIDStr. Both must match the Adobe IDs and  populate browser and OS data, respectively.

You need these mixins with the three IDs populated (device/typeID, environment/browserIDStr, and environment/operatingSystemIDStr). The lookup dimensions will then be pulled automatically by Customer Journey Analytics and will be available in the Data View.

The catch here is that they can only populate those IDs today if they have a direct relationship with Device Atlas. They are Device Atlas IDs, and they provide an API to allow a customer to look them up. This is a significant hurdle, and we may just want to take the reference to this capability out of the product documentation until we have a productized way to expose the Device Atlas ID lookup functionality.
-->

### Verfügbare Standardsuchfelder

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Bericht zu Dimensionen der Standardsuche

Um Berichte zu Dimensionen der Standardsuche in Adobe zu erstellen, müssen Sie eine oder mehrere dieser Dimensionen hinzufügen, wenn Sie eine [Datenansicht](/help/data-views/data-views.md) in Customer Journey Analytics erstellen. In **[!UICONTROL Datenansicht]** > **[!UICONTROL Komponenten]**:

1. Wählen Sie **[!UICONTROL Schemafelder]** aus dem Dropdown-Menü in der linken Leiste aus.
1. Wählen Sie **[!UICONTROL Adobe]** Suchenaus der Liste der Schemafelder-Container aus.
1. Drilldown nach **[!UICONTROL Browser]**, **[!UICONTROL Mobile]** oder **[!UICONTROL Betriebssystem]**, bis Sie die Dimension finden, die Sie hinzufügen möchten.
1. Ziehen Sie die Dimension in die Tabelle **[!UICONTROL Metriken]** oder **[!UICONTROL Dimensionen]** innerhalb der **[!UICONTROL Enthaltene Komponenten]**.

   ![Erstellen Sie eine Datenansicht, die die Liste Komponenten hinzufügen anzeigt](assets/add-standard-lookup-dimension.gif)

Anschließend können Sie die Suchdaten in Workspace verwenden:

![Freiformtabelle mit den Daten](assets/gl-reporting.png)
