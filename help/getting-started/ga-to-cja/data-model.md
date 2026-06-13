---
title: Zuordnung des GA4-Datenmodells zu Customer Journey Analytics
description: Erfahren Sie, wie das ereignisbasierte Datenmodell von GA4 in XDM-Schemata und Datensätze in Customer Journey Analytics übersetzt wird.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# Zuordnung des GA4-Datenmodells zu Customer Journey Analytics

GA4 und Customer Journey Analytics sind beide ereignisbasierte Plattformen, wodurch die Übersetzung des Datenmodells zwischen beiden direkter erfolgt als mit Universal Analytics. Wenn Sie verstehen, wie die Ereignisse und Parameter von GA4 mit den XDM-Feldern und -Datensätzen von Customer Journey Analytics übereinstimmen, können Sie Berichte leichter interpretieren und mit Ihrem Implementierungsteam zusammenarbeiten.

## Ereignisbasiertes Datenmodell von GA4

Jede Interaktion in GA4 ist ein **Ereignis** eine benannte Aktion mit einem optionalen Satz von **Parametern** die Kontext bereitstellen. Es gibt keine separaten Objekttypen für Seitenansichten, Sitzungen oder Ziele. Es handelt sich jeweils um Ereignisse.

| GA4-Ereignistyp | Beispiele |
|---|---|
| Automatisch erfasst | `page_view`, `session_start`, `first_visit`, `scroll` |
| Erweiterte Messung | `file_download`, `video_start`, `form_submit` |
| Empfohlen | `purchase`, `add_to_cart`, `sign_up` |
| Benutzerspezifisch | Beliebiger Ereignisname, den Sie definieren |

Jedes Ereignis kann bis zu 25 Parameter enthalten. Beispielsweise enthält ein `purchase`-Ereignis normalerweise `transaction_id`, `value`, `currency` und `items` als Parameter.

## Speichern von Daten in Customer Journey Analytics

Customer Journey Analytics erhält seine Daten von **Adobe Experience Platform**. Daten in Platform werden in **Datensätzen** gespeichert, die jeweils einem **Schema** entsprechen, das mit dem **Experience-Datenmodell (XDM) erstellt**. XDM ist der offene Standard von Adobe für die Darstellung von Kundenerlebnisdaten.

In Customer Journey Analytics werden drei Datensatztypen verwendet:

| CJA-Datensatztyp | GA4-Äquivalent | Was sie enthält |
|---|---|---|
| [!UICONTROL Ereignisdatensatz] | GA4-Ereignis-Stream | Zeitreihen-Interaktionen (Seitenansichten, Klicks, Käufe) |
| [!UICONTROL Profildatensatz] | GA4-Benutzereigenschaften | Attribute auf Personenebene (CRM-Felder, Treuestatus, Demografie) |
| [!UICONTROL Lookup-Datensatz] | Benutzerdefinierte GA4-Dimensionen als Referenztabellen | Schlüssel-Wert-Referenzdaten (Produktkatalog, Kampagnennamen) |

Customer Journey Analytics hat keine eVars, Props oder Erfolgsereignisse. Alle Dimensionen und Metriken werden direkt aus XDM-Schemafeldern bezogen. Die Anzahl der eindeutigen Dimensionswerte ist unbegrenzt.

## Automatisch erfasste Ereignisse

GA4 erfasst automatisch eine Reihe von Ereignissen über seine SDK. In der folgenden Tabelle werden diese Ereignisse ihren XDM- oder Customer Journey Analytics-Entsprechungen zugeordnet.

| Automatisch erfasstes GA4-Ereignis | XDM/Customer Journey Analytics-Entsprechung |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` (XDM-Standardfeld) |
| `session_start` | Sitzungsstart (automatisch, pro Definition der Datenansichtssitzung) |
| `first_visit` | [!UICONTROL Erste Sitzung] Segment |
| `scroll` | Benutzerspezifisches Ereignis (erfordert explizites Implementierungs-Mapping) |
| `click` | `xdm.web.webInteraction` Felder (Implementierung erforderlich) |
| `video_start` / `video_complete` | Schemafelder für die Mediensammlung (mit Adobe Streaming Media Services) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order` (Standard-XDM-Commerce-Schema) |
| `add_to_cart` | `xdm.commerce.productListAdds` (Standard-XDM-Commerce-Schema) |

>[!NOTE]
>
>Einige der erweiterten Messereignisse von GA4 (wie Bildlauf, Dateidownload oder Video) erfordern bei der Implementierung der Web-SDK eine explizite Zuordnung zu XDM-Feldern. Sie sammeln sich nicht automatisch auf die gleiche Weise, wie die SDK von GA4 sie verarbeitet.

## Benutzerdefinierte Ereignisse und Parameter

In GA4 haben benutzerdefinierte Ereignisse einen Namen und bis zu 25 Parameter. In Customer Journey Analytics werden benutzerdefinierte Ereignisse benutzerdefinierten XDM-Schemafeldern zugeordnet, die während der Implementierung definiert wurden:

* Der **Ereignisname** wird zu einem Feldwert in einem XDM-Feld (normalerweise [`xdm.eventType`](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/classes/experienceevent)).
* Jeder **Parameter** wird zu einem separaten XDM-Schemafeld. Jedes XDM-Feld kann beim [Konfigurieren einer Datenansicht“ entweder als Dimension oder Metrik &#x200B;](/help/data-views/component-settings/overview.md) werden.

>[!NOTE]
>
>Die spezifischen XDM-Feldpfade für die benutzerdefinierten Ereignisse Ihres Unternehmens werden während der Implementierung von Web SDK festgelegt. Arbeiten Sie mit Ihrem Implementierungs-Team zusammen, um Ihre spezifische Feldzuordnung zu verstehen, bevor Sie Berichte erstellen. Weitere Informationen [&#x200B; Sie unter &#x200B;](../cja-upgrade/cja-upgrade-schema-architect.md) Ihres Schemas erstellen .

## Benutzereigenschaften

GA4-Benutzereigenschaften sind dauerhafte Attribute, die für eine Benutzerin oder einen Benutzer festgelegt werden (z. B. `membership_tier` oder `account_type`). In Customer Journey Analytics werden diese Profildatensätzen **Platform**.

Ein Profildatensatz wird getrennt von Ereignisdaten aufgenommen und in Customer Journey Analytics mit einer freigegebenen Personen-ID verbunden. Häufig verwendete Personen-IDs in diesem Kontext sind Kunden-ID oder E-Mail-Hash. Nach dem Join sind diese Profilattribute als Dimensionen in Analysis Workspace zusammen mit Ihren Daten auf Ereignisebene verfügbar.

Dieser Ansatz bietet Customer Journey Analytics mehr Flexibilität als das Benutzereigenschaftsmodell von GA4: GA4 beschränkt Sie auf Benutzereigenschaften, die in seiner SDK definiert sind, während Customer Journey Analytics-Profildatensätze jedes Attribut aus jedem System enthalten können (CRM, Treueplattform, Support-Datensätze), sofern sie eine verknüpfbare Kennung gemeinsam haben.

Wenn Ihr Unternehmen weiterhin GA-Daten in Adobe Experience Platform importieren muss, finden Sie unter [Aufnehmen historischer Google Analytics-Daten](/help/use-cases/third-party/ga/backfill.md) und [Konfigurieren von Streaming-Google Analytics-](/help/use-cases/third-party/ga/streaming.md)) die Einrichtungshandbücher für Administratoren.
