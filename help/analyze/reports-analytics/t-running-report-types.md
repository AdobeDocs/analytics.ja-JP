---
description: 異なるレポートタイプの実行手順を説明します。
title: 異なるレポートタイプの実行
topic: Reports,Reports and analytics
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 異なるレポートタイプの実行

異なるレポートタイプの実行手順を説明します。


## ランクレポートの実行 {#task_C570BA4A213F4F2EB7B30E012934BE7D}

ランクレポートでは、指標に関するレポートページのランクが、数や割合に応じて表に表示されます。 ランクレポートでは、1 つのレポートに複数の指標を表示できます。

<!-- 

t_reports_ranked.xml

 -->

1. (> > [!UICONTROL Pages Report] )などのレ **[!UICONTROL Reports]** ポート **[!UICONTROL Site Content]** を生成 **[!UICONTROL Pages]**&#x200B;する。
1. In the report header, click **[!UICONTROL Ranked.]**
1.  レポートのランクを設定するには、テーブルの列ヘッダーをクリックします。

   ランクレポートには、表に 200 個までの行項目（製品、カテゴリ、Web ページなど）と 10 個までの指標（売上高、注文件数、表示回数など）を含めることができます。

## トレンドレポートの実行 {#task_F03B4E760B9E4EA29FC3F654E6316887}

トレンドレポートには、経時的に指標が表示されます。 このレポートタイプは、セグメントのある期間から次の期間へのパフォーマンスを確認する場合に使用します。

<!-- 

t_reports_trended.xml

 -->

ほとんどのコンバージョンレポートとトラフィックレポートでは、トレンド表示を使用できます。 を使用 [!UICONTROL Calendar]すると、月内の日、年内の週、四半期内の週、年内の月など、どの期間の内訳でも改善を表示できます。 トレンドレポートは、最大 5 つまでの項目（製品、カテゴリ、Web ページなど）に対して 1 つの指標（売上高、注文、表示回数など）のトレンドを表示できます。

**トレンドレポートを実行するには**

1. > >などのコンバージョンまたはトラフィックレポ **[!UICONTROL Reports]** ートを **[!UICONTROL Site Content]** 実行しま **[!UICONTROL Pages]**&#x200B;す。
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

## コンバージョンファネルレポートの実行 {#task_B926A74AA6A641138C2986C1635120CB}

コンバージョンファネルレポートには、一連の訪問者を経て望ましい行動をとるに至ったイベントの割合が表示されます。 例えば、Webページの訪問者のうち、買い物かごに訪問者を追加し、購入に至った人の数を確認できます。 このレポートには、途中で離脱した人の数も表示されます。

<!-- 

t_reports_conversion_funnel.xml

 -->

このレポートを実行するには、ページレポートなどのレポートを選 **[!UICONTROL Reports]** 択しま **[!UICONTROL Campaigns]** す(// **[!UICONTROL Tracking Code]** > **[!UICONTROL Campaign Conversion Funnel]**)。

詳しくは、[コンバージョンレポート](https://marketing.adobe.com/resources/help/ja_JP/reference/reports_conversion.html)を参照してください。

## フォールアウトレポートの実行 {#task_8FD97C8260464F9DA731A93DB8F80184}

に、事 [!UICONTROL Fallout Report] 前に指定された一連のページを訪問した訪問者の数を示します。 また、各ステップ間のコンバージョン率とフォールアウト率も表示されます。

<!-- 

t_reports_fallout.xml

 -->

Workspace Workspaceの新しいフォールアウ [ト分析](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/fallout_flow.html) ・パネルを分析

1. で、// [!UICONTROL Adobe Analytics]/をク **[!UICONTROL Reports]** リック **[!UICONTROL Paths]** しま **[!UICONTROL Pages]** す **[!UICONTROL Fallout]**。
1. ページ上で、 [!UICONTROL Fallout Report] をクリックしま **[!UICONTROL Launch the Fallout Report Builder]**&#x200B;す。

   ![手順の結果](assets/fallout_add_items.png)

1. On the [!UICONTROL Define Checkpoints] page, specify the checkpoints that you want to use for the report.
1. クリック **[!UICONTROL Run Report]**.

   ![手順の結果](assets/fallout_report.png)

>[!MORELIKETHIS]
>
>* [フォールアウトレポートの説明](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-fallout.translate.html)


## ページフローレポートの実行 {#task_133E8B87C3F04DA0A42D10CBA499305B}

ページフローレポートは、訪問者がページにアクセスし、サイト内を移動した順序を示します。 このレポートは回答に役立ちます

Workspaceで新しいフロービジュアライゼ [ーションを](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/flow.html) 分析

パスレポー [トを実](https://marketing.adobe.com/resources/help/ja_JP/reference/reports_paths.html) 行します。

例えば、/// **[!UICONTROL Reports]** をク **[!UICONTROL Paths]** リック **[!UICONTROL Pages]** します **[!UICONTROL Next Page Flow]**。

![](assets/page_flow.png)

このレポートは、選択したページから始めて左から右へ読みます。 選択したページの後に閲覧されたページは、右側に分岐として表示されます。

後続の各ページが閲覧された割合が、ページ名の横に表示されます。 次の各ページに接続される線の幅は、この相対的な割合を示します。

**[!UICONTROL Path Views]**:表示されたパスに従って、あるページが表示された回数を示します。

例えば、プライバシーポリシーページの総ページビュー数は 10,000 であっても、ホームページを見た直後にこのページを閲覧したのはそのうち 500 のみだったとすると、この場合のパスビュー数は 500 になります。このようにして、パス表示という用語が使用されます。

相対的な割合は、線の相対的な幅で示されます。 このレポートには、デフォルトで5つの2次レベルの分岐と5つの3次レベルの分岐が表示されます。2次レベルの分岐は10本まで、3次表示は5本までできます。 これにより、レポートの高さが高くなり、グラフ全体をスクロールして表示にする必要があります。

## ファネルレポートの実行 {#task_2BBF6FACD48F479E8B2EE458919941CB}

成功オプションをイベントし、レポートまたはレ [!UICONTROL Purchase Conversion Funnel] ポートに追加することがで [!UICONTROL Product Conversion Funnel] きます。

<!-- 

t_reports_funnel.xml

 -->

1. /製品コンバ **[!UICONTROL Reports]** ージョンフ **[!UICONTROL Products]** ァネル [をクリックします](https://marketing.adobe.com/resources/help/ja_JP/reference/reports_conversion_funnel.html)。

## マーケティングチャネルレポートの実行 {#task_64ADED5CC75248319E06E3E029B47F78}

マーケティングチャネルレポートは、ファーストタッチとラストタッチのチャネル配分の概要レポートと、売上高、注文件数、コストなどの標準的なレポート指標を提供します。 これらのレポートを使用すると、各チャネルが生み出す売上高を分析できます。

<!-- 

t_reports_marketing_channel.xml

 -->

See the [Marketing Channel](https://marketing.adobe.com/resources/help/ja_JP/mchannel/index.html) help system for more information.

## 異常値検出レポートの実行 {#task_4808C96327354D789C075823F5C3A049}

異常値検出レポートに表示される概要グラフと個別の指標グラフの見方を説明します。

<!-- 

t_anomaly_view.xml

 -->

Analysis Workspace の新しい[異常値検出と貢献度分析](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/anomaly_detection.html)機能を調べます。

**[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Anomaly Detection]** .

>[!NOTE]Analysis Workspace プロジェクト内からも異常値検出を実行できます。[さらに詳しく...](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/anomaly_detection.html)

異常値検出の設定について詳しくは、リファレンスガイドを参照 [してください](https://marketing.adobe.com/resources/help/en_US/sc/user/index.html#Setting_up_Anomaly_Detection)。

異常値検出は、次の2種類のグラフを表示します。サマリグラフと個々の指標のグラフ。 個々の指標グラフは、その指標に対して1つ以上の異常値が検出された場合にのみ表示されます。

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>グラフのタイプ </p> </th> 
   <th colname="col2" class="entry"> <p>機能 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>概要グラフ </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">各ボックスは、以下の指標に対応する、1日に1つの異常値を追跡します。 </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">緑はトレンドラインより上の異常値を示し、青はトレンドラインより下の異常値を示します。 </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">異常値の強さを示します。異常値が大きいほど、データポイントの色が濃くなり、トレンドラインから遠くなります。 </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">個々の異常値をクリックすると、その異常値の個々の指標グラフ（概要グラフの下）が上に表示されます。 </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">偏差率の値（グラフの左）は、次のように計算されます。 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">上限と期待値が同じ場合、偏差率は100%です。 </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">それ以外の場合は、偏差率は「((実際の値 – 上限値) / (上限値 – 期待値)) * 100」で計算されます。 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">下限値と期待値が等しい場合は、偏差率は –100% になります。 </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">それ以外の場合は、偏差率は「((下限値 – 実際の値) / (期待値 – 下限値)) * -100」で計算されます。  </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">「<span class="uicontrol">表示セグメント</span>」をクリックすると、異常値検出レポートにセグメントを適用するためのセグメントパネルが表示されます。セグメントについての<a href="https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/"  >詳細</a>を参照してください。 </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">「<span class="uicontrol">指標を編集</span>」をクリックすると、異常値を検出する指標の選択および選択解除が行えます。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>個々の指標グラフ </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">個々のトレンド指標（計算指標を含む）の異常なデータポイントをドットで表示します。 </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">異常値の数別に、最新の異常値を上位および下位に表示します。 </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">実線を表示して、現在収集されている実際のデータを示します。 これは、エラーの予測とマージンと比較され、データポイントが異常かどうかを判断します。 </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">履歴データ（トレーニング期間）に基づく予測を表す点線を表示します。 </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">灰色の網掛けで、95%の信頼区間の上限と下限を表示します。 </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">指標名の横にある上向きまたは下向きの重複をクリックして、個々のレポートを折りたたんだり展開したりできます。 </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">概要レポート（上記を参照）のドリルダウンに反応して、指標グラフの表示順序を変更します。 </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">すべてのページ関連指標に対して「ページ」などの検索用語を使用して、グラフをフィルタリングできます。 </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">定義したすべての指標または異常値を持つ指標のみを表示できます。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 異常値検出の設定 {#task_AF347B34F56E44A6AE70E019B6EB2F08}

異常値検出のレポートスイート、指標、トレーニング期間、表示期間を選択する手順を説明します。

<!-- 

t_anomaly_config.xml

 -->

異常値検出は、各レポートスイートに対して個別に設定します。

1. に移動しま **[!UICONTROL Analytics > Reports > Site Metrics > Anomaly Detection]** す。
1. 異常値検出を毎日追跡したいレポートスイートを選択します。レポートスイートのリストを表示するには、レポートスイートセレクターのドロップダウンメニューをクリックします。
1. To select the metrics and/or define filtered metrics, click **[!UICONTROL Edit Metrics]** at the top right of the screen:  ![](assets/metrics_icon.png).

   全指標のリスト（計算指標を含む）または追跡指標のリストから、必要な指標を選択できます。特定の条件に基づいてフィルターし、リストを絞り込むこともできます。1. Once the report has been generated, define the **[!UICONTROL Training Period]** and the **[!UICONTROL View Period]** for anomaly detection. （トレーニング期間は、このアルゴリズムの「学習期間」と考えてください）。

   ![](assets/view_training_periods.png)

   次の点に注意してください。

* トレーニング期間は、表示期間の直前に終了します。
* どちらの場合もデフォルトは30日で、60日または90日に延長できます。
* トレーニング期間を延長すると、データのコンテキストが大きくなり、異常値のサイズが小さくなる場合があります。

   異常値検出指標レポートは、パラメータを変更するたびに更新されます。
1. (Optional) Apply segments to the report by clicking **[!UICONTROL Show Segments]** and selecting one or more existing segments or creating a new segment and applying it.

   ![](assets/ad_top_menu.png)

   セグメントの作成と管理について詳しくは、[Analytics セグメント化ガイド](https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/)を参照してください。1.（オプション）レポートをお気に入りにするか、ブックマークします。
1. （オプション）表示期間の終了日を変更します。デフォルトは昨日です。
1. これで、レポートを表示できるようになります。[異常値検出グラフの表示](/help/analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049)。

## リアルタイムレポートの実行 {#task_5D25929C918E40B18965222FA94176B0}

リアルタイムレポートの表示方法と見方を説明します。

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL Reports > Site Metrics > Real-Time]**&#x200B;を参照してください。

リアルタイムレポートオファーには、概要レポートと詳細レポートの2つの主要なレポートがあります。 各レポートレットは複数のレポートレットで構成されます。

リアルタイムレポートの設定について詳しくは、 [Analyticsリファレンスガイドを参照してください](https://marketing.adobe.com/resources/help/ja_JP/reference/index.html#RealTime_Reports_Configuration)。

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UIコンポーネント </th> 
   <th class="chdeschd"> 説明 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>レポートスイートの選択</strong></td> 
   <td class="chdesc stentry"> このリアルタイムレポートに表示するレポートスイートを選択します。レポートスイートを変更する方法については、<a href="https://marketing.adobe.com/resources/help/ja_JP/reference/t_realtime_admin.html"  >リアルタイムレポートの設定</a>を参照してください。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>レポートの切り替え</strong></td> 
   <td class="chdesc stentry"> 設定済みのレポート（最大 3 つ）を切り替えることができます。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>時間範囲の選択</strong></td> 
   <td class="chdesc stentry"> このレポート内のすべてのレポートレットで使用する全体的な時間範囲を選択します。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>レポートの設定</strong></td> 
   <td class="chdesc stentry"> この歯車アイコンは、ユーザーが管理者権限を持つ場合にのみ表示されます。このアイコンをクリックすると、<span class="ignoretag"><span class="uicontrol">管理ツール</span>／<span class="uicontrol">レポートスイート</span>／<span class="uicontrol">設定を編集</span>／<span class="uicontrol">リアルタイム</span></span>の下にある Report Suite Manager が表示されます。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>フルスクリーン表示</strong></td> 
   <td class="chdesc stentry"> フルスクリーン表示アイコンは、モニターの縦横比が 16:9 または 16:10 であり、かつ、ブラウザーがフルスクリーン表示をサポートしている場合にのみ表示されます。フルスクリーン表示モードの間は操作ができないことに注意してください（元の表示に戻るには <span class="uicontrol">Esc</span> キーを押します）。フルスクリーン表示モードにタイムアウトはありません。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>サイトトラフィックレポートレット</strong></td> 
   <td class="chdesc stentry"> 青いトレンドラインデータは、サイト全体のトラフィックの合計を示します。 X軸はリテラルラベル（15分前、10分前）を使用しますが、現在の値はリアルタイム式として表示されます。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>サイト合計レポートレット</strong></td> 
   <td class="chdesc stentry"> リアルタイムレポートで選択された指標の、過去N分間のサイト合計の数を表示します。 「N」は、時間範囲セレクターで設定できます。 <p>矢印の色と方向は、次のアルゴリズムに基づきます。 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">大幅な増加（上向き矢印）:&gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">ゲイン（上向き右向き矢印）:5 ～ 100% </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> フラット（右向き矢印）:5% ～ -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> 損失（右下向き矢印）:-5% ～ -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> 大幅な損失（下向き矢印）:&lt; -100% </li> 
      </ul> </p> <p>サイトの合計が「インスタンス」でレポートされる場合、これらのインスタンスはプライマリレポートレットのディメンションを反映します。 インスタンス固有の名前(「ページ表示」など)が存在する場合は、その名前がサイト合計に表示されます。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>プライマリレポートレット</strong></td> 
   <td class="chdesc stentry"> リアルタイムレポートのプライマリディメンションとその指標に関するレポートです。 選択した時間範囲のその要素のトレンドラインを表示します。 指標の合計は、トレンドライン全体の合計を表します。 矢印は、アイテムが強く上昇しているか、上昇しているか、横ばいか、負けているか、または強く下降しているかを示します。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>検索ダイアログ</strong></td> 
   <td class="chdesc stentry"> この検索は、すべてのレポートレットに影響を与えます。 検索は、レポートの表示時に保持されます。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>並べ替え... 最頻使用／勝者／敗者</strong></td> 
   <td class="chdesc stentry"> <span class="uicontrol">最頻使用</span>（デフォルト）、<span class="uicontrol">勝者</span>（最も大きく上昇したディメンション）、<span class="uicontrol">敗者</span>（最も大きく下降したディメンション）の順で並べ替えることができます。 <p>リアルタイムレポートで勝者または敗者を判定する際には、最古のサンプルと最新より 1 つ前のサンプルが参照され、単純な変化率の計算が行われます。したがって、「過去 15 分間」を選択していて、n が現在の分を表す場合には、n-1 と n-15 を比較することになります。現在、リアルタイムは重み付けを行いません。 現在の分は無視されます。これは、完了しておらず、誤った%の変化が生じる可能性が高いからです。 </p> <p>この数式は、リアルタイムレポートで使用されるすべての指標で一致します。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>セカンダリ 1 レポートレット</strong></td> 
   <td class="chdesc stentry"> プロビジョニングされた2番目のレポートのディメンションと指標に関するリアルタイムレポートを表示します。 <p>セカンダリ1レポートレットには、上位4つのカテゴリが表示され、5つ目は残りの値の集計です。 各カテゴリに対して、そのカテゴリの生表示の合計が表示されます。 さらに、すべてのカテゴリの合計が中央に表示されます。 </p> <p> セクションにカーソルを重ねると、関連するカテゴリが強調表示され、カテゴリのトレンドラインがドーナツグラフの下に表示されます。 </p> <p> 行項目にカーソルを重ねると、その行項目と関連するセクションが強調表示され、カテゴリのトレンドラインがドーナツグラフの下に表示されます。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>セカンダリ 2 レポートレット</strong></td> 
   <td class="chdesc stentry"> プロビジョニングされた3番目のレポートのディメンションと指標に関するリアルタイムレポートを表示します。 項目ラベルの上にカーソルを置くと、ラベルが右にスライドし、カーソルを置いた項目のトレンドラインが表示されます。 </td> 
   </tr> 
   </table>

1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **項目トレンドレポートレット** | 概要レポートで選択した項目の、過去N分間のトレンドラインを表示します。 Nは、時間範囲セレクターで設定できます。 |
   |---|---|
   | **項目合計レポートレット** | 概要レポートで選択した項目の、過去N分間の指標の合計数を表示します。 Nは、時間範囲セレクターで設定できます。 |
   | **相関するセカンダリ1レポートレット** | このレポートレットはセカンダリ1レポートレットと非常に似ています。 唯一の違いは、このレポートに入力するデータソースです。この例では、特定のページ（概要レポートのプライマリレポートレットで選択したページ）と表示されたインスタンスとの相関関係（または分類）を示しています。 |
   | **相関するセカンダリ2レポートレット** | このレポートレットはセカンダリ2レポートレットと非常に似ています。 唯一の違いは、このレポートに入力するデータソースです。この例では、特定のページ（概要レポートのプライマリレポートレットで選択したページ）と言語ディメンションとの間の相関関係（または分類）を示しています。 |
