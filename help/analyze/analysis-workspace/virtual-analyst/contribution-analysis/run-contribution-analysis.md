---
description: Workspace プロジェクトで貢献度分析レポートを実行します。
title: 貢献度分析の実行
uuid: 5282a5f9-0771-4974-93cb-335204bde114
feature: AI Tools
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 99%

---


# 貢献度分析の実行

貢献度分析は、Adobe Analytics で異常値と見なされた結果に貢献した要因を発見するために設計された、集中的な機械学習プロセスです。目的は、ユーザーが、別の方法よりもずっと迅速に、焦点を当てるべき領域や追加の分析のオポチュニティを見つけるのを支援することです。

## 貢献度分析の実行 {#section_7D2C5E48A5664727941DF4C90976D9DC}

プロジェクトで貢献度分析を呼び出すには、2 つの方法があります。

* 毎日の精度のフリーフォームテーブルで、任意の行を右クリックして、「**[!UICONTROL 貢献度分析を実行]**」を選択します。異常値が表示されていない行でも実行できます。

   >[!NOTE]
   >
   >貢献度分析は、現在、毎日の精度でのみサポートされています。

   ![](assets/run_ca.png)

* 折れ線グラフでは、折れ線グラフの異常値データポイントの上にマウスポインターを置きます。表示される&#x200B;**[!UICONTROL 分析]**&#x200B;リンクをクリックします。

   ![](assets/contribution-analysis.png)

1. （オプション）折れ線グラフまたはテーブルで「**[!UICONTROL 貢献度分析を実行]**」をクリックしたら、[ディメンションを除外](#section_F6932F4BF74544B5872164E7B1E0C6FC)することで、分析の範囲を狭める（その結果、スピードアップする）ことができます。

1. 貢献度分析が読み込まれるまでしばらく待ちます。レポートスイートのサイズおよびディメンションの数によって、これには、かなりの時間がかかる可能性があります。貢献度分析は、ディメンションあたり上位 50,000 項目の分析を実行します。
1. 次に、このプロジェクト内に直接新しい貢献度分析パネルが読み込まれます。以前 Reports &amp; Analytics の貢献度分析を使用したことがあるユーザーは、多くのパネルを既に目にしたことがあるでしょう。

   * その日の&#x200B;**訪問**&#x200B;数を表示するビジュアライゼーション。
   * コンテキストに関する毎月の&#x200B;**訪問トレンドライン**。
   * [貢献度スコア](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html)で並べ替えられた、この異常値に貢献した&#x200B;**トップアイテム**。加えて、問題の指標と、サイズの観点から指標を文脈の中で捉えるためのユニーク訪問者指標。

   * [生成されたセグメント](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-build.html)（トップアイテムクラスター）テーブルは、貢献度スコア、異常値の発生数、異常な指標に貢献する全体的な割合に基づいて、トップアイテムの関連性を識別します。これは、その後、オーディエンスセグメントとしてキャプチャされます（貢献度セグメント 1、貢献度セグメント 2 など）。「i」（情報）ボタンをクリックすると、構成する上位の項目を含む、各自動セグメントの定義が表示されます。

      ![](assets/auto_segment.png)

1. 貢献度分析は、Analysis Workspace の一部なので、テーブルの右クリックメニューから数多くの機能を活用して、分析を一層意味のあるものにすることができます。例えば、次のような機能があります。

   * [各ディメンション項目を別のディメンションで分類する](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [1 つまたは複数の行のトレンドを示す](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [新しいビジュアライゼーションを追加する](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [アラートを作成する](/help/components/c-alerts/intellligent-alerts.md)
   * [セグメントを作成したり比較したりする](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>貢献度分析およびそれにリンクされたインテリジェントアラートプロジェクトで、分析された異常値が青い点でハイライト表示されます。これにより、分析された異常値がより明確に示されます。

## ディメンションの貢献度分析からの除外 {#section_F6932F4BF74544B5872164E7B1E0C6FC}

貢献度分析から一部のディメンションを除外したい場合があります。例えば、ブラウザーまたはハードウェア関連のディメンションは関係がなく、これらを削除することで分析を高速化したい場合です。

1. 「**[!UICONTROL 貢献度分析を実行]**」（または折れ線グラフの「**[!UICONTROL 分析]**」）をクリックすると、**[!UICONTROL 除外されたディメンション]**&#x200B;パネルが表示されます。

1. 不要なディメンションを&#x200B;**[!UICONTROL 除外されたディメンション]**&#x200B;パネルにドラッグして、「**[!UICONTROL デフォルトとして設定]**」をクリックしてリストを保存します。または、「**[!UICONTROL すべてクリア]**」をクリックして、除外するディメンションを選択することからやり直します。

   ![](assets/exclude_dimensions.png)

1. 除外するディメンションを追加したら（または除外しないものを選択したら）、もう一度「**[!UICONTROL 貢献度分析を実行]**」をクリックします。
1. 除外されたディメンションのリストを変更する必要がある場合はいつでも、ディメンションをダブルクリックすると、除外されたディメンションのリストが表示されます。

   ![](assets/excluded-dimensions.png)

1. 不要なディメンションの隣にある x をクリックして削除し、「**[!UICONTROL デフォルトとして設定]**」をクリックしてリストを保存します。

