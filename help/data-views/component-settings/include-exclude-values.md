---
title: Komponenteneinstellung „Werte einschließen/ausschließen“
description: Ein Dimensionselement kann abhängig von seinem Wert bedingt ein- oder ausgeschlossen werden.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 97%

---

# Komponenteneinstellung „Werte einschließen/ausschließen“

„Werte einschließen/ausschließen“ ermöglicht die Erstellung von Regeln, die vom Wert eines Dimensionselements abhängen. Werte, die die von Ihnen festgelegten Kriterien nicht erfüllen, werden in Analysis Workspace so behandelt, als wären sie nicht vorhanden, obwohl die Daten noch im zugrunde liegenden Datensatz vorhanden sind.

![Datenansichten, in denen die Werte zum Ausschließen einschließen hervorgehoben werden](../assets/include-exclude.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Werteinschluss/-ausschluss festlegen] | Ein Kontrollkästchen, mit dem Sie Bedingungen aktivieren können, wenn Daten in einer Datenansicht enthalten sind. |
| [!UICONTROL Von Schreibweise abhängig] | Sichtbar bei Datentypen des Zeichenfolgen-Schemas. Standardmäßig ist diese Einstellung aktiviert. Diese Einstellung gilt nur für die Logik [!UICONTROL Werte einschließen/ausschließen], nicht für den resultierenden Wert. Sie können damit angeben, ob bei der Regel zwischen Groß- und Kleinschreibung unterschieden wird. |
| [!UICONTROL Übereinstimmung] | Hier können Sie angeben, welche Werte Sie vor der Attribution und den Filtern für das Reporting berücksichtigen möchten (z. B. nur Werte mit dem Wort „Fehler“). Sie können **[!UICONTROL Wenn alle Kriterien erfüllt sind]** oder **[!UICONTROL Wenn beliebige Kriterien erfüllt sind]** auswählen. |
| [!UICONTROL Kriterien] | Hier können Sie die Übereinstimmungslogik angeben, die auf eine bestimmte Filterregel angewendet werden soll.<ul><li>**Zeichenfolge**: Enthält die Wortgruppe, Enthält einen Begriff, Enthält alle Begriffe, Enthält keinen Begriff, Enthält die Wortgruppe nicht, Ist gleich, Ist nicht gleich, Beginnt mit, Endet mit</li><li>**Dezimalzahl/Ganzzahl**: gleich, ungleich, größer als, kleiner als, größer oder gleich, kleiner oder gleich</li><li>**Datum**: gleich, ungleich, ist später als, ist früher als, liegt zwischen</li></ul> |
| [!UICONTROL Übereinstimmungsoperand] | Hiermit können Sie den Übereinstimmungsoperanden angeben, auf den der Übereinstimmungsoperator angewendet werden soll.<ul><li>**Zeichenfolge**: Textfeld</li><li>**Dezimalzahl/Ganzzahl**: Textfeld mit Pfeilen nach oben/unten für numerische Werte</li><li>**Datum**: Auswahl der Tagesgranularität (Kalender)</li><li>**Datum Uhrzeit**: Auswahl der Datums- und Uhrzeitgranularität</li></ul> |
| [!UICONTROL Regel hinzufügen] | Hier können Sie einen zusätzlichen Übereinstimmungsoperator und -operanden angeben. |

{style="table-layout:auto"}
