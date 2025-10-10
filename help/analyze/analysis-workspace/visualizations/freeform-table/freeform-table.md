---
title: フリーフォームテーブルの概要
description: Analysis Workspaceのデータ分析の基盤となるフリーフォームテーブルの使用方法について説明します。
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 97%

---

# フリーフォームテーブルの概要 {#freeform-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="フリーフォームテーブル"
>abstract="ディメンション、セグメント、指標および日付範囲を使用して作成できる、空のフリーフォームテーブルのビジュアライゼーションを作成します。フリーフォームテーブルを他のビジュアライゼーションの基礎として使用できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** のフリーフォームテーブルビジュアライゼーションについて説明します。_<br/>_この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** バージョンについて詳しくは、[フリーフォームテーブル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/freeform-table)を参照してください。_

>[!ENDSHADEBOX]


Analysis Workspace では、![テーブル](/help/assets/icons/Table.svg) **[!UICONTROL フリーフォームテーブル]**&#x200B;ビジュアライゼーションがインタラクティブなデータ分析の基盤となります。[コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)の組み合わせを行と列にドラッグ＆ドロップして、分析用のカスタムテーブルを作成できます。各コンポーネントをドロップすると、テーブルがすぐに更新されるので、すばやく分析してさらに深く掘り下げることができます。

![複数の web ページの訪問回数やオンライン注文数などのコンポーネントを行と列で表示するフリーフォームテーブル。](assets/opening-section.png)

[!UICONTROL フリーフォームテーブル]を作成および設定するには：

* ![テーブル](/help/assets/icons/Table.svg) **[!UICONTROL フリーフォームテーブル]**&#x200B;ビジュアライゼーションを追加します。[パネルへのビジュアライゼーションの追加](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。

## 自動化されたテーブル

テーブルを最もすばやく作成するには、空のプロジェクト、パネル、またはフリーフォームテーブルにコンポーネントを直接ドロップします。推奨される形式のフリーフォームテーブルが作成されます。[こちら](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace)から、チュートリアルをご覧ください。

![訪問回数コンポーネントを作業用スペースにドロップした新しいパネル。](assets/automated-table.png)

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、「**[!UICONTROL テーブルビルダーを有効にする]**」を選択できます。ビルダーを有効にすれば、ディメンション、分類、指標およびフィルターをドラッグ＆ドロップして、より複雑な質問に回答するテーブルを作成できます。「**[!UICONTROL 作成]**」を選択すると、データが更新されます。

![フリーフォームテーブルビルダーの表示](assets/table-builder.png)

## インタラクション

フリーフォームテーブルは、様々な方法で操作およびカスタマイズできます。

### フィルタリングと並べ替え

* テーブルのデータの[フィルタリングと並べ替え](filter-and-sort.md)を行うことができます。

### 行

* ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg) を使用すると、1 つ以上の行から[新しいビジュアライゼーションをすばやく作成](../freeform-analysis-visualizations.md#visualize)できます。
* プロジェクトの[表示密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md)を調整すると、1 つの画面に表示する行を増やすことができます。
* 各ディメンション行は、ページネーションの前に最大 400 行を表示できます。最初の列ヘッダーの&#x200B;**[!UICONTROL 行]**&#x200B;の横にある数字を選択すると、ページにさらに多くの行が表示されます。最初の列ヘッダーの ![ChevronRight](/help/assets/icons/ChevronRight.svg) を使用して別のページに移動します。
* 追加のコンポーネントごとに行を分類できます。複数の行を一度に分類するには、複数の行を選択し、次のコンポーネントを選択した行の上にドラッグします。[分類](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)について説明します。
* 行を[フィルタリング](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)して、表示する項目数を減らすここができます。[行設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)で追加の設定を使用できます。

### 列

* 列内にコンポーネントを積み重ねて、フィルター適用済み指標やクロスタブ分析などを作成できます。
* 各列の表示は、[列設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)で調整できます。
* [コンテキストメニュー](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)からはいくつかのアクションを実行できます。メニューには、テーブルヘッダー、行または列のいずれを選択するかに応じて、異なるアクションが表示されます。


## 設定

![設定](/help/assets/icons/Setting.svg) を選択して、**[!UICONTROL テーブル設定]**&#x200B;を表示します。次の特定のビジュアライゼーション[設定](../freeform-analysis-visualizations.md#settings)が使用できます。

### データソース

| オプション | 説明 |
|---|---|
| **[!UICONTROL リンクされたビジュアライゼーション]**。 | すべてのリンクされたビジュアライゼーションを一覧表示します。 |
| **[!UICONTROL データソースを表示]** | オフにすると、ビジュアライゼーションのデータソースとして機能するフリーフォームテーブルは、ワークスペースで非表示になります。 |

### 設定

| オプション | 説明 |
|---|---|
| **[!UICONTROL 各列の日付をすべて同じ行から始まるように整列]** | 各列の日付をすべて同じ行から始まるように整列するかしないかを指定します。 |


## コンテキストメニュー

次の[コンテキストメニュー](../freeform-analysis-visualizations.md#context-menu)オプションは、ビジュアライゼーションのヘッダーから使用できます。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL コピーしたビジュアライゼーションを挿入]** | コピーしたビジュアライゼーションをプロジェクト内の別の場所または完全に別のプロジェクトにペースト（「挿入」）します。 |
| **[!UICONTROL クリップボードにデータをコピー]** | ビジュアライゼーションからクリップボードにデータをコピーします。 |
| **[!UICONTROL クリップボードに選択範囲をコピー]** | ビジュアライゼーションからクリップボードに選択範囲をコピーします。 |
| **[!UICONTROL 項目を CSV（*ディメンション名*）としてダウンロード]** | ビジュアライゼーションのディメンション項目（最大 50,000 個）をローカルデバイスにすぐにダウンロードします。選択したディメンションの最大ディメンション項目数は 50,000 個です。 |
| **[!UICONTROL ビジュアライゼーションをコピー]** | ビジュアライゼーションをコピーして、プロジェクト内の別の場所または完全に別のプロジェクトにビジュアライゼーションを挿入できるようにします。 |
| **[!UICONTROL データ CSV をダウンロード]** | ビジュアライゼーションの表示データをローカルデバイスにすぐにダウンロードします。 |
| **[!UICONTROL ビジュアライゼーションを複製]** | ビジュアライゼーションの完全な複製を作成します。 |
| **[!UICONTROL 説明を編集]** | ビジュアライゼーションの説明テキストを追加（または編集）します。[テキスト](../text.md)を参照してください。 |
| **[!UICONTROL ビジュアライゼーションリンクを取得]** | リンクをコピーして、ビジュアライゼーションと直接共有します。 共有リンクダイアログにリンクが表示されます。「コピー」を選択して、リンクをクリップボードにコピーします。 |
| **[!UICONTROL やり直し]** | 現在のビジュアライゼーションの設定を削除し、ゼロから再設定できるようにします。 |



## ビデオ

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フリーフォームテーブルビルダーの概要](https://video.tv.adobe.com/v/31318?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フリーフォームテーブルフィルター](https://video.tv.adobe.com/v/23232?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フリーフォームテーブルの合計](https://video.tv.adobe.com/v/29273?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


>[!MORELIKETHIS]
>
>[パネルへのビジュアライゼーションの追加](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[ビジュアライゼーション設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[ビジュアライゼーションコンテキストメニュー](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>



