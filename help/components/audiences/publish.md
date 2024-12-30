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




In diesem Abschnitt wird beschrieben, wie Sie Zielgruppen, die beim Customer Journey Analytics identifiziert wurden, in [Echtzeit-Kundenprofil) in Adobe Experience Platform ](https://experienceleague.adobe.com/de/docs/experience-platform/profile/home) Targeting und Personalisierung erstellen und veröffentlichen.

Lesen Sie diesen [Überblick](/help/components/audiences/audiences-overview.md), um sich mit dem Konzept des Customer Journey Analytics-Zielgruppen vertraut zu machen.

## Erstellen und Veröffentlichen einer Zielgruppe {#create}

1. Führen Sie einen der folgenden Schritte aus, um eine Zielgruppe zu erstellen und zu veröffentlichen:

   | Erstellungsmethode | Details |
   | --- | --- |
   | Innerhalb der **[!UICONTROL Zielgruppen]**-Oberfläche. | Wählen **[!UICONTROL Komponenten]** > **[!UICONTROL Zielgruppen]** aus dem Hauptmenü Customer Journey Analytics aus. Die Benutzeroberfläche „Zielgruppen“ wird angezeigt. Wählen Sie **[!UICONTROL Zielgruppe erstellen]** und der [!UICONTROL Audience Builder] wird geöffnet. |
   | Von einer Visualisierung in Analysis Workspace | Viele Visualisierungen in Analysis Workspace ermöglichen es Ihnen, mithilfe des Kontextmenüs eine Zielgruppe zu erstellen. Sie können beispielsweise **[!UICONTROL Zielgruppe erstellen]** aus dem Kontextmenü eines Elements in einer [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) oder eines Knotens auf der [Journey-Arbeitsfläche ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).<p>Mit dieser Methode wird der Filter im Audience Builder vorab mit der ausgewählten Dimension oder dem ausgewählten Dimensionselement ausgefüllt.</p><p>Mit den folgenden Visualisierungen können Sie mithilfe des Kontextmenüs eine Zielgruppe erstellen:</p><ul><li>[Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Fluss](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[Journey-Arbeitsfläche](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Hinweis:** Zielgruppen können keine berechneten Metriken enthalten. Wenn Sie versuchen, eine Zielgruppe zu erstellen, die eine berechnete Metrik enthält, wird die berechnete Metrik nicht in die Zielgruppendefinition einbezogen.</p> |
   | Über die Benutzeroberfläche zur Erstellung/Bearbeitung von Filtern: | Markieren Sie das Kästchen **[!UICONTROL Zielgruppe über diesen Filter erstellen]**. Mit dieser Methode wird der Filter vorab ausgefüllt. Siehe [Filter erstellen](/help/components/filters/create-filters.md) für weitere Informationen. |

   {style="table-layout:auto"}

1. Erstellen Sie die Zielgruppe mit dem [Audience Builder](#audience-builder).

1. Interpretieren Sie die Daten mithilfe des Bedienfelds [Datumsvorschau](#data-preview).

1. Wählen Sie **[!UICONTROL [!UICONTROL Beispiel-IDs anzeigen]]**, um ein Beispiel von IDs in dieser Zielgruppe anzuzeigen. Im Dialogfeld **[!UICONTROL Beispiel-IDs]** können Sie ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *Beispiel-IDs suchen*] um nach Beispiel-IDs zu suchen.

1. Überprüfen Sie Ihre Zielgruppenkonfiguration und wählen Sie **[!UICONTROL Publish]** aus.
Sie erhalten eine Bestätigungsnachricht, dass die Zielgruppe veröffentlicht wurde. Es dauert nur ein bis zwei Minuten, bis diese Zielgruppe im Experience Platform angezeigt wird.

1. Wählen **[!UICONTROL in derselben Nachricht „Zielgruppe in AEP]**&quot; aus und Sie gelangen zur [Segment-Benutzeroberfläche](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview) in Adobe Experience Platform. Weitere Informationen finden Sie unten.

## Audience Builder

Konfigurieren Sie diese Einstellungen, um Ihre Audience zu definieren oder zu aktualisieren.

![Screenshot von „Zielgruppe erstellen“ mit Einstellungen, die im nächsten Abschnitt beschrieben werden.](assets/create-audience.png)

| Einstellung | Beschreibung |
| --- | --- |
| ![Daten](/help/assets/icons/Data.svg) | Datenansicht auswählen, die für die Erstellung der Zielgruppe verwendet werden soll. |
| **[!UICONTROL Name]** | Der Name der Zielgruppe. Beispiel: `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Tags]** | Alle Tags, die Sie der Zielgruppe zu organisatorischen Zwecken zuweisen möchten. Sie können ein oder mehrere bereits vorhandene Tags auswählen oder ein neues eingeben. |
| **[!UICONTROL Beschreibung]** | Eine Beschreibung der Zielgruppe, um sie von anderen zu unterscheiden. Beispiel: `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Häufigkeit der Aktualisierung]** | Die Häufigkeit, mit der Sie die Zielgruppe aktualisieren möchten.<p/>Sie können zwischen folgenden Optionen wählen <ul><li>**[!UICONTROL Einmalige]** Zielgruppe: Eine Zielgruppe (Standard), die nicht aktualisiert werden muss. Diese Option kann beispielsweise für bestimmte einmalige Kampagnen hilfreich sein.<br/>Sie müssen einen **[!UICONTROL einmaligen Datumsbereich“]**. Sie können ![Kalender](/help/assets/icons/Calendar.svg) verwenden, um einen Datumsbereich einzugeben.</li><li>Eine erfrischende Zielgruppe. Sie können aus den folgenden Optionen auswählen:<ul><li>**[!UICONTROL Alle 4 Stunden]**: Eine Zielgruppe, die alle 4 Stunden aktualisiert wird.</li><li>**[!UICONTROL Täglich]**: eine Zielgruppe, die täglich aktualisiert wird</li><li>**[!UICONTROL Wöchentlich]**: Eine Zielgruppe, die wöchentlich aktualisiert wird.</li><li>**[!UICONTROL Monatlich]**: eine Zielgruppe, die monatlich aktualisiert wird</li></ul></li>Zum Aktualisieren von Zielgruppen müssen Sie Folgendes angeben:<ul><li>**[!UICONTROL Lookback-Fenster]**. Definieren Sie die Anzahl der Lookback-Tage ab heute, ab denen eine Zielgruppe ausgewertet wird. Sie können aus Optionen auswählen oder eine benutzerdefinierte Zeit definieren. Die maximale Wartezeit beträgt 90 Tage.</li><li>**[!UICONTROL Ablaufdatum]**: Legt fest, wann die Aktualisierung der Zielgruppe beendet wird. Sie können ![Kalender](/help/assets/icons/Calendar.svg) verwenden, um ein Datum auszuwählen. Der Standardwert liegt bei 1 Jahr ab dem Erstellungsdatum. Vor der Beendigung der Zielgruppen-Aktualisierung werden ablaufende terminierte Berichte ähnlich gehandhabt. Der Administrator erhält einen Monat vor Ablauf der Zielgruppe eine E-Mail.</li></ul> Beachten Sie, dass es je nach Ihrer Customer Journey Analytics-Berechtigung ein Limit von 75 bis 150 Zielgruppen-Aktualisierungen gibt.</li></ul> |
| **[!UICONTROL Filter]** | Filter sind die Hauptauswahloptionen für die Zielgruppe. Ziehen Sie einen oder mehrere Filter aus dem linken Bedienfeld ![Segmentierung](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filter]** in den Filterbereich. Sie können die Filter ![Suche](/help/assets/icons/Search.svg) [!UICONTROL *Suchfilter*] verwenden. Sie können bis zu 20 Filter hinzufügen. Filter können mit den Operatoren **[!UICONTROL Und]** oder **[!UICONTROL Oder]** verbunden werden.<p>Beim Erstellen einer Zielgruppe aus einer Visualisierung in Analysis Workspace (z. B. einer Freiformtabelle oder einer Journey-Arbeitsfläche) werden alle auf das Bedienfeld oder die Spalte angewendeten Filter beibehalten. Sie können alle Filter entfernen, die automatisch angewendet werden.</p> |
| **[!UICONTROL Datenvorschau]** | Wählen Sie ![Info](/help/assets/icons/Info.svg) aus, um die [Datenvorschau](#data-preview) für den ausgewählten Datumsbereich ein- oder auszublenden. |

## Datenvorschau

Das Bedienfeld Datenvorschau enthält die folgenden Informationen.

| Element | Beschreibung |
| --- | --- |
| **[!UICONTROL Personen insgesamt]** | Die Gesamtzahl der Personen in dieser Zielgruppe. Die maximale Größe beträgt 20 Millionen Menschen. Wenn Ihre Zielgruppe mehr als 20 Millionen Personen umfasst, müssen Sie die Zielgruppengröße verringern, bevor Sie veröffentlichen können. |
| **[!UICONTROL Zielgruppen-Limit]** | Visualisierung, die zeigt, wie weit diese Zielgruppe vom Limit von 20 Millionen entfernt ist. |
| **[!UICONTROL Geschätzte Zielgruppenrendite]** | Sie können diesen Wert verwenden, um Personen in dieser Zielgruppe, die zu Ihrer Site, Ihrer Mobile App oder einem anderen Kanal zurückkehren, erneut anzusprechen.<p>Sie können den Zeitrahmen (**[!UICONTROL Nächste 7 Tage]**, **[!UICONTROL Nächste 2 Wochen]** oder **[!UICONTROL Nächster Monat]**) für die geschätzte Anzahl der Kundinnen und Kunden auswählen, die möglicherweise zurückkehren. |
| **[!UICONTROL Voraussichtliche Rückkehr]** | Mit dieser Zahl erhalten Sie eine geschätzte Anzahl an wiederkehrenden Kunden über den von Ihnen ausgewählten Zeitraum. Diese Zahl wird anhand der historischen Abwanderungsrate für diese Zielgruppe prognostiziert. |
| **[!UICONTROL Metriken in der Vorschau anzeigen]** | Sie können eine bestimmte Metrik auswählen, um zu sehen, wie die Daten für diese Metrik auf der von Ihnen definierten Audience basieren.  Jede Vorschaumetrik zeigt eine Gesamtsumme für die Metrik basierend auf der Audience an. Und ein Prozentsatz der zielgruppenbasierten Metrik von der Gesamtsumme der Metrik, wie durch die Datenansicht definiert. Beispielsweise sind 381 Personen (die von Ihnen ausgewählte Metrik) das Ergebnis Ihrer Zielgruppendefinition, was 5 % der insgesamt in der Datenansicht verfügbaren Personen entspricht. Sie können eine beliebige Metrik auswählen, die in Ihrer Datenansicht verfügbar ist. |
| **[!UICONTROL Enthaltene Namespaces]** | Die spezifischen Namespaces, die mit den Personen in Ihrer Zielgruppe verknüpft sind. Beispiele sind ECID, CRM-ID, E-Mail-Adressen usw. |
| **[!UICONTROL Sandbox]** | Die [Experience Platform-Sandbox](https://experienceleague.adobe.com/de/docs/experience-platform/sandbox/home), in der sich diese Zielgruppe befindet. Wenn Sie diese Zielgruppe in Platform veröffentlichen, können Sie nur innerhalb dieser Sandbox mit der Zielgruppe arbeiten. |

{style="table-layout:auto"}

## Was passiert, nachdem eine Zielgruppe erstellt und veröffentlicht wurde? {#after-audience-created}

Nachdem Sie eine Zielgruppe auf Customer Journey Analytics erstellt und veröffentlicht haben, ist sie auf Experience Platform verfügbar. Ein Adobe Experience Platform-Streaming-Segment wird nur erstellt, wenn für Ihre Organisation Streaming-Segmentierung eingerichtet ist.

* Die Zielgruppe in Platform hat denselben Namen und dieselbe Beschreibung wie die Customer Journey Analytics-Zielgruppe. An den Namen wird die Customer Journey Analytics-Zielgruppen-ID angehängt, um sicherzustellen, dass die Zielgruppe eindeutig ist.
* Alle Änderungen am Namen oder an der Beschreibung der Zielgruppe in Customer Journey Analytics werden auf Experience Platform übernommen.
* Wenn eine Zielgruppe auf Customer Journey Analytics gelöscht wird, ist die Zielgruppe weiterhin auf Experience Platform verfügbar, bis die Profilmitgliedschaft der Zielgruppe abläuft. Die Profilmitgliedschaft läuft für einmalige Zielgruppen nach 420 Tagen und für wiederkehrende Zielgruppen nach 16 Tagen ab.

## Latenzaspekte {#latency}

An verschiedenen Stellen vor, während und nach der Veröffentlichung von Zielgruppen können Latenzen auftreten. Im Folgenden finden Sie einen Überblick über mögliche Latenzen.

![Latenzen in der Zielgruppenveröffentlichung, wie in diesem Abschnitt beschrieben.](assets/latency-diagram.svg)

|  | Latenzpunkt | Latenzdauer |
| --- | --- | --- |
| Nicht angezeigt | Adobe Analytics zu Analytics-Quell-Connector (A4T) | Bis zu 30 Minuten |
| 1 | Datenaufnahme in den Data Lake (aus dem Analytics-Quell-Connector oder anderen Quellen) | Bis zu 90 Minuten |
| 2 | Datenaufnahme aus dem Experience Platform Data Lake in den Customer Journey Analytics | Bis zu 90 Minuten |
| 3 | Zielgruppenveröffentlichung im Echtzeit-Kundenprofil, einschließlich der automatischen Erstellung des Streaming-Segments, sodass das Segment bereit für den Empfang der Daten ist. | Ein paar Sekunden |
| 4 | Aktualisierungshäufigkeit für Zielgruppen | <ul><li>Einmalige Aktualisierung (Latenz von weniger als 5 Minuten)</li><li>Aktualisierung alle 4 Stunden, täglich, wöchentlich, monatlich (die Latenz wird mit der Aktualisierungsrate in Verbindung gebracht) |
| 5 | Erstellen eines Ziels in Adobe Experience Platform: Aktivieren des neuen Segments | 1–2 Stunden |

{style="table-layout:auto"}

## Verwenden von Customer Journey Analytics-Zielgruppen beim Experience Platform {#audiences-aep}

Customer Journey Analytics nimmt alle Namespace- und ID-Kombinationen aus Ihrer veröffentlichten Zielgruppe und streamt sie in Real-time Customer Data Platform . Beim Customer Journey Analytics wird die Zielgruppe entsprechend der beim Verbindungsaufbau gewählten [!UICONTROL Personen-ID“ mit dem primären Identitätssatz ] Experience Platform gesendet.

Real-time Customer Data Platform untersucht dann jede Namespace/ID-Kombination und sucht nach einem Profil, zu dem sie gehören könnte. Ein Profil ist im Grunde eine Gruppe verknüpfter Namespaces, IDs und Geräte. Wenn ein Profil gefunden wird, werden der Namespace und die ID zu den anderen IDs in diesem Profil als Segmentzugehörigkeitsattribut hinzugefügt. Beispielsweise können <user@adobe.com> auf allen Geräten und Kanälen als Ziel ausgewählt werden. Wenn kein Profil gefunden wird, wird ein neues erstellt.

So zeigen Sie Customer Journey Analytics-Zielgruppen in Platform an:

1. Erweitern Sie **[!UICONTROL Kunde]** im linken Bereich und wählen Sie dann **[!UICONTROL Zielgruppen]** aus<!-- is there a folder called "Customer Journey Analytics? -->

1. Wählen Sie die Registerkarte **[!UICONTROL Durchsuchen]** aus.

1. Führen Sie einen der folgenden Schritte aus, um die von Customer Journey Analytics veröffentlichte Zielgruppe zu finden:

   ![Option „Zielgruppen“ im linken Bedienfeld](assets/aep-audiences.png)

   * Sortieren Sie die Tabelle nach der Spalte **[!UICONTROL Herkunft]**, um Zielgruppen anzuzeigen, die [!UICONTROL **Customer Journey Analytics**] als Herkunft aufweisen.

   * Filtern Sie ![](/help/assets/icons/Filter.svg) nach **[!UICONTROL Herkunft]** und wählen Sie **[!UICONTROL Customer Journey Analytics]**.

   * Verwenden Sie das ![Suche](/help/assets/icons/Search.svg)-Suchfeld.

Weitere Informationen zur Verwendung von Zielgruppen in Platform finden Sie [ Abschnitt „Zielgruppen](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) im [Handbuch zur Benutzeroberfläche von Segment Builder](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) in der Experience Platform-Dokumentation.


## Häufig gestellte Fragen (FAQ) {#faq}

Häufig gestellte Fragen zur Veröffentlichung von Zielgruppen.

+++**Was passiert, wenn eine Benutzerin bzw. ein Benutzer nicht mehr Mitglied einer Zielgruppe auf Customer Journey Analytics ist?**

In diesem Fall wird ein Beendigungsereignis von Customer Journey Analytics an Experience Platform gesendet.

+++

+++**Was passiert, wenn eine Zielgruppe auf Customer Journey Analytics gelöscht wird?**

Wenn eine Customer Journey Analytics-Zielgruppe gelöscht wird, wird diese Zielgruppe nicht mehr in der Experience Platform-Benutzeroberfläche angezeigt. Profile, die mit dieser Zielgruppe verknüpft sind, werden jedoch nicht in Experience Platform gelöscht.

+++

+++**Wenn in Real-time Customer Data Platform kein entsprechendes Profil vorhanden ist, wird dann ein neues Profil erstellt?**

Ja.

+++

+++**Sendet Customer Journey Analytics die Zielgruppendaten als Pipeline-Ereignisse oder als Einfachdatei, die auch an den Data Lake gesendet wird?**

Customer Journey Analytics streamt die Daten über die Pipeline in Real-time Customer Data Platform, und diese Daten werden auch in einem Systemdatensatz im Data Lake erfasst.

+++

+++**Welche Identitäten sendet Customer Journey Analytics?**

Die Identitäts-/Namespace-Paare, die bei der [Verbindungseinrichtung“ angegeben ](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-connections/create-connection). Insbesondere der Schritt, in dem ein Benutzer das Feld auswählt, das er als Personen-ID verwenden möchte.

+++

+++**Welche ID wird als primäre Identität ausgewählt?**

Siehe oben. Pro Customer Journey Analytics-Person wird nur eine Identität gesendet.

+++

+++**Verarbeitet Real-time Customer Data Platform auch die Customer Journey Analytics-Nachrichten? Kann Customer Journey Analytics einem Profilidentitätsdiagramm durch Zielgruppenfreigabe Identitäten hinzufügen?**

Nein. Pro Person wird nur eine Identität gesendet, sodass Real-time Customer Data Platform keine Diagrammkanten nutzen kann.

+++

+++**Zu welcher Tageszeit werden täglich, wöchentlich und monatlich Aktualisierungen vorgenommen? An welchem Wochentag werden die Wochentage aktualisiert?**

Der Zeitpunkt der Aktualisierung basiert auf dem Zeitpunkt der Veröffentlichung der ursprünglichen Zielgruppe und auf dieser Tageszeit (und dem Wochentag oder Monat).

+++

+++**Kann die tägliche, wöchentliche und monatliche Aktualisierungszeit konfiguriert werden?**

Nein, Benutzende können den Zeitpunkt der Aktualisierung nicht konfigurieren.

+++


## Nächste Schritte

* Um diese Zielgruppe zu verwalten, navigieren Sie zur [Verwaltungs-Benutzeroberfläche](/help/components/audiences/manage.md).
