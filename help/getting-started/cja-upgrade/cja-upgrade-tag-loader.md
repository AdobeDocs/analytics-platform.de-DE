---
title: Implementieren des Loader-Tags für die Web-SDK-Erweiterung
description: Erfahren Sie, wie Sie das Loader-Tag für die Web-SDK-Erweiterung implementieren
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '283'
ht-degree: 100%

---

# Implementieren des Loader-Tags für die Web-SDK-Erweiterung {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Loader-Tag auf Ihrer Site implementieren"
>abstract="Arbeiten Sie mit Ihrem Website-Entwicklungs-Team zusammen, um das Loader-Tag auf jeder Seite Ihrer Site zu installieren.<br><br>Der Fertigstellungszeitpunkt für diese Aufgabe hängt stark von der Reaktionszeit des Engineering-Teams ab, mit dem Sie den Code bereitstellen. Einige Organisationen mit sehr anpassungsfähigen Engineering-Teams können diesen Schritt in Tagen abschließen, während Entwicklungsteams mit einem umfangreichen Aufgabenrückstand möglicherweise einen Monat oder länger benötigen."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Sie müssen Ihr Tag auf der Website installieren, die Sie verfolgen möchten. Das heißt, Sie müssen Code in das Header-Tag der Vorlage Ihrer Website einfügen.

Im folgenden Prozess wird beschrieben, wie Sie den Code abrufen, der auf Ihr Tag verweist. Ergänzende Informationen finden Sie in den [Implementierungshandbüchern für Tags und Ereignisweiterleitung](https://experienceleague.adobe.com/de/docs/experience-platform/tags/get-started/implementation-guides) in der Dokumentation zu Experience Platform.

Gehen Sie folgendermaßen vor, um Code abzurufen, der auf Ihr Tag verweist:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei experiencecloud.adobe.com an.

1. Navigieren Sie in Adobe Experience Platform zu **[!UICONTROL Datenerfassung]** > **[!UICONTROL Tags]**.

1. Wählen Sie auf der Seite **[!UICONTROL Tag-Eigenschaften]** das neu erstellte Tag aus der Liste der Eigenschaften aus, um es zu öffnen.

1. Wählen Sie **[!UICONTROL Umgebungen]** in der linken Leiste aus.

1. Wählen Sie in der Umgebungsliste die jeweilige Installieren-Schaltfläche (Kästchen) aus.

   Wählen Sie im Dialog [!UICONTROL Web-Installationsanleitung] die Schaltfläche „Kopieren“ neben dem Skriptcode aus, der wie folgt aussehen sollte:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Umgebung](assets/environment.png)

1. Wählen Sie **[!UICONTROL Schließen]** aus.

   Anstelle des Codes für die Entwicklungsumgebung hätten Sie auch eine andere Umgebung (Staging, Produktion) auswählen können, je nachdem, wo Sie das Adobe Experience Platform Web SDK bereitstellen möchten.

   Weitere Informationen finden Sie in [Umgebungen](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=de?).

{{upgrade-final-step}}
