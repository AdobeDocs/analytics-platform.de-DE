---
title: Veröffentlichung von CJA-Zielgruppen – Überblick
description: Erfahren Sie mehr über das Konzept der Zielgruppenveröffentlichung in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 7b86650cd3475a203d597baeec2ec2152e082b10
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 83%

---

# Überblick über die Veröffentlichung von CJA-Zielgruppen

Sie können jetzt Zielgruppen erstellen und veröffentlichen, die in Customer Journey Analytics (CJA) in [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) (RTCDP) in Adobe Experience Platform für das Targeting und die Personalisierung von Kunden.

Das Veröffentlichen von Zielgruppen bietet die Möglichkeit, die in CJA vorhandenen Einblicke zu aktivieren und entsprechende Maßnahmen zu ergreifen. Zu diesen Maßnahmen zählen:

* Verwenden der Zielgruppe für eine Journey in Adobe Journey Optimizer.
* Exportieren der Zielgruppe zu einem Drittanbieter über ein Experience Platform-Ziel.
* Anreichern des Echtzeit-Kundenprofils mit nützlichen Attributen, die aus ereignisbasierten Daten in CJA abgeleitet wurden.
* Dies alles geschieht mit minimaler Latenz nach der Publikation der Zielgruppe. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=de#latency)
* Veröffentlichen einmaliger oder wiederkehrender Zielgruppen.

Die Zielgruppen, die Sie in Customer Journey Analytics erstellen, müssen nicht auf für Profile aktivierten Datensätzen basieren. Sie können historische Daten in Experience Platform erfassen, ohne verknüpfte Datensätze und Schemas für Profile zu aktivieren. Verwenden Sie dann diese Datensätze, um relevante Zielgruppen in CJA zu ermitteln und diese Zielgruppen in der RTCDP-Experience Platform zu Aktivierungszwecken zu veröffentlichen.

## Wichtige Terminologie

**Zielgruppe**: Ein Satz oder eine Liste von Identitäten, die sowohl einen Namespace als auch eine spezifische ID für diesen Namespace haben. Zielgruppen können aus Adobe Experience Platform und Anwendungen, die darauf aufsetzen (z. B. CJA), extrahiert werden. Zielgruppen können gemischte Namespaces enthalten.

**Filter**: Ein Regelsatz, mit dem bei der Auswertung eines Datensatzes über einen bestimmten Zeitraum eine Teilmenge von Daten erzeugt wird. Bei der Erstellung einer Zielgruppe kann ein Filter verwendet werden, wenn auch andere unterstützende Services genutzt werden. Filter werden in CJA definiert und verwaltet.

**Filter** im Vergleich zu **Segmenten**: CJA verwendet „Filter“ anstelle von „Segmenten“. Bei beiden handelt es sich zwar um einen Regelsatz, der eine ähnliche Logik enthalten kann, das erzeugte Ergebnis ist jedoch ein anderes. Ein Filter wird verwendet, um einen Datensatz für Analysezwecke einzugrenzen. Ein Segment wird verwendet, um eine Liste von Identitäten zu erstellen, die zur Aktivierung verwendet werden können. Segmente erzeugen Zielgruppen im Echtzeit-Kundenprofil, Filter (allein) dagegen nicht. Bei der Veröffentlichung von CJA-Zielgruppen wird ein CJA-Filter verwendet, um eine Zielgruppe zu erstellen, die vom Echtzeit-Kundenprofil genutzt werden kann.

## Zugriffsberechtigungen

* Administratoren erhalten automatisch die Berechtigung **[!UICONTROL Zielgruppenveröffentlichung]** in Adobe Admin Console.

* Administratoren können diese Berechtigung für einzelne Benutzer erteilen.

* Admins benötigen außerdem die Berechtigung **[!UICONTROL Profile verwalten]** in Adobe Experience Platform.

## Data Governance und Einverständnis

Wenn Sie eine Zielgruppe in CJA veröffentlichen, werden die mit den in der Zielgruppe verwendeten Feldern verknüpften Data Governance-Beschriftungen und -Richtlinien aufgezeichnet.  Wenn die Zielgruppe in einem Adobe Experience-Programm aktiviert wird, sind alle zugehörigen Data Governance-Beschriftungen und -Richtlinien für diese Zielgruppe verfügbar und es kann eine geeignete Durchsetzung angewendet werden. [Weitere Informationen über Einverständnis](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=de#consent-policy).

## Nächste Schritte

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)
* [Verwalten von Audiences](/help/components/audiences/manage.md)
