---
title: Informationen zu Customer Journey Analytics-spezifischen Funktionen
description: Erfahren Sie mehr über Customer Journey Analytics-spezifische Funktionen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
TQID: https://experienceleague.adobe.com/8yBVFyHrc31-ac8XLV-aW-SWBfDZodlIXirICmdzpkY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 591
ht-degree: 100%

---

# Informationen zu Customer Journey Analytics-spezifischen Funktionen {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Verbinden von Daten aus unterschiedlichen Quellen"
>abstract="(Empfohlen) Verknüpfen Sie Daten aus verschiedenen Web-, Mobile- und Offline-Eigenschaften, um eine einzige, konsolidierte Ansicht des Kundenverhaltens zu erstellen. Diese Fähigkeit, Analysedaten aus anderen Kanälen zu kombinieren, ist der wichtigste Anwendungsfall für Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Zusammenfügen von Treffern aus mehreren Datensätzen"
>abstract="Wenn einer Ihrer Datensätze keine primäre Kennung (z. B. eine Experience Cloud-ID) aufweist, können Sie diese Daten dennoch mithilfe einer anderen Dimension, z. B. Anmeldename oder E-Mail-Adresse, zusammenfügen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Zuordnung für relevante Datensätze aktivieren"
>abstract="Wenn Sie über ein Feld verfügen, das eine Kennung enthält, die in mehreren Datensätzen vorhanden ist, aber nicht die primäre Kennung ist, können Sie die Daten mithilfe der Zuordnung in einen oder mehrere Datensätze einbinden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integrieren mit Real-time CDP"
>abstract="Kombinieren Sie Profildaten aus verschiedenen Quellen, um Zielgruppen und Segmente basierend auf Benutzereigenschaften zu generieren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Vorübergehendes Integrieren mit Adobe Target"
>abstract="Adobe empfiehlt für Personalisierungs-Anwendungsfälle die Integration mit Adobe Journey Optimizer. Die Integration mit Adobe Target ist möglich, ist aber nur eine kurzfristige Lösung."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integrieren mit Journey Optimizer"
>abstract="Stellen Sie Ihren Kundinnen und Kunden vernetzte, kontextuelle und personalisierte Erlebnisse bereit."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Vorübergehendes Integrieren mit Adobe Audience Manager"
>abstract="Adobe empfiehlt für zielgruppenbasierte Anwendungsfälle die Integration mit Adobe Real-time CDP. Die Integration mit Audience Manager ist zwar möglich, ist aber nur eine kurzfristige Lösung."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

In der folgenden Liste sind nur die Customer Journey Analytics-Funktionen aufgeführt, die beim Upgrade berücksichtigt werden müssen. Eine umfassende Liste der Adobe Analytics-Funktionen, die vollständig, teilweise oder nicht in Customer Journey Analytics unterstützt werden, finden Sie unter [Unterstützung der Customer Journey Analytics-Funktion](/help/getting-started/aa-vs-cja/cja-aa.md).

Überlegen Sie, welche der folgenden Customer Journey Analytics-Funktionen beim Upgrade auf Customer Journey Analytics übernommen werden sollen:

| Customer Journey Analytics-Funktion | Funktion |
|---------|----------|
| [Web-Daten mit Daten aus anderen Quellen (z. B. Daten des Kontakt-Centers) verbinden](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des [Experience-Datenmodells (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Adobe Analytics konzentriert sich hauptsächlich auf Web-basierte und Mobile-Analysedaten, wobei verschiedene Funktionen für den [Datenimport](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=de) zur Verfügung stehen. |
| [Treffer aus anderen Datensätzen mithilfe einer benutzerdefinierten Dimension zuordnen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/stitching/overview) | Mit Customer Journey Analytics können Sie [Daten aus mehreren Report Suites so kombinieren](/help/connections/combined-dataset.md), als bildeten sie eine einzige Report Suite in Adobe Analytics. |
| [Mit Adobe Real-Time CDP integrieren](/help/components/audiences/audiences-overview.md) | Sie können in Customer Journey Analytics identifizierte [Zielgruppen erstellen](/help/components/audiences/audiences-overview.md) und im Echtzeit-Kundenprofil in Adobe Experience Platform veröffentlichen, um sie zum Targeting und zur Personalisierung zu verwenden. |
| [Mit Adobe Target (A4T) integrieren](/help/integrations/at.md) | Mit dem Target-Reporting in Customer Journey Analytics können Sie [Adobe Target-Aktivitäten](/help/integrations/at.md) direkt in Customer Journey Analytics messen und Berichte dazu erstellen. Adobe empfiehlt für Personalisierungs-Anwendungsszenarien jedoch die Integration mit Adobe Journey Optimizer. |
| [Mit Adobe Journey Optimizer integrieren](/help/integrations/ajo.md) | Sie können von Journey Optimizer generierte Daten konfigurieren, um [eine erweiterte Analyse in Customer Journey Analytics durchzuführen](/help/integrations/ajo.md). |
| [Mit Adobe Audience Manager integrieren](https://experienceleague.adobe.com/de/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Sie können [Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform freigeben](https://experienceleague.adobe.com/de/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Adobe empfiehlt für zielgruppenbasierte Anwendungsfälle jedoch die Integration mit Adobe Real-time CDP. |
