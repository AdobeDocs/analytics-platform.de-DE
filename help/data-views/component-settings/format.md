---
title: Formatierungs-Komponenteneinstellungen
description: Konfigurieren Sie die Formatierung einer Metrik.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 23%

---

# Formatierungs-Komponenteneinstellungen {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="Format"
>abstract="Legen Sie fest, wie eine Komponente in Berichten angezeigt wird."

<!-- markdownlint-enable MD034 -->


Mit „Format“ können Sie bestimmen, wie eine bestimmte Metrik angezeigt wird, wenn sie in Berichten verwendet wird.

## Konfigurieren von Formateinstellungen für eine Metrik

Sie können bestimmen, wie eine bestimmte Metrik angezeigt wird, indem Sie ihre Formateinstellungen anpassen.

1. Wählen Sie in Customer Journey Analytics die Registerkarte [!UICONTROL **Datenansichten**] aus.

1. Wählen Sie die Datenansicht aus, die die Komponente enthält, deren Formateinstellung Sie konfigurieren möchten.

1. Wählen Sie die Registerkarte [!UICONTROL **Komponenten**] aus.

1. Wählen Sie die zu konfigurierende Komponente aus und erweitern Sie dann den [!UICONTROL **Format**] auf der rechten Seite der Seite.

   ![Formateinstellungen](../assets/format-settings.png)

1. Geben Sie die folgenden Informationen an:

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Format]** | Hier können Sie die Formatierung einer Metrik als Dezimal, Zeit, Prozent oder Währung angeben. |
   | **[!UICONTROL Dezimal]** | Nicht sichtbar bei Schemadatentypen des Typs „Ganzzahl“. Hier können Sie die Anzahl der Dezimalstellen angeben, die eine Metrik anzeigt. |
   | **[!UICONTROL Datum]** | Hiermit können Sie bestimmen, wie das „date-time“-Feld angezeigt werden soll, wenn es als Dimension in Berichten verwendet wird. [Weitere Informationen](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date-Time]** | Hiermit können Sie bestimmen, wie das „date-time“-Feld angezeigt werden soll, wenn es als Dimension in Berichten verwendet wird. [Weitere Informationen](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Währung]** | Hiermit können Sie festlegen, in welcher Währung die Metrik angezeigt werden soll. <p>Wenn Sie globale Daten analysieren, bei denen Transaktionen in verschiedenen Währungen auftreten, lesen Sie [Verwenden von Währungsumrechnungen](#use-currency-conversion).</p> |
   | **[!UICONTROL Aufwärts-Trend anzeigen als]** | Hier können Sie angeben, ob bei dieser Metrik ein Aufwärts-Trend gut (grün) oder schlecht (rot) ist. |
   | **[!UICONTROL Wert „True“]** und **[!UICONTROL Wert „False“]** | Nur bei booleschen Schemadatentypen sichtbar. Ermöglicht die Anpassung der Bezeichnung des Dimensionselements für die Werte `true` und `false`. |

   {style="table-layout:auto"}

## Verwenden der Währungsumrechnung {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="Währungsumrechnung"
>abstract="Wählen Sie eine Währungs-Code-Dimension aus, um die Währung in einem ausgewählten Währungstyp zu konfigurieren und anzuzeigen."

<!-- markdownlint-enable MD034 -->

Die Währungsumrechnung in Customer Journey Analytics kann für international tätige Unternehmen äußerst wertvoll sein. Durch die Beseitigung der Komplexität der manuellen Währungsumrechnung bringt die Währungsumrechnung in Customer Journey Analytics Einheitlichkeit und Klarheit in die Finanzdaten. Die Währungsumrechnung erfasst die täglichen historischen Wechselkurse und behält diese täglichen Kurse für einen Zeitraum von 4 Jahren bei.

Wenn beispielsweise ein E-Commerce-Unternehmen in den USA, Großbritannien und der EU tätig ist, können die Verkaufsdaten automatisch in USD umgewandelt werden, was einen einfachen Vergleich und ein ganzheitliches Verständnis der Leistung ermöglicht.

>[!NOTE]
>
>Bevor Sie mit der Konfiguration einer Metrik für die Währungsumrechnung beginnen, beachten Sie Folgendes:
>
>* Die Metrik, die Sie für die Währungsumrechnung auswählen, muss einen numerischen Typ aufweisen (Double, Long, Integer, Short, Byte).
>* Richten Sie Ihre Customer Journey Analytics-Verbindung so ein, dass sie mindestens einen Ereignisdatensatz enthält, der für jedes Ereignis, das eine Währungsmetrik enthält, eine Währungscodedimension enthält. Diese Währungs-Code-Dimension verwendet einen alphabetischen Währungs-Code, der der Norm [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) für die Darstellung von Währungen entspricht. Diese Werte sollten in vollem Großbuchstaben angegeben werden, wie z. B. USD für $, EUR für €, GBP für £.

So bestimmen Sie, wie Währungen für eine bestimmte Metrik angezeigt und konvertiert werden:

1. Beginnen Sie mit der Konfiguration der Metrik, für die Sie die Währung als Format verwenden möchten, wie oben unter &quot;[ für eine Metrik konfigurieren“ ](#configure-format-settings-for-a-metric).

1. Treffen Sie bei ausgewählter Metrik die folgenden Auswahlen im [!UICONTROL **Format**] auf der rechten Seite der Seite:

   * Wählen Sie im Feld [!UICONTROL **Format**] die Option [!UICONTROL **Währung**] aus.

   * Wählen Sie im Feld [!UICONTROL **Dezimalstellen**] die Anzahl der Dezimalstellen aus, die die Metrik anzeigt.

     Diese Option ist nur verfügbar, wenn die Metrik einen numerischen Typ von „Double“ hat.

   * Wählen Sie die Option [!UICONTROL **Währung umrechnen**] aus.

   * Wählen Sie im Feld [!UICONTROL **Währungs-Code-Dimension auswählen**] die Dimension aus, die für die Währung steht, aus der Sie die Umrechnung durchführen (die Währung, auf der Ihre Daten basieren). Wählen Sie beispielsweise eine Dimension mit dem Namen [!UICONTROL **Währungs-Code**].

     Wenn Sie in Ihrem aktuellen Datenschema keine Dimension haben, die ein Feld für den Währungs-Code enthält, können Sie ein neues Feld für den Währungs-Code mit [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de), [Daten-Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) oder [Abgeleiteten Feldern](/help/data-views/derived-fields/derived-fields.md) erstellen. Die Datenvorbereitung ist nur für neue Implementierungen geeignet, da sie nur auf einer Zukunftsbasis erfolgt. Je nach Einrichtung einer Organisation können Daten-Distiller und abgeleitete Felder verwendet werden, um historisch auf die Währungs-Code-Werte zuzugreifen.

   * Wählen [!UICONTROL **Feld „Währung umrechnen und anzeigen in**] die Währung, in der Daten umgerechnet werden sollen.

1. Wiederholen Sie diese Schritte, wenn Sie eine Währungsumrechnung auf weitere Metriken anwenden möchten.



### Häufig gestellte Fragen

+++ Wie wird die Währungsumrechnung durchgeführt?

Zur Berichtszeit werden der Wert der Metrik und der ursprüngliche Währungs-Code in USD umgerechnet und dann in die für die Anzeige konfigurierte Währung umgerechnet. Für diese Umrechnung werden die täglichen Wechselkurse verwendet, die für die Zeit des Ereignisses gelten.

+++

