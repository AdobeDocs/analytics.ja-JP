---
description: 訪問者が特定のページを閲覧した回数、特定ページから行われた購入数、来訪日時など、Web サイトについての量的な情報が表示されます。これらの各レポートはその他の項目ベースのレポートに設定できる指標です。
title: サイト指標レポート
topic: Ad hoc analysis
uuid: 0730747a-216f-4a58-b62b-a9812968cde5
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# サイト指標レポート

訪問者が特定のページを閲覧した回数、特定ページから行われた購入数、来訪日時など、Web サイトについての量的な情報が表示されます。これらの各レポートはその他の項目ベースのレポートに設定できる指標です。

## サイト指標レポート {#concept_0639CA16551749A693F49ADED4842CCE}

訪問者が特定のページを閲覧した回数、特定ページから行われた購入数、来訪日時など、Web サイトについての量的な情報が表示されます。これらの各レポートはその他の項目ベースのレポートに設定できる指標です。

指標レポートには経時的なトレンドが表示されます。これらのレポートに時間や曜日の精度を適用できます。サイトでの滞在時間、購入、売上などの指標を分析することもできます。

The following Site Metrics reports are available in the [!UICONTROL Site Metrics] menu.

## ページビュー数レポート {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

指定された期間（時間、日、週、月、四半期、年）に Web サイトのページが閲覧された回数を表示するトレンドレポートです。A [!UICONTROL Page View] is a request for a full page document, rather than an element of a page, such as an image or video. 例えば、1 名の訪問者が 1 回の訪問中に 15 ページ閲覧すると、15 ページビューとカウントされます。1 名の訪問者が 1 回の訪問中に同じページを 3 回閲覧すると、3 ページビューとカウントされます。このレポートでは、Web サイトのページの表示数と、サイト全体のページビュー合計数を計測できます。

## 訪問件数レポート {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

指定期間内の Web サイト全体への訪問件数を表示します。一連のページビューが 1 回の訪問となります。**&#x200B;訪問者がページを読み込むと訪問は開始となり、無操作状態が 30 分間続くとその訪問の終了となります。1 回の訪問は、その訪問者がタイムアウト前に少なくとも 1 ページを読み込む限り、数時間になることもあり得ます。1 回の訪問が 1 回のブラウザーセッションに一致するとは限りません。例えば、訪問者がブラウザーを閉じてから再度開き、5 分後にサイトにアクセスした場合、そのアクセスは同じ訪問の継続と見なされます。また、訪問者が 1 ページを 35 分間眺めていた場合、この訪問は閉じたものとして処理され、その後訪問者がクリックして別のページに移動した場合は、新しい訪問が開始されます。訪問は cookie によって追跡されます。1 回の訪問で継続的な操作が 12 時間続いた場合は、この訪問が終了されます。

<!-- 

c_reports_visits.xml

 -->

In marketing reports and analytics, you can run a [!UICONTROL Visits Report] on a selected page. ad hoc analysis では、データをセグメント化し、特定のページを表示できます。

## 実訪問者数レポート {#concept_39097C54E46C496CBAD537329DB3C84A}

サイトにアクセスした個別訪問者数を示すトレンドレポートです。各訪問者は、Web サイトの訪問回数に関係なく 1 回だけカウントされます。アドビでは、cookie ハンドシェイクテクノロジーを使用して個別訪問者と再来訪者を区別します。cookie ハンドシェイクは、インターネットブラウザーの cookie テクノロジーの限界を克服したものです。

<!-- 

c_reports_unique_visitors.xml

 -->

このレポートは次の目的に使用できます。

* 指定期間中に Web サイトを閲覧した個別の訪問者数を確認する。
* 最近のトラフィックパターンを表示し、プロモーションがサイトの個別訪問者数にどのように影響しているかを確認する。
* 個別訪問者数とページビュー数とを比較する。

## 訪問者数レポート {#concept_7371DAB5DA474D03A2D1448F151E011B}

選択した時間、日、週、月、四半期、年におけるサイトへの実訪問者数が表示されます。個別訪問者は選択した期間中 1 度しかカウントされません。サイトに戻った訪問者は、その期間が過ぎるまで個別訪問者としてカウントされません。

<!-- 

c_reports_visitors.xml

 -->

表の一番下に表示される合計値は指定期間内の合計訪問件数であり、必ずしも実訪問者数を表しているとは限りません。For example, if you run a [!UICONTROL Daily Unique Visitors Report] with a time frame of several days, the total can include repeat visitors, because the same visitor might return on the next day and be counted again. However, if you run a [!UICONTROL Monthly Unique Visitors Report], the value in the Totals column accurately reflects how many unique visitors came during the month.

## 訪問別滞在時間レポート {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

各訪問において訪問者がサイトの閲覧に費やした時間を表示します。これとは別に「サイトでの平均滞在時間」の指標もあり、これは訪問者がサイトの閲覧に費やした平均時間を表します。

<!-- 

c_reports_time_spent_per_visit.xml

 -->

このレポートを使用すると、次のことができます。

* 訪問者のサイト滞在時間の長さを特定します。
* 訪問者の関心を引くコンテンツやプロモーションを特定します。
* アクセス数は多いのに訪問者がすぐ離脱してしまう理由を明らかにします。

## 購入レポート {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

売上高、注文件数および購入点数のサマリデータを表示します。また、[!DNL Purchase Conversion Funnel] レポートを表示することもできます。

<!-- 

c_reports_purchases.xml

 -->

* **売上高**：選択した期間の粗利益を見ることができます。例としては、3 月の売上高、先週の購入、本日の売上高などがあります。
* **注文件数**：指定された期間における Web サイトでの注文件数を表示します。注文には複数の製品が含まれることがあります。
* **購入点数**：指定された期間に注文された総数量が表示されます。
* **購入コンバージョンファネル**：小売設定のように、特定の順序で発生する場合のサイトのコンバージョンイベントの表示に最適です。ファネルレポートには、コンバージョンプロセスの各手順のコンバージョン指標のほか、注文件数、売上高、購入点数が表示されます。

## 買い物かごレポート {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

指定された期間内に開かれた買い物かごの数が表示されます。レポートを実行して買い物かご表示、追加、削除、チェックアウト数を分析できます。買い物かごは通常、顧客が購入する品目を選択したときに開きますが、品目なしでも開くことができます。

<!-- 

c_reports_shopping_cart.xml

 -->

を使用して、次のことがで [!UICONTROL Carts Report] きます。

* サイトで開かれた買い物かご数のパターン、ピーク、ボトムなどを判断します。
* 特定期間を詳しく調査して、買い物かごを開くことにつながった指標についての詳細を調べます。

## カスタムイベントレポート {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

サイト上で訪問者がおこなうことが望まれるコンバージョンアクションを表示します。このようなアクションには、登録、購読、リードフォーム記入の完了、チャットの開始、購入、予約、調査の完了などがあります。

<!-- 

c_reports_custom_events.xml

 -->

Analytics のレポートスイートはそれぞれが異なるので、このレポート群の使用法も各 Analytics クライアントによって異なります。A [!UICONTROL Custom Event] report can be used as a counter that shows the number of times an event occurs. For example, if **[!UICONTROL event1]** is set to count the number of times a document is downloaded, then the [!UICONTROL Custom Event] report for Event 1 shows the total number of times the event (or download) occurs. 複数のカスタムイベントレポートを持つことができます。

## コンバージョンレポート {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Web サイトの様々な側面から得た売上を表示します。広告キャンペーンから得た売上、常連客から得た売上と新規顧客から得た売上の比較、製品別の売上内訳など、様々な形式の売上レポートを見ることができます。コンバージョンレポートには、広告クリック数やダウンロード数など、他の成功イベントも表示できます。

<!-- 

c_reports_conversion.xml

 -->

コンバージョンレポートには、次のような、すべての重要な顧客アクティビティに関するリアルタイムの統計情報が含まれています。

* 顧客の購入パターン
* 買い物かごの指標（フォールアウトを含む）
* 顧客のコンバージョン率（訪問者が顧客となる率）
* 宣伝効果とチャネルパートナーの効果
* オンラインおよびオフラインのマーケティングキャンペーンのパフォーマンス
* 顧客忠誠度指標
* 販売サイクルのインサイト

## マーケティングチャネルレポート {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

マーケティングチャネルレポートには、ファーストタッチチャネルおよびラストタッチチャネルの配分が、売上高、注文件数、コストなど重要な標準指標と共に表示され、各チャネルが生み出す売上高を調べることができます。チャネル定義ルールは [!DNL Admin Console] で設定し、チャネルレポート固有の API を利用できます。

<!-- 

c_reports_marketing_channel.xml

 -->

**[!UICONTROL First or Last Touch Channel Report]**:特定のファーストタッチまたはラストタッチのデータを示す指標をチャネルします。 これらのレポートでは、チャネルを分類し、各チャネルの詳細を表示できます。AdLens が有効になっている場合は、Reports and Analytics チャネルレポートに分類が表示されます。

**[!UICONTROL First or Last Touch Channel Detail Reports]**:ルールの設定時にオプションで設定したチャネル値から取得される、ページ名や転送者などの詳細 [!UICONTROL Set the channel's value to] が表示されます。 チャネル詳細レポートでは、概要レポートで報告されたチャネルの詳細値を詳しく調査できます。

Reports &amp; Analytics でマーケティングチャネルを設定する方法について詳しくは、[マーケティングチャネルのヘルプ](/help/components/c-marketing-channels/analyze-mc.md)システムを参照してください。
