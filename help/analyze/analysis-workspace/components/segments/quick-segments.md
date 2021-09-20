---
description: Analysis Workspaceでのクイックセグメントの使用。
title: クイックセグメント
feature: Workspace Basics
role: User, Admin
source-git-commit: 8cd5d5ec1525e29779a13330dfeaeae120dfdd56
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---


# クイックセグメント

プロジェクト内に迅速なセグメントを作成して、[セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md)全体の複雑さを回避できます。 本格的なコンポーネントレベルのセグメントとクイックセグメントで実行できる操作の比較については、[ここ](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)を参照してください。

>[!IMPORTANT]
> 現在、クイックセグメントは制限付きテストで、一般にはまだ利用できません。

## クイックセグメントの作成

1. フリーフォームテーブルで、パネルヘッダーのフィルター+アイコンをクリックします。

   ![](assets/quick-seg1.png)

   :

   - ディメンション/指標/日付範囲をセグメントに含める（またはセグメントから除外する）ことができるセグメントコンテナは1つだけです。
   - コンテナは、ヒット、訪問または訪問者レベルに設定できます。 初期設定は「ヒット」です。

1. 次の3つの方法のいずれかで、ディメンション/指標/日付範囲を追加します。

   - 入力を開始すると、クイックセグメントビルダーが適切なコンポーネントを自動的に見つけます。
   - ドロップダウンリストを使用して、コンポーネントを検索します。
   - 左側のパネルからコンポーネントをドラッグ&amp;ドロップします。

1. 最初のルール（例：`Page equals workspace`）を指定します。 セグメント定義には、最大3つのルールを含めることができます。 「+」記号をクリックして、別のルールを追加します。 「AND」修飾子または「OR」修飾子をルールに追加できますが、1つのセグメント定義で「AND」修飾子と「OR」修飾子を混在させることはできません。

   ディメンションと指標を組み合わせたセグメントの例を次に示します。

