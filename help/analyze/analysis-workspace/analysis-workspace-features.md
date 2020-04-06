---
keywords: Analysis Workspace
title: Analysis Workspace概要
topic: Reports and analytics
uuid: 4df6be48-2c88-4b9d-9536-ed64ffbb6ee4
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analysis Workspace の概要

分析ワークスペースでは、単一のAnalyticsレポートの一般的な制限がすべて削除されます。 堅牢で柔軟性の高いキャンバスを提供し、カスタム分析プロジェクトを作成します。 任意の数のデータテーブル、ビジュアライゼーションおよびコンポーネント（ディメンション、指標、セグメントおよび時間の精度）をプロジェクトにドラッグ&amp;ドロップします。 瞬時に分類とセグメントを作成し、分析用のコホートを作成し、アラートを作成し、セグメントを比較し、フローとフォールアウトの分析を行い、レポートをキュレーションしてスケジュールし、社内の任意のユーザーと共有します。

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

## 概要ビデオ {#section_B99BF8A326D94ECB91BD69C9888AD10C}

>[!VIDEO](https://www.youtube.com/watch?v=IHOy-QsvVcA)

YouTube のプレイリストは、[こちら](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)から参照できます。

>[!NOTE]
>
>機能に関する更新については、[Analysis Workspace の新機能](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)を参照してください。

## プロジェクト要素およびコンポーネントのフルコントロール {#section_B7E3EDA3EDEE407D833F4FDB69646EEC}

分析ワークスペースは、次のような自由と柔軟性を提供します。

* コンポーネント（ディメンション、指標、セグメントおよび時間の精度）のドラッグ&amp;ドロップ
* 複数のビジュアライゼーションをプロジェクトにドラッグ&amp;ドロップ
* プロジェクト内の任意の場所にビジュアライゼーションを移動、サイズ変更およびスタックする

![](assets/fa_project_new.png)

[Analysis Workspace プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)を参照してください。

## プロジェクト内の複数のビジュアライゼーション {#section_B7670740C2D44130B21DAF0873280DA5}

必要な数のビジュアライゼーションをプロジェクトにドラッグ＆ドロップします。

![](assets/visualizations-multiple.png)

フリーフォームデータテーブルのセルに対応する複数のビジュアライゼーションを使用して、変化の割合を示すプロジェクトを作成します。

![](assets/visualizations-multiple02.png)

[Analysis Workspace プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)を参照してください。

## パネルとビジュアライゼーションへのイントラリンク {#section_253EA04E067F4A29A8B54CE2B7631086}

Analysis Workspace の[リッチテキスト編集](/help/analyze/analysis-workspace/visualizations/text.md)機能と併せて、テキストボックスからプロジェクト内の特定のパネルとビジュアライゼーションにリンクする機能があります。これは例えば、プロジェクトの目次を作成するために使用できます。プロジェクトリンクを共有するのと同じように、プロジェクト内の特定のビジュアライゼーションやパネルを他の人と共有することができます。「パネルリンクを取得」および「ビジュアライゼーションリンクを取得」という新しい右クリックオプションが追加されました。プロジェクトにイントラリンクを追加するには：

1. テキストのビジュアライゼーションをプロジェクト内にドラッグします。コンテキストが必要なビジュアライゼーションまたはテーブルの横にドラッグすることもできます。
1. 例えば、テキストボックスにコンテンツのテーブルを入力し、パネルやビジュアライゼーションにリンクする項目（成功指標など）をハイライト表示します。

   ![](assets/intra-linking1.png)

1. そのパネルまたはビジュアライゼーションまでスクロールし、パネルのヘッダーを右クリックします。
1. 下にスクロールして、または **[!UICONTROL Get Panel Link]** を選択しま **[!UICONTROL Get Visualization Link]**&#x200B;す。

   ![](assets/intra-linking2.png)

1. そのリンクをコピーし、テキストビジュアライゼーションの成功指標ハイパーリンクに追加します。 チェックマークをクリックして、テキストを保存します。

プロジェクト内でパネルまたはビジュアライゼーションが折りたたまれている場合、リンクをクリックすると、パネルまたはビジュアライゼーションが展開され、ユーザーが見えるようになります。

>[!NOTE] この機能は、右クリックオプション内で使 **[!UICONTROL Edit Description]** 用することもできます。

## 他のプロジェクトへのリンク {#section_AE886C367C3E4F189B65B1BD9BCDBD8C}

You can link users to other projects that may be of interest to them by going to  **[!UICONTROL Share]** > **[!UICONTROL Get Project Link]** and embedding this link in project descriptions, for example.

## 選択したセルの動的ビジュアライゼーション {#section_182CEC285E4547EBA4608D5F70C9D5D7}

個々のセルを選択し、ビジュアライゼーションの変化を動的に確認します。 [ビジュアライゼーションを](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_9D66A001586F49CEB0C565581E44957C) 、選択したセルと同期およびロックします。

![](assets/visualize-selected-cells.png)

## 選択した項目または位置のロック {#section_9D66A001586F49CEB0C565581E44957C}

ビジュアライゼーションをロックすることで、ビジュアライゼーションに対応するフリーフォームデータテーブルのソースを制御できます。

![](assets/manage-data-source.png)

[データソースの管理](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)を参照してください。

## 選択したセルからのトレンドのビジュアライゼーション {#section_34930C967C104C2B9092BA8DCF2BF81A}

選択したセルからビジュアライゼーションを作成します(右クリック/を選択し **[!UICONTROL Trend Selection]**&#x200B;ます)。

![](assets/trend-selection.png)

トレンド選択は、下のテーブルに&#x200B;**リンク**&#x200B;され、テーブルで別の行を選択すると、トレンドグラフにその行が反映されるようになりました。

![](assets/trend-selection2.png)

## ディメンションとディメンション項目の分類 {#section_1380C1F9E51E4BFB8C5D35E7A53BC70D}

小売業者として、顧客とのより良い関わり方を理解するために、キャンペーンをこれまで以上に深く掘り下げることができます。 特定のニーズに合わせて、データを無制限に分類します。関連する指標、ディメンション、セグメント、タイムラインおよびその他のクエリ分類値を使用して分析を作成します。

![手順の結果](assets/fa_data_table_actions.png)

[ディメンションの分類](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)を参照してください。

## テーブルの選択範囲からのセグメント {#section_73BC3688089B426D969B3D5B606DA970}

フリーフォームデータテーブルのセルを選択し、選択範囲からセグメントを作成します。

複数のセグメントを比較し、セグメントを即座に作成して適用します。 複数のセグメントを適用して、行動やインタラクションに基づいて特定の顧客に焦点を当て、比較および対照を行うことができます。

![](assets/segment_inline.png)

セグメントをプロジェクトレベルのフリーフォームパネルにドロップすると、セグメントがプロジェクト全体に適用されます。

![](assets/segment-panel.png)

セグメント [を参照](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)。

## プロジェクトとコンポーネントのタグ付け {#section_F54D688132A541F2982326D5E022B90D}

Analysis Workspace でプロジェクトおよびコンポーネントにタグを適用できます。

* 情報パネルでプロジェクトレベルのタグを適用または作成します ![](assets/information_icon.png)。

* コンポーネントを右クリックし、コンポーネントパネルからタグ付け（またはタグの作成）します。
* 検索フィールドで#を使用して、タグを検索します。

## コンポーネントのアクション {#section_CBF4D0A5F63E4B0883077B8D852B800B}

コンポーネントの左側のパネルの最上部にあるアクションメニューから、コンポーネントレベルのアクションを実行します。Select a component and click **[!UICONTROL Actions]** to view the actions.

| コンポーネントアクション | 説明 |
|--- |--- |
| タグ | コンポーネントにタグを適用して整理したり管理したりします。このアクションは各コンポーネントマネージャーに表示されます（Analytics／コンポーネント／セグメントや Analytics／コンポーネント／プロジェクトなど）。 |
| お気に入り | お気追加に入りのリストの このアクションは各コンポーネントマネージャーに表示されます（Analytics／コンポーネント／セグメントや Analytics／コンポーネント／プロジェクトなど）。 |
| 承認 | コンポーネントを正規のコンポーネントにするように承認します。 このアクションは各コンポーネントマネージャーに表示されます（Analytics／コンポーネント／セグメントや Analytics／コンポーネント／プロジェクトなど）。 |
| 共有 | セグメントにのみ適用されます。 |
| 削除 | セグメントにのみ適用されます。 |

詳しくは、[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を参照してください。

## 追加機能の説明 {#section_5F06AE43C0194CFDBCA7EE0EA3C30B05}

**ドラッグおよびスタックできるもの**

コンポーネント

* ディメンション
* セグメント
* 指標
* 日付範囲
* 時間の精度（時間、日、週など）。

**複数のフリーフォームテーブルおよび複数のビジュアライゼーション**

パネルに追加できるフリーフォームテーブルおよびビジュアライゼーションの数に技術的な制限はありません。また、各フリーフォームテーブルまたはテーブルの選択した行で、新しいビジュアライゼーションを実行（またはCSVに書き出し）できます。

**列の整列、並べ替えおよびコピー**

* 日付範囲プリセットを並べ替えます（カスタム日付範囲は含まれません）。
* 列をCtrl（またはCommand）キーを押しながらクリックしながらドラッグすると、列がコピーされ、コピーをドラッグすると、テーブル内の新しい位置に貼り付けられます。

詳しくは、[Analysis Workspace で使用できるホットキー](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を参照してください。

**選択と操作**

行と列は、Excelでの選択と同様に選択できます。 その後、選択に対してアクションを実行できます。 次に例を示します。

* 選択範囲からのビジュアライゼーションの作成
* クリップボードにコピー（CtrlまたはCommand + C）
* 複数選択した行の分類。 行を選択し、ディメンションを選択範囲にドラッグします。 または、選択範囲を右クリックし、分類メニューを使用します。

**自動保存と未保存の変更**

ブラウザを閉じようとした（または[戻る]ボタンを使用しようとした）が、プロジェクトが保存されていない場合は、変更を保存するように求められます。 システムがクラッシュした場合は、プロジェクトの読み込み時に前のプロジェクトの状態に戻すように警告が表示されます。

既存の（新しくない）プロジェクトは、ブラウザーがクラッシュした場合、または保存の機会が与えられなかった場合にのみ、自動保存されます。

**すべての訪問**

Analysis Workspace に特有のデフォルトのセグメントです。*`All Visits`*&#x200B;は、テーブルに追加したコンポーネントの合計を表示します。

**計算指標**

標準指標と同じ方法で計算を使用します。

「計算指 [標」を参照](https://marketing.adobe.com/resources/help/ja_JP/analytics/calcmetrics/)。
