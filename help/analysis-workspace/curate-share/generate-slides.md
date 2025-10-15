---
description: Erfahren Sie, wie Sie aus Workspace-Berichten Präsentationen im PPTX-Format generieren.
keywords: Analysis Workspace
title: Erstellen von Präsentationen aus Workspace-Berichten
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Data storytelling: Folien-Präsentationen aus Workspace-Berichten generieren {#generate-powerpoint}

Sie können automatisch PPTX-Präsentationen aus Analysis Workspace-Projekten generieren. Beim Generieren von Präsentationen erkennt Customer Journey Analytics automatisch wichtige Erkenntnisse und konvertiert sie in Stakeholder-fähige Folien.

Diese Funktion reduziert den Zeit- und Arbeitsaufwand für das Aufdecken von Ergebnissen aus Ihren Workspace-Projekten und ermöglicht es Ihnen, schnell Erzählungen für Führungskräfte zu erstellen und geschäftliche Auswirkungen zu kommunizieren.

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

1. Gehen Sie zum Workspace-Projekt, das die Daten enthält, die Sie als Grundlage für Ihre Präsentation verwenden möchten.

1. Wählen **[!UICONTROL oben rechts]** der Seite die Option „Folien generieren“ aus.

1. Geben Sie die folgenden Informationen an:

   | Option | Beschreibung |
   |---------|----------|
   | **[!UICONTROL Titeltitel]** | Geben Sie einen Titel für die Präsentation an. Dieser Titel wird auf der Titelfolie der Präsentation angezeigt. |
   | **[!UICONTROL Name des Referenten einschließen]** | Geben Sie den Namen des Referenten an. Dieser Name wird auf der Titelfolie der Präsentation unter dem Titeltitel angezeigt. |
   | **[!UICONTROL Bedienfelder und einzuschließende Visualisierungen]** | Wählen Sie die Bedienfelder und Visualisierungen aus, die Sie in die Präsentation aufnehmen möchten. Sie können bis zu 50 Visualisierungen einschließen.<p>Die meisten Bedienfelder und Visualisierungen werden unterstützt. Informationen zu nicht unterstützten Bereichen und Visualisierungen finden Sie unter [Nicht unterstützte Projektelemente und -funktionen](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Bedienfeld- und Visualisierungsbeschreibungen]** | |
   | **[!UICONTROL Anmerkungen]** | |
   | **[!UICONTROL Komponenten hervorheben]** | Wählen Sie aus Ihren Visualisierungen, die Sie in der Präsentation hervorheben möchten, bis zu 5 Metriken und 5 Dimensionen aus.<p>Wenn keine Hervorhebung angewendet wird, werden Komponenten in Präsentationen wie folgt angezeigt:<ul><li>**Metriken und Dimensionen:** Kursiv</li><li>**Dimension-Elemente:** Anführungszeichen</li></ul></p><p>Wenn die Hervorhebung angewendet wird, werden Komponenten in Präsentationen wie folgt angezeigt:</p><ul><li>**Metriken und Dimensionen:** und fett</li><li>**Dimension-Elemente:** Fett, wenn die entsprechende Dimension hervorgehoben wird<p>Eine Farbe wird auch auf das Dimensionselement angewendet, wenn das Dimensionselement im Diagramm hervorgehoben wird.</p></li></ul> |

(Bedingt) Wählen Sie **[!UICONTROL Standarddesign]** aus, wenn Ihre Folien mit dem Standarddesign generiert werden sollen.

1. Wählen Sie aus, ob ein Standarddesign verwendet oder eine benutzerdefinierte Vorlage hochgeladen werden soll:

   * **[!UICONTROL Standarddesign]**:

   * **[!UICONTROL Vorlage hochladen]**:





## Bearbeiten von Folien aus einer zuvor generierten Präsentation


## Herunterladen einer generierten .pptx-Präsentation

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


