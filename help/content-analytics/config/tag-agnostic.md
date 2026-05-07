---
title: Content Analytics Tags-agnostische Konfiguration
description: Erfahren Sie, wie Sie Content Analytics ohne Verwendung von Datenerfassungs-Tags in Experience Platform konfigurieren.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
source-git-commit: 64b96d8b0917975f19c353e26d9e6437d1b4e5ac
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 5%

---


# Agnostische Konfiguration für Content Analytics Tags

Die Adobe Content Analytics JavaScript-Bibliothek ermöglicht das Tracking von inhaltsbezogenen Ereignissen auf Websites, indem Inhaltsdaten über die Experience Platform Edge Network an Adobe Experience Platform gesendet werden. Verwenden Sie diese Bibliothek, wenn Sie Content Analytics ohne Adobe Experience Platform-Tags (Launch) implementieren möchten.

>[!NOTE]
>
>Dieser Artikel gilt für Content Analytics für den Web-Kanal.


>[!PREREQUISITES]
>
>Adobe Experience Platform Web SDK (Alloy) muss auf der Seite initialisiert werden, bevor `initializeContentLibrary` aufgerufen wird.

## Installation

Sie können die Bibliothek auf zwei Arten installieren:

### npm-Paket

Installieren Sie die Bibliothek mithilfe von `npm`.

1. Verwenden Sie in der Befehlszeile:

   ```bash
   npm install @adobe/content-analytics
   ```

1. Bibliothek importieren:

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### Skript-Tag (CDN)

Laden Sie die Bibliothek direkt vom CDN.

1. Initialisieren Sie die [Web SDK JavaScript-Bibliothek](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library) und laden Sie das Content Analytics-Bundle:

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   wobei
   * `alloy/2.x.x` bezieht sich auf die Version, die Sie mit der [Web SDK JavaScript Library) verwenden &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library).
   * `content-analytics/1.x.x` bezieht sich auf die Version, die Sie mit der Content Analytics SDK-Bibliothek verwenden möchten.

2. Der eigenständige Build stellt `window.contentAnalytics` als Initialisierungsfunktion bereit.


## Datenstromkonfiguration

Die `datastreamId` ist erforderlich und muss auf einen Datenstrom verweisen, bei dem der Experience Platform-Service mit einem aktivierten Content Analytics-Erlebnisereignis-Datensatz konfiguriert ist. Stellen Sie sicher, dass die mit dem Datenstrom verknüpfte Sandbox nicht bereits mit einer anderen Content Analytics-Einrichtung verknüpft ist.

Sie können für jede Umgebung separate Datenstrom-IDs bereitstellen:

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Erlebniserfassung und -definition

Erlebnis-Tracking aktivieren und steuern, wie Erlebnisse auf Ihrer Website identifiziert werden. Erlebnisse werden durch die Kombination eines **regulären Ausdrucks der Domain** mit optionalen **Abfrageparametern** die innerhalb übereinstimmender Seiten ein Erlebnis von einem anderen unterscheiden, definiert.

| Option | Typ | Standard | Beschreibung |
|--------|------|---------|-------------|
| `includeExperiences` | boolean | `false` | Seiten-/Erlebnisansichts-Tracking aktivieren |
| `experienceConfigurations` | array | - | Erlebnisse nach Domain-Regex- und Abfrageparametern definieren |

Jeder Eintrag in `experienceConfigurations` akzeptiert:

| Eigenschaft | Typ | Beschreibung |
|----------|------|-------------|
| `regEx` | string | Regulärer Ausdruck der Domain, der mit der Seiten-URL abgeglichen wird (z. B. `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | array | Namen von Abfrageparametern, deren Werte Erlebnisse auf übereinstimmenden Seiten unterscheiden (z. B. `["outdoors", "patio", "kitchen"]`) |

### Beispiel

Unten finden Sie ein Beispiel dafür, wie Sie das Erlebnis-Tracking mit Domain-Regex- und Abfrageparametern aktivieren.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## Ereignisfilterung

Steuern Sie mithilfe regulärer Ausdrücke, welche Seiten-URLs und Asset-URLs in die Datenerfassung eingeschlossen werden. Verwenden Sie die folgenden Musterbeispiele als Ausgangspunkt und validieren Sie die Muster vor der Bereitstellung mit einem Regex-Tester.

| Option | Typ | Standard | Beschreibung |
|--------|------|---------|-------------|
| `pageUrlQualifier` | Zeichenfolge (Regex) | - | Nur Seiten verfolgen, deren URL diesem Muster entspricht |
| `assetUrlQualifier` | Zeichenfolge (Regex) | - | Nur Assets verfolgen, deren URL diesem Muster entspricht |
| `excludeURLsFromTracking` | array | `[]` | Liste der vom Tracking auszuschließenden URL-Zeichenfolgen |

### Beispiel

Unten finden Sie ein Beispiel dafür, wie Sie Dokumentationsseiten aus Content Analytics ausschließen und nur Produktbilder für Content Analytics berücksichtigen können.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```

>[!NOTE]
>
>Nachdem eine Content Analytics-Konfiguration in der Benutzeroberfläche [Geführte Konfiguration](/help/content-analytics/config/guided.md) eingerichtet wurde, sind die konfigurationsspezifischen JavaScript-Einstellungen in dieser Konfigurationsansicht verfügbar.

