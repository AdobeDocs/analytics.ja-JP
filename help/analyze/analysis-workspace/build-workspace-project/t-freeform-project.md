---
description: プロジェクトを作成して、コンポーネント（ディメンション、指標、セグメントおよびデータ範囲）をフリーフォームパネルに追加します。
keywords: Analysis Workspace
title: Workspace プロジェクトの作成
topic: Reports and analytics
uuid: c1def77a-a76e-4699-9feb-1ede5b70b7ba
translation-type: tm+mt
source-git-commit: cf88e73a67db9ba55ba6721df57e3c2db649b31d
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 99%

---


# Workspace プロジェクトの作成

プロジェクトを作成して、コンポーネント（ディメンション、指標、セグメントおよびデータ範囲）をフリーフォームパネルに追加します。

この記事では、Analysis Workspace インターフェイス要素について説明し、プロジェクトの作成方法を示します。

## プロジェクトの作成

1. プロジェクトを作成およびキュレーションするためのユーザー権限を指定します。

   Analysis Workspace プロジェクトを作成またはキュレーションするユーザーは、先に、管理者に **[!UICONTROL Analysis Workspace のプロジェクトを作成／キュレーション]**&#x200B;権限を有効にしたグループか、**[!UICONTROL 全レポートアクセス]**&#x200B;ユーザーグループに追加してもらう必要があります（**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー管理]**／[グループ](https://docs.adobe.com/content/help/ja-JP/analytics/admin/user-product-management/user-groups/groups.html)。）

1. [!DNL Experience Cloud] で、**[!UICONTROL Analytics]**／**[!UICONTROL Workspace]** をクリックします。

   ![](assets/analysis_workspace_menu.png)

   または、スラッシュ（/）を入力してレポート検索バーを開き、「*`workspace`*」と入力します。

   ![](assets/analysis-app-search.png)

1. 「**[!UICONTROL 新規プロジェクトを作成]**」をクリックします。

   以下からプロジェクトを作成するかどうかを選択できます。

* 空白のプロジェクト（デフォルト）。手順については、以下を参照してください。
* 標準テンプレート。これらのテンプレートは、アドビによって作成され、標準で提供されます。手順については、[テンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)を参照してください。
* カスタムテンプレート。これらのテンプレートは、管理者権限を持つユーザーによって作成されます。手順については、[テンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)を参照してください。

   ![](assets/start_modal.png)

1. 空のプロジェクトからプロジェクトを作成するには、「**[!UICONTROL 空のプロジェクト]**」をクリックします。

   * 次に、「**[!UICONTROL 作成]**」をクリックするか、または
   * 単に **[!UICONTROL Enter]** キーを押します。

   空のプロジェクトが表示され、フリーフォームパネルとデータテーブルビジュアライゼーションが表示されます。

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >プロジェクトに含まれているコンポーネント（指標またはディメンション）の一部がレポートスイートに含まれていないプロジェクトをロードする（またはレポートスイートに切り替える）と、「互換性のないレポートスイート」というメッセージが表示される場合があります。互換性のないコンポーネントのリストを表示できるので、このメッセージが表示される理由を把握できます。

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > コンポーネント</a> </td> 
   <td colname="col2"> <p>プロジェクトにドラッグできるディメンション、指標、セグメントおよび日付範囲。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > ビジュアライゼーション</a> </td> 
   <td colname="col2"> <p>インターフェイスのパネルまたはプロジェクト領域にドラッグできる項目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table.md"  >フリーフォームパネル</a> </td> 
   <td colname="col2"> <p>Analysis Workspace で操作するキャンバスまたはワークスペース。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. プロジェクトを保存します。プロジェクトに名前を付け、説明を入力し（オプションですが便利です）、タグ付け（オプション）をおこない、「**[!UICONTROL プロジェクトを保存]**」をクリックします。

   ![](assets/save_project.png)

1. ビジュアライゼーションまたはパネルを右クリックしてコピーし、コピーした要素をプロジェクト内の別の場所、または別のプロジェクトに貼り付ける（「挿入する」）ことができるようになりました。

   この機能を使用すると、ビジネスに固有のデータで「構築ブロック」（定義済みのビジュアライゼーション／パネル）を作成し、他のプロジェクトにコピーして作業を迅速化できます。

   >[!NOTE]
   >
   >コピーまたは名前を付けて保存した後でも、内部リンクは、コピー元のプロジェクトではなく、内部のプロジェクトに対して相対的になりました。

## コンポーネントとビジュアライゼーションの追加 {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. プロジェクトを作成するには、*`components`* および *`visualizations`* をプロジェクトにドラッグします。

   **コンポーネント**

   コンポーネントツールバーには、最もよく使用する、検索可能なディメンション、指標、セグメントおよび日付範囲が表示されます。

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コンポーネント </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ディメンション（オレンジ） </td> 
   <td colname="col2"> <p>プロジェクトレベルに適用します </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop の番号、eVar の番号およびイベントの番号がディメンション名に追加され、これらの番号を検索できます。例：「内部キャンペーン」は、左側のパネルに「内部キャンペーン (evar2)」と表示されます。 </p> <p> 表示文字数を短くするために、prop、eVar、イベントの番号はテーブルに表示されません。 </p> <p>一部の事前設定済みディメンションには、フリーフォームテーブルにドラッグする場合または左側のパネルに表示される場合のデフォルトの並べ替え順があります。例えば、「時間帯」がテーブルにドロップされる場合または左側のパネルに表示される場合、午前 12 時～午後 11 時の順に並べ替えられます。指標列で並べ替えるオプションは現在も使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 指標（緑） </td> 
   <td colname="col2"> <p>プロジェクトレベルに適用します。 </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> 「<span class="term">回数</span>」は、データテーブルのデフォルト指標です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セグメント（青） </td> 
   <td colname="col2"> <p>パネルレベルにのみドラッグできますが、データテーブルにインラインセグメントを作成できます。 </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>詳しくは、 <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > セグメント </a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日付範囲および精度（紫） </td> 
   <td colname="col2"> <p>パネルレベルにのみドラッグできます。日付範囲を設定する際に、カレンダーからプロジェクトを作成できます。 </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

[!UICONTROL ビジュアライゼーション]パネルには、標準の Analytics グラフ、チャート、ドーナツ、データテーブル、[コホート](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)テーブル、ベン図などが用意されています。複数のビジュアライゼーションをプロジェクトにドラッグ＆ドロップできます。

![手順の結果](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. 手順

## 右クリックメニューを使用したデータのカスタマイズ {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

右クリックメニューを使用すると、右クリックしたテーブルのセルに応じて、次のアクションを実行できます。

![手順の結果](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アクション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 期間列を追加</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 期間を比較</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クリップボードにコピー </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>選択したアイテムの削除 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > 選択からアラートを作成</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > 分類</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">ディメンション </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">指標 </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">セグメント </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">時間 </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 視覚化</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  > CSV としてダウンロード</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/home.md"  > トレンド選択</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > 選択からセグメントを作成</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"  > セグメント比較で実行</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 選択した行のみを表示 </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> すべての行を表示 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

行のコピーおよび選択について詳しくは、[Analysis Workspace で使用できるキーボードおよびマウスの操作](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を参照してください。
