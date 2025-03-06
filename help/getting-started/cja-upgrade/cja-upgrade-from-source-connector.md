---
title: Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics vom Analytics-Quell-Connector zum Web SDK wechseln
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 773c03dfec99abcabdc667c549cce0dc1b1aabc4
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 14%

---

# Wechsel vom Analytics-Quell-Connector zum Web SDK für Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Implementierung des Analytics-Quell-Connectors"
>abstract="Mit dem Analytics-Quell-Connector können Sie mit Customer Journey Analytics einen Mehrwert erzielen. Sie müssen jedoch sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen. Dieser Leitfaden kann Sie bei zu einer unabhängigen Web SDK-Implementierung unterstützen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Vorhandenen Analytics-Quell-Connector löschen"
>abstract="Der Analytics-Quell-Connector, den Sie derzeit haben, ist nicht mit dem benutzerdefinierten Schema Ihrer Organisation kompatibel. Die Daten sind jedoch weiterhin in der Analytics Report Suite vorhanden. In diesem Schritt wird der aktuelle Analytics-Quell-Connector entfernt, damit Sie ihn in einem nachfolgenden Schritt mit dem richtigen Schema erneut erstellen können.<br><br>Bevor Sie den Quell-Connector löschen, sollten Sie sich mit anderen Personen in Ihrer Organisation abstimmen, um sicherzustellen, dass sich das Entfernen des Quell-Connectors nicht auf das Reporting in Ihrer Organisation auswirkt. Es kann mehrere Wochen dauern, bis diese Koordinierung abgeschlossen ist."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Die Verwendung des Analytics-Quell-Connectors als einzige Implementierung für Customer Journey Analytics hat inhärente Nachteile.

Wenn Ihr Unternehmen bereits ein Upgrade auf Customer Journey Analytics durchgeführt hat, indem es nur die Analytics-Quell-Connector-Implementierung verwendet, empfiehlt Adobe, zur fortlaufenden Datenerfassung auf eine neue Implementierung der Web-SDK überzugehen und den Analytics-Quell-Connector nur für Verlaufsdaten zu verwenden.

## Die Vor- und Nachteile der ausschließlichen Verwendung des Analytics-Quell-Connectors verstehen

Informationen zu den Vor- und Nachteilen der Verwendung des Analytics-Quell-Connectors finden Sie unter [Verwenden des Analytics-Quell-Connectors ausschließlich für die Aktualisierung auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Wechsel vom Analytics-Quell-Connector zum Web SDK

Im Folgenden finden Sie den allgemeinen Prozess für den Übergang von der ausschließlichen Verwendung des Analytics-Quell-Connectors zu einer Implementierung, die sowohl den Analytics-Quell-Connector als auch eine Web SDK-Implementierung umfasst:

1. Erstellen Sie eine Web-SDK-Implementierung, wie [Detaillierte empfohlene Upgrade](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) im Artikel „Upgrade [ Adobe Analytics auf Customer Journey Analytics&quot; ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

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

1. Fügen Sie den automatisch mit Ihrem ursprünglichen Analytics-Quell-Connector erstellten Datensatz zu Ihrer Customer Journey Analytics-Verbindung hinzu.

   Weitere Informationen finden Sie unter [Hinzufügen des Datensatzes aus Ihrem aktuellen Analytics-Quell-Connector zur Verbindung](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Bedingt) Wenn Sie Lookup-Datensätze verwenden, müssen Sie den Lookup-Datensatz erstellen und ihn Ihrer Verbindung hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Such-Datensätzen zum Klassifizieren von Daten in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Löschen Sie Ihren ursprünglichen Analytics-Quell-Connector. <!-- need to add steps somewhere about how to do this -->

1. [Erstellen Sie einen neuen Analytics-Quell-Connector und ordnen Sie Felder zu](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
