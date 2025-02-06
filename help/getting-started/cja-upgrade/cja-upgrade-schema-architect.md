---
title: Entwickeln eines Schemas zur Verwendung mit Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad beim Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Entwickeln eines Schemas zur Verwendung mit Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Entwickeln eines Schemas"
>abstract="Besprechen Sie in Ihrem Unternehmen die Anforderungen an die Datenerfassung und bestimmen Sie, wie Sie ein Schema zur Verwendung in Adobe Experience Platform erstellen möchten. Dieser Schritt wird angezeigt, weil Sie den empfohlenen Prozess der Verwendung eines auf Ihre Organisation zugeschnittenen Schemas verwenden möchten. Die korrekte Durchführung dieses Schritts ist von entscheidender Bedeutung, da ein Schema, an dem sich alle Teams in Ihrer Organisation ausrichten, die Datenaufnahme erheblich erleichtert.<br><br>Die geschätzte Zeit, um alle relevanten Parteien in Ihrer Organisation zusammenzubringen, um ein einheitliches Schema zu erstellen, beträgt 1-2 Monate. Dieser Zeitrahmen hängt stark von der Anzahl der Teams ab, die koordiniert werden müssen, sowie von der Anzahl der Dimensionen + Metriken, die aufeinander abgestimmt werden müssen."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Befolgen Sie die Schritte auf dieser Seite erst, nachdem Sie alle vorherigen Upgrade-Schritte abgeschlossen haben. Sie können die [empfohlenen Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die Upgrade-Schritte ausführen, die für Ihr Unternehmen mit dem [Fragebogen für das Upgrade von Adobe Analytics auf Customer Journey Analytics dynamisch generiert wurden](https://gigazelle.github.io/cja-ttv/).
>
>Nachdem Sie die Schritte auf dieser Seite abgeschlossen haben, folgen Sie den empfohlenen Upgrade-Schritten oder den dynamisch generierten Upgrade-Schritten.

Adobe empfiehlt die Erstellung eines benutzerdefinierten Experience-Datenmodell (XDM)-Schemas zur Verwendung mit der Web-SDK beim Upgrade von Adobe Analytics auf Customer Journey Analytics. Alternativ können Sie das standardmäßige Adobe Analytics-Schema verwenden, das die Adobe Analytics ExperienceEvent-Feldergruppe verwendet.

Ein benutzerdefiniertes XDM-Schema ermöglicht ein optimiertes Schema, das auf die Anforderungen Ihres Unternehmens und die von Ihnen verwendeten Platform-Programme zugeschnitten ist. Im Gegensatz zum standardmäßigen Adobe Analytics-Schema, das die Adobe Analytics ExperienceEvent-Feldergruppe verwendet, müssen Sie, wenn Änderungen an einem benutzerdefinierten XDM-Schema erforderlich sind, nicht Tausende von nicht verwendeten Feldern durchsuchen, um das Feld zu finden, das aktualisiert werden muss.

Weitere Informationen zu diesen Schemaoptionen finden Sie unter [Schema zum Customer Journey Analytics auswählen](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Lesen Sie die folgenden Abschnitte, wenn Sie mit der Architektur Ihres XDM-Schemas beginnen.

## Vermeiden von Adobe Analytics-Einschränkungen in Ihrem XDM-Schema

Die zugrunde liegende Architektur von Customer Journey Analytics bietet deutlich mehr Flexibilität als Adobe Analytics. Die Erstellung eines neuen XDM-Schemas ist eine wichtige Möglichkeit, diese Flexibilität zu erschließen. Stellen Sie beim Upgrade auf Customer Journey Analytics sicher, dass Sie nicht unnötige Adobe Analytics-Einschränkungen in Ihr Schema übertragen.

| Adobe Analytics-Datenarchitektur | XDM-Schemaarchitektur |
|---------|----------|
| Einzelne Metriken werden zur Analytics-Datenarchitektur hinzugefügt.<br/>In Adobe Analytics haben Sie beispielsweise für jedes Ereignis eine andere eVar. | Erstellen Sie einzelne Metriken in der Datenansicht anstatt im XDM-Schema. Dadurch erhalten Sie mehr Flexibilität bei , wenn Sie zu einem späteren Zeitpunkt Änderungen vornehmen müssen.<br/>Beispiel: Beim Customer Journey Analytics befindet sich im Schema ein einzelnes Ereignis, das in der Datenansicht mit „Ereignisse erstellen“ angezeigt wird. |
| Props und eVars sind erforderlich, um benutzerdefinierte Variablen zu erstellen. | B2 |
| A3 | B3 |

## Identifizieren Ihres Daten-Teams und anderer Stakeholder in Ihrem Unternehmen


## Erwägen anderer in Ihrem Unternehmen verwendeter Adobe Experience Platform-Anwendungen



1. Fahren Sie mit den [empfohlenen Upgrade-Schritten](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder den [dynamisch generierten Upgrade-Schritten](https://gigazelle.github.io/cja-ttv/) fort.
