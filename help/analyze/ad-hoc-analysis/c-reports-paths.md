---
description: Web サイトのページがアクセスされた順序が表示されます。訪問者がサイト上の各ページに達する前と後にどのページにアクセスしたかの情報を収集できます。
seo-description: Web サイトのページがアクセスされた順序が表示されます。訪問者がサイト上の各ページに達する前と後にどのページにアクセスしたかの情報を収集できます。
seo-title: パスレポート
solution: Analytics
title: パスレポート
topic: Ad Hoc Analysis
uuid: 5881cb1c-6d66-49fe- ac84-70b82662acd2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# パスレポート

Web サイトのページがアクセスされた順序が表示されます。訪問者がサイト上の各ページに達する前と後にどのページにアクセスしたかの情報を収集できます。

## Paths reports {#concept_CB32E270FB9E4D929C91FDFE428CB224}

Web サイトのページがアクセスされた順序が表示されます。訪問者がサイト上の各ページに達する前と後にどのページにアクセスしたかの情報を収集できます。

パスレポートには、閲覧されたページのクリックストリームを明らかにする標準分析とオプションの詳細分析が含まれます。完全パス、最長パス、最も頻繁にアクセスされるパスの表示、ページフロー、フォールアウト、ドロップアウトの図解、新しいパターンおよび経時的な変化パターンの表示、入口や出口パスの分析などをおこなうことができます。

** [!UICONTROL Next Page Flow] ** or ** [!UICONTROL Next Site Flow]**: Displays a two-level-deep branching graphic of a selected page (or section, department, and so on), that your visitors view after moving away from the selected page. このレポートを使用して、選択されたページを閲覧した後に訪問者が最もよくとるステップを分析し特定することができます。以下の操作をおこなうことができます。

* 選択されたページを閲覧した後に最も多くおこなわれた手順を把握します。
* 訪問者を目的のページに誘導するよう、サイトのパス設計を最適化します。
* 訪問者が、想定したページ以外のどのページへ移動しているかを特定します。

** [!UICONTROL Next Page] ** (or next categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed after seeing a selected page. 例えば、サイト全体を選択してレポートするとき、レポートには最上位 10 のランディングページに続いて、各ランディングページの次に最頻訪問されるページが 5 つずつ表示されます。このデータは、どのコンテンツ、特集などが最もよく訪問者をひきつけてサイト内を移動させるかを把握するのに役立ちます。を参照してください。

** [!UICONTROL Previous Page Flow] ** (or other previous categories flow): Displays two levels of the most popular pages that your visitors view before the selected page. また、訪問者がサイトに来訪した時間が強調表示されます。

** [!UICONTROL Previous Page] ** (or other previous categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed before seeing a selected page on your site.

** [!UICONTROL Fallout] **: Displays the visit attrition and conversion rates between each checkpoint you define. ステップが上から下へ順に表示されます。それぞれの行番号と割合が左側に、コンバージョン率とフォールアウト率が右側に表示されます。

詳しくは、[フォールアウトレポート](../../analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347)を参照してください。

** [!UICONTROL Path Length] **: Shows how deep visitors browse into your site (both by percentage and by total count). つまり、このレポートはサイトの平均的な訪問者がサイトを出るまでに閲覧するページ数を示します。

** [!UICONTROL Page Analysis] **: Contains a subset of reports that let you analyze the following:

* ** [!UICONTROL Page Summary / Site Category Summary] **: Tells you everything you need to know about the page report. このレポートは、単一のページに関するページ特有の情報を収集してまとめ、1 つのレポートとして表示します。
* ** [!UICONTROL Reloads] **: Shows the number of times individual pages were reloaded by visitors.
* ** [!UICONTROL Time Spent on Page / Site Category] **: Displays the length of time that visitors browse individual pages in your site. 滞在時間は 10 のカテゴリ（15 秒未満、15 ～ 30 秒、30 ～ 60 秒、1 ～ 3 分、3 ～ 5 分、5 ～ 10 分、10 ～ 15 分、15 ～ 20 分、20 ～ 30 分、30 分超）に分類されます。
* ** [!UICONTROL Clicks to Page] **: Identifies the number of clicks visitors used to access each page in your site. ページの深さとは、そのページにアクセスするまでに閲覧したページをカウントしたページ数のことです。

** [!UICONTROL Entries &amp; Exits] **: The [!UICONTROL Entry Page] report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visitors. 表示される情報は以下のとおりです。

* ** [!UICONTROL Entry Pages] ** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visitor. このレポートは、最頻入口点である Web ページを特定したり、サイトの主な入口点を最適化したり、入口トラフィックを主要メッセージのあるページに導くために使用できます。
* ** [!UICONTROL Original Entry Pages] **: Shows the first page viewed for first-time visitors to your site. 各ユーザーは、各自が cookie を削除したり、cookie を使って追跡されていない場合を除き、一度しかカウントされません。
* ** [!UICONTROL Single Page Visits] **: Shows pages that are most often both the entry and exit pages for visitor browsing sessions.
* ** [!UICONTROL Exit Pages] **: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site.

## フォールアウトレポート {#concept_0ED452F3B1D04A19A59DD04D76D20347}

[!UICONTROL フォールアウトレポート]には、事前に指定した一連のページ内で、訪問者が離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。各ステップ間のコンバージョン率とフォールアウト率を示します。例えば、購入プロセス中の訪問者のフォールアウトポイントを追跡できます。開始点と終了点を選択し、中間点を追加して、Web サイトのナビゲーションパスを作成します。

<!-- 

c_reports_fallout.xml

 -->

フォールアウトデータは、訪問または訪問者のレベルで分析できます。また、指定した期間におけるフォールアウトのグラフを表示するトレンドパスも表示できます。単一のページまたは複数のページのグループをレポートのチェックポイントとして設定したり、あらゆる組み合わせや順番でディメンションや指標を追加することができます。また、Reports and Analytics で設定したカテゴリをこのレポートのチェックポイントとして使用することもできます。

このレポートでは、以下を分析できます。

* サイト上の特定のプロセス（購入や登録プロセスなど）を通してのコンバージョン率。
* 一般的でより広範囲なトラフィックフロー。ホームページを閲覧した訪問者のうち、検索を実行した訪問者の人数、その後特定の品目を閲覧した訪問者の人数などを表示できます。
* サイト上のイベント間の関連性。例えばプライバシーポリシーを閲覧した訪問者のうち製品の購入に到達した人の割合を示します。

## フォールアウトレポートの実行 {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

[!UICONTROL フォールアウトレポート]を実行する手順を説明します。

<!-- 

t_fallout.xml

 -->

1. **[!UICONTROL レポート]** / **[!UICONTROL 新規レポート]** / **[!UICONTROL フォールアウトをクリックします。]**

   Other Fallout reports are found in **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]**.

1. （オプション）特定のセグメントでデータをフィルターする場合、セグメントを「[!UICONTROL ここにセグメントをドロップ]」フィールドにドラッグします。
1. ディメンション項目を「[!UICONTROL ここにイベント項目またはディメンション項目をドロップ]」にドラッグします。
1. Click **[!UICONTROL Show Fallout At]**Visit or Visitor level, depending on whether you want to view fallout at the visit level, or across visitor sessions.
1. ページなどのディメンション項目をレポートに追加します。

## フォールアウトレポートへのページの割り当て {#task_B386289703494FA7B5A40FF9F97CB537}

ページをフォールアウトレポートに割り当てる手順を説明します。

<!-- 

t_fallout_assign_pages.xml

 -->

1. **[!UICONTROL レポート]** / **[!UICONTROL パス]** / **[!UICONTROL ページ]** / **[!UICONTROL ページフォールアウトをクリック]**&#x200B;します。
1. [!UICONTROL ディメンション]パネルで追加するページを探し、そのページを「[!UICONTROL ここにイベントまたはディメンションをドロップ]」フィールドにドラッグします。

## フォールアウトレポート - フィールドの説明 {#reference_74255CC8D6134F349FEBFEC72934C866}

[!UICONTROL フォールアウト]レポートのフィールドについて説明します。

<!-- 

r_dsc_fallout.xml

 -->

| フィールド | 説明 |
|--- |--- |
| 次の時点でのフォールアウトを表示（訪問または訪問者レベル） | 「訪問」と「訪問者」を切り替えて、訪問者のパスを分析できます。これらの設定により、訪問者のエンゲージメントを訪問全体にわたって訪問者レベルで分析できます。サイト分析レポート、フローレポートおよびフォールアウトレポートは、訪問者のパスに対して実行できます。この設定を変更するとレポートが再実行され、データが選択項目に制限されます。 |
| 成功の合計 | 成功の合計を示します。この値には、パスの最後のチェックポイントでの値が反映されます。 |
| 成功の合計 (%) | 各チェックポイントに到達した訪問者の割合の累計です。 |
| チェックポイント (%) | チェックポイント間の成功の割合です（累計ではありません）。 |
| すべての訪問を含める | すべての訪問を最初のチェックポイントとして追加します。 |
| フォールアウト | 指定したチェックポイントパスから訪問者が離脱した後に閲覧されたページを確認できます。 |
| フォールスルー | 指定したチェックポイントパスの次のステップで閲覧されたページを確認できます。 |
