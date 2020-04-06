---
description: 'null'
title: 貢献度分析の実行
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 貢献度分析の実行

貢献度分析は、Adobe Analyticsで異常値が観察された結果の貢献者を明らかにするために設計された、集中的な機械学習プロセスです。 この目的は、ユーザーが、他の可能な範囲よりもはるかに迅速に、焦点を当てる領域や追加の分析の機会を見つけるのを支援することです。

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

1. 貢献度分析の読み込み中。 レポートスイートのサイズとディメンション数によっては、この処理にかなりの時間がかかる場合があります。 貢献度分析は、ディメンションあたり上位50,000項目の分析を実行します。
1. 次に、このプロジェクト内に新しい貢献度分析パネルが読み込まれます。 以前にReports &amp; Analyticsの貢献度分析を使用したことがある場合は、多くのパネルが見慣れています。

   * その日の訪問数を示すビジュア **ライゼーショ** ンです。
   * コンテキスト **の月別訪問トレンド** ライン。
   * [貢献度スコア](https://marketing.adobe.com/resources/help/ja_JP/analytics/contribution/ca_contribution_score.html)で並べ替えられた、この異常値に貢献した&#x200B;**トップアイテム**。加えて、問題の指標と、サイズの観点から指標を文脈の中で捉えるための実訪問者数指標。

   * 生成さ [れたセグメント](https://marketing.adobe.com/resources/help/ja_JP/analytics/contribution/ca_workflow_premium.html) （上位の項目クラスター）テーブルは、貢献度スコア、異常値の発生数、異常な指標に貢献する全体的な割合に基づいて、上位の項目の関連付けを識別します。 次に、これをオーディエンスセグメント（貢献度セグメント1、貢献度セグメント2など）としてキャプチャします。 「i」（情報）ボタンをクリックすると、各自動セグメントの定義が表示され、その定義の構成要素は次のとおりです。

      ![](assets/auto_segment.png)

1. 貢献度分析は、分析ワークスペースの一部になったので、テーブルの右クリックメニューにある多くの機能を利用して、分析をさらに意味のあるものにすることができます。例：

   * [各ディメンション項目を別のディメンションで分類する](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [1 つまたは複数の行のトレンドを示す](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [新しいビジュアライゼーションを追加する](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [アラートを作成する](/help/components/c-alerts/intellligent-alerts.md)
   * [セグメントを作成したり比較したりする](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]貢献度分析およびそれにリンクされたインテリジェントアラートプロジェクトで、分析された異常値が青い点でハイライト表示されます。これにより、分析された異常値がより明確に示されます。

## ディメンションの貢献度分析からの除外 {#section_F6932F4BF74544B5872164E7B1E0C6FC}

貢献度ディメンションから一部のディメンションを除外する場合があります。分析 例えば、ブラウザやハードウェアに関連するディメンションは一切気にしない場合があり、削除することで分析を高速化できます。

1. （折れ線グラフで） **[!UICONTROL Run Contribution Analysis]** をク **[!UICONTROL Analyze]** リックすると、パネルが表示 **[!UICONTROL Excluded Dimensions]** されます。

1. 不要なディメンションをパネルにドラッ **[!UICONTROL Excluded Dimensions]** グし、をクリックしてリストを保存しま **[!UICONTROL Set as Default]**&#x200B;す。 Or, click **[!UICONTROL Clear All]** to start over with selecting dimensions to exclude.

   ![](assets/exclude_dimensions.png)

1. After you have added dimensions to exclude (or chosen not to), click **[!UICONTROL Run Contribution Analysis]** again.
1. 除外されたディメンションのリストを変更する必要がある場合はいつでも、ディメンションをダブルクリックすると、除外されたディメンションのリストが表示されます。

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.

