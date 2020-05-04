---
description: 'null'
title: 貢献度分析の実行
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: ad9a7729924636055e456d0fd7ab928be227034d

---


# 貢献度分析の実行

貢献度分析は、Adobe Analytics で異常値と見なされた結果に貢献した要因を発見するために設計された、集中的な機械学習プロセスです。目的は、ユーザーが、別の方法よりもずっと迅速に、焦点を当てるべき領域や追加の分析のオポチュニティを見つけるのを支援することです。

## 貢献度分析の実行 {#section_7D2C5E48A5664727941DF4C90976D9DC}

プロジェクトで貢献度分析を呼び出すには、2 つの方法があります。

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. 異常値が表示されていない行でも実行できます。

   >[!NOTE]
   >
   >貢献度分析は、現在、毎日の精度でのみサポートされています。

   ![](assets/run_ca.png)

* 折れ線グラフでは、折れ線グラフの異常値データポイントの上にマウスポインターを置きます。Click the **[!UICONTROL Analyze]** link that appears.

   ![](assets/contribution-analysis.png)

1. (Optional) After you have clicked **[!UICONTROL Run Contribution Analysis]** in either the line chart or a table, you can narrow the scope of (and thus speed up) the analysis by [excluding dimensions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. 貢献度分析が読み込まれるまでしばらく待ちます。レポートスイートのサイズおよびディメンションの数によって、これには、かなりの時間がかかる可能性があります。貢献度分析は、ディメンションあたり上位 50,000 項目の分析を実行します。
1. 次に、このプロジェクト内に直接新しい貢献度分析パネルが読み込まれます。以前 Reports &amp; Analytics の貢献度分析を使用したことがあるユーザーは、多くのパネルを既に目にしたことがあるでしょう。

   * その日の&#x200B;**訪問**&#x200B;数を表示するビジュアライゼーション。
   * コンテキストに関する毎月の&#x200B;**訪問トレンドライン**。
   * [貢献度スコア](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html)で並べ替えられた、この異常値に貢献した&#x200B;**トップアイテム**。加えて、問題の指標と、サイズの観点から指標を文脈の中で捉えるための実訪問者数指標。

   * [生成されたセグメント](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-build.html)（トップアイテムクラスター）テーブルは、貢献度スコア、異常値の発生数、異常な指標に貢献する全体的な割合に基づいて、トップアイテムの関連性を識別します。これは、その後、オーディエンスセグメントとしてキャプチャされます（貢献度セグメント 1、貢献度セグメント 2 など）。「i」（情報）ボタンをクリックすると、構成する上位の項目を含む、各自動セグメントの定義が表示されます。

      ![](assets/auto_segment.png)

1. 貢献度分析は、Analysis Workspace の一部なので、テーブルの右クリックメニューから数多くの機能を活用して、分析を一層意味のあるものにすることができます。例えば、次のような機能があります。

   * [各ディメンション項目を別のディメンションで分類する](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [1 つまたは複数の行のトレンドを示す](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [新しいビジュアライゼーションを追加する](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [アラートを作成する](/help/components/c-alerts/intellligent-alerts.md)
   * [セグメントを作成したり比較したりする](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]貢献度分析およびそれにリンクされたインテリジェントアラートプロジェクトで、分析された異常値が青い点でハイライト表示されます。これにより、分析された異常値がより明確に示されます。

## ディメンションの貢献度分析からの除外 {#section_F6932F4BF74544B5872164E7B1E0C6FC}

貢献度分析から一部のディメンションを除外したい場合があります。例えば、ブラウザーまたはハードウェア関連のディメンションは関係がなく、これらを削除することで分析を高速化したい場合です。

1. (または折れ線グラフ **[!UICONTROL Run Contribution Analysis]** 内で)をクリックすると、 **[!UICONTROL Analyze]****[!UICONTROL Excluded Dimensions]** パネルが表示されます。

1. 不要なサイズを **[!UICONTROL Excluded Dimensions]** パネルにドラッグし、をクリックしてリストを保存するだけで **[!UICONTROL Set as Default]**&#x200B;す。 Or, click **[!UICONTROL Clear All]** to start over with selecting dimensions to exclude.

   ![](assets/exclude_dimensions.png)

1. After you have added dimensions to exclude (or chosen not to), click **[!UICONTROL Run Contribution Analysis]** again.
1. 除外されたディメンションのリストを変更する必要がある場合はいつでも、ディメンションをダブルクリックすると、除外されたディメンションのリストが表示されます。

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.

