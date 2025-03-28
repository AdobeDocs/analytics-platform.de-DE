---
title: Konfigurieren von Inhaltsanalysen
description: Eine Übersicht über die Konfiguration von Inhaltsanalysen
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 40739525db8061f32a4cef1a27177fedad9bc458
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 1%

---

# Konfigurieren von Inhaltsanalysen

{{release-limited-testing}}

Die Konfiguration von Content Analytics besteht aus den folgenden Schritten:

![Konfiguration der Inhaltsanalyse](../assets/aca-configuration.svg){zoomable="yes"}

1. Verwenden Sie den Content Analytics [Konfigurationsassistenten](guided.md) um Sie durch alle Schritte zu führen, die zum Einrichten der Voraussetzungen für eine Konfiguration von Content Analytics erforderlich sind. Sie können Ihre Konfigurationen jederzeit speichern und zu einem späteren Zeitpunkt zurückkehren.
1. Sobald Sie mit den Konfigurationswerten vertraut sind, können Sie die Konfiguration implementieren. Diese Implementierung erstellt alle erforderlichen Artefakte, basierend auf den Konfigurationen im Assistenten.
1. Nur wenn Sie [ Tags](manual.md)Eigenschaft manuell veröffentlichen, wird die Content Analytics-Konfiguration effektiv bereitgestellt und die Datenerfassung gestartet.

1. Sie können nur einige kleinere Änderungen an einer implementierten Konfiguration mithilfe des Assistenten [Geführte Konfiguration](guided.md) vornehmen. Ändern Sie beispielsweise die [Datenansicht](/help/data-views/data-views.md).
1. Mit der Erweiterung [ Adobe Content Analytics können Sie weitere Änderungen an einer implementierten Konfiguration ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) der zugehörigen Tags-Eigenschaft vornehmen.
1. Nur wenn [ die Tags](manual.md)Eigenschaft manuell erneut veröffentlichen, werden die Konfigurationsänderungen effektiv bereitgestellt und die Datenerfassung, basierend auf Ihren Änderungen, wird gestartet.


## Voraussetzungen

Stellen Sie vor dem Konfigurieren von Content Analytics sicher, dass die folgenden Voraussetzungen erfüllt sind:

* Sie haben den Benutzeragenten und die IP-Adresse für den in Content Analytics verwendeten Feature Service auf die Zulassungsliste gesetzt. Die zu konfigurierende Benutzeragenten-Zeichenfolge lautet: <code>AdobeFeatureIzation/1.0</code>.
* Sie verfügen über die Rolle eines Customer Journey Analytics-Produktadministrators mit den zusätzlichen Berechtigungen zum Verwalten von Verbindungen und Datenansichten.
* Sie müssen über [Berechtigungen für die Datenerfassung“ ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}. Diese Berechtigungen bestehen aus:
   * [Experience Platform-Berechtigungen](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Berechtigungen für die Datenerfassung in Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank" }
* Sie haben die folgenden wichtigen Konfigurationsoptionen sorgfältig geprüft:

   * Ihre Site ist für das Reporting zu Erlebnissen geeignet. Ein ordnungsgemäßes Reporting zu Erlebnissen ist nur möglich, wenn die folgenden Bedingungen erfüllt sind:
      * Sie können auf den Site-Inhalt nur über öffentlich zugängliche URLs zugreifen. Für den Zugriff auf die Website sind keine personalisierten Token, Cookies oder andere Mechanismen erforderlich, die nicht über die URL verfügbar sind.
      * Die Seiten auf Ihrer Site sind mit der Seiten-URL reproduzierbar, und Sie wissen, welche optionalen URL-Parameter Erlebnisse fördern.
   * Sie haben ein klares Verständnis dafür, für welche Seiten Sie Inhaltsinteraktionsanalysen und Einblicke erfassen möchten.
   * Sie haben ein klares Verständnis dafür, für welche (Art von) Assets Sie die Inhaltsinteraktionsanalyse und -einblicke erfassen möchten.


## Zugriffssteuerung

>[!IMPORTANT]
>
>Es gibt keine Content Analytics-Berechtigung, die Sie konfigurieren können, um den Content Analytics-Zugriff für einzelne Benutzende oder Benutzergruppen zu aktivieren oder zu deaktivieren.
>

Um einem Benutzer oder einer Benutzergruppe Zugriff auf Content Analytics zu gewähren, müssen Sie dem Benutzer oder der Benutzergruppe Zugriff auf eine oder mehrere [Datenansichten) gewähren, die für Content Analytics konfiguriert ](guided.md#data-view).

Dieser Zugriff beinhaltet:

1. Die für Content Analytics aktivierte Datenansicht ist als Teil der Datenansichtsberechtigungen für ein bestimmtes Customer Journey Analytics-Produktprofil enthalten.
1. Dieses spezifische Customer Journey Analytics-Produktprofil ist eines der Produktprofile, die dem Benutzer oder der Benutzergruppe zugewiesen sind.

>[!MORELIKETHIS]
>
>* [Geführte Konfiguration](guided.md)
>* [Manuelle Konfiguration](manual.md)
>* [Zugriffskontrolle](/help/technotes/access-control.md)
>
