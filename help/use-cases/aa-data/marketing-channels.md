---
title: Verwenden von Marketing-Kanal-Dimensionen in Adobe Experience Platform
description: Verwenden Sie den Analytics-Quell-Connector, um Marketingkanal-Verarbeitungsregeln in Adobe Experience Platform zu importieren.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 61%

---

# Verwenden von Marketing-Kanal-Dimensionen in Adobe Experience Platform

Wenn Ihr Unternehmen den [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) verwendet, um Report Suite-Daten in die Customer Journey Analytics zu importieren, können Sie eine Verbindung in der Customer Journey Analytics konfigurieren, um Berichte zu Marketingkanal-Dimensionen zu erstellen.

## Voraussetzungen

* Report Suite-Daten müssen bereits mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) in Adobe Experience Platform importiert worden sein. Andere Datenquellen werden nicht unterstützt, da Marketing-Kanäle auf Verarbeitungsregeln in einer Analytics Report Suite angewiesen sind.
* Verarbeitungsregeln für den Marketing-Kanal müssen bereits eingerichtet sein. Siehe [Verarbeitungsregeln für Marketingkanäle](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=de) im Adobe Analytics-Komponentenleitfaden.

## Marketing-Kanal: Schema-Elemente

Nachdem Sie den Analytics-Quell-Connector in einer gewünschten Report Suite eingerichtet haben, wird ein XDM-Schema für Sie erstellt. Dieses Schema enthält alle Analytics-Dimensionen und -Metriken als Rohdaten. Diese Rohdaten enthalten keine Attribution oder Persistenz. Stattdessen durchläuft jedes Ereignis die Verarbeitungsregeln des Marketing-Kanals und zeichnet die erste Regel auf, die es erfüllt. Beim Erstellen einer Datenansicht in Customer Journey Analytics geben Sie Attribution und Persistenz an.

1. [Erstellen Sie eine Verbindung](/help/connections/create-connection.md) , die einen Datensatz enthält, der auf dem Analytics-Quell-Connector basiert.
2. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) mit folgenden Dimensionen:
   * **`channel.typeAtSource`**: entspricht der [Marketing-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=de)-Dimension.
   * **`channel._id`**: entspricht dem [Marketing-Kanal-Detail](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=de).
3. Weisen Sie jeder Dimension das gewünschte Attributionsmodell und die gewünschte Persistenz zu. Wenn Sie sowohl die First Touch- als auch die Last Touch-Dimension verwenden möchten, ziehen Sie jede Marketing-Kanal-Dimension mehrmals in den Komponentenbereich. Weisen Sie jeder Dimension das gewünschte Attributionsmodell und die gewünschte Persistenz zu. Adobe empfiehlt außerdem, jeder Dimension einen Anzeigenamen zu geben, um die Verwendung in Arbeitsbereich zu vereinfachen.
4. Erstellen Sie die Datenansicht.

Die Dimensionen Ihres Marketing-Kanals stehen jetzt in Analysis Workspace zur Verfügung.

>[!NOTE]
>
> Für den Analytics-Quell-Connector müssen sowohl `channel.typeAtSource` (Marketingkanal) als auch `channel._id` (Marketingkanal-Detail) ausgefüllt werden. Andernfalls wird keines von beiden in das XDM ExperienceEvent übertragen. Wenn die Marketing-Kanal-Details in der Quell-Report Suite leer sind, wird das Ergebnis leer `channel._id` und der Analytics-Quell-Connector wird ebenfalls `channel.typeAtSource` leer gelassen. Dies kann zu Berichtsunterschieden zwischen Adobe Analytics und Customer Journey Analytics führen.

## Unterschiede in der Verarbeitung und der Architektur

>[!IMPORTANT]
>
>Es gibt mehrere grundlegende Datenunterschiede zwischen Report Suite-Daten und Platform-Daten. Adobe empfiehlt dringend, die Verarbeitungsregeln für den Marketing-Kanal Ihrer Report Suite anzupassen, um eine korrekte Datenerfassung in Platform zu erleichtern.

>[!NOTE]
>
>Um die Effektivität von Marketing-Kanälen für Attribution IQ und Customer Journey Analytics zu maximieren, haben wir einige [überarbeitete Best Practices](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=de) veröffentlicht.

Die Marketing-Kanal-Einstellungen funktionieren bei Platform-Daten und Report Suite-Daten unterschiedlich. Beachten Sie beim Einrichten von Marketingkanälen für Customer Journey Analytics die folgenden Unterschiede:

* **Ist erste Seite des Besuchs**: Dieses Regelkriterium ist in verschiedenen Standarddefinitionen des Marketing-Kanals üblich. Jede Verarbeitungsregel, die dieses Kriterium enthält, wird in Platform ignoriert (andere Kriterien in derselben Regel sind weiterhin gültig). Sitzungen werden zum Zeitpunkt der Datenabfrage und nicht zum Zeitpunkt der Datenerfassung festgelegt. Dadurch wird verhindert, dass Platform dieses spezifische Regelkriterium verwendet. Adobe empfiehlt, alle Marketing-Kanal-Verarbeitungsregeln, die die Kriterien „Ist erste Seite des Besuchs“ enthalten, neu zu bewerten und alternative Ansätze zu wählen, die die gewünschten Ergebnisse liefern.

  ![Erste Seite des Besuchs](../assets/first-page-of-visit.png)

* **Last Touch-Kanal überschreiben**: Diese Einstellung im Marketing-Kanal-Manager verhindert normalerweise, dass bestimmte Kanäle eine Last Touch-Kanal-Gutschrift erhalten. Platform ignoriert diese Einstellung, sodass breite Kanäle wie „Direkt“ oder „Intern“ Metriken möglicherweise auf unerwünschte Art zuordnen können. Adobe empfiehlt, Kanäle zu entfernen, bei denen „Last Touch-Kanal überschreiben“ deaktiviert ist.
   * Sie können den Marketingkanal &quot;Direkt&quot;im Marketingkanal-Manager löschen und sich dann auf das Dimensionselement &quot;Kein Wert&quot;von Customer Journey Analytics für diesen Kanal verlassen. Sie können dieses Dimensionselement auch in „Direkt“ umbenennen oder das Dimensionselement beim Konfigurieren einer Datenansicht vollständig ausschließen.
   * Alternativ können Sie eine Marketing-Kanal-Classification erstellen und jeden Wert für sich selbst klassifizieren, mit Ausnahme der Kanäle, die Sie im Customer Journey Analytics ausschließen möchten. Sie können diese Klassifizierungsdimension dann beim Erstellen einer Datenansicht anstelle von `channel.typeAtSource` verwenden.

  ![Last Touch-Kanal überschreiben](../assets/override-last-touch-channel.png)

* **Ablauf des Marketing-Kanals**: Diese Einstellung für den Interaktionszeitraum legt den Zeitraum der Inaktivität fest, bevor eine Person einen neuen Erstkontakt-Kanal in den Report Suite-Daten abrufen kann. Platform verwendet eigene Attributionseinstellungen, sodass diese Einstellung beim Customer Journey Analytics vollständig ignoriert wird.

  ![Marketing-Kanalablauf](../assets/marketing-channel-expiration.png)

## Vergleichen von Daten zwischen Customer Journey Analytics und Adobe Analytics

Da sich die Architektur von Adobe Experience Platform von der einer Adobe Analytics-Report Suite unterscheidet, ist eine Übereinstimmung der Ergebnisse nicht garantiert. Sie können jedoch die folgenden Tipps nutzen, um diesen Vergleich zu erleichtern:

* Vergewissern Sie sich, dass die oben aufgeführten Unterschiede in der Architektur Ihren Vergleich nicht beeinträchtigen. Dazu gehört das Entfernen von Kanälen, die den Last Touch-Kanal nicht überschreiben, und das Entfernen von Regelkriterien, die dem ersten Treffer eines Besuchs (Sitzung) entsprechen.
* Überprüfen Sie, ob Ihre Verbindung dieselbe Report Suite wie Adobe Analytics verwendet. Wenn Ihre Customer Journey Analytics-Verbindung mehrere Report Suites mit eigenen Marketingkanal-Verarbeitungsregeln enthält, ist es nicht einfach, diese mit Adobe Analytics zu vergleichen. Sie müssten dann für jede Report Suite eine separate Verbindung für den Datenvergleich erstellen.
* Vergewissern Sie sich, dass Sie die gleichen Datumsbereiche vergleichen und dass die Zeitzoneneinstellung in Ihrer Datenansicht mit der Zeitzone der Report Suite übereinstimmt.
* Verwenden Sie beim Anzeigen von Report Suite-Daten ein benutzerspezifisches Attributionsmodell. Verwenden Sie beispielsweise die Dimension [Marketing-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=de) für Metriken mit nicht standardmäßigem Attributionsmodell. Adobe rät davon ab, die Standarddimensionen [First Touch-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=de) oder [Last Touch-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=de) zu vergleichen, da sie auf Attributionen beruhen, die in der Report Suite erfasst wurden. Customer Journey Analytics verlässt sich nicht auf die Attributionsdaten einer Report Suite. Stattdessen werden sie bei Ausführung eines Customer Journey Analytics-Berichts berechnet.
* Einige Metriken bieten aufgrund von Architektur-Unterschieden zwischen Report Suite-Daten und Platform-Daten keinen angemessenen Vergleich. Beispiele sind Besuche/Sitzungen, Personen/Personen und Ereignisse/Ereignisse.
