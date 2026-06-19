---
description: Erläutert die Strategie zur kontinuierlichen Veröffentlichung von Funktionen für Customer Journey Analytics
title: Strategie zur Veröffentlichung von Customer Journey Analytics-Funktionen
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
autotag-review: '2026-05-19T09:19:46.530Z'
TQID: 'https://experienceleague.adobe.com/nNV-qOa3LVmHUMLf-R2MwNHY0N67hxG2DWbVrpA-ZpI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: ht
source-wordcount: 402
ht-degree: 100%

---

# Strategie zur Veröffentlichung von Customer Journey Analytics-Funktionen

Customer Journey Analytics-Versionen basieren auf einem Modell der kontinuierlichen Bereitstellung, das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht.

## Veröffentlichungsstrategie

[!UICONTROL Analysis Workspace] verwendet Funktionsmarkierungen (auch als „Umschalter“ bezeichnet), um die Sichtbarkeit neuer Funktionen zu steuern, sodass vor der Vollversion ein kontrollierter Skalierungstest durchgeführt werden kann. Diese Veröffentlichungsstrategie umfasst die folgenden Phasen:

* **Eingeschränktes Testen**: Eine schrittweise Veröffentlichung beginnt mit Tests durch Adobe-interne Benutzende. Sie wird dann einer kleinen Gruppe von Kundenkonten zur Verfügung gestellt, um sicherzustellen, dass die Funktion den Kundenanforderungen und Erwartungen entspricht.

* **Start des Rollouts**: Der Rollout einer stufenweisen Veröffentlichung beginnt mit der eingeschränkten Testphase. Die Verfügbarkeit der Version für Kunden wird dann im Laufe einiger Monate von 0 % auf 100 % skaliert. Die schrittweise Einführung erfolgt auf der CX Enterprise-Organisationsebene, sodass alle Benutzenden mit Berechtigung in einem Unternehmen dasselbe Erlebnis erhalten.

* **Allgemeine Verfügbarkeit (GA)**: Die Funktion steht 100 % der berechtigten CX Experience-Organisationen zur Verfügung und die Veröffentlichung der Funktion ist abgeschlossen.

Bei jeder Funktionsveröffentlichung kann die Timeline von RTP bis GA variieren. Ziel ist es, die Veröffentlichungen kurz zu halten, sodass innerhalb von 2 Monaten nach Beginn der Veröffentlichung (RTP) eine Funktion allgemein verfügbar (GA) ist.

## Funktionsmarkierungen

Mithilfe von Funktionsmarkierungen wird die Sichtbarkeit neuer Funktionen während der Veröffentlichung gesteuert. Adobe empfiehlt, `app.launchdarkly.com` über die Firewall Ihres Unternehmens zuzulassen, um eine optimale Nutzung während der Veröffentlichungen zu gewährleisten. Diese Flags werden entfernt, nachdem eine Funktion für alle veröffentlicht wird. Weitere Informationen finden Sie unter [Domains, die von Customer Journey Analytics verwendet werden](../technotes/domains.md).

Sie können sich Ihre aktiven Funktionsmarkierungen jederzeit unter **Hilfe > Über den Workspace > Aktive Funktionsmarkierungen** ansehen.

## Vorteile

Die stufenweise Veröffentlichung ermöglicht es Adobe, den Software-Bereitstellungsprozess besser zu skalieren und sicherzustellen, dass die Funktionen vor der allgemeinen Verfügbarkeit vollständig gehärtet sind. Außerdem können Funktionen veröffentlicht werden, sobald sie verfügbar sind, anstatt sich an ein festes monatliches Veröffentlichungsfenster zu halten.

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
| --- | --- |
| Kann ich frühzeitigen Zugriff auf eine Funktion anfordern? | Nein. Es wird kein frühzeitiger Zugriff gewährt.<br>Wenn Sie frühe Analytics-Konzepte testen möchten, empfehlen wir Ihnen, [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=de) zu testen, um Feedback zu unseren branchenführenden Innovationen zu geben. |
| Hat diese Veröffentlichungsstrategie Auswirkungen auf meinen Zugriff auf Funktionen? | Nein. Sobald eine Funktion GA erreicht hat, haben Sie Zugriff auf die Funktion, wenn sie in Ihrem Analytics-Paket enthalten ist. |
