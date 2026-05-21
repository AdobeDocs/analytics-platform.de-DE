---
title: Eingeschränkte Beschriftungen in Report Builder
description: Erfahren Sie mehr über eingeschränkte Beschriftungen in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: f2ef16dc-055a-4bb7-baa5-7039653f3966id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 39%

---

# Eingeschränkte Beschriftungen in Report Builder

Im Allgemeinen werden die Einstellungen für die Data Governance in Customer Journey Analytics von Experience Platform übernommen. Die Integration zwischen Customer Journey Analytics und Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler Customer Journey Analytics-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt werden, können im Workflow für Customer Journey Analytics-Datenansichten angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzende, die Metriken und Dimensionen aus sensiblen Feldern erstellen. Weiterführende Informationen über Datensätze finden Sie in der [Datensatzübersicht](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/overview)

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Labels hinzugefügt, die Benutzende darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Mit dieser Integration können Sie die Compliance verwalten. Datenverantwortliche in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Dadurch können Ihre Customer Journey Analytics-Benutzenden die Daten sicherer nutzen, da sie wissen, dass sie mit den von den Datenverantwortlichen festgelegten Richtlinien übereinstimmen.

Weitere Informationen finden Sie unter [Customer Journey Analytics und Data Governance](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)

## Eingeschränkte Daten anzeigen

In Customer Journey Analytics werden zwei von Adobe definierte Richtlinien angezeigt, die sich auf die Berichterstellung, den Download und die Freigabe auswirken:

* Analytics erzwingen-Richtlinie
* Download erzwingen-Richtlinie

Komponenten, die diesen Richtlinien unterliegen, sind ausgegraut und haben ein ![InfoOutline](/help/assets/icons/InfoOutline.svg)-Symbol. Wenn Sie den Mauszeiger über das Infosymbol bewegen, wird ein Hinweis angezeigt, der Folgendes angibt: **[!UICONTROL Auf dieses Feld wurden Richtlinien angewendet, die die Verwendung dieser Daten verbieten]**.

Weitere Informationen finden Sie unter [Kennzeichnungen und Richtlinien](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance).


![Der Hinweis zu verbotenen Datennutzungen.](assets/restricted-label.png){zoomable="yes"}


## Aktualisieren von Berichten mit eingeschränkten Daten

Wenn ein Anwender einen Report Builder-Bericht mit Datenelementen erstellt hat, die später eingeschränkt werden, wird bei der Aktualisierung des Berichts eine Fehlermeldung angezeigt.

![Die Fehlermeldung, die angezeigt wird, nachdem Datenelemente später eingeschränkt wurden.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
