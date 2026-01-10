---
title: Planen eines Schemas für Customer Journey Analytics
description: Erfahren Sie, wie Sie ein XDM-Schema entwerfen, das Customer Journey Analytics-Flexibilität ermöglicht und gleichzeitig einen praktischen Migrationspfad von Adobe Analytics unterstützt.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 9%

---

# Planen eines Schemas für Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Schema planen"
>abstract="Besprechen Sie in Ihrer Organisation die Anforderungen an die Datenerfassung und bestimmen Sie, wie Sie ein Schema für Adobe Experience Platform erstellen möchten. Dieser Schritt wird angezeigt, weil Sie den empfohlenen Prozess – Verwendung eines auf Ihre Organisation zugeschnittenen Schemas – nutzen möchten. Die korrekte Durchführung dieses Schritts ist von entscheidender Bedeutung, da ein Schema, an dem sich alle Teams in Ihrer Organisation ausrichten, die Datenaufnahme erheblich erleichtert.<br><br>Alle relevanten Parteien in Ihrer Organisation zusammenzubringen, um ein einheitliches Schema zu erstellen, dauert ungefähr 1 bis 2 Monate. Dieser Zeitrahmen hängt stark von der Anzahl der Teams ab, die koordiniert werden müssen, sowie von der Anzahl der Dimensionen und Metriken, die aufeinander abgestimmt werden müssen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe empfiehlt die Erstellung eines benutzerdefinierten [Experience-Datenmodell](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/home)-Schemas (XDM) für Customer Journey Analytics bei der Implementierung der [Adobe Experience Platform-Datenerfassung](https://experienceleague.adobe.com/en/docs/experience-platform/collection/home). Das Erstellen dieses Schemas erfolgt in der Regel, bevor Implementierungsänderungen oder Code berührt werden. Mit einem benutzerdefinierten Schema können Sie einen knappen, organisationsspezifischen Datenvertrag entwerfen, ohne Einschränkungen von Adobe Analytics zu übernehmen oder Tausende von nicht verwendeten Feldern zu verwalten. Weitere [ zu den für Ihr Unternehmen verfügbaren Schematypen finden ](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) unter „Wählen Sie Ihr Schema für die Customer Journey Analytics aus .

Schemata sind als optimierte Versionen dazu gedacht, wie Ihre Daten langfristig strukturiert sein sollen. Änderungen an Schemata sind teuer, da sie sich auf die Datenerfassung, Validierung und nachgelagerten Services auswirken. Sie können Schemata im Laufe der Zeit hinzufügen, wie es die Geschäftsanforderungen zulassen. Schemafelder können jedoch nicht entfernt werden, sobald Daten in sie fließen.

## Vergleichen von Schemas mit Datenansichten

Die Datenpipeline für Customer Journey Analytics enthält separate Bereiche für die Datenerfassung und Dateninterpretation. Beim Upgrade von Adobe Analytics besteht ein häufiger Fehler darin, Props und eVars mit ihren Verhaltensweisen in XDM neu zu erstellen. Verwenden Sie stattdessen die Web-SDK , um die Daten zu erfassen, und verwenden [Datenansichten](/help/data-views/data-views.md) um zu bestimmen, wie diese Daten in Berichten interpretiert werden.

| Ebene | Primärer Zweck | Was gehört | Was nicht gehört |
|---|---|---|---|
| **XDM-Schema** | Definieren der dauerhaften Struktur und Bedeutung der erfassten Daten | Ereignis- und Entitätsform, Feldbedeutung, Beziehungen, zulässige Werte, Wiederverwendung über Kanäle hinweg | Nummerierte „Slots“ (eVar1/prop1), Attributionslogik/Persistenzlogik, berichterstellungsspezifische Problemumgehungen |
| **Datenansichten** | Verhalten der erfassten Daten in der Analyse definieren | Komponenteneinstellungen, Attributions- und Persistenzverhalten, abgeleitete Felder, gefilterte Metriken, berechnete Metriken | Grundlegende Bedeutung von Feldern; diese Bedeutung sollte im Schema stabil sein |

## Vergleichen von Schemas mit der Datenerfassung in Adobe Analytics

Das Experience-Datenmodell, das Customer Journey Analytics verwendet, bietet deutlich mehr Flexibilität als die meisten anderen Analytics-Lösungen (einschließlich Adobe Analytics). Durch die Einrichtung eines soliden Schemas erhält Ihr Unternehmen die Möglichkeit, Einschränkungen zu vermeiden, die in anderen Analytics-Produkten vorhanden sind.

| Allgemeine Adobe Analytics-Gewohnheit | Besserer Ansatz in XDM und CJA |
|---|---|
| Gestaltung um nummerierte Steckplätze (`eVar1`-`eVar250`, `prop1`-`prop75`) | Erstellen Sie Felder mit stabiler Bedeutung (z. B. `search.term`, `content.category`, `user.membershipTier`) und verwenden Sie sie konsistent wieder |
| Codierung der Persistenz/Zuordnung/Gültigkeit in das Datenmodell | Dauerhafte Fakten im Schema erfassen; Attributions- und Persistenzverhalten auf Datenansichtsebene anwenden |
| Duplizieren desselben Werts in mehreren Variablen zum Erzielen von Berichtsverhalten | Speichern Sie den Wert einmal und erstellen Sie daraus mehrere Komponenten (Dimensionen/Metriken) in Datenansichten |
| Erstellen eines eindeutigen „Metrikfelds“ für jede Zählung, die Sie vielleicht möchten | Einmal die richtigen Fakten erfassen (häufig als Aufzählungen/Boolesche Werte/Zeichenfolgen) und dann Metriken in Datenansichten als gefilterte Zählungen definieren |
| Variablen zur „Vorauflösung“ des Reportings entwerfen | Entwerfen Sie Ihr Schema, um zuverlässig Fakten zu erfassen und Datenansichten zur Lösung von Berichtssemantik zu verwenden |

## Schema mit allgemeinen Attributen erstellen

Ein einheitliches Schema für alle Kanäle wird möglich, wenn Sie einen Satz wiederverwendbarer Attribute standardisieren, die über viele Ereignisse hinweg angezeigt werden. Einige Beispiele:

* **Erlebniskontext:** Site-/App-Name, Umgebung, Gebietsschema, Kanal, Marke
* **Journey-Kontext:** Kampagnenkennungen, Verweiskontext, Experimentkennungen
* **Benutzerstatus:** Anmeldestatus, Mitgliedschaftsstufe, Kontotyp
* **Interaktionsdetails:** Interaktionsname/-typ, Benutzeroberflächenregion, Elementbeschriftung, Fehlerkategorie

Der Schlüssel besteht darin, das, was das Feld darstellt, unabhängig vom Kanal zu standardisieren. Vermeiden Sie es, dasselbe Konzept kanalübergreifend unterschiedlich zu modellieren, es sei denn, sie stellen wirklich unterschiedliche Konzepte dar. So kann es beispielsweise ratsam sein, keine separaten Schemafelder für Web-Kampagnen-IDs und Mobile-Kampagnen-IDs zu verwenden. Separate Schemafelder erschweren die Erstellung einer kanalübergreifenden Rendite für Daten zu Ausgaben und Ausgaben. Wenn beim Reporting eine Differenzierung erforderlich ist, können Sie nach Kanal segmentieren oder mehrere Felder verketten, um diese Unterscheidung zu ermöglichen. Dasselbe Schemafeld kann in einer beliebigen Anzahl von Dimensionen oder Metriken verwendet werden.

Eine praktische Möglichkeit, mehrere Kanäle zu unterstützen und dabei eine einzige Schemastrategie beizubehalten, besteht darin, ein **Core + Extensions**-Muster zu verwenden:

* **Core:** Felder, die für alle Kanäle und Teams gelten
* **Erweiterungen:** kanal- oder domänenspezifische Feldergruppen, die nur bei Bedarf gelten (Web-Interaktion, Commerce, mobiler Lebenszyklus, Server-seitige Besonderheiten)

Dieses Muster unterstützt eine einzelne organisatorische Schemastrategie, ohne jedes Team zu zwingen, Felder auszufüllen, die nicht für seinen Kanal gelten.

## Standardfeldgruppen bevorzugen, wo sie passen

Adobe empfiehlt die Verwendung standardisierter Feldergruppen, wenn sie Ihren Anforderungen entsprechen, und die Erweiterung um benutzerdefinierte Felder für organisationsspezifische Konzepte.

Standardfeldergruppen helfen in der Regel bei Folgendem:

* Reduzieren von Mehrdeutigkeiten mithilfe bekannter Feldsemantik
* Einfachere Abstimmung zwischen Teams
* Unterstützung der Interoperabilität zwischen Adobe Experience Platform-Anwendungen

Benutzerdefinierte Felder sind geeignet, wenn:

* Ihre Organisation verfügt über Konzepte, die Standardfeldern nicht sauber zugeordnet werden können
* Sie benötigen zusätzliche Attribute, um die Berichts-, Governance- oder Aktivierungsanforderungen zu erfüllen
* Sie möchten eine geschäftsspezifische Taxonomie darstellen (z. B. interne Inhaltskategorien)

## Entscheiden, wo die „metrische Bedeutung“ lebt

In Adobe Analytics behandeln viele Teams die `events` als den Ort, an den die Metriken gehen. In Customer Journey Analytics können Sie Metriken auf verschiedene Arten modellieren, je nachdem, was Sie zählen müssen und wie Sie sie interpretieren möchten.

Halten Sie sich beim Entwickeln eines Schemas an die Fakten. Beispiel: `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Definieren Sie Metriken in der Datenansicht als Zählungen und gefilterte Zählungen über diese Fakten. Zum Beispiel:

* `checkout.step` (Enum/String) kann:
   * „Checkout: Versandschritt erreicht“ (Anzahl wo `checkout.step == "shipping"`)
   * „Checkout: Zahlungsschritt erreicht“
* `error.type` (Enum/String) kann:
   * „Validierungsfehler“
   * „Autorisierungsfehler“
* `user.isLoggedIn` (Boolesch) kann Folgendes bewirken:
   * „Authentifizierte Sitzungen“
   * „Authentifizierte Konversionen“

>[!TIP]
>
>Bei der Entscheidung, ob ein bestimmtes Feld im Vergleich zu einem abgeleiteten Feld später verwendet werden soll, empfiehlt es sich, den dauerhaften Fakt im Schema zu erfassen, sofern dies im Großen und Ganzen nützlich und stabil ist. Sie können abgeleitete Felder verwenden, um Daten nach der Sammlung zu korrigieren oder neu zu formen.

## Wahrung der Parität mit Adobe Analytics während der Umstellung ohne Schema-Gepäck

Einige Unternehmen müssen beim Upgrade auf Customer Journey Analytics weiterhin Berichte für Adobe Analytics erstellen. Sie können die Parität wahren, ohne Analytics-spezifische Artefakte in Ihr langfristiges Schema-Design einzuführen, indem Sie den folgenden Ansatz verwenden:

1. **Verwenden von XDM-Feldpfaden, die Adobe Analytics erkennt und automatisch zuordnet:** Wenn Sie erkannte XDM-Felder über die Edge Network an Adobe Analytics senden, werden sie [ automatisch ](https://experienceleague.adobe.com/de/docs/analytics/implementation/aep-edge/xdm-var-mapping).
1. **Verwenden benutzerdefinierter XDM-Felder für organisationsspezifische Konzepte:** Alle XDM-Felder, die nicht automatisch einer Analytics-Variablen zugeordnet sind, werden als [Kontextdatenvariablen](https://experienceleague.adobe.com/de/docs/analytics/implementation/vars/page-vars/contextdata) in Adobe Analytics weitergeleitet.
1. **Verwenden Sie Adobe Analytics-Verarbeitungsregeln, um diese Kontextdatenvariablen Props/eVars zuzuordnen:** [Verarbeitungsregeln](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) ermöglichen es Ihnen letztendlich, jedes benutzerdefinierte XDM-Feld einer beliebigen eVar oder Eigenschaft zuzuordnen. Dieses Konzept unterstützt die Paritätsberichterstattung in Adobe Analytics, wobei Ihr Schema sauber und auf Customer Journey Analytics zentriert bleibt.

## Identifizieren von Stakeholdern und Definieren der Eigentümerschaft

Der Schema-Entwurf ist erfolgreich, wenn die Feldbedeutung vereinbart und beibehalten wird. Auch wenn sich die Organisationsstrukturen unterscheiden, nehmen in der Regel die folgenden Rollen teil:

* **Analytics-Admin/Analyst**: Definiert Berichtsfragen, validiert, ob Felder aussagekräftige Konzepte darstellen, und prüft die Analysesemantik in Datenansichten.
* **Entwickler/Implementierungs-Verantwortlicher**: Stellt sicher, dass Felder mithilfe der Web-SDK zuverlässig erfasst und an der Datenschicht-/App-Instrumentierung ausgerichtet werden können.
* **Datenarchitekt/-ingenieur**: Stellt die Schemakonsistenz, die Wiederverwendung über Domains hinweg und die Kompatibilität mit nachgelagerten Services sicher.
* **Datenschutz/Governance-Stakeholder**: Überprüft Datenminimierung, Einverständniserklärungen und Datennutzungsbeschränkungen.

Definieren Sie einen eindeutigen Verantwortlichen für Schemaänderungen. Ein stabiles Schema mit disziplinierter Änderungskontrolle verhindert nachgelagerte Brüche und reduziert Nacharbeit. Erwägen Sie die Verwendung eines Tracking-Governance-Workflows oder -Tools, um Anfragen zu demokratisieren und die Änderungskontrolle im Laufe der Zeit zu verwalten.

## Überlegungen zum Datenschutz und zur Governance

Das Schema-Design sollte die Datenschutz- und Governance-Erwartungen gemäß den Datenschutzrichtlinien Ihres Unternehmens widerspiegeln. Beachten Sie beim Entwickeln Ihres Schemas die folgenden Punkte:

* Nur das erfassen, was Sie zur Unterstützung definierter Anwendungsfälle benötigen.
* Stellen Sie sicher, dass die Anforderungen an Einverständnis und Datennutzung in Ihrer Sammlungsstrategie berücksichtigt werden. Weitere [ finden Sie unter „Verwenden der Web-SDK zur Verarbeitung ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/consent/sdk) Kundeneinverständnisdaten .
* Beachten Sie, wie sensible Felder in den Governance-Tools von Adobe Experience Platform gekennzeichnet und gesteuert werden. Weitere Informationen finden Sie unter [Adobe Customer Journey Analytics ](/help/privacy/privacy-overview.md) Data Governance.

## Nächste Schritte

Sobald Sie eine Schemaarchitektur eingerichtet und vereinbart haben, können Sie sie in Adobe Experience Platform erstellen. Customer Journey Analytics Weitere [ finden Sie unter „Erstellen eines benutzerdefinierten Schemas zur Verwendung mit ](cja-upgrade-schema-create.md)&quot;.
