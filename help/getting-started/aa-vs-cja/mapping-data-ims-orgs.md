---
title: Zuordnen von Analytics-Daten aus mehreren IMS-Organisationen
description: Erfahren Sie, wie Sie anfordern können, Daten aus Report Suites mehrerer Quell-IMS-Organisationen Report Suites und letztendlich Datensätzen in einer Ziel-IMS-Organisation zuzuordnen.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: 888420e8cd11cd447fec99257b213669edd345c1
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 1%

---

# Cross-IMS-Datenzuordnung

In diesem Artikel wird beschrieben, wie Sie Daten aus Report Suites in mehreren IMS-Organisationen Report Suites und letztendlich Datensätzen in einer IMS-Organisation zuordnen.

Der Analytics-Quell-Connector nimmt standardmäßig Daten aus Adobe Analytics Report Suites innerhalb einer einzigen Organisation auf. *Cross-IMS Data Mapping* ist eine Funktion zur Zuordnung von Analytics-Daten aus mehreren IMS-Organisationen und bietet eine Lösung für diese Einschränkung. Der Prozess zum Aktivieren dieser Funktion wird in diesem Artikel beschrieben.


## Szenario

Sie verfügen über mehrere IMS-Organisationen und Analytics-Daten in mehreren Report Suites dieser IMS-Organisationen. Diese Einrichtung kann folgende Ursachen haben:

* Akquisitionen oder Fusionen
* Anforderungen an die Organisationsstruktur
* Regionale Bereitstellungseinschränkungen

Standardmäßig können Sie keinen Bericht zur Kombination von Daten aus mehreren Report Suites über mehrere IMS-Organisationen hinweg in Customer Journey Analytics erstellen. Der Grund für diese Einschränkung besteht darin, dass die Datenaufnahme von Adobe Analytics in Experience Platform über den Analytics-Quell-Connector nur die Aufnahme von Daten unterstützt, die einer einzigen IMS-Organisation gehören. Die IMS-Organisation, für die Sie bereitgestellt wurden und mit der Sie sich bei Adobe Analytics, Experience Platform und Customer Journey Analytics anmelden.

Mit der Funktion *Cross-IMS-Datenzuordnung* können Sie Adobe anfordern, Daten zuzuordnen. Die Funktion verwendet den Analytics-Quell-Connector zur Zuordnung von Daten aus Report Suites, die sich in mehreren *Quell-)* IMS-Organisationen befinden, zu Report Suites (und letztendlich Datensätzen), die Teil einer *Ziel-)* IMS-Organisation sind. Zum Beispiel:

| Abbildung | Erklärung |
|---|---|
| ![Daten über mehrere IMS-Organisationen hinweg zuordnen](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Mit dieser Zuordnung können Sie Berichte zu Report Suites erstellen, die in IMS Organisation 1, IMS Organisation 2 und IMS Organisation 3 vorhanden sind, und zwar über eine Verbindung in Customer Journey Analytics, die innerhalb von IMS Organisation 3 bereitgestellt wird. |

{style="table-layout:fixed"}

## Informationen zur Verwendung

Um die Funktion *Cross-IMS-Datenzuordnung* zu konfigurieren und zu aktivieren, müssen Sie die Zuordnung über Ihren Adobe Account Manager anfordern. Gehen Sie dazu wie folgt vor:

1. Fordern Sie als Ziel-IMS-Organisationsadministrator Genehmigungs-E-Mails von allen Quell-IMS-Organisationsadministratoren an, denen Sie Report Suites zuordnen möchten. Sie können den folgenden Text als Vorlage für die E-Mail verwenden, um die Genehmigung von den Administrierenden der Quell-IMS-Organisation anzufordern.

   | E-Mail-Beispielvorlage |
   | --- |
   | *Name des Unternehmens*, um der ausgewählten Ziel-Organisation Zugriff auf die folgenden IMS-Organisationen (Liste der Quell-IMS-Organisationen) zu gewähren, müssen wir sicherstellen, dass ein Administrator für jede IMS-Organisation seine Genehmigung einreicht, um den Zugriff auf ihre Daten zu ermöglichen. Dadurch wird sichergestellt, dass die Datenzugriffsberechtigungen der betroffenen IMS-Organisation eingehalten wurden. Um sicherzustellen, dass wir eine ordnungsgemäße Genehmigung haben, bitten wir einen registrierten Adobe-Administrator für jede Admin-Organisation, auf diese E-Mail mit ihrem Namen und ihrer IMS-Organisation zu antworten, die sie repräsentieren, und zu sagen: „Ich genehmige“, um anzugeben, dass sie ihre Genehmigung erteilen, die Daten dieser IMS-Organisation in der Ziel-Organisation ([) ]. Beachten Sie, dass dieser Administrator ein Administrator sein muss, der im Adobe-System als Administrator für diese IMS-Organisation registriert ist. |

1. Senden Sie im Namen des Ziel-IMS-Organisationsadministrators eine E-Mail an den Adobe Account Manager, der die Zuordnung von Report Suites aus mehreren Quell-IMS-Organisationen zur Ziel-IMS-Organisation anfordert. Hängen Sie die Genehmigungs-E-Mails an, die Sie von den Administrierenden der Quell-IMS-Organisation erhalten haben.

Sobald der Adobe-Kundenbetreuer die E-Mail mit der Anforderung erhält, Analytics-Daten von mehreren Organisationen zuzuordnen, wird die Anfrage in Adobe geprüft. Der Adobe-Kundenbetreuer kontaktiert Sie für weitere Fragen, optionale Schulungen und weitere Informationen.

Nach der Genehmigung wird die angeforderte Zuordnung erstellt und Sie werden benachrichtigt. Der Name der IMS-Quellorganisation wird dem Namen der Report Suite in der [Liste der Analytics Report Suites](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) in Experience Platform angehängt.


## Einschränkungen

Die folgenden Einschränkungen gelten für die Funktion *Cross-IMS Data Mapping*:

* Sie können eine Report Suite nur einmal organisationsübergreifend verbinden.
* Sie müssen alle Verbindungen für eine IMS-Organisation, die als Ziel-IMS-Organisation definiert ist, in einer Zuordnung löschen, bevor Sie die Löschung der Zuordnung anfordern können.
* ECIDs sind nicht zwischen zugeordneten Quell-IMS-Organisationen kompatibel und nicht mit der Ziel-IMS-Organisation kompatibel.


## Zu beachten

Sie sollten die folgenden Themen berücksichtigen, bevor Sie die Funktion *Cross-IMS Data Mapping* anfordern:

### Profile

Sobald die Funktion *Cross-IMS-Datenzuordnung* genehmigt ist, können Sie Daten zu Experience Platform für eine oder mehrere Report Suites in der Ziel-IMS-Organisation hinzufügen. Dies erfolgt über die Konfiguration des [Analytics-Quell-Connectors](https://experienceleague.adobe.com/de/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Zieldatensätze werden dann in Experience Platform erstellt. Im Rahmen dieser Konfiguration und dieses Prozesses haben Sie die Möglichkeit, Profildaten aus einer oder mehreren Report Suites an den Profil-Service zu senden.

Schätzen Sie die Gesamtzahl der Profile, die das Ergebnis der Konfiguration und des Prozesses sind, wie oben beschrieben. Stellen Sie sicher, dass die Gesamtzahl innerhalb der Anzahl der Profile liegt, auf die Sie für die Zielorganisation vertraglich Anspruch haben. Wenden Sie [Filterregeln und -bedingungen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"} an, um Daten selektiv in den Profil-Service aufzunehmen oder davon auszuschließen. Oder deaktivieren Sie die Option zum Senden von Profildaten an den Profil-Service für relevante Report Suites.


#### Zuordnung

Sie können sowohl [&#x200B; (feldbasierte](/help/stitching/fbs.md) als auch [Diagrammbasierte](/help/stitching/gbs.md) Zuordnung für die Zieldatensätze verwenden. Wenn Sie das diagrammbasierte Stitching für einen oder mehrere dieser Zieldatensätze verwenden, stellen Sie sicher, dass Sie die vertraglichen Berechtigungen für die Anzahl der Profile einhalten, wie im Abschnitt [Profile](#profiles) beschrieben.

Wenn Sie nicht für das Echtzeit-Kundenprofil lizenziert sind, aber dennoch diagrammbasiertes Stitching für einen oder mehrere Zieldatensätze verwenden möchten, stellen Sie sicher, dass Sie nur den [Identity Service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) für diese Zieldatensätze aktivieren.


### Zugriffsberechtigung

Ein Benutzer mit ausreichenden Berechtigungen zum Konfigurieren des Analytics-Quell-Connectors in der Ziel-IMS-Organisation kann Analytics-Daten aus einer beliebigen zugeordneten Quell-IMS-Organisation aufnehmen. Für diese Person werden für keine der Quell-IMS-Organisationen Berechtigungen überprüft.

### Datenbericht

Die Funktion *Cross-IMS-Datenzuordnung* ist nur ein erster Schritt, um sicherzustellen, dass Sie die Daten als Teil einer Customer Journey Analytics [Verbindung](/help/connections/overview.md), eines oder mehrerer [Datenansichten](/help/data-views/data-views.md) und [Workspace-Projekte](/help/analysis-workspace/home.md) können. Sie müssen die Daten, die Ihnen jetzt in einer IMS-Organisation zur Verfügung stehen, sorgfältig prüfen. Erwägen Sie auch Funktionen wie Datenvorbereitung, abgeleitete Felder, zusätzliche Suchtabellen und mehr, bevor Sie in der Lage sind, ordnungsgemäß über diese Daten zu berichten.
