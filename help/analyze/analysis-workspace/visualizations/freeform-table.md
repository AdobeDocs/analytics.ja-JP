---
title: フリーフォームテーブル
description: フリーフォームテーブルとフリーフォームテーブルビルダーについて説明します
translation-type: tm+mt
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# フリーフォームテーブル

Analysis Workspaceでは、フリーフォームテーブルは単なるデータテーブルではなく、インタラクティブなビジュアライゼーションです。 コンポーネントの組み合わせを行と列に [ドラッグ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) &amp;ドロップして、分析用のカスタムテーブルを作成できます。 各コンポーネントがドロップされると、テーブルが直ちに更新され、迅速な分析が可能になります。

テーブルは、様々な方法でカスタマイズできます。

* **行**
   * 各ディメンション行は、ページ分割が行われる前に、最大400行を表示できます。 プロジェクトのビュー密度を調整することで、1つの画面に表示する行を増やすこと [ができます](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)。
   * 行は、追加のコンポーネントで分類できます。 複数の行を一度に分類するには、単に複数の行を選択し、次のコンポーネントを選択した行の上にドラッグします。 内訳の詳細を表 [示します](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)。
   * 行をフィルターし [て](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) 、項目のセットを少なく表示できます。 行の設定で追加の設定を使 [用できます](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html)。

* **列**
   * コラム内にコンポーネントを積み重ねて、セグメント化された指標やクロスタブ分析などを作成できます。
   * 各列の表示は、列の設定で調整で [きます](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)。
   * 右クリックメニューからは、いく [つかの操作を実行できます](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)。 このメニューには、テーブルのヘッダー、行または列をクリックするかどうかに応じて、様々なアクションが表示されます。

## フリーフォームテーブルビルダー

最初に表に複数のコンポーネントを追加し、次にデータをレンダリングする場合は、フリーフォーム表ビルダーを有効にします。 ビルダーを有効にすると、多くのディメンション、分類、指標およびセグメントをドラッグ&amp;ドロップして、より複雑な質問に答えるテーブルを作成できます。 データはその場で更新されず、「ビルド」をクリックすると更新さ **[!UICONTROL れます]**。

表ビルダーは、データに関する複雑な質問があり、質問に答えるために構築する表を考えるときに、時間を節約できるオプションです。 表ビルダーのその他の利点は、次のとおりです。

* 各アクションがレンダリングされるのを待たずに、必要な形式でテーブルを配置します。
* 最大4レベルの分類をすばやく実行できます。
* テーブルの行とディメンションの列ごとに、行と分類の設定を定義します。
* **[!UICONTROL デフォルトでは]**、テーブルのすべてのレベルの「位置」で分類します(従来のフリーフォームテーブルでは、デフォル**[!UICONTROL &#x200B;トは「項目別分類]**」です)。
* テーブル内の静的な行の順序を手動で指定します。 例えば、指標行を特定の順序で表示する場合などです。
* 実際のデータをレンダリングする前に、テーブルの形式をプレビューします。

フリーフォーム表ビルダーの動作を確認し [ます](https://youtu.be/GUMWiJAmMGI)。

## フリーフォームテーブルデータの書き出し

フリーフォームテーブルのデータは、次の方法でAnalysis Workspaceからコピーできます。

* テーブルヘッダーを右クリックし、「クリップボードにコ **[!UICONTROL ピー」を選択しま]**す。 これにより、（表示可能な）テーブル全体がエクスポートされます。
* テーブル内の特定のセルをハイライト表示し、右クリックして「ク **[!UICONTROL リップボードにコピー]**」を選択するか、Ctrl + cホットキーを使用します。
* **[!UICONTROL プロジェクト/CSVをダウンロード]**。 これにより、プロジェクト内の表示可能なすべてのテーブルがCSVとしてエクスポートされます。
