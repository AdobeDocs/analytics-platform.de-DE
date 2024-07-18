---
title: Was sind eingeschränkte Beschriftungen in Report Builder
description: Beschreibt eingeschränkte Beschriftungen in Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 48f5e9d6c5d3a33a5bae45e841eb8364b7172876
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 70%

---

# Eingeschränkte Beschriftungen in Report Builder

Im Allgemeinen werden alle Einstellungen in Bezug auf die Data Governance in Customer Journey Analytics von Adobe Experience Platform übernommen. Die Integration zwischen Customer Journey Analytics und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler Daten von Customer Journey Analytics und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Datenansichts-Workflow von Customer Journey Analytics angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen. Weiterführende Informationen über Datensätze finden Sie in der [Datensatzübersicht](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=de)

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Beschriftungen hinzugefügt, die Benutzer darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Datenverantwortliche in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Daher können Ihre Customer Journey Analytics-Benutzer Daten in dem Bewusstsein, dass sie den von Data Stewards definierten Richtlinien entsprechen, sicherer verwenden.

Weitere Informationen finden Sie unter [Customer Journey Analytics und Data Governance](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=de)

## Anzeigen eingeschränkter Daten in Report Builder

Unter Customer Journey Analytics werden zwei Adobe definierte Richtlinien angezeigt, die sich auf das Reporting, Herunterladen und Freigeben auswirken:

* Analytics erzwingen-Richtlinie
* Download erzwingen-Richtlinie

Komponenten, die von diesen Richtlinien betroffen sind, sind grau ausgeblendet. Wenn Sie den Mauszeiger über eine Komponente bewegen, auf die eine Richtlinie angewendet wurde, wird ein Hinweis angezeigt, der Folgendes angibt: **Auf dieses Feld wurden Richtlinien angewendet, die die Verwendung dieser Daten untersagen.** Weitere Informationen finden Sie unter [Beschriftungen und Richtlinien](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=de).

![Der Richtlinienvermerk, der die verbotene Verwendung von Daten angibt.](assets/rb-restricted-label.png)

## Aktualisieren von Berichten mit eingeschränkten Daten

Wenn ein Anwender einen Report Builder-Bericht mit Datenelementen erstellt hat, die später eingeschränkt werden, wird bei der Aktualisierung des Berichts eine Fehlermeldung angezeigt.

![Die Fehlermeldung, die angezeigt wird, nachdem Datenelemente später eingeschränkt wurden.](assets/error-restricted-data.png)
