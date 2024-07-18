---
description: Informationen
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 36%

---

# Metriktyp und Attribution

Wenn Sie das Zahnradsymbol neben einer Metrik auswählen, können Sie den Metriktyp und das Attributionsmodell angeben.

## Metriktyp

So legen Sie den Metriktyp beim Erstellen einer berechneten Metrik fest:

1. Wählen Sie das Zahnradsymbol neben der Metrik aus, deren Typ Sie auswählen möchten.

   ![Zahnradsymbol mit Popup-Fenster, das den Metriktyp gleich &quot;Standard&quot;anzeigt.](assets/cm_type_alloc.png)

1. Wählen Sie aus den folgenden Optionen:

   | Metriktyp | Definition |
   |---|---|
   | Standard | Diese Metriken sind dieselben, die auch in der Standard-[!DNL Analytics]-Berichterstellung verwendet werden. Wenn eine Formel aus einer einzelnen Standardmetrik besteht, zeigt sie die gleichen Daten wie das nicht berechnete Metrikgegenstück an. Standardmetriken eignen sich zum Erstellen berechneter Metriken, die speziell für die einzelnen Einzelposten gelten. Beispielsweise teilt [Bestellungen] / [Sitzungen] die Bestellungen für diesen Zeileneintrag und teilt ihn durch die Anzahl der Sitzungen für diesen Zeileneintrag. |
   | Gesamtsumme | Verwenden Sie in jedem Zeileneintrag die Gesamtsumme für den Berichtszeitraum. Wenn eine Formel aus einer einzelnen Gesamtmetrik bestand, wird für jeden Zeileneintrag dieselbe Gesamtsumme angezeigt. Gesamtmetriken sind nützlich für die Erstellung berechneter Metriken, die mit Gesamtdaten vergleichen. Beispielsweise zeigt [Bestellungen] / [Gesamtsitzungen] den Anteil der Bestellungen für ALLE Sitzungen eines Kanals, nicht nur die Sitzungen für den jeweiligen Zeileneintrag. |

## Attribution

Informationen zur Attribution in Customer Journey Analytics finden Sie unter [Einstellungen der Zuordnungskomponente](/help/data-views/component-settings/attribution.md).
