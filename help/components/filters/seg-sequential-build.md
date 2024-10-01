---
description: Sequenzielle Filter sind Filter, die den THEN -Operator verwenden, um die Sequenz von Filterbedingungen zu definieren.
title: Sequenzielle Filter
feature: Filters
exl-id: 64cb10b5-36f0-42c8-b687-ae5de5ced8b5
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '2491'
ht-degree: 2%

---

# Sequenzielle Filter

Sequenzielle Filter werden mit dem logischen Operator Then anstelle des logischen Operators And oder Or zwischen Komponenten, Containern und Komponenten oder Containern erstellt. Der logische Operator Then impliziert, dass eine Filterbedingung gefolgt von einer anderen auftritt.

+++ Hier ist ein Video, das die sequenzielle Segmentierung demonstriert.

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

{{videoaa}}

+++


Ein sequenzieller Filter verfügt über einige [grundlegende Funktionen](#basics) und zusätzliche Optionen, die Sie konfigurieren können, um dem sequenziellen Filter mehr Komplexität hinzuzufügen:

![Sequenzieller Filter](assets/sequential-filter.gif)

* [Nach und innerhalb von](#after-and-within) -Begrenzungen für die Then -Logik in der Definition des Sequenzfilters:

* Welche Daten sollen [include](#include) als Teil der Gesamtsequenz für die Filterdefinition enthalten? Oder für eine Sequenz, die als Teil eines Containers definiert ist. Standardmäßig werden alle übereinstimmenden Daten berücksichtigt, identifiziert durch ![UserGroup](/help/assets/icons/UserGroup.svg) [!UICONTROL Alle einschließen].

   * Wählen Sie ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Only Before Sequence]** aus, um nur Daten vor der Sequenz zu berücksichtigen.
   * Wählen Sie ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Nur nach Sequenz]** aus, um nur Daten nach der Sequenz zu berücksichtigen.

* Welche Daten [exclude](#exclude) als Teil der Definition des sequenziellen Filters sind.

* So gruppieren Sie [ Bedingungen logisch ](#logic-group) in Ihrer Definition für sequenzielle Filter.

## Grundlagen



Die Grundlagen zum Erstellen eines sequenziellen Filters unterscheiden sich nicht von dem Erstellen eines regulären Filters mit dem [Filter-Builder](filter-builder.md). Verwenden Sie den [Definition-Builder](filter-builder.md#definition-builder), um Ihre Filterdefinition zu erstellen. In dieser Konstruktion verwenden Sie Komponenten, Container, Operatoren und Logik. Ein regulärer Filter wird automatisch zu einem sequenziellen Filter, sobald Sie den Operator **[!UICONTROL Then]** in der Hauptdefinition oder in einem der Container auswählen, die Sie im [Definition-Builder](filter-builder.md#definition-builder) verwenden.

### Beispiele

Die folgenden Beispiele veranschaulichen die Verwendung sequenzieller Filter in verschiedenen Anwendungsfällen.

#### Einfache Sequenz

Identifizieren Sie Personen, die eine Seite und dann eine andere Seite angezeigt haben. Die Daten auf Ereignisebene filtern diese Sequenz unabhängig von vorherigen, vergangenen oder Interimssitzungen oder der Zeit oder Anzahl der Seitenansichten, die zwischen den Sitzungen auftreten.

![Sequenzieller Filter umfasst alle](assets/sequence-include-everyone.png)

#### Sequenzierung sitzungsübergreifend

Identifizieren Sie Personen, die eine Seite in einer Sitzung und dann in einer anderen Sitzung eine andere Seite angezeigt haben. Um zwischen Sitzungen zu unterscheiden, verwenden Sie Behälter, um die Sequenz zu erstellen und ![Besuchsebene](/help/assets/icons/Visit.svg) **[!UICONTROL Sitzung]** für jeden Behälter zu definieren.

![ Sequenzfilter sitzungsübergreifend](assets/sequence-filter-session.png)

#### Sequenz mit gemischten Ebenen

Identifizieren Sie Personen, die zwei Seiten in einer unbestimmten Anzahl von Sitzungen anzeigen und dann eine dritte Seite in einer separaten Sitzung anzeigen. Verwenden Sie erneut Container, um die Sequenz zu erstellen und ![Besuchsebene](/help/assets/icons/Visit.svg) **[!UICONTROL Sitzungsebene]** für den Container zu definieren, der die separate Sitzung definiert.

![Sequenzfilter mit separater finaler Sitzung](assets/sequence-filter-final-session.png)

#### Aggregat-Sequenz

Identifizieren Sie Personen, die bei ihrer ersten Sitzung eine bestimmte Seite besucht und später einige andere Seiten besucht haben. Um zwischen der Ereignissequenz zu unterscheiden, verwenden Sie Container, um die Logik auf einer ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Session]** -Behälterebene zu trennen.

![Sitzungs-Aggregat-Container](assets/session-aggregate-containers.png)


#### Verschachteln einer Sequenz

Identifizieren Sie alle Sitzungen, in denen eine Person eine Seite vor einer anderen Seite besucht, und verfolgen Sie dann Sitzungen mit zwei weiteren Seiten. Identifizieren Sie beispielsweise alle Sitzungen, bei denen eine Person zuerst die Startseite und dann die Seite der Kategorie 1 besucht und dann andere Sitzungen hat, bei denen in jeder Sitzung die Seite der Kategorie 2 und 3 besucht wird.

![Verschachtelte Sequenz](assets/sequence-nested.png)

## Nach und innerhalb

Sie können ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]** und ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** den Operator **[!UICONTROL Then]** verwenden, um zusätzliche [Zeitbeschränkungen](#time-constraints) oder [Beschränkungen für Ereignisse, Sitzungen oder Dimensionen](#event-session-and-dimension-constraints) zu definieren.

### Zeitbeschränkungen

So wenden Sie Zeitbeschränkungen auf den Operator **[!UICONTROL Then]** an:

1. Wählen Sie ![Clock](/help/assets/icons/Clock.svg) aus.
1. Wählen Sie **[!UICONTROL Within]** oder **[!UICONTROL After]** aus dem Kontextmenü.
1. Geben Sie einen Zeitraum (**[!UICONTROL Minute]**, **[!UICONTROL Stunde]** bis **[!UICONTROL Jahre]**) an.
1. Wählen Sie ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL *number *]**aus, um ein Popup zu öffnen, in dem Sie eine Zahl mit**[!UICONTROL -]**oder**[!UICONTROL +]**eingeben oder angeben können.

Verwenden Sie ![CrossSize75](/help/assets/icons/CrossSize75.svg), um eine Zeitbegrenzung zu entfernen.

In der folgenden Tabelle werden die Zeitbegrenzungsoperatoren genauer erläutert.

| Operatoren | Beschreibung |
|--- |--- |
| **[!UICONTROL Nach]** | Der Operator [!UICONTROL Nach] wird verwendet, um eine minimale Zeitbegrenzung zwischen zwei Checkpoints anzugeben. Beim Festlegen der After-Werte beginnt die Zeitbegrenzung mit der Anwendung des Filters. Wenn beispielsweise der Nach -Operator in einem Container festgelegt ist, um Personen zu identifizieren, die Seite A besuchen, aber erst nach einem Tag zum Besuch von Seite B zurückkehren, beginnt dieser Tag mit dem Verlassen von Seite A durch den Besucher.  Damit der Besucher in den Filter aufgenommen wird, müssen nach dem Verlassen von Seite A mindestens 1440 Minuten (ein Tag) vergehen, um Seite B anzuzeigen. |
| **[!UICONTROL Within]** | Der Operator [!UICONTROL Within] wird verwendet, um eine maximale Zeitbegrenzung zwischen zwei Checkpoints anzugeben. Wenn beispielsweise der Operator [!UICONTROL Within] in einem Container festgelegt ist, um Personen zu identifizieren, die Seite A besuchen und dann innerhalb eines Tages zu Seite B zurückkehren, beginnt dieser Tag mit dem Verlassen von Seite A durch die Person. Damit sie in den Filter aufgenommen wird, hat die Person eine maximale Zeit von einem Tag, bevor sie Seite B öffnet. Damit die Person in den Filter aufgenommen wird, muss das Öffnen von Seite B innerhalb von maximal 1440 Minuten (ein Tag) nach dem Verlassen von Seite A erfolgen, um Seite B anzuzeigen. |
| **[!UICONTROL Nach, aber innerhalb]** | Bei Verwendung der Operatoren [!UICONTROL Nach] und [!UICONTROL Innerhalb] beginnen und enden beide Operatoren parallel und nicht sequenziell. <br/>Sie erstellen beispielsweise einen Filter, bei dem der Container auf &quot;`After = 1 Week(s) and Within = 2 Week(s)`&quot; gesetzt ist.<br/>Die Bedingungen zur Identifizierung von Besuchern in diesem Filter sind nur zwischen einer und zwei Wochen erfüllt. Beide Bedingungen werden ab dem Zeitpunkt des ersten Seitenaufrufs erzwungen. |


#### Beispiele

Einige Beispiele für die Verwendung von Zeitbeschränkungen.

##### Nach Operator

Identifizieren Sie Personen, die nur nach zwei Wochen eine Seite und dann eine andere Seite besucht haben. Zum Beispiel Personen, die die Homepage besucht haben, aber die Frauen | Schuhseite nur nach zwei Wochen.

![Sequenz nach](assets/sequence-after.png)

Wenn am 1. Juni 2024 um 00:01 Uhr eine Seitenansicht für die Startseite erfolgt, wird eine Seitenansicht für die Seite &quot;Frauen&quot;angezeigt | Schuhe stimmen überein, solange diese Seitenansicht nach dem 15. Juni 2024 um 00:01 Uhr erfolgt.

##### In-Operator

Identifizieren Sie Personen, die innerhalb von fünf Minuten eine Seite und dann eine andere Seite besucht haben. Zum Beispiel Personen, die die Homepage und dann die Frauen besucht haben | Schuhseite innerhalb von 5 Minuten.

![Sequenz innerhalb](assets/sequence-within.png)

Wenn am 1. Juni 2024 um 12:01 Uhr eine Seitenansicht für die Startseite erfolgt, wird eine Seitenansicht für die Seite &quot;Frauen&quot;angezeigt | Schuhe stimmen überein, solange diese Seitenansicht vor dem 15. Juni 2024 um 12:16 Uhr stattfindet.

##### Nach, aber In-Operator

Identifizieren Sie Personen, die eine Seite und dann nach zwei Wochen, aber innerhalb eines Monats eine andere Seite besucht haben. Zum Beispiel Personen, die die Startseite besucht haben und dann nach zwei Wochen und innerhalb eines Monats die Frauen | Schuhseite.

![Sequenz nach, aber innerhalb](assets/sequence-afterbutwithin.png)

Alle Personen, die am 1. Juni 2024 auf die Startseite tippen und die zum Besuch der Frauen zurückkehren | Schuhseite nach dem 15. Juni 2019 00:01 Uhr, aber vor dem 1. Juli 2019 gilt für das Segment.


### Ereignis-, Sitzungs- und Dimension-Einschränkungen

Mit den Begrenzungen ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]** und ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** können Sie nicht nur eine Zeitbegrenzung, sondern auch eine Ereignis-, Sitzungs- oder Dimensionsbegrenzung festlegen. Wählen Sie **[!UICONTROL Ereignis(e)]**, **[!UICONTROL Sitzung(n)]** oder **[!UICONTROL Sonstige Dimensionen]** ![ChevronRight](/help/assets/icons/ChevronRight.svg) **[!UICONTROL *Dimension-Name *]**aus. Sie können das Feld [!UICONTROL *Suchen*] verwenden, um nach einer Dimension zu suchen.

#### Beispiel

Nachstehend finden Sie ein Beispiel für einen sequenziellen Filter, der nach Personen sucht, die eine Produktkategorieseite besucht haben (Frau) | Schuhe), gefolgt von einer Checkout-Seite (Checkout) | Vielen Dank) innerhalb einer Seite.

![Sequenzfilter innerhalb](assets/sequence-filter-within.png)

Die folgenden Beispielsequenzen stimmen mit oder stimmen nicht überein:

| Sequenz | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|--- | :---: |
| Seite `Women \| Shoes` gefolgt von Seite `Checkout \| Thank You` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| Seite `Women \| Shoes` , gefolgt von Seite `Women \| Tops` , gefolgt von Seite `Checkout \| Thank You` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) |

## Einschließlich

Sie können angeben, welche Daten in Ihren sequenziellen Filter oder in einen sequenziellen Container, der Teil Ihres sequenziellen Filters ist, aufgenommen werden sollen.

### Alle {#include_everyone}

Um einen sequenziellen Filter zu erstellen, der alle einschließt, wählen Sie die Option ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Alle einschließen]** aus.

Der sequenzielle Filter identifiziert Daten, die mit dem angegebenen Muster als Ganzes übereinstimmen.  Nachfolgend finden Sie ein Beispiel für einen einfachen Sequenzfilter, der nach Personen sucht, die eine Produktkategorieseite besucht haben (Frau) | Schuhe), gefolgt von einer Checkout-Seite (Checkout) | Danke). Der Filter ist auf ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Alle einschließen]** eingestellt.

![Sequenzieller Filter umfasst alle](assets/sequence-include-everyone.png)

Die folgenden Beispielsequenzen stimmen mit oder stimmen nicht überein:

| Sequenz | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|--- | --- |
| A, dann B in derselben Sitzung | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| A, dann C, dann D, dann B (sitzungsübergreifend) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| B, dann A | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) |

### „Nur vor Sequenz“ und „Nur nach Sequenz“

Die Optionen ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Nur vor Sequenz]** und ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Nur nach Sequenz]** filtern die Daten vor oder nach der angegebenen Sequenz in eine Teilmenge.

* ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **Nur vor Sequenz**: Umfasst alle Daten vor einer Sequenz und die ersten Daten der Sequenz selbst (siehe Beispiel 1 und 3). Wenn eine Sequenz als Teil der Daten mehrmals vorkommt, enthält [!UICONTROL Nur vor Sequenz] den ersten Treffer des letzten Vorkommens der Sequenz und alle vorherigen Treffer (siehe Beispiel 2).
* ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **Nur nach Sequenz**: Umfasst alle Treffer nach einer Sequenz und die letzten Daten der Sequenz selbst (siehe Beispiel 1 und 3). Wenn eine Sequenz als Teil der Daten mehrmals vorkommt, schließt &quot;Nur nach&quot;den letzten Treffer des ersten Vorkommens der Sequenz sowie alle nachfolgenden Treffer ein (siehe Beispiel 2).

Erwägen Sie eine Definition, die eine Sequenz einer Komponente mit Kriterien angibt, die von B identifiziert werden, gefolgt von einer Komponente mit Kriterien, die von D identifiziert werden. Mit den drei Optionen werden die Daten wie folgt identifiziert:


| B Dann D | A | B | C | D | E | F |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Alle einschließen | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| Nur vor Sequenz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |  |
| Nur nach Sequenz |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |



| B Then D (tritt mehrmals auf) | A | B | C | D | B | C | D | E |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Alle einschließen | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| Nur vor Sequenz | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |
| Nur nach Sequenz |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |

#### Beispiel

Sie haben drei Versionen eines sequenziellen Filters für Sitebereiche definiert. Eine mit der Option ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Alle einschließen]**, eine mit der Option ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Nur vor Sequenz]** und eine mit der Option ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Nur nach Sequenz]**. Sie haben die drei Filter entsprechend benannt.

![Sequenzfilter](assets/site-section-filters.png)

Wenn Sie Berichte zu Sitebereichen erstellen, die diese drei Filter verwenden, ist dies die Beispielausgabe in einer Freiformtabelle.

![Sequenzieller Filterbericht](assets/sequential-filter-freeform-table.png)

## Außer

Filterdefinitionen beinhalten alle Daten, es sei denn, Sie schließen ![Benutzer](/help/assets/icons/User.svg) [!UICONTROL Person], ![Besuch](/help/assets/icons/Visit.svg) [!UICONTROL Sitzung] oder ![WebPage](/help/assets/icons/WebPage.svg) [!UICONTROL Ereignis] mit **[!UICONTROL Ausschließen]** ausdrücklich aus.

Mit [!UICONTROL Ausschließen] können Sie allgemeine Daten schließen und Filter mit mehr Fokus erstellen. Ausschließen ermöglicht auch die Erstellung von Filtern mit Ausnahme bestimmter Personengruppen. Beispielsweise um einen Filter zu definieren, der Personen angibt, die Bestellungen aufgegeben haben, und dann diese Personengruppe ausschließt, um *Nicht-Käufer* zu identifizieren. Es empfiehlt sich, Regeln zu erstellen, die eine breite Definition verwenden, anstatt [!UICONTROL Ausschließen] für bestimmte Personen zu verwenden, die bestimmten Einschlusswerten entsprechen.

Beispiele für Ausschlussdefinitionen:

* **Schließen Sie Seiten aus**. Verwenden Sie eine Filterdefinition, um eine bestimmte Seite (z. B. *Homepage*) aus einem Bericht auszuschließen, erstellen Sie eine Ereignisregel, bei der die Seite gleich `Home Page` ist, und schließen Sie dann die Regel aus. Diese Definition umfasst automatisch alle Seiten mit Ausnahme der *Homepage*.
* **Schließen Sie die Referrerdomäne aus**. Verwenden Sie eine Definition, die nur verweisende Domänen von Google.com umfasst und alle anderen ausschließt.
* **Identifizieren Sie Nicht-Käufer**. Ermitteln Sie, wann Bestellungen größer als null sind, und schließen Sie dann die [!UICONTROL Person] aus.

[!UICONTROL Ausschließen] kann verwendet werden, um eine Sequenz zu identifizieren, in der bestimmte Sitzungen oder Ereignisse nicht von der Person ausgeführt werden. [!UICONTROL Ausschließen] kann auch in eine logische Gruppe aufgenommen werden (siehe unten).

Sie können Container ausschließen, nicht Komponenten.

### Beispiele

Nachfolgend finden Sie Beispiele für die Verwendung von [!UICONTROL Exclude].

#### Ausschluss innerhalb

Identifizieren Sie Personen, die eine Seite besucht, keine andere Seite besucht und dann eine andere Seite besucht haben. Sie schließen den Container mit ![Einstellung](/help/assets/icons/Setting.svg) Ausschließen aus. Ein ausgeschlossener Container wird durch einen roten, dünnen Balken auf der linken Seite identifiziert.

![Sequenz ausschließen](assets/sequence-exclude.png)


#### Ausschluss beim Start

Identifizieren Sie Personen, die eine Seite besucht haben, ohne jemals zu einer anderen Seite zu wechseln. Zum Beispiel Personen, die einen Kauf ausgecheckt haben, ohne jemals die Homepage besucht zu haben.

![Sequenzausschlussstart](assets/sequence-exclude-start.png)


#### Am Ende ausschließen

Identifizieren Sie Personen, die eine Seite besucht, aber keine anderen Seiten besucht haben. Zum Beispiel Personen, die Ihre Homepage besucht haben, aber nie eine Ihrer Checkout-Seiten.

![Sequenzausschluss-Ende](assets/sequence-exclude-end.png)


## logische Gruppe

>[!NOTE]
>
>Eine [!UICONTROL logische Gruppe] kann nur in einem sequenziellen Filter definiert werden, was bedeutet, dass der Operator [!UICONTROL Then] im Container verwendet wird.

Mit der logischen Gruppe können Sie Bedingungen zu einem einzigen sequenziellen Filter-Checkpoint gruppieren. Als Teil der Sequenz wird die im als logische Gruppe identifizierten Container definierte Logik nach jedem vorherigen sequenziellen Checkpoint und vor jedem nachfolgenden sequenziellen Checkpoint ausgewertet.

Die Bedingungen innerhalb der logischen Gruppe selbst können in beliebiger Reihenfolge erfüllt werden. Dagegen erfordern nicht sequenzielle Container (Ereignis, Sitzung, Person) nicht, dass ihre Bedingungen innerhalb der Gesamtsequenz erfüllt sind, was bei Verwendung mit einem Then -Operator zu möglichen intuitiven Ergebnissen führt.

[!UICONTROL Logische Gruppe] wurde entwickelt, um *mehrere Bedingungen als Gruppe zu behandeln, ohne dass eine Reihenfolge* zwischen den gruppierten Bedingungen besteht. Andernfalls ist die Reihenfolge der Bedingungen innerhalb einer logischen Gruppe irrelevant.

Einige Best Practices für die Verwendung der logischen Gruppe sind:

* So gruppieren Sie sequenzielle Checkpoints.
* Vereinfachung der Erstellung sequenzieller Filter.

### Beispiele

Im Folgenden finden Sie Beispiele zur Verwendung des logischen Gruppenbehälters.

#### Beliebige Bestellung

Identifizieren Sie Personen, die eine Seite besucht und dann jede Seite aus einem anderen Satz von Seiten in beliebiger Reihenfolge angezeigt haben. Zum Beispiel Personen, die die Startseite besucht und dann die einzelnen Seiten &quot;Männer&quot;, &quot;Frauen&quot;und &quot;Kinder&quot;besucht haben, unabhängig von der Reihenfolge.

Sie können diesen Filter ohne eine [!UICONTROL logische Gruppe] erstellen, aber die Konstruktion wird komplex und aufwändig sein. Sie müssen jede Seitensequenz angeben, die der Besucher anzeigen kann. Aus Gründen der Klarheit wird nur der erste Container ![ChevronDown](/help/assets/icons/ChevronDown.svg) geöffnet und die anderen Container werden ![ChevronRight](/help/assets/icons/ChevronRight.svg) geschlossen. Sie können den Inhalt der anderen Container durch die Titel ableiten.

![Beispiel, das keine logische Gruppe verwendet](assets/logicgroup-example-notusing.png)

Sie können [!UICONTROL Logische Gruppe] verwenden, um die Erstellung dieses Filters zu vereinfachen, wie unten dargestellt. Stellen Sie sicher, dass Sie ![Gruppe](/help/assets/icons/Group.svg) **[!UICONTROL Logische Gruppe]** für den Container auswählen.

![Beispiel, das keine logische Gruppe verwendet](assets/logicgroup-example-using.png)

#### Erste Übereinstimmung

Identifizieren Sie Personen, die eine Seite oder eine andere Seite besucht und dann eine andere Seite besucht haben. Zum Beispiel Personen, die die Seite &quot;Frauen&quot;oder &quot;Männer&quot;besucht und dann die Checkout-Seite besucht haben | Dankeseite.

![Beispiel für die Verwendung der ersten Übereinstimmung mit der logischen Gruppe](assets/logicgroup-example-firstmatch.png)

#### Ausschließen und

Identifizieren Sie Personen, die eine Seite besucht haben, die dann explizit eine Reihe anderer Seiten nicht besucht haben, sondern eine andere Seite besucht haben. Beispielsweise haben Personen, die die Homepage besucht haben, nicht die Seite &quot;Männer&quot;oder &quot;Frauen&quot;besucht, sondern die Seite &quot;Kinder&quot;besucht.

![Logische Gruppe - Ausschluss und ](assets/logicgroup-exclude-and.png)

#### Ausschließen oder

Identifizieren Sie Personen, die eine Seite besucht haben, die dann explizit keine Seite einer Reihe von Seiten besucht haben, aber eine andere Seite besucht haben. Beispielsweise besuchten Personen, die die Homepage besucht haben, nicht die Seite &quot;Männer und Frauen&quot;, sondern die Seite &quot;Kinder&quot;.

![Logische Gruppe - Ausschluss und ](assets/logicgroup-exclude-or.png)


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->


## Ein letztes Beispiel

Als letztes Beispiel möchten Sie Personen identifizieren, die über eine bestimmte Produktseite gelernt haben, ohne dass diese Personen jemals von Ihrer Empower Your Move -Kampagne berührt werden. Und in ihrem ersten Besuch in Ihrem Online-Shop sah die Homepage, aber nicht weiter auf Fitness-Produkte (Zahnrad) aus der Kategorie Männer. In ihrer nächsten Sitzung jedoch direkt danach gingen sie auf eine Produktseite und stellten eine Online-Bestellung auf, ohne zuerst die Startseite zu besuchen.


![Beispiel für komplexen sequenziellen Filter](assets/sequential-complex.png)
