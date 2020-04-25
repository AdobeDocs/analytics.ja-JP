---
keywords: Analysis Workspace
title: Analysis Workspace の概要
topic: Reports and analytics
uuid: 4df6be48-2c88-4b9d-9536-ed64ffbb6ee4
translation-type: tm+mt
source-git-commit: 5161ccaf333908525c261b73419899918554b91c

---


# Analysis Workspace の概要

Analysis Workspace では、単一の Analytics レポートの通常の制限事項がすべて取り除かれます。堅牢かつ柔軟なキャンバスでカスタム分析プロジェクトを作成できます。任意の数のデータテーブル、ビジュアライゼーション、コンポーネント（ディメンション、指標、セグメントおよび時間の精度）をプロジェクトにドラッグ＆ドロップします。分類およびセグメントの作成、分析用のコホートの作成、アラートの作成、セグメントの比較、フローおよびフォールアウト分析をすばやくおこなうほか、レポートのキュレーションとスケジュールをおこなって会社の任意のユーザーと共有します。

**[!UICONTROL Analytics]**／**[!UICONTROL Workspace]**

## 概要ビデオ

>[!VIDEO](https://video.tv.adobe.com/v/26266?quality=12)

YouTube のプレイリストは、[こちら](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)から参照できます。

>[!NOTE]
>
>機能に関する更新については、[Analysis Workspace の新機能](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)を参照してください。

## プロジェクト要素およびコンポーネントのフルコントロール

Analysis Workspace は、次のような自由と柔軟性を提供します。

* コンポーネント（ディメンション、指標、セグメントおよび時間の精度）をドラッグ＆ドロップする
* 複数のビジュアライゼーションをプロジェクトにドラッグ＆ドロップする
* プロジェクト内で場所を問わずビジュアライゼーションを移動、リサイズおよびスタックする

![](assets/fa_project_new.png)

[Analysis Workspace プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)を参照してください。

## プロジェクト内の複数のビジュアライゼーション

必要な数のビジュアライゼーションをプロジェクトにドラッグ＆ドロップします。

![](assets/visualizations-multiple.png)

フリーフォームデータテーブルのセルに対応する複数のビジュアライゼーションで、変化の割合を示すプロジェクトを作成します。

![](assets/visualizations-multiple02.png)

[Analysis Workspace プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)を参照してください。

## パネルとビジュアライゼーションへのイントラリンク

Analysis Workspace の[リッチテキスト編集](/help/analyze/analysis-workspace/visualizations/text.md)機能と併せて、テキストボックスからプロジェクト内の特定のパネルとビジュアライゼーションにリンクする機能があります。これは例えば、プロジェクトの目次を作成するために使用できます。プロジェクトリンクを共有するのと同じように、プロジェクト内の特定のビジュアライゼーションやパネルを他の人と共有することができます。「パネルリンクを取得」および「ビジュアライゼーションリンクを取得」という新しい右クリックオプションが追加されました。イントラリンクをプロジェクトに追加するには：

1. テキストビジュアライゼーションをプロジェクト内にドラッグします。例えば、コンテキストが必要なビジュアライゼーションまたはテーブルの横に配置します。
1. テキストボックスに目次などを入力して、パネルまたはビジュアライゼーションにリンクさせたい項目（この例では成功指標）をハイライト表示します。

   ![](assets/intra-linking1.png)

1. 目的のパネルまたはビジュアライゼーションまでスクロールして、そのヘッダーを右クリックします。
1. 下にスクロールして、または **[!UICONTROL Get Panel Link]** を選択しま **[!UICONTROL Get Visualization Link]**&#x200B;す。

   ![](assets/intra-linking2.png)

1. そのリンクをコピーして、テキストビジュアライゼーション内の成功指標ハイパーリンクに追加します。チェックマークをクリックしてテキストを保存します。

パネルまたはビジュアライゼーションがプロジェクト内で折りたたまれている場合は、リンクをクリックすると、パネル／ビジュアライゼーションが展開されて表示されます。

>[!NOTE] この機能は、右クリックオプション内で使 **[!UICONTROL Edit Description]** 用することもできます。

## 他のプロジェクトへのリンク

You can link users to other projects that may be of interest to them by going to  **[!UICONTROL Share]** > **[!UICONTROL Get Project Link]** and embedding this link in project descriptions, for example.

## 選択したセルの動的ビジュアライゼーション

個別のセルを選択して、ビジュアライゼーションの変更を動的に確認します。選択したセルでビジュアライゼーションを[同期およびロック](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_9D66A001586F49CEB0C565581E44957C)します。

![](assets/visualize-selected-cells.png)

## 選択した項目または位置のロック

ビジュアライゼーションをロックすることで、ビジュアライゼーションに対応するフリーフォームデータテーブルのソースを制御できます。

![](assets/manage-data-source.png)

[データソースの管理](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)を参照してください。

## 選択したセルからのトレンドのビジュアライゼーション

選択したセルからビジュアライゼーションを作成します(Right-click > **[!UICONTROL Trend Selection]**.)

![](assets/trend-selection.png)

トレンド選択は、下のテーブルに&#x200B;**リンク**&#x200B;され、テーブルで別の行を選択すると、トレンドグラフにその行が反映されるようになりました。

![](assets/trend-selection2.png)

## ディメンションとディメンション項目の分類

小売業者の場合、キャンペーンをこれまでよりも深く分析して、顧客とのより良い関わり方を把握できます。特定のニーズに合わせて様々な方法でデータを分類し、関連する指標、ディメンション、セグメント、タイムライン、その他の分析分類値を使用するクエリを作成します。

![手順の結果](assets/fa_data_table_actions.png)

[ディメンションの分類](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)を参照してください。

## テーブルの選択範囲からのセグメント

フリーフォームデータテーブルのセルを選択し、選択範囲からセグメントを作成します。

複数のセグメントを比較して、即座にセグメントを作成および適用します。複数のセグメントを適用して、行動や操作に基づいて特定の顧客に焦点を当て、比較および対比します。

![](assets/segment_inline.png)

プロジェクトレベルのフリーフォームパネルにセグメントをドロップすると、セグメントがプロジェクト全体に適用されます。

![](assets/segment-panel.png)

セグメント [を参照](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)。

## プロジェクトとコンポーネントのタグ付け

Analysis Workspace でプロジェクトおよびコンポーネントにタグを適用できます。

* 情報パネルでプロジェクトレベルのタグを適用または作成します ![](assets/information_icon.png)。

* コンポーネントを右クリックして、コンポーネントパネルからタグ付け（またはタグを作成）します。
* 検索フィールドで # を使用して、タグを検索します。

## コンポーネントのアクション

コンポーネントの左側のパネルの最上部にあるアクションメニューから、コンポーネントレベルのアクションを実行します。Select a component and click **[!UICONTROL Actions]** to view the actions.

| コンポーネントのアクション | 説明 |
|--- |--- |
| タグ | コンポーネントにタグを適用して整理したり管理したりします。このアクションは各コンポーネントマネージャーに表示されます（Analytics／コンポーネント／セグメントや Analytics／コンポーネント／プロジェクトなど）。 |
| お気に入り | コンポーネントをお気に入りのリストに追加します。このアクションは各コンポーネントマネージャーに表示されます（Analytics／コンポーネント／セグメントや Analytics／コンポーネント／プロジェクトなど）。 |
| 承認 | コンポーネントを正規のものとして承認します。このアクションは各コンポーネントマネージャーに表示されます（Analytics／コンポーネント／セグメントや Analytics／コンポーネント／プロジェクトなど）。 |
| 共有 | セグメントにのみ適用します。 |
| 削除 | セグメントにのみ適用します。 |

詳しくは、[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を参照してください。

## 追加機能の説明

**ドラッグおよびスタックできるもの**

コンポーネント

* ディメンション
* セグメント
* 指標
* 日付範囲
* 時間の精度（時間、日、週など）

**複数のフリーフォームテーブルおよび複数のビジュアライゼーション**

パネルに追加できるフリーフォームテーブルおよびビジュアライゼーションの数に技術的な制限はありません。また、各フリーフォームテーブルまたはテーブルの選択した行で新しいビジュアライゼーションを実行（または CSV に書き出し）できます。

**列の整列、並べ替えおよびコピー**

* 日付範囲プリセットを並べ替えます（カスタム日付範囲は含まれません）。
* 列を Ctrl（または Command）+ クリック + ドラッグすると、その列がコピーされ、このコピーをドラッグして、テーブルの新しい位置に貼り付けます。

詳しくは、[Analysis Workspace で使用できるホットキー](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を参照してください。

**選択と操作**

Excel で選択するのと同じように、行および列を選択できます。さらに、選択範囲に対して次の操作を実行できます。次に例を示します。

* 選択範囲からビジュアライゼーションを作成
* クリップボードにコピー（Ctrl または Command + C）
* 複数選択した行の分類。行を選択し、次にディメンションを選択範囲にドラッグします。または、選択範囲を右クリックして、分類メニューを使用します。

**自動保存と未保存の変更**

ブラウザーを閉じようとすると（または戻るボタンを使用すると）、プロジェクトが保存されていない場合、変更の保存を促すメッセージが表示されます。システムがクラッシュした場合、アラートを受け取り、前回プロジェクトを読み込んだ際のプロジェクトの状態に復元できます。

既に存在する（新規でない）プロジェクトは、ブラウザーがクラッシュしたとき、または保存する機会がない何らかの状態のときにのみ、自動保存されます。

**すべての訪問**

Analysis Workspace に特有のデフォルトのセグメントです。*`All Visits`*&#x200B;は、テーブルに追加したコンポーネントの合計を表示します。

**計算指標**

標準指標を使用するのと同じ方法で計算を使用します。

[計算指標](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/cm-overview.html)を参照してください。
