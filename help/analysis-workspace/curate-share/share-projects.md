---
description: Projektfreigabe und Projektrollen in Workspace
keywords: Analysis Workspace-Freigabe
title: Freigeben von Projekten
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1966'
ht-degree: 34%

---

# Freigeben von Projekten

Sie können ein Analysis Workspace-Projekt für die folgenden Personentypen freigeben:

* Benutzer und Gruppen in Ihrem Unternehmen, die Zugriff auf Adobe Customer Journey Analytics haben

  Sie können den Zugriff &quot;Bearbeiten&quot;, &quot;Duplizieren&quot;oder &quot;Anzeigen&quot;freigeben

* Benutzer und Gruppen in Ihrer Organisation, die keinen Zugriff auf Customer Journey Analytics haben

  Empfänger haben schreibgeschützten Zugriff

* Personen außerhalb Ihrer Organisation

  Empfänger haben schreibgeschützten Zugriff

Alle [Kuratierung](curate.md) Sie vor der Freigabe beantragen, wird beim Öffnen des Projekts durch die Empfänger angezeigt.

Im Folgenden finden Sie eine Videoübersicht zur gemeinsamen Nutzung von Projekten:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Freigeben für Customer Journey Analytics-Benutzer und -Gruppen in Ihrer Organisation {#Add}

Sie können ein Projekt für bestehende Customer Journey Analytics-Benutzer oder -Gruppen in Ihrem Unternehmen freigeben. Wenn Sie ein Projekt wie in diesem Abschnitt beschrieben freigeben, müssen die Benutzer, für die Sie freigeben, bereits über ein Customer Journey Analytics-Konto verfügen.

Sie können eine bestimmte Rolle für Benutzende oder Gruppen freigeben oder einen Link freigeben.

* [Freigeben einer bestimmten Projektrolle](#share-a-specific-project-role)

* [Freigeben eines Links zu einem Projekt](#share-a-link-to-a-project)

## Freigeben einer bestimmten Projektrolle

Beachten Sie beim Freigeben einer bestimmten Projektrolle für Benutzende und Gruppen in Ihrer Organisation Folgendes:

* Projektrollen (**[!UICONTROL Original bearbeiten]**, **[!UICONTROL Kopie bearbeiten]**, und **[!UICONTROL Schreibgeschützt]**) sind an den Benutzer und die spezifische Projekt-ID gebunden. Projektrollen sind unabhängig von Benutzerberechtigungen, die in der [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=de) verwaltet werden.

* Unter Customer Journey Analytics werden Gruppen durch Produktprofile im [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=de). Die von Administrierenden durchgeführte Freigabe ist für jede Gruppe möglich, einschließlich „Alle“. Nichtadministrierende können Freigaben für Gruppen durchführen, denen sie angehören (mit Ausnahme von „Alle“).

* Benutzende, denen mehrere Rollen zugewiesen sind, erhalten immer die maximale Berechtigung. Dies kann vorkommen, wenn Benutzende sowohl als Einzelpersonen als auch als Gruppenmitglieder hinzugefügt werden. Wenn einem Benutzer beispielsweise die Variable **[!UICONTROL Original bearbeiten]** Rolle als Einzelperson und **[!UICONTROL Schreibgeschützt]** Als Mitglied einer Gruppe erhalten sie eine **[!UICONTROL Original bearbeiten]** Projekterlebnis.

* Administratoren, die im **[!UICONTROL Kopie bearbeiten]** oder **[!UICONTROL Schreibgeschützt]** Rolle erhält diese eingeschränkten Erlebnisse beim Öffnen eines Projekts. Ein Administrator kann seine Rolle in **[!UICONTROL Original bearbeiten]** indem Sie das Projekt für sich selbst freigeben und die Rolle &quot;Bearbeiten&quot;zuweisen, wie im folgenden Verfahren beschrieben.

So geben Sie eine bestimmte Projektrolle für Benutzende oder Gruppen in Ihrer Organisation frei:

1. Wechseln Sie zu dem Projekt, das Sie freigeben möchten, und klicken Sie dann auf **[!UICONTROL Freigeben]** > **[!UICONTROL Freigeben für Workspace-Benutzer]**.
Wenn nicht gespeicherte Änderungen vorhanden sind, werden Sie aufgefordert, Ihr Projekt zuerst zu speichern.

   ![Das Fenster Projekt freigeben .](assets/share-proj-modal.png)

   Informationen dazu, wie Sie mehrere Projekte gleichzeitig freigeben, finden Sie unter [Freigeben von Projekten im Projekt-Manager](#share-projects-in-the-project-manager).

1. Fügen Sie Empfänger und Empfängerinnen oder Empfängergruppen in eines der angegebenen Rollenfelder hinzu:

   **Original bearbeiten:** Empfänger können **[!UICONTROL Speichern]** Änderungen an einem Projekt vornehmen und als Miteigentümer fungieren. Diese Rolle ist nützlich, wenn Sie ein Projekt mit anderen Kollegen gemeinsam verwalten möchten. Dazu gehören das Bearbeiten, Löschen und Bearbeiten von Empfängerlisten für ein freigegebenes Projekt. <br>Hinweis: Analysis Workspace unterstützt derzeit keine Live-Zusammenarbeit. Es wird daher empfohlen, dass zu jedem Zeitpunkt nur ein Benutzer ein Projekt bearbeitet. Wenn Projekte zum gleichen Zeitpunkt gespeichert werden, wird die letzte Version beibehalten.

   **Kopie bearbeiten:** Empfänger können **[!UICONTROL Speichern unter]** und haben Zugriff auf die linke Leiste. Projektinteraktionen sind in dieser Rolle nicht beschränkt. Diese Rolle ist nützlich, wenn Sie ein Projekt für Benutzende freigeben möchten, die mit der Datennutzung in Ihrem Unternehmen und der Verwendung von Analysis Workspace vertraut sind, Ihr Projekt jedoch nicht geändert werden soll.

   **Schreibgeschützt:** Empfänger können **[!UICONTROL Speichern]** oder **[!UICONTROL Speichern unter]** und keinen Zugriff auf die linke Leiste haben. Auch die Projektinteraktionen sind begrenzt. Diese Rolle ist nützlich, wenn Sie ein Projekt für Benutzer freigeben möchten, die mit der Datenstruktur Ihres Unternehmens, Analysis Workspace oder Customer Journey Analytics im Allgemeinen weniger vertraut sind. Sie möchten jedoch, dass sie Daten und Erkenntnisse in einer sicheren Umgebung einsehen können. Weitere Informationen zum [Schreibgeschütztes Projekterlebnis](/help/analysis-workspace/curate-share/view-only-projects.md).

1. Wählen Sie aus, ob beim Freigeben des Projekts die folgenden Optionen aktiviert werden sollen:

   * **Freigeben eingebetteter Projektkomponenten:** Gibt Filter, berechnete Metriken und Datumsbereiche für alle Empfänger frei. Nach der Freigabe werden diese Komponenten im Dropdown-Menü „Komponenten“ im Arbeitsbereich des Empfängers bzw. der Empfängerin angezeigt. Diese Einstellung wird nicht beibehalten. Es handelt sich um eine einmalige Aktion zum Zeitpunkt der Freigabe.

   * **Als Landingpage für Empfänger und Empfängerinnen festlegen:** Legt diese Seite als Landingpage für Empfänger und Empfängerinnen fest. Diese Einstellung wird nicht beibehalten. Es handelt sich um eine einmalige Aktion zum Zeitpunkt der Freigabe.

1. Klicken Sie auf **[!UICONTROL Freigabe]**. (Wenn das Projekt bereits freigegeben wurde, klicken Sie auf [!UICONTROL **Aktualisieren**].

   Oder

   Klicks **[!UICONTROL Kuratieren und freigeben]** , um die Projektkuratierung automatisch anzuwenden. (Wenn das Projekt bereits freigegeben wurde, klicken Sie auf **[!UICONTROL Kuratieren und aktualisieren]**. Weitere Informationen zur [Projektkuratierung](curate.md).

## Freigeben eines Links zu einem Projekt

Beachten Sie bei der Freigabe eines Links, wie in diesem Abschnitt beschrieben, Folgendes:

* Empfänger, die den Link verwenden, müssen sich bei Customer Journey Analytics anmelden, bevor sie Zugriff auf das Projekt erhalten.

* Wenn Empfängern oder Empfängerinnen keine Rolle zugewiesen wurde und sie einen [Link](/help/analysis-workspace/curate-share/shareable-links.md) zum Projekt erhalten (**[!UICONTROL Freigeben] > [!UICONTROL Projekt-Link abrufen]**), wird ihnen standardmäßig eine Rolle zugewiesen. Administratoren erhalten **[!UICONTROL Original bearbeiten]** und Nicht-Administratoren erhalten **[!UICONTROL Kopie bearbeiten]**.

So geben Sie den Projekt-Link für Benutzende in Ihrer Organisation frei:

1. Speichern Sie das Projekt. Wenn nicht gespeicherte Änderungen vorhanden sind, werden Sie aufgefordert, Ihr Projekt zu speichern, bevor Sie einen Link freigeben.

1. Auswählen **[!UICONTROL Freigeben]** > **[!UICONTROL Freigeben für Workspace-Benutzer]**, wählen Sie **[!UICONTROL Kopieren]** neben dem **[!UICONTROL Über Link freigeben]** -Feld.

   ![Das Projekt Freigabe , das das Feld Freigabe nach Link hervorhebt.](assets/share-proj-modal.png)

1. Geben Sie den Link für Benutzende in Ihrer Organisation frei. Sie können ihn beispielsweise in eine E-Mail oder eine interne Website usw. einfügen.

## Projekt für andere freigeben (keine Anmeldung erforderlich) {#share-public-link}

Sie können [Schreibgeschützter Zugriff](/help/analysis-workspace/curate-share/view-only-projects.md) für Analysis Workspace-Projekte für Personen, die keinen Zugriff auf Customer Journey Analytics haben. Dies kann Folgendes umfassen:

* Personen außerhalb Ihrer Organisation

* Personen in Ihrer Organisation, die keinen Zugriff auf Customer Journey Analytics haben

>[!NOTE]
>
>Beachten Sie Folgendes bei der Freigabe eines Analysis Workspace-Projekts für Personen, die keinen Zugriff auf Customer Journey Analytics haben:
>
>* Die Möglichkeit, ein Projekt auf diese Weise freizugeben, kann vom Customer Journey Analytics-Administrator deaktiviert werden, wie unter [Voreinstellungen](/help/analysis-workspace/user-preferences.md). Wenn Sie ein Projekt nicht wie in diesem Abschnitt beschrieben freigeben können, hat Ihr Customer Journey Analytics-Administrator diese Funktion deaktiviert.
>
>* Projekte mit mehr als 50 erweiterten Visualisierungen können nicht für Personen freigegeben werden, die keinen Zugriff auf Customer Journey Analytics haben.
>
>* Benutzer, für die Sie freigeben, können alle Filter anzeigen, die während der [Kuratierung](curate.md).
> 
>* Benutzer, für die Sie freigeben, können den Projektdatumsbereich ändern. Der Datumsbereich, den Sie für das Projekt festgelegt haben, wird standardmäßig angezeigt.
>
>* Ein Projekt kann nicht mehr zugänglich sein, wenn viele Benutzer versuchen, gleichzeitig auf einen bestimmten Link zuzugreifen. Standardmäßig können alle 5 Minuten mehr als 190 Personen auf einen einzelnen Link zugreifen. Wenn Ihr Unternehmen diese Grenze erreicht, warten Sie 5 Minuten und versuchen Sie dann erneut, auf den Link zuzugreifen.
>
>* Wenn Ihr Unternehmen eine Lizenz für den Gesundheitsfürsorgeschild besitzt, können Sie Projekte nur für Benutzer freigeben, die sich entweder durch Single Sign On (SSO) oder Adobe ID authentifiziert haben. Sie können keine Projekte für nicht authentifizierte Benutzer freigeben. Es liegt in Ihrer Verantwortung, diese Funktion gemäß den internen Richtlinien Ihres Unternehmens zur Datenverwaltung zu verwenden und nur Projektlinks mit personenbezogenen Gesundheitsdaten (PHI) für Benutzer mit den entsprechenden Berechtigungen freizugeben.

Die folgende Videodemonstration und die zugehörige Dokumentation beschreiben die Optionen im Zusammenhang mit der Freigabe eines Links für andere:

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

So geben Sie ein Analysis Workspace-Projekt für andere frei:

1. Öffnen Sie das Analysis Workspace-Projekt, das Sie freigeben möchten.

1. Klicks **[!UICONTROL Freigeben]** > **[!UICONTROL Für alle freigeben]**.

   Wenn nicht gespeicherte Änderungen vorhanden sind, werden Sie aufgefordert, Ihr Projekt zu speichern.

   <!-- Add screen shot of new modal -->

1. Aktivieren Sie die **[!UICONTROL Link ist aktiv]** -Option, wenn sie noch nicht aktiviert ist.

   Wenn Sie diese Option auswählen, wird ein Link zum Projekt erstellt, der für alle freigegeben werden kann. Sie können den Zugriff auf das Projekt jederzeit deaktivieren, indem Sie diese Option deaktivieren.

   Der Eigentümer des Projekts ist auch Eigentümer dieses Links. Das Linkeigentum kann nur dann an einen anderen Benutzer übertragen werden, wenn das Projekteigentum übertragen wird, wie unter [Übertragen von Benutzer-Assets oder Festlegen des Kontoablaufs](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=de) im Analytics Admin-Handbuch.

1. Wählen Sie aus, ob die folgende Sicherheitsoption aktiviert werden soll (diese Option kann von Ihrem Customer Journey Analytics-Administrator gesteuert werden):

   * **[!UICONTROL Experience Cloud-Authentifizierung erforderlich]:**

     Wenn diese Option aktiviert ist, können nur Benutzer auf das Projekt zugreifen, die sich bei der Adobe Experience Cloud-Organisation anmelden können, in der das freigegebene Projekt erstellt wurde. Für Benutzer, für die Sie freigeben, ist jedoch kein Zugriff auf Adobe Analytics erforderlich.

     Customer Journey Analytics-Administratoren können diese Voreinstellung für das Unternehmen konfigurieren, wie unter [Voreinstellungen](/help/analysis-workspace/user-preferences.md). Je nachdem, wie der Administrator diese Option konfiguriert hat, können die folgenden Szenarien auftreten:

      * Wenn diese Option nicht angezeigt wird, hat Ihr Customer Journey Analytics-Administrator diese Funktion nicht aktiviert.

      * Wenn diese Option aktiviert ist und Sie sie nicht deaktivieren können, erfordert Ihr Customer Journey Analytics-Administrator die Experience Cloud-Authentifizierung für alle Benutzer, die auf Analysis Workspace-Projekte zugreifen. Dies gilt immer für Organisationen, die Gesundheitsschild bestellen.

1. Neben dem **[!UICONTROL Mit anderen teilen (keine Anmeldung erforderlich)]** und klicken Sie auf das **Link kopieren** icon ![Symbol Link kopieren](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg)), um den Link in die Zwischenablage Ihres Systems zu kopieren.

1. Geben Sie den Link für die Personen frei, die Zugriff auf das Projekt haben möchten. Sie können beispielsweise den Link in eine E-Mail einfügen.

   Alle Personen, für die Sie den Link freigeben, können das Analysis Workspace-Projekt anzeigen.

1. (Optional) Sie können auf die **Neuen Link erstellen** icon ![Symbol &quot;Link generieren&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) , um den Zugriff von Benutzern zu entfernen, die zuvor einen Link zum Projekt erhalten haben. Es wird ein neuer Link generiert, den Sie für Benutzer freigeben können, die auf das Projekt zugreifen möchten.

1. Auswählen **[!UICONTROL Schließen]** , um das Dialogfeld &quot;Freigeben&quot;zu schließen. Ihre Änderungen werden automatisch gespeichert.

## Freigeben von Projekten im Projekt-Manager {#Manager}

Projekte können auch über **[!UICONTROL Komponenten] > [!UICONTROL Projekte]** freigegeben werden. Ein einzelnes Projekt kann wie oben beschrieben freigegeben werden.  Wenn mehrere Projekte zum Freigeben ausgewählt wurden, werden die Empfänger für jedes Projekt der bestehenden Empfängerliste hinzugefügt.

Zum Beispiel:

* Projekt A wird für die Empfänger 1, 2 und 3 freigegeben
* Projekt B wird für die Empfänger 4, 5 und 6 freigegeben

Während Projekt A und B ausgewählt sind, werden die Empfänger 4 und 7 den Freigabelisten hinzugefügt. Die neue Freigabeliste für jedes Projekt lautet nun:

* Projekt A: 1, 2, 3, 4, 7
* Projekt B: 4, 5, 6, 7

![Das Fenster Empfänger zu mehreren Projekten hinzufügen .](assets/mult-proj-sharing.png)

## Freigeben von eingebetteten Komponenten

Im Folgenden finden Sie ein Video zum Thema:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Häufig gestellte Fragen (FAQ) {#FAQs}

| Frage | Antwort |
|---|---|
| Was passiert, wenn zwei Bearbeiter ein Projekt gleichzeitig speichern? | Die Änderungen werden nicht zusammengeführt und die zuletzt gespeicherte Projektversion bleibt erhalten. Analysis Workspace unterstützt derzeit keine Live-Zusammenarbeit. |
| Welches Projekterlebnis sehe ich als Administrator? | Administratoren, die in einer **[!UICONTROL Kopie bearbeiten]** oder **[!UICONTROL Schreibgeschützt]** Rolle erhält diese eingeschränkten Erlebnisse beim Öffnen eines Projekts. Bei Bedarf kann ein Administrator seine Rolle auf **[!UICONTROL Original bearbeiten]** jederzeit durch **[!UICONTROL Komponenten] > [!UICONTROL Projekte]**. |
| Was passiert, wenn ein Empfänger als Einzelperson einer Rolle und als Gruppenmitglied einer weiteren Rolle zugewiesen wird? | Wenn einem Empfänger mehrere Rollen zugewiesen werden, erhält er immer das höhere Erlebnis. Wenn einem Empfänger beispielsweise die Variable **[!UICONTROL Original bearbeiten]** Rolle als Einzelperson und **[!UICONTROL Kann anzeigen]** Als Mitglied einer Gruppe erhalten sie eine **[!UICONTROL Original bearbeiten]** Projekterlebnis. |
| Welches Erlebnis erhält ein Empfänger, wenn er einen Projekt-Link öffnet? | Empfänger erhalten die Rolle, die Sie ihnen im Freigabe-Modal zugewiesen haben. Wenn einem Empfänger keine Rolle zugewiesen wurde und er einen Link zum Projekt erhält (**[!UICONTROL Freigeben]** > **[!UICONTROL Freigeben für Workspace-Benutzer]**, wählen Sie **[!UICONTROL Kopieren]** neben dem **[!UICONTROL Über Link freigeben]** -Feld), werden sie standardmäßig in eine Rolle eingefügt. Administratoren erhalten **[!UICONTROL Original bearbeiten]** und Nicht-Administratoren erhalten **[!UICONTROL Kopie bearbeiten]**. |
