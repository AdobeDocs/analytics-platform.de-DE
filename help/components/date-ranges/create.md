---
title: Datumsbereich erstellen
description: Datumsbereich zur Verwendung in Berichten erstellen.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 91%

---

# Datumsbereich erstellen

Sie können einen Datumsbereich mit einer der beiden folgenden Methoden erstellen:

* Direkt in einem Workspace-Projekt durch Klicken auf die Schaltfläche ‚`+`‘ neben der Liste der Datumsbereichskomponenten auf der linken Seite
* Innerhalb des Datumsbereichsmanagers

So erstellen Sie einen Datumsbereich im Datumsbereichmanager:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei [analytics.adobe.com](https://analytics.adobe.com) an.
1. Navigieren Sie zu [!UICONTROL Komponenten] > [!UICONTROL Datumsbereiche].
1. Klicken Sie auf die Schaltfläche [!UICONTROL Hinzufügen], um das modale Fenster zu öffnen, das einen Datumsbereich erstellt.

## Erstellen eines modalen Datumsbereichsfensters

Das modale Fenster verfügt über vier Felder, die Sie bearbeiten können:

* **Datumsbereich**: Der Datumsbereich, den Sie für diese Komponente anlegen möchten.
* **Titel**: Der Name, den Sie für diese Komponente vergeben möchten. Der Titel wird in Workspace-Projekten verwendet.
* **Beschreibung**: Die Beschreibung, die Sie für diese Komponente verwenden möchten. Die Beschreibung wird beim Klicken auf das Symbol ![i](../assets/i.png) angezeigt.
* **Tags**: Organisieren Sie Ihre Datumsbereiche mithilfe von Tags. Ein Datumsbereich kann mehreren Tags angehören.

## Datumsbereich auswählen

Wenn Sie im modalen Fenster auf den Datumsbereich klicken, haben Sie mehrere Optionen:

* **Kalender**: Wählen Sie das Anfangs- und das Enddatum aus.
* **Rollierende Datumswerte verwenden**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie möchten, dass sich der Datumsbereich im Zeitverlauf ändert. Aktivieren Sie dieses Kontrollkästchen nicht, wenn Ihr Datumsbereich statisch bleiben soll.
* **Vorgabe auswählen**: Verwenden Sie diese Dropdownauswahl, wenn Sie einen benutzerdefinierten Datumsbereich wünschen, der auf einem Bereich basiert, den Adobe standardmäßig anbietet. Wenn Sie eine Voreinstellung auswählen, können Sie den Datumsbereich entsprechend Ihren Anforderungen weiter anpassen. Die von Adobe angebotenen Voreinstellungen werden dadurch nicht beeinflusst.

## Rollierende Datumsbereiche

Wenn Sie einen rollierenden Datumsbereich benötigen, können Sie diesen während des Rollierens anpassen. Sie können das Anfangs- und das Enddatum unabhängig voneinander rollieren lassen.

* **Anfangsdatum**: Wählen Sie, ob das Datum am Anfang eines Zeitraums oder am Ende eines Zeitraums beginnt, oder verwenden Sie einen festen Tag.
* **Der zu verwendende Zeitraum**: Wählen Sie aus, wie oft der Datumsbereich rollieren soll. Sie können ihn täglich, jede Woche, jeden Monat, jedes Quartal oder jedes Jahr rollieren lassen.
* **Versatz**: Wählen Sie den Versatz des Datumsbereichs aus. Sie können Tage, Wochen, Monate, Quartale oder Jahre hinzufügen oder abziehen.

## Beispiele für rollierende Daten

Einige Datumsbereiche können in bestimmten Berichten nützlich sein.

Seit Jahresbeginn bis heute:

```text
Start: Start of current year
End: End of current day
```

Seit letzten Donnerstag bis diesen Donnerstag:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Geschäftsjahr (z. B. wenn ein Geschäftsjahr im Dezember beginnt)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
