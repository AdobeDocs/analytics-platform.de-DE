---
title: Zuordnen von Analytics-Daten aus mehreren IMS-Organisationen
description: Erfahren Sie, wie Sie Daten aus Report Suites mehrerer Quell-IMS-Organisationen einer Ziel-IMS-Organisation zuordnen können.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Zuordnen von Analytics-Daten aus mehreren IMS-Organisationen

Der Analytics-Quell-Connector kann nur Daten aus Adobe Analytics Report Suites aufnehmen, die zu derselben Organisation gehören, für die Sie zur Verwendung von Customer Journey Analytics berechtigt sind. Die Funktion zum Zuordnen von Analytics-Daten aus mehreren IMS-Organisationen bietet eine Lösung für diese Einschränkung. Der Prozess zum Aktivieren dieser Funktion wird in diesem Artikel beschrieben.


## Szenario

Sie verfügen über mehrere IMS-Organisationen und Analytics-Daten in mehreren Report Suites dieser IMS-Organisationen. Diese Einrichtung kann folgende Ursachen haben:

* Akquisitionen oder Fusionen
* Anforderungen an die Organisationsstruktur
* Regionale Bereitstellungseinschränkungen

Standardmäßig können Sie keinen Bericht zur Kombination von Daten aus mehreren Report Suites über mehrere IMS-Organisationen hinweg in Customer Journey Analytics erstellen. Der Grund für diese Einschränkung besteht darin, dass die Datenaufnahme von Adobe Analytics in Experience Platform über den Analytics-Quell-Connector nur die Aufnahme von Daten unterstützt, die einer einzigen IMS-Organisation gehören. Die IMS-Organisation, für die Sie bereitgestellt wurden und mit der Sie sich bei Adobe Analytics, Experience Platform und Customer Journey Analytics anmelden.

Mit der Funktion *Analytics-Daten aus mehreren IMS* Organisationen zuordnen“ können Sie Adobe anfordern, Daten zuzuordnen. Die Funktion verwendet den Analytics-Quell-Connector, um Daten aus Report Suites, die sich in mehreren *Quelle* IMS-Organisationen befinden, Datensätzen zuzuordnen, die Teil einer *Ziel* IMS-Organisation sind. Zum Beispiel:

| Abbildung | Erklärung |
|---|---|
| ![Daten über mehrere IMS-Organisationen hinweg zuordnen](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Mit dieser Zuordnung können Sie Berichte zu Report Suites erstellen, die in IMS Organisation 1, IMS Organisation 2 und IMS Organisation 3 vorhanden sind, und zwar über eine Verbindung in Customer Journey Analytics, die innerhalb von IMS Organisation 3 bereitgestellt wird. |

{style="table-layout:fixed"}

## Informationen zur Verwendung

Um die Funktion *Analytics-Daten von mehreren IMS-Organisationen zuordnen* zu konfigurieren und zu aktivieren, müssen Sie die Zuordnung über Ihren Adobe Account Manager anfordern. Gehen Sie dazu wie folgt vor:

1. Fordern Sie als Ziel-IMS-Organisationsadministrator Genehmigungs-E-Mails von allen Quell-IMS-Organisationsadministratoren an, denen Sie Report Suites zuordnen möchten. Sie können den folgenden Text als Vorlage für die E-Mail verwenden, um die Genehmigung von den Administrierenden der Quell-IMS-Organisation anzufordern.

   | E-Mail-Beispielvorlage |
   | --- |
   | *Name des Unternehmens*, um der ausgewählten Ziel-Organisation Zugriff auf die folgenden IMS-Organisationen (Liste der Quell-IMS-Organisationen) zu gewähren, müssen wir sicherstellen, dass ein Administrator für jede IMS-Organisation seine Genehmigung einreicht, um den Zugriff auf ihre Daten zu ermöglichen. Dadurch wird sichergestellt, dass die Datenzugriffsberechtigungen der betroffenen IMS-Organisation eingehalten wurden. Um sicherzustellen, dass wir eine ordnungsgemäße Genehmigung haben, bitten wir einen registrierten Adobe-Administrator für jede Admin-Organisation, auf diese E-Mail mit ihrem Namen und ihrer IMS-Organisation zu antworten, die sie repräsentieren, und zu sagen: „Ich genehmige“, um anzugeben, dass sie ihre Genehmigung erteilen, die Daten dieser IMS-Organisation in der Ziel-Organisation ([) ]. Beachten Sie, dass dieser Administrator ein Administrator sein muss, der im Adobe-System als Administrator für diese IMS-Organisation registriert ist. |

1. Senden Sie eine E-Mail als Ziel-IMS-Organisationsadministrator an den Adobe-Account-Manager, der die Zuordnung von Report Suites innerhalb mehrerer Quell-IMS-Organisationen zur Ziel-IMS-Organisation anfordert. Hängen Sie die Genehmigungs-E-Mails an, die Sie von den Administrierenden der Quell-IMS-Organisation erhalten haben.

Sobald der Account Manager die E-Mail mit der Anfrage erhält, Analytics-Daten von mehreren Organisationen zuzuordnen, wird die Anfrage in Adobe geprüft. Der Account Manager kontaktiert Sie für weitere Fragen, optionale Schulungen und weitere Informationen.

Nach der Genehmigung wird die angeforderte Zuordnung erstellt und Sie werden benachrichtigt. Der Name der IMS-Quellorganisation wird dem Namen der Report Suite in der [Liste der Analytics Report Suites](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) in Experience Platform angehängt.

## Einschränkungen und Risiken

Die folgenden Einschränkungen gelten für die Funktion *Analytics-Daten von mehreren IMS-Organisationen zuordnen*:

* Sie können eine Report Suite nur einmal organisationsübergreifend verbinden.
* Sie müssen alle Verbindungen für eine IMS-Organisation, die als Ziel-IMS-Organisation definiert ist, in einer Zuordnung löschen, bevor Sie die Löschung der Zuordnung anfordern können.
* ECIDs sind nicht zwischen zugeordneten Quell-IMS-Organisationen kompatibel und nicht mit der Ziel-IMS-Organisation kompatibel.
* Ein Benutzer mit ausreichenden Berechtigungen zum Konfigurieren des Analytics-Quell-Connectors in der Ziel-IMS-Organisation kann Analytics-Daten aus einer beliebigen zugeordneten Quell-IMS-Organisation aufnehmen. Für diese Person werden für keine der Quell-IMS-Organisationen Berechtigungen überprüft.
