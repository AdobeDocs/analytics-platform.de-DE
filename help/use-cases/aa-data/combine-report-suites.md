---
title: Kombinieren von Report Suites mit verschiedenen Schemata
description: Erfahren Sie, wie Sie mithilfe der Datenvorbereitung Report Suites mit verschiedenen Schemata kombinieren
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 57%

---

# Kombinieren von Report Suites mit verschiedenen Schemata

Die [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) bringt Report Suite-Daten aus Adobe Analytics zur Verwendung durch Adobe Experience Platform-Anwendungen wie Real-time Customer Data Platform und Customer Journey Analytics (Customer Journey Analytics) in die Adobe Experience Platform. Jede Report Suite, die in Adobe Experience Platform eingebunden wird, wird als Datenfluss der individuellen Quellverbindung konfiguriert und jeder Datenfluss wird als Datensatz im Adobe Experience Platform Data Lake landet. Der Analytics-Quell-Connector erstellt einen Datensatz pro Report Suite.

Customer Journey Analytics-Kunden verwenden [Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de) , um Datensätze aus dem Adobe Experience Platform Data Lake in Customer Journey Analytics Analysis Workspace zu integrieren. Wenn Sie jedoch Report Suites innerhalb einer Verbindung kombinieren, müssen Schemaunterschiede zwischen Report Suites mithilfe von Adobe Experience Platform behoben werden [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) Funktionalität. Dadurch soll sichergestellt werden, dass Adobe Analytics-Variablen wie Props und eVars eine einheitliche Bedeutung im Customer Journey Analytics haben.

## Schemaunterschiede zwischen Report Suites sind problematisch

Angenommen, Ihr Unternehmen möchte Daten aus zwei verschiedenen Report Suites zur Verwendung durch Customer Journey Analytics in Adobe Experience Platform importieren und geht davon aus, dass die Schemata für die beiden Report Suites unterschiedlich sind:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 = Suchbegriff | eVar1 = Geschäftseinheit |
| eVar2 = Kundenkategorie | eVar2 = Suchbegriff |

Sagen wir aus Gründen der Einfachheit, dass dies die einzigen definierten eVars für beide Report Suites sind.

Angenommen, Sie führen nun die folgenden Aktionen durch:

- Erstellen einer Analytics-Quellverbindung (ohne Verwendung von Data Prep), die erfasst **Report Suite A** in Adobe Experience Platform Data Lake als **Datensatz A**.
- Erstellen einer Analytics-Quellverbindung (ohne Verwendung von Data Prep), die erfasst **Report Suite B** in Adobe Experience Platform Data Lake als **Datensatz B**.
- Erstellen Sie eine [Customer Journey Analytics-Verbindung](/help/connections/create-connection.md) aufgerufen **Alle Report Suites** , der Datensatz A und Datensatz B kombiniert.
- Erstellen Sie eine [Customer Journey Analytics-Datenansicht](/help/data-views/create-dataview.md) aufgerufen **Globale Ansicht** , der auf der Verbindung Alle Report Suites basiert.

Ohne die Verwendung der Datenvorbereitung zur Auflösung der Schemaunterschiede zwischen Datensatz A und Datensatz B enthalten die eVars in der Datenansicht der globalen Ansicht eine Mischung aus Werten:

| Datenansicht in der globalen Ansicht in Customer Journey Analytics |
| --- |
| eVar1 => eine Mischung aus Suchbegriffen und Geschäftseinheiten |
| eVar2 => eine Mischung aus Kundenkategorien und Suchbegriffen |

Dies führt zu sinnlosen Berichten für eVar1 und eVar2:

- Die eVar-Felder enthalten eine Mischung aus Werten mit unterschiedlicher semantischer Bedeutung.
- Suchbegriffe werden zwischen eVar1 und eVar2 verteilt.
- Es ist nicht möglich, verschiedene Attributionsmodelle für die einzelnen Suchbegriffe, Geschäftseinheiten und Kundenkategorien zu verwenden.

## Adobe Experience Platform-Datenvorbereitung verwenden, um Schemaunterschiede zwischen Report Suites zu beheben

Die Experience Platform Data Prep-Funktion ist in den Analytics-Quell-Connector integriert und kann verwendet werden, um die im obigen Szenario beschriebenen Unterschiede beim Schema zu beheben. Dies führt zu eVars mit konsistenter Bedeutung in der Customer Journey Analytics-Datenansicht. (Die unten verwendeten Benennungskonventionen können Ihren Bedürfnissen entsprechend angepasst werden.)

1. Bevor Sie die Datenflüsse für die Quellverbindung für Report Suite A und Report Suite B erstellen, [Neues Schema erstellen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=de) in Adobe Experience Platform (nennen wir es **Einheitliches Schema** in unserem Beispiel.) Fügen Sie Folgendes zu diesem Schema hinzu:

   | „Einheitliches Schema“ |
   | --- |
   | **XDM ExperienceEvent**-Klasse |
   | **Adobe Analytics ExperienceEvent-Vorlage**-Feldergruppe |

1. Fügen Sie eine weitere Feldgruppe zum Schema hinzu oder [erstellen Sie eine benutzerdefinierte Feldergruppe](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) und fügen Sie sie zum Schema hinzu. Wir erstellen eine neue Feldergruppe und nennen sie **Einheitliche Felder**. Anschließend fügen wir die folgenden Felder zur neuen Feldergruppe hinzu:

   | Benutzerdefinierte Feldergruppe „Einheitliche Felder“  |
   | --- |
   | Suchbegriff |
   | Geschäftseinheit |
   | Kundenkategorie |

1. Erstellen Sie den Datenfluss der Quellverbindung für **Report Suite A**, wobei Sie **Einheitliches Schema** zur Verwendung im Datenfluss auswählen. Fügen Sie benutzerdefinierte Zuordnungen wie folgt zum Datenfluss hinzu:

   | Quellfeld von Report Suite A | Zielfeld aus der Feldergruppe „Einheitliche Felder“ |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >Der XDM-Pfad für Ihre Zielfelder hängt davon ab, wie Sie Ihre benutzerdefinierte Feldergruppe strukturieren.

1. Erstellen Sie den Datenfluss der Quellverbindung für **Report Suite B**, wobei Sie erneut **Einheitliches Schema** zur Verwendung im Datenfluss auswählen. Der Workflow zeigt an, dass zwei Felder einen Konflikt mit dem Deskriptornamen aufweisen. Der Grund dafür ist, dass sich die Deskriptoren für eVar1 und eVar2 in Report Suite B von denen in Report Suite A unterscheiden. Wir wissen dies jedoch bereits, sodass wir den Konflikt ignorieren und benutzerdefinierte Zuordnungen wie folgt verwenden können:

   | Quellfeld von Report Suite B | Zielfeld aus der Feldergruppe „Einheitliche Felder“ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Erstellen Sie jetzt eine **Alle Report Suites** Verbindung für Customer Journey Analytics, indem Datensatz A und Datensatz B kombiniert werden.

1. Erstellen Sie eine **Globale Ansicht** Datenansicht in Customer Journey Analytics. Ignorieren Sie die ursprünglichen eVar-Felder und schließen Sie nur die Felder aus der Feldergruppe „Einheitliche Felder“ ein.

   **Globale Ansicht** Datenansicht in Customer Journey Analytics:

   | Quellfeld | In Datenansicht einschließen? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nein |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nein |
   | _\&lt;path>_.Search_term | Ja |
   | _\&lt;path>_.Customer_category  | Ja |
   | _\&lt;path>_.Business_unit | Ja |

Sie haben nun die eVar1 und eVar2 aus den Quell-Report Suites drei neuen Feldern zugeordnet. Beachten Sie, dass ein weiterer Vorteil der Verwendung der Datenvorbereitung darin besteht, dass die Zielfelder jetzt auf semantisch aussagekräftigen Namen (Suchbegriff, Geschäftseinheit, Kundenkategorie) statt auf den weniger aussagekräftigen eVar-Namen (eVar1, eVar2) basieren.

>[!NOTE]
>
>Die benutzerdefinierte Feldergruppe &quot;Unified Fields&quot;und die zugehörigen Feldzuordnungen können vorhandenen Datenflüssen und Datensätzen des Analytics-Quell-Connectors jederzeit hinzugefügt werden. Dies wirkt sich jedoch nur auf künftige Daten aus.

## Mehr als nur Report Suites

Die Fähigkeiten der Datenvorbereitung zum Kombinieren von Datensätzen mit verschiedenen Schemata gehen über Report Suites von Analytics hinaus. Angenommen, Sie haben zwei Datensätze, die die folgenden Daten enthalten:

| Datensatz A = Analytics-Report Suite über Analytics-Quell-Connector |
| --- |
| `eVar1` => Kundenkategorie |

| Datensatz B = Callcenter-Daten |
| --- |
| Some_field => Kundenkategorie |

Mithilfe der Datenvorbereitung können Sie die Kundenkategorie in eVar 1 der Analytics-Daten mit der Kundenkategorie in Some_field in den Callcenter-Daten kombinieren. Hier ist eine Möglichkeit, das zu tun. Auch hier kann die Namenskonvention Ihren Bedürfnissen entsprechend geändert werden.

1. Erstellen Sie ein Schema in Adobe Experience Platform. Fügen Sie Folgendes zu diesem Schema hinzu:

   | „Erweitertes Schema“ |
   | --- | 
   | **XDM-Erlebnisereignis**-Klasse |
   | Feldergruppe **Adobe Analytics-Erlebnisereignisvorlage** |

1. Erstellen Sie eine neue Feldergruppe und fügen Sie sie zum Schema hinzu. Fügen Sie Felder zur Feldergruppe hinzu:

   | Benutzerdefinierte Feldergruppe „Kundeninformationen“  |
   | --- |
   | Customer_category |

1. Erstellen Sie den Datenfluss für **Datensatz A**, wobei Sie **Erweitertes Schema** als Schema auswählen. Fügen Sie benutzerdefinierte Zuordnungen wie folgt zum Datenfluss hinzu:

   | Quellfeld von Datensatz A | Zielfeld aus der Feldergruppe „Kundeninformationen“ |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Erstellen Sie den Datenfluss für **Datensatz B**, wobei Sie erneut **Erweitertes Schema** als Schema auswählen. Fügen Sie benutzerdefinierte Zuordnungen wie folgt zum Datenfluss hinzu:

   | Quellfeld für Datensatz B | Zielfeld aus der Feldergruppe „Kundeninformationen“ |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. Erstellen Sie eine Customer Journey Analytics-Verbindung, die Datensatz A und Datensatz B kombiniert.

1. Erstellen Sie eine Datenansicht in Customer Journey Analytics mithilfe der soeben erstellten Customer Journey Analytics-Verbindung. Ignorieren Sie die ursprünglichen eVar-Felder und schließen Sie nur die Felder aus der Feldergruppe „Kundeninformationen“ ein.

   Datenansicht unter Customer Journey Analytics:

   | Quellfeld | In Datenansicht einschließen? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nein |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nein |
   | _\&lt;path>_.Customer_category | Ja |

## Datenvorbereitung vs. Komponenten-ID

Wie oben beschrieben, können Sie mithilfe der Datenvorbereitung verschiedene Felder über mehrere Report Suites in Adobe Analytics hinweg zuordnen. Dies ist beim Customer Journey Analytics hilfreich, wenn Sie Daten aus mehreren Datensätzen zu einer Customer Journey Analytics-Verbindung kombinieren möchten. Wenn Sie die Report Suites jedoch in separaten Customer Journey Analytics-Verbindungen halten möchten, aber ein Berichtssatz für diese Verbindungen und Datenansichten verwenden möchten, bietet eine Änderung der zugrunde liegenden Komponenten-ID in Customer Journey Analytics eine Möglichkeit, Berichte kompatibel zu machen, selbst wenn es sich um andere Schemata handelt. Siehe [Komponenteneinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html) für weitere Informationen.

Das Ändern der Komponenten-ID ist eine Nur-Customer Journey Analytics-Funktion und hat keine Auswirkungen auf Daten aus dem Analytics-Quell-Connector, der an das Echtzeit-Kundenprofil und die RTCDP gesendet wird.
