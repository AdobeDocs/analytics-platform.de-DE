---
title: Erfahren Sie mehr über die Veröffentlichung von Customer Journey Analytics-Zielgruppen - Übersicht
description: Erfahren Sie mehr über das Konzept der Zielgruppenveröffentlichung in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 43%

---

# Zielgruppenveröffentlichung - Übersicht

Sie können jetzt Zielgruppen, die beim Customer Journey Analytics an das Echtzeit[Kundenprofil in Adobe Experience Platform erkannt wurden, erstellen ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) in veröffentlichen, um sie zum Targeting und zur Personalisierung zu verwenden.

Das Veröffentlichen von Zielgruppen bietet eine klare Möglichkeit, die in Customer Journey Analytics enthaltenen Einblicke zu aktivieren und entsprechende Maßnahmen zu ergreifen. Zu diesen Maßnahmen zählen:

* Verwenden der Zielgruppe für eine Journey in Adobe Journey Optimizer.
* Exportieren der Zielgruppe zu einem Drittanbieter über ein Experience Platform-Ziel.
* Anreicherung des Echtzeit-Kundenprofils mit nützlichen Attributen, die aus ereignisbasierten Daten in Customer Journey Analytics abgeleitet wurden.
* Dies alles geschieht mit minimaler Latenz nach der Publikation der Zielgruppe. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-components/audiences/publish#latency)
* Veröffentlichen einmaliger oder wiederkehrender Zielgruppen.

Die Zielgruppen, die Sie im Customer Journey Analytics erstellen, müssen nicht auf Datensätzen basieren, die für das Profil aktiviert sind. Sie können Verlaufsdaten in Experience Platform aufnehmen, ohne verknüpfte Datensätze und Schemata für Profile zu aktivieren. Verwenden Sie diese Datensätze dann, um relevante Zielgruppen im Customer Journey Analytics zu ermitteln, und veröffentlichen Sie diese Zielgruppen zur Aktivierung im Echtzeit-Kundenprofil im Experience Platform.

## Wichtige Terminologie

**Zielgruppe**: Ein Satz oder eine Liste von Identitäten, die sowohl einen Namespace als auch eine spezifische ID für diesen Namespace haben. Zielgruppen können aus Adobe Experience Platform und Anwendungen, die darauf aufsetzen (z. B. Customer Journey Analytics), transportiert werden. Zielgruppen können gemischte Namespaces enthalten.

**Filter**: Ein Regelsatz, mit dem bei der Auswertung eines Datensatzes über einen bestimmten Zeitraum eine Teilmenge von Daten erzeugt wird. Bei der Erstellung einer Zielgruppe kann ein Filter verwendet werden, wenn auch andere unterstützende Services genutzt werden. Filter werden in Customer Journey Analytics definiert und verwaltet.

**Filter** versus **Segmente**: Beim Customer Journey Analytics wird nicht das Konzept *Segmente* verwendet, sondern *Filter*. Bei beiden handelt es sich zwar um einen Regelsatz, der eine ähnliche Logik enthalten kann, das erzeugte Ergebnis ist jedoch ein anderes. Ein Filter wird verwendet, um einen Datensatz für Analysezwecke einzugrenzen. Ein Segment wird verwendet, um eine Liste von Identitäten zu erstellen, die zur Aktivierung verwendet werden können. Segmente erzeugen Zielgruppen im Echtzeit-Kundenprofil, Filter (allein) dagegen nicht. Beim Customer Journey Analytics von Zielgruppenveröffentlichungen wird ein Customer Journey Analytics-Filter verwendet, um eine Zielgruppe zu erstellen, die vom Echtzeit-Kundenprofil genutzt werden kann.

## Zugriffsberechtigung

* Administratoren erhalten automatisch die Berechtigung **[!UICONTROL Zielgruppenveröffentlichung]** in Adobe Admin Console.

* Admins und Produktprofil-Admins können einzelnen Benutzenden die Berechtigungen **[!UICONTROL Zielgruppenerstellung]** und **[!UICONTROL Zielgruppenansicht]** gewähren. Weitere Informationen finden Sie unter [Zugriffskontrolle auf Benutzerebene](/help/technotes/access-control.md#user-level-access).

* Admins benötigen außerdem die Berechtigung **[!UICONTROL Profile verwalten]** in Adobe Experience Platform.

## Data Governance und Einverständnis

Wenn Sie eine Zielgruppe in Customer Journey Analytics veröffentlichen, werden die mit den in der Zielgruppe verwendeten Feldern verknüpften Data Governance-Beschriftungen und -Richtlinien aufgezeichnet.  Wenn die Zielgruppe in einem Adobe Experience-Programm aktiviert wird, sind alle zugehörigen Data Governance-Beschriftungen und -Richtlinien für diese Zielgruppe verfügbar und es kann eine geeignete Durchsetzung angewendet werden. [Weitere Informationen über Einverständnis](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=de#consent-policy).

## Nächste Schritte

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)
* [Verwalten von Audiences](/help/components/audiences/manage.md)
