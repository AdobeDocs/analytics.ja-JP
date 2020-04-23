---
description: Analysis Workspace のビジュアライゼーションおよびビジュアライゼーション設定について説明します。
keywords: Analysis Workspace
title: ビジュアライゼーションの概要
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# ビジュアライゼーションの概要

Workspaceオファーには、棒グラフ、ドーナツグラフ、ヒストグラム、折れ線グラフ、マップ、散布グラフなど、データを視覚的に表現する様々なビジュアライゼーションが含まれています。 各ビジュアライゼーションには、独自の設定があり、管理できます。 ビジュアライゼーションの名前をクリックすると、詳細情報が表示されます。

YouTubeビデオ：分析 [ワークスペースのビジュアライゼーション](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) のタイプ(2:57)

| ビジュアライゼーション名 | 説明 |
|---|---|
| [面グラフ](/help/analyze/analysis-workspace/visualizations/area.md) | 折れ線グラフのように見えますが、線の下に色付きの領域があります。 複数の指標があり、複数の指標の交差で表される領域を視覚化する場合は、面グラフを使用します。 |
| [棒グラフ](/help/analyze/analysis-workspace/visualizations/bar.md) | 1つ以上の指標の様々な値を表す縦棒グラフを表示します。 |
| [ブレットグラフ](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 目的の値が他のパフォーマンス範囲（目標）と比較または測定される方法を示します。 |
| [コホートテーブル](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* とは、特定の期間、共通の特性を共有する人々のグループのことです。コホート分析は、例えば、コホートがブランドとどのように関わっているかを学ぶ場合に便利です。トレンドの変更を簡単に見分けて、それに応じて対応できます |
| [ドーナツ](/help/analyze/analysis-workspace/visualizations/donut.md) | 円グラフと同様に、このビジュアライゼーションはデータを全体の一部またはセグメントとして表示します。 |
| [フォールアウト](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | フォールアウトレポートは、事前に指定した一連のページ間で、訪問者が離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。 |
| [フロー](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | Webサイトやアプリを通る顧客パスを表示します。 |
| [フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table.md) | フリーフォームテーブルは、単なるデータテーブルではなく、インタラクティブなビジュアライゼーションです。 |
| [ヒストグラム](/help/analyze/analysis-workspace/visualizations/histogram.md) | ヒストグラムは棒グラフに似ていますが、数値を範囲（グループ）にグループ化します。 |
| [横棒グラフ](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 1つ以上の指標の様々な値を表す横棒グラフを表示します。 |
| [行](/help/analyze/analysis-workspace/visualizations/line.md) | 一定期間の値の変化を示す線を使用して指標を表します。 折れ線グラフは、時間がディメンションとして使用されている場合にのみ使用できます。 |
| [マップ](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 任意の指標（計算指標を含む）のビジュアルマップを作成できます。 |
| [散布図](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | ディメンション値と最大3つの指標の関係を表示します。 |
| [概要番号](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | このビジュアライゼーションは、選択したセルに応じて、合計と概要を表示します。 |
| [変更の概要](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | このビジュアライゼーションでは、選択されているセルに応じて、セルが相互に比較されます。 |
| [テキスト](/help/analyze/analysis-workspace/visualizations/text.md) | ユーザー定義のテキストを Workspace に追加できます。 |
| [ツリーマップ](/help/analyze/analysis-workspace/visualizations/treemap.md) | 階層（ツリー構造）のデータをネストされた長方形のセットとして表示します。 |
| [ベン](/help/analyze/analysis-workspace/visualizations/venn.md) | 最大3つのセグメント（コンポーネントから）と1つの指標をドラッグして、ベン図を作成できます。 |

## ビジュアライゼーションパネル {#section_DC07F032FBEF4046A40F7B95C28DA018}

To display the Visualizations panel, click **[!UICONTROL Visualizations]** in the side panel.

![手順の結果](assets/visualizations.png)

Adobe Analytics を使用したことのあるユーザーにとって、大半のビジュアライゼーションタイプ（面グラフ、棒グラフ、ドーナツグラフ、折れ線グラフなど）は馴染みのあるものです。ただし、分析ワークスペースにはビジュアライゼーション設定が含まれ、インタラクティブ機能を備えた新しいまたは独自のビジュアライゼーションタイプが多数用意されています。

## ビジュアライゼーション設定 {#section_D3BB5042A92245D8BF6BCF072C66624B}

アクセスする [!UICONTROL Visualization Settings]には、ビジュアライゼーションをにド [!UICONTROL Freeform Panel]ラッグし、歯車アイコンをク [!UICONTROL Visualization Settings] リックします。

>[!IMPORTANT]
>
>どのビジュアライゼーション設定が表示されるかは、ビジュアライゼーションの種類によって決まります。すべてのビジュアライゼーションに適用される設定はありません。 また、一部の詳細設定は、ヒストグラ **ム設定** など、特定のビジュアライゼーションに対してのみ表 [示されます](/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)。

![](assets/visualization_settings.png)

| 設定 | 説明 |
|--- |--- |
| 割合（％） | 値をパーセントで表示します。 |
| 100% 積み重ね | 積み重ね面グラフ、積み重ね面グラフ、横棒グラフ、横棒グラフの積み重ね面グラフの各設定を使用すると、グラフが「100%積み重ね」のビジュアライゼーションに変換されます。 例：![](assets/stacked_100_percent.png) |
| 凡例を表示 | 数の概要/変更概要ビジュアライゼーションのフィルターの詳細テキストを非表示にできます。 |
| 最大項目数の制限 | ビジュアライゼーションで表示する項目数を制限できます。 |
| Y 軸をゼロに固定 | グラフにプロットされるすべての値が0より大きい場合、グラフのデフォルトでは、Y軸の下端が0以外になります。 このチェックボックスをオンにすると、Y軸が強制的にゼロに設定され、グラフが再描画されます。 |
| 正規化 | 指標を均等な比率にします。 |
| 二重軸を表示 | 2 つの指標がある場合にのみ適用されます。（ある指標の）Y 軸を左側に、（他の指標の）Y 軸を右側に表示できます。 |
| 異常値を表示 | 折れ線グラフとフリーフォームテーブルを拡張して、データの異常値を表示します。 |

## ビジュアルを作成アイコン {#section_9C11D9DEDC42413AA53E69A71A509DFC}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row. このアイコンは、テーブル行の上にカーソルを置くと表示されます。 クリックすると、分析ワークスペースに、データに最も適したビジュアライゼーションを学歴に基づいて推測するよう求められます。 例えば、最大3つのセグメントを選択した場合、ベン図が作成されます。 3 セグメントを超える場合、棒グラフが作成されます。その他のタイプのデータの場合は、折れ線グラフなどを作成できます。

![](assets/create-visual.png)

## 右クリックビジュアライゼーション／パネルメニュー {#section_05B7914D4C9E443F97E2BFFDEC70240C}

グラフのコンテキスト設定は、ビジュアライゼーションまたはパネルのヘッダーの横を右クリックするとアクセスできます。 次の設定の一部またはすべてを使用できます。

![](assets/right-click_menu.png)

| 設定 | 説明 |
|--- |--- |
| コピーしたビジュアライゼーション/パネルの挿入 | 要素をコピーした場所をプロジェクト内の別の場所に貼り付けたり、完全に別のプロジェクトに貼り付けたり（「挿入」）できます。 |
| ビジュアライゼーション/パネルのコピー | 右クリックして、ビジュアライゼーションまたはパネルをコピーできます。 |
| 重複の視覚化/パネル | 現在のビジュアライゼーションの正確な重複を作成し、変更できます。 |
| すべてのパネルを折りたたむ | すべてのプロジェクトパネルを折りたたみます。 |
| パネル内のすべてのビジュアライゼーションを折りたたむ | このプロジェクトパネル内のすべてのビジュアライゼーションを折りたたみます。 |
| すべてのパネルを展開 | すべてのプロジェクトパネルを展開します。 |
| パネル内のすべてのビジュアライゼーションを展開 | このプロジェクトパネル内のすべてのビジュアライゼーションを展開します。 |
| 説明の編集 | ビジ追加ュアライゼーション/パネルの説明テキストを編集（または編集）します。 この説明は、プロジェクト／プロジェクト情報および設定に表示されます。 |
| パネルリンクの取得 | プロジェクト内の特定のパネルにユーザーを誘導できます。 |
| ビジュアライゼーションリンクの取得 | このリンクをコピーして共有し、他のユーザーをこのビジュアライゼーションに直接送信できます。 ユーザーはログインする必要があります。 |
| 開始オーバー | （フロー、ベン、ヒストグラムで機能）現在のビジュアライゼーションの設定を削除し、新しいパネルを開いて再設定できます。 |

## 凡例ラベルの編集 {#section_94F1988CB4B9434BA1D9C6034062C3DE}

ビジュアライゼーションの凡例（フォールアウト、領域、積み重ね面、棒グラフ、棒グラフ、ドーナツグラフ、ヒストグラム、横棒グラフ、横棒グラフ、積み重ね面グラフ、折れ線グラフ、散布図、ベン図）のシリーズ名を変更して、ビジュアライゼーションをより消耗させます。

凡例の編集は次に適 **用され** ません：ツリーマップ、箇条書き、変更の概要または数値、テキスト、フリーフォーム、ヒストグラム、コホートまたはフローのビジュアライゼーション。

折れ線グラフの凡例ラベルを編集するには、次のようにします。

1. 凡例ラベルの1つを右クリックします。
1. クリック **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. 新しいラベルテキストを入力します。
1. Press **[!UICONTROL Enter]** to save.

このトピックに関する[ビデオへのリンクはこちら](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)です。
