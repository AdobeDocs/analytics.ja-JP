---
description: 異なるレポートタイプの実行手順を説明します。
title: 異なるレポートタイプの実行
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics の基本
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 97%

---

# 異なるレポートタイプの実行

異なるレポートタイプの実行手順を説明します。

## ランクレポートの実行 {#task_C570BA4A213F4F2EB7B30E012934BE7D}

ランクレポートでは、指標の大小で並べ替えられた項目がテーブルに表示されます。ランクレポートでは、1 つのレポートに複数の指標を表示できます。

1. [!UICONTROL ページレポート]などのレポートを生成します（**[!UICONTROL レポート]**／**[!UICONTROL サイトコンテンツ]**／**[!UICONTROL ページ]**）。
1. レポートタイプで「**[!UICONTROL ランク]**」をクリックします。
1.  レポートのランクを設定するには、テーブルの列ヘッダーをクリックします。

   ランクレポートには、表に 200 個までの行項目（製品、カテゴリ、Web ページなど）と 10 個までの指標（売上高、注文件数、表示回数など）を含めることができます。

## トレンドレポートの実行 {#task_F03B4E760B9E4EA29FC3F654E6316887}

トレンドレポートには、時系列で指標が表示されます。このレポートタイプは、指定した期間における指定の増減を表示するために使用します。

ほとんどのコンバージョンとトラフィックレポートではトレンドを表示できます。[!UICONTROL カレンダー]を使用すると、月内の日、年内の週、四半期内の週、月など、どの期間ごとのパフォーマンスの改善も見ることができます。トレンドレポートは、最大 5 つまでの項目（製品、カテゴリ、Web ページなど）に対して 1 つの指標（売上高、注文、表示回数など）のトレンドを表示できます。

**トレンドレポートを実行するには**

1. **[!UICONTROL レポート]**／**[!UICONTROL サイトコンテンツ]**／**[!UICONTROL ページ]**&#x200B;などの変換またはトラフィックレポートを実行します。
1. 「**[!UICONTROL レポートタイプ]**」の「**[!UICONTROL トレンド]**」をクリックします。

## フォールアウトレポートの実行 {#task_8FD97C8260464F9DA731A93DB8F80184}

[!UICONTROL フォールアウトレポート]には、事前に指定されたページ順に訪問した訪問者の数が表示されます。ステップ間のコンバージョン率とフォールアウト率も示します。

Analysis Workspace の新しい[フォールアウト分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=ja)パネルを調べます。

1. [!UICONTROL Adobe Analytics] で、**[!UICONTROL レポート]**／**[!UICONTROL パス]**／**[!UICONTROL ページ]**／**[!UICONTROL フォールアウト]**&#x200B;をクリックします。
1. [!UICONTROL フォールアウトレポート]ページで、「**[!UICONTROL フォールアウト Report Builder の起動]**」をクリックします。

   ![手順の結果](assets/fallout_add_items.png)

1. [!UICONTROL チェックポイントの定義ページで]、レポートに使用するチェックポイントを指定します。
1. 「**[!UICONTROL レポートを実行]**」をクリックします。

   ![手順の結果](assets/fallout_report.png)

## ページフローレポートの実行 {#task_133E8B87C3F04DA0A42D10CBA499305B}

ページフローレポートには、訪問者がページにアクセスした順序と使用したナビゲーション方法が表示されます。このレポートは問題を解決するのに役立ちます。

Analysis Workspaceの[フロービジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)を確認します。

例えば、**[!UICONTROL レポート]**／**[!UICONTROL パス]**／**[!UICONTROL ページ]**／**[!UICONTROL 次ページのフロー]**&#x200B;をクリックします。

## マーケティングチャネルレポートの実行 {#task_64ADED5CC75248319E06E3E029B47F78}

マーケティングチャネルレポートには、ファーストタッチチャネルおよびラストタッチチャネルの配分の概要、および注文件数、売上高、コストなどの標準のレポート指標が表示されます。これらのレポートでは各チャネルが生み出す売上高を調べることができます。

詳細については、[マーケティングチャネル](/help/components/c-marketing-channels/analyze-mc.md)のヘルプシステムを参照してください。

## 異常値検出レポートの実行 {#task_4808C96327354D789C075823F5C3A049}

[異常値検出と貢献度分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=ja)は、Analysis Workspaceでのみ実行できます。

## リアルタイムレポートの実行 {#task_5D25929C918E40B18965222FA94176B0}

リアルタイムレポートの表示方法と見方を説明します。

**[!UICONTROL レポート／サイト指標／リアルタイム]**。

リアルタイムレポートには、概要レポートと詳細レポートという 2 つのメインレポートがあります。それぞれは複数のレポートレットから構成されています。

リアルタイムレポートの設定については、[Analytics リファレンスガイド](https://experienceleague.adobe.com/docs/analytics/landing/home.html#RealTime_Reports_Configuration)を参照してください。

1. **[!UICONTROL 概要]**&#x200B;レポートとそのコンポーネントをひととおり確認します。![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UI コンポーネント </th> 
   <th class="chdeschd"> 説明 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>レポートスイートの選択</strong></td> 
   <td class="chdesc stentry"> このリアルタイムレポートに表示するレポートスイートを選択します。レポートスイートを変更する方法については、<a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html"  >リアルタイムレポートの設定</a>を参照してください。 </td> 
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
   <td class="chdesc stentry"> 青いトレンドラインデータは、サイト全体のトラフィックの合計を表します。X 軸ではリテラルラベル（15 分前、10 分前など）を使用しますが、現在値はリアルタイムのエクスプレッションとして表示されます。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>サイト合計レポートレット</strong></td> 
   <td class="chdesc stentry"> このリアルタイムレポートで選択されている指標の、過去 N 分間のサイト合計の数を表示します。N の数値は時間範囲セレクターで設定できます。 <p>矢印の色と向きは、次のアルゴリズムに基づいて決定されます。 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">大きく上昇（上向き矢印）：100% 超 </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">上昇（右上向き矢印）：5% ～ 100% </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> 横ばい（右向き矢印）：5% ～ -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> 下降（右下向き矢印）：-5% ～ -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> 大きく下降（下向き矢印）：-100% 未満 </li> 
      </ul> </p> <p>サイト合計が「インスタンス」単位でレポートされる場合は、このインスタンス数はプライマリレポートレット内のディメンションを反映しています。インスタンス固有の名前（「ページビュー数」など）が存在している場合は、その名前がサイト合計に表示されます。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>プライマリレポートレット</strong></td> 
   <td class="chdesc stentry"> このリアルタイムレポートのプライマリディメンションとその指標に関するレポートです。選択されている時間範囲での各要素のトレンドラインを表示します。指標合計は、トレンドライン全体の合計を表します。矢印は各項目の増減を表します（大きく上昇、上昇、横ばい、下降、大きく下降）。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>検索ダイアログ</strong></td> 
   <td class="chdesc stentry"> この検索結果はすべてのレポートレットに影響を与えます。検索結果は、レポートを表示している間は維持されます。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>並べ替え... 最頻使用／勝者／敗者</strong></td> 
   <td class="chdesc stentry"> <span class="uicontrol">最頻使用</span>（デフォルト）、<span class="uicontrol">勝者</span>（最も大きく上昇したディメンション）、<span class="uicontrol">敗者</span>（最も大きく下降したディメンション）の順で並べ替えることができます。 <p>リアルタイムレポートで勝者または敗者を判定する際には、最古のサンプルと最新より 1 つ前のサンプルが参照され、単純な変化率の計算が行われます。したがって、「過去 15 分間」を選択していて、n が現在の分を表す場合には、n-1 と n-15 を比較することになります。リアルタイムレポートは、現時点では重み付けを行いません。現在の分が無視されるのは、その分がまだ完了していないため、誤った変化率が導かれる可能性があるからです。 </p> <p>この計算方法は、リアルタイムレポートで使用されるすべての指標に適用されます。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>セカンダリ 1 レポートレット</strong></td> 
   <td class="chdesc stentry"> プロビジョニングされた 2 番目のレポートのディメンションと指標に関するリアルタイムレポートを表示します。 <p>セカンダリ 1 レポートレットには上位 4 カテゴリが表示され、残るすべての値を集計したものが 5 番目のカテゴリとして表示されます。各カテゴリについて、そのカテゴリの生の合計ビューが表示されます。さらに、全カテゴリの合計が中央に表示されます。 </p> <p> いずれかのセクションにカーソルを重ねると、関連するカテゴリが強調表示され、そのカテゴリのトレンドラインがドーナツグラフの下に表示されます。 </p> <p> 行項目にカーソルを重ねると、その行項目と関連するセクションが強調表示され、カテゴリのトレンドラインがドーナツグラフの下に表示されます。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>セカンダリ 2 レポートレット</strong></td> 
   <td class="chdesc stentry"> プロビジョニングされた 3 番目のレポートのディメンションと指標に関するリアルタイムレポートを表示します。行ラベルにカーソルを重ねると、行ラベルが右にスライドし、その項目のトレンドラインが表示されます。 </td> 
   </tr> 
   </table>

1. プライマリレポートレットのリスト項目をクリックすると、リスト項目の&#x200B;**[!UICONTROL 詳細]**&#x200B;ビューが表示されます。![](assets/rtr_detail_report.png)

   | **アイテムトレンドレポートレット** | 概要レポートで選択した項目の、過去 N 分間のトレンドラインを表示します。N の数値は時間範囲セレクターで設定できます。 |
   |---|---|
   | **アイテム合計レポートレット** | 概要レポートで選択した項目の、過去 N 分間の指標カウントの合計を表示します。N の数値は時間範囲セレクターで設定できます。 |
   | **相関するセカンダリ 1 レポートレット** | このレポートレットはセカンダリ 1 レポートレットによく似ています。両者の違いは、使用されるデータソースだけです。この例では、このレポートレットは特定のページ（概要レポートのプライマリレポートレットで選択したページ）と表示されたインスタンスとの相関を示します。 |
   | **相関するセカンダリ 2 レポートレット** | このレポートレットはセカンダリ 2 レポートレットによく似ています。両者の違いは、使用されるデータソースだけです。この例では、このレポートレットは特定のページ（概要レポートのプライマリレポートレットで選択したページ）と言語ディメンションとの相関を示します。 |
