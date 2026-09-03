---
title: Wechsel vom Analytics-Quell-Connector zum Web-SDK für Customer Journey Analytics
description: Erfahren Sie, wie Sie beim Upgrade auf Customer Journey Analytics vom Analytics-Quell-Connector zum Web-SDK wechseln
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
autotag-review: '2026-05-19T08:14:22.976Z'
TQID: 'https://experienceleague.adobe.com/af02lBhLgsKQOkm2yVW4jHvFYVbqOCDi6-puKoKytMo'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 100%

---

# Wechsel vom Analytics-Quell-Connector zum Web-SDK für Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Implementierung des Analytics-Quell-Connectors"
>abstract="Mit dem Analytics-Quell-Connector können Sie mit Customer Journey Analytics einen Mehrwert erzielen. Sie müssen jedoch sowohl für Adobe Analytics als auch für Customer Journey Analytics bezahlen. Dieser Leitfaden kann Sie bei einer unabhängigen Implementierung des Web SDK unterstützen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Löschen des vorhandenen Analytics-Quell-Connectors"
>abstract="Der derzeit genutzte Analytics-Quell-Connector ist nicht mit dem benutzerdefinierten Schema Ihres Unternehmens kompatibel. Die Daten sind jedoch weiterhin in der Analytics Report Suite vorhanden. In diesem Schritt wird der aktuelle Analytics-Quell-Connector entfernt, damit Sie ihn in einem nachfolgenden Schritt mit dem richtigen Schema erneut erstellen können.<br><br>Bevor Sie den Quell-Connector löschen, empfiehlt es sich, sich mit anderen in Ihrem Unternehmen abzustimmen, um sicherzustellen, dass sich das Entfernen des Quell-Connectors nicht auf das Reporting im Unternehmen auswirkt. Es kann mehrere Wochen dauern, bis diese Abstimmung abgeschlossen ist."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Die Verwendung des Analytics-Quell-Connectors als einzige Implementierung für Customer Journey Analytics hat inhärente Nachteile.

Wenn Ihre Organisation bereits ein Upgrade auf Customer Journey Analytics durchgeführt hat, bei dem sie nur die Analytics-Quell-Connector-Implementierung verwendet, empfiehlt Adobe, zur fortlaufenden Datenerfassung auf eine neue Implementierung des Web SDK umzustellen und den Analytics-Quell-Connector nur für historische Daten zu nutzen.

## Informationen zu den Vor- und Nachteile der ausschließlichen Verwendung des Analytics-Quell-Connectors

Informationen zu den Vor- und Nachteilen der Verwendung des Analytics-Quell-Connectors finden Sie unter [Ausschließliches Verwenden des Analytics-Quell-Connectors für das Upgrade auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Wechsel vom Analytics-Quell-Connector zum Web-SDK

Im Folgenden finden Sie den allgemeinen Prozess für den Wechsel von der ausschließlichen Verwendung des Analytics-Quell-Connectors zu einer Implementierung, die sowohl den Analytics-Quell-Connector als auch eine Web-SDK-Implementierung umfasst:

1. Erstellen Sie eine Web-SDK-Implementierung, wie unter [Detaillierte empfohlene Upgrade-Schritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) im Artikel [Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) beschrieben.

   Nachdem Sie die Web-SDK-Implementierung konfiguriert haben, fahren Sie mit den folgenden Schritten fort.

1. [Erstellen Sie ein XDM-Schema für den Analytics-Quell-Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Ordnen Sie jede Adobe Analytics-Dimension aus Ihrem Analytics-Quell-Connector der Dimension im Web-SDK-Schema zu.

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
