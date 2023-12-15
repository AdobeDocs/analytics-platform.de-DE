---
title: Formatierungs-Komponenteneinstellungen
description: Konfigurieren Sie die Formatierung einer Metrik.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: cf9e8c90eec78658e470d3a7a56cb2e3414591d4
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 19%

---

# Formatierungs-Komponenteneinstellungen

Mit &quot;Format&quot;können Sie festlegen, wie eine bestimmte Metrik bei Verwendung in Berichten angezeigt wird.

## Formateinstellungen für eine Metrik konfigurieren

Sie können bestimmen, wie eine bestimmte Metrik angezeigt wird, indem Sie ihre Formateinstellungen anpassen.

1. Wählen Sie unter Customer Journey Analytics die [!UICONTROL **Datenansichten**] Registerkarte.

1. Wählen Sie die Datenansicht aus, die die Komponente enthält, deren Formateinstellung Sie konfigurieren möchten.

1. Wählen Sie die Registerkarte [!UICONTROL **Komponenten**] aus.

1. Wählen Sie die Komponente aus, die Sie konfigurieren möchten, und erweitern Sie dann die [!UICONTROL **Format**] auf der rechten Seite der Seite.

   ![Formateinstellungen](../assets/format-settings.png)

1. Geben Sie die folgenden Informationen an:

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Format]** | Hier können Sie die Formatierung einer Metrik als Dezimal, Zeit, Prozent oder Währung angeben. |
   | **[!UICONTROL Dezimal]** | Nicht sichtbar bei Schemadatentypen des Typs „Ganzzahl“. Hier können Sie die Anzahl der Dezimalstellen angeben, die eine Metrik anzeigt. |
   | **[!UICONTROL Datum]** | Hiermit können Sie bestimmen, wie das „date-time“-Feld angezeigt werden soll, wenn es als Dimension in Berichten verwendet wird. [Weitere Informationen](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date-Time]** | Hiermit können Sie bestimmen, wie das „date-time“-Feld angezeigt werden soll, wenn es als Dimension in Berichten verwendet wird. [Weitere Informationen](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Währung]** | Ermöglicht Ihnen die Bestimmung der Währung, in der die Metrik angezeigt werden soll. <p>Wenn Sie globale Daten analysieren, in denen Transaktionen in verschiedenen Währungen stattfinden, lesen Sie  [Währungsumrechnung verwenden](#use-currency-conversion).</p> |
   | **[!UICONTROL Aufwärts-Trend anzeigen als]** | Hier können Sie angeben, ob bei dieser Metrik ein Aufwärts-Trend gut (grün) oder schlecht (rot) ist. |
   | **[!UICONTROL Wert „True“]** und **[!UICONTROL Wert „False“]** | Nur bei booleschen Schemadatentypen sichtbar. Ermöglicht die Anpassung der Bezeichnung des Dimensionselements für die Werte `true` und `false`. |

   {style="table-layout:auto"}

## Währungsumrechnung verwenden

Die Währungsumrechnung in Customer Journey Analytics kann für international tätige Unternehmen äußerst wertvoll sein. Indem die Komplexität der manuellen Währungsumrechnung beseitigt wird, bringt die Währungsumrechnung in Customer Journey Analytics Einheitlichkeit und Klarheit in den Finanzdaten. Die Währungsumrechnung verfolgt die historischen Tageskurse und behält diese Tageskurse für einen Zeitraum von vier Jahren bei.

Wenn beispielsweise ein E-Commerce-Unternehmen in den USA, Großbritannien und der EU tätig ist, können Verkaufsdaten automatisch in USD umgewandelt werden, was einen einfachen Vergleich und ein ganzheitliches Verständnis der Leistung gewährleistet.

>[!NOTE]
>
>Beachten Sie Folgendes, bevor Sie mit der Konfiguration einer Metrik für die Währungsumrechnung beginnen:
>
>* Die Metrik, die Sie für die Währungsumrechnung auswählen, muss einen numerischen Typ aufweisen (Double, Long, Integer, Short, Byte).
>* Richten Sie Ihre Customer Journey Analytics-Verbindung so ein, dass sie mindestens einen Ereignis-Datensatz enthält, der eine Währungscode-Dimension für jedes Ereignis enthält, das eine Währungsmetrik enthält. Diese Dimension des Währungscodes verwendet einen alphabetischen Währungscode, der dem [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) Standard für die Darstellung von Währungen. Diese Werte sollten in einem vollständigen Großbuchstabenformat vorliegen, z. B. USD für $, EUR für €, GBP für £.

So bestimmen Sie, wie Währungen für eine bestimmte Metrik angezeigt und konvertiert werden:

1. Beginnen Sie mit der Konfiguration der Metrik, für die Sie die Währung als Format verwenden möchten, wie oben beschrieben in [Formateinstellungen für eine Metrik konfigurieren](#configure-format-settings-for-a-metric).

1. Wenn die Metrik ausgewählt ist, sollten Sie die folgenden Auswahlen im [!UICONTROL **Format**] rechts auf der Seite:

   * Im [!UICONTROL **Format**] Feld auswählen [!UICONTROL **Währung**].

   * Im [!UICONTROL **Dezimalstellen**] auswählen, die Anzahl der Dezimalstellen, die die Metrik anzeigt.

     Diese Option ist nur verfügbar, wenn die Metrik den numerischen Typ &quot;Double&quot;aufweist.

   * Wählen Sie die [!UICONTROL **Währung konvertieren**] -Option.

   * Im [!UICONTROL **Dimension Währungscode auswählen**] auswählen Sie die Dimension, die die Währung darstellt, aus der Sie konvertieren (die Währung, auf der Ihre Daten basieren). Wählen Sie beispielsweise eine Dimension mit dem Namen [!UICONTROL **Währungscode**].

     Wenn Ihr aktuelles Datenschema keine Dimension enthält, die ein Währungscode-Feld enthält, können Sie ein neues Währungscode-Feld mit [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)oder [Abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md). Die Datenvorbereitung eignet sich nur für neue Implementierungen, da sie nur für künftige Implementierungen geeignet ist. Je nach Einrichtung eines Unternehmens können Data Distiller und abgeleitete Felder verwendet werden, um historisch auf die Währungscodewerte zuzugreifen.

   * Im [!UICONTROL **Währung konvertieren und anzeigen in**] auswählen, die Währung, in die die Daten konvertiert werden sollen.

1. Wiederholen Sie diese Schritte, wenn Sie die Währungsumrechnung auf zusätzliche Metriken anwenden möchten.



### Häufig gestellte Fragen

+++ Wie wird die Währungsumrechnung ausgeführt?

Bei Berichtszeit werden der Wert der Metrik und der ursprüngliche Währungscode in USD konvertiert und dann in die für die Anzeige konfigurierte Währung konvertiert. Für diese Konversion werden die Tageswährungskurse verwendet, die für die Zeit des Ereignisses gelten.

+++

