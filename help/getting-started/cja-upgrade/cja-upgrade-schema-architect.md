---
title: Planen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad für das Upgrade von Adobe Analytics auf Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

---

# Planen eines Schemas für Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Schema planen"
>abstract="Besprechen Sie in Ihrer Organisation die Anforderungen an die Datenerfassung und bestimmen Sie, wie Sie ein Schema für Adobe Experience Platform erstellen möchten. Dieser Schritt wird angezeigt, weil Sie den empfohlenen Prozess – Verwendung eines auf Ihre Organisation zugeschnittenen Schemas – nutzen möchten. Die korrekte Durchführung dieses Schritts ist von entscheidender Bedeutung, da ein Schema, an dem sich alle Teams in Ihrer Organisation ausrichten, die Datenaufnahme erheblich erleichtert.<br><br>Alle relevanten Parteien in Ihrer Organisation zusammenzubringen, um ein einheitliches Schema zu erstellen, dauert ungefähr 1 bis 2 Monate. Dieser Zeitrahmen hängt stark von der Anzahl der Teams ab, die koordiniert werden müssen, sowie von der Anzahl der Dimensionen und Metriken, die aufeinander abgestimmt werden müssen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe empfiehlt die Erstellung eines benutzerdefinierten Experience-Datenmodell(XDM)-Schemas zur Verwendung mit dem Web-SDK beim Upgrade von Adobe Analytics auf Customer Journey Analytics. Alternativ können Sie das standardmäßige Adobe Analytics-Schema mit der Adobe Analytics ExperienceEvent-Feldergruppe verwenden.

Ein benutzerdefiniertes XDM-Schema bietet ein optimiertes Schema, das auf die Anforderungen Ihrer Organisation und die von Ihnen verwendeten spezifischen Platform-Anwendungen zugeschnitten ist. Im Gegensatz zum standardmäßigen Adobe Analytics-Schema, das die Adobe Analytics ExperienceEvent-Feldergruppe verwendet, müssen Sie, wenn Änderungen an einem benutzerdefinierten XDM-Schema erforderlich sind, nicht Tausende nicht verwendeter Felder durchgehen, um das zu aktualisierende Feld zu finden.

Weitere Informationen zu diesen Schemaoptionen finden Sie unter [Auswählen Ihres Schemas für Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Lesen Sie die folgenden Abschnitte, wenn Sie mit der Planung Ihres XDM-Schemas beginnen.

## Vermeiden von Adobe Analytics-Einschränkungen in Ihrem XDM-Schema

Die zugrunde liegende Architektur von Customer Journey Analytics bietet viel mehr Flexibilität als Adobe Analytics. Die Erstellung eines neuen XDM-Schemas ist ein wichtiges Instrument, um diese Flexibilität zu erschließen. Stellen Sie beim Upgrade auf Customer Journey Analytics sicher, dass Sie nicht unnötige Adobe Analytics-Einschränkungen in Ihr Schema übertragen.

>[!NOTE]
>
>Die folgenden Informationen sind noch nicht vollständig, werden aber demnächst entsprechend ergänzt.

| Adobe Analytics-Datenarchitektur | XDM-Schemaarchitektur |
|---------|----------|
| Einzelne Metriken werden zur Analytics-Datenarchitektur hinzugefügt.<br/>In Adobe Analytics gibt es beispielsweise für jedes Ereignis eine andere eVar. | Erstellen Sie einzelne Metriken in der Datenansicht und nicht im XDM-Schema. Dadurch erhalten Sie mehr Flexibilität, wenn Sie zu einem späteren Zeitpunkt Änderungen vornehmen müssen.<br/>In Customer Journey Analytics gibt es beispielsweise ein einzelnes Ereignis im Schema und Sie verwenden die Option „Ereignisse erstellen“ in der Datenansicht. |
| Props und eVars sind erforderlich, um benutzerdefinierte Variablen zu erstellen. |  |

## Identifizieren Ihres Daten-Teams und anderer Stakeholder in Ihrer Organisation

>[!NOTE]
>
>Diese Informationen sind noch nicht verfügbar, stehen aber demnächst bereit.

## Berücksichtigen anderer in Ihrer Organisation verwendeter Adobe Experience Platform-Anwendungen

>[!NOTE]
>
>Diese Informationen sind noch nicht verfügbar, stehen aber demnächst bereit.
