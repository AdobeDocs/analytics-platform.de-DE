---
description: Erfahren Sie, wie Sie aus Workspace-Berichten Präsentationen im PPTX-Format generieren.
keywords: Analysis Workspace
title: Erstellen von Präsentationen aus Workspace-Berichten
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# Data storytelling: Folien-Präsentationen aus Workspace-Berichten generieren {#generate-powerpoint}

Benutzende mit [den erforderlichen Berechtigungen](#permission-requirements-to-generate-slides) können automatisch PPTX-Präsentationen aus Analysis Workspace-Projekten generieren. Beim Generieren dieser Folienpräsentationen erstellt Customer Journey Analytics automatisch eine Story aus Ihren Daten, indem wichtige Erkenntnisse identifiziert und in Stakeholder-fähige Folien umgewandelt werden.

Diese Funktion reduziert den Zeit- und Arbeitsaufwand für das Aufdecken von Ergebnissen aus Ihren Workspace-Projekten und ermöglicht es Ihnen, schnell Erzählungen für Führungskräfte zu erstellen und den Stakeholdern geschäftliche Auswirkungen zu kommunizieren.

Diese automatisch generierte Daten-Story ermöglicht es Analysten, sich auf die Datenexploration zu konzentrieren, während Customer Journey Analytics die Ergebnisse des Analysten für die Verwendung durch Stakeholder kuratiert und formatiert.

## Verstehen von Daten-Storys in Folienpräsentationen

Analysis Workspace verwendet generative KI zum Erstellen von Daten-Storys in Folienpräsentationen. Diese Daten-Storys ergänzen eine Analyse für ein bestimmtes Workspace-Projekt, indem sie zusätzlichen Kontext bieten, wichtige Highlights aufzeigen und Ideen für die nächsten Schritte geben. Rufen Sie versteckte Trends, Anomalien, beitragende Faktoren, wichtige Treiber auf

### Zusätzlicher Nutzen durch Daten-Storys

Datenverläufe ergänzen eine Analyse für ein bestimmtes Workspace-Projekt durch:

* Bereitstellen von zusätzlichem Kontext

* Hervorheben wichtiger Erkenntnisse

* Hinweisen auf verborgene Trends, Anomalien und andere beitragende Faktoren

* Schlüsseltreiber identifizieren

* Ideen für die nächsten Schritte

### Projektelemente, die Daten-Storys formen

Analysis Workspace erstellt Daten-Storys unter Berücksichtigung der folgenden Projektelemente:

* Beziehungen zwischen Dimensionen und Metriken

* Die einzelnen Elemente, die die Grundlage der Analyse bilden: Dimensionen, Metriken, Filter, Freiformtabellenstruktur, Visualisierungen und Bedienfelder

* Die den Bedienfeldern, Tabellen und Visualisierungen gegebenen Namen

* Die Reihenfolge der Metriken in einer Freiformtabelle (um die Priorität zu bestimmen)

* Zusammenfassungsnummern und Zusammenfassungstexte (um Metriken zu bestimmen, die in der Daten-Story hervorgehoben werden müssen)

### Präsentationselemente einer Daten-Story

Daten-Storys bestehen aus einer Folien-Zusammenfassung für Führungskräfte, Detailfolien und Abschnittstrennelementen.

**Zusammenfassung:** Priorisiert die wertvollsten Einblicke und erstellt eine übergreifende Geschichte mit einer Länge von 1 bis 5 Sätzen.

**Detailfolien:** Erzeugt Einblicke zu allen Tabellen, Bereichen und Visualisierungen in einem Workspace-Projekt. Einblicke bestehen aus Trends, Saisonalen, Anomalien und Korrelationen.

**Abschnittstrenner:** Teilt Einblicke durch entsprechend platzierte und benannte Abschnittstrenner.

## Erzeugen einer .pptx-Präsentation basierend auf einem Workspace-Projekt

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Eingeschlossene Bedienfelder und Visualisierungen"
>abstract="Wählen Sie die Bedienfelder und Visualisierungen aus, die Sie in die Präsentation einbeziehen möchten. Sie können bis zu 50 Visualisierungen einschließen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Hervorgehobene Komponenten"
>abstract="Wählen Sie aus Ihren Visualisierungen, die Sie in der Präsentation hervorheben möchten, bis zu 5 Metriken und 5 Dimensionen aus. Die ausgewählten Metriken werden kursiv angezeigt, Dimensionen werden fett und Dimensionselemente in einer kontrastierenden Farbe angezeigt."

<!-- markdownlint-enable MD034 -->

1. Gehen Sie zum Workspace-Projekt, das die Daten enthält, die Sie als Grundlage für Ihre Folienpräsentation verwenden möchten.

1. Wählen **[!UICONTROL oben rechts]** der Seite die Option „Folien generieren“ aus.

   Das Dialogfeld Folien generieren wird angezeigt.

   ![Dialogfeld „Folien generieren“](assets/generate-slides.png)

1. Geben Sie die folgenden Informationen an:

   | Option | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Titeltitel]** | Geben Sie einen Titel für die Präsentation an. Dieser Titel wird auf der Titelfolie der Präsentation angezeigt. |
   | **[!UICONTROL Name des Referenten einschließen]** | Geben Sie den Namen des Referenten an. Dieser Name wird auf der Titelfolie der Präsentation unter dem Titeltitel angezeigt. |
   | **[!UICONTROL Bedienfelder und einzuschließende Visualisierungen]** | Wählen Sie die Bedienfelder und Visualisierungen aus, die Sie in die Präsentation aufnehmen möchten. Sie können bis zu 50 Visualisierungen einschließen.<p>Die meisten Bedienfelder und Visualisierungen werden unterstützt. Informationen zu nicht unterstützten Bereichen und Visualisierungen finden Sie unter [Nicht unterstützte Projektelemente und -funktionen](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Bedienfeld- und Visualisierungsbeschreibungen]** | |
   | **[!UICONTROL Anmerkungen]** | |
   | **[!UICONTROL Komponenten hervorheben]** | Wählen Sie aus Ihren Visualisierungen, die Sie in der Präsentation hervorheben möchten, bis zu 5 Metriken und 5 Dimensionen aus.<p>Wenn keine Hervorhebung angewendet wird, werden Komponenten in Präsentationen wie folgt angezeigt:<ul><li>**Metriken und Dimensionen:** Kursiv</li><li>**Dimension-Elemente:** Anführungszeichen</li></ul></p><p>Wenn die Hervorhebung angewendet wird, werden Komponenten in Präsentationen wie folgt angezeigt:</p><ul><li>**Metriken und Dimensionen:** und fett</li><li>**Dimension-Elemente:** Fett, wenn die entsprechende Dimension hervorgehoben wird<p>Eine Farbe wird auch auf das Dimensionselement angewendet, wenn das Dimensionselement im Diagramm hervorgehoben wird.</p></li></ul> |

1. (Bedingt) Wählen Sie **[!UICONTROL Standarddesign]** aus, wenn Sie Folien schnell in weniger Schritten generieren möchten und für Ihre Folienpräsentation kein Unternehmensdesign erforderlich ist.

   Wählen Sie einfach das Farbthema Ihrer Präsentation aus, indem Sie die gewünschte Farbe auswählen.

   ![Erstellen von Folien mit dem Standarddesign](assets/generate-slides-default-theme.png)

1. (Bedingt) Wählen Sie **[!UICONTROL Vorlage hochladen]**, wenn Ihre Folienpräsentation einem Unternehmensdesign entsprechen muss. Für diese Option müssen Sie eine benutzerdefinierte Vorlage hochladen und Ihre benutzerdefinierten Stile anwenden.

   ![Erzeugen von Folien mit einer benutzerdefinierten Vorlage](assets/generate-slides-upload-template.png)

   Führen Sie einen der folgenden Schritte aus, um eine benutzerdefinierte Vorlage hochzuladen:

   * (Empfohlen) Leere Vorlagen herunterladen und ändern.

      1. Diese leere Vorlage herunterladen. <!--add link-->

      1. Wenden Sie Ihre benutzerdefinierten Stile auf die leere Vorlage an.

      1. Laden Sie die Vorlage erneut hoch, ohne die übergeordneten Layoutnamen zu ändern.

   * Laden Sie eine benutzerdefinierte Vorlage direkt hoch.

      1. Ziehen Sie Ihre benutzerdefinierte Vorlage aus Ihrem Dateisystem in den Ablagebereich.

         Oder

         Wählen **[!UICONTROL Durchsuchen]**, navigieren Sie zu und wählen Sie Ihre benutzerdefinierte Vorlage aus dem Dateisystem aus.

         Stellen Sie sicher, dass die hochgeladene Datei über Master-Layouts mit den folgenden Namen verfügt: „Title_Slide“, „Section_Divider“, „Title_Text“, „Title_Chart“, „Title_Two_Content_Mixed“, „Title_Three_Content_Mixed“

         .pptx- und .potx-Dateien mit einer Größe von bis zu 25 MB werden unterstützt.

1. Wählen Sie **[!UICONTROL PPT exportieren]**.

1. (Empfohlen) Überprüfen und bearbeiten Sie die .ppt-Präsentation und nehmen Sie alle erforderlichen Änderungen vor, wie im folgenden Abschnitt beschrieben (Bearbeiten [ Folien aus einer zuvor generierten Präsentation](#edit-slides-from-a-previously-generated-presentation).

## Bearbeiten von Folien aus einer zuvor generierten Präsentation


## Herunterladen einer generierten .pptx-Präsentation



## Berechtigungsanforderungen zum Generieren von Folien

>[!AVAILABILITY]
>
>Wenn Ihr Unternehmen keinen Zugriff auf die Erstellung von Folien aus einem Workspace-Projekt hat, wenden Sie sich an Ihren Adobe-Kundenbetreuer, um mehr über die Lizenzierung zu erfahren.
>
>Diese Funktion ist standardmäßig für alle Benutzer in Organisationen aktiviert, die über die erforderliche Lizenz verfügen.

Produktprofil-Admins, deren Organisationen über die Lizenzierung zum Generieren von Folien verfügen, können den Zugriff bei Bedarf deaktivieren.

In der [!UICONTROL Adobe Admin Console] bestimmt die Berechtigung [!UICONTROL Reporting-]**[!UICONTROL Data]** storytelling) den Zugriff auf diese Funktion. Ein [Produktprofil-Administrator](https://helpx.adobe.com/de/enterprise/using/manage-product-profiles.html) muss diese Schritte in der [!UICONTROL Admin Console ausführen] wenn er den Zugriff deaktivieren möchte:
1. Navigieren Sie zu **[!UICONTROL Admin Console]** > **[!UICONTROL Produkte und Dienste]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Produktprofile]**.
1. Wählen Sie den Titel des Produktprofils aus, für das Sie Zugriff auf &quot;[!UICONTROL  storytelling&quot; ] möchten.
1. Wählen Sie im entsprechenden Produktprofil die Option **[!UICONTROL Berechtigungen]** aus.
1. Wählen Sie ![Bearbeiten](/help/assets/icons/Edit.svg) aus, um **[!UICONTROL Reporting-Tools]** zu bearbeiten.
1. Wählen Sie ![AddCircle](/help/assets/icons/RemoveCircle.svg) aus, um **Data storytelling** aus den **[!UICONTROL Included permission items]**.

   <!--add screenshot of permission in the admin console-->

1. Wählen Sie **[!UICONTROL Speichern]** aus, um die Berechtigungen zu speichern.

Weitere Informationen finden Sie unter [Zugriff auf Benutzerebene](/help/technotes/access-control.md#user-level-access) in [Zugriffssteuerung](/help/technotes/access-control.md#access-control).

## Nicht unterstützte Projektelemente und Funktionen {#unsupported}

Die folgenden Analysis Workspace-Elemente und -Funktionen, die in einem Projekt verwendet werden, werden beim Generieren von Folien nicht unterstützt:

* Panel „Attribution“

  Dieses Bedienfeld wird abgeblendet angezeigt, wenn die Konfigurationsoptionen angezeigt werden.

  Alle anderen Bedienfelder können in Folien eingeschlossen werden, die aus einem Workspace-Projekt generiert werden.

* Einige Visualisierungen

  Die meisten Visualisierungen können in Folien eingefügt werden, die aus einem Workspace-Projekt generiert werden. Die folgenden Visualisierungen können jedoch nicht eingeschlossen werden und werden abgeblendet angezeigt, wenn die Konfigurationsoptionen angezeigt werden:

   * Kohortentabelle

   * Journey-Arbeitsfläche

   * Bullet

   * Kombination

   * Streuung

   * Baumkarte

* Aufschlüsselung

* Geführte Analysen


