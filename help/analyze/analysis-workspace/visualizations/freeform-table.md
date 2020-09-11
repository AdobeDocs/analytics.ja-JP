---
title: フリーフォームテーブル
description: フリーフォームテーブルとフリーフォームテーブルビルダーについて説明します
translation-type: tm+mt
source-git-commit: 677539632878655a6e573176321b59b531e1ab2c
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 100%

---


# フリーフォームテーブル

Analysis Workspace では、フリーフォームテーブルは、単なるデータテーブルではなく、インタラクティブなビジュアライゼーションです。[コンポーネント](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html)の組み合わせを行と列にドラッグ＆ドロップして、分析用のカスタムテーブルを作成できます。各コンポーネントがドロップされると、テーブルが直ちに更新され、迅速な分析が可能になります。

テーブルは、様々な方法でカスタマイズできます。

* **行**
   * 各ディメンション行は、ページネーションの前に最大 400 行を表示できます。プロジェクトの[表示密度](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)を調整すると、1 つの画面に表示する行を増やすことができます。
   * 行は、追加のコンポーネントで分類できます。複数の行を一度に分類するには、複数の行を選択し、次のコンポーネントを選択した行の上にドラッグします。[分類](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)について説明します。
   * 行を[フィルタリング](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html)して、表示する項目数を減らすここができます。[行設定](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html)で追加の設定を使用できます。

* **列**
   * 列内にコンポーネントを積み重ねて、セグメント化された指標やクロスタブ分析などを作成できます。
   * 各列の表示は、[列設定](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)で調整できます。
   * [右クリックメニュー](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)からは、いくつかの操作を実行できます。テーブルのヘッダー、行または列をクリックしたかどうかに応じて、このメニューに表示されるアクションが変わります。

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、フリーフォームテーブルビルダーを有効にできます。ビルダーを有効にすれば、多くのディメンション、分類、指標およびセグメントをドラッグ＆ドロップして、より複雑な質問に回答するテーブルを作成できます。データはその場では更新されず、「**[!UICONTROL ビルド]**」をクリックすると更新されます。

データに関する複雑な質問があり、質問に答えるために表を作成したいときに、テーブルビルダーを使用すると時間を節約できます。テーブルビルダーのその他の利点は、次のとおりです。

* 各アクションがレンダリングされるのを待たずに、必要な形式でテーブルを配置できる。
* 最大 4 レベルの分類をすばやく実行できる。
* テーブルの行とディメンションの列ごとに、行と分類の設定を定義できる。
* デフォルトでは、テーブルの各レベルを&#x200B;**[!UICONTROL 位置で分類]**&#x200B;できる（従来のフリーフォームテーブルの場合、デフォルトは「**[!UICONTROL 項目で分類]**」です)。
* テーブル内の静的な行の順序を手動で指定できる。例：指標行を特定の順序で表示する場合など。
* 実際のデータをレンダリングする前に、テーブルの形式をプレビューします。

[ここ](https://youtu.be/GUMWiJAmMGI)でフリーフォーム表ビルダーの動作を確認します。

## フリーフォームテーブルデータの書き出し

フリーフォームテーブルのデータは、次の方法で Analysis Workspace からコピーできます。

* テーブルヘッダーを右クリックし、「**[!UICONTROL クリップボードにコピー]**」を選択します。これにより、（表示可能な）テーブル全体を書き出します。
* テーブル内の特定のセルをハイライト表示し、右クリックして「**[!UICONTROL クリップボードにコピー]**」を選択するか、Ctrl + C ホットキーを使用します。
* **[!UICONTROL プロジェクト／CSV をダウンロード]**。これにより、プロジェクト内の表示可能なすべてのテーブルが CSV 形式で書き出されます。
