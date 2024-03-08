---
title: Bindungsdimensionen und Metriken in Customer Journey Analytics verwenden
description: Ordnen Sie den Objekt-Arrays Dimensionen für die komplexe Persistenzanalyse zu.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 83%

---


# Bindungsdimensionen und Metriken in Customer Journey Analytics verwenden

Customer Journey Analytics bietet mehrere Möglichkeiten, Dimensionswerte über den Treffer hinaus beizubehalten, für den sie festgelegt wurden. Eine der Persistenzmethoden, die Adobe anbietet, wird als Bindung bezeichnet. In früheren Versionen von Adobe Analytics wurde dieses Konzept als Merchandising bezeichnet.

Sie können Bindungsdimensionen zwar mit Ereignisdaten der obersten Ebene verwenden, dieses Konzept empfiehlt sich jedoch am meisten bei der Arbeit mit [Arrays von Objekten](/help/use-cases/object-arrays.md). Sie können eine Dimension einem Teil eines Objekt-Arrays zuordnen, ohne sie auf alle Attribute in einem bestimmten Ereignis anzuwenden. Sie können beispielsweise einen Suchbegriff einem Produkt in Ihrem Warenkorb-Objekt-Array zuordnen, ohne diesen Suchbegriff an das gesamte Ereignis zu binden.

## Beispiel 1: Bindungsdimensionen verwenden, um zusätzliche Produktattribute einem Kauf zuzuordnen

Sie können Dimensionselemente innerhalb eines Objekt-Arrays an eine andere Dimension binden. Wenn das gebundene Dimensionselement angezeigt wird, ruft Customer Journey Analytics die gebundene Dimension zurück und schließt sie in das Ereignis für Sie ein. Betrachten Sie die folgende Customer Journey:

1. Ein Besucher sieht sich eine Produktseite zu einer Waschmaschine an.

   ```json
   {
       "PersonID": "1",
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. Der Besucher sieht sich dann eine Produktseite zu einem Trockner an.

   ```json
   {
       "PersonID": "1",
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. Letztlich tätigt er einen Kauf. Die Farbe der einzelnen Produkte war nicht im Kaufereignis enthalten.

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

Wenn Sie den Umsatz nach Farbe ohne eine gebundene Dimension betrachten wollten, bleibt die Dimension `product.color` bestehen und schreibt der Farbe des Trockners fälschlicherweise eine Gewichtung zu:

| product.color | Umsatz |
| --- | --- |
| Neonorange | 2099 |

Anmelden **[!UICONTROL Datenansichten]** und binden die [!DNL Product Color] Dimension zu [!DNL Product Name]:

![Bindungsdimension](../assets/binding-dimension.png)

Wenn Sie dieses Persistenzmodell festlegen, nimmt Customer Journey Analytics den Produktnamen bei jedem Festlegen der Produktfarbe zur Kenntnis. Wenn bei einem nachfolgenden Ereignis für diese Person derselbe Produktname erkannt wird, wird auch die Produktfarbe übernommen. Wenn Sie die Produktfarbe an den Produktnamen binden, sehen dieselben Daten etwa wie folgt aus:

| product.color | Umsatz |
| --- | --- |
| weiß | 1.600 |
| Neonorange | 499 |

## Beispiel 2: Verwenden von Bindungsmetriken, um Suchbegriffe mit einem Produktkauf zu verknüpfen

Eine der gängigsten Merchandising-Methoden in Adobe Analytics besteht darin, einen Suchbegriff an ein Produkt zu binden, sodass jeder Suchbegriff für das entsprechende Produkt angerechnet wird. Betrachten Sie die folgende Customer Journey:

1. Ein Besucher gelangt zu Ihrer Website und sucht „Boxhandschuhe“. Die Suchmetrik wird um 1 inkrementiert und die drei wichtigsten Suchergebnisse werden angezeigt.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
           },
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Professional gloves",
           }
       ]
   }
   ```

2. Er findet ein Paar Handschuhe, die ihm gefallen, und fügt sie zu seinem Warenkorb hinzu.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           }
       ]
   }
   ```

3. Der Besucher sucht dann nach „Tennisschläger“. Die Suchmetrik wird um 1 inkrementiert und die drei wichtigsten Suchergebnisse werden angezeigt.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Women's open racket",
           },
           {
               "name": "Extreme racket",
           }
       ]
   }
   ```

4. Er findet einen Schläger, der ihm gefällt, und fügt ihn seinem Warenkorb hinzu.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           }
       ]
   }
   ```

5. Der Besucher sucht ein drittes Mal, dieses Mal „Schuhe“. Die Suchmetrik wird um 1 inkrementiert und die drei wichtigsten Suchergebnisse werden angezeigt.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
           },
           {
               "name": "Tennis shoes",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

6. Er findet ein Paar Schuhe, die ihm gefallen, und fügt sie zu seinem Warenkorb hinzu.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

7. Der Besucher durchläuft den Checkout-Prozess und kauft diese drei Artikel.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "price": "79.99"
           }
       ]
   }
   ```

Wenn Sie ein Zuordnungsmodell verwenden, dessen Suchbegriffe keine Bindingsdimension enthalten, weisen alle drei Produkte den Umsatz nur einem einzigen Suchbegriff zu. Wenn Sie beispielsweise [!UICONTROL Original] Zuordnung mit der Suchbegriffdimension:

| search_term | Umsatz |
| --- | --- |
| Boxhandschuhe | $ 204.97 |

Wenn Sie [!UICONTROL Zuletzt verwendet] -Zuordnung mit der Suchbegriffdimension zuordnen, weisen alle drei Produkte weiterhin den Umsatz einem einzelnen Suchbegriff zu:

| search_term | Umsatz |
| --- | --- |
| Schuhe | $ 204.97 |

Während dieses Beispiel nur eine Person umfasst, können viele Personen, die nach verschiedenen Elementen suchen, Suchbegriffe verschiedenen Produkten zuordnen, was es schwierig macht festzustellen, welche die besten Suchergebnisse tatsächlich sind.

Sie können jetzt binden [!DNL Search Term] nach [!DNL Product Name] wann immer [!DNL Searches] -Metrik vorhanden ist, um Suchbegriffe korrekt dem Umsatz zuzuordnen.

![Bindungsmetrik](../assets/binding-metric.png)

In Analysis Workspace würde der resultierende Bericht in etwa wie folgt aussehen:

| search_term | Umsatz |
| --- | --- |
| Boxhandschuhe | $ 89.99 |
| Tennisschläger | $34.99 |
| Schuhe | $79.99 |

Customer Journey Analytics erkennt automatisch die Beziehung zwischen der ausgewählten Dimension und der Bindungsdimension. Wenn sich die Bindungsdimension in einem Objekt-Array befindet, während die ausgewählte Dimension auf einer höheren Ebene liegt, ist eine Bindungsmetrik erforderlich. Eine Bindungsmetrik fungiert als Trigger für eine Bindungsdimension, sodass sie sich nur an Ereignisse bindet, bei denen die Bindungsmetrik vorhanden ist. Im Beispiel oben enthält die Suchergebnisseite immer eine Suchbegriffdimension und eine Suchmetrik.

Wenn Sie die Suchbegriffdimension auf dieses Persistenzmodell festlegen, wird die folgende Logik ausgeführt:

* Wenn die Suchbegriffdimension festgelegt ist, überprüfen Sie, ob der Produktname vorhanden ist.
* Wenn der Produktname nicht vorhanden ist, führen Sie keine Aktionen aus.
* Wenn der Produktname vorhanden ist, überprüfen Sie, ob die Suchmetrik vorhanden ist.
* Wenn die Suchmetrik nicht vorhanden ist, führen Sie keine Aktionen aus.
* Wenn die Suchmetrik vorhanden ist, binden Sie den Suchbegriff an alle Produktnamen in diesem Ereignis. Er kopiert sich selbst auf die gleiche Ebene wie der Produktname für dieses Ereignis.  In diesem Beispiel ist er product.search_term.
* Wenn derselbe Produktname in einem nachfolgenden Ereignis angezeigt wird, wird der gebundene Suchbegriff auch an dieses Ereignis weitergeleitet.

## Beispiel 3: Binden des Videosuchbegriffs an das Benutzerprofil

Sie können einen Suchbegriff an ein Benutzerprofil binden, damit die Persistenz zwischen Profilen vollständig getrennt bleibt. Ihr Unternehmen führt beispielsweise einen Streaming-Service aus, bei dem ein übergeordnetes Konto mehrere Profile haben kann. Der Besucher besitzt ein Kinderprofil und ein Erwachsenenprofil.

1. Der Besucher meldet sich unter dem Kinderprofil an und sucht nach einer Kinderfernsehsendung. Beachten Sie Folgendes: `"ProfileID"` ist `2` und stellt das Kinderprofil dar.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "Searches": "1",
       "search_term": "kids show"
   }
   ```

1. Der Besucher findet die Sendung „Orangey“ und spielt sie für sein Kind ab.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

1. Später wechselt der Besucher zu seinem eigenen Profil und sucht nach Inhalten für Erwachsene. Beachten Sie Folgendes: `"ProfileID"` ist `1` und stellt das Erwachsenen-Profil dar. Beide Profile gehören zum selben Konto, das durch dasselbe `"PersonID"` repräsentiert wird.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "Searches": "1",
       "search_term": "grownup movie"
   }
   ```

1. Die Person findet die Sendung „Analytics After Hours“ und sieht sie sich an.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "1",
       "ShowName": "Analytics After Hours",
       "VideoStarts": "1"
   }
   ```

1. Am nächsten Tag spielt sie wieder die Sendung „Orangey“ für ihr Kind ab. Die Person muss nicht danach suchen, da sie die Show jetzt bereits kennt.

   ```json
   {
       "PersonID": "7078",
       "ProfileID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

Wenn Sie die Zuordnung „Zuletzt gesehen“ mit „Gültigkeit der Person“ verwenden, wird der Suchbegriff `"grownup movie"` dem letzten Abspielen der Kindersendung zugeordnet.

| Suchbegriff | Videostarts |
| --- | --- |
| Film für Erwachsene | 2 |
| Kindersendung | 1 |

Wenn Sie jedoch `search_term` an `ProfileID` binden, werden die Suchvorgänge jedes Profils auf sein eigenes Profil beschränkt und den richtigen Sendungen zugewiesen, nach denen es sucht.

![Besucherbindung](../assets/binding-profileid.png)

Analysis Workspace ordnet die zweite Folge von Orangey korrekt dem Suchbegriff `"kids show"` zu, ohne die Suche anderer Profile zu berücksichtigen.

| Suchbegriff | Videostarts |
| --- | --- |
| Kindersendung | 2 |
| Film für Erwachsene | 1 |

## Beispiel 4: Bewertung des Browse- und Suchverhaltens in einer Einzelhandelsumgebung

Sie können Werte an Dimensionen binden, die für vorhergehende Ereignisse festgelegt wurden. Wenn Sie eine Variable mit einer Bindungsdimension festlegen, berücksichtigt Customer Journey Analytics den beibehaltenen Wert. Wenn dieses Verhalten unerwünscht ist, können Sie die Persistenzeinstellungen der Bindungsdimension anpassen. Betrachten Sie das folgende Beispiel, bei dem `product_finding_method` für ein Ereignis festgelegt und dann für das folgende Ereignis an die Metrik „Hinzufügen zum Warenkorb“ gebunden wird.

1. Ein Besucher sucht nach `"camera"`. Beachten Sie, dass auf dieser Seite keine Produkte festgelegt sind.

   ```json
   {
       "search_term": "camera",
       "product_finding_method": "search"
   }
   ```

1. Der Besucher klickt auf eine Kamera, die ihm gefällt, und legt sie in seinen Warenkorb.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Er browst dann zur Kategorie „Herrengürtel“, ohne eine Suche durchzuführen. Beachten Sie, dass auf dieser Seite keine Produkte festgelegt sind.

   ```json
   {
       "category": "Men's belts",
       "product_finding_method": "browse"
   }
   ```

1. Er klickt auf einen Gürtel, der ihm gefällt, und legt ihn in den Warenkorb.

   ```json
   {
       "Product": [
           {
               "name": "Ratchet belt"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Er durchläuft den Checkout-Prozess und kauft diese beiden Artikel.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera",
               "price": "399.99"
           },
           {
               "name": "Ratchet belt",
               "price": "19.99"
           }
       ],
       "Purchase": "1"
   }
   ```

Wenn die Persistenz auf die letzte Zuordnung ohne Bindungsdimension eingestellt ist, werden alle 419,98 USD des Umsatzes der `browse`-Suchmethode zugerechnet.

| Produktsuchmethode | Umsatz |
| --- | --- |
| Browsen | 419,98 |

Wenn die Persistenz auf die letzte Zuordnung ohne Bindungsdimension eingestellt ist, werden alle 419,98 USD des Umsatzes der `search`-Suchmethode zugerechnet.

| Produktsuchmethode | Umsatz |
| --- | --- |
| Suche | 419,98 |

Wenn Sie jedoch `product_finding_method` an die Metrik „Hinzufügen zum Warenkorb“ binden, ordnet der resultierende Bericht jedes Produkt der richtigen Suchmethode zu.

| Produktsuchmethode | Umsatz |
| --- | --- |
| Suche | 399,99 |
| Browsen | 19,99 |


>[!MORELIKETHIS]
>
>[Binden von Dimensionen in Datenansichten](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/binding-dimensions-in-data-views.html) Tutorial.
