---
title: フリーフォームテーブル
description: フリーフォームテーブルは、Workspaceのデータ分析の基盤です
translation-type: tm+mt
source-git-commit: ae04b10edb35f15e552527948b5b7d57c175f562
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 59%

---


# フリーフォームテーブル

Analysis Workspaceでは、フリーフォームテーブルはインタラクティブなデータ分析の基盤となっています。 You can drag and drop a combination of [components](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) into rows and columns to create a custom table for your analysis. 各コンポーネントが削除されると、テーブルは直ちに更新されるので、分析や掘り下げを迅速に行うことができます。

## 自動化されたテーブル

テーブルを最もすばやく作成するには、空のプロジェクト、パネルまたはフリーフォームテーブルにコンポーネントを直接ドロップします。 推奨の形式で自動的にフリーフォームテーブルが作成されます。 [チュートリアルを見る](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html)。

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、フリーフォームテーブルビルダーを有効にできます。ビルダーを有効にすれば、多くのディメンション、分類、指標およびセグメントをドラッグ＆ドロップして、より複雑な質問に回答するテーブルを作成できます。データはその場では更新されず、「**[!UICONTROL ビルド]**」をクリックすると更新されます。「 [フリーフォーム表ビルダー」のチュートリアルをご覧ください](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-freeform-table-builder-in-analysis-workspace.html)。

データに関する複雑な質問があり、質問に答えるために表を作成したいときに、テーブルビルダーを使用すると時間を節約できます。テーブルビルダーのその他の利点は、次のとおりです。

* 各アクションがレンダリングされるのを待たずに、必要な形式でテーブルを配置できる。
* 最大 4 レベルの分類をすばやく実行できる。
* テーブルの行とディメンションの列ごとに、行と分類の設定を定義できる。
* デフォルトでは、テーブルの各レベルを&#x200B;**[!UICONTROL 位置で分類]**&#x200B;できる（従来のフリーフォームテーブルの場合、デフォルトは「**[!UICONTROL 項目で分類]**」です）。
* テーブル内の静的な行の順序を手動で指定できる。例：指標行を特定の順序で表示する場合など。
* 実際のデータをレンダリングする前に、テーブルの形式をプレビューします。

## テーブルの操作

フリーフォームテーブルは、様々な方法で操作およびカスタマイズできます。

* **行**
   * プロジェクトの[表示密度](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)を調整すると、1 つの画面に表示する行を増やすことができます。
   * 各ディメンション行は、ページネーションの前に最大 400 行を表示できます。「行」の横の数字をクリックして、ページにさらに行を表示します。 ヘッダーのページ矢印を使用して、別のページに移動します。
   * 行は、追加のコンポーネントで分類できます。複数の行を一度に分類するには、複数の行を選択し、次のコンポーネントを選択した行の上にドラッグします。[分類](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)について説明します。
   * 行を[フィルタリング](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html?lang=ja-JP)して、表示する項目数を減らすここができます。[行設定](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html)で追加の設定を使用できます。

* **列**
   * 列内にコンポーネントを積み重ねて、セグメント化された指標やクロスタブ分析などを作成できます。
   * 各列の表示は、[列設定](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)で調整できます。
   * [右クリックメニュー](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)からは、いくつかの操作を実行できます。テーブルのヘッダー、行または列をクリックしたかどうかに応じて、このメニューに表示されるアクションが変わります。

## フリーフォームテーブルデータの書き出し

フリーフォームテーブルのデータは、次の方法で Analysis Workspace からコピーできます。

* 右クリックし、「データをクリップボードに **[!UICONTROL コピー]** 」をクリックして、表示されたデータを書き出します。 テーブルを選択した場合、このオプションは「選択範囲をクリップボードに **[!UICONTROL コピー]**」と表示します。 また、 **Ctrl + Cホットキーを押すと** 、選択したデータがコピーされます。
* 右クリック/データをCSVとして **[!UICONTROL ダウンロード]** (Download data as CSV)を選択すると、表示されたデータがCSVとしてダウンロードされます。 テーブルを選択した場合、このオプションでは「選択範囲をCSVとして **[!UICONTROL ダウンロード]**」と表示されます。
* 右クリック/ **[!UICONTROL プロジェクト/項目をCSVとしてダウンロード]** ：選択したディメンションに対して最大50,000個のディメンション項目がエクスポートされます。

Analysis Workspaceのすべてのデータ [書き出しオプション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html) 。
