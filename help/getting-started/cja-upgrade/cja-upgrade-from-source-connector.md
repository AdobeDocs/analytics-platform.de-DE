---
title: Übergang vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics vom Analytics-Quell-Connector zum Web SDK wechseln
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Übergang vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics

>[!NOTE]
> 
>Verwenden Sie die Informationen auf dieser Seite, wenn Sie Fragen in der Checkliste für das [Customer Journey Analytics-Upgrade](https://gigazelle.github.io/cja-ttv/) beantworten.

Die Verwendung des Analytics-Quell-Connectors als einzige Implementierung für Customer Journey Analytics hat Nachteile.

Wenn Ihr Unternehmen bereits über die Implementierung des Analytics-Quell-Connectors auf Customer Journey Analytics aktualisiert hat, sollten Sie in Erwägung ziehen, zu einer Implementierung überzugehen, die den Analytics-Quell-Connector verwendet (um historische Daten abzurufen), zusammen mit einer neuen Implementierung des Web SDK (für die kontinuierliche Datenerfassung).

## Vorteile und Nachteile der ausschließlichen Verwendung des Analytics-Quell-Connectors

Informationen zu den Vor- und Nachteilen der Verwendung des Analytics-Quell-Connectors finden Sie unter [Verwenden des Analytics-Quell-Connectors ausschließlich für die Aktualisierung auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Übergang vom Analytics-Quell-Connector zum Web SDK

Im Folgenden finden Sie den allgemeinen Prozess für die Umstellung von der ausschließlichen Verwendung des Analytics-Quell-Connectors auf eine Implementierung, die sowohl aus dem Analytics-Quell-Connector als auch einer Web-SDK-Implementierung besteht:

1. Erstellen Sie eine Web SDK-Implementierung, wie in [Detaillierte empfohlene Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) im Artikel, [Aktualisierung von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) beschrieben.

   Nachdem die Web SDK-Implementierung konfiguriert wurde, fahren Sie mit den folgenden Schritten fort.

1. [Erstellen Sie ein XDM-Schema für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Ordnen Sie jede Adobe Analytics-Dimension aus Ihrem Analytics-Quell-Connector der Dimension im Web SDK-Schema zu.

   1. 
      <!-- how do you get here -->

   1. Wählen Sie im Abschnitt **[!UICONTROL Standardfelder zuordnen]** die Registerkarte **[!UICONTROL Benutzerdefiniert]** aus.

   1. Wählen Sie **[!UICONTROL Neue Zuordnung hinzufügen]** aus.

      ![Schemafelder zuordnen](assets/schema-mapping.png)

   1. Wählen Sie im Feld **[!UICONTROL Source]** ein Adobe Analytics -Feld aus der Feldergruppe Adobe Analytics ExperienceEvent Template aus. Wählen Sie dann im Feld **[!UICONTROL Ziel]** das XDM-Feld aus, dem Sie es zuordnen möchten.

   1. Wiederholen Sie diesen Vorgang für jedes Feld in der Feldergruppe &quot;Adobe Analytics ExperienceEvent Template&quot;, mit dem Sie Daten in Adobe Analytics erfassen.

1. Fügen Sie den Datensatz hinzu, der automatisch mit Ihrem ursprünglichen Analytics-Quell-Connector erstellt wurde, zu Ihrer Customer Journey Analytics-Verbindung.

   Weitere Informationen finden Sie unter [Hinzufügen des Datensatzes aus Ihrem aktuellen Analytics-Quell-Connector zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Bedingt) Wenn Sie Lookup-Datensätze verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn zu Ihrer Verbindung hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Löschen Sie den ursprünglichen Analytics-Quell-Connector. <!-- need to add steps somewhere about how to do this -->

1. [Erstellen Sie einen neuen Analytics-Quell-Connector und Zuordnungsfelder](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
