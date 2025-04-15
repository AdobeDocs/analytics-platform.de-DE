---
title: Wechsel vom Analytics-Quell-Connector zum Web-SDK für Customer Journey Analytics
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics vom Analytics-Quell-Connector zum Web-SDK wechseln
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 92%

---

# Wechsel vom Analytics-Quell-Connector zum Web-SDK für Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Implementierung des Analytics-Quell-Connectors"
>abstract="Mit dem Analytics-Quell-Connector können Sie mit Customer Journey Analytics einen Mehrwert erzielen. Sie müssen jedoch sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen. Dieser Leitfaden kann Sie bei zu einer unabhängigen Web SDK-Implementierung unterstützen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Löschen des vorhandenen Analytics-Quell-Connectors"
>abstract="Der derzeit genutzte Analytics-Quell-Connector ist nicht mit dem benutzerdefinierten Schema Ihres Unternehmens kompatibel. Die Daten sind jedoch weiterhin in der Analytics Report Suite vorhanden. In diesem Schritt wird der aktuelle Analytics-Quell-Connector entfernt, damit Sie ihn in einem nachfolgenden Schritt mit dem richtigen Schema erneut erstellen können.<br><br>Bevor Sie den Quell-Connector löschen, empfiehlt es sich, sich mit anderen in Ihrem Unternehmen abzustimmen, um sicherzustellen, dass sich das Entfernen des Quell-Connectors nicht auf das Reporting im Unternehmen auswirkt. Es kann mehrere Wochen dauern, bis diese Abstimmung abgeschlossen ist."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Die Verwendung des Analytics-Quell-Connectors als einzige Implementierung für Customer Journey Analytics hat inhärente Nachteile.

Wenn Ihr Unternehmen bereits ein Upgrade auf Customer Journey Analytics durchgeführt hat, indem es nur die Analytics-Quell-Connector-Implementierung verwendet, empfiehlt Adobe, zur fortlaufenden Datenerfassung auf eine neue Implementierung der Web-SDK überzugehen und den Analytics-Quell-Connector nur für Verlaufsdaten zu verwenden.

## Informationen zu den Vor- und Nachteile der ausschließlichen Verwendung des Analytics-Quell-Connectors

Informationen zu den Vor- und Nachteilen der Verwendung des Analytics-Quell-Connectors finden Sie unter [Ausschließliches Verwenden des Analytics-Quell-Connectors für das Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Wechsel vom Analytics-Quell-Connector zum Web-SDK

Im Folgenden finden Sie den allgemeinen Prozess für den Wechsel von der ausschließlichen Verwendung des Analytics-Quell-Connectors zu einer Implementierung, die sowohl den Analytics-Quell-Connector als auch eine Web-SDK-Implementierung umfasst:

1. Erstellen Sie eine Web-SDK-Implementierung, wie unter [Detaillierte empfohlene Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) im Artikel [Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) beschrieben.

   Nachdem Sie die Web-SDK-Implementierung konfiguriert haben, fahren Sie mit den folgenden Schritten fort.

1. [Erstellen Sie ein XDM-Schema für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Ordnen Sie jede Adobe Analytics-Dimension aus Ihrem Analytics-Quell-Connector der Dimension im Web-SDK-Schema zu.

   1. 
      <!-- how do you get here -->

   1. Wählen Sie im Abschnitt **[!UICONTROL Standardfelder zuordnen]** die Registerkarte **[!UICONTROL Benutzerdefiniert]** aus.

   1. Wählen Sie **[!UICONTROL Neue Zuordnung hinzufügen]** aus.

      ![Zuordnen von Schemafeldern](assets/schema-mapping.png)

   1. Wählen Sie unter **[!UICONTROL Quellfeld]** ein Adobe Analytics-Feld aus der Feldergruppe „Adobe Analytics ExperienceEvent Template“ aus. Wählen Sie dann unter **[!UICONTROL Zielfeld]** das XDM-Feld aus, dem es zugeordnet werden soll.

   1. Wiederholen Sie diesen Vorgang für jedes Feld in der Feldergruppe „Adobe Analytics ExperienceEvent Template“, mit dem Sie Daten in Adobe Analytics erfassen.

1. Fügen Sie den automatisch mit Ihrem ursprünglichen Analytics-Quell-Connector erstellten Datensatz zu Ihrer Customer Journey Analytics-Verbindung hinzu.

   Weitere Informationen finden Sie unter [Hinzufügen des Datensatzes aus Ihrem aktuellen Analytics-Quell-Connector zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Bedingt) Wenn Sie Lookup-Datensätze verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn Ihrer Verbindung hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Löschen Sie Ihren ursprünglichen Analytics-Quell-Connector. <!-- need to add steps somewhere about how to do this -->

1. [Erstellen Sie einen neuen Analytics-Quell-Connector und ordnen Sie Felder zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

{{upgrade-final-step}}
