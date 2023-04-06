---
title: フリーフォームテーブル
description: フリーフォームテーブルは、Workspace のデータ分析の基盤となっています。
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: 8ca676a9e69195ef873981dd390bb0a6d4d465f1
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 69%

---

# フリーフォームテーブル

Analysis Workspaceでは、フリーフォームテーブルはインタラクティブなデータ分析の基盤となっています。[コンポーネント](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=ja)の組み合わせを行と列にドラッグ＆ドロップして、分析用のカスタムテーブルを作成できます。各コンポーネントが削除されると、テーブルは直ちに更新されるので、分析や掘り下げを迅速におこなうことができます。

例として、空のフリーフォームテーブルから始めます。

![空のフリーフォームテーブル](assets/freeform-table-1.png)

次の場合、 **[!UICONTROL **&#x200B;訪問回数&#x200B;**]** 指標 **[!UICONTROL **&#x200B;ここに指標（または他のコンポーネント）をドロップ&#x200B;**]**&#x200B;を指定した場合、フリーフォームテーブルは、選択した期間の 1 日あたりの訪問数を自動的に入力します。

![訪問回数フリーフォームテーブル](assets/freeform-table-2.png)

次に **[!UICONTROL **&#x200B;ページ&#x200B;**]** 置き換えるディメンション **[!UICONTROL **&#x200B;日&#x200B;**]** ディメンション列を使用すると、フリーフォームテーブルは各ページの訪問を自動的に反映します。

![ページフリーフォームテーブル別訪問回数](assets/freeform-table-3.png)

その後、例えば **[!UICONTROL ** category:5 **]** ページをドロップして **[!UICONTROL **&#x200B;マーケティングチャネル&#x200B;**]** ディメンション **[!UICONTROL ** category:5 **]** 行

![ページフリーフォームテーブルによる訪問の分類](assets/freeform-table-4.png)


## 自動化されたテーブル

上の図に示すように、テーブルを最もすばやく作成するには、空のプロジェクト、パネルまたはフリーフォームテーブルにコンポーネントを直接ドロップします。 推奨される形式のフリーフォームテーブルが自動的に作成されます。[こちら](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=ja)から、チュートリアルをご覧ください。

![](assets/automated-table.png)

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、フリーフォームテーブルビルダーを有効にできます。ビルダーを有効にすると、多くのディメンション、分類、指標およびセグメントをドラッグ&amp;ドロップして、より複雑な質問に回答するテーブルを作成できます。 データはその場では更新されず、「 **[!UICONTROL ビルド]**.

![](assets/table-builder.png)

## テーブルの操作

フリーフォームテーブルは、様々な方法で操作およびカスタマイズできます。

* **行**
   * プロジェクトの[表示密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=ja)を調整すると、1 つの画面に表示する行を増やすことができます。
   * 各ディメンション行は、ページネーションの前に最大 400 行を表示できます。「行」の横の数字をクリックすると、ページに行が表示されます。ヘッダーのページ矢印を使用して、別のページに移動します。
   * 行は、追加のコンポーネントで分類できます。複数の行を一度に分類するには、複数の行を選択し、次のコンポーネントを選択した行の上にドラッグします。[分類](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=ja)について説明します。
   * 行を[フィルタリング](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=ja)して、表示する項目数を減らすここができます。[行設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=ja)で追加の設定を使用できます。

* **列**
   * 列内にコンポーネントを積み重ねて、セグメント化された指標やクロスタブ分析などを作成できます。
   * 各列の表示は、[列設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=ja)で調整できます。
   * [右クリックメニュー](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=ja)からは、いくつかの操作を実行できます。テーブルのヘッダー、行または列をクリックしたかどうかに応じて、このメニューに表示されるアクションが変わります。

## フリーフォームテーブルデータの書き出し

Analysis Workspace のすべてのデータエクスポートオプションについては、[こちら](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja)から確認できます。

* 右クリック >「**[!UICONTROL データソースをクリップボードにコピー]**」：表示されているテーブルデータを書き出します。テーブルを選択すると、このオプションが「**[!UICONTROL 選択範囲をクリップボードにコピー]**」に変わります。ホットキー **Ctrl + C** を使用して、選択したデータをコピーすることもできます。
* 右クリック >「**[!UICONTROL データを CSV 形式でダウンロード]**」：表示されているテーブルデータが CSV 形式でダウンロードされます。テーブルを選択すると、このオプションが「**[!UICONTROL 選択内容を CSV 形式でダウンロード]**」に変わります。
* 右クリック > **[!UICONTROL プロジェクト/項目を CSV 形式でダウンロード]** 選択したディメンションの最大 50,000 個のディメンション項目をエクスポートします。

Analysis Workspace のすべてのデータエクスポートオプションについては、[こちら](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja)から確認できます。

![](assets/export-options.png)

## ビデオ

フリーフォームテーブルビルダーの概要：

>[!VIDEO](https://video.tv.adobe.com/v/31318/?quality=12)

フリーフォームテーブルフィルター：

>[!VIDEO](https://video.tv.adobe.com/v/23232/?quality=12)

フリーフォームテーブルの合計：

>[!VIDEO](https://video.tv.adobe.com/v/29273/?quality=12)
