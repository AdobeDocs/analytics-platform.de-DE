---
title: Verarbeitungsregeln, VISTA und Klassifizierungen vs. Datenvorbereitung für den Analytics-Quell-Connector
description: Erfahren Sie mehr über die Umwandlung von Daten mithilfe von Verarbeitungsregeln und VISTA statt mithilfe der Datenvorbereitung.
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 99%

---

# Verarbeitungsregeln, VISTA und Klassifizierungen im Vergleich zur Datenvorbereitung

[Verarbeitungsregeln und VISTA-Regeln](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html) in Adobe Analytics stellen eine Möglichkeit bereit, Daten, die an die [Datenerfassung](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=de) in Adobe Analytics übergeben werden, umzuwandeln und zu bearbeiten. Diese Umwandlungen werden im Rahmen der Datenverarbeitung in Adobe vorgenommen, bevor die Daten zu Reporting- und Analysezwecken in Adobe Analytics gespeichert werden.

Die [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) ist ein Tool, mit dem Sie zeilenbasierte Zuordnungen und Umwandlungen auf Daten anwenden können, die in [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=de) aufgenommen werden. Anschließend werden die Daten für Experience Platform-Anwendungen wie Customer Journey Analytics bereitgestellt. Die Datenvorbereitung ist in viele der Platform-[Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=de) sowie in den [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) integriert. Dieser Connector bietet eine Möglichkeit, Report Suite-Daten aus Adobe Analytics in Platform aufzunehmen.

## Weitere Umwandlung mithilfe der Datenvorbereitung {#data-prep}

Daten, die erfasst und in Adobe Analytics gespeichert werden, können durch Verarbeitungsregeln oder VISTA-Regeln oder beide umgewandelt werden. Report Suites, die dann über den Analytics-Quell-Connector an Platform weitergeleitet werden, können jedoch mithilfe der Datenvorbereitung erneut umgewandelt werden. Dies kann aus verschiedenen Gründen wünschenswert sein:

* **Beheben von Schemaunterschieden zwischen Report Suites zur Verwendung in Customer Journey Analytics und/oder RTCDP**. Beispiel: Report Suite A definiert `eVar1` als „Suchbegriff“ und Report Suite B definiert `eVar2` als „Suchbegriff“. Sie können die Datenvorbereitung verwenden, um die beiden unterschiedlichen eVars einem gemeinsamen Feld zuzuordnen, das Daten aus beiden eVars enthält. Dies ermöglicht es, [Report Suites mit verschiedenen Schemata](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html) in einer [Customer Journey Analytics-Verbindung](/help/connections/overview.md) oder zur Verwendung in [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html) zu kombinieren.
* **Zuordnen von `eVars`-Feldern zu semantisch aussagekräftigen Namen**. `eVars` und `props` aus dem Analytics-Quell-Connector werden Feldern wie _\_experience.analytics.customDimensions.eVars.eVar1_ zugeordnet. Die Datenvorbereitung kann für die Zuordnung von `eVar`- und `prop`-Feldern zu neuen Feldern verwendet werden, die aussagekräftigere Namen für Ihre Benutzenden haben oder Namen entsprechen, die aus anderen Datenquellen stammen. (Dies lässt sich auch auf andere Weise erreichen, z. B. durch Umbenennen der Felder in einer [Customer Journey Analytics-Datenansicht](/help/data-views/create-dataview.md).)
* **Allgemeines Transformieren von Daten**. Die Datenvorbereitung verfügt über Hunderte von Zuordnungsfunktionen, mit denen neue Felder basierend auf den Daten, die über den Analytics-Quell-Connector eingehen, berechnet werden können. Sie können durch Trennzeichen getrennte Felder in separate Felder aufteilen. Sie können Felder kombinieren. Sie können Zeichenfolgen bearbeiten. Sie können Informationen basierend auf regulären Ausdrücken aus einem Feld extrahieren und vieles mehr.

## Datenvorbereitung und Klassifizierung {#classifications}

Die Datenvorbereitung hat in bestimmten Situationen Überscheidungen mit [Klassifizierungen](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=de).

Beispielsweise können Sie in einem durch Trennzeichen getrennten Feld mithilfe der Datenvorbereitung dieses Feld in mehrere einzelne Felder aufteilen, ohne Klassifizierungen zu verwenden. Im Allgemeinen bieten Klassifizierungen die Möglichkeit, einem Feld Metadaten hinzuzufügen, indem eine Suchdatei hochgeladen wird, die außerhalb des Streams eingehender Analytics-Ereignisse bereitgestellt wird.

Sie können beispielsweise eine Klassifizierungsdatei hochladen, in der SKUs nach „Größe“, „Marke“, „Farbe“ usw. gruppiert sind. Ein weiterer Unterschied zwischen Klassifizierungen und der Datenvorbereitung besteht darin, dass Klassifizierungen für _historische und zukünftige_ Daten gelten. Zuordnungen der Datenvorbereitung werden hingegen auf Daten angewendet, die _nach_ dem Zeitpunkt liegen, zu dem die Zuordnung erstellt wurde.
