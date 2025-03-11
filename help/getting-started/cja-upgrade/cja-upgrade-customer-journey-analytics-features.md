---
title: Grundlegendes zu den einzigartigen Funktionen von Customer Journey Analytics
description: Erfahren Sie mehr über Customer Journey Analytics-spezifische Funktionen
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 57%

---

# Grundlegendes zu den einzigartigen Funktionen von Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Verknüpfen von Daten aus unterschiedlichen Quellen"
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
>title="Kontaktieren der Adobe-Kundenunterstützung, um einen zusammengefügten Datensatz zu generieren"
>abstract="Wenn Sie über ein Feld verfügen, das eine Kennung enthält, die in mehreren Datensätzen vorhanden ist, aber nicht die primäre Kennung ist, können Sie diese verwenden, um einen neuen Datensatz mit einer konsistenten Kennung zu generieren."

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
>abstract="Adobe empfiehlt für zielgruppenbasierte Anwendungsfälle die Integration mit Adobe Real-time CDP. Die Integration mit Audience Manager ist möglich, ist aber nur eine kurzfristige Lösung."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

In der folgenden Liste sind nur die Customer Journey Analytics-Funktionen aufgeführt, die beim Upgrade berücksichtigt werden müssen. Eine umfassende Liste der Adobe Analytics-Funktionen, die vollständig, teilweise oder nicht in Customer Journey Analytics unterstützt werden, finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/aa-vs-cja/cja-aa.md).

Überlegen Sie, welche der folgenden Customer Journey Analytics-Funktionen Sie beim Upgrade auf Customer Journey Analytics übernehmen möchten:

| Customer Journey Analytics-Funktion | Funktion |
|---------|----------|
| [Verknüpfen von Web-Daten mit Daten aus anderen Kanälen, z. B. Callcenter-Daten](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics wird mit der Fähigkeit von Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des [Experience-Datenmodells (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Adobe Analytics konzentriert sich hauptsächlich auf Web-basierte und Mobile-Analysedaten, wobei verschiedene Funktionen für den [Datenimport](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=de) zur Verfügung stehen. |
| [Treffer aus anderen Datensätzen mithilfe einer benutzerdefinierten Dimension zusammenfügen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Mit Customer Journey Analytics können Sie [Daten aus mehreren Report Suites so kombinieren](/help/connections/combined-dataset.md), als bildeten sie eine einzige Report Suite in Adobe Analytics. |
| [Integration mit Adobe Real-time CDP](/help/components/audiences/audiences-overview.md) | Sie können [Zielgruppen erstellen und veröffentlichen](/help/components/audiences/audiences-overview.md) die in Customer Journey Analytics im Echtzeit-Kundenprofil in Adobe Experience Platform zum Targeting und zur Personalisierung verwendet werden. |
| [Integration mit Adobe Target (A4T)](/help/integrations/at.md) | Mit dem Target-Reporting in Customer Journey Analytics können [ Adobe Target-Aktivitäten ](/help/integrations/at.md) in Customer Journey Analytics messen und Berichte dazu erstellen. Adobe empfiehlt jedoch die Integration mit Adobe Journey Optimizer für Personalisierungs-Anwendungsfälle. |
| [Integration mit Adobe Journey Optimizer](/help/integrations/ajo.md) | Sie können die von Journey Optimizer generierten Daten so konfigurieren[ dass eine erweiterte Analyse in Customer Journey Analytics durchgeführt ](/help/integrations/ajo.md). |
| [Integration mit Adobe Audience Manager](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Sie können [Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform freigeben](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Für zielgruppenbasierte Anwendungsfälle empfiehlt Adobe jedoch die Integration mit Adobe Real-time CDP. |
