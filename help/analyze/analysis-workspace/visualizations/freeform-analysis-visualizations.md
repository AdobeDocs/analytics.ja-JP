---
description: Analysis Workspace のビジュアライゼーションおよびビジュアライゼーション設定について説明します。
keywords: Analysis Workspace
title: ビジュアライゼーションの概要
translation-type: tm+mt
source-git-commit: b952ea84a63cdb73684e8765dde6551785c0d6c1
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 97%

---


# ビジュアライゼーションの概要

Workspace オファーには、棒グラフ、ドーナツグラフ、ヒストグラム、折れ線グラフ、マップ、散布図など、データを視覚的に表現する様々なビジュアライゼーションがあります。各ビジュアライゼーションには、管理可能な独自の設定があります。ビジュアライゼーションの名前をクリックすると、詳細情報が表示されます。

Video tutorial: [Visualization Types in Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/visualization-types.html) (2:57)

| ビジュアライゼーション名 | 説明 |
|---|---|
| [面グラフ](/help/analyze/analysis-workspace/visualizations/area.md) | 折れ線グラフに似ていますが、線の下に色付きの領域があります。指標が複数あり、2 個以上の指標の交差により表現される領域を視覚化する場合は、面グラフを使用します。 |
| [棒グラフ](/help/analyze/analysis-workspace/visualizations/bar.md) | 1 つ以上の指標の様々な値を表す縦棒グラフが表示されます。 |
| [ブレットグラフ](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 目的の値が、他のパフォーマンス範囲（目標）と照らし合わせて、どのように比較または測定されるかを示します。 |
| [コホートテーブル](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* とは、特定の期間、共通の特性を共有する人々のグループのことです。コホート分析は、例えば、コホートがブランドとどのように関わっているかを学ぶ場合に便利です。トレンドの変更を簡単に見分けて、それに応じて対応できます |
| [ドーナツ](/help/analyze/analysis-workspace/visualizations/donut.md) | このビジュアライゼーションは、円グラフと同様に、データを全体の一部または断片として表示します。 |
| [フォールアウト](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | フォールアウトレポートは、事前に指定した一連のページ間で、訪問者が離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。 |
| [フロー](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | Web サイトおよびアプリの顧客パスを表示します。 |
| [フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | フリーフォームテーブルは、単なるデータテーブルではなく、インタラクティブなビジュアライゼーションです。 |
| [ヒストグラム](/help/analyze/analysis-workspace/visualizations/histogram.md) | ヒストグラムは、棒グラフに似ていますが、数を範囲（グループ）でグループ化します。 |
| [横棒グラフ](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 1 つ以上の指標の様々な値を表す横棒グラフが表示されます。 |
| [行](/help/analyze/analysis-workspace/visualizations/line.md) | 時間の経過に伴う値の変化を確認できるように、折れ線で指標が表されます。折れ線グラフは、時間がディメンションとして使用される場合にのみ使用できます。 |
| [マップ](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 任意の指標（計算指標を含む）のビジュアルマップを作成できます。 |
| [散布図](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | ディメンション項目と最大 3 つの指標の関係を表示します。 |
| [概要番号](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | このビジュアライゼーションは、選択したセルに応じて、合計と概要を表示します。 |
| [変更の概要](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | このビジュアライゼーションでは、選択されているセルに応じて、セルを互いに比較します。 |
| [テキスト](/help/analyze/analysis-workspace/visualizations/text.md) | ユーザー定義のテキストを Workspace に追加できます。 |
| [ツリーマップ](/help/analyze/analysis-workspace/visualizations/treemap.md) | ネストされた長方形の集まりとして、（ツリー構造の）階層データが表示されます。 |
| [ベン](/help/analyze/analysis-workspace/visualizations/venn.md) | （コンポーネントから）最大 3 セグメントおよび 1 つの指標をドラッグして、ベン図を作成できます。 |

## ビジュアライゼーションパネル {#section_DC07F032FBEF4046A40F7B95C28DA018}

ビジュアライゼーションパネルを表示するには、サイドパネルで「**[!UICONTROL ビジュアライゼーション]**」をクリックします。

![手順の結果](assets/visualizations.png)

Adobe Analytics を使用したことのあるユーザーにとって、大半のビジュアライゼーションタイプ（面グラフ、棒グラフ、ドーナツグラフ、折れ線グラフなど）は馴染みのあるものです。しかし、Analysis Workspace にはビジュアライゼーション設定があり、インタラクティブ機能を備えた新しいまたは独自のビジュアライゼーションタイプを数多く揃えています。

## ビジュアライゼーション設定 {#section_D3BB5042A92245D8BF6BCF072C66624B}

「[!UICONTROL ビジュアライゼーション設定]」にアクセスするには、[!UICONTROL フリーフォームパネル]にビジュアライゼーションをドラッグした後、[!UICONTROL ビジュアライゼーション設定]ギアアイコンをクリックします。

>[!IMPORTANT]
>
>どのビジュアライゼーション設定が表示されるかは、ビジュアライゼーションの種類によって決まります。すべてのビジュアライゼーションにすべての設定が適用されるわけではありません。さらに一部の詳細設定は、特定のビジュアライゼーションの場合に&#x200B;**のみ**&#x200B;表示されます（例えば[ヒストグラム設定](/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)）。

![](assets/visualization_settings.png)

| 設定 | 説明 |
|--- |--- |
| 割合（％） | 値を割合で表示します。 |
| 100% の積み重ね | この設定は、積み重ね面、積み重ね棒または積み重ね横棒グラフのビジュアライゼーションを「100% の積み重ね」に変更します。例：![](assets/stacked_100_percent.png) |
| 凡例を表示 | 数値の概要／変更概要ビジュアライゼーションのフィルター詳細テキストを隠すことができます。 |
| 項目数の上限を設定 | ビジュアライゼーションで表示する項目の数を制限できます。 |
| Y 軸をゼロに固定 | グラフに示されるすべての値がゼロよりもかなり上の場合、グラフのデフォルトでは、Y 軸の一番下はゼロ以外になります。このボックスをチェックすると、Y 軸は強制的にゼロになります（グラフは再描画されます）。 |
| 正規化 | 指標を均等な比率にします。 |
| 二重軸を表示 | 2 つの指標がある場合にのみ適用されます。（ある指標の）Y 軸を左側に、（他の指標の）Y 軸を右側に表示できます。 |
| 異常値を表示 | 折れ線グラフおよびフリーフォームテーブルを強化して、データの異常値を表示します。 |

## ビジュアルを作成アイコン {#section_9C11D9DEDC42413AA53E69A71A509DFC}

どのビジュアライゼーションが選択されているかわからない場合は、テーブルの行にある&#x200B;**[!UICONTROL ビジュアルを作成]**&#x200B;アイコンをクリックします。このアイコンは、テーブルの行の上にマウスポインターを置くと表示されます。クリックすると、データに最適なビジュアライゼーションを Analysis Workspace が学習に基づいて推測することの確認が表示されます。例えば、最大 3 セグメントを選択した場合、ベン図が作成されます。3 セグメントを超える場合、棒グラフが作成されます。他のタイプのデータの場合、折れ線グラフなどが作成されます。

![](assets/create-visual.png)

## 右クリックビジュアライゼーション／パネルメニュー {#section_05B7914D4C9E443F97E2BFFDEC70240C}

グラフのコンテキスト設定は、ビジュアライゼーションまたはパネルヘッダーの隣を右クリックするとアクセスできます。次の設定の一部またはすべてを利用できます。

![](assets/right-click_menu.png)

| 設定 | 説明 |
|--- |--- |
| コピーしたビジュアライゼーション／パネルを挿入 | コピーした要素をプロジェクト内の別の場所、または完全に別のプロジェクトに貼り付ける（「挿入する」）ことができます。 |
| ビジュアライゼーション／パネルをコピー | 右クリックしてビジュアライゼーションまたはパネルをコピーできます。 |
| ビジュアライゼーション／パネルを複製 | 現在のビジュアライゼーションの厳密な複製を作成して、修正できます。 |
| すべてのパネルを折りたたむ | すべてのプロジェクトパネルを折りたたみます。 |
| パネル内のすべてのビジュアライゼーションを折りたたむ | そのプロジェクトパネルのすべてのビジュアライゼーションを折りたたみます。 |
| すべてのパネルを展開 | すべてのプロジェクトパネルを展開します。 |
| パネル内のすべてのビジュアライゼーションを展開 | そのプロジェクトパネルのすべてのビジュアライゼーションを展開します。 |
| 説明を編集 | ビジュアライゼーション／パネルの説明テキストを追加（または編集）します。この説明は、プロジェクト／プロジェクト情報および設定に表示されます。 |
| パネルリンクを取得 | プロジェクト内の特定のパネルに他のユーザーを誘導することができます。 |
| ビジュアライゼーションリンクを取得 | 他のユーザーをこのビジュアライゼーションに直接移動させるこのリンクをコピーして共有できます。ユーザーはログインする必要があります。 |
| やり直し | （フロー、ベン、ヒストグラムで動作）現在のビジュアライゼーションの設定を削除して、新しいパネルを開き、ビジュアライゼーションを再設定できます。 |

## 凡例ラベルの編集 {#section_94F1988CB4B9434BA1D9C6034062C3DE}

使いやすくするために、ビジュアライゼーション凡例の系列名を変更できます（フォールアウト、面グラフ、積み重ね面グラフ、棒グラフ、積み重ね棒グラフ、ドーナツ、ヒストグラム、横棒グラフ、積み重ね横棒グラフ、折れ線グラフ、散布図、ベン図）。

凡例の編集は、ツリーマップ、ブレットグラフ、変更概要または数値の概要、テキスト、フリーフォーム、ヒストグラム、コホートまたはフローのビジュアライゼーションには&#x200B;**適用されません**。

折れ線グラフの凡例ラベルを編集するには、例えば、次のようにします。

1. 凡例ラベルの 1 つを右クリックします。
1. 「**[!UICONTROL ラベルを編集]**」をクリックします。

   ![](assets/edit-label.png)

1. 新しいラベルテキストを入力します。
1. **[!UICONTROL Enter]** キーを押して保存します。

このトピックに関する[ビデオへのリンクはこちら](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html)です。
