---
description: Erfahren Sie, wie Sie aus Workspace-Berichten Präsentationen im PPTX-Format generieren.
keywords: Analysis Workspace
title: Erstellen von Präsentationen aus Workspace-Berichten
feature: Curate and Share
role: User
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 4%

---

# Data storytelling: Folien-Präsentationen aus Workspace-Berichten generieren {#generate-powerpoint}

>[!NOTE]
>
>Data Storytelling ist eine Qualifikation unter Data Insights Agent und steht berechtigten Kunden für eine begrenzte Zeit zur Verfügung. Der Zugriff auf Data Insights Agent endet am 28. Februar 2026. Um Data Insights Agent oder andere Adobe Experience Platform-Agenten ohne Unterbrechung weiter zu verwenden, wenden Sie sich an Ihren Adobe-Kundenbetreuer, um mehr über die Lizenzierung von Adobe Experience Platform Agent Orchestrator zu erfahren.


Benutzende mit [den erforderlichen Berechtigungen](#permission-requirements-to-generate-slides) können automatisch PPTX-Präsentationen basierend auf Analysis Workspace-Projekten generieren. Beim Generieren dieser Folienpräsentationen erstellt Customer Journey Analytics automatisch eine Story aus Ihren Daten, indem wichtige Erkenntnisse identifiziert und in Stakeholder-fähige Folien umgewandelt werden.

Diese generierte Daten-Story reduziert den Zeit-, Arbeits- und Expertenaufwand, der zum Aufdecken von Ergebnissen aus einem Workspace-Projekt erforderlich ist. Analysten können sich stärker auf die Datenexploration konzentrieren und es Customer Journey Analytics gleichzeitig ermöglichen, die Erzählung für Führungskräfte zu erstellen und zu formatieren und die geschäftlichen Auswirkungen für die Stakeholder zu kommunizieren.

## Verstehen von Daten-Storys in Folienpräsentationen

Eine **Daten-Story** ist die Erzählung, die Customer Journey Analytics basierend auf Ihren Workspace-Daten erstellt. Mithilfe der generativen KI identifiziert Customer Journey Analytics wichtige Themen in den Bedienfeldern und Visualisierungen, die Sie in Ihre Folienpräsentation aufnehmen möchten. Es generiert Einblicke und durchläuft dann einen Deduplizierungs- und Bewertungsprozess, um eine Untergruppe von Einblicken zu identifizieren, die zur Erstellung der Daten-Story verwendet werden können.

In den folgenden Abschnitten werden der zusätzliche Wert beschrieben, den Daten-Storys bieten, die erforderlichen Elemente eines Projekts, die zur Gestaltung der Erzählung beitragen, und die Schlüsselelemente, die in der PPTX-Präsentationsausgabe enthalten sind.

### Zusätzlicher Nutzen durch Daten-Storys

Daten-Storys bieten Mehrwert und Erkenntnisse für ein Workspace-Projekt, indem sie Daten für Benutzende zugänglich machen, die weniger Erfahrung mit der Datenanalyse haben.

Datenverläufe ergänzen eine Analyse für ein bestimmtes Workspace-Projekt durch:

* Bereitstellen von zusätzlichem Kontext

* Hervorheben wichtiger Erkenntnisse

* Bewertung, ob bestimmte Variablen zu niedrig oder zu hoch bewertet werden

* Hinweisen auf verborgene Trends, Anomalien und andere beitragende Faktoren

* Ideen für die nächsten Schritte

### Projektelemente, die Daten-Storys formen

Analysis Workspace erstellt Daten-Storys unter Berücksichtigung der folgenden Projektelemente:

* Beziehungen zwischen Dimensionen und Metriken

* Die einzelnen Elemente, die die Grundlage der Analyse bilden (Dimensionen, Metriken, Filter, Freiformtabellen-Struktur, Visualisierungen und Bedienfelder)

* Die den Bedienfeldern, Tabellen und Visualisierungen gegebenen Namen

* Die Reihenfolge der Metriken in einer Freiformtabelle (um die Priorität zu bestimmen)

* Reihenfolge der Visualisierungen in einem Bedienfeld (zur Bestimmung der Priorität)

* Zusammenfassungsnummern und Zusammenfassungstexte (um Metriken zu bestimmen, die in der Daten-Story hervorgehoben werden müssen)

### Präsentationselemente einer Daten-Story

Daten-Storys bestehen aus einer Titelfolie, einer Übersichtsfolie, Detailfolien und Abschnittstrennelementen.

**Titelfolie:** Zeigt den Titel und den Namen des Referenten an, den Sie angeben. Informationen finden sich in den Sprechernotizen, die den Prozess beschreiben, wie das Thema und die Erzählung erstellt wurden, wie viele Einblicke generiert und verwendet wurden und welche Bedienfelder verwendet wurden.

**Zusammenfassung:** priorisiert die wertvollsten Einblicke und erstellt eine übergreifende Geschichte, die zwischen 1 und 5 Sätzen lang ist.

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
   | **[!UICONTROL Bedienfelder und einzuschließende Visualisierungen]** | Wählen Sie die Bedienfelder und Visualisierungen aus, die Sie in die Präsentation einbeziehen möchten. Sie können bis zu 50 Visualisierungen einschließen.<p>Wenn eine Visualisierung abgeblendet ist, folgt entweder der Text **[!UICONTROL (nicht unterstützt)]** oder **[!UICONTROL (eingeschränkte Daten)]**.</p><ul><li>**Nicht**: Die meisten Bedienfelder und Visualisierungen werden unterstützt. Informationen zu nicht unterstützten Bereichen und Visualisierungen finden Sie unter [Nicht unterstützte Projektelemente und -funktionen](#unsupported-project-elements-and-features).</li><li>**Eingeschränkte Daten**: Die Visualisierung enthält eine Komponente, die nicht durch eine von Ihrem Unternehmen durchgesetzte Data-Governance-Richtlinie exportiert werden darf. Wenden Sie sich an Ihren Systemadministrator, um zu erfahren, welche Komponenten nicht exportiert werden dürfen, und entfernen Sie dann die eingeschränkten Komponenten, bevor Sie Folien erstellen.</li></ul> |
   | **[!UICONTROL Komponenten hervorheben]** | Wählen Sie die Metriken und Dimensionen aus Ihren Visualisierungen aus, die Sie in der Präsentation hervorheben möchten. Die von Ihnen ausgewählten Komponenten werden höher eingestuft und erhalten mehr Gewicht, wenn die Themen und die übergreifende Erzählung der Daten-Story erstellt werden. <p>Wenn keine Hervorhebung angewendet wird, werden Komponenten in Präsentationen wie folgt angezeigt:<ul><li>**Metriken und Dimensionen:** Kursiv</li><li>**Dimension-Elemente:** Anführungszeichen</li></ul></p><p>Wenn die Hervorhebung angewendet wird, werden Komponenten in Präsentationen wie folgt angezeigt:</p><ul><li>**Metriken und Dimensionen:** und fett</li><li>**Dimension-Elemente:** Fett, wenn die entsprechende Dimension hervorgehoben wird<p>Eine Farbe wird auch auf das Dimensionselement angewendet, wenn das Dimensionselement im Diagramm hervorgehoben wird.</p></li></ul> |

   <!-- add this later: - **[!UICONTROL Panel and visualization descriptions]** - Choose whether to include panel and visualization descriptions in your generated slide presentation. - 
   - **[!UICONTROL Annotations]** - Choose whether annotations are visible in your generated slide presentation. For more information about annotations, see [Annotations overview](/help/components/annotations/overview.md).  -  -->

1. (Bedingt) Wählen Sie **[!UICONTROL Standarddesign]** aus, wenn Sie Folien in weniger Schritten generieren möchten und wenn für Ihre Folienpräsentation kein Unternehmensdesign erforderlich ist.

   Wählen Sie einfach das Farbthema Ihrer Präsentation aus, indem Sie die gewünschte Farbe auswählen.

   ![Erstellen von Folien mit dem Standarddesign](assets/generate-slides-default-theme.png)

1. (Bedingt) Wählen Sie **[!UICONTROL Vorlage hochladen]**, wenn Ihre Folienpräsentation einem Unternehmensdesign entsprechen muss. Für diese Option müssen Sie eine benutzerdefinierte Vorlage hochladen und Ihre benutzerdefinierten Stile anwenden.

   Die zuletzt hochgeladene benutzerdefinierte Vorlage wird lokal im Browser-Cache gespeichert und steht beim Generieren zukünftiger Folienpräsentationen zur Verfügung.

   ![Erzeugen von Folien mit einer benutzerdefinierten Vorlage](assets/generate-slides-upload-template.png)

   Führen Sie einen der folgenden Schritte aus, um eine benutzerdefinierte Vorlage hochzuladen:

   +++(Empfohlen) Leere Vorlage herunterladen und ändern

   1. Download [diese leere Vorlage](https://d30ln29764hddd.cloudfront.net/deploy/builds/data-storytelling.2025-10-20T15:10:19/resources/components/Blank.potx?).

   1. Wenden Sie Ihre benutzerdefinierten Stile auf die leere Vorlage an.

   1. Laden Sie die Vorlage erneut hoch, ohne die übergeordneten Layout-Namen zu ändern:

      Ziehen Sie aus Ihrem Dateisystem die leere Vorlage, auf die Ihre benutzerdefinierten Stile angewendet wurden, in den Ablagebereich.

      Oder

      Wählen Sie **[!UICONTROL Durchsuchen]**, navigieren Sie zu und wählen Sie Ihre leere Vorlage aus, auf die Ihre benutzerdefinierten Stile aus dem Dateisystem angewendet wurden.

   1. Im Abschnitt **[!UICONTROL Layout-]**&quot; wird jedes Folien-Layout, das in generierten Präsentationen verwendet wird, automatisch einer Folie aus Ihrem hochgeladenen Design zugeordnet. Überprüfen Sie die Auswahl, um sicherzustellen, dass sie korrekt sind.

      ![Layout-Zuordnung](assets/generate-slides-layout-mapping.png)

   1. (Bedingt) Wenn ein Folien-Layout falsch zugeordnet ist, wählen Sie über der Folie, **[!UICONTROL aus Ihrer hochgeladenen Präsentation ausgewählt wurde, die Option Auswahl ändern]** und dann die Folie aus, die dem Layout entspricht.

      Wiederholen Sie diesen Vorgang für jede Folie, die falsch zugeordnet wurde.

   +++

   +++Direktes Hochladen einer benutzerdefinierten Vorlage 

   1. Ziehen Sie Ihre benutzerdefinierte Vorlage aus Ihrem Dateisystem in den Ablagebereich.

      Oder

      Wählen **[!UICONTROL Durchsuchen]**, navigieren Sie zu und wählen Sie Ihre benutzerdefinierte Vorlage aus dem Dateisystem aus.

      Stellen Sie sicher, dass die hochgeladene Datei über Master-Layouts mit den folgenden Namen verfügt: „Title_Slide“, „Section_Divider“, „Title_Text“, „Title_Chart“, „Title_Two_Content_Mixed“, „Title_Three_Content_Mixed“.

      Es werden bis zu 25 primäre Layouts unterstützt.

      .pptx- und .potx-Dateien mit einer Größe von bis zu 25 MB werden unterstützt.

   1. Im Abschnitt **[!UICONTROL Layout-]**&quot; wird jedes Folien-Layout, das in generierten Präsentationen verwendet wird, automatisch einer Folie aus Ihrem hochgeladenen Design zugeordnet. Überprüfen Sie die Auswahl, um sicherzustellen, dass sie korrekt sind.

      ![Benutzerdefinierte Layoutzuordnung](assets/generate-slides-layout-mapping-custom-template.png)

   1. (Bedingt) Wenn ein Folien-Layout falsch zugeordnet ist, wählen Sie über der Folie, **[!UICONTROL aus Ihrer hochgeladenen Präsentation ausgewählt wurde, die Option Auswahl ändern]** und dann die Folie aus, die dem Layout entspricht.

      Wiederholen Sie diesen Vorgang für jede Folie, die falsch zugeordnet wurde.

   +++

1. Wählen Sie **[!UICONTROL PPT exportieren]**.

   Die .pptx-Präsentation wird automatisch auf Ihre Workstation heruntergeladen.

1. (Empfohlen) Öffnen Sie die .pptx-Präsentation und überprüfen Sie sie. Nehmen Sie die erforderlichen Änderungen vor.

## Berechtigungsanforderungen zum Generieren von Folien

>[!AVAILABILITY]
>
>Wenn Ihr Unternehmen keinen Zugriff auf die Erstellung von Folien aus einem Workspace-Projekt hat, wenden Sie sich an Ihren Adobe-Kundenbetreuer, um mehr über die Lizenzierung zu erfahren.

Die Möglichkeit, Folien zu generieren, ist standardmäßig für alle Benutzer in Organisationen aktiviert, die über die erforderliche Lizenz verfügen.

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

   * Bereich

   * Bullet

   * Kohortentabelle

   * Kombination

   * Freiformtabellen mit mehreren Dimensionsspalten (Tabellen mit einer einzigen Dimensionsspalte werden unterstützt)

   * Journey-Arbeitsfläche

   * Streuung

   * Baumkarte

* Geführte Analysen

* Komponenten, die durch eine Data-Governance-Richtlinie nicht exportiert werden dürfen

  Weitere Informationen finden Sie unter [Fehlerbehebung bei fehlgeschlagenen ](/help/components/exports/troubleshoot-exports.md)).

## Projektelemente und -funktionen mit begrenzter Unterstützung

* Aufschlüsselung

  Im Rahmen des Deduplizierungs- und Bewertungsprozesses beim Generieren relevanter Einblicke wird jede Aufschlüsselung innerhalb einer Freiformtabelle unabhängig analysiert, und nur die ersten 5 Aufschlüsselungen innerhalb einer einzelnen Freiformtabelle werden analysiert.

  Es wird nur die erste Ebene einer Aufschlüsselung unterstützt. Eine Aufschlüsselung einer Aufschlüsselung ist nicht in der Präsentation enthalten.


