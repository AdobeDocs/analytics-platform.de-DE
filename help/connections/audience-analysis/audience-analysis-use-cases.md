---
title: Anwendungsfälle für die Zielgruppenanalyse
description: Lernen Sie Anwendungsfälle für die Zielgruppenanalyse kennen.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
exl-id: 4f465e71-f1b5-4f38-a1db-645550856849
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Anwendungsfälle für die Zielgruppenanalyse {#analyze-audiences-use-cases}

Die Zielgruppenanalyse ermöglicht das Reporting von Daten zur Zielgruppenzugehörigkeit zu Experience Platform in Customer Journey Analytics. Dies wird durch Konfigurationen erreicht, die über den Konfigurationsassistenten für Zielgruppenanalysen verwaltet werden. Dieser hilft Ihnen dabei, zu bestimmen, welchen Profildatensatz Sie aufnehmen, sowie andere Parameter und Konfigurationsdetails. (Weitere Übersichtsinformationen finden Sie unter [Übersicht über die Zielgruppenanalyse](/help/connections/audience-analysis/audience-analysis-overview.md).)

Dieses Dokument enthält Beispielanwendungsfälle, die den Wert von Audience Analysis verdeutlichen. Bevor Sie sich die Anwendungsfälle ansehen, machen Sie sich zunächst mit den folgenden Überlegungen zum Reporting vertraut. Es ist wichtig, diese Überlegungen beim Durchgehen Ihrer Anwendungsfälle zu beachten, da sie sich auf die endgültige Ausgabe Ihrer Berichte auswirken können.

## Überlegungen zum Reporting

Die erste Version von Audience Analysis schafft die notwendigen Grundlagen für die Verarbeitung und Aufnahme von Experience Platform-Zielgruppen in Customer Journey Analytics. Beachten Sie bei der Analyse verschiedene Faktoren, die Ihre Ergebnisse in allen Workspace-Projekten beeinflussen können:

* **Daten zur Zielgruppenzugehörigkeit sind nur für den Vortag („gestern„) korrekt**: Die Daten zur Zielgruppenzugehörigkeit enthalten immer den neuesten Profil-Schnappschuss-Datensatz, der vom einheitlichen Profil-Service generiert wurde. Dieser Profildatensatz ist eine tägliche Momentaufnahme und ist nur für den Vortag („gestern„) korrekt, wobei er jede Nacht automatisch neu generiert und neu verarbeitet wird. Zielgruppendimensionen sind für Berichte und Aufschlüsselungen verfügbar, nicht zur Rekonstruktion historischer Zielgruppenzustände.

   * Beispiel: Unabhängig vom ausgewählten Berichtszeitfenster respektiert die berichtspflichtige Zielgruppe von CJA immer den Status der Zielgruppenzugehörigkeit, der in der letzten erfassten Profilschnappschuss („gestern„) vorhanden ist.

      * Die Ausweitung des Reporting-Zeitfensters auf beispielsweise „letzte 30 Tage“ umfasst mehr Ereignisse und vermittelt den Eindruck, dass sich die Zielgruppengröße ändert. Die Profilzusammensetzung der Zielgruppe entspricht jedoch immer dem Schnappschuss von „gestern“, unabhängig vom ausgewählten Zeitfenster.

* **Dimensionen müssen ein entsprechendes Ereignis aufweisen, um einbezogen zu werden**: Zielgruppenanalysedimensionen können nur analysiert werden, wenn entsprechende Ereignisse in CJA vorhanden sind. Wenn ein Verhalten, ein Kanal oder ein Lebenszyklusmoment nicht als Ereignis in der CJA-Verbindung dargestellt wird, kann es nicht analysiert werden.

   * Beispiel: Eine Zielgruppe, die verwendet wird, um Personen mit einer Anzeige anzusprechen, würde erheblich mehr Personen in die RTCDP-Zielgruppe aufnehmen als in die CJA-Zielgruppe. Dies liegt daran, dass die CJA-Zielgruppe auf Personen beschränkt ist, die während des Berichtszeitraums ein Ereignis in CJA hatten.

* **Die Identitätsauflösung basiert ausschließlich auf einem einzelnen Namespace**: Die Identitätsauflösung hängt vollständig vom ausgewählten Identity-Namespace als Teil der Zielgruppenanalyse-Konfiguration ab. Die Analyse ist auf diesen Identity-Namespace beschränkt, wobei Ereignisse, die außerhalb dieses Namespace liegen, nicht für das Reporting zur Zielgruppenanalyse verfügbar sind.

   * Beispiel: Für einen zugeordneten Ereignisdatensatz, der CRM und ECID kombiniert und die Zielgruppenanalysekonfiguration die CRM-ID verwendet, werden nur Zeilen, die eine CRM-ID enthalten, als Teil der berichtspflichtigen Zielgruppe in CJA erkannt. Daher kann die resultierende Zielgruppengröße kleiner sein als erwartet.

## Beispielhafte Anwendungsfälle

### Anwendungsfall 1

Erfahren Sie, wie sich eine bestimmte Zielgruppe in einem bestimmten Kanal (z. B. Web oder App) verhält, um Fragen wie diese zu beantworten:

* _„Was machen derzeit Mitglieder von High-Value Prospects auf der Website (Seiten, Funktionen, Trichter)?“_

* _„Welche Kampagnen und Inhalte überindizieren diese Zielgruppe im Vergleich zu allen anderen?“_

#### Konfigurationsablauf

1. Konfigurieren Sie die Zielgruppenanalyse in CJA für einen einzigen Identity-Namespace (z. B. ECID oder CRM_ID) und eine Web-orientierte Datenansicht.

   * Dadurch werden die Daten zur Zielgruppenzugehörigkeit über den täglichen Schnappschuss-Export der Profile automatisch in die ausgewählte Verbindung aufgenommen

   * Es wird empfohlen, den Identity-Namespace auszuwählen, von dem Sie glauben, dass er in Ihrem Ereignis-Datensatz die größte Abdeckung hat

1. Erstellen Sie Ihre Workspace-Projekte, um:

   * Audience-Name nach Seite, Produkt, Kampagne, Gerät usw. aufschlüsseln

   * Vergleichen Sie Zielgruppe mit Nicht-Zielgruppe (oder mit einer anderen Zielgruppe) in Metriken wie Sitzungen, Konversionsrate, Umsatz pro Person.

1. Verwenden Sie die generierten Einblicke, um Strategien zur Kanaloptimierung (z. B. Zielgruppenbestimmungsregeln, Inhalts- oder Angebotsoptimierung) anzupassen.

#### Überlegungen zur Identitätsauflösung

| Anwendungsfall | Kerngeschäftsfrage | Überlegungen zur Identitätsauflösung | Organisationen mit hoher Authentifizierung/einem einzelnen Namespace (Ereignisse, die bereits unter einer Personen-ID liegen, z. B. Anmeldung/CRM) | Fragmentierte Organisationen/Organisationen mit mehreren Namespaces (Ereignisse unter ECID + CRM + andere) |
|---------|----------|---------|---------|---------|
| Detaillierte Einblicke in das Verhalten der aktuellen Zielgruppe | _„Was macht Audience X gerade in Kanal Y?“ (Seiten, Trichter, Inhalte, Angebote)_ | Ereignisse und Profile müssen einen einheitlichen Identity-Namespace in der Konfiguration von CJA Connection und Audience Analysis gemeinsam nutzen, um eine optimale Abdeckung zu gewährleisten. | Die meisten Aktivitäten sind bereits an eine Anmelde-/CRM-ID gebunden, sodass sich Zielgruppen aus AEP sauber zu Verhaltensdaten in CJA verbinden. <p>Sie erhalten einen klaren Überblick darüber, was jede Zielgruppe in einem bestimmten Kanal mit minimalen erwarteten Berichtslücken tut.</p> | Selbst wenn Berichte mit einem zugeordneten Datensatz verbunden werden, sind sie auf den einzelnen Identity-Namespace beschränkt, der in der Konfiguration ausgewählt wird. <p>Wenn einige Kunden unter anderen IDs vorhanden sind, wird ihr Verhalten nicht einbezogen, was zu einer partiellen Ansicht während des Reportings führen kann.</p> |

### Anwendungsfall 2

Helfen Sie Marketing- oder Journey-Designern zu verstehen, welche Zielgruppen sich überschneiden, damit sie Erlebnisse deduplizieren und Angebotskollisionen in allen Kampagnen vermeiden können:

* _„Wie viele Überschneidungen gibt es heute zwischen Mitgliedern des Treueprogramms, Abbrechern vom Warenkorb und einer hohen Abwanderungsneigung?“_

* _„Welche Zielgruppen stoßen diese Woche am ehesten auf hochwertige Werbeangebote?“_

#### Konfigurationsablauf

1. Konfigurieren Sie die Zielgruppenanalyse in CJA für einen einzigen Identity-Namespace, der an der RTCDP-/AJO-Aktivierung ausgerichtet ist (z. B. CRM_ID, wenn die Journey personenbasiert sind).

   * Dadurch werden die Daten zur Zielgruppenzugehörigkeit automatisch über den täglichen Schnappschuss-Export der Profile in die ausgewählte Verbindung aufgenommen.

   * Dies kann verwendet werden, um eine vorhandene Datenansicht anzureichern, die bereits wichtige Interaktions- und Konversionsberichte ermöglicht.

1. Verwenden Sie die vordefinierte Vorlage Zielgruppenanalyse - Übersicht und Überschneidungsvisualisierungen:

   * Führen Sie Zielgruppenüberschneidungen und Ansichten für Über-/Unterindizierung aus (z. B. % der Warenkorbabbrecher, die sich auch in Treueprogramm-Gold befinden).

   * Slice überschneidet sich nach Kerndimensionen (z. B. Gerätetyp, Produktinteresse), um zu verstehen, wo Konflikte am wichtigsten sind.

1. Verwenden Sie die Einblicke zur Feinabstimmung kritischer Aspekte, z. B.:

   * Regeln für Angebotskonflikte oder Marketing-Aktionen in RTCDP und AJO.

   * Zielgruppenverfeinerung (z. B. Verschärfung der Zielgruppendefinitionen bei zu hoher Überschneidung).

#### Überlegungen zur Identitätsauflösung

| Anwendungsfall | Kerngeschäftsfrage | Überlegungen zur Identitätsauflösung | Organisationen mit hoher Authentifizierung/einem einzelnen Namespace (Ereignisse, die bereits unter einer Personen-ID liegen, z. B. Anmeldung/CRM) | Fragmentierte Organisationen/Organisationen mit mehreren Namespaces (Ereignisse unter ECID + CRM + andere) |
|---------|----------|---------|---------|---------|
| Zielgruppenüberschneidung und Kollisionserkennung | _„Welche Zielgruppen überschneiden sich heute, sodass wir Angebotskollisionen vermeiden können?“_ | Die Überschneidung wird nur für Zielgruppen berechnet, die dieselbe Personen-ID verwenden und deren Aktivität in der CJA-Verbindung ist. | Da die meisten Aktivitäten bereits an eine einzelne Anmelde-/CRM-ID gebunden sind, wird erwartet, dass dies eine zuverlässige Überschneidungszuordnung für alle Zielgruppen bietet. <p>Überlagerungsdiagramme liefern ein zuverlässiges Bild davon, welche Zielgruppen kollidieren und wo Unterdrückungen oder Prioritätsregeln angewendet werden.</p> | Wenn Teile der Journey unter anderen IDs vorhanden sind (z. B. anonymes Durchsuchen der ECID, Callcenter-IDs), werden diese Ereignisse in der Überschneidungsanalyse nicht angezeigt. <p>Personen können weiterhin über mehrere Namespaces hinweg vorhanden sein.</p><p>Die Überschneidung basiert auf dem in der Konfiguration enthaltenen Identity-Namespace. Wenn einige Profile weiterhin auf mehrere IDs aufgeteilt sind, kann es vorkommen, dass Überschneidungen echte Kollisionen zu wenig melden.</p> |

### Anwendungsfall 3

Erfahren Sie mehr über das Verhalten von Kunden, die kürzlich eine wichtige Zielgruppe verlassen haben, und darüber, was sie rund um diesen Ausstieg getan haben, um Fragen zu beantworten wie:

* _„Wer hat gerade eine wichtige Zielgruppe verlassen und was haben sie in Bezug auf Exit gemacht?“_

* _„Was ist vor dem Verlassen passiert? (Fehler, geringe Interaktion, Preisänderungen).“_

#### Konfigurationsablauf

1. Konfigurieren Sie die Zielgruppenanalyse in CJA für einen einzigen Identity-Namespace (z. B. CRM-ID oder Anmelde-ID) und die entsprechenden Datenansichten (Web, App, CRM usw.).

   * Dadurch werden die Daten zur Zielgruppenzugehörigkeit automatisch über den täglichen Schnappschuss-Export der Profile in die ausgewählte Verbindung aufgenommen.

   * Es wird empfohlen, den Identity-Namespace auszuwählen, von dem Sie glauben, dass er in Ihrem Ereignis-Datensatz die größte Abdeckung hat.

1. Verwenden Sie in der Vorlage Zielgruppenanalyse/Zielgruppenübersicht (_gestern_):

   * Aktuelle Mitglieder: wer noch im Publikum ist

   * Ausgetretenes Publikum: Wer ist gestern gegangen?

1. Erstellen Sie Ihre Workspace-Projekte, um:

   * Filtern Sie nach Profilen, die Audience X gestern verlassen haben, und betrachten Sie dann Folgendes:

      * Ihr Verhalten, das zum Austritt führt (letzte Sitzungen, Fehler, Preis-/Angebotsrisiko, Kanalmix).

      * Ihr Verhalten nach dem Ausstieg (wechselten sie ihre Produkte, nahmen sie herab und wurden inaktiv).

   * Schlüsseln Sie die verlassene Kohorte nach Region, Gerät, Beschäftigungsdauer und Wertestufe auf, um wirkungsvolle Taschen zu finden.

1. Verwenden Sie die Einblicke für Journey-Updates und Win-back-Zielgruppenkonfigurationen in RTCDP oder AJO.

#### Überlegungen zur Identitätsauflösung

| Anwendungsfall | Kerngeschäftsfrage | Überlegungen zur Identitätsauflösung | Organisationen mit hoher Authentifizierung/einem einzelnen Namespace (Ereignisse, die bereits unter einer Personen-ID liegen, z. B. Anmeldung/CRM) | Fragmentierte Organisationen/Organisationen mit mehreren Namespaces (Ereignisse unter ECID + CRM + andere) |
|---------|----------|---------|---------|---------|
| Ausgetretene Zielgruppen - Abwanderungsanalyse | _„Wer hat gerade eine wichtige Zielgruppe verlassen?“_ <p>_„Was haben sie in der Umgebung von Exit gemacht?“_</p> | Das Verlassen der Zielgruppe wird mit derselben Personen-ID verfolgt, die für die Verbindung und Zielgruppenkonfiguration verwendet wird. | Ausstiege, die mit einer stabilen Anmelde-/CRM-ID gemessen werden, spiegeln tendenziell wahre Verhaltensänderungen wider. <p>Wenn jemand eine Zielgruppe mit dieser ID verlässt, bedeutet dies normalerweise eine echte Änderung (Abwanderung, Downgrade, Inaktivität).</p><p>Sie können ihr aktuelles Verhalten analysieren, um Journey und Win-back-Angebote mit Zuversicht zu optimieren.</p> | Ausstiege sind nur dort sichtbar, wo Profile und Ereignisse die konfigurierte ID gemeinsam haben und daher sorgfältig interpretiert werden müssen.<p>Verwenden Sie ausgetretene Kohorten als starken Hinweis oder Signal, aber es wird empfohlen, vor kritischen Entscheidungen einen Abgleich mit anderen Datenpunkten durchzuführen.</p> |
