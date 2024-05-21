---
title: Abgeleitete Felder
description: Ein abgeleitetes Feld gibt die Berichtszeitbearbeitung von Schemafeldern und/oder Standardkomponenten durch eine Reihe verfügbarer Funktionen und Funktionsvorlagen an.
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
source-git-commit: d9ec1dfe99ad77f7b995ef97b71eb31f28eafd35
workflow-type: tm+mt
source-wordcount: '5987'
ht-degree: 13%

---

# Abgeleitete Felder

Abgeleitete Felder sind ein wichtiger Aspekt der Echtzeitberichterstellungsfunktion in Adobe Customer Journey Analytics. Mit einem abgeleiteten Feld können Sie mithilfe eines anpassbaren Regel-Builders spontan (häufig komplexe) Datenmanipulationen definieren. Anschließend können Sie dieses abgeleitete Feld als Komponente (Metrik oder Dimension) in [Arbeitsbereich](../../analysis-workspace/home.md) oder definieren Sie das abgeleitete Feld als Komponente in [Datenansicht](../data-views.md).

Abgeleitete Felder können viel Zeit und Mühe sparen, verglichen mit der Transformation oder Manipulation Ihrer Daten an anderen Orten außerhalb von Customer Journey Analytics. Beispiel: [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)oder innerhalb Ihrer eigenen Extract Transform Load (ETL)-/Extract Load Transform (ELT)-Prozesse.

Abgeleitete Felder werden in [Datenansichten](../data-views.md), basieren auf einem Satz von Funktionen, die als Regeln definiert und auf verfügbare Standard- und/oder Schemafelder angewendet werden.

Anwendungsbeispiele sind:

- Definieren Sie ein abgeleitetes Feld für den Seitennamen, das falsche erfasste Seitennamenwerte korrigiert, um die Seitennamenwerte zu korrigieren.

- Definieren Sie ein abgeleitetes Marketing-Kanal -Feld, das den korrekten Marketing-Kanal anhand einer oder mehrerer Bedingungen bestimmt (z. B. URL-Parameter, Seiten-URL, Seitenname).

## Abgeleitete Feldoberfläche

Wenn Sie ein abgeleitetes Feld erstellen oder bearbeiten, verwenden Sie die abgeleitete Feldoberfläche.

![Screenshot des Dialogfelds &quot;Abgeleitetes Feld&quot;](assets/derived-field-dialog.png)


|  | Name | Beschreibung |
|---------|----------|--------|
| 1 | **Selektor** | Sie verwenden den Auswahlbereich, um Ihre Funktion, Funktionsvorlage, Schemafelder oder Standardfelder auszuwählen und in den Regel-Builder zu ziehen. <br/>Verwenden Sie das Dropdown-Menü, um zwischen folgenden Optionen auszuwählen: <br/>![Funktion](assets/Smock_Function_18_N.svg) [!UICONTROL Funktionen] - verfügbare Listen [Funktionen](#function-reference), </br>![Symbol für Funktionsvorlage](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL Funktionsvorlagen] - verfügbare Listen [Funktionsvorlagen](#function-templates), <br/>![Symbol für Schemafeld](assets/Smock_Folder_18_N.svg)  [!UICONTROL Schemafelder] - listet Felder auf, die aus Datensatzkategorien (Ereignis, Profil, Suche) und zuvor definierten abgeleiteten Feldern verfügbar sind, und <br/>![Standardfeld-Symbol](assets/Smock_DragHandle_18_N.svg) [!UICONTROL Standardfelder] - standardmäßige verfügbare Felder (z. B. Platform-Datensatz-ID). In der Auswahl werden nur Zeichenfolgen- und numerische Standardfelder angezeigt. Wenn die Funktion andere Datentypen unterstützt, können in der Regelschnittstelle Standardfelder mit diesen anderen Datentypen für Werte oder Felder ausgewählt werden.<br/>Sie können mithilfe der Variablen ![Suchsymbol](assets/Smock_Search_18_N.svg) Suchfeld. <br/>Sie können die ausgewählte Objektliste filtern, indem Sie ![Filtersymbol](assets/Smock_Filter_18_N.svg) Filter und Filter im [!UICONTROL Filtern von Feldern nach] angezeigt. Sie können Filter einfach mit ![Symbol &quot;Schließen&quot;](assets/CrossSize75.svg) für jeden Filter. |
| 2 | **Regel-Builder** | Sie erstellen Ihr abgeleitetes Feld sequenziell mithilfe einer oder mehrerer Regeln. Eine Regel ist eine spezifische Implementierung einer Funktion und ist daher immer nur einer Funktion zugeordnet. Sie erstellen eine Regel, indem Sie eine Funktion per Drag-and-Drop in den Regel-Builder ziehen. Der Funktionstyp bestimmt die Schnittstelle der Regel.<br/>Siehe [Regelschnittstelle](#rule-interface) für weitere Informationen. <br/>Sie können eine Funktion am Anfang, Ende oder zwischen Regeln einfügen, die bereits im Regel-Builder verfügbar sind. Die letzte Regel im Regel-Builder bestimmt die endgültige Ausgabe des abgeleiteten Felds. |
| 3 | **[!UICONTROL ** Feldeinstellungen **]** | Sie können Ihr abgeleitetes Feld benennen und beschreiben und dessen Feldtyp überprüfen. |
| 4 | **[!UICONTROL ** Endausgabe **]** | Dieser Bereich zeigt eine direkt aktualisierte Vorschau der Ausgabewerte basierend auf den Daten der letzten 30 Tage und den Änderungen, die Sie am abgeleiteten Feld im Regel-Builder vornehmen. |

{style="table-layout:auto"}

## Assistent für Feldvorlagen

Wenn Sie zum ersten Mal auf die abgeleitete Feldoberfläche zugreifen, wird die [!UICONTROL Mit einer Feldvorlage beginnen] angezeigt.

1. Wählen Sie die Vorlage aus, die den Typ des zu erstellenden Felds am besten beschreibt.
2. Wählen Sie die **[!UICONTROL ** Auswählen **]** zum Fortfahren.

Ihr abgeleitetes Felddialogfeld enthält Regeln (und Funktionen), die für den von Ihnen ausgewählten Feldtyp erforderlich oder nützlich sind. Siehe [Funktionsvorlagen](#function-templates) für weitere Informationen zu den verfügbaren Vorlagen.

## Regelschnittstelle

Wenn Sie eine Regel im Regel-Builder definieren, verwenden Sie die Regel-Oberfläche.

![Screenshot der abgeleiteten Felderregelschnittstelle](assets/rule-interface.png)

|  | Name | Beschreibung |
|---------|----------|--------|
| A  | **Regelname** | Standardmäßig lautet der Regelname **Regel X** (X bezieht sich auf eine Sequenznummer). Um den Namen einer Regel zu bearbeiten, wählen Sie deren Namen aus und geben Sie den neuen Namen ein, z. B. `Query Parameter`. |
| B | **Funktionsname** | Der ausgewählte Funktionsname für die Regel, z. B. [!UICONTROL URL PARSE]. Wenn die Funktion der letzte in der Funktionssequenz ist und die endgültigen Ausgabewerte bestimmt, folgt dem Funktionsnamen [!UICONTROL - ENDGÜLTIGE AUSGABE], beispielsweise [!UICONTROL URL-PARSE - ENDGÜLTIGE AUSGABE]. <br/>Um ein Popup mit weiteren Informationen zur Funktion anzuzeigen, wählen Sie ![Hilfesymbol](assets/Smock_HelpOutline_18_N.svg). |
| C  | **Regelbeschreibung** | Sie können optional einer Regel eine Beschreibung hinzufügen.<br/>Auswählen ![Weitere Symbole](assets/More.svg), wählen Sie **[!UICONTROL ** Beschreibung hinzufügen **]** , um eine Beschreibung hinzuzufügen, oder **[!UICONTROL ** Beschreibung bearbeiten **]** , um eine vorhandene Beschreibung zu bearbeiten.<br/>Geben Sie im Editor eine Beschreibung ein. Sie können die Symbolleiste verwenden, um den Text zu formatieren (mithilfe der Stilauswahl, fett, kursiv, unterstrichen, rechts, links, zentriert, Farbe, Nummernliste, Aufzählungsliste) und Links zu externen Informationen hinzuzufügen. <br/>Um die Bearbeitung der Beschreibung abzuschließen, klicken Sie außerhalb des Editors auf . |
| D | **Funktionsbereich** | Definiert die Logik der Funktion. Die Benutzeroberfläche hängt vom Funktionstyp ab. Das Dropdown-Menü für [!UICONTROL Feld] oder [!UICONTROL Wert] zeigt alle verfügbaren Feldkategorien (Regeln, Standardfelder, Felder) basierend auf dem Typ der Eingabe an, die die Funktion erwartet. Alternativ können Sie ein Feld aus der Auswahl &quot;Schema&quot;und &quot;Standard-Felder&quot;per Drag-and-Drop in ein Feld oder einen Wert ziehen. Wenn dieses gezogene Feld aus einem Lookup-Datensatz stammt, wird vor der von Ihnen definierten Funktion automatisch eine Suchfunktion eingefügt. <br/>Siehe [Funktionsreferenz](#function-reference) Detaillierte Informationen zu den einzelnen unterstützten Funktionen. |

{style="table-layout:auto"}

## abgeleitetes Feld erstellen

1. Wählen Sie eine Datenansicht aus oder erstellen Sie eine Datenansicht. Siehe [Datenansichten](../data-views.md) für weitere Informationen.

2. Wählen Sie die **[!UICONTROL ** Komponenten **]** in der Datenansicht.

3. Auswählen **[!UICONTROL ** abgeleitetes Feld erstellen **]** über die linke Leiste.

4. Um Ihr abgeleitetes Feld zu definieren, verwenden Sie die [!UICONTROL abgeleitetes Feld erstellen] -Schnittstelle. Siehe [Abgeleitete Feldoberfläche](#derived-field-interface).

   Um Ihr neues abgeleitetes Feld zu speichern, wählen Sie **[!UICONTROL ** Speichern **]**.

5. Ihr neues abgeleitetes Feld wird zum [!UICONTROL Abgeleitete Felder >] Container, als Teil von **[!UICONTROL ** Schemafelder **]** in der linken Leiste Ihrer Datenansicht.


## abgeleitetes Feld bearbeiten

1. Wählen Sie eine Datenansicht aus. Siehe [Datenansichten](../data-views.md) für weitere Informationen.

2. Wählen Sie die **[!UICONTROL ** Komponenten **]** in der Datenansicht.

3. Auswählen **[!UICONTROL ** Schemafelder **]** im [!UICONTROL Verbindung] auf der linken Seite.

4. Auswählen **[!UICONTROL ** Abgeleitete Felder >**]** Container.

5. Bewegen Sie den Mauszeiger über das abgeleitete Feld, das Sie bearbeiten möchten, und wählen Sie ![Symbol Bearbeiten](assets/Smock_Edit_18_N.svg).

6. Um Ihr abgeleitetes Feld zu bearbeiten, verwenden Sie die [!UICONTROL abgeleitetes Feld bearbeiten] -Schnittstelle. Siehe [Abgeleitete Feldoberfläche](#derived-field-interface).

   - Auswählen **[!UICONTROL ** Speichern **]** , um Ihr aktualisiertes abgeleitetes Feld zu speichern.

   - Auswählen **[!UICONTROL ** Abbrechen **]** , um alle Änderungen abzubrechen, die Sie am abgeleiteten Feld vorgenommen haben.

   - Auswählen **[!UICONTROL ** Speichern unter **]** , um das abgeleitete Feld als neues abgeleitetes Feld zu speichern. Das neue abgeleitete Feld hat denselben Namen wie das ursprünglich bearbeitete abgeleitete Feld mit `(copy)` hinzugefügt.

Wenn Sie ein abgeleitetes Feld als Komponente für Dimensionen oder Metriken in Ihrer Datenansicht verwendet haben:

1. Wählen Sie die Komponente aus. Beachten Sie, dass die Komponente möglicherweise einen anderen Namen hat als Ihr abgeleitetes Feld.

1. Wählen Sie im Komponentenbereich die ![Symbol Bearbeiten](assets/Smock_Edit_18_N.svg) neben Ihrem abgeleiteten Feld unter dem Namen des Schemafelds.

1. Um Ihr abgeleitetes Feld zu bearbeiten, verwenden Sie die [!UICONTROL abgeleitetes Feld bearbeiten] -Schnittstelle. Siehe [Abgeleitete Feldoberfläche](#derived-field-interface).

   - Auswählen **[!UICONTROL ** Speichern **]** , um Ihr aktualisiertes abgeleitetes Feld zu speichern.

   - Auswählen **[!UICONTROL ** Abbrechen **]** , um alle Änderungen abzubrechen, die Sie am abgeleiteten Feld vorgenommen haben.

   - Auswählen **[!UICONTROL ** Speichern unter **]** , um das abgeleitete Feld als neues abgeleitetes Feld zu speichern. Das neue abgeleitete Feld hat denselben Namen wie das ursprünglich bearbeitete abgeleitete Feld mit `(copy)` hinzugefügt.



## abgeleitetes Feld löschen

1. Wählen Sie eine Datenansicht aus. Siehe [Datenansichten](../data-views.md) für weitere Informationen.

2. Wählen Sie die **[!UICONTROL ** Komponenten **]** in der Datenansicht.

3. Auswählen **[!UICONTROL ** Schemafelder **]** Registerkarte in [!UICONTROL Verbindung] -Bereich.

4. Auswählen **[!UICONTROL ** Abgeleitete Felder >**]** Container.

5. Bewegen Sie den Mauszeiger über das abgeleitete Feld, das Sie löschen möchten, und wählen Sie ![Symbol Bearbeiten](assets/Smock_Edit_18_N.svg).

6. Im [!UICONTROL abgeleitetes Feld bearbeiten] Benutzeroberfläche, wählen Sie **[!UICONTROL Löschen]**.

   A [!UICONTROL Komponente löschen] werden Sie aufgefordert, den Löschvorgang zu bestätigen. Betrachten Sie alle externen Verweise, die außerhalb der Datenansicht auf das abgeleitete Feld vorhanden sein könnten.

   - Auswählen **[!UICONTROL ** Weiter **]** , um das abgeleitete Feld zu löschen.

Wenn Sie ein abgeleitetes Feld als Komponente für Dimensionen oder Metriken in Ihrer Datenansicht verwendet haben:

1. Wählen Sie die Komponente aus. Beachten Sie, dass die Komponente möglicherweise einen anderen Namen hat als Ihr abgeleitetes Feld.

1. Wählen Sie im Komponentenbereich die ![Symbol Bearbeiten](assets/Smock_Edit_18_N.svg) neben Ihrem abgeleiteten Feld unter dem Namen des Schemafelds.

1. Im [!UICONTROL abgeleitetes Feld bearbeiten] Benutzeroberfläche, wählen Sie **[!UICONTROL Löschen]**.

   A [!UICONTROL Komponente löschen] werden Sie aufgefordert, den Löschvorgang zu bestätigen. Betrachten Sie alle externen Verweise, die außerhalb der Datenansicht auf das abgeleitete Feld vorhanden sein könnten.

   - Auswählen **[!UICONTROL ** Weiter **]** , um das abgeleitete Feld zu löschen.

>[!NOTE]
>
>Abgeleitete Felder werden auf Verbindungsebene im Customer Journey Analytics verwaltet. Jede Änderung, die an einem abgeleiteten Feld in einer der mit dieser Verbindung verknüpften Datenansichten vorgenommen wurde, gilt für alle diese zugehörigen Datenansichten.



## Funktionsvorlagen

Um schnell ein abgeleitetes Feld für bestimmte Anwendungsfälle zu erstellen, sind Funktionsvorlagen verfügbar. Auf diese Funktionsvorlagen kann über den Auswahlbereich in der abgeleiteten Feldoberfläche zugegriffen werden oder sie werden bei der ersten Verwendung in der [!UICONTROL Mit einer Feldvorlage beginnen] Assistent.


### Marketing-Kanäle

Diese Vorlage ist so konfiguriert, dass die [URL-Analyse](#dnl-url-parse) und [Groß-/Kleinschreibung](#dnl-case-when) verwendet mehrere Male, um geeignete Werte aus einer URL zu erhalten. Anschließend wird auf diese Werte Logik angewendet, um die URL einem bestimmten Marketing-Kanal zuzuordnen.

+++ Details

Um die Vorlage zu verwenden, müssen Sie die richtigen Parameter für jede Funktion angeben, die als Teil der Regeln in der Vorlage aufgeführt wird. Siehe [Funktionsreferenz](#function-reference) für weitere Informationen.

![Screenshot des Regel-Builders für Marketing-Kanal-Vorlagen](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Funktionsreferenz

{{select-package}}

Für jede unterstützte Funktion finden Sie im Folgenden Details zu:

- Spezifikationen:
   - Eingabedatentyp: Typ der unterstützten Daten,
   - Eingabe: mögliche Werte für die Eingabe,
   - enthaltene Operatoren: für diese Funktion unterstützte Operatoren (falls vorhanden),
   - Einschränkungen: Einschränkungen, die für diese spezifische Funktion gelten,
   - Ausgabe.

- Anwendungsbeispiele, darunter:
   - Daten vor der Definition des abgeleiteten Felds,
   - wie das abgeleitete Feld definiert wird,
   - Daten nach der Definition des abgeleiteten Felds.

- Einschränkungen (falls zutreffend).

>[!NOTE]
>
>Die Suchfunktion wurde in [Klassifizieren](#classify). Siehe [Klassifizieren](#classify) für weitere Informationen.

<!-- CASE WHEN -->

### Fall wenn

Wendet Bedingungen an, die auf definierten Kriterien aus einem oder mehreren Feldern basieren. Diese Kriterien werden dann verwendet, um die Werte in einem neuen abgeleiteten Feld basierend auf der Reihenfolge der Bedingungen zu definieren.

+++ Details

## Spezifikationen {#casewhen-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Einschränkungen | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum</li></ul> | <ul><li>[!UICONTROL Wenn], [!UICONTROL Else If] container:</p><ul><li>[!UICONTROL Wert]</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul><li>[!UICONTROL Kriterium] (siehe eingeschlossene Operatoren, basierend auf dem ausgewählten Werttyp)</li></ul></li><li>[!UICONTROL Legen Sie dann den Wert auf], [!UICONTROL Setzen Sie den Wert andernfalls auf]:</p><ul><li>[!UICONTROL Wert]</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul></ul></li></ul> | <p>Zeichenfolgen</p><ul><li>Gleich</li><li>Gleich jedem Begriff</li><li>Enthält die Wortgruppe</li><li>Enthält einen der Begriffe</li><li>Enthält alle Begriffe</li><li>Beginnt mit</li><li>Beginnt mit einem beliebigen Begriff</li><li>Endet mit</li><li>Endet mit einem beliebigen Begriff</li><li>Ist nicht gleich</li><li>Entspricht keinem Begriff</li><li>Enthält nicht die Wortgruppe</li><li>Enthält keine Begriffe</li><li>Enthält nicht alle Begriffe</li><li>Beginnt nicht mit</li><li>Beginnt nicht mit einem Begriff</li><li>Endet nicht mit</li><li>endet nicht mit einem Begriff</li><li>Ist eingestellt</li><li>Ist nicht eingestellt</li></ul><p>Numerisch</p><ul><li>Gleich</li><li>Ist nicht gleich</li><li>Größer als</li><li>Größer als oder gleich</li><li>Kleiner als</li><li>Kleiner als oder gleich</li><li>Ist eingestellt</li><li>Ist nicht eingestellt</li></ul><p>Daten </p><ul><li>Gleich</li><li>Ist nicht gleich</li><li>ist später als</li><li>Ist später als oder gleich</li><li>ist vor</li><li>Ist vor oder gleich</li><li>Ist eingestellt</li><li>Ist nicht eingestellt</li></ul> | <ul><li>5 Funktionen pro abgeleitetem Feld</li><li>200 [Operatoren](#operators) pro abgeleitetes Feld. Ein Beispiel für einen einzelnen Operator ist &quot;Referrerdomäne enthält Google&quot;. </li></ul> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}

## Anwendungsfall 1 {#casewhen-uc1}

Sie möchten Regeln definieren, um verschiedene Marketing-Kanäle zu identifizieren, indem Sie eine kaskadierende Logik anwenden, um ein Marketing-Kanal-Feld auf den richtigen Wert festzulegen:

- Wenn der Referrer aus einer Suchmaschine stammt und die Seite einen Abfragezeichenfolgenwert hat, wobei `cid` contains `ps_`sollte der Marketing-Kanal als [!DNL *Gebührenpflichtige Suche*].
- Wenn der Referrer aus einer Suchmaschine stammt und die Seite keine Abfragezeichenfolge aufweist `cid`sollte der Marketing-Kanal als [!DNL *Kostenlose Suche*].
- Wenn eine Seite einen Abfragezeichenfolgenwert hat, bei dem `cid` contains `em_`sollte der Marketing-Kanal als [!DNL *Email*].
- Wenn eine Seite einen Abfragezeichenfolgenwert hat, bei dem `cid` contains `ds_`sollte der Marketing-Kanal als [!DNL *Display Ad*].
- Wenn eine Seite einen Abfragezeichenfolgenwert hat, bei dem `cid` contains `so_`sollte der Marketing-Kanal als [!DNL *Paid Social*].
- Wenn der Referrer aus einer Referrer-Domäne von [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com]oder [!DNL tiktok.com]sollte der Marketing-Kanal als [!DNL *Natürliche Social*].
- Wenn keine der oben genannten Regeln übereinstimmt, sollte der Marketing-Kanal als [!DNL *Andere verweisende Stelle*].

Falls Ihre Site die folgenden Beispielereignisse erhält, die [!UICONTROL Referrer] und [!UICONTROL Seiten-URL]sollten diese Ereignisse wie folgt identifiziert werden:

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### Daten vor {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` | |

{style="table-layout:auto"}

### Abgeleitetes Feld {#casewhen-uc1-derivedfield}

Sie definieren eine neue `Marketing Channel` abgeleitetes Feld. Sie verwenden die [!UICONTROL WENN] Funktionen zum Definieren von Regeln, die Werte für die basierend auf vorhandenen Werten für `Page URL` und `Referring URL` -Feld.

Beachten Sie die Verwendung der Funktion . [!UICONTROL URL PARSE] zum Definieren von Regeln zum Abrufen der Werte für `Page Url` und `Referring Url` vor dem [!UICONTROL WENN] -Regeln angewendet werden.

![Screenshot des Falls bei Regel 1](assets/case-when-1.png)

### Daten nach {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## Anwendungsfall 2 {#casewhen-uc2}

Sie haben mehrere verschiedene Suchvarianten in Ihrer [!DNL Product Finding Methods] Dimension. Um die Gesamtleistung der Suche im Vergleich zum Durchsuchen zu verstehen, müssen Sie viel Zeit damit verbringen, die Ergebnisse manuell zu kombinieren.

Ihre Site erfasst die folgenden Werte für Ihre [!DNL Product Finding Methods] Dimension. Letztlich weisen alle diese Werte auf eine Suche hin.

| Erfasster Wert | Tatsächlicher Wert |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### Daten vor {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### Abgeleitetes Feld {#casewhen-uc2-derivedfield}

Sie definieren eine `Product Finding Methods (new)` abgeleitetes Feld. Sie erstellen Folgendes [!UICONTROL WENN] Regeln im Regel-Builder. Diese Regeln gelten für die Logik für alle möglichen Varianten der alten [!UICONTROL Methoden zur Produktsuche] Feldwerte für `search` und `browse` mithilfe der [!UICONTROL Enthält die Wortgruppe] Kriterium.

![Screenshot des Falls, wenn Regel 2](assets/case-when-2.png)

### Daten nach {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## Anwendungsfall 3 {#casewhen-uc3}

Als Reiseunternehmen möchten Sie die Reisedauer für gebuchte Reisen buchen, damit Sie über die gesammelten Reisen berichten können.

Annahmen:

- Die Organisation erfasst die Reisedauer in ein numerisches Feld.
- Sie möchten 1-3 Tage Dauer in einen Eimer mit der Bezeichnung &#39;[!DNL short trip]&#39;
- Sie möchten 4 bis 7 Tage lang in einen Eimer mit der Bezeichnung &#39;[!DNL medium trip]&#39;
- Sie möchten 8-Tage-Dauern in einen Behälter mit der Bezeichnung &#39;[!DNL long trip]&#39;
- 132 Reisen wurden für eine Dauer von 1 Tag gebucht
- 110 Ausflüge wurden für eine Dauer von 2 Tagen gebucht
- 105 Ausflüge wurden für eine Dauer von 3 Tagen gebucht
- 99 Reisen wurden für eine Dauer von 4 Tagen gebucht
- 92 Reisen wurden für eine Dauer von 5 Tagen gebucht
- 85 Ausflüge wurden für eine Dauer von 6 Tagen gebucht
- 82 Reisen wurden für eine Dauer von 7 Tagen gebucht
- 78 Reisen wurden für eine Dauer von 8 Tagen gebucht
- 50 Reisen wurden für eine Dauer von 9 Tagen gebucht
- 44 Reisen wurden für eine Dauer von 10 Tagen gebucht
- 38 Ausflüge wurden für eine Dauer von 11 Tagen gebucht
- 31 Ausflüge wurden für eine Dauer von 12 Tagen gebucht

Ihr gewünschter Bericht sollte wie folgt aussehen:

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### Daten vor {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### Abgeleitetes Feld {#casewhen-uc3-derivedfield}

Sie definieren eine `Trip Duration (bucketed)` abgeleitetes Feld. Sie erstellen Folgendes [!UICONTROL WENN] Regel im Regel-Builder. Diese Regel wendet eine Logik an, um die alte [!UICONTROL Reisedauer] -Feldwerte in drei Werte: `short trip`, `medium  trip`, und `long trip`.

![Screenshot des Falls, wenn Regel 3](assets/case-when-3.png)


### Daten nach {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## Weitere Informationen

Customer Journey Analytics verwendet eine verschachtelte Containerstruktur, die nach dem Modell von Adobe Experience Platform modelliert wurde [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de) (Experience-Datenmodell). Siehe [Container](../create-dataview.md#containers) und [Filter-Container](../../components/filters/filters-overview.md#filter-containers) für weitere Hintergrundinformationen. Dieses Containermodell, auch wenn es von Natur aus flexibel ist, stellt bei der Verwendung des Regel-Builders einige Einschränkungen auf.

Customer Journey Analytics verwendet das folgende standardmäßige Containermodell:

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

Die folgenden Einschränkungen gelten und werden erzwungen, wenn *Auswählen* und *Einstellung* -Werte.

|  | Begrenzungen |
|:---:|----|
| **<span style='color: red'>A</span>** | Werte *select* innerhalb desselben [!UICONTROL Wenn], [!UICONTROL Else If] struct (using [!UICONTROL und] oder [!UICONTROL Oder]) in einer Regel muss aus demselben Container stammen und kann von jedem Typ sein (Zeichenfolge) ![Zeichenfolge](assets/Smock_ABC_18_N.svg), numerisch ![Numerisch](assets/Smock_123_18_N.svg)usw.). <br/>![Screenshot der Abhängigkeit A](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | Alle Werte, die Sie *set* in einer Regel muss aus demselben Container stammen und denselben Typ oder einen abgeleiteten Wert desselben Typs aufweisen. <br/> ![Screenshot der Abhängigkeit B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | Die Werte, die Sie *select* Überall [!UICONTROL Wenn], [!UICONTROL Else If] -Konstrukte in der Regelaufgabe *not* müssen aus demselben Container stammen und tun *not* müssen vom gleichen Typ sein. <br/> ![Screenshot der Abhängigkeit C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### Klassifizieren

Definiert einen Satz von Werten, die in einem neuen abgeleiteten Feld durch entsprechende Werte ersetzt werden.

+++ Details

>[!NOTE]
>
>Diese Funktion hieß ursprünglich Lookup , wurde aber in Classify umbenannt, um die Lookup-Funktion mit unterschiedlichen Funktionen aufzunehmen.

## Spezifikationen {#classify-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Einschränkungen | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum</li></ul> | <ul><li>[!UICONTROL Zu klassifizierendes Feld]:<ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul></li><li>[!UICONTROL Wenn der Wert gleich] und [!UICONTROL Werte ersetzen durch]:</p><ul><li>Zeichenfolge</li></ul><li>Originalwerte anzeigen<ul><li>Boolesch</li></ul></li></ul> | <p>Nicht angegeben</p> | <ul><li>5 Funktionen pro abgeleitetem Feld</li><li>200 [Operatoren](#operators) pro abgeleitetes Feld. Jeder Eintrag für [!UICONTROL Wenn Wert gleich Originalwert ist] [!UICONTROL Wert durch neuen Wert ersetzen] als Vorgang betrachtet.</li></ul> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#classify-uc1}

Sie verfügen über eine CSV-Datei, die eine Schlüsselspalte für `hotelID` und eine oder mehrere zusätzliche Spalten, die mit dem `hotelID`: `city`, `rooms`, `hotel name`.
Sie sammeln [!DNL Hotel ID] in einer Dimension, aber eine [!DNL Hotel Name] aus der `hotelID` in der CSV-Datei.

**Struktur und Inhalt von CSV-Dateien**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |
| [!DNL AMS789] | [!DNL Amsterdam] | 50 | [!DNL Okura] |

{style="table-layout:auto"}

**Aktueller Bericht**

| [!DNL Hotel ID] | Produktansichten |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |
| [!DNL AMS789] | 150 |

{style="table-layout:auto"}


**Gewünschter Bericht**

| [!DNL Hotel Name] | Produktansichten |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### Daten vor {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |
| [!DNL AMS789] |

{style="table-layout:auto"}


### Abgeleitetes Feld {#classify-uc1-derivedfield}

Sie definieren eine `Hotel Name` abgeleitetes Feld. Sie verwenden die [!UICONTROL CLASSIFY] -Funktion, um eine Regel zu definieren, mit der Sie Werte der [!UICONTROL Hotel-ID] und durch neue Werte ersetzen.

Wenn Sie Originalwerte einbeziehen möchten, die Sie nicht als Teil der zu klassifizierenden Werte definiert haben (z. B. Hotel-ID AMS789), wählen Sie **[!UICONTROL Originalwerte anzeigen]**. Dadurch wird sichergestellt, dass AMS789 Teil der Ausgabe für das abgeleitete Feld ist, obwohl dieser Wert nicht klassifiziert wird.

![Screenshot der Klassifizierungsregel 1](assets/classify-1.png)

### Daten nach {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## Anwendungsfall 2 {#classify-uc2}

Sie haben URLs anstelle des benutzerfreundlichen Seitennamens für mehrere Seiten erfasst. Diese gemischte Sammlung von Werten unterbricht die Berichterstellung.

### Daten vor {#classify-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Abgeleitetes Feld {#classify-uc2-derivedfield}

Sie definieren eine `Page Name (updated)` abgeleitetes Feld. Sie verwenden die [!UICONTROL CLASSIFY] -Funktion, um eine Regel zu definieren, mit der Sie Werte Ihrer vorhandenen [!UICONTROL Seitenname] und ersetzen Sie sie durch die aktualisierten richtigen Werte.

![Screenshot der Klassifizierungsregel 2](assets/classify-2.png)

### Daten nach {#classify-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |


## Weitere Informationen {#classify-moreinfo}

Die folgenden zusätzlichen Funktionen sind in der Benutzeroberfläche der Regel klassifizieren verfügbar:

- Um alle Tabellenwerte schnell zu löschen, wählen Sie ![Löschen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg) **[!UICONTROL Alle Tabellenwerte löschen]**.
- Um eine CSV-Datei hochzuladen, die die ursprünglichen Werte für Wenn -Werte gleich und neue Werte für Ersetzen mit enthält, wählen Sie ![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL CSV hochladen]**.
- Um eine Vorlage zum Erstellen einer CSV-Datei mit den hochzuladenden ursprünglichen und neuen Werten herunterzuladen, wählen Sie ![Herunterladen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL CSV-Vorlage herunterladen]**.
- Um eine CSV-Datei mit allen ursprünglichen und neuen Werten in der Regeloberfläche herunterzuladen, wählen Sie ![Herunterladen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL CSV-Werte herunterladen]**.


+++

<!-- CONCATENATE -->

### Verketten

Verbindet Feldwerte in einem neuen abgeleiteten Feld mit definierten Trennzeichen.

+++ Details

## Spezifikationen {#concatenate-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Einschränkungen | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li></ul> | <ul><li>[!UICONTROL Wert]:<ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li><li>Zeichenfolge</li></ul></li><li>[!UICONTROL Trennzeichen]:<ul><li>Zeichenfolge</li></ul></li> </ul> | <p>Nicht angegeben</p> | <p>2 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall {#concatenate-uc}

Sie erfassen derzeit die Ursprungs- und Zielflughafencodes als separate Felder. Sie möchten die beiden Felder zu einer durch Bindestriche (-) getrennten Dimension zusammenfassen. So können Sie die Kombination aus Ursprung und Ziel analysieren, um die wichtigsten gebuchten Routen zu identifizieren.

Annahmen:

- Die Ursprungs- und Zielwerte werden in separaten Feldern in derselben Tabelle erfasst.
- Der Benutzer legt fest, das Trennzeichen &quot;-&quot;zwischen den Werten zu verwenden.

Stellen Sie sich die folgenden Buchungen vor:

- Der Kunde ABC123 bucht einen Flug zwischen Salt Lake City (SLC) und Orlando (MCO)
- Der Kunde ABC456 bucht einen Flug zwischen Salt Lake City (SLC) und Los Angeles (LAX)
- Der Kunde ABC789 bucht einen Flug zwischen Salt Lake City (SLC) und Seattle (SEA)
- Der Kunde ABC987 bucht einen Flug zwischen Salt Lake City (SLC) und San Jose (SJO)
- Der Kunde ABC654 bucht einen Flug zwischen Salt Lake City (SLC) und Orlando (MCO)

Der gewünschte Bericht sollte wie folgt aussehen:

| Ursprung/Ziel | Buchungen |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Daten vor {#concatenate-uc-databefore}

| Origin | Ziel |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Abgeleitetes Feld {#concatenate-derivedfield}

Sie definieren eine neue [!UICONTROL Origin - Ziel] abgeleitetes Feld. Sie verwenden die [!UICONTROL CONCATENATE] -Funktion, um eine Regel zum Verketten der [!UICONTROL Original] und [!UICONTROL Ziel] -Felder, die `-` [!UICONTROL Trennzeichen].

![Screenshot der Verkettungsregel](assets/concatenate.png)

### Daten nach {#concatenate-dataafter}

| Origin - Ziel<br/>(abgeleitetes Feld) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- FIND AND REPLACE -->

### Suchen und ersetzen

Sucht alle Werte in einem ausgewählten Feld und ersetzt diese Werte durch einen anderen Wert in einem neuen abgeleiteten Feld.

+++ Details

## Spezifikationen {#findreplace-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Einschränkungen | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li></ul> | <ul><li>[!UICONTROL Wert]<ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul></li><li>[!UICONTROL Alle suchen], [!UICONTROL und ersetzen Sie alle durch]:<ul><li>Zeichenfolge</li></ul></li></ul></ul> | <p>Zeichenfolgen</p><ul><li>[!UICONTROL Alle suchen], [!UICONTROL und ersetzen Sie alle durch]</li></ul> | <p>5 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall {#findreplace-uc}

Sie haben einige falsch formatierte Werte für Ihren externen Marketingkanalbericht erhalten, z. B. `email%20 marketing` anstelle von `email marketing`. Diese fehlerhaften Werte brechen Ihre Berichterstellung auf und erschweren die Performance von E-Mails. Sie möchten `email%20marketing` mit `email marketing`.

**Originalbericht**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**Bevorzugter Bericht**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### Daten vor {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### Abgeleitetes Feld {#findreplace-uc-derivedfield}

Sie definieren eine `Email Marketing (updated)` abgeleitetes Feld. Sie verwenden die [!UICONTROL Suchen und Ersetzen] -Funktion zum Definieren einer Regel zum Suchen und Ersetzen aller Vorkommen von `email%20marketing` mit `email marketing`.

![Screenshot der Regel &quot;Suchen und Ersetzen&quot;](assets/find-and-replace.png)

### Daten nach {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### Suche

Sucht Werte mithilfe eines Felds aus einem Lookup-Datensatz und gibt einen Wert in einem neuen abgeleiteten Feld oder zur weiteren Regelverarbeitung zurück.

+++ Details

## Spezifikation {#lookup-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum</li></ul> | <ul><li>[!UICONTROL Feld zum Anwenden der Suche]:</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul><li>[!UICONTROL Datensatz nachschlagen]</li><ul><li>Datensatz</li></ul><li>[!UICONTROL Passender Schlüssel]<ul><li>Regeln</li><li>Felder</li></ul></li><li>Zurückzugebende Werte<ul><li>Regeln</li><li>Felder</li></ul></li></ul> | <p>Nicht angegeben</p> | <p>3 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld oder Wert für die weitere Verarbeitung in der nächsten Regel</p> |

{style="table-layout:auto"}

## Anwendungsfall {#lookup-uc}

Sie möchten den Aktivitätsnamen mithilfe der Aktivitäts-ID nachschlagen, die erfasst wird, wenn Ihre Kunden auf ein personalisiertes Banner klicken, das über Adobe Target angezeigt wird. Sie möchten einen Lookup-Datensatz mit A4T-Aktivitäten (Analytics for Target) verwenden, die Aktivitäten-IDs und Aktivitätsnamen enthalten.

### A4T-Lookup-Datensatz {#lookup-uc-lookup}

| Aktivitäts-ID | Aktivitätsname |
|---|---|
| 415851 | MVT-Test-Kategorieseiten |
| 415852 | Luma - Campaign Max. 2022 |
| 402922 | Homepage-Banner |

{style="table-layout:auto"}

### Abgeleitetes Feld {#lookup-uc-derivedfield}

Sie definieren eine `Activity Name` abgeleitetes Feld. Sie verwenden die [!UICONTROL SUCHEN] -Funktion, um eine Regel zu definieren, mit der Sie den Wert aus Ihren erfassten Daten abrufen können, wie in der [!UICONTROL Feld zum Anwenden der Suche] -Feld (z. B. **[!DNL ActivityIdentifier]**). Sie wählen den Lookup-Datensatz aus der [!UICONTROL Datensatz nachschlagen] list (beispielsweise **[!DNL New CJA4T Activities]**). Wählen Sie dann das Kennungsfeld aus (z. B. **[!DNL ActivityIdentifier]**) aus dem [!UICONTROL Übereinstimmungsschlüssel] und das Feld, das von der [!UICONTROL Rückzugebende Werte] list (beispielsweise **[!DNL ActivityName]**).

![Screenshot der Regel &quot;Kleinbuchstaben&quot;](assets/lookup.png)

## Weitere Informationen

Sie können schnell eine [!UICONTROL Suche] -Funktion im Regel-Builder verwenden, die bereits eine oder mehrere andere Funktionen enthält.

1. Auswählen **[!UICONTROL Schemafelder]** über Selektor.
1. Auswählen ![Symbol für Schemafeld](assets/Smock_Folder_18_N.svg) **[!UICONTROL Datensätze nachschlagen]**.
1. Wählen Sie Ihren Lookup-Datensatz aus und suchen Sie das Feld, das Sie für die Suche verwenden möchten.
1. Ziehen Sie das Suchfeld auf eines der verfügbaren Eingabefelder für eine Funktion (z. B. &quot;Case When&quot;). Wenn gültig, wird ein blaues Feld mit der Bezeichnung **[!UICONTROL + Hinzufügen]**, können Sie das Feld ablegen und automatisch eine Suchfunktion einfügen, bevor die Funktion das Suchfeld abgelegt hat. Die hinzugefügte Suchfunktion wird automatisch mit den entsprechenden Werten für alle Felder ausgefüllt.
   ![Lookup-Ziehen](assets/lookup-drag.png)

+++


<!-- LOWERCASE -->

### Kleinschreibung

Konvertiert Werte aus einem Feld in Kleinbuchstaben und speichert sie in ein neues abgeleitetes Feld.

+++ Details

## Spezifikation {#lowercase-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum</li></ul> | <ul><li>[!UICONTROL Feld]:</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul> | <p>Nicht angegeben</p> | <p>2 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}

## Anwendungsfall {#lowercase-uc}

Sie möchten alle erfassten Produktnamen für eine korrekte Berichterstellung in Kleinbuchstaben konvertieren.

### Daten vor {#lowercase-uc-databefore}

| Erfasste Produktnamen | Produktansichten |
|---|---:|
| Tennisschläger | 35 |
| Tennis Racket | 33 |
| Tennisschläger | 21 |
| Baseballschläger | 15 |
| Baseball Bat | 12 |
| Baseballschläger | 10 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#lowercase-uc-derivedfield}

Sie definieren eine `Product Names` abgeleitetes Feld. Sie verwenden die [!UICONTROL KLEIN] -Funktion, um eine Regel zum Konvertieren des Werts aus dem [!UICONTROL Erfasste Produktnamen] in Kleinbuchstaben umzuwandeln und im neuen abgeleiteten Feld zu speichern.

![Screenshot der Regel &quot;Kleinbuchstaben&quot;](assets/lowercase.png)


### Daten nach {#lowercase-uc-dataafter}

| Produktnamen | Produktansichten |
|---|---|
| Tennisschläger | 89 |
| Baseballschläger | 37 |

{style="table-layout:auto"}

+++

<!-- MERGE FIELDS -->

### Felder zusammenführen

Führt Werte aus zwei verschiedenen Feldern zu einem neuen abgeleiteten Feld zusammen.

+++ Details

## Spezifikation {#merge-fields-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum</li></ul> | <ul><li>[!UICONTROL Feld]:</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul> | <p>Nicht angegeben</p> | <p>5 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}

## Anwendungsfall {#merge-fields-uc}

Sie möchten eine Dimension erstellen, die sich aus dem Feld &quot;Seitenname&quot;und dem Feld &quot;Anrufgrund&quot;zusammensetzt und die Journey kanalübergreifend analysieren soll.

### Daten vor {#merge-fields-uc-databefore}

| Seitenname | Sitzung | Besucher |
|---|--:|--:|
| Hilfeseite | 250 | 200 |
| Startseite | 500 | 250 |
| Produktdetailseite | 300 | 200 |

{style="table-layout:auto"}

| Grund des Aufrufs | Sitzung | Besucher |
|---|--:|--:|
| Fragen zu meiner Bestellung | 275 | 250 |
| Änderung meiner Bestellung | 150 | 145 |
| Bestellproblem | 100 | 95 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#merge-fields-uc-derivedfield}

Sie definieren eine `Cross Channel Interactions` abgeleitetes Feld. Sie verwenden die [!UICONTROL FELDER ZUSAMMENFÜHREN] -Funktion, um eine Regel zum Zusammenführen der Werte aus dem [!UICONTROL Seitenname] und [!UICONTROL Grund des Aufrufs] und speichern Sie es im neuen abgeleiteten Feld.

![Screenshot der Regel &quot;Felder zusammenführen&quot;](assets/merge-fields.png)

### Daten nach {#merge-fields-uc-dataafter}

| Kanalübergreifende Interaktionen | Sitzungen | Besucher |
|---|--:|--:|
| Startseite | 500 | 250 |
| Produktdetailseite | 300 | 200 |
| Fragen zu meiner Bestellung | 275 | 250 |
| Hilfeseite | 250 | 200 |
| Änderung meiner Bestellung | 150 | 145 |
| Bestellproblem | 100 | 95 |

{style="table-layout:auto"}

## Weitere Informationen {#merge-fields-moreinfo}

Sie müssen denselben Feldtyp in einer Regel zum Zusammenführen von Feldern auswählen. Wenn Sie beispielsweise ein Datumsfeld auswählen, müssen alle anderen Felder, die Sie zusammenführen möchten, Datumsfelder sein.

![Screenshot der Einschränkung für Zusammenführungsfelder](assets/merge-fields-constraint.png)

+++


<!-- REGEX REPLACE -->

### Regulären Ausdruck ersetzen

Ersetzt einen Wert aus einem Feld mithilfe eines regulären Ausdrucks in ein neues abgeleitetes Feld.

+++ Details

## Spezifikation {#regex-replace-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li></ul> | <ul><li>[!UICONTROL Feld]:</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul></ul><ul><li>[!UICONTROL Regex]:</li><ul><li>Zeichenfolge</li></ul></li><li>[!UICONTROL Ausgabeformat]:<ul><li>Zeichenfolge</li></ul></ul><ul><li>Groß-/Kleinschreibung beachten</li><ul><li>Boolesch</li></ul></li></ul></li> | <p>Nicht angegeben</p> | <p>1 Funktion pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}

## Anwendungsfall {#regex-replace-uc}

Sie möchten eine Option einer URL erfassen und diese als eindeutige Seitenkennung verwenden, um den Traffic zu analysieren. Sie verwenden `[^/]+(?=/$|$)` für den regulären Ausdruck, um das Ende der URL zu erfassen, und `$1` als Ausgabemuster.

### Daten vor {#regex-replace-uc-databefore}

| Seiten-URL |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### Abgeleitetes Feld {#regex-replace-uc-derivedfield}

Sie erstellen eine `Page Identifier` abgeleitetes Feld. Sie verwenden die [!UICONTROL REGEX REPLATZ] -Funktion, um eine Regel zu definieren, die den Wert der [!UICONTROL Verweisende URL] -Feld mithilfe eines [!UICONTROL Regex] von `[^/]+(?=/$|$)` und [!UICONTROL Ausgabeformat] von `$1`.

![Screenshot der Regex-Ersetzungsregel](assets/regex-replace.png)


### Daten nach {#regex-replace-uc-dataafter}

| Seiten-ID |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## Weitere Informationen

Customer Journey Analytics verwendet eine Untergruppe der Perl-Regex-Syntax. Die folgenden Ausdrücke werden unterstützt:

| Ausdruck | Beschreibung |
| --- | --- |
| `a` | Ein einzelnes Zeichen: `a`. |
| `a\|b` | Ein einzelnes Zeichen: `a` oder `b`. |
| `[abc]` | Ein einzelnes Zeichen: `a`, `b` oder `c`. |
| `[^abc]` | Ein beliebiges einzelnes Zeichen, außer: `a`, `b` oder `c`. |
| `[a-z]` | Ein beliebiges einzelnes Zeichen im Bereich `a`–`z`. |
| `[a-zA-Z0-9]` | Ein beliebiges einzelnes Zeichen im Bereich `a`–`z`, `A`–`Z` oder im Ziffernbereich `0`–`9`. |
| `^` | Entspricht dem Zeilenanfang. |
| `$` | Entspricht dem Zeilenende. |
| `\A` | Beginn der Zeichenfolge. |
| `\z` | Ende der Zeichenfolge. |
| `.` | Entspricht einem beliebigen Zeichen. |
| `\s` | Beliebiges Whitespace-Zeichen. |
| `\S` | Beliebiges Zeichen, außer Whitespace-Zeichen. |
| `\d` | Beliebige Ziffer. |
| `\D` | Beliebiges Zeichen, außer Ziffern. |
| `\w` | Beliebige Buchstaben, Zahlen oder Unterstriche. |
| `\W` | Beliebiges Zeichen, das nicht in Wörtern zulässig ist. |
| `\b` | Beliebige Wortgrenze. |
| `\B` | Beliebiges Zeichen, das keine Wortgrenze ist. |
| `\<` | Wortbeginn. |
| `\>` | Wortende. |
| `(...)` | Alles dazwischen wird erfasst. |
| `(?:...)` | Nicht-kennzeichnende Erfassung. Verhindert, dass in der Ausgabezeichenfolge auf die Übereinstimmung verwiesen wird. |
| `a?` | Null oder eins von `a`. |
| `a*` | Null oder mehr von `a`. |
| `a+` | Eines oder mehr von `a`. |
| `a{3}` | Genau 3 von `a`. |
| `a{3,}` | 3 oder mehr von `a`. |
| `a{3,6}` | Zwischen 3 und 6 von `a`. |

Sie können diese Sequenzen im [!UICONTROL Ausgabeformat] beliebig oft und in beliebiger Reihenfolge verwenden, um die gewünschte Zeichenfolgenausgabe zu erlangen.

| Ausgabe-Platzhaltersequenz | Beschreibung |
| --- | --- |
| `$&` | Gibt aus, was mit dem gesamten Ausdruck übereinstimmt. |
| `$n` | Gibt aus, was mit dem n-ten Unterausdruck übereinstimmt. Beispiel: `$1` gibt den ersten Unterausdruck aus. |
| ``$` `` | Gibt den Text zwischen dem Ende der letzten gefundenen Übereinstimmung (oder dem Beginn des Textes aus, wenn keine vorherige Übereinstimmung gefunden wurde) und dem Beginn der aktuellen Übereinstimmung aus. |
| `$+` | Gibt aus, was mit dem letzten markierten Unterausdruck im regulären Ausdruck übereinstimmt. |
| `$$` | Gibt das Zeichenfolgenzeichen `"$"` aus. |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### Split

Teilt einen Wert aus einem Feld in ein neues abgeleitetes Feld.

+++ Details

## Spezifikation {#split-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li></ul> | <ul><li>[!UICONTROL Feld]:</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul></ul><ul><li>[!UICONTROL Methode]:</li><ul><li>Von links</li><li>Von rechts</li><li>In Array konvertieren</li></ul></li><li>Für Trennzeichen:<ul><li>Zeichenfolge</li></ul><li>Für Index:<ul><li>Numerisch</li></ul></li> | <p>Nicht angegeben</p> | <p>5 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}

## Anwendungsfall 1 {#split-uc1}

Sie erfassen Sprach-App-Antworten in einer durch Trennzeichen getrennten Liste in einer einzigen Dimension. Jeder Wert in der Liste soll ein eindeutiger Wert im Antwortbericht sein.

### Daten vor {#split-uc1-databefore}

| Voice-App-Antworten | Ereignisse |
|---|--:|
| Es war großartig, hat vollkommenen Sinn, wird anderen empfehlen | 1 |
| Es war toll, etwas verwirrend, wird anderen empfehlen | 1 |
| Es war nicht groß, sehr verwirrend, wird nicht empfohlen, andere | 1 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#split-u1-derivedfield}

Sie erstellen eine `Responses` abgeleitetes Feld. Sie verwenden die [!UICONTROL AUFTEILUNG] -Funktion, um eine Regel zur Verwendung der  [!UICONTROL In Array konvertieren] -Methode zum Konvertieren der Werte aus der [!UICONTROL Sprachanwendungs-Antwort] Feld verwenden `,` als [!UICONTROL Trennzeichen].

![Screenshot der Aufspaltungsregel 1](assets/split-1.png)

### Daten nach {#split-uc1-dataafter}

| Antworten | Ereignisse |
|---|--:|
| es war toll | 2 |
| wird anderen | 2 |
| es war nicht groß | 1 |
| vollendeten Sinn | 1 |
| etwas verwirrend | 1 |
| sehr verwirrend | 1 |
| wird anderen nicht empfehlen | 1 |

{style="table-layout:auto"}

## Anwendungsfall 2 {#split-uc2}

Sie erfassen Sprach-App-Antworten in einer durch Trennzeichen getrennten Liste in einer einzigen Dimension. Sie möchten die Antworten aus dem ersten Wert in der Liste in eine eigene Dimension umwandeln. Sie möchten den letzten Wert in der Liste in eine eigene Dimension setzen.

### Daten vor {#split-uc2-databefore}

| Antworten | Ereignisse |
|---|--:|
| es war großartig, vollendete Sinn, wird anderen empfohlen | 1 |
| Es war toll, etwas verwirrend, wird anderen empfehlen | 1 |
| Es war nicht groß, sehr verwirrend, wird nicht empfohlen, andere | 1 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#split-u2-derivedfield}

Sie erstellen eine  `First Response` abgeleitetes Feld. Sie verwenden die [!UICONTROL AUFTEILUNG] -Funktion, um eine Regel zu definieren, die den ersten Wert aus der [!UICONTROL Antworten] -Feld links neben der Antwort `,` als Trennzeichen.

![Screenshot der Aufspaltungsregel - erster Wert](assets/split-2.png)

Sie erstellen eine `Second Response` abgeleitetes Feld, um den letzten Wert aus dem [!UICONTROL Antworten] durch Auswahl von Von rechts, 1 als Trennzeichen und 1 als Index.

![Screenshot der Aufspaltungsregel - letzter Wert](assets/split-3.png)

### Daten nach {#split-uc2-dataafter}

| Erste Antwort | Ereignisse |
|---|--:|
| es war toll | 2 |
| es war nicht groß | 1 |

{style="table-layout:auto"}

| Zweite Antwort | Ereignisse |
|---|--:|
| wird anderen | 2 |
| wird anderen nicht empfehlen | 1 |

{style="table-layout:auto"}

+++


<!-- TRIM -->

### Zuschneiden

Beschneidet Leerzeichen, Sonderzeichen oder die Anzahl der Zeichen vom Anfang oder Ende der Feldwerte in ein neues abgeleitetes Feld.

+++ Details

## Spezifikation {#trim-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li></ul> | <ul><li>[!UICONTROL Feld]<ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul></li><li>Leerzeichen trimmen</li><li>Sonderzeichen trimmen<ul><li>Eingabe von Sonderzeichen</li></ul></li><li>Von links beschneiden<ul><li>Von <ul><li>Beginn der Zeichenfolge</li><li>Position<ul><li>Position #</li></ul></li><li>Zeichenfolge<ul><li>Zeichenfolgenwert</li><li>Index</li><li>Flag zum Einschließen von Zeichenfolge</li></ul></li></ul></li><li>Hierzu<ul><li>Ende der Zeichenfolge</li><li>Position<ul><li>Position #</li></ul></li><li>Zeichenfolge<ul><li>Zeichenfolgenwert</li><li>Index</li><li>Flag zum Einschließen von Zeichenfolge</li></ul></li><li>Länge</li></ul></li></ul></li><li>Von rechts zuschneiden<ul><li>Von <ul><li>Ende der Zeichenfolge</li><li>Position<ul><li>Position #</li></ul></li><li>Zeichenfolge<ul><li>Zeichenfolgenwert</li><li>Index</li><li>Flag zum Einschließen von Zeichenfolge</li></ul></li></ul></li><li>Hierzu<ul><li>Beginn der Zeichenfolge</li><li>Position<ul><li>Position #</li></ul></li><li>Zeichenfolge<ul><li>Zeichenfolgenwert</li><li>Index</li><li>Flag zum Einschließen von Zeichenfolge</li></ul></li><li>Länge</li></ul></li></ul></li></ul> | <p>Nicht angegeben</p> | <p>1 Funktion pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}

## Anwendungsfall 1 {#trim-uc1}

Sie erfassen Produktdaten, diese Daten enthalten jedoch ausgeblendete Leerzeichen, die die Fragmentberichterstellung enthalten. Sie möchten alle überschüssigen Leerzeichen einfach abschneiden

### Daten vor {#trim-uc1-databefore}

| Produkt-ID | Ereignisse |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#trim-u1-derivedfield}

Sie erstellen eine `Product Identifier` abgeleitetes Feld. Sie verwenden die [!UICONTROL TRIM] -Funktion zum Definieren einer Regel für **[!UICONTROL Leerzeichen zuschneiden]** aus dem **[!UICONTROL Produkt-ID]** -Feld.

![Screenshot der Aufspaltungsregel 1](assets/trim-1.png)

### Daten nach {#trim-uc1-dataafter}

| Produkt-ID | Ereignisse |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## Anwendungsfall 2 {#trim-uc2}

Ihre Daten zu den erfassten Seitennamen enthalten einige fehlerhafte Sonderzeichen am Ende des Seitennamens, die entfernt werden müssen.

### Daten vor {#trim-uc2-databefore}

| Name | Ereignisse |
|---|--:|
| Startseite# | 1 |
| Homepage? | 1 |
| Homepage% | 1 |
| Startseite&amp; | 1 |
| Homepage/ | 1 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#trim-u2-derivedfield}

Sie erstellen eine  `Page Name` abgeleitetes Feld. Sie verwenden die [!UICONTROL TRIM] -Funktion zum Definieren einer Regel für [!UICONTROL Sonderzeichen beschneiden] aus dem [!UICONTROL Name] -Feld mithilfe des [!UICONTROL Sonderzeichen] `#?%&/`.

![Screenshot der Aufspaltungsregel - erster Wert](assets/trim-2.png)

### Daten nach {#trim-uc2-dataafter}

| Seitenname | Ereignisse |
|---|--:|
| Startseite | 5 |

{style="table-layout:auto"}


## Anwendungsfall 3 {#trim-uc3}

Sie erfassen Daten, einschließlich einer storeID. Die storeID enthält den abgekürzten US-Statuscode als die ersten beiden Zeichen. Sie möchten diesen Statuscode nur in Ihren Berichten verwenden.

### Daten vor {#trim-uc3-databefore}

| storeID | Ereignisse |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| ODER234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### Abgeleitetes Feld {#trim-u3-derivedfield}

Sie erstellen eine  `Store Identifier` abgeleitetes Feld. Sie verwenden die [!UICONTROL TRIM] -Funktion zum Definieren einer Regel für [!UICONTROL Von rechts abschneiden] die [!UICONTROL storeID] -Feld vom String-Ende bis zur Position `3`.

![Screenshot der Aufspaltungsregel - erster Wert](assets/trim-3.png)

### Daten nach {#trim-uc3-dataafter}

| Store-Kennung | Ereignisse |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| ODER | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### URL-Parsen

Analysiert verschiedene Teile einer URL, einschließlich Protokoll-, Host-, Pfad- oder Abfrageparametern.

+++ Details

## Spezifikationen {#urlparse-io}

| Eingabedatentyp | Eingabe | Einbezogene Operatoren | Limit | Ausgabe |
|---|---|---|---|---|
| <ul><li>Zeichenfolge</li></ul> | <ul><li>[!UICONTROL Feld]:</li><ul><li>Regeln</li><li>Standardfelder</li><li>Felder</li></ul><li>[!UICONTROL Option]:<ul><li>[!UICONTROL Protokoll abrufen]</li><li>[!UICONTROL Hosting abrufen]</li><li>[!UICONTROL Pfad abrufen]</li><li>[!UICONTROL Abfragezeichenfolgenwert abrufen]<ul><li>[!UICONTROL Abfrageparameter]:<ul><li>Zeichenfolge</li></ul></li></ul></li><li>[!UICONTROL Hashwert abrufen]</li></ul></li></ul></li></ul> | <p>Nicht angegeben</p> | <p>5 Funktionen pro abgeleitetem Feld</p> | <p>Neues abgeleitetes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#urlparse-uc1}

Sie möchten die Referrer-Domäne aus der Referrer-URL nur als Teil des Regelsatzes eines Marketing-Kanals verwenden.

### Daten vor {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Abgeleitetes Feld {#urlparse-uc1-derivedfield}

Sie definieren eine  `Referring Domain` abgeleitetes Feld. Sie verwenden die [!UICONTROL URL PARSE] -Funktion, um eine Regel zum Abrufen des Hosts aus dem [!UICONTROL Verweisende URL] und speichern Sie es im neuen abgeleiteten Feld.

![Screenshot der Url Parse-Regel 1](assets/url-parse-1.png)

### Daten nach {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## Anwendungsfall 2 {#urlparse-uc2}

Sie möchten den Wert der Variablen `cid` -Parameter einer Abfragezeichenfolge in einer [!DNL Page URL] als Teil der Ausgabe eines abgeleiteten Trackingcode-Berichts.

### Daten vor {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Abgeleitetes Feld {#urlparse-uc2-derivedfield}

Sie definieren eine `Query String CID` abgeleitetes Feld. Sie verwenden die [!UICONTROL URL PARSE] -Funktion, um eine Regel zum Abrufen des Werts des Abfragezeichenfolgenparameters im [!UICONTROL Seiten-URL] -Feld angeben `cid` als Abfrageparameter. Der Ausgabewert wird im neuen abgeleiteten Feld gespeichert.

![Screenshot der Url Parse-Regel 2](assets/url-parse-2.png)

### Daten nach {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## Einschränkungen

Die folgenden Einschränkungen gelten für die Funktion für abgeleitete Felder im Allgemeinen:

- Sie können beim Definieren von Regeln für ein abgeleitetes Feld maximal zehn verschiedene Schemafelder (ohne Standardfelder) verwenden.
   - Von diesen maximal zehn verschiedenen Schemafeldern sind maximal drei Lookup-Schema- oder Profilschemafelder zulässig.
- Pro Customer Journey Analytics-Verbindung können maximal 100 abgeleitete Felder verwendet werden.


### Zusammenfassung der Funktionsbeschränkungen

| Funktion | Einschränkungen |
|---|---|
| <p>Fall wenn</p> | <ul><li>5 Fall Wenn Funktionen eines abgeleiteten Felds</li><li>200 [Operatoren](#operators) pro abgeleitetem Feld</li></ul> |
| <p>Klassifizieren</p> | <ul><li>5 Klassifizieren von Funktionen pro abgeleitetem Feld</li><li>200 [Operatoren](#operators) pro abgeleitetem Feld</li></ul> |
| <p>Verketten</p> | <ul><li>2 Funktionen pro abgeleitetem Feld verketten</li></ul> |
| <p>Suchen und Ersetzen</p> | <ul><li>2 Funktionen zum Suchen und Ersetzen für abgeleitetes Feld</li></ul> |
| <p>Suche</p> | <ul><li>5 Suchfunktionen pro abgeleitetem Feld</li></ul> |
| <p>Kleinschreibung</p> | <ul><li>2 Funktionen in Kleinbuchstaben pro abgeleitetem Feld</li></ul> |
| <p>Felder zusammenführen</p> | <ul><li>2 Funktionen zum Zusammenführen von Feldern pro abgeleitetem Feld</li></ul> |
| <p>Regulären Ausdruck ersetzen</p> | <ul><li>1 Regex-Ersetzungsfunktion pro abgeleitetem Feld</li></ul> |
| <p>Split</p> | <ul><li>5 Aufspaltungsfunktionen pro abgeleitetem Feld</li></ul> |
| <p>Zuschneiden</p> | <ul><li>1 Trimmfunktion pro abgeleitetem Feld</li></ul> |
| <p>URL-Parsen</p> | <ul><li>5 URL-Parsen-Funktionen pro abgeleitetem Feld</li></ul> |

{style="table-layout:auto"}

### Operatoren

Ein Operator in einem If - oder Else If -Konstrukt in einer Case When -Funktion ist die Kombination einer Bedingung mit **one** -Wert. Jeder zusätzliche Wert für das Kriterium erhöht die Anzahl der Benutzer.

In der folgenden Bedingung werden beispielsweise 13 Operatoren verwendet.

![Beispieloperatoren](assets/operators-sample.png)

Ein Operator in der Klassifizierungsfunktion ist ein Einzeleintrag für [!UICONTROL Wenn Wert gleich Ausgangswert] [!UICONTROL Wert durch neuen Wert ersetzen].

Die unten stehende Regel Klassifizieren verwendet beispielsweise 3 Operatoren.

![Screenshot der Klassifizierungsregel 1](assets/classify-1.png)


## Weitere Informationen

[`Trim`](#trim) und [`Lowercase`](#lowercase) sind bereits in den Komponenteneinstellungen in verfügbar. [Datenansichten](../component-settings/overview.md). Mithilfe von abgeleiteten Feldern können Sie diese Funktionen kombinieren, um eine komplexere Datenumwandlung direkt im Customer Journey Analytics durchzuführen. Sie können beispielsweise `Lowercase` , um die Groß-/Kleinschreibung in einem Ereignisfeld zu entfernen, und verwenden Sie dann [`Lookup`](#lookup) , um das neue Feld in Kleinbuchstaben mit einem Lookup-Datensatz abzugleichen, der nur Suchschlüssel in Kleinbuchstaben enthält. Oder Sie können `Trim` zum Entfernen von Zeichen vor der Einrichtung `Lookup` im neuen Feld.

Die Unterstützung von Lookup- und Profilfeldern in abgeleiteten Feldern ermöglicht es Ihnen, Daten basierend auf der Ereignissuche und den Profilattributen umzuwandeln. Dies kann besonders bei B2B-Szenarien mit Daten auf Kontoebene in Lookup- oder Profildatensätzen hilfreich sein. Darüber hinaus ist diese Unterstützung nützlich, um Daten in allgemeinen Feldern aus Suchdaten (wie Kampagneninformationen und Angebotstyp) oder aus Profildaten (wie Mitgliederebene und Kontotyp) zu bearbeiten.

Weitere Hintergrundinformationen zu abgeleiteten Feldern finden Sie unter .

- [Optimale Nutzung Ihrer Daten: Ein Framework für die Verwendung abgeleiteter Felder im Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)

- [Abgeleitete Felder Anwendungsfälle für Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)
