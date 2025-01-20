---
title: フリーフォームテーブル
description: フリーフォームテーブルは、Workspace のデータ分析の基盤となっています。
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 64%

---

# フリーフォームテーブル {#freeform-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="フリーフォームテーブル"
>abstract="ディメンション、セグメント、指標および日付範囲を使用して作成できる、空のフリーフォームテーブルのビジュアライゼーションを作成します。フリーフォームテーブルを他のビジュアライゼーションの基礎として使用できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics![ でのフリーフォームテーブルのビジュアライゼーションについて説明します**。_<br/>_この記事の [CustomerJourneyAnalytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/freeform-table)_ _**Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) バージョンについては、![ フリーフォームテーブル** を参照してください。_

>[!ENDSHADEBOX]

Analysis Workspaceでは、フリーフォームテーブルはインタラクティブなデータ分析の基盤となっています。[コンポーネント](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=ja)の組み合わせを行と列にドラッグ＆ドロップして、分析用のカスタムテーブルを作成できます。各コンポーネントがドロップされると、テーブルは直ちに更新されるので、分析したり、深く掘り下げたりすることができます。

## シンプルなフリーフォームテーブルの作成

空のフリーフォームテーブルから開始します。

![ 空のフリーフォームテーブル ](assets/freeform-table-1.png)

**[!UICONTROL ** 指標（または他のコンポーネント）に **[!UICONTROL ** 訪問回数 **]** 指標をドロップ **]** すると、フリーフォームテーブルには、選択したカレンダー期間の 1 日あたりの訪問回数が自動的に入力されます。

![ 訪問回数フリーフォームテーブル ](assets/freeform-table-2.png)

次に、**[!UICONTROL ** ページ **]** ディメンションをドロップして **[!UICONTROL ** 日 **]** ディメンション列を置き換えると、フリーフォームテーブルに各ページの訪問回数が自動的に反映されます。

![ ページ別の訪問回数フリーフォームテーブル ](assets/freeform-table-3.png)

次に、**[!UICONTROL ** マーケティングチャネル **]** ディメンションを **[!UICONTROL ** category:5 **]** 行にドロップして、**[!UICONTROL ** category:5 **]** ページなどを分類できます。

![ ページ別の訪問数の分類フリーフォームテーブル ](assets/freeform-table-4.png)


## 自動化されたテーブル

上図のように、テーブルを作成する最も簡単な方法は、空のプロジェクト、パネルまたはフリーフォームテーブルにコンポーネントを直接ドロップすることです。 推奨される形式のフリーフォームテーブルが自動的に作成されます。[こちら](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=ja)から、チュートリアルをご覧ください。

![](assets/automated-table.png)

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、フリーフォームテーブルビルダーを有効にできます。ビルダーを有効にすれば、多くのディメンション、分類、指標およびセグメントをドラッグ&amp;ドロップして、より複雑な質問に回答するテーブルを作成できます。 データはその場では更新されず、「**[!UICONTROL ビルド]**」をクリックすると更新されます。

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
* 右クリック/**[!UICONTROL プロジェクト/項目を CSV としてダウンロード]** を選択すると、選択したディメンションに対して最大 50,000 個のディメンション項目が書き出されます。

Analysis Workspace のすべてのデータエクスポートオプションについては、[こちら](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja)から確認できます。

![](assets/export-options.png)

## ビデオ

フリーフォームテーブルビルダーの概要：

>[!VIDEO](https://video.tv.adobe.com/v/31318/?quality=12)

フリーフォームテーブルフィルター：

>[!VIDEO](https://video.tv.adobe.com/v/23232/?quality=12)

フリーフォームテーブルの合計：

>[!VIDEO](https://video.tv.adobe.com/v/29273/?quality=12)
