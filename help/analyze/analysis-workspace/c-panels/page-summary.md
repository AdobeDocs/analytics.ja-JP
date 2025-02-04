---
description: ページの概要パネルには、選択したページの概要情報が表示されます。
title: ページの概要パネル
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 28%

---

# ページの概要パネル {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="ページの概要"
>abstract="いくつかの高レベルの指標と、特定のページ間の移動をすばやく確認します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="ページの概要パネル"
>abstract="いくつかの高レベルの指標と、特定のページ間の移動をすばやく確認します。<br/><br/>**パラメーター&#x200B;**<br/>**ページディメンション項目を追加**：コンポーネントパネルを開き、ページディメンションを見つけて、キャレットをクリックして展開し、ディメンション項目を表示します。  次に、詳しく知りたい特定のページをビルダーにドラッグ＆ドロップします。ディメンション項目をドラッグ＆ドロップすると、ページに関する主要な情報がレポートに自動的に入力されます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事は、![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_**Adobe Analytics_ のページの概要パネルに関する説明です**。_<br/>__ CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) ![4}Customer Journey Analytics **には、同等のパネルがありません。__**

>[!ENDSHADEBOX]

**[!UICONTROL ページの概要]** パネルを使用すると、特定のページに関する主要な統計を調べることができます。

## 使用

**[!UICONTROL ページの概要]** パネルを使用するには：

1. **[!UICONTROL ページの概要]** パネルを作成します。 パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。



パネルには、{Reports[!UICONTROL  内または ]2}Workspace] 内からアクセスできます。[!UICONTROL 

| アクセスポイント | 説明 |
| --- | --- |
| [!UICONTROL レポート] | <ul><li>パネルは既にプロジェクトにドロップされています。</li><li>左側のレールが折りたたまれている。</li><li>ページディメンションのみがサポートされます。</li><li>デフォルト設定は既に適用されています。この場合は、[!UICONTROL Page] ディメンションで最も訪問されたページです。 この設定は変更できます。</li></ul> |
| Workspace | 新しいプロジェクトを作成し、左パネルのパネル アイコンを選択します。 [!UICONTROL  ページの概要 ] パネルをフリーフォームテーブルの上にドラッグします。 「[!UICONTROL Dimension項目 ] ページ」フィールドは空白のままです。 ドロップダウンリストからディメンション項目を選択します。 |

### パネル入力 {#panel-input}

[!UICONTROL  ページの概要 ] パネルは、次の入力設定を使用して設定できます。

![ ページ入力の概要 ](assets/page-summary-input.png)

| 入力 | 説明 |
| --- | --- |
| **[!UICONTROL ページ]** | 主要統計を調べるページのページディメンションを選択します。 |

{style="table-layout:auto"}


**[!UICONTROL ビルド]** を選択して、パネルをビルドします。

### パネル出力 {#panel-output}

[!UICONTROL  ページの概要 ] パネルは、特定のページに関する統計をより深く理解するのに役立つ指標データとビジュアライゼーションの豊富なセットを返します。

![ページの概要パネル](assets/page-summary-output.png)

| ビジュアライゼーション | 説明 |
| --- | --- |
| **[!UICONTROL ページビュー ] – 今月（これまで）** | 当月のこのページに対するページビュー数を表示する [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。 |
| **[!UICONTROL ページビュー ] - 4 週間前** | 先月のこのページのページビュー数を表示する [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。 |
| **[!UICONTROL ページビュー ] - 52 週間前** | 過去 1 年間のこのページのページビュー数を表示する [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。 |
| **[!UICONTROL トレンド]** | 今月、4 週間前、52 週間前のページビューのトレンド [ 折れ線グラフ ](/help/analyze/analysis-workspace/visualizations/line.md) ビジュアライゼーション。 |
| **[!UICONTROL すべてのページビューの割合]** | このページに送信されたすべてのページビューの割合を示す概要番号。 |
| **[!UICONTROL ページでの滞在時間]** | このページでの滞在時間を表示する [ 横棒グラフ ](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) ビジュアライゼーション。 |
| **[!UICONTROL 単一ページ訪問]** | このページが唯一の訪問ページだったページビューの数を示す [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)。 |
| **[!UICONTROL リロード回数]** | リロード中にディメンション項目が存在した回数を示す [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)。 訪問者によるブラウザーの更新は、再読み込みをトリガーする最も一般的な方法です。 |
| **[!UICONTROL 入口]** | 特定のディメンション項目が訪問の最初の値として取得された回数を示す [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)。 |
| **[!UICONTROL 出口]** | 特定のディメンション項目が訪問の最後の値として取得された回数を示す [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)。 |
| **[!UICONTROL フロー]** | 選択したページをフォーカルポイントとする [ フロー ](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) ビジュアライゼーション。 [ フロー ](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) ビジュアライゼーションと同様に、データをさらに詳しく調べることができます。 |

{style="table-layout:auto"}

![ 編集 ](/help/assets/icons/Edit.svg) を使用して、パネルの再設定と再構築を行います。
