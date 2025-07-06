---
description: Analysis Workspaceで貢献度分析レポートを実行する方法を説明します。
title: 貢献度分析の実行
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 14%

---

# 貢献度分析の実行

[貢献度分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) は、Adobe Analytics で異常値と見なされた結果に貢献した要因を発見するために設計された、集中的な機械学習プロセスです。目的は、ユーザーが重点領域や追加分析の機会をより迅速に見つけられるように支援することです。

>[!NOTE]
>
>貢献度分析は、毎日の精度を持つデータに対してのみサポートされます。

貢献度分析を実行する手順は次のとおりです。

1. プロジェクトで貢献度分析を呼び出します。

   ![ 貢献度分析の実行 ](assets/run-contribution-analysis.png)

   1. 折れ線グラフ ビジュアライゼーションで、毎日の精度を持つフリーフォームテーブルに基づいて、異常値データポイントを選択します。 ポップアップから、「**[!UICONTROL 分析]**」を選択します。
   1. 毎日の精度を持つフリーフォームテーブルで、任意の行のコンテキストメニューから「**[!UICONTROL 貢献度分析を実行]**」を選択します。 異常値が表示されない行に対して分析を実行することもできます。
   1. 毎日の精度を持つフリーフォームテーブルで、異常値を示す行に対して：
      1. インジケーターの ◥ を選択します。
      1. ![ アラート ](/help/assets/icons/Alert.svg)**[!UICONTROL 異常値検出]** ダイアログで、「**[!UICONTROL 貢献度分析を開く]**」を選択します。



1. （任意）分析の範囲を狭める（その結果、スピードアップする）には、[ ディメンションを除く ](#exclude-dimensions) を使用します。

   ![ ディメンションの貢献度分析からの除外 ](assets/excluding-dimensions.png)

1. 「**[!UICONTROL 貢献度分析を実行]**」を選択します。

1. 貢献度分析が処理されるまでお待ちください。 レポートスイートのサイズとディメンションの数によっては、処理に時間がかかる可能性があります。 貢献度分析は、ディメンションごとに上位 50,000 個の項目に対して分析を実行します。 残りの [ 貢献度分析トークン ](anomaly-detection.md#contribution-analysis-tokens) の数も通知されます。

   ![ 実行中の貢献度分析 ](assets/contribution-analysis-executing.png)

1. Analysis Workspaceは、このプロジェクト内に直接新しい **[!UICONTROL 貢献度分析]** パネルを読み込みます。

   ![ 貢献度分析パネル ](assets/contribution-analysis.png)

   * [ 数値概要 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。
   * 月別のトレンド [ 折れ線グラフ ](/help/analyze/analysis-workspace/visualizations/line.md) ビジュアライゼーション。
   * この異常値に貢献する上位の項目を **[!UICONTROL 貢献度スコア]** で並べ替えて表示する [&#128279;](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) 上位の項目 [ フリーフォームテーブル ](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)。 追加の列には、該当する指標と、コンテキストを提供する **[!UICONTROL ユニーク訪問者]** 指標が表示されます。

   * **[!UICONTROL 生成されたセグメント（上位の項目クラスター）]**&#x200B;[ フリーフォームテーブル ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) は、貢献度スコア、異常値の発生件数、および異常値指標に貢献した全体的な割合に基づいて、上位の項目の関連付けを識別します。 この関連付けは、次にオーディエンスセグメント（貢献度セグメント 1、貢献度セグメント 2 など）として取得されます。 「![ 情報 ](/help/assets/icons/Info.svg)」を選択すると、セグメントが構成されている上位の項目など、セグメントの定義が表示されます。


1. 貢献度分析は現在、Analysis Workspaceの一部なので、フリーフォームテーブルのコンテキストメニューから多くの機能を利用して、分析をさらに有意義なものにすることができます。以下に例を示します。

   * [ 各ディメンション項目を別のディメンションで分類 ](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [1 つ以上の行のトレンド ](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [ 新しいビジュアライゼーションの追加 ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [ アラートの作成 ](/help/components/c-alerts/intellligent-alerts.md)
   * [セグメントを作成または比較する。](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>分析された異常値は、貢献度分析内で青い点でハイライト表示され、その異常値にリンクされたインテリジェントアラートプロジェクトが表示されます。 このハイライト表示により、分析された異常値がより明確に示されます。


## ディメンションを除外

一部のディメンションは、貢献度分析から除外することができます。 例えば、ブラウザーまたはハードウェア関連のディメンションは関係がなく、これらを削除することで分析を高速化したい場合です。

除外されたディメンションを管理するには：

* 不要なディメンションを **[!UICONTROL 除外されたディメンション]** パネルにドラッグしてから、「デフォルトとして設定 **[!UICONTROL をクリックしてリストを保存し]** す。

* 「**[!UICONTROL すべてクリア]**」を選択してやり直します。

* ![ ディメンション ](/help/assets/icons/Dimensions.svg) を選択してコンテキストメニューを表示し、![CrossSize400](/help/assets/icons/CrossSize400.svg) を使用して、選択した除外されたディメンションをリストから削除します。

  ![](assets/excluded-dimensions-list.png)

除外するディメンションを変更したら、もう一度 **[!UICONTROL 貢献度分析を実行]** を選択します。

