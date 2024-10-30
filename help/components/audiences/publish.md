---
title: Erstellen und Veröffentlichen von Zielgruppen
description: Erfahren Sie, wie Sie Zielgruppen in Customer Journey Analytics veröffentlichen
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 126d2213b97b71ff3116ff53e56217b8b6e7a479
workflow-type: tm+mt
source-wordcount: '1973'
ht-degree: 18%

---

# Erstellen und Veröffentlichen von Zielgruppen {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_refreshfrequency"
>title="Häufigkeit der Aktualisierung"
>abstract="Ermitteln Sie, wie oft die Mitgliedschaft einer Zielgruppe neu ausgewertet wird.<br/>Einmalige Zielgruppen werden nur einmal ausgewertet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_audiencelimit"
>title="Zielgruppen-Limit"
>abstract="Die Aktualisierung von Zielgruppen ist abhängig davon, wie oft sie aktualisiert werden, begrenzt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_component_audiences_refreshlookbackwindow"
>title="Lookback-Fenster aktualisieren"
>abstract="Definieren Sie die Anzahl der Lookback-Tage ab heute, in denen eine Zielgruppe ausgewertet wird."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_component_audiences_audiencesizelimit"
>title="Größenlimit für Zielgruppen"
>abstract="Zielgruppen dürfen maximal 20 Millionen Mitglieder umfassen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_component_audiences_namespacesincluded"
>title="Enthaltene Namespaces"
>abstract="Die Identitäten in dieser Zielgruppe bestehen aus den unten stehenden Namespaces."

<!-- markdownlint-enable MD034 -->




In diesem Thema wird beschrieben, wie Sie Zielgruppen erstellen und veröffentlichen, die im Customer Journey Analytics in [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/de/docs/experience-platform/profile/home) in Adobe Experience Platform identifiziert werden, um Kunden-Targeting und -Personalisierung zu ermöglichen.

Lesen Sie diesen [Überblick](/help/components/audiences/audiences-overview.md) , um sich mit dem Konzept der Customer Journey Analytics-Zielgruppen vertraut zu machen.

## Erstellen und Veröffentlichen einer Zielgruppe {#create}

1. Führen Sie einen der folgenden Schritte aus, um eine Audience zu erstellen und zu veröffentlichen:

   | Erstellungsmethode | Details |
   | --- | --- |
   | Von der Oberfläche von **[!UICONTROL Audiences]** aus. | Wählen Sie im Hauptmenü die Option **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** aus. Die Benutzeroberfläche &quot;Zielgruppen&quot;wird angezeigt. Wählen Sie die Option **[!UICONTROL Erstellen der Audience]** aus und der [!UICONTROL Audience Builder] wird geöffnet. |
   | Aus einer Visualisierung in Analysis Workspace | Mit vielen Visualisierungen in Analysis Workspace können Sie mithilfe des Kontextmenüs eine Zielgruppe erstellen. Sie können beispielsweise **[!UICONTROL Zielgruppe erstellen]** aus dem Kontextmenü eines Elements in einer [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) oder eines Knotens in der [Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) auswählen.<p>Mit dieser Methode wird der Filter im Audience Builder vorab mit der ausgewählten Dimension oder dem Dimensionselement ausgefüllt.</p><p>Mit den folgenden Visualisierungen können Sie eine Zielgruppe mithilfe des Kontextmenüs erstellen:</p><ul><li>[Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Fluss](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Hinweis:** Zielgruppen können keine berechneten Metriken enthalten. Wenn Sie versuchen, eine Zielgruppe zu erstellen, die eine berechnete Metrik enthält, ist die berechnete Metrik nicht in der Zielgruppendefinition enthalten.</p> |
   | Über die Benutzeroberfläche zur Erstellung/Bearbeitung von Filtern: | Markieren Sie das Kästchen **[!UICONTROL Zielgruppe über diesen Filter erstellen]**. Mit dieser Methode wird der Filter vorab ausgefüllt. Weitere Informationen finden Sie unter [Filter erstellen](/help/components/filters/create-filters.md) . |

   {style="table-layout:auto"}

1. Erstellen Sie die Zielgruppe mit dem [Audience Builder](#audience-builder).

1. Interpretieren Sie die Daten mithilfe des Bereichs [Datumsvorschau](#data-preview) .

1. Wählen Sie **[!UICONTROL [!UICONTROL Beispiel-IDs anzeigen]]** aus, um ein Beispiel für IDs in dieser Zielgruppe anzuzeigen. Im Dialogfeld **[!UICONTROL Beispiel-IDs]** können Sie ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *Suchen nach Beispiel-IDs*] verwenden, um nach Beispiel-IDs zu suchen.

1. Überprüfen Sie Ihre Zielgruppenkonfiguration und wählen Sie **[!UICONTROL Publish]** aus.
Sie erhalten eine Bestätigungsmeldung, dass die Zielgruppe veröffentlicht wurde. Die Publikation dauert nur eine oder zwei Minuten, bis diese Audience im Experience Platform angezeigt wird.

1. Wählen Sie in derselben Nachricht die Option **[!UICONTROL Audience in AEP anzeigen]** aus, und Sie gelangen zur [Segmentbenutzeroberfläche](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview) in Adobe Experience Platform. Weitere Informationen finden Sie unten.

## Audience Builder

Konfigurieren Sie diese Einstellungen, um Ihre Audience zu definieren oder zu aktualisieren.

![Screenshot zum Erstellen von Zielgruppen-Sbowing-Einstellungen, beschrieben im nächsten Abschnitt.](assets/create-audience.png)

| Einstellung | Beschreibung |
| --- | --- |
| ![Daten](/help/assets/icons/Data.svg) | Wählen Sie eine Datenansicht aus, die für die Erstellung der Zielgruppe verwendet werden soll. |
| **[!UICONTROL Name]** | Der Name der Zielgruppe. Beispiel: `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Tags]** | Alle Tags, die Sie der Zielgruppe für organisatorische Zwecke zuweisen möchten. Sie können einen oder mehrere bereits vorhandene Tags auswählen oder einen neuen eingeben. |
| **[!UICONTROL Beschreibung]** | Beschreibung der Audience, um sie von anderen zu unterscheiden. Beispiel: `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Häufigkeit der Aktualisierung]** | Die Häufigkeit, mit der Sie die Zielgruppe aktualisieren möchten.<p/>Sie können zwischen <ul><li>**[!UICONTROL Einmalige]** Audience: eine Audience (Standard), die nicht aktualisiert werden muss. Diese Option kann beispielsweise für bestimmte einmalige Kampagnen hilfreich sein.<br/>Sie müssen einen **[!UICONTROL einmaligen Datumsbereich]** angeben. Sie können ![Kalender](/help/assets/icons/Calendar.svg) verwenden, um einen Datumsbereich einzugeben.</li><li>Eine erfrischende Zielgruppe. Sie können aus den folgenden Optionen auswählen:<ul><li>**[!UICONTROL Alle 4 Stunden]** s: Eine Zielgruppe, die alle 4 Stunden aktualisiert wird.</li><li>**[!UICONTROL Täglich]**: Eine Zielgruppe, die täglich aktualisiert wird</li><li>**[!UICONTROL Wöchentlich]**: Eine Zielgruppe, die wöchentlich aktualisiert wird.</li><li>**[!UICONTROL Monatlich]**: Eine Zielgruppe, die monatlich aktualisiert wird</li></ul></li>Für die Aktualisierung von Zielgruppen müssen Sie Folgendes angeben:<ul><li>**[!UICONTROL Lookback-Fenster aktualisieren]**. Definieren Sie die Anzahl der Lookback-Tage ab heute, an denen eine Zielgruppe ausgewertet wird. Sie können aus den Optionen auswählen oder eine benutzerdefinierte Zeit definieren. Die Höchstdauer beträgt 90 Tage.</li><li>**[!UICONTROL Ablaufdatum]**: Definieren Sie, wann die Aktualisierung der Zielgruppe beendet wird. Sie können ![Kalender](/help/assets/icons/Calendar.svg) verwenden, um ein Datum auszuwählen. Der Standardwert liegt bei 1 Jahr ab dem Erstellungsdatum. Das Ablaufen von Zielgruppen wird ähnlich wie das Ablaufen geplanter Berichte behandelt. Der Administrator erhält einen Monat vor Ablauf der Audience eine E-Mail.</li></ul> Beachten Sie, dass je nach Customer Journey Analytics-Berechtigung 75 bis 150 Zielgruppenaktualisierungen vorgenommen werden können.</li></ul> |
| **[!UICONTROL Filter]** | Filter sind die Hauptauswahloptionen für die Zielgruppe. Ziehen Sie einen oder mehrere Filter aus dem linken Bereich ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** in den Filterbereich. Sie können die Suchfilter ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *3} verwenden, um nach Filtern zu suchen.*] Sie können bis zu 20 Filter hinzufügen. Filter können mit den Operatoren **[!UICONTROL UND]** oder **[!UICONTROL ODER]** verbunden werden.<p>Beim Erstellen einer Zielgruppe aus einer Visualisierung in Analysis Workspace (z. B. einer Freiformtabelle oder einer Journey-Arbeitsfläche) bleiben alle auf das Bedienfeld oder die Spalte angewendeten Filter erhalten. Sie können alle automatisch angewendeten Filter entfernen.</p> |
| **[!UICONTROL Datenvorschau]** | Wählen Sie ![Info](/help/assets/icons/Info.svg) aus, um die [Datenvorschau](#data-preview) für den ausgewählten Datumsbereich ein- oder auszublenden. |

## Datenvorschau

Im Bereich Datenvorschau finden Sie die folgenden Informationen.

| Element | Beschreibung |
| --- | --- |
| **[!UICONTROL Personen insgesamt]** | Die Gesamtzahl der Personen in dieser Zielgruppe. Die maximale Größe beträgt 20 Millionen Menschen. Wenn Ihre Zielgruppe mehr als 20 Millionen Benutzer umfasst, müssen Sie die Zielgruppengröße verringern, bevor Sie veröffentlichen können. |
| **[!UICONTROL Zielgruppen-Limit]** | Visualisierung , um anzuzeigen, wie weit diese Zielgruppe von der 20-Millionen-Grenze entfernt ist. |
| **[!UICONTROL Geschätzte Zielgruppenrendite]** | Sie können diesen Wert verwenden, um Personen in dieser Zielgruppe erneut anzusprechen, die zu Ihrer Site, App oder einem anderen Kanal zurückkehren.<p>Sie können den Zeitrahmen (**[!UICONTROL Nächste 7 Tage]**, **[!UICONTROL Nächste 2 Wochen]** oder **[!UICONTROL Nächster Monat]**) für die geschätzte Anzahl von Kunden auswählen, die zurückkehren können. |
| **[!UICONTROL Voraussichtliche Rückkehr]** | Diese Zahl gibt Ihnen eine geschätzte Anzahl an wiederkehrenden Kunden über den von Ihnen ausgewählten Zeitraum. Diese Zahl wird anhand der historischen Abwanderungsrate für diese Zielgruppe prognostiziert. |
| **[!UICONTROL Metriken in der Vorschau anzeigen]** | Sie können eine bestimmte Metrik auswählen, um zu sehen, wie die Daten für diese Metrik auf der von Ihnen definierten Zielgruppe basieren.  Jede Vorschaumetrik zeigt einen Gesamtwert für die Metrik basierend auf der Zielgruppe an. Und ein Prozentsatz der zielgruppenbasierten Metrik vom Gesamtwert der Metrik, wie durch die Datenansicht definiert. Beispielsweise sind 381 Personen (die von Ihnen ausgewählte Metrik) das Ergebnis Ihrer Zielgruppendefinition, was 5 % der Gesamtanzahl der in der Datenansicht verfügbaren Personen entspricht. Sie können eine beliebige Metrik auswählen, die in Ihrer Datenansicht verfügbar ist. |
| **[!UICONTROL Enthaltene Namespaces]** | Die spezifischen Namespaces, die mit den Personen in Ihrer Zielgruppe verknüpft sind. Beispiele sind ECID, CRM-ID, E-Mail-Adressen usw. |
| **[!UICONTROL Sandbox]** | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home), in der sich diese Zielgruppe befindet. Wenn Sie diese Zielgruppe in Platform veröffentlichen, können Sie nur innerhalb der Grenzen dieser Sandbox mit der Zielgruppe arbeiten. |

{style="table-layout:auto"}

## Was passiert, nachdem eine Zielgruppe erstellt und veröffentlicht wurde? {#after-audience-created}

Nachdem Sie eine Zielgruppe im Customer Journey Analytics erstellt und veröffentlicht haben, ist sie im Experience Platform verfügbar. Ein Adobe Experience Platform-Streaming-Segment wird nur erstellt, wenn Ihr Unternehmen für Streaming-Segmentierung eingerichtet ist.

* Die Audience in Platform trägt denselben Namen und dieselbe Beschreibung wie die Customer Journey Analytics-Audience. Der Name wird an die Customer Journey Analytics-Zielgruppen-ID angehängt, um sicherzustellen, dass die Zielgruppe eindeutig ist.
* Alle Änderungen, die am Namen oder an der Beschreibung der Audience im Customer Journey Analytics vorgenommen werden, werden im Experience Platform übernommen.
* Wenn eine Zielgruppe im Customer Journey Analytics gelöscht wird, ist die Zielgruppe bis zum Ablauf der Profilmitgliedschaft der Zielgruppe weiterhin im Experience Platform verfügbar. Die Profilmitgliedschaft läuft für einmalige Zielgruppen nach 420 Tagen und für wiederkehrende Zielgruppen nach 16 Tagen ab.

## Latenzaspekte {#latency}

An verschiedenen Stellen vor, während und nach der Veröffentlichung von Zielgruppen können Latenzen auftreten. Im Folgenden finden Sie einen Überblick über mögliche Latenzen.

![Latenzen beim Veröffentlichen von Zielgruppen, wie in diesem Abschnitt beschrieben.](assets/latency-diagram.svg)

|  | Latenzpunkt | Latenzdauer |
| --- | --- | --- |
| Nicht angezeigt | Quell-Connector von Adobe Analytics zu Analytics (A4T) | Bis zu 30 Minuten |
| 1 | Datenaufnahme in den Data Lake (aus dem Analytics-Quell-Connector oder anderen Quellen) | Bis zu 90 Minuten |
| 2 | Datenerfassung vom Experience Platform Data Lake in Customer Journey Analytics | Bis zu 90 Minuten |
| 3 | Zielgruppenveröffentlichung im Echtzeit-Kundenprofil, einschließlich der automatischen Erstellung des Streaming-Segments, sodass das Segment bereit für den Empfang der Daten ist. | Einige Sekunden |
| 4 | Aktualisierungshäufigkeit für Zielgruppen | <ul><li>Einmalige Aktualisierung (Latenz von weniger als 5 Minuten)</li><li>Aktualisierung alle 4 Stunden, täglich, wöchentlich, monatlich (die Latenz wird mit der Aktualisierungsrate in Verbindung gebracht) |
| 5 | Erstellen eines Ziels in Adobe Experience Platform: Aktivieren des neuen Segments | 1–2 Stunden |

{style="table-layout:auto"}

## Verwenden von Customer Journey Analytics-Zielgruppen in Experience Platform {#audiences-aep}

Customer Journey Analytics übernimmt alle Namespace- und ID-Kombinationen aus Ihrer veröffentlichten Zielgruppe und streamt sie an Real-time Customer Data Platform . Customer Journey Analytics sendet die Zielgruppe mit dem Hauptidentitätssatz an Experience Platform, je nachdem, was bei der Verbindungskonfiguration als [!UICONTROL Personen-ID] ausgewählt wurde.

Real-time Customer Data Platform prüft dann jede Namespace-/ID-Kombination und sucht nach einem Profil, zu dem sie gehören kann. Ein Profil ist im Grunde eine Gruppe verknüpfter Namespaces, IDs und Geräte. Wenn ein Profil gefunden wird, werden der Namespace und die ID den anderen IDs in diesem Profil als Attribut für die Segmentmitgliedschaft hinzugefügt. Beispielsweise kann <user@adobe.com> für alle Geräte und Kanäle als Ziel ausgewählt werden. Wenn kein Profil gefunden wird, wird ein neues erstellt.

Anzeigen von Customer Journey Analytics-Zielgruppen in Platform:

1. Erweitern Sie **[!UICONTROL Kunde]** im linken Bereich und wählen Sie dann **[!UICONTROL Zielgruppen]** <!-- is there a folder called "Customer Journey Analytics? --> aus.

1. Wählen Sie die Registerkarte **[!UICONTROL Durchsuchen]** aus.

1. Führen Sie einen der folgenden Schritte aus, um die von Ihnen unter Customer Journey Analytics veröffentlichte Zielgruppe zu finden:

   ![Option &quot;Zielgruppen&quot;im linken Bereich](assets/aep-audiences.png)

   * Sortieren Sie die Tabelle nach der Spalte **[!UICONTROL Origin]** , um Zielgruppen anzuzeigen, die [!UICONTROL **Customer Journey Analytics**] als Ursprung anzeigen.

   * Filtern Sie ![Filter](/help/assets/icons/Filter.svg) nach **[!UICONTROL Ursprung]** und wählen Sie **[!UICONTROL Customer Journey Analytics]** aus.

   * Verwenden Sie das Suchfeld ![Suche](/help/assets/icons/Search.svg) .

Weitere Informationen zur Verwendung von Zielgruppen in Platform finden Sie im Abschnitt [Zielgruppen](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) im Handbuch zur Benutzeroberfläche von [Segment Builder](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) in der Experience Platform-Dokumentation.


## Häufig gestellte Fragen (FAQ) {#faq}

Häufig gestellte Fragen zur Veröffentlichung von Zielgruppen.

+++**Was passiert, wenn ein Benutzer in Customer Journey Analytics nicht mehr Mitglied einer Zielgruppe ist?**

In diesem Fall wird ein exit -Ereignis von Customer Journey Analytics an Experience Platform gesendet.

+++

+++**Was passiert, wenn Sie eine Audience im Customer Journey Analytics löschen?**

Wenn eine Customer Journey Analytics-Zielgruppe gelöscht wird, wird diese Zielgruppe nicht mehr in der Experience Platform-Benutzeroberfläche angezeigt. Profile, die mit dieser Audience verknüpft sind, werden jedoch nicht im Experience Platform gelöscht.

+++

+++**Wenn kein entsprechendes Profil in Real-time Customer Data Platform vorhanden ist, wird ein neues Profil erstellt?**

Ja.

+++

+++**Sendet Customer Journey Analytics die Zielgruppendaten als Pipeline-Ereignisse oder als flache Datei, die auch zum Data Lake gelangt?**

Customer Journey Analytics streamt die Daten über die Pipeline in Real-time Customer Data Platform, und diese Daten werden auch in einem Systemdatensatz im Data Lake erfasst.

+++

+++**Welche Identitäten sendet Customer Journey Analytics?**

Die Identitäts-/Namespace-Paare, die in der [Verbindungseinrichtung](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection) angegeben wurden. Insbesondere der Schritt, in dem ein Benutzer das Feld auswählt, das er als Personen-ID verwenden möchte.

+++

+++**Welche ID wird als primäre Identität ausgewählt?**

Siehe oben. Pro Customer Journey Analytics wird nur eine Identität gesendet.

+++

+++**Verarbeitet Real-time Customer Data Platform auch die Customer Journey Analytics-Nachrichten? Kann Customer Journey Analytics Identitäten zu einem Profilidentitätsdiagramm durch Zielgruppenfreigabe hinzufügen?**

Nein. Es wird nur eine Identität pro Person gesendet, sodass Real-time Customer Data Platform keine Diagrammränder verwenden kann.

+++

+++**Zu welcher Tageszeit werden tägliche, wöchentliche und monatliche Aktualisierungen vorgenommen? Welchen Wochentag werden wöchentliche Aktualisierungen durchgeführt?**

Der Zeitpunkt der Aktualisierung hängt davon ab, wann die ursprüngliche Zielgruppe veröffentlicht wurde, und verankert diese Tageszeit (und Wochentag oder Monat).

+++

+++**Können Sie die tägliche, wöchentliche und monatliche Aktualisierungszeit konfigurieren?**

Nein, Benutzer können die Aktualisierungszeit nicht konfigurieren.

+++


## Nächste Schritte

* Um diese Zielgruppe zu verwalten, navigieren Sie zur [Verwaltungs-Benutzeroberfläche](/help/components/audiences/manage.md).
