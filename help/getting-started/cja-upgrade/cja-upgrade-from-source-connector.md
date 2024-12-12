---
title: Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics vom Analytics-Quell-Connector zum Web SDK wechseln
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: f4fd3c1932a736577d480e86cad70f55de75cb21
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite bei der Beantwortung von Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/).

Die Verwendung des Analytics-Quell-Connectors als einzige Implementierung für das Customer Journey Analytics hat inhärente Nachteile.

Wenn Ihr Unternehmen bereits ein Upgrade auf Customer Journey Analytics durchgeführt hat, bei dem nur die Analytics-Quell-Connector-Implementierung verwendet wird, empfiehlt Adobe den Wechsel zu einer Implementierung, die den Analytics-Quell-Connector (für Verlaufsdaten) in Verbindung mit einer neuen Implementierung der Web-SDK (für die fortlaufende Datenerfassung) verwendet.

## Die Vor- und Nachteile der ausschließlichen Verwendung des Analytics-Quell-Connectors verstehen

Informationen zu den Vor- und Nachteilen der Verwendung des Analytics-Quell-Connectors finden Sie unter [Verwenden des Analytics-Quell-Connectors ausschließlich für die Aktualisierung auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Wechsel vom Analytics-Quell-Connector zum Web SDK

Im Folgenden finden Sie den allgemeinen Prozess für den Übergang von der ausschließlichen Verwendung des Analytics-Quell-Connectors zu einer Implementierung, die sowohl den Analytics-Quell-Connector als auch eine Web SDK-Implementierung umfasst:

1. Erstellen Sie eine Web-SDK-Implementierung, wie [Detaillierte empfohlene Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) im Artikel &quot;[ von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) beschrieben.

   Nachdem die Web-SDK-Implementierung konfiguriert wurde, fahren Sie mit den folgenden Schritten fort.

1. [Erstellen eines XDM-Schemas für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Ordnen Sie jede Adobe Analytics-Dimension aus Ihrem Analytics-Quell-Connector der Dimension im Web SDK-Schema zu.

   1. 
      <!-- how do you get here -->

   1. Wählen **[!UICONTROL Abschnitt Standardfelder zuordnen]** die Registerkarte **[!UICONTROL Benutzerdefiniert]** aus.

   1. Wählen Sie **[!UICONTROL Neue Zuordnung hinzufügen]** aus.

      ![Schemafelder zuordnen](assets/schema-mapping.png)

   1. Wählen Sie im Feld **[!UICONTROL Source]** ein Adobe Analytics-Feld aus der Feldergruppe der Adobe Analytics ExperienceEvent-Vorlage aus. Wählen Sie dann im **[!UICONTROL Zielfeld]** das XDM-Feld aus, dem Sie es zuordnen möchten.

   1. Wiederholen Sie diesen Vorgang für jedes Feld in der Feldergruppe der Adobe Analytics ExperienceEvent-Vorlage, das Sie zum Erfassen von Daten in Adobe Analytics verwenden.

1. Fügen Sie den Datensatz, der automatisch mit Ihrem ursprünglichen Analytics-Quell-Connector erstellt wurde, zu Ihrer Customer Journey Analytics-Verbindung hinzu.

   Weitere Informationen finden Sie unter [Hinzufügen des Datensatzes aus Ihrem aktuellen Analytics-Quell-Connector zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Bedingt) Wenn Sie Lookup-Datensätze verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn Ihrer Verbindung hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Löschen Sie Ihren ursprünglichen Analytics-Quell-Connector. <!-- need to add steps somewhere about how to do this -->

1. [Erstellen Sie einen neuen Analytics-Quell-Connector und ordnen Sie Felder zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
