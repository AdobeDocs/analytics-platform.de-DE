---
title: Abgeleitete Felder
description: Ein abgeleitetes Feld gibt die Bearbeitung der Berichtszeit von Schemafeldern und/oder Standardkomponenten über einen Satz verfügbarer Funktionen und Funktionsvorlagen an.
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 27%

---


# Abgeleitete Felder (eingeschränkte Tests){#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>Dies ist eine vorläufige Dokumentation neuer abgeleiteter Feldfunktionen, die noch nicht allgemein verfügbar sind. Verwenden Sie diese Informationen, um mehr über die neuen Funktionen abgeleiteter Felder zu erfahren. Diese Dokumentation kann noch geändert werden, und aus der aktuellen Version dieses Artikels können keine rechtlichen Verpflichtungen abgeleitet werden.
>&#x200B;><br/>Unter [Abgeleitete Felder](derived-fields.md) finden Sie Informationen zur Funktionalität abgeleiteter Felder im Allgemeinen sowie zu den aktuell verfügbaren veröffentlichten Funktionen und Funktionsvorlagen.
>

## Funktionsreferenz

{{select-package}}

Details zu jeder unterstützten Funktion finden Sie unten unter:

- Spezifikationen:
   - Eingabedatentyp: Art der unterstützten Daten,
   - Eingabe: mögliche Werte für die Eingabe,
   - Enthaltene Operatoren: Für diese Funktion unterstützte Operatoren (falls vorhanden),
   - Einschränkungen: Einschränkungen, die für diese spezifische Funktion gelten,
   - Ausgabe

- Anwendungsfälle, einschließlich:
   - (Optional) Daten vor der Definition des abgeleiteten Felds,
   - wie das abgeleitete Feld definiert wird,
   - (Optional) Daten nach der Definition des abgeleiteten Felds.

- Einschränkungen (falls zutreffend).



<!-- DATE MATH -->

### Datumsberechnung {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="Datumsberechnung"
>abstract="Diese Funktion bietet die Möglichkeit, die Differenz zwischen zwei Datums- oder Datums-/Uhrzeitfeldern zurückzugeben."

Gibt die Differenz zwischen zwei Datumsangaben oder zwei Datums-/Uhrzeitfeldern zurück.

+++ Details

## Spezifikationen {#datemath-io}

| Eingabedatentyp | Eingabe | Enthaltene Operatoren | Einschränkungen | Ausgabe |
|---|---|---|---|---|
| <ul><li>Datum</li><li>Datum-Uhrzeit</li></ul> | <ul><li>[!UICONTROL Anwendungsbereich]<ul><li>Ereignis</li><li>Sitzung</li><li>Person</li></ul></li><li>[!UICONTROL Wert]:<ul><li>Datum</li><li>Datum/Uhrzeit</li><li>Statisches Datum (vom Benutzer eingegeben)</li><li>Statische Datums-/Uhrzeitangabe (Benutzereingabe)</li><li>Dynamisches Datum<ul><li>Am aktuellen Tag</li></ul></li><li>Dynamisches Datum/Uhrzeit<ul><li>Jetzt</li></ul></li></ul></li><li>[!UICONTROL Granularität]:<ul><li>Seconds</li><li>Minutes</li><li>Stunden</li><li>Days</li><li>Weeks</li><li>Months</li><li>Quartale</li><li>Jahre</li></ul></li><li>Für jede Datums- oder Datums-/Uhrzeitangabe:<ul><li>Erste(r) (innerhalb der Sitzung oder Person)</li><li>Letzte(r) (innerhalb der Sitzung oder Person)</li></ul></li></ul> | <p>k. A.</p> | <p>2 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#datemath-uc1}

Als Marketing-Analyst eines Hotelunternehmens möchten Sie den Unterschied der Anzahl der Tage zwischen dem Check-in-Datum des Kunden und dem Buchungstermin über die letzte Woche verstehen.


### Abgeleitetes Feld {#datemath-uc1-derivedfield}

Sie definieren ein abgeleitetes `Days between booking and check-in`-Feld. Mit der Funktion [!UICONTROL DATE MATH] können Sie eine Regel definieren, mit der die Tage für [!UICONTROL Scope] [!DNL Person] zwischen dem [!UICONTROL Buchungsdatum] und [!UICONTROL Check-in-Datum] berechnet werden. Wählen Sie [!UICONTROL Tag] als [!UICONTROL Ausgabegranularität] aus. Und Sie wählen [!UICONTROL Letztes &#x200B;] sowohl für [!UICONTROL Buchungsdatum] als auch für [!UICONTROL Check-in-Datum], um sicherzustellen, dass der Wert der letzten Person in der Berechnung verwendet wird.

![Screenshot der Regel für Datumsmathematik](assets/datemath-1.png)


## Anwendungsfall 2 {#datemath-uc2}

Als Marketing-Analyst eines stationären Geschäfts möchten Sie verstehen, wie viele Tage zuvor der letzte Besuch eines Kunden im Geschäft war. Sie verwenden Geolocation-Funktionen innerhalb einer mobilen App und Beacons im Shop, um physische Besuche von Kunden zu erfassen.

### Abgeleitetes Feld {#datemath-uc2-derivedfield}

Sie definieren ein neues abgeleitetes `Days Since Visit To Shop`-Feld. Mit [!UICONTROL DATE MATH]-Funktion definieren Sie eine Regel zur Berechnung der Tage zwischen einer benutzerdefinierten Datums-/Uhrzeitangabe (die Sie in [!UICONTROL Date] angeben) und der [!UICONTROL Lokalzeit] (aus Ihrer [!UICONTROL placeContext]-Feldergruppe Ihres Ereignisdatensatzes) mit einem [!UICONTROL Deduplizierungsumfang] von [!UICONTROL Person]. Sie wählen [!UICONTROL Letzte zurückgeben], um sicherzustellen, dass der letzte von einer Person erfasste Wert für [!UICONTROL Ortszeit] in der Berechnung verwendet wird. Wählen Sie Tag als [!UICONTROL Ausgabegranularität] aus.

![Screenshot der Regel 2 für mathematische Datumsangaben](assets/datemath-2.png)


## Anwendungsfall 3 {#datemath-uc3}

Sie möchten die Suchzeit in Minuten verstehen, bevor ein Kunde innerhalb einer Sitzung eine Bestellung aufgibt.

Sie definieren ein neues `Time Between Search And Order In Minutes` abgeleitetes Feld, das das Ergebnis zweier [[!UICONTROL CASE WHEN]-Funktionen ist](#case-when) um [!UICONTROL Suchzeit] und [!UICONTROL Bestellzeit] Werte zu definieren.
Anschließend verwenden Sie diese beiden Werte, um die Differenz mit einer [!UICONTROL DATE MATH]-Funktion zu berechnen, wobei [!UICONTROL Scope] auf [!UICONTROL Session], Werte auf [!UICONTROL Search Time] und [!UICONTROL Order Time] und [!UICONTROL Output-Granularität] auf [!UICONTROL Minute] gesetzt sind. Für beide Werte wählen Sie [!UICONTROL Erste zurückgeben] um sicherzustellen, dass die erste [!UICONTROL Suchzeit] und [!UICONTROL Bestellzeit] zurückgegeben wird.

![Screenshot der Datumsmathematikregel 3](assets/datemath-3.png)



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### Tiefe {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="Tiefe"
>abstract="Diese Funktion bietet die Möglichkeit, die Tiefe eines beliebigen Felds zurückzugeben, ähnlich der Funktionalität der Standardkomponente für Ereignistiefe."

Gibt die Tiefe eines Felds zurück, ähnlich wie dies mit der standardmäßigen ([-Dimension) möglich ](/help/components/dimensions/overview.md#standard-dimensions).

+++ Details

## Spezifikationen {#depth-io}

| Eingabedatentyp | Eingabe | Enthaltene Operatoren | Einschränkungen | Ausgabe |
|---|---|---|---|---|
| Eines | Beliebiges Feld | k. A. | 3 Funktionen pro abgeleitetem Feld | Neues abgeleitetes Feld |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## Anwendungsfall {#depth-uc1}

Sie möchten die Suchtiefe verstehen (die Sie auch als Anzahl der Suchvorgänge interpretieren können). So können Sie diese Suchtiefe später verwenden, um den Suchbegriff zu suchen, der mit einer bestimmten Suchtiefe verknüpft ist.


### Abgeleitetes Feld {#depth-uc1-derivedfield}

Sie definieren ein neues abgeleitetes `Search Depth`-Feld. Mit der [!UICONTROL DEPTH]-Funktion definieren Sie eine Regel, um die Tiefe von [!UICONTROL Search] abzurufen und in einem neuen, abgeleiteten Feld zu speichern.

![Screenshot der Tiefenregel](assets/depth-1.png)

+++


<!-- TYPECASE -->

### Typecast {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="Typecast"
>abstract="Diese Funktion bietet die Möglichkeit, den Feldtyp spontan zu ändern, um das Feld für zusätzliche Transformationen in Customer Journey Analytics verfügbar zu machen."

Ändern des Feldtyps eines Felds, um es für zusätzliche Transformationen in Customer Journey Analytics verfügbar zu machen.

+++ Details

## Spezifikationen {#typecast-io}

| Eingabedatentyp | Eingabe | Enthaltene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Numerisch</li><li>Datum</li><li>Datum-Uhrzeit</li><li>Zeichenfolge</li></ul> | <ul><li>[!UICONTROL Feld] | <p><ul><li>Ganzzahl<ul><li>An Zeichenfolge <strong>(muss)</strong></li></ul></li><li>Double<ul><li>An Zeichenfolge <strong>(muss)</strong><ul><li>Anzahl der zu erbenden Dezimalstellen einschließen (max. 5?)</li></ul></li><li>Zu Ganzzahl <strong>(sollte)</strong></li></ul></li><li>Byte<ul><li>An Zeichenfolge <strong>(muss)</strong></li></ul></li><li>Lang<ul><li>An Zeichenfolge <strong>(muss)</strong></li></ul></li><li>Datum<ul><li>An Zeichenfolge <strong>(muss)</strong><ul><li>Möglichkeit zur Definition des Ausgabeformats</li></ul></li><li>Beispiele<ul><li>Datum (Beispiel: 7. Januar 2025)<ul><li data-stringify-indent="1" data-stringify-border="0">MM-TT-JJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM-TT-JJJJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">TT-MM-JJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">TT-MM-JJJJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">JJ-MM-TT<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">JJJJ-MM-TT<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 07.01.2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/TT/JJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 01/07/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/TT/JJJJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 01/07/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">JJJJ/MM/TT<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">JJ/MM/TT<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. 25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MMM TT, JJJJ<ul><li data-stringify-indent="2" data-stringify-border="0">z. B. Mittwoch, 7. Januar 2025</li></ul></li></ul></li></ul></li></ul></li><li>Datum-Uhrzeit<ul><li>An Zeichenfolge <strong>(muss)</strong><ul><li>Möglichkeit zur Definition des Ausgabeformats</li></ul></li><li>Beispiele<ul><li data-stringify-indent="0" data-stringify-border="0">Datum-Uhrzeit (Beispiel: 7. Januar 2025 um 1::30pm, 52 Sekunden)<ul><li data-stringify-indent="2" data-stringify-border="0">MM-TT-JJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM-TT-JJJJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">TT-MM-JJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">TT-MM-JJJJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">JJ-MM-TT hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">JJJJ-MM-TT hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 07.01.2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/TT/JJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/TT/JJJJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 01/07/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">JJJJ/MM/TT hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 2025/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">JJ/MM/TT hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MMM TT, JJJJ hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">z. B. 7. Januar 2025 13:30:52</li></ul></li></ul></li></ul></li><li>Zeichenfolge<ul><li>Zu numerischem <strong> (sollte)</strong><ul><li>Wenn wir Werte haben, die nicht numerischer Natur sind, geben sie null zurück.</li><li>Der Benutzer muss die Präzision und das zu verwendende Gebietsschema eingeben. </li></ul></li></ul></li></ul></li></ul></p> | <p>3 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#typecast-uc1}

Sie verfügen über ein ganzzahliges Feld, die Bildschirmhöhe (z. B. device.screenHeight aus Ihrem Ereignis-Datensatz), das Sie als zeichenfolgenbasierte Dimension verwenden möchten.


### Abgeleitetes Feld {#typecast-uc1-derivedfield}

Sie definieren ein abgeleitetes  `Screen Height`-Feld. Mit der Funktion [!UICONTROL TYPECAST] definieren Sie eine Regel für [!UICONTROL &#x200B; Feld Typecast to] [!UICONTROL String] [!UICONTROL Screen height] und speichern diese im neuen abgeleiteten Feld.

![Screenshot der Typecast-Regel 1](assets/typecast-1.png)



## Anwendungsfall 2 {#typecast-uc2}

Sie möchten den Umsatz in einer Kohortentabelle verwenden (die nur Ganzzahlen unterstützt), aber das Feld Umsatz hat den Typ Double.

![Screenshot der Typecast-Regel 2](assets/typecast-2.png)


### Abgeleitetes Feld {#typecast-uc2-derivedfield}

Sie definieren ein abgeleitetes  `Revenue (integer)`-Feld. Mit der Funktion [!UICONTROL TYPECAST] definieren Sie eine Regel für [!UICONTROL &#x200B; Feld Typecast to] [!UICONTROL Integer] [!UICONTROL Revenue] und speichern diese im neuen abgeleiteten Feld.


+++
