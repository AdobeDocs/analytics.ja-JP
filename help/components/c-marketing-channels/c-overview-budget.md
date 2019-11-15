---
description: チャネルにコストと予算額を割り当てる方法を説明します。
solution: Analytics
subtopic: Marketing channels
title: コストと予算
topic: Reports and analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# コストと予算

チャネルにコストと予算額を割り当てる方法を説明します。

コストは、そのチャネルに費やした費用を示します。予算とは、使用可能な金額を表します。

投資利益率（ROI）を確認する方法の一つは、売上高からコストを引いた額を示す計算指標を作成することです。また、合計コストおよび新規のエンゲージメント当たりのコストの分類を示す計算指標を作成する方法もあります。例えば、新規のエンゲージメントを示す[!UICONTROL ファーストタッチチャネル]レポートを実行し、計算指標を作成して新規のエンゲージメント当たりのコストを示すファーストタッチコスト指標を追加することが可能です。

詳しくは、 [マーケティングチャネルレポートで使用される計算指標](/help/components/c-marketing-channels/c-channel-calc-metrics.md).

チャネルにはコストと予算額のみを割り当てることができます。すべてのコストに対して、レポート内で適用される期間が示されます。コストをチャネルに直接関連付けると、チャネル内のキャンペーンごとのコストの内訳を示すために配分指標が選択されます。

コストおよび予算項目を追加した後で、表のデータを CSV ファイルにエクスポートできます。また、CSV ファイルをマーケティングチャネル コストページにインポートすることも可能です。

## コストと予算項目の追加 {#add-cost-and-budget}

コストと予算項目をマーケティングチャネルに追加します。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. [!UICONTROL Report Suite Manager] ページで、レポートスイートを選択します。
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. On the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Add Cost Item]** or **[!UICONTROL Add Budget Item]**.
1. Click **[!UICONTROL Save.]**

   To continue adding cost items, click **[!UICONTROL Save and Add Another]**.

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#mktg-channel-costs}

「マーケティングチャネルのコスト（または予算）」のフィールドの定義です。

| フィールド | 定義 |
|--- |--- |
| 名前 |  コストまたは予算項目の名前（SAINT を使用している場合、これがキー値となります）。 |
| チャネル | この金額を関連付けるチャネル。ファーストタッチチャネルまたはラストタッチチャネルにコストまたは予算を割り当てるかどうかを指定します。ファーストタッチコストの金額を 1 度限りの新規のエンゲージメントとして考えます。ラストタッチコストの金額は、クリックスルーのために使用します。 |
| 期間 | この金額を使用したい期間。 |
| タイプ | コストまたは予算のタイプ。「レート」または「1 回のみのコスト」のいずれか。「レート」はクリック 1 回あたりの金額など、継続的なコストを指します。「1 回のみのコスト」では、「以下により配分」の金額を指定できます。たとえばクリックあたりのコストを配分する場合、合計クリック数の 60% を占めるアフィリエイトは、合計コストの 60% に関連付けます。配布元値は、数値分類に分ける際に使用する指標です。 |
| ファイルのエクスポート | 表のデータを CSV ファイルにエクスポートできます。 |
| ファイルのインポート | CSV ファイルをマーケティングチャネルのコスト設定ページにインポートできます。 |
