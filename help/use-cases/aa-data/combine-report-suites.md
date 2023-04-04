---
title: Kombinieren von Report Suites mit verschiedenen Schemata
description: Erfahren Sie, wie Sie mithilfe der Datenvorbereitung Report Suites mit verschiedenen Schemata kombinieren
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: ht
source-wordcount: '1335'
ht-degree: 100%

---

# Kombinieren von Report Suites mit verschiedenen Schemata

Der [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) bringt Report Suite-Daten aus Adobe Analytics in Adobe Experience Platform (AEP) zur Verwendung durch AEP-Programme wie Real-time Customer Data Platform und Customer Journey Analytics (CJA). Jede Report Suite, die in AEP importiert wird, wird als Datenfluss der individuellen Quellverbindung konfiguriert, und jeder Datenfluss gelangt als Datensatz in den Data Lake von AEP. Der Analytics-Quell-Connector erstellt einen Datensatz pro Report Suite.

CJA-Kundinnen und Kunden verwenden [Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de), um Datensätze aus dem Data Lake von AEP in Analysis Workspace von CJA zu integrieren. Wenn Sie jedoch Report Suites innerhalb einer Verbindung kombinieren, müssen Schemaunterschiede zwischen Report Suites mithilfe der Funktionalität [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) von AEP aufgelöst werden. Damit soll sichergestellt werden, dass Adobe Analytics-Variablen wie Props und eVars in CJA eine einheitliche Bedeutung haben.

## Schemaunterschiede zwischen Report Suites sind problematisch

Angenommen, Ihre Firma möchte Daten aus zwei verschiedenen Report Suites in AEP zur Verwendung durch CJA importieren und geht davon aus, dass die Schemata für die beiden Report Suites Unterschiede aufweisen:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 = Suchbegriff | eVar1 = Geschäftseinheit |
| eVar2 = Kundenkategorie | eVar2 = Suchbegriff |

Sagen wir aus Gründen der Einfachheit, dass dies die einzigen definierten eVars für beide Report Suites sind.

Angenommen, Sie führen nun die folgenden Aktionen durch:

- Sie erstellen eine Analytics-Quellverbindung (ohne Verwendung der Datenvorbereitung), die die **Report Suite A** als **Datensatz A** in den Data Lake von AEP aufnimmt.
- Sie erstellen eine Analytics-Quellverbindung (ohne Verwendung der Datenvorbereitung), die die **Report Suite B** als **Datensatz B** in den Data Lake von AEP aufnimmt.
- Sie erstellen eine [CJA-Verbindung](/help/connections/create-connection.md) namens **Alle Report Suites**, die Datensatz A und Datensatz B kombiniert.
- Sie erstellen eine [CJA-Datenansicht](/help/data-views/create-dataview.md) namens **Globale Ansicht**, die auf der Verbindung „Alle Report Suites“ basiert.

Ohne die Verwendung der Datenvorbereitung zur Auflösung der Schemaunterschiede zwischen Datensatz A und Datensatz B enthalten die eVars in der Datenansicht der globalen Ansicht eine Mischung aus Werten:

| Datenansicht der globalen Ansicht in CJA |
| --- |
| eVar1 => eine Mischung aus Suchbegriffen und Geschäftseinheiten |
| eVar2 => eine Mischung aus Kundenkategorien und Suchbegriffen |

Dies führt zu sinnlosen Berichten für eVar1 und eVar2:

- Die eVar-Felder enthalten eine Mischung aus Werten mit unterschiedlicher semantischer Bedeutung.
- Suchbegriffe werden zwischen eVar1 und eVar2 verteilt.
- Es ist nicht möglich, verschiedene Attributionsmodelle für die einzelnen Suchbegriffe, Geschäftseinheiten und Kundenkategorien zu verwenden.

## Verwenden der AEP-Datenvorbereitung, um Schemaunterschiede zwischen Report Suites zu beheben

Die Datenvorbereitungs-Funktion von Experience Platform ist in den Analytics-Quell-Connector integriert und kann verwendet werden, um die im obigen Szenario beschriebenen Schemaunterschiede zu beheben. Dies führt zu eVars mit konsistenter Bedeutung in der CJA-Datenansicht. (Die unten verwendeten Benennungskonventionen können Ihren Bedürfnissen entsprechend angepasst werden.)

1. Bevor Sie die Datenflüsse für die Quellverbindung für Report Suite A und Report Suite B erstellen, [erstellen Sie ein neues Schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=de) in AEP (nennen wir es in unserem Beispiel **Einheitliches Schema**.) Fügen Sie Folgendes zu diesem Schema hinzu:

   | „Einheitliches Schema“ |
   | --- |
   | **XDM ExperienceEvent**-Klasse |
   | **Adobe Analytics ExperienceEvent-Vorlage**-Feldergruppe |

1. Fügen Sie eine weitere Feldgruppe zum Schema hinzu oder [erstellen Sie eine benutzerdefinierte Feldergruppe](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=de#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) und fügen Sie sie zum Schema hinzu. Wir erstellen eine neue Feldergruppe und nennen sie **Einheitliche Felder**. Anschließend fügen wir die folgenden Felder zur neuen Feldergruppe hinzu:

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

1. Erstellen Sie jetzt eine Verbindung des Typs **Alle Report Suites** für CJA, wobei Datensatz A und Datensatz B kombiniert werden.

1. Erstellen Sie eine Datenansicht des Typs **Globale Ansicht** in CJA. Ignorieren Sie die ursprünglichen eVar-Felder und schließen Sie nur die Felder aus der Feldergruppe „Einheitliche Felder“ ein.

   Datenansicht des Typs **Globale Ansicht** in CJA:

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
>Die benutzerdefinierte Feldergruppe „Einheitliche Felder“ und die zugehörigen Feldzuordnungen können jederzeit zu vorhandenen Datenflüssen und Datensätzen des Analytics-Quell-Connectors hinzugefügt werden. Dies wirkt sich jedoch nur auf künftige Daten aus.

## Mehr als nur Report Suites

Die Fähigkeiten der Datenvorbereitung zum Kombinieren von Datensätzen mit verschiedenen Schemata gehen über Report Suites von Analytics hinaus. Angenommen, Sie haben zwei Datensätze, die die folgenden Daten enthalten:

| Datensatz A = Report Suite von Analytics über den Analytics-Quell-Connector |
| --- |
| `eVar1` => Kundenkategorie |

| Datensatz B = Callcenter-Daten |
| --- |
| Some_field => Kundenkategorie |

Mithilfe der Datenvorbereitung können Sie die Kundenkategorie in eVar 1 der Analytics-Daten mit der Kundenkategorie in Some_field in den Callcenter-Daten kombinieren. Hier ist eine Möglichkeit, das zu tun. Auch hier kann die Namenskonvention Ihren Bedürfnissen entsprechend geändert werden.

1. Erstellen Sie ein Schema in AEP. Fügen Sie Folgendes zu diesem Schema hinzu:

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

1. Erstellen Sie eine CJA-Verbindung, die Datensatz A und Datensatz B kombiniert.

1. Erstellen Sie eine Datenansicht in CJA mithilfe der soeben erstellten CJA-Verbindung. Ignorieren Sie die ursprünglichen eVar-Felder und schließen Sie nur die Felder aus der Feldergruppe „Kundeninformationen“ ein.

   Datenansicht in CJA:

   | Quellfeld | In Datenansicht einschließen? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nein |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nein |
   | _\&lt;path>_.Customer_category | Ja |

## Datenvorbereitung vs. Komponenten-ID

Wie oben beschrieben, können Sie mithilfe der Datenvorbereitung verschiedene Felder über mehrere Report Suites in Adobe Analytics hinweg zuordnen. Dies ist in CJA hilfreich, wenn Sie Daten aus mehreren Datensätzen in einer CJA-Verbindung kombinieren möchten. Wenn Sie die Report Suites jedoch in separaten CJA-Verbindungen belassen möchten, aber einen Berichtssatz für diese Verbindungen und Datenansichten verwenden möchten, bietet eine Änderung der zugrunde liegenden Komponenten-ID in CJA eine Möglichkeit, Berichte kompatibel zu machen, selbst wenn die Schemata unterschiedlich sind. Siehe [Komponenteneinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=de) für weitere Informationen.

Das Ändern der Komponenten-ID ist eine Funktion, die nur CJA betrifft, und hat keine Auswirkungen auf Daten aus dem Analytics-Quell-Connector, die an das Echtzeit-Kundenprofil und die RTCDP gesendet werden.