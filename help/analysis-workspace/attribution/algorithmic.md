---
title: Algorithmische Zuordnung
description: Machen Sie sich mit den Details des algorithmischen Attributionsmodells vertraut.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 42%

---

# Algorithmische Attribution

Das algorithmische [Attributionsmodell](models.md) in Analysis Workspace unterscheidet sich von anderen Modellen insofern, als es mithilfe statistischer Verfahren Gewichtungen über die Dimensionselemente in Ihrem Bericht oder Ihrer Freiform-Tabelle verteilt. Wie alle anderen Attributionsmodelle in Analysis Workspace kann die algorithmische Attribution für jede Dimension oder Metrik verwendet werden. Algorithmische Attribution unterstützt eine unbegrenzte Segmentierung und Aufschlüsselungen und verteilt 100 % der Konversionen auf eine oder mehrere Dimensionen in der Tabelle (auch als „fraktionelle“ Attribution bezeichnet).

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

Der für die Zuordnung verwendete Algorithmus basiert auf der Harsanyi-Dividende aus der kooperativen Spieltheorie. Die Harsanyi-Dividende ist eine Verallgemeinerung der Shapley-Value-Lösung (benannt nach Lloyd Shapley, einem Wirtschaftsnobelpreisträger), um in einem Spiel mit ungleichen Beiträgen zum Ergebnis Kredite unter den Spielern zu verteilen.

Auf allgemeiner Ebene wird bei der Attributionsberechnung der Konversion für jeden Touchpoint jeder der Marketing-Touchpoints innerhalb eines Lookback-Fensters als eine Koalition von Playern berücksichtigt. Dieser Koalition von Akteuren muss ein Überschuss gerecht verteilt werden. Die Überschussverteilung jeder Koalition wird aus dem Überschuss bestimmt, den jede Subkoalition zuvor rekursiv erzeugt hat.

Weitere Einzelheiten finden Sie in den Originalpapieren von John Harsanyi und Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Das Ergebnis der algorithmischen Attribution unterscheidet sich nur dann von anderen Modellen, wenn innerhalb des angegebenen Lookback-Fensters mehrere Touchpoints vorhanden sind. Konversionen mit einem einzigen Touchpoint erhalten eine Gewichtung von 100 % unabhängig vom Attributionsmodell.
