---
title: Warum sich GA4- und Customer Journey Analytics-Daten unterscheiden
description: Erfahren Sie, warum Daten zwischen GA4 und Customer Journey Analytics unterschiedlich sein können und wie Sie Diskrepanzen prüfen können.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# Warum sich GA4- und Customer Journey Analytics-Daten unterscheiden

Es ist normal, dass GA4 und Customer Journey Analytics unterschiedliche Zahlen für denselben Zeitraum und dieselbe offensichtliche Metrik melden. Verschiedene Datenerfassungsmethoden, Metrikdefinitionen, Identitätsmodelle und Sitzungsregeln tragen alle zu Diskrepanzen bei. Auf dieser Seite werden die häufigsten Ursachen von Unterschieden erläutert und Anleitungen zum Überprüfen unerklärlicher Lücken gegeben.

## Interaktive Sitzungen

Bei GA4 wird eine Sitzung als **aktiv** behandelt, wenn sie 10 oder mehr Sekunden gedauert hat, mindestens ein Schlüsselereignis enthielt oder zwei oder mehr Seitenansichten hatte. Diese einzelne Definition unterstützt mehrere GA4-Metriken, einschließlich Interaktionsrate, Absprungrate und Interaktionsschwellenwert hinter aktiven Benutzern.

Customer Journey Analytics verfügt über keine integrierte Metrik oder Dimension für interaktive Sitzungen. Sie definieren die Interaktion passend zu Ihrem Unternehmen. Adobe empfiehlt die Erstellung eines Segments, das Ihre Interaktionskriterien erfasst, und die Wiederverwendung dieses Segments, wo immer die Interaktion wichtig ist. Ihr Administrator kann diese Definition auch zu einer Metrik in der Datenansicht hochstufen, damit sie für alle verfügbar ist.

Wählen Sie bei der Formulierung Ihrer eigenen Kriterien die Signale aus, die wirklich Wert für Ihre Site angeben. Drei gemeinsame Bausteine für die Interaktion sind:

* **Dauer**: Mindestdauer der Sitzung, z. B. 10 oder mehr Sekunden
* **Tiefe**: Eine Mindestanzahl von Ereignissen oder Seitenansichten, z. B. 2 oder mehr
* **Aktion**: Das Vorhandensein einer Konversion oder eines Schlüsselereignisses, z. B. einer Anmeldung oder eines Kaufs

Sie können sie mit `OR` kombinieren, sodass eine Sitzung als aktiv zählt, wenn sie eine der Bedingungen erfüllt (wie GA4 es tut), oder sie mit `AND` für eine strengere Anforderung kombiniert. Wenn die Parität mit GA4 Ihr Ziel ist, starten Sie von den Standardwerten und stimmen Sie von dort.

### Interaktionsrate

Sobald Sie über eine Definition für interaktive Sitzungen verfügen, ist die Interaktionsrate der Anteil der Sitzungen, die interagiert wurden. So erstellen Sie eine berechnete Metrik:

1. Wählen Sie in Analysis Workspace das Symbol **[!UICONTROL +]** neben der Metrikliste aus, um den Generator für berechnete Metriken zu öffnen.
2. Benennen Sie ihn mit „Interaktionsrate“ und legen Sie das Format auf **[!UICONTROL Prozent]** fest.
3. Definieren Sie die Formel als Ihr Segment für interaktive Sitzungen, geteilt durch **[!UICONTROL Sitzungen]**.
4. Wählen Sie **[!UICONTROL Speichern]** aus.

### Absprungrate

In GA4 ist ein Bounce das Gegenteil einer aktiven Sitzung, sodass die Bounce-Rate von GA4 `1 - Engagement Rate` beträgt. Erstellen Sie sie in Customer Journey Analytics als zweite berechnete Metrik unter Verwendung dieser Formel.

Customer Journey Analytics bietet auch eine integrierte Metrik **[!UICONTROL Absprungrate]**, aber seine Standarddefinition unterscheidet sich: Sie zählt Sitzungen, in denen nur ein einziges Ereignis aufgezeichnet wurde, was der GA4-Definition für viele Sites direkt entgegengesetzt ist. Der Vergleich der Absprungrate von GA4 mit der Standardmetrik [!UICONTROL Absprungrate] - anstatt mit Ihrer `1 - Engagement Rate` Berechnung - erzeugt wesentlich andere Zahlen.

>[!TIP]
>
>Die Sitzungsdefinition in Customer Journey Analytics kann pro Datenansicht konfiguriert werden. Die Bounce- und Interaktionsdefinitionen können an die Kriterien der GA4 angepasst werden (10-sekündige Dauer, 2+ Seitenansichten oder ein Schlüsselereignis), wenn diese Parität für Ihr Unternehmen eine Berichtsanforderung ist.

## Sitzungen

Sowohl GA4 als auch Customer Journey Analytics verwenden standardmäßig ein 30-minütiges Inaktivitäts-Timeout und halten eine Sitzung über Mitternacht und über eine Kampagnenänderung während der Sitzung hinweg aufrecht. (Universal Analytics-Zurücksetzungssitzungen in beiden Fällen, sodass sie eine häufige Verwirrungsquelle darstellen, aber keine Unterschiede zwischen GA4 und Customer Journey Analytics darstellen.) Die Regeln, die sich unterscheiden, sind:

| Regel | GA4 | Customer Journey Analytics |
|---|---|---|
| Zeitüberschreitung bei Inaktivität | Eigenschaftsweit einstellbar (30-Minuten-Standard, bis zu 7 Stunden 55 Minuten) | Konfigurierbar pro Datenansicht |
| Ereignisse für den Sitzungsstart | Nur `session_start` (automatisch) | Konfigurierbar; jedes Ereignis kann eine Sitzung starten |
| Sitzungsende Ereignisse | Keine | Konfigurierbar; jedes Ereignis kann eine Sitzung beenden |

Da die Sitzungsdefinition von Customer Journey Analytics konfigurierbar ist, hängt die Anzahl der Sitzungen von der Einrichtung Ihrer Datenansicht ab. Indem Sie die Zeitüberschreitungs- und Sitzungsstartereignisse einer Datenansicht mit Ihrer GA4-Eigenschaft abgleichen, kommen Sie den Sitzungszahlen zwischen den Plattformen näher.

## Personen und Aktive Benutzer

Die primäre Benutzermetrik von GA4, **Aktive Benutzer**, zählt Benutzer, die mindestens eine engagierte Sitzung im Datumsbereich hatten. Die **[!UICONTROL Personen]**-Metrik in Customer Journey Analytics zählt eindeutige Personen-IDs im Datumsbereich.

Es wird erwartet, dass diese Metriken aus verschiedenen Gründen unterschiedlich sind:

* **Interaktionsschwellenwert**: Aktive GA4-Benutzer schließen Besucher aus, die keine [interaktive Sitzung](#engaged-sessions) hatten. Die [!UICONTROL Personen]-Metrik in Customer Journey Analytics enthält alle unabhängig vom Interaktionsniveau.
* **[!UICONTROL Zuordnung]**: Wenn die Zuordnung aktiviert ist, kann eine Person, die sowohl von einem Mobilgerät als auch von einem Desktop aus besucht hat, in Customer Journey Analytics als eine Person gezählt werden, in GA4 jedoch zwei Benutzende. Beim Zusammenfügen ist die Metrik [!UICONTROL Personen] für zusammengeführte Datensätze in der Regel niedriger als bei GA4-Benutzern.
* **Identitätsmodell**: GA4 verwendet ein kaskadierendes Identitätsmodell; Customer Journey Analytics verwendet die im Datensatz definierte Personen-ID. Diese Unterschiede beeinflussen die Anzahl der Personen unabhängig von der Zuordnung.

## Identität und Zuordnung

GA4 verwendet ein kaskadierendes Identitätsmodell, um Benutzer zu identifizieren:

1. Benutzer-ID (sofern von Ihrer Implementierung festgelegt)
2. Google-Signale (wenn die Benutzerin bzw. der Benutzer bei einem Google-Konto mit aktivierter Personalisierung angemeldet ist)
3. Geräte-ID (Cookie-basierte Client-ID)

In den meisten Implementierungen ist diese Personen-ID eine ECID (Experience Cloud ID). Die optionale **[!UICONTROL Stitching]**-Funktion kann dann geräte- und kanalübergreifende Identitäten mithilfe feldbasierter oder diagrammbasierter Methoden auflösen, sodass eine Mobile-App-Sitzung und eine Desktop-Browser-Sitzung derselben Person zugeordnet werden können.

Da die Identitätsauflösung zwischen den Plattformen unterschiedlich ist, stimmen die Zahlen auf Benutzerebene selten genau überein. Diese Diskrepanz ist zu erwarten und weist nicht auf ein Datenqualitätsproblem hin.

## Attribution

GA4 wendet ein Attributionsmodell für Berichte an, das auf der Eigenschaftsebene (unter „Admin„) konfiguriert ist, mit datengesteuerter Attribution als Standard. Wie Customer Journey Analytics bewertet auch GA4 dieses Modell zum Zeitpunkt der Berichterstellung. Durch die Änderung werden daher historische und zukünftige Berichte rückwirkend aktualisiert. In GA4 ist das Modell jedoch eigenschaftsweit und betrifft nur Berichte mit Schlüsselereignissen, die Traffic-Dimensionen im Ereignisbereich verwenden (z. B. Source, Medium und Campaign).

Customer Journey Analytics wendet die Attribution auch zum Zeitpunkt der Berichterstellung an, jedoch mit granularerer Steuerung. Es gibt zwei Stellen, an denen dies konfiguriert werden kann:

* **Einstellungen für die Datenansicht**: Ein [Attributionsmodell](/help/data-views/component-settings/attribution.md) kann für jede Metrikkomponente in der Datenansicht festgelegt werden, wodurch der Standard für diese Metrik für alle Berichte festgelegt wird. Standardmäßig wird kein Attributionsmodell angewendet. Sie können eine Datenansicht so konfigurieren, dass sie mehrere Kopien derselben Metrik enthält, wobei jede Kopie ein anderes standardmäßiges Attributionsmodell verwendet.
* **Überschreibung auf Komponentenebene**: Nachdem Sie eine Metrik in eine [!UICONTROL Freiformtabelle“ gezogen ], klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift und wählen Sie **[!UICONTROL Nicht-Standard-Attributionsmodell verwenden]** aus, um sie für diese Instanz zu überschreiben. Sie können dieselbe Metrik auch mehrmals in die Tabelle ziehen, wobei jeweils ein anderes Attributionsmodell für einen direkten Seitenvergleich verwendet wird.

Da GA4 standardmäßig auf die datengesteuerte Attribution festgelegt ist und Customer Journey Analytics kein Modell anwendet, außer Sie konfigurieren eines, unterscheiden sich die Konversions- und Kanalmetriken wahrscheinlich, bis Sie sie anpassen. Das Festlegen von GA4 auf ein Modell mit dem letzten Klick und das Konfigurieren eines passenden Letztkontaktmodells in Customer Journey Analytics ist die zuverlässigste Methode, um eine ähnliche Baseline festzulegen. Jede Modelländerung in Customer Journey Analytics gilt rückwirkend für alle historischen Daten ohne erneute Verarbeitung.

## Diskrepanzen beim Auditing

Wenn die Zahlen die erwarteten Werte überschreiten, stehen drei Prüfpfade zur Verfügung:

* **Assurance**: Das produktinterne Validierungs-Tool von Adobe bestätigt, dass XDM-Ereignisse korrekt ausgelöst werden, den Edge Network erreichen und in Platform-Datensätze geschrieben werden. Verwenden Sie dieses Tool, um Ihre Implementierung zu überprüfen, bevor Sie die Berichtszahlen vergleichen.
* **Datensatzvorschauen**: In der Platform-Benutzeroberfläche können Sie Rohzeilen in jedem Datensatz in der Vorschau anzeigen. Vergleichen Sie diese mit dem DebugView- oder BigQuery-Export von GA4, um die Genauigkeit auf Feldebene zu überprüfen.
* **Adobe Consulting**: Bei anhaltenden, nicht erläuterten Diskrepanzen kann Ihr Adobe-Account-Team ein formelles Implementierungs-Audit mit einem Adobe-Berater arrangieren.
* **Aufnahmeprüfung**: Wenn Sie vermuten, dass die Diskrepanz davon stammt, wie allgemeine Daten in Platform und nicht in Berichtsdefinitionen importiert wurden, überprüfen Sie die Aufnahmeeinrichtung in [Daten aus Google Analytics migrieren](/help/use-cases/third-party/ga/overview.md).
