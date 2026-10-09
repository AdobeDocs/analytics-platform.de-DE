---
title: Konfiguration der eingehenden Markensichtbarkeit-Integration
description: Erfahren Sie, wie Sie die Integration von Markensichtbarkeit mit Customer Journey Analytics konfigurieren
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fbbb3ffb1b0d1d5361b594e81c260dab25f44338
workflow-type: tm+mt
source-wordcount: '1783'
ht-degree: 0%
---
# Einrichten und Konfigurieren der eingehenden Integration

In diesem Artikel werden die [Voraussetzungen](#prerequisites), [Zuständigkeiten](#responsibilities), [Schritte zur &#x200B;](#verification), [Fehlerbehebung &#x200B;](#troubleshoot) und [Abschlusskriterien](#completion-criteria) für das Einrichten und Konfigurieren der eingehenden Markensichtbarkeit-Integration mit Customer Journey Analytics beschrieben.

## Voraussetzungen

Beachten Sie die folgenden Voraussetzungen, bevor Sie die eingehende Integration aktivieren. und das Überprüfungsverfahren zur Überprüfung

### BYOCDN-Protokollweiterleitung

CDN-Zugriffsprotokolle müssen für jede Markensichtbarkeit-Site an Adobe Brand Visibility weitergeleitet und von empfangen werden, bevor der Markensichtbarkeit-Quell-Connector funktionsfähig ist.

Diese Anforderung gilt für jede Markensichtbarkeit-Site. Eine CDN-Konfiguration oder ein Protokoll-Feed für eine Site, Domain oder Subdomain deckt nur diese Site ab, es sei denn, Adobe bestätigt diese Abdeckung für eine andere Site.

Überprüfen Sie mit Adobe beide Teile der Übergabe:

1. Sie haben die entsprechende CDN- oder Protokoll-Pipeline konfiguriert, um die erforderlichen Zugriffsprotokolle an das von Adobe bereitgestellte Amazon S3-Ziel weiterzuleiten.
1. Adobe hat bestätigt, dass Protokolle für die entsprechende Site empfangen und erkannt werden.

Die BYOCDN-Protokollweiterleitung stellt die Server-seitigen CDN-Anfragedaten bereit, die für die automatisierte Analyse von Agenten-Traffic verwendet werden. Die Daten hängen nicht von JavaScript-Tags ab, die in einem Browser ausgeführt werden. Die erforderlichen
CDN-Protokoll-Feed stellt sicher, dass der nachgelagerte Zusammenfassungsdatensatz die vorgesehenen Markensichtbarkeit-agenten-Traffic-Daten enthält. Weitere Informationen finden Sie [BYOCDN](https://experienceleague.adobe.com/de/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)Protokollweiterleitungsreferenz).

### Erforderliche Informationen

Stellen Sie sicher, dass Sie für jede Markensichtbarkeit-Site Werte für alle erforderlichen Details in der folgenden Tabelle aufgeführt haben.

| Erforderlicher Wert | Bestätigung oder Hinweise |
|---|---|
| Markensichtbarkeit-Site oder -Domain | Bestätigen Sie, dass die Website von der CDN-Protokollweiterleitung abgedeckt wird. |
| CDN-Provider | Identifizieren Sie das CDN, das die Site bereitstellt. |
| CDN-Protokollweiterleitungsstatus | Nachweis, dass die Protokolle für die Website weitergeleitet und von der Markensichtbarkeit erkannt werden |
| Markensichtbarkeit-Bereitschaft bestätigen | Bestätigen Sie mit dem Adobe-Konto-Team die Bereitschaft , bevor Sie den Connector aktivieren und planen. |
| IMS-Organisation | Verwenden Sie die exakte IMS-Organisation, die mit Markensichtbarkeit, Experience Platform verknüpft ist. |
| Sandbox | Verwenden Sie den genauen Sandbox-Namen, der für die eingehende Integration angegeben ist. |
| Verbindung | Identifizieren Sie die Kunden-Journey-Verbindung, die den Datensatz enthalten soll. |
| Datenansicht | Identifizieren Sie eine neue oder vorhandene Customer Journey Analytics-Datenansicht, die die -Komponenten enthalten sollte. |
| Administrator oder Besitzer | Geben Sie den Namen oder das Team an, das der Konfigurationskontakt ist. |

Bevor Adobe den verwalteten Connector plant, muss Ihr Adobe-Accountteam bestätigen, dass die Site für die eingehende Integration bereit ist. Versandnachrichten bezeichnen dies als Bestätigung der Markensichtbarkeit-Validierung oder der Website-Bereitschaft. Die Planung des verwalteten Connectors ist eine Managed-Service-Anforderung und keine Self-Service-Aktion für Kunden.

### Sandbox

Der verwaltete Connector muss den Datensatz in der spezifischen benannten AEP-Sandbox erstellen, die vom Kunden in der IMS-Organisation angegeben wurde.

Bestätigen Sie Folgendes:

* IMS-Organisation
* Experience Platform-Sandbox von Target

Die Ziel-AEP-Sandbox ist dieselbe benannte Sandbox, die von der entsprechenden Customer Journey Analytics-Verbindung bzw. den Verbindungen verwendet wird, die den Datensatz enthalten.

Der Kunde kann den Datensatz erst dann zur entsprechenden CJA-Verbindung hinzufügen, wenn Adobe bestätigt hat, dass der verwaltete Datensatz erstellt wurde.

### Zusammenfassungsdatensatz

Die eingehende Integration bietet einen aggregierten Zusammenfassungsdatensatz in Experience Platform, der serverseitige CDN-Anfrageinformationen enthält, die mit LLM, Bot und Automated-Agent verknüpft sind
Traffic

Markensichtbarkeit verwendet CDN-Zugriffsprotokolle, um Anfragen von Bots und automatisierten Agenten zu identifizieren. Dieser Traffic löst keine Browser-JavaScript-Tags aus und wird daher nicht über eine herkömmliche Web-Analytics-Implementierung erfasst.

Eine ausführliche Beschreibung der eingehenden Integration, der Datensatzstruktur und der verfügbaren Felder finden Sie unter [Über den Datensatz](#about-the-dataset).

Der verwaltete Connector erstellt den Zusammenfassungsdatensatz in Experience Platform mithilfe von:

* Die **[!UICONTROL XDM Summary Metrics]**-Klasse
* Die Feldergruppe **[!UICONTROL CDN-]**-Zusammenfassung“
* Felder, die unter einem (**[!UICONTROL )]** Objekt organisiert sind

Der Connector erstellt den Datensatz für jede Markensichtbarkeit-Site unter Verwendung des folgenden Benennungsmusters: <code>Adobe Brand Visibility (ABV)-Datensatz - _baseUrl ohne Schema_</code>. <br/>Zum Beispiel `Adobe Brand Visibility (ABV) Dataset - example.com` für die Site-<https://example.com>.

Datensätze, die vor der Annahme dieser Namenskonvention erstellt wurden, zeigen das frühere Muster <code>LLM-Optimierungsdatensatz (LLMO) - _baseUrl ohne Schema_</code>.
In allen Fällen müssen Kunden den genauen Datensatznamen oder die Datensatz-ID nach der Erstellung mit ihrem Adobe-Account-Team bestätigen.

Der Datensatz besteht aus aggregierten Zusammenfassungsdaten. Verwenden Sie beim Analysieren des Anfragevolumens in Customer Journey Analytics die bereitgestellte Metrik **[!UICONTROL CDN-Anfragenanzahl]** anstatt die Datensatzzeilen zu zählen.

Überprüfen Sie die verfügbaren Felder im Datensatzschema, das für die jeweilige Markensichtbarkeit-Site erstellt wurde. Um die Konfiguration der Datenansicht zu planen, überprüfen Sie die Felder.

## Zuständigkeiten

Adobe verwaltet den eingehenden Connector und, nachdem die Voraussetzungen bestätigt wurden:

* Aktiviert den verwalteten ABV → AEP-Connector.
* Erstellt den Zusammenfassungsdatensatz für jede konfigurierte ABV-Site.
* Lädt den Datensatz in der vom Kunden bereitgestellten AEP-Sandbox.
* Stellt dem Kunden den Datensatznamen oder die Datensatz-ID zur Überprüfung bereit.

Ihre Aufgaben als Kunde sind:

* Um sicherzustellen, dass CDN-Protokolle an jede Markensichtbarkeit-Site weitergeleitet und von Markensichtbarkeit empfangen werden.
* Um die richtige IMS-Organisation und benannte Experience Platform-Sandbox anzugeben.
* So wählen Sie die Customer Journey Analytics-Verbindung aus, die den Datensatz enthalten soll.
* So fügen Sie den Datensatz zu dieser Verbindung hinzu.
* So wählen Sie die Felder aus, die als Komponenten in der entsprechenden Customer Journey Analytics-Datenansicht verfügbar gemacht werden sollen.
* So überprüfen Sie, ob die resultierenden Dimensionen und Metriken die beabsichtigte Analyse unterstützen.

>[!IMPORTANT]
>
>Der verwaltete Connector wird absichtlich angehalten, nachdem der Experience Platform-Datensatz erstellt und ausgefüllt wurde. Adobe ändert Ihre Customer Journey Analytics-Verbindungen oder -Datenansichten nicht.

Der Datensatz steht erst dann für die Customer Journey Analytics-Analyse zur Verfügung, wenn Sie den Datensatz zu einer Verbindung hinzufügen. Die Daten
steht Benutzern erst dann über eine Datenansicht zur Verfügung, wenn die entsprechenden Felder zu dieser Datenansicht hinzugefügt wurden.

## Verifizierung

Gehen Sie wie folgt vor, um die eingehende Integration zu überprüfen:

1. Bestätigen der Bereitschaft von ABV-Site und CDN-Protokoll

   Für jede ABV-Website:

   * Bestätigen Sie die genaue Site oder Domain, die von der Anfrage abgedeckt wird.
   * Bestätigen Sie den CDN-Provider.
   * Vergewissern Sie sich, dass die CDN- oder Protokoll-Pipeline die erforderlichen Zugriffsprotokolle weiterleitet.
   * Vergewissern Sie sich, dass der Markensichtbarkeit Protokolle für diese Website empfängt oder erkennt.
   * Erhalten Sie von Adobe die Markensichtbarkeit-Bereitschaftsbestätigung der Site.

   Fahren Sie nicht mit der allgemeinen Aussage fort, dass „CDN-Protokolle aktiviert sind“, es sei denn, die Bestätigung bezieht sich auf die spezifische ABV-Site.

1. Überprüfen des verwalteten Datensatzes in Experience Platform

   Nachdem Adobe bestätigt hat, dass der verwaltete Connector den Datensatz erstellt hat:
   1. Bei **[!UICONTROL Experience Platform anmelden]**.
   1. Wählen Sie die benannte Sandbox aus der Sandbox-Liste aus, die während der Aufnahme bereitgestellt wird.
   1. Suchen Sie den von Adobe bereitgestellten Datensatznamen oder die Datensatz-ID in **[!UICONTROL Datensätze]**.
   1. Vergewissern Sie sich, dass der Datensatz mit der erwarteten Markensichtbarkeit-Site verknüpft ist.
   1. Zeichnen Sie die **[!UICONTROL Datensatz-ID]** und das verknüpfte **[!UICONTROL Schema]** auf.
   1. Überprüfen Sie die Anzahl der Datensätze, die neuesten Aufnahmeinformationen und verfügbare Beispieldaten, sofern zulässig.
   1. Öffnen Sie das verknüpfte Schema und überprüfen Sie die erwartete XDM-Struktur:
      * Klasse: **[!UICONTROL XDM Summary Metrics]**
      * Feldergruppe: **[!UICONTROL CDN-Anfragen - Zusammenfassung]**
      * Objekt: **[!UICONTROL cdn]**
      * Erwartete Dimensionen und Metriken, z **[!UICONTROL B. &quot;]**&quot;, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL requests]** und **[!UICONTROL timeToFirstByte]**.

1. Hinzufügen des Datensatzes zu einer Verbindung

   Ihr Customer Journey Analytics-Administrator muss den verwalteten Datensatz zur gewünschten Verbindung hinzufügen:

   1. Melden Sie sich bei Customer Journey Analytics an.
   1. [Erstellen Sie eine neue Verbindung oder bearbeiten Sie die vorgesehene vorhandene Verbindung](/help/connections/create-connection.md). Vergewissern Sie sich, dass die Verbindung dieselbe Experience Platform-Sandbox verwendet, in der der verwaltete Datensatz erstellt wurde.
   1. Suchen Sie mithilfe des von Adobe bereitgestellten Datensatznamens oder der Datensatz-ID nach dem Datensatz.
   1. Fügen Sie den Datensatz zur Verbindung hinzu.
   1. Konfigurieren Sie die Datensatzeinstellungen entsprechend dem Customer Journey Analytics-Design des Kunden.
   1. Speichern Sie die Verbindung.
   1. Um sicherzustellen, dass der Datensatz enthalten ist und die Aufnahme fortschreitet, überprüfen Sie die Verbindungsdetails.

1. Datenansicht konfigurieren oder aktualisieren

   Nachdem der Datensatz Teil der Verbindung ist:
   1. Melden Sie sich bei Customer Journey Analytics an.
   1. [Erstellen Sie eine neue Datenansicht oder bearbeiten Sie die Datenansicht](/help/data-views/create-dataview.md) die mit dem vorgesehenen Reporting-Anwendungsfall verknüpft ist.
   1. Wählen Sie die Verbindung aus, die den verwalteten Markensichtbarkeit-Datensatz enthält.
   1. Hinzufügen der erforderlichen Schemafelder als Dimensionen oder Metriken.
   1. Schließen Sie die für die geplante Analyse erforderlichen Felder ein, z. B.:
      * **[!UICONTROL Bot-Typ]**
      * **[!UICONTROL CDN-Anbieter]**
      * **[!UICONTROL URL]**
      * **[!UICONTROL Host]**
      * **[!UICONTROL HTTP-Status]**
      * **[!UICONTROL Anzahl der Anfragen]**
      * **[!UICONTROL Zeit bis zum ersten Byte]**
   1. Speichern Sie die Datenansicht.
   1. Validieren Sie die Felder in Analysis Workspace oder im vom Kunden ausgewählten Reporting-Workflow.

1. Validieren des End-to-End-Ergebnisses

   Verwenden Sie einen aktuellen Berichtszeitraum und überprüfen Sie, ob:

   * Die erwartete Markensichtbarkeit-Site wird angezeigt.
   * Die erwarteten CDN-Provider- und Host-Werte sind vorhanden.
   * Traffic von Bots oder automatisierten Agenten wird dargestellt.
   * URL- und HTTP-Status-Dimensionen enthalten erwartete Werte.
   * Die CDN-Anfragenanzahl und -Leistungsmetriken sind verfügbar.
   * Der Datensatz ist in der beabsichtigten Verbindung enthalten.
   * Die erforderlichen Felder werden in der vorgesehenen Datenansicht verfügbar gemacht.

Der genaue Zeitraum, der erforderlich ist, damit Daten verfügbar werden, hängt vom verwalteten Aufnahme- und Customer Journey Analytics-Verarbeitungs-Workflow ab. Ihr Adobe-Account-Team sollte alle zutreffenden Erwartungen bezüglich der Verarbeitung Ihrer Anfrage angeben.

## Fehlerbehebung

Im Folgenden erfahren Sie, was bei Problemen zu tun ist:

* Der Datensatz wird nicht in AEP angezeigt.

  Überprüfen Sie, ob:

  * Die IMS-Organisation ist korrekt.
  * Die ausgewählte Experience Platform-Sandbox ist korrekt.
  * Adobe hat bestätigt, dass der verwaltete Connector aktiviert wurde.
  * Der von Adobe bereitgestellte Datensatzname oder die ID wurde verwendet.
  * Der Datensatz wurde für die richtige Markensichtbarkeit-Site erstellt.

* Der Datensatz existiert, enthält aber keine erwarteten Daten.

  Überprüfen Sie, ob:
  * CDN-Protokolle werden an die exakte Markensichtbarkeit-Site weitergeleitet.
  * ABV hat bestätigt, dass Protokolle empfangen oder erkannt werden.
  * Die Site oder Domain in der CDN-Konfiguration stimmt mit der Markensichtbarkeit-Site überein.
  * Der verwaltete Connector wurde aktiviert, nachdem die CDN-Protokollbereitschaft bestätigt wurde.
  * Der ausgewählte Datumsbereich umfasst den Zeitraum nach Beginn der Protokollaufnahme.


* Der Datensatz existiert in Experience Platform, ist aber in Customer Journey Analytics nicht verfügbar.

  Überprüfen Sie, ob:
  * Die Customer Journey Analytics-Verbindung verwendet dieselbe benannte Experience Platform-Sandbox.
  * Der Datensatz wurde der Verbindung explizit hinzugefügt.
  * Der Customer Journey Analytics-Administrator verfügt über die erforderlichen Berechtigungen.
  * Die Verbindung wurde gespeichert, nachdem der Datensatz hinzugefügt wurde.

* Der Datensatz befindet sich in der Verbindung, Felder sind jedoch nicht für das Reporting verfügbar.

  Überprüfen Sie, ob:
  * Die Datenansicht wählt die richtige Customer Journey Analytics-Verbindung aus.
  * Die erwarteten Schemafelder wurden als Datenansichtskomponenten hinzugefügt.
  * Die Felder wurden im vorgesehenen Abschnitt **[!UICONTROL Dimensionen]** oder **[!UICONTROL Metriken)]**.
  * Die Datenansicht wurde gespeichert, nachdem die Komponenten hinzugefügt wurden.
  * Das Datensatzschema entspricht der erwarteten Feldergruppenstruktur **[!UICONTROL CDN-]**-Zusammenfassung).


## Abschlusskriterien


Die eingehende Integration ist für die kundenseitige Customer Journey Analytics-Konfiguration bereit, wenn alles Folgende bestätigt wird:

* CDN-Protokolle werden für jede angeforderte ABV-Site an Markensichtbarkeit weitergeleitet und von dieser empfangen.
* Adobe hat die Site-Bereitschaft für den verwalteten Connector bestätigt.
* Die IMS-Organisation wurde bereitgestellt.
* Die Experience Platform-Sandbox für die exakte Zielgruppe wurde bereitgestellt.
* Adobe hat den Datensatz mit der Zusammenfassung pro Site in dieser Sandbox erstellt.
* Sie haben den Datensatz und sein XDM-Schema überprüft.
* Sie haben den Datensatz zur gewünschten CJA-Verbindung hinzugefügt.
* Sie haben die entsprechenden CJA-Datenansichtskomponenten konfiguriert.

