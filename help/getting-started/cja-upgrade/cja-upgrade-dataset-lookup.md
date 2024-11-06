---
title: Erstellen eines Schemas für Customer Journey Analytics
description: Erfahren Sie mehr über den empfohlenen Pfad bei der Aktualisierung von Adobe Analytics auf Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Erstellen von Lookup-Datensätzen zum Klassifizieren von Daten im Customer Journey Analytics

>[!NOTE]
> 
>Führen Sie die Schritte auf dieser Seite erst aus, nachdem Sie alle vorherigen Aktualisierungsschritte ausgeführt haben. Sie können die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ausführen oder die für Ihr Unternehmen dynamisch generierten Aktualisierungsschritte mit dem Fragebogen [Adobe Analytics to Customer Journey Analytics Upgrade Fragenkatalog](https://gigazelle.github.io/cja-ttv/) ausführen.
>
>Nachdem Sie die Schritte auf dieser Seite ausgeführt haben, fahren Sie mit den empfohlenen Aktualisierungsschritten oder den dynamisch generierten Aktualisierungsschritten fort.

Ähnlich wie Klassifizierungsdaten in Adobe Analytics sind Lookup-Datensätze die Methode zum Klassifizieren von Daten in Customer Journey Analytics.

Bei Verwendung des Analytics-Quell-Connectors werden einige standardmäßige Lookup-Datensätze automatisch zur Berichtszeit angewendet. Weitere Informationen finden Sie unter [Hinzufügen von Standardsuchvorgängen zu Datensätzen](/help/connections/standard-lookups.md).

Um Daten mit einer neuen Implementierung des Experience Platform Web SDK zu klassifizieren, müssen Sie einen Lookup-Datensatz für jede Dimension erstellen, die Daten enthält, die Sie klassifizieren möchten.

So erstellen Sie Lookup-Datensätze zur Verwendung in Customer Journey Analytics:

1. Erstellen Sie in AEP ein neues Schema. Dies ist ein neues Schema, das speziell für Lookup-Datensätze gilt. Sie können kein vorhandenes Schema verwenden.

1. Sie müssen eine neue Schemaklasse erstellen, die für Suchen verwendet wird.

1. Erstellen Sie einen Lookup-Datensatz davon.

1. Führen Sie die [empfohlenen Aktualisierungsschritte](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oder die dynamisch generierten Aktualisierungsschritte](https://gigazelle.github.io/cja-ttv/) aus.[
