---
description: ビジュアライゼーションでデータを視覚的に表示します。
keywords: Analysis Workspace
title: ビジュアライゼーションの概要
feature: ビジュアライゼーション
role: Business Practitioner, Administrator
exl-id: b40aa942-4a08-4ff3-9895-e92f9a187b54
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 99%

---

# ビジュアライゼーションの概要

Workspace オファーには、棒グラフ、ドーナツグラフ、ヒストグラム、折れ線グラフ、マップ、散布図など、データを視覚的に表現する様々なビジュアライゼーションがあります。Adobe Analytics を使用すると、ほとんどのビジュアライゼーションタイプがなじみのあるものになります。しかし、Analysis Workspace にはビジュアライゼーション設定があり、インタラクティブ機能を備えた新しいまたは独自のビジュアライゼーションタイプを数多く揃えています。

ビジュアライゼーションには、Workspace の左上のアイコン、[空白のパネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=ja)、またはワークフローの右クリックメニューからアクセスできます。

![](assets/viz-rail.png)

Analysis Workspace では、次のビジュアライゼーションタイプを利用できます。

| ビジュアライゼーション名 | 説明 |
| --- | --- |
| [面グラフ](/help/analyze/analysis-workspace/visualizations/area.md) | 折れ線グラフに似ていますが、線の下に色付きの領域があります。指標が複数あり、2 個以上の指標の交差により表現される領域を視覚化する場合は、面グラフを使用します。 |
| [棒グラフ](/help/analyze/analysis-workspace/visualizations/bar.md) | 1 つ以上の指標の様々な値を表す縦棒グラフが表示されます。 |
| [ブレットグラフ](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 目的の値が、他のパフォーマンス範囲（目標）と照らし合わせて、どのように比較または測定されるかを示します。 |
| [コホートテーブル](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* とは、特定の期間、共通の特性を共有する人々のグループのことです。コホート分析は、リテンション、チャーン、または遅延の分析に役立ちます。 |
| [ドーナツ](/help/analyze/analysis-workspace/visualizations/donut.md) | このビジュアライゼーションは、円グラフと同様に、データを全体の一部または断片として表示します。 |
| [フォールアウト](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | フォールアウトレポートは、事前に指定した一連のページ間で、訪問者が離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。最終的または正確なシーケンスに設定できます |
| [フロー](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | web サイトおよびアプリを介して正確な顧客パスを表示します。 |
| [フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | フリーフォームテーブルは、単なるデータテーブルではなく、インタラクティブなビジュアライゼーションです。これは、Workspace のデータ分析の基礎になります。 |
| [ヒストグラム](/help/analyze/analysis-workspace/visualizations/histogram.md) | ヒストグラムは、指標の量に基づいて、訪問者、訪問、またはヒットをバケットにまとめます。 |
| [横棒グラフ](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 1 つ以上の指標の様々な値を表す横棒グラフが表示されます。 |
| [行](/help/analyze/analysis-workspace/visualizations/line.md) | 時間の経過に伴う値の変化を確認できるように、折れ線で指標が表されます。折れ線グラフは、X 軸で時間を表します。 |
| [マップ](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 任意の指標（計算指標を含む）のビジュアルマップを作成できます。 |
| [散布図](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | ディメンション項目と最大 3 つの指標の関係を表示します。 |
| [概要番号](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 選択したセルを 1 つの大きな数値として表示します。 |
| [変更の概要](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 選択したセル間の変化を 1 つの大きい数値/パーセントで表示します。 |
| [テキスト](/help/analyze/analysis-workspace/visualizations/text.md) | ユーザー定義のテキストを Workspace に追加できます。パネルおよびビジュアライゼーションの説明の活用に加えて、分析とインサイトにコンテキストを追加するのに役立ちます。 |
| [ツリーマップ](/help/analyze/analysis-workspace/visualizations/treemap.md) | ネストされた長方形の集まりとして、（ツリー構造の）階層データが表示されます。 |
| [ベン](/help/analyze/analysis-workspace/visualizations/venn.md) | 円を使用して、最大 3 つのセグメントの指標の重複を表します。 |

## 設定 {#settings}

各ビジュアライゼーションには、管理可能な独自の設定があります。「[!UICONTROL ビジュアライゼーション設定]」にアクセスするには、[!UICONTROL ビジュアライゼーション設定]歯車アイコンをクリックします。

![](assets/settings.png)

| 設定 | 説明 |
| --- | --- |
| ビジュアライゼーションのタイプ | データを表現するために使用するビジュアルのタイプを変更します。 |
| 精度 | トレンドのビジュアライゼーションでは、このドロップダウンから時間の精度（日、週、月など）を変更できます。この変更は、データソーステーブルにも適用されます。 |
| 割合（％） | 値を割合で表示します。 |
| 100% の積み重ね | 積み上げ面、積み上げ棒、または積み上げ横棒のビジュアライゼーションのこの設定は、グラフを「100 % の積み上げ」のビジュアライゼーションに変更します。例：![100 % の積み上げ](assets/stacked_100_percent.png) |
| 凡例を表示 | 数の概要／変更の概要ビジュアライゼーションの詳細な凡例テキストを非表示にします。 |
| 項目数の上限を設定 | ビジュアライゼーションで表示する項目の数を制限できます。 |
| Y 軸をゼロに固定 | グラフに示されるすべての値がゼロよりもかなり上の場合、グラフのデフォルトでは、Y 軸の一番下はゼロ以外になります。このボックスをチェックすると、Y 軸は強制的にゼロになります（グラフは再描画されます）。 |
| 正規化 | 指標を均等な比率にします。これは、プロットされた指標の大きさが非常に異なる場合に役立ちます。 |
| 二重軸を表示 | 2 つの指標がある場合にのみ適用されます。（ある指標の）Y 軸を左側に、（他の指標の）Y 軸を右側に表示できます。これは、プロットされた指標の大きさが非常に異なる場合に役立ちます。 |
| 異常値を表示 | 異常値検出を表示することで、折れ線グラフおよびフリーフォームテーブルを強化します。 線のビジュアライゼーションでの異常値検出には、期待値（破線）と期待範囲（影付きの帯）が含まれます。 |

## 凡例 {#legend}

ビジュアライゼーションの凡例を使用すると、ソーステーブルの日付をビジュアライゼーション内のプロットされたシリーズに関連付けることができます。 凡例はインタラクティブです。凡例項目をクリックして、ビジュアライゼーション内のシリーズの表示/非表示を切り替えることができます。 これは、視覚化するデータを簡略化する場合に便利です。

また、凡例ラベルの名前を変更して、図をより使いやすくすることができます。 注：凡例の編集は、ツリーマップ、ブレットグラフ、変更の概要／数値の概要、テキスト、フリーフォーム、ヒストグラム、コホート、またはフローのビジュアライゼーションには&#x200B;**適用されません**。

凡例ラベルを編集するには、次の手順を実行します。

1. 凡例ラベルの 1 つを右クリックします。
1. 「**[!UICONTROL ラベルを編集]**」をクリックします。

   ![](assets/edit-label.png)

1. 新しいラベルテキストを入力します。
1. **[!UICONTROL Enter]** キーを押して保存します。

このトピックに関する[ビデオへのリンクはこちら](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html)です。

## 右クリックメニュー {#right-click}

ビジュアライゼーションの追加機能は、ビジュアライゼーションのヘッダーを右クリックすると使用できます。設定は、ビジュアライゼーションによって異なります。 次の設定を使用できます。

![](assets/right-click.png)

| 設定 | 説明 |
| --- | --- |
| コピーしたパネル／ビジュアライゼーションを挿入 | コピーした要素をプロジェクト内の別の場所、または完全に別のプロジェクトに貼り付ける（「挿入」する）ことができます。 |
| ビジュアライゼーションをコピー | ビジュアライゼーションを右クリックしてコピーし、プロジェクト内の別の場所に挿入したり、完全に別のプロジェクトに挿入したりできます。 |
| [項目を CSV としてダウンロード](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja#download-items) | 選択したディメンションの最大 50,000 個のディメンション項目を CSV としてダウンロードします。 |
| [データを CSV としてダウンロード](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja?#download-data) | ビジュアライゼーションデータソースを CSV 形式でダウンロードします。 |
| 重複ビジュアライゼーション | 現在のビジュアライゼーションの厳密な複製を作成して、修正できます。 |
| 説明を編集 | ビジュアライゼーションの説明テキストを追加（または編集）します。 |
| ビジュアライゼーションリンクを取得 | プロジェクト内の特定のビジュアライゼーションに他のユーザーを誘導することができます。受信者は、リンクをクリックした後、リンク先の正確なビジュアライゼーションにリダイレクトされる前にログインするよう求められます。 |
| やり直し | （フロー、ベン図、ヒストグラムで機能）現在のビジュアライゼーションの設定を削除し、ゼロから再設定できるようにします。 |

## ビジュアルを作成アイコン {#quick-viz}

どのビジュアライゼーションが選択されるかわからない場合は、テーブルの行にある&#x200B;**[!UICONTROL ビジュアルを作成]**&#x200B;アイコン（カーソルを合わせると使用できます）をクリックします。これは、ビジュアライゼーションを追加する最も速い方法です。 クリックすると、データに最適なビジュアライゼーションを Analysis Workspace が学習に基づいて推測することの確認が表示されます。例えば、1 行を選択した場合、トレンド折れ線グラフが作成されます。 3 つのセグメント行を選択した場合は、ベン図が作成されます。

![](assets/quick-viz.png)
