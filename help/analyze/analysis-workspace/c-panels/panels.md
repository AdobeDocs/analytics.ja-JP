---
description: パネルと Analysis Workspace でのパネルの使用方法について説明します。
title: パネルの概要
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '2228'
ht-degree: 100%

---

# パネルの概要

[!UICONTROL パネル]は、テーブルとビジュアライゼーションのコレクションです。パネルには、Workspace の左上のアイコンまたは[空のパネル](/help/analyze/analysis-workspace/c-panels/blank-panel.md)からアクセスできます。パネルは、期間、レポートスイートまたは分析のユースケースに従ってプロジェクトを整理する場合に役立ちます。

## パネルタイプ

[!UICONTROL Adobe Analytics] の Analysis Workspace では、次のパネルタイプを使用できます。

| パネル名 | 説明 |
| --- | --- |
| [空のパネル](/help/analyze/analysis-workspace/c-panels/blank-panel.md) | 使用可能なパネルおよびビジュアライゼーションから選択し、分析を開始します。 |
| [アトリビューション](attribution.md) | 任意のディメンションとコンバージョン指標を使用して、アトリビューションモデルをすばやく比較および視覚化します。 |
| [Analytics for Target](a4t-panel.md) | Analysis Workspace で Target アクティビティとエクスペリエンスを分析します。 |
| [フリーフォーム](freeform-panel.md) | 無制限の比較および分類を実行し、ビジュアライゼーションを追加して豊かなデータのストーリーを示します。 |
| [メディア分平均オーディエンス](average-minute-audience-panel.md) | 特定のコンテンツまたはカスタマイズされた期間での分平均オーディエンスを分析します。 |
| [メディア同時閲覧者数](media-concurrent-viewers.md) | 同時実行のピークの詳細と分類および比較機能を使用して、経時的に同時視聴者を分析します。 |
| [メディア再生滞在時間](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | 再生に費やした時間を分析して、同時実行のピークが発生した場所やドロップオフが発生した場所を把握します。 |
| [次または前の項目](next-previous.md) | ユーザーが移動する次のページまたは前のページを表示します。 |
| [クイックインサイト](quickinsight.md) | フリーフォームテーブルとそれに伴うビジュアライゼーションを素早く作成し、インサイトを迅速に分析して取得します。 |
| [ページの概要](page-summary.md) | 特定のページに関する主要な統計を探索します。 |
| [セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) | すべてのデータポイントで 2 つのセグメントをすばやく比較して、関連する相違点を自動的に見つけます。 |


分析を開始するには、[!UICONTROL クイックインサイト]パネル、[!UICONTROL 空白]パネル、[!UICONTROL フリーフォーム]パネルが最適です。一方、[!UICONTROL アトリビューション]は、より高度な分析に適しています。キャンバスの下部に ![AddCircle](/help/assets/icons/AddCircle.svg) が表示されるので、いつでも空白のパネルを追加できます。

デフォルトの開始パネルは[!UICONTROL フリーフォーム]パネルですが、[空白パネル](/help/analyze/analysis-workspace/c-panels/blank-panel.md)または[クイックインサイト](/help/analyze/analysis-workspace/c-panels/quickinsight.md)をデフォルトにすることができます。詳しくは、[プロジェクトと分析の環境設定](/help/analyze/analysis-workspace/user-preferences.md#projects--analyses-preferences)を参照してください。


## パネルの作成

パネルを作成するには：

* 左パネルから&#x200B;**[!UICONTROL パネル]**&#x200B;をキャンバスにドラッグ＆ドロップします。
* [空白のパネル](blank-panel.md)からパネルを選択します。
* Workspace の&#x200B;**[!UICONTROL 挿入]**&#x200B;メニューを使用してパネルを選択します。または、任意の[ショートカット](../build-workspace-project/fa-shortcut-keys.md)を使用してパネルを挿入することもできます。

  ![パネルの作成](assets/create-panel.png)

次のことができます。

* 任意のパネル&#x200B;**内**&#x200B;の ![AddCircle](/help/assets/icons/AddCircle.svg) を選択して、別のビジュアライゼーションを追加します。ビジュアライゼーションを選択できるポップアップが表示されます。

  ![使用可能なビジュアライゼーションを示すポップアップ](assets/blank-panel.png)

  | ..を選択 | ...を作成するには |
  |---|---|
  | ![テーブル](/help/assets/icons/Table.svg) | [フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![折れ線グラフ](/help/assets/icons/GraphTrend.svg) | [折れ線グラフ](/help/analyze/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [棒グラフ](/help//analyze/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [数値の概要](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) |
  | ![テキスト](/help/assets/icons/Text.svg) | [テキスト](/help/analyze/analysis-workspace/visualizations/text.md) |
  | ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [フォールアウト](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![ワークフロー](/help/assets/icons/GraphPathing.svg) | [フロー](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [積み重ね面グラフ](/help/analyze/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [コホートテーブル](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [ブレット](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [ドーナツ](/help/analyze/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [変更の概要](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) |
  | ![ヒストグラム](/help/assets/icons/Histogram.svg) | [ヒストグラム](/help/analyze/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散布図](/help/analyze/analysis-workspace/visualizations/scatterplot.md) |
  | ![タイプ](/help/assets/icons/TwoDots.svg) | [ベン図](/help/analyze/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [ツリーマップ](/help/analyze/analysis-workspace/visualizations/treemap.md) |

* ワークスペースの最後のパネル&#x200B;**外**&#x200B;の ![AddCircle](/help/assets/icons/AddCircle.svg) を選択し、別の[空白のパネル](blank-panel.md)を追加します。


## パネルの管理

パネルは、次の方法で管理できます。

![パネルの管理](assets/manage-panel.png)

* パネルを折りたたむには、![下向き山形記号](/help/assets/icons/ChevronDown.svg) を選択します。
* 折りたたまれたパネルを表示するには、![左向き山形記号](/help/assets/icons/ChevronLeft.svg) を選択します。
* パネルを削除するには、![クロスサイズ400](/help/assets/icons/CrossSize200.svg) を選択します。元に戻すには、**[!UICONTROL 編集]**／**[!UICONTROL 元に戻す]**（**[!UICONTROL *cmd+z *]**|**[!UICONTROL * ctrl+z *]**）を選択します。
* パネルを移動するには、![移動](/help/assets/icons/Move.svg) が表示されているとき（通常はヘッダーにポインタを合わせているとき）に、パネルをドラッグ＆ドロップします。


## レポートスイート

各パネルは、[レポートスイート](/help/admin/tools/manage-rs/report-suites-admin.md)に関連付けられており、パネルの右上にあるドロップダウンメニューの&#x200B;**[!UICONTROL *レポートスイート&#x200B;*]**の![データ名](/help/assets/icons/Data.svg)で識別されます。

新しいパネルを作成する場合、デフォルトのレポートスイートは、Analysis Workspace プロジェクトで最後に作業したパネルのレポートスイートに基づいています。

プロジェクト内では、分析のユースケースに応じて、1 つまたは[複数のレポートスイート](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md)を使用できます。

レポートスイートのリストは、関連性に基づいて並べ替えられます。これらの関連性は、現在のユーザーがスイートを使用した最近のタイミングと頻度、および組織内でスイートを使用した頻度に基づき、アドビによって定義されます。

![](assets/panel-report-suite.png)

>[!IMPORTANT]
>
>選択したレポートスイートによって、パネル内のビジュアライゼーションの作成に使用できるディメンション、指標、セグメントが決まります。
>
>
>パネルのレポートスイートを切り替えると、その新しいレポートスイートで一部のコンポーネントを使用できなくなる場合があります。この変更により、ビジュアライゼーションが正しくレンダリングされない可能性があります。次のような警告が表示される場合があります。
>
>* このパネルには、選択したレポートスイートで有効になっていないコンポーネントが含まれています。レポートスイートを変更するか、レポートスイートで必要なコンポーネントを有効にしてください。
>* ビジュアライゼーションをレンダリングできません。列と行で有効なコンポーネントが含まれていることを確認してください。
>

## カレンダー

パネルカレンダーは、パネル内のテーブルおよびビジュアライゼーションのレポート日付範囲を制御します。

>[!NOTE]
>
>![カレンダー](/help/assets/icons/Calendar.svg)日付範囲コンポーネントがビジュアライゼーションまたはパネル内で（例えばセグメントとして）使用されている場合、日付範囲コンポーネントがパネルカレンダーを上書きします。
>


![選択した日付範囲を示すカレンダーウィンドウ。](assets/panel-calendar.png)

1. 最初に開始日を選択し、次に終了日を選択して、日付範囲を選択します。
または、**[!UICONTROL プリセットを選択]**&#x200B;ドロップダウンメニューから「[!UICONTROL *プリセット*]」を選択できます。

1. オプションで、「**[!UICONTROL 詳細設定を表示]**」を選択して、次の操作を行います。

   * デフォルトの `12:00 AM`（`0:00`）と `11:59 PM`（`23:59`）以外の&#x200B;**[!UICONTROL 開始時間]**&#x200B;と&#x200B;**[!UICONTROL 終了時間]**&#x200B;を指定します。終了時間には常に 59 秒が含まれます。日付範囲が何日にもわたる場合、開始時間は日付範囲の最初の日、終了時間は日付範囲の最終日に適用されます。**[!UICONTROL 日時の値をリセット]**&#x200B;を使用して、開始時間と終了時間をデフォルトにリセットします。
   * **[!UICONTROL パネルカレンダーを基準とした日付範囲コンポーネントの作成]**&#x200B;無効にした場合、パネルで使用される日付範囲コンポーネントは現在の時刻を基準とします。有効にした場合、パネルで使用される日付範囲コンポーネントがパネルカレンダーに関連付けられます。
   * **[!UICONTROL 相対日付の使用]**&#x200B;有効にした場合、現在の日付と時間の進行状況に応じて、プリセットされた日付範囲（**[!UICONTROL 過去 7 日間]**&#x200B;など）が動的に更新されます。無効にすると、そのようなプリセットは適用されると更新されません。

     ![周期的な日付](assets/calendar-rolling.png)

     角括弧で囲まれたテキスト（例：**[!UICONTROL 固定開始 - 日周期]**）を選択して、パネルを拡張し、**[!UICONTROL 開始]**&#x200B;と&#x200B;**[!UICONTROL 終了]**&#x200B;の詳細を指定できます。

      1. 「**[!UICONTROL 開始日]**」、「**[!UICONTROL 終了日]**」または「**[!UICONTROL 固定日]**」を選択します。
      1. 「**[!UICONTROL 開始日]**」または「**[!UICONTROL 終了日]**」を選択すると、完全な式を作成できます。例：**[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**。式の個々の部分に適した値を選択します。
         * 現在の値を選択します。例：**[!UICONTROL current year]**。
         * 追加の計算の値を選択します。例：**[!UICONTROL plus]**。
         * 追加の計算を指定した場合は、値を指定します。例：`1`。
         * 追加の計算を指定した場合は、計算に使用する期間を選択します。例：**[!UICONTROL day]**。

     周期的な日付の計算の詳細を非表示にするには、「**[!UICONTROL 詳細を非表示]**」を選択します。

1. 「**[!UICONTROL 適用]**」を選択して、カレンダーを呼び出したパネルに日付範囲を適用します。
「**[!UICONTROL すべてのパネルに適用]**」を選択すると、Workspace プロジェクトのすべてのパネルに日付範囲が適用されます。


## ドロップゾーン {#dropzone}

パネルドロップゾーンを使用すると、パネル内のすべてのテーブルおよびビジュアライゼーションにセグメントおよびドロップダウンセグメントを適用できます。1 つのパネルに 1 つまたは複数のセグメントを適用できます。

### セグメント

パネルのドロップゾーンに左パネルからセグメントをドラッグ＆ドロップして、パネルのセグメント化を開始します。このプロセスを繰り返して、パネルにセグメントを追加します。セグメントは、パネルの上部に並んで表示されます。

![左パネルには、パネルのドロップゾーンにドラッグされた使用可能な指標とモバイル顧客指標が表示されます。](assets/segment-filter.png)

#### クイックセグメント

セグメント以外のコンポーネントをドロップゾーンに直接ドラッグしてクイックセグメントを作成することもできるので、[セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md)への移行にかかる時間と手間を省くことができます。この方法で作成されたセグメントは、イベントレベルのセグメントとして自動的に定義されます。この定義は、セグメント名の横にある「![編集](/help/assets/icons/Edit.svg)」を選択すると、すばやく変更できます。

<!-- For more information, see [Quick segments](/help/components/segmentation/). -->

![公開されてドロップゾーンにドロップされるアドホックセグメント。](assets/adhoc-segment-filter.png)

### ドロップダウンセグメント


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ドロップダウンセグメント](https://video.tv.adobe.com/v/23877?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


#### 静的ドロップダウンセグメント

静的ドロップダウンセグメントを使用すると、制御された方法でデータを操作できます。例えば、モバイルデバイスタイプにドロップダウンセグメントを追加すして、タブレット、携帯電話、デスクトップ別にパネルをセグメント化できます。

静的ドロップダウンセグメントを使用して、多くのプロジェクトを 1 つに統合することもできます。例えば、同じプロジェクトに異なる国セグメントが適用された複数のバージョンがある場合、すべてのバージョンを 1 つのプロジェクトに統合して「国」ドロップダウンセグメントを追加できます。

![マーケットチャネル「ダイレクト」フィルターがハイライト表示された静的ドロップダウンセグメント。](assets/dropdown-filter-intro.png)

##### 静的ドロップダウンセグメントの作成

* ディメンション項目を使用したドロップダウンセグメントの場合は、左パネルから 1 つのディメンションを選択し、⇧（*Shift*）キーを押したまま、パネルのドロップゾーンにドロップします。この操作により、そのディメンションに関連付けられたすべてのディメンション項目を選択できる、ドロップダウンセグメントが作成されます。

  または、ディメンションに関連付けられた特定のディメンション項目のみをドロップダウンセグメントに含める場合は、左パネルで、目的のディメンションの横にある右矢印アイコンを選択します。このアクションにより、使用可能なすべてのディメンション項目が表示されます。⇧ キーを押しながら![選択](/help/assets/icons/Select.svg)（*Shift* キーを押しながら&#x200B;*選択*）または ^ キーを押しながら![選択](/help/assets/icons/Select.svg)（*Ctrl* キーを押しながら&#x200B;*選択*）を使用して、このリストから複数のディメンション項目を選択し、⇧ キーを&#x200B;**押しながら**、それらをパネルのドロップゾーンにドロップします。

* 単一のコンポーネントタイプ（ディメンションのみ、セグメントのみ、指標のみなど）を使用するドロップダウンセグメントの場合は、⇧ キーを押しながら![選択](/help/assets/icons/Select.svg)、または ^ を押しながら![選択](/help/assets/icons/Select.svg)を使用して、左パネルから同じタイプの複数の項目を選択します。次に、⇧ キーを&#x200B;**押しながら**、項目をパネルのドロップゾーンにドロップします。

  選択したコンポーネントを使用して、1 つのドロップダウンセグメントが作成されます。

* コンポーネントタイプの組み合わせ（2 つの指標と 3 つのセグメントなど）を使用するドロップダウンセグメントの場合は、⇧ キーを押しながら![選択](/help/assets/icons/Select.svg)、または ^ キーを押しながら![選択](/help/assets/icons/Select.svg)を使用して、複数のコンポーネントを選択します。⇧ キーを&#x200B;**押しながら**、選択内容をパネルのドロップゾーンにドロップします。このコンテキストでは、すべてのコンポーネントタイプは個別のドロップダウンセグメントとして扱われます。例えば、指標とディメンション項目の両方を選択範囲に含める場合、2 つの異なるドロップダウンセグメントが作成されます。1 つのドロップダウンセグメントにはディメンション項目、もう 1 つには指標が含まれます。

ドロップダウンセグメントには、次のコンテキストメニューオプションがあります。

* **[!UICONTROL ドロップダウンを削除]**：パネルからドロップダウンセグメントを削除します。
* **[!UICONTROL ラベルを削除]**：ドロップダウンセグメントの上にあるテキストを削除します。ラベルを変更するには、ラベルの上にポインタを合わせて、「![ドロップダウンセグメントのラベルを編集](/help/assets/icons/Edit.svg)」を選択します。
* **[!UICONTROL ラベルを追加]**：プロジェクトにドロップダウンセグメントを追加すると、ラベルが自動的にコンポーネント名に設定されます。ラベルを削除した場合は、このオプションを使用して再度追加できます。
* **[!UICONTROL 選択を要求]**：パネルにセグメントが設定されている必要があります。

##### 静的ドロップダウンセグメントの使用

ユーザーは、次のいずれかの方法でドロップダウンセグメントメニューを使用して、パネルをセグメント化できます。

* ドロップダウンセグメントからセグメントを選択して、1 つのセグメントをパネルに適用します。

* ドロップダウンセグメントから複数のセグメントを選択して、パネルに複数のセグメントを適用します。パネルがセグメント化され、選択したセグメントのいずれかが含まれます。


#### 動的ドロップダウンセグメント

動的ドロップダウンセグメントを使用すると、パネルのレポート範囲内のデータと他のドロップダウンセグメントの値に基づいて、使用可能な値を決定できます。例えば、国ディメンションと市区町村ディメンションを使用して、2 つの動的なドロップダウンを作成できます。**[!UICONTROL 国]**&#x200B;ドロップダウンリストから国を選択すると、**[!UICONTROL 市区町村]**&#x200B;ドロップダウンリストが動的に調整され、その国内の市区町村のみが表示されます。

これと同じ概念がすべてのディメンションに適用され、パネルの日付範囲内に表示されるディメンション項目と選択したセグメントのみが表示されます。静的ドロップダウンセグメントで選択したディメンション項目は、動的ドロップダウンセグメントで使用できる値に影響します。ただし、その逆は成り立ちません。動的ドロップダウンセグメントで選択したディメンション項目は、静的ドロップダウンセグメントで使用可能な値には影響しません。

将来収集される特定のディメンション項目が予想される場合は、ディメンション項目を手動で選択できます。また、動的ドロップダウンセグメントをクリアして、値が含まれないようにすることもできます。それにより、他の動的ドロップダウンセグメントにより多くの値を含めることができます。「**[!UICONTROL すべてをリセット]**」を選択すると、そのパネルのすべてのドロップダウンセグメントから選択内容をクリアできます。

動的ドロップダウンセグメントを作成するには：

* ⇧ キーを&#x200B;**押しながら**、1 つのディメンションをパネルのドロップゾーンにドラッグ＆ドロップします。

動的ドロップダウンセグメントは、指標、セグメントまたは日付範囲では使用できないことに注意してください。

動的ドロップダウンセグメントには、静的ドロップダウンセグメントと同じコンテキストメニューオプションがあります。


## コンテキストメニュー

パネルの追加機能は、パネルのヘッダーのコンテキストメニュー（右クリック）から使用できます。

![パネルヘッダーの右クリックオプション。](assets/right-click-menu.png)

次のオプションがあります。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL コピーしたパネルを挿入]** | コピーしたパネルをプロジェクト内の別の場所または別のプロジェクトにペーストできます。 |
| **[!UICONTROL コピーしたビジュアライゼーションを挿入]** | コピーしたビジュアライゼーションをプロジェクト内の別の場所または別のプロジェクトにペーストできます。 |
| **[!UICONTROL レポートスイートをすべてのパネルに適用]** | このパネルのレポートスイートをプロジェクト内の他のすべてのパネルに適用します。 |
| **[!UICONTROL パネルをコピー]** | パネルをコピーして、プロジェクト内の別の場所または別のプロジェクトに挿入できます。 |
| **[!UICONTROL パネルを複製]** | 現在のパネルの完全な複製を作成して、修正できます。 |
| **[!UICONTROL すべてのパネルを折りたたむ]** | すべてのプロジェクトパネルを折りたたみます。 |
| **[!UICONTROL すべてのパネルを展開]** | すべてのプロジェクトパネルを展開します。 |
| **[!UICONTROL パネル内のすべてのビジュアライゼーションを折りたたむ]** | 現在のパネルのすべてのビジュアライゼーションを折りたたみます。 |
| **[!UICONTROL パネル内のすべてのビジュアライゼーションを展開]** | 現在のパネル内のすべてのビジュアライゼーションを展開します。 |
| **[!UICONTROL 説明を編集]** | パネルの説明テキストを追加（または編集）します。 |
| **[!UICONTROL パネルリンクを取得]** | プロジェクト内の特定のパネルに他のユーザーを誘導します。受信者は、リンクを選択した後、リンク先の正確なパネルにリダイレクトされる前にログインする必要があります。 |

## 設定

一部のパネル（[!UICONTROL アトリビューション]、[!UICONTROL 実験]、[!UICONTROL メディア分平均オーディエンス]など）には、ビジュアライゼーションの構築を支援する設定ダイアログがあります。パネルの上部にある「![編集](/help/assets/icons/Edit.svg)」を使用して、設定にアクセスして変更します。

![パネルの設定](/help/analyze/analysis-workspace/c-panels/assets/configure-panel.png)

<!--
## Panel types

The following panel types are available in Analysis Workspace:

| Panel name | Description |
| --- | --- |
| [Blank panel](blank-panel.md) | Choose from available panels and visualizations to start your analysis. |
| [Quick Insights panel](quickinsight.md) | Quickly build a freeform table and an accompanying visualization in order to analyze and uncover insights faster. |
| [Analytics for Target panel](a4t-panel.md) | Analyze Target activities and experiences in Analysis Workspace. |
| [Attribution panel](attribution.md) | Quickly compare and visualize any number of attribution models using any dimension and conversion metric. |
| [Freeform panel](freeform-panel.md) | Perform unlimited comparisons and breakdowns, then add visualizations to tell a rich data story. |
| [Media Average Minute Audience panel](average-minute-audience-panel.md) | Analyze average minute audience over time, with details on peak views and the ability to break down and compare. |
| [Media Concurrent Viewers panel](media-concurrent-viewers.md) | Analyze concurrent viewers over time, with details on peak concurrency and the ability to break down and compare. |
| [Media Playback Timespent panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analyze concurrent viewers over time, with details on peak concurrency and the ability to break down and compare. |
| [Segment Comparison panel](c-segment-comparison/segment-comparison.md) | Quickly compare two segments across all data points to automatically find relevant differences. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights], [!UICONTROL Blank] and [!UICONTROL Freeform] panels are great places to start your analysis, while [!UICONTROL Analytics for Target], [!UICONTROL Attribution], [!UICONTROL Media Concurrent Viewers] and [!UICONTROL Segment Comparison] lend themselves to more advanced analyses. A `"+"` button is available in projects so you can add blank panels at any time.

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) your default as well.

## Report suite {#report-suite}

Tables and visualizations within a panel derive data from the [!UICONTROL report suite] selected in the top right of the panel. The report suite also determines what components are available in the left rail. Within a project, you can use one or [many report suites](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) depending on your analysis use cases. To apply a single report suite to all panels in a project, **right-click panel header > Apply report suite to all panels**.

The list of report suites is sorted on relevancy, which Adobe defines based on how recently and frequently the suite has been used by the current user, and how frequently the suite is used within the organization.

![](assets/panel-report-suite.png)

## Calendar {#calendar}

The panel calendar controls the reporting range for tables and visualizations within a panel.

>[!NOTE]
>If a (purple) date range component is used within a table, visualization or panel drop zone, it overrides the panel calendar.

![](assets/panel-calendar.png)

You can apply a minute-level date range under the advanced settings of your panel calendar. If you are reporting on a date range that spans many days, start time applies to the first day and end time applies to the last day in your range.

## Drop zone {#dropzone}

The panel drop zone enables you to apply segment and drop-down filters to all tables and visualizations within a panel. You can apply one or many filters to a panel. 

### Segment filters

Drag and drop any segments from the left rail into the panel drop zone to begin filtering your panel. Repeat this process to add additional filters to the panel. Filters appear side by side at the top of the panel.

![Filter](assets/segment-filter.png)

### Ad hoc segment filters

Non-segment components can also be dragged directly into the drop zone to create ad hoc segments, saving you the time and effort of going to the Segment Builder. Segments created in this way are automatically defined as hit-level segments. This definition can be modified by clicking the information icon (i) next to the segment, then the pencil-shaped edit icon and editing it in the Segment Builder.

Ad hoc segments are a type of quick segment, and are local to the project. They do not show up in the left rail unless you make them public.

For more information, see [Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Static drop-down segments

Static drop-down segments enable you to interact with the data in a controlled way. For example, you can add a drop-down segment for Mobile Device Types so that you can segment the panel by Tablet, Mobile Phone, or Desktop.

Static drop-down segments can also be used to consolidate many projects into one. For example, if you have many versions of the same project with different Country segments applied, you can consolidate all versions into a single project and add a Country drop-down segment.

![](assets/dropdown-filter-intro.png)

#### Create static drop-down segments

* For drop-down segments using dimension items, select a single dimension from the left rail and drop it into the panel dropzone **while holding `[Shift]`**. This creates a drop-down segment with all the dimension items that are associated with that dimension. 

  Or, if you want the drop-down segment to include only specific dimension items that are associated with a dimension, click the right arrow icon next to the desired dimension in the left rail. This action exposes all available dimension items. Select multiple dimension items from this list using `[Shift + Click]` or `[Ctrl + Click]`, then drop them into the panel dropzone **while holding** `[Shift]`.

* For drop-down segments using a single component type (for example, only dimensions, or only segments, or only metrics), select multiple items of the same type in the left rail using `[Shift + Click]` or `[Ctrl + Click]`, then drop them into the panel dropzone **while holding `[Shift]`**.

  A single drop-down segment is created with components that you selected.

* For drop-down segments using a mix of component types (such as 2 metrics and 3 filters), select multiple components using `[Shift + Click]` or `[Ctrl + Click]`. Drop the selection into the panel dropzone **while holding `[Shift]`**. In this context, all component types are treated as separate drop-down segments. For example, if you include both metrics and dimension items in your selection, two separate drop-down segments are created: one drop-down segments includes dimension items, and the other includes metrics.

  ![The Panel window with the Mobile Customer segment field available to drop a static drop-down segment. ](assets/create-dropdown.png)

Right-clicking a drop-down segment provides the following options:

* **[!UICONTROL Delete drop-down]**: Removes the drop-down segment from the panel. 
* **[!UICONTROL Delete label]**: Remove the text above a drop-down segment. To modify the label, select the pencil icon.
* **[!UICONTROL Add label]**: When you add a drop-down segment to a project, a label is automatically set to the component name. If you delete the label, you can add it again with this option.
* **[!UICONTROL Require selection]**: Requires that a segment is set on the panel. 

[Watch the video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) to learn more about how to add drop-down filters to your project.

#### Use static drop-down segments

Use the drop-down segments menu in any of the following ways in order to filter the panel:
     
* Apply a single segment to the panel by selecting the segment from the drop-down menu.

* Apply multiple segments to the panel by selecting more than one segment from the drop-down menu. The panel is filtered to include any of the selected segments. 

  To remove a segment from the list, select it again in the drop-down menu.

  ![Select multiple segments](assets/dropdown-filter-multiselect.png)

### Dynamic drop-down segments

Dynamic drop-down segments allow you to determine available values based on data within the panel's reporting range and values in other drop-down segments. For example, you can create two dynamic drop-downs using the [Countries](/help/components/dimensions/countries.md) dimension and [Cities](/help/components/dimensions/cities.md) dimension. When you select a country from the [!UICONTROL Countries] drop-down list, the [!UICONTROL Cities] drop-down list dynamically adjusts to only show cities within that country.

This same concept applies to all dimensions; only dimension items that appear within the panel's date range and selected segments are visible. Dimension items selected in static drop-down segments affect available values in dynamic drop-down segments. However, the inverse is not true; Dimension items selected in dynamic drop-down segments do not affect available values in static drop-down segments.

Manual selection of dimension items is available if you anticipate a certain dimension item to be collected in the future. You can also clear a dynamic drop-down segment so that it does not contain a value, allowing other dynamic drop-down segments to contain more values. Select **[!UICONTROL Reset all]** to clear the selection from all drop-down segments for that panel.

To create a dynamic drop-down segment:

* Drag and drop a single dimension into the panel dropzone **while holding `[Shift]`**.
* Dynamic drop-down segments are not available for metrics, segments, or date ranges.
* Right-click a drop-down segment and select **[!UICONTROL Delete dropdown]** to delete it.

Right-clicking a dynamic drop-down filter provides the same options as static drop-down filters.

## Right-click menu {#right-click}

Additional functionality for a panel is available by right-clicking on the panel header.

![Right-click menu](assets/right-click-menu.png)

The following settings are available:

| Setting | Description |
| --- | --- |
| Insert Copied Panel/Visualization|Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a different project.|
| Copy Panel | Lets you right-click and copy a panel, so that you can insert it to another place within the project, or into a different project.|
| Apply Report Suite to all panels | Lets you apply the active panel report suite to all panels in the project.|
| Duplicate Panel | Makes an exact duplicate of the current panel, which you can then modify. |
| Collapse/Expand all Panels | Collapses and expands all project panels. |
| Collapse/Expand all Visualizations in Panel | Collapses and expands all visualizations in the current panel. |
| Edit Description | Add (or edit) a text description for the panel. |
| Get Panel Link | Lets you direct someone to a specific panel within a project. When the link is clicked, the recipient will be required to login before being directed to the exact panel linked to. |

-->
