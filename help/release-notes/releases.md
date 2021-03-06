---
description: Erläutert die Strategie zur kontinuierlichen Veröffentlichung von Funktionen für Customer Journey Analytics
title: Versionen von Customer Journey Analytics-Funktionen
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: f2c82f54ec534603539327597d5f4c4ec875d44c
workflow-type: ht
source-wordcount: '379'
ht-degree: 100%

---

# Versionen von Customer Journey Analytics-Funktionen

Customer Journey Analytics-Versionen basieren auf einem Modell der kontinuierlichen Bereitstellung, das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht.

## Veröffentlichungsstrategie

[!UICONTROL Analysis Workspace] verwendet Funktionsmarkierungen (auch als „Umschalter“ bezeichnet), um die Sichtbarkeit neuer Funktionen zu steuern, sodass vor der Vollversion ein kontrollierter Skalierungstest durchgeführt werden kann. Diese Veröffentlichungsstrategie umfasst die folgenden Phasen:

* **Freigabe für die Produktion (RTP)**: Der Code wird für die Produktion freigegeben, wobei die Sichtbarkeit der Funktionen in Analysis Workspace deaktiviert ist. Die Funktion ist manchmal in der CJA-API verfügbar.

* **Eingeschränktes Testen**: Eine schrittweise Veröffentlichung beginnt mit Tests durch interne Adobe-Benutzer. Die Verfügbarkeit der Version wird dann im Laufe einiger Monate von 0 % auf 100 % skaliert. Die schrittweise Einführung erfolgt auf der Organisationsebene in Experience Cloud, sodass alle Benutzer mit Berechtigung in einem Unternehmen dasselbe Erlebnis erhalten.

* **Allgemeine Verfügbarkeit (GA)**: Die Funktion steht 100 % der berechtigten Experience Cloud-Organisationen zur Verfügung und die Veröffentlichung der Funktion ist abgeschlossen.

Bei jeder Funktionsveröffentlichung kann die Timeline von RTP bis GA variieren. Ziel ist es, die Veröffentlichungen kurz zu halten, sodass innerhalb von 2 Monaten nach Beginn der Veröffentlichung (RTP) eine Funktion allgemein verfügbar (GA) ist.

## Funktionsmarkierungen

Mithilfe von Funktionsmarkierungen wird die Sichtbarkeit neuer Funktionen während der Veröffentlichung gesteuert. Adobe empfiehlt, `app.launchdarkly.com` zur [Zulassungsliste](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=de) Ihrer Firewall hinzuzufügen, um eine optimale Funktionalität bei der Veröffentlichung zu erzielen. Kurz nach der allgemeinen Verfügbarkeit wird die Markierung entfernt.

Sie können sich Ihre aktiven Funktionsmarkierungen jederzeit unter **Hilfe > Über den Workspace > Aktive Funktionsmarkierungen** ansehen.

## Vorteile

Die stufenweise Veröffentlichung ermöglicht es Adobe, den Software-Implementierungsprozess besser zu skalieren und sicherzustellen, dass die Funktionen vor der allgemeinen Verfügbarkeit vollständig gehärtet sind. Außerdem können Funktionen veröffentlicht werden, sobald sie verfügbar sind, anstatt sich an ein festes monatliches Veröffentlichungsfenster zu halten.

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
| --- | --- |
| Kann ich frühzeitigen Zugriff auf eine Funktion anfordern? | Nein. Es wird kein frühzeitiger Zugriff gewährt.<br>Wenn Sie frühe Analytics-Konzepte testen möchten, empfehlen wir Ihnen, [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=de) zu testen, um Feedback zu unseren branchenführenden Innovationen zu geben. |
| Hat diese Veröffentlichungsstrategie Auswirkungen auf meinen Zugriff auf Funktionen? | Nein. Sobald eine Funktion GA erreicht hat, haben Sie Zugriff auf die Funktion, wenn sie in Ihrem Analytics-Paket enthalten ist. |
