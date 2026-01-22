---
title: Weitere Informationen zum Überblick über die Zielgruppenveröffentlichung in Customer Journey Analytics
description: Erfahren Sie mehr über das Konzept der Zielgruppenveröffentlichung in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 3f369122863df4f3fc339730ced8c193360d07c6
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 94%

---

# Überblick über die Zielgruppenveröffentlichung

<!--

>[!NOTE]
>
>Understand the difference between audience analysis and audience publishing:
>
>* **Audience analysis**: Allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. For information about audience analysis, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).
>* **Audience publishing**: Allows you to create and publish audiences discovered in Customer Journey Analytics to Adobe Experience Platform for customer targeting and personalization. 

-->

Sie können in Customer Journey Analytics verfügbare Zielgruppen erstellen und im [Echtzeit-Kundenprofil) ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) Adobe Experience Platform veröffentlichen, um sie zum Targeting und zur Personalisierung zu verwenden.

<!-- add this when Audience Analysis releases: (For information about ingesting audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).) -->

Das Veröffentlichen von Zielgruppen bietet die Möglichkeit, die in Customer Journey Analytics vorhandenen Einblicke zu aktivieren und entsprechende Maßnahmen zu ergreifen. Zu diesen Maßnahmen zählen:

* Verwenden der Zielgruppe für eine Journey in Adobe Journey Optimizer.
Weitere Informationen zum Verwenden von in Experience Platform veröffentlichten Zielgruppen finden Sie in der Dokumentation zu Journey Optimizer unter [Erste Schritte mit Zielgruppen](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences).
* Exportieren der Zielgruppe zu einem Drittanbieter über ein Experience Platform-Ziel.
* Anreichern des Echtzeit-Kundenprofils mit nützlichen Attributen, die aus ereignisbasierten Daten in Customer Journey Analytics abgeleitet wurden.
* Ausführen all dieser Vorgänge mit minimaler Latenz nach der Veröffentlichung der Zielgruppe.
Weitere Informationen finden Sie unter [Latenzaspekte](/help/components/audiences/publish.md#latency-considerations) in [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md).
* Veröffentlichen einmaliger oder wiederkehrender Zielgruppen.

Die Zielgruppen, die Sie in Customer Journey Analytics erstellen, müssen nicht auf den für das Profil aktivierten Datensätzen basieren. Sie können historische Daten in Experience Platform ohne die Aktivierung verknüpfter Datensätze und Schemata für Profile aufnehmen. Verwenden Sie diese Datensätze dann, um relevante Zielgruppen in Customer Journey Analytics zu ermitteln, und veröffentlichen Sie diese Zielgruppen zur Aktivierung im Echtzeit-Kundenprofil in Experience Platform.

## Wichtige Terminologie

**Zielgruppe**: Ein Satz oder eine Liste von Identitäten, die sowohl einen Namespace als auch eine spezifische ID für diesen Namespace haben. Zielgruppen können aus Adobe Experience Platform und Anwendungen, die darauf aufsetzen (z. B. Customer Journey Analytics), extrahiert werden. Zielgruppen können gemischte Namespaces enthalten.

**Segment**: Ein Regelsatz, mit dem bei der Auswertung eines Datensatzes über einen bestimmten Zeitraum eine Teilmenge von Daten erzeugt wird. Bei der Erstellung einer Zielgruppe kann ein Segment verwendet werden, wenn auch andere unterstützende Services genutzt werden. Segmente werden in Customer Journey Analytics definiert und verwaltet.

## Berechtigungen

* Admins erhalten automatisch die Berechtigung **[!UICONTROL Zielgruppenveröffentlichung]** in Adobe Admin Console.

* Admins und Produktprofil-Admins können einzelnen Benutzenden die Berechtigungen **[!UICONTROL Zielgruppenerstellung]** und **[!UICONTROL Zielgruppenansicht]** gewähren. Weitere Informationen finden Sie unter [Zugriffskontrolle auf Benutzerebene](/help/technotes/access-control.md#user-level-access).

* Admins benötigen außerdem die Berechtigung **[!UICONTROL Profile verwalten]** in Adobe Experience Platform.

## Data Governance und Einverständnis

Wenn Sie eine Zielgruppe in Customer Journey Analytics veröffentlichen, werden die mit den in der Zielgruppe verwendeten Feldern verknüpften Data Governance-Beschriftungen und -Richtlinien aufgezeichnet.  Wenn die Zielgruppe in einem Adobe Experience-Programm aktiviert wird, sind alle zugehörigen Data-Governance-Labels und -Richtlinien für diese Zielgruppe verfügbar und es kann eine geeignete Durchsetzung angewendet werden. [Weitere Informationen über Einverständnis](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=de#consent-policy).

## Nächste Schritte

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)
* [Verwalten von Zielgruppen](/help/components/audiences/manage.md)
