---
title: レポート
description: 各レポートで Reports & Analytics が使用するディメンションと指標。
feature: Reports & Analytics Basics & Analytics Basics
role: Business Practitioner, Administrator
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 99%

---

# レポート

Reports &amp; Analytics の各レポートは、専用のディメンションとデフォルトの指標を使用します。必要に応じて、各レポートの指標を変更し、分類を追加できます。次のリストは、各レポートで使用されるディメンションを示します。

>[!NOTE]
>
>組織の管理者が行ったカスタマイズに応じて、レポートメニューの外観が変わります。詳しくは、『管理者ユーザーガイド』の「[メニューのカスタマイズ](/help/admin/admin/customize-menus.md)」を参照してください。

## サイト指標

通常、日付範囲を使用したトレンドを示すレポートが含まれます。また、推奨レポートやリアルタイムレポートなどの個別レポートも含まれます。

* 推奨レポート：すぐに洞察を得るための複数の小型レポートを含むダッシュボードを作成します。
* 主要指標：一度に 5 つまでの指標のトレンドを表示できるレポート。トレンド[ページビュー](/help/components/metrics/page-views.md)、[訪問](/help/components/metrics/visits.md)、[ユニーク訪問者](/help/components/metrics/unique-visitors.md)（デフォルト）。
* ページビュー：[Page views](/help/components/metrics/page-views.md) 指標の経時的な推移を示します。
* 訪問：[Visits](/help/components/metrics/visits.md) 指標の経時的な推移を示します。
* 訪問者：様々な[ユニーク訪問者](/help/components/metrics/unique-visitors.md)指標の経時的な推移を示します。
   * ユニーク訪問者：選択した日付範囲全体で訪問者を 1 回だけカウントします。
   * 時間別ユニーク訪問者：選択した日付範囲の異なる時間に訪問者が訪問した場合に複数回カウントします。
   * 日別ユニーク訪問者：選択した日付範囲の異なる日に訪問者が訪問した場合に複数回カウントします。
   * 週別ユニーク訪問者：選択した日付範囲の異なる週に訪問者が訪問した場合に複数回カウントします。
   * 月別ユニーク訪問者：選択した日付範囲の異なる月に訪問者が訪問した場合に複数回カウントします。
   * 四半期別ユニーク訪問者：選択した日付範囲の異なる四半期に訪問者が訪問した場合に複数回カウントします。四半期は、1 月から 3 月、4 月から 6 月、7 月から 9 月、10 月から 12 月です。
   * 年別ユニーク訪問者：選択した日付範囲の異なる年に訪問者が訪問した場合に複数回カウントします。
* 訪問別滞在時間：[訪問別滞在時間 — グループ](/help/components/dimensions/time-spent-per-visit.md)ディメンションを使用します。
* イベント前の時間：「[イベント前の](/help/components/dimensions/time-prior-to-event.md)時間」ディメンションを使用します。
* 購入：購入ベースの指標に関するレポートが含まれます。
   * 購入コンバージョンファネル：ファネルレポートで[訪問](/help/components/metrics/visits.md)、[買い物かご](/help/components/metrics/carts.md)、[注文](/help/components/metrics/orders.md)、[売上高](/help/components/metrics/revenue.md)、[単位](/help/components/metrics/units.md)をレポートします。Analysis Workspace でも、[フォールアウトビジュアライゼーション](../analysis-workspace/visualizations/fallout/fallout-flow.md)を使用して同様のビジュアライゼーションを実現できます。
   * 売上高：指標の[売上高](/help/components/metrics/revenue.md)の経時的な傾向。
   * 注文件数：[Orders](/help/components/metrics/orders.md) 指標の経時的な推移を示します。
   * 数量：[Units](/help/components/metrics/units.md) 指標の経時的な推移を示します。
* 買い物かご：買い物かご指標に関するレポートが含まれます。
   * 買い物かごコンバージョンファネル：ファネルレポートで[インスタンス](/help/components/metrics/instances.md)、[買い物かご](/help/components/metrics/carts.md)、[チェックアウト](/help/components/metrics/checkouts.md)、[注文](/help/components/metrics/orders.md)、[売上高](/help/components/metrics/revenue.md)をレポートします。
   * 買い物かご：[Carts](/help/components/metrics/carts.md) 指標の経時的な推移を示します。
   * 買い物かごビュー：[Cart views](/help/components/metrics/cart-views.md) 指標の経時的な推移を示します。
   * 買い物かごへの追加：[Cart additions](/help/components/metrics/cart-additions.md) 指標の経時的な推移を示します。
   * 買い物かごからの削除：[Cart removals](/help/components/metrics/cart-removals.md) 指標の経時的な推移を示します。
   * チェックアウト：[Checkouts](/help/components/metrics/checkouts.md) 指標の経時的な推移を示します。
* カスタムイベント：お客様の実装に固有のカスタム[イベント](/help/components/metrics/custom-events.md)に関するすべてのレポートが含まれます。
* ボット：ボット関連のレポートを表示します。
   * ボット：サイトを最も頻繁に訪問するボットを表示します。詳しくは、『管理者ユーザーガイド』の「[ボットルール](../../admin/admin/bot-removal/bot-rules.md)」を参照してください。
   * ボットページ：ボットが頻繁に訪問したページを表示します。
* リアルタイム：データ収集後、特定のディメンションおよび指標を数秒以内に表示します。詳しくは、「[リアルタイムレポート](/help/components/c-real-time-reporting/realtime.md)」を参照してください。

## サイトコンテンツ

通常、サイトのコンテンツを表示するディメンションに関するレポートが含まれます。これらのレポートの一部に分類を適用できます。分類を適用すると、レポートがソースレポートと分類レポートを含むメニューになります。

* ページ：[Page](/help/components/dimensions/page.md) ディメンションを使用します。
* サイトセクション：[Site section](/help/components/dimensions/site-section.md) ディメンションを使用します。
* サーバー：[Server](/help/components/dimensions/server.md) ディメンションを使用します。
* リンク：リンクトラッキングを使用するレポートが含まれます。
   * 離脱リンク：離脱リンク [Exit link](/help/components/dimensions/exit-link.md) ディメンションを使用します。
   * ファイルのダウンロード：[Download link](/help/components/dimensions/download-link.md) ディメンションを使用します。
   * カスタムリンク：[Custom link](/help/components/dimensions/custom-link.md) ディメンションを使用します。
   * エラーページ：エラー [Pages not found](/help/components/dimensions/pages-not-found.md) ディメンションを使用します。

## モバイル

レガシーモバイルレポートに関するレポートが含まれます。これらのレポートは、ユーザーエージェント文字列に基づいてデータを作成します。各レポートで様々な[モバイル（mobile）ディメンション](/help/components/dimensions/mobile-dimensions.md)を使用します。

* デバイス：[Mobile device](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* デバイスの種類：[Mobile device type](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 製造元：[Mobile manufacturer](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 画面サイズ：[Mobile screen size](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 画面の高さ：[Mobile screen height](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 画面の幅：[Mobile screen width](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* Cookie のサポート：[Mobile cookie support](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 画像サポート：[Mobile image support](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 画面の色：[Mobile color depth](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* オーディオサポート：[Mobile audio support](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* ビデオサポート：[Mobile video support](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* オペレーティングシステム（非推奨）：[Mobile operating system（非推奨）](/help/components/dimensions/mobile-dimensions.md)ディメンションを使用します。

## パス

訪問者のパスデータを表示できるレポートが含まれます。

* 次ページのフロー：トップページのディメンション項目に関するフローレポートを使用します。パスビューは[インスタンス](/help/components/metrics/instances.md)に似ています。レポートされたディメンション項目は変更できます。Analysis Workspace の[フローのビジュアライゼーション](../analysis-workspace/visualizations/c-flow/flow.md)を使用すると、同様のレポートを利用できます。
* 次のページ：トップページのディメンション項目を取得し、訪問者が次に閲覧したページを示します。
* 前ページのフロー：トップページのディメンション項目に関するフローレポートを使用します。Analysis Workspace の[フロービジュアライゼーション](../analysis-workspace/visualizations/c-flow/flow.md)を使用すると、同様のレポートを利用できます。
* 前のページ：トップページのディメンション項目を取得し、訪問者が前に閲覧したページを示します。
* フォールアウト：ページディメンションの項目をステップ単位で選択でき、そのパスをたどった訪問者とたどらなかった訪問者の割合が表示されます。Analysis Workspace の[フォールアウトビジュアライゼーション](../analysis-workspace/visualizations/fallout/fallout-flow.md)を使用すると、同様のレポートを利用できます。
* フルパス：個々のパスをディメンション項目として表示します。Analysis Workspace では廃止しました。代わりに、 [フロービジュアライゼーション](../analysis-workspace/visualizations/c-flow/flow.md)を使用できます。
* パスファインダ：パスを分析できる複数のタイプのレポートを提供します（Analysis Workspace では廃止）。
* パスの長さ：訪問の深さ [Visit depth](/help/components/dimensions/visit-depth.md) ディメンションを使用します。
* ページ分析
   * ページ概要：トップページのディメンション項目を使用し、トレンドを表示します。また、そのトップページのディメンション項目の入口、前のページ、出口、次のページも表示します。
   * リロード回数：[Page](/help/components/dimensions/page.md) ディメンションと [Reloads](/help/components/metrics/reloads.md) 指標を使用します。
   * ページでの滞在時間：[Time spent on page - bucketed](/help/components/dimensions/time-spent-on-page.md) ディメンションを使用します。
   * ページへのクリック数：トップページのディメンション項目を使用し、特定の訪問でそのページに到達するのに費やしたクリック数を示します。
* 入口と出口
   * 入口ページ：[Entry pages](/help/components/dimensions/entry-dimensions.md) ディメンションを使用します。
   * オリジナルの入口ページ：[Entry page original](/help/components/dimensions/entry-dimensions.md) ディメンションを使用します。
   * 直帰数：アドビが提供する「単一ページ訪問」セグメントを適用した [Page](/help/components/dimensions/page.md) ディメンションを使用します。
   * 出口ページ：[Exit pages](/help/components/dimensions/exit-dimensions.md) ディメンションを使用します。

>[!NOTE]
>
>このフォルダーには、他のレポートも表示できます。これらは prop などの他のディメンションで、レポートスイートの設定で[パスを有効にしています](../../admin/admin/c-traffic-variables/traffic-var.md)。

## トラフィックソース

訪問者がサイトに到着する前にどこから来たかを知ることができるレポートが含まれます。これらのレポートは、レポートスイートの設定で[内部 URL フィルター](../../admin/admin/internal-url-filter-admin.md)を正しく設定しない限り、機能しません 。

* 検索キーワード — すべて：[Search keyword](/help/components/dimensions/search-keyword.md) ディメンションを使用します。
* 検索キーワード — 有料：[Search keyword - paid](/help/components/dimensions/search-keyword.md) ディメンションを使用します。
* 検索キーワード — 自然：[Search keyword - natural](/help/components/dimensions/search-keyword.md) ディメンションを使用します。
* 検索エンジン — すべて：[Search engine](/help/components/dimensions/search-engine.md) ディメンションを使用します。
* 検索エンジン — 有料：検 [Search engine - paid](/help/components/dimensions/search-engine.md) ディメンションを使用します。
* 検索エンジン — 自然：[Search engine - natural](/help/components/dimensions/search-engine.md) ディメンションを使用します。
* すべての検索ページのランク：[All search page rank](/help/components/dimensions/all-search-page-rank.md) ディメンションを使用します。
* 参照ドメイン：[Referring domain](/help/components/dimensions/referring-domain.md) ディメンションを使用します。
* オリジナルの参照ドメイン：[Original referring domain](/help/components/dimensions/original-referring-domain.md) ディメンションを使用します。
* 転送者：[Referrer](/help/components/dimensions/referrer.md) ディメンションを使用します。
* 転送者タイプ：[Referrer type](/help/components/dimensions/referrer-type.md) ディメンションを使用します。

## キャンペーン

主に [Tracking code（追跡コード）](/help/components/dimensions/tracking-code.md) ディメンションに関するレポートが含まれます。

* キャンペーンコンバージョンファネル：ファネルレポートでクリックスルー、[チェックアウト](/help/components/metrics/checkouts.md)、[注文](/help/components/metrics/orders.md)、[売上高](/help/components/metrics/revenue.md)をレポートします。クリックスルー指標は、[Tracking code](/help/components/dimensions/tracking-code.md) ディメンションに関連する[インスタンス](/help/components/metrics/instances.md)指標に似ています。Analysis Workspace でも、[フォールアウトビジュアライゼーション](../analysis-workspace/visualizations/fallout/fallout-flow.md)を使用して同様のビジュアライゼーションを実現できます。
* トラッキングコード：[Tracking code](/help/components/dimensions/tracking-code.md) ディメンションを使用します。

## 製品

主に [Product](/help/components/dimensions/product.md) ディメンションに関するレポートが含まれます。

* 製品コンバージョンファネル：ファネルレポートで[製品ビュー](/help/components/metrics/product-views.md)、[買い物かごへの追加](/help/components/metrics/cart-additions.md)、[チェックアウト](/help/components/metrics/checkouts.md)、[注文](/help/components/metrics/orders.md)、[単位](/help/components/metrics/units.md)、[売上高](/help/components/metrics/revenue.md)をレポートします。Analysis Workspace でも、[フォールアウトビジュアライゼーション](../analysis-workspace/visualizations/fallout/fallout-flow.md)を使用して同様のビジュアライゼーションを実現できます。
* 製品：[Products](/help/components/dimensions/product.md) ディメンションを使用します。
* クロス販売：共に販売される製品を表示します（Analysis Workspace では廃止）。
* カテゴリ：[Category](/help/components/dimensions/category.md) ディメンションを使用します。

## 訪問者保持率

サイトに戻る訪問者に関するレポートが含まれます。

* 再来訪頻度：[Return frequency](/help/components/dimensions/return-frequency.md) ディメンションを使用します。
* 再来訪：アドビが提供する「再来訪」セグメントを適用した、[Visits](/help/components/metrics/visits.md) 指標の経時的な推移を示します。
* 訪問数：[Visit number ](/help/components/dimensions/visit-number.md)ディメンションを使用します。
* 販売サイクル：購入関連レポートのフォルダー。
   * 顧客の忠誠度：[Customer loyalty](/help/components/dimensions/customer-loyalty.md) ディメンションを使用します。
   * 初回購入までの日数：[Days before first purchase](/help/components/dimensions/days-before-first-purchase.md) ディメンションを使用します。
   * 前回購入からの日数：[Days since last purchase](/help/components/dimensions/days-since-last-purchase.md) ディメンションを使用します。
   * 日別ユニーク顧客：アドビが提供する「購入者」セグメントが適用された[日別ユニーク顧客](/help/components/metrics/unique-visitors.md)の経時的な推移を示します。
   * 週別ユニーク顧客：アドビが提供する「購入者」セグメントを適用した[週別ユニーク顧客](/help/components/metrics/unique-visitors.md)指標の経時的な推移を示します。
   * 月別ユニーク顧客：アドビが提供する「購入者」セグメントを適用した[月別ユニーク顧客](/help/components/metrics/unique-visitors.md)指標の経時的な推移を示します。
   * 四半期別ユニーク顧客：アドビが提供する「購入者」セグメントを適用した[四半期別ユニーク顧客](/help/components/metrics/unique-visitors.md)指標の経時的な推移を示します。四半期は、1 月から 3 月、4 月から 6 月、7 月から 9 月、10 月から 12 月です。
   * 年別ユニーク顧客：アドビが提供する「購入者」セグメントを適用した[年別ユニーク訪問者](/help/components/metrics/unique-visitors.md)指標の経時的な推移を示します。

## 訪問者プロファイル

サイトの訪問者に関するレポートが含まれます。

* 地理特性：世界中のサイト訪問者がどこから来訪したかに関するレポートです。
   * 国：[Countries](/help/components/dimensions/countries.md) ディメンションを使用します。
   * 地域：[Regions](/help/components/dimensions/regions.md) ディメンションを使用します。
   * 市区町村：[Cities](/help/components/dimensions/cities.md) ディメンションを使用します。
   * 米国の州：[US states](/help/components/dimensions/us-states.md) ディメンションを使用します。
   * 米国 DMA：[US DMA](/help/components/dimensions/us-dma.md) ディメンションを使用します。
* 言語：[Language](/help/components/dimensions/language.md) ディメンションを使用します。
* タイムゾーン：time zone ディメンションを使用します（Analysis Workspace では廃止）。ディメンション項目は、ヒットの GMT オフセットです。
* ドメイン：[Domain](/help/components/dimensions/domain.md) ディメンションを使用します。
* トップレベルドメイン：トップレベルのドメインディメンションを使用します（Analysis Workspace では廃止）。このレポートは、[domains](/help/components/dimensions/domain.md) ディメンションを上位レベルのカテゴリ（通常、ドメインの国別）にグループ化します。
* 技術：訪問者がサイトにアクセスする際に使用したレポートを含むフォルダー。
   * ブラウザー：[Browsers](/help/components/dimensions/browser.md) ディメンションを使用します。
   * ブラウザータイプ：[Browser type](/help/components/dimensions/browser-type.md) ディメンションを使用します。
   * ブラウザーの幅：[Browser width - bucketed](/help/components/dimensions/browser-width.md) ディメンションを使用します。
   * ブラウザーの高さ：[Browser height - bucketed](/help/components/dimensions/browser-height.md) ディメンションを使用します。
   * オペレーティングシステム：[Operating systems](/help/components/dimensions/operating-systems.md) ディメンションを使用します。
   * オペレーティングシステムタイプ：[Operating system types](/help/components/dimensions/operating-system-types.md) ディメンションを使用します。
   * 画面の色：[Color depth](/help/components/dimensions/color-depth.md) ディメンションを使用します。
   * 画面の解像度：[Monitor resolution](/help/components/dimensions/monitor-resolution.md) ディメンションを使用します。
   * Java：[Java enabled](/help/components/dimensions/java-enabled.md) ディメンションを使用します。
   * JavaScript：JavaScript enabled ディメンションを使用します（Analysis Workspace では廃止）。ブラウザーで JavaScript が有効になっているかどうかに応じて、ディメンション項目は「有効」、「無効」または「不明」です。
   * JavaScript のバージョン：JavaScript version ディメンションを使用します（Analysis Workspace では廃止）。ディメンション項目は、ブラウザーが使用する JavaScript のバージョンを示します。
   * Cookie：[Cookie support](/help/components/dimensions/cookie-support.md) ディメンションを使用します。
   * 接続タイプ：[Connection type](/help/components/dimensions/connection-type.md) ディメンションを使用します。
   * 携帯電話会社：[Mobile carrier](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* 訪問者の状態：State ディメンションを使用します（Analysis Workspace では廃止）。ディメンション項目は [`state`](../../implement/vars/page-vars/state.md) 変数から始まります。
* 訪問者の郵便番号：[Zip code](/help/components/dimensions/zip-code.md) ディメンションを使用します。

## カスタムコンバージョン

実装に固有のレポートが含まれます。カスタムコンバージョンレポートでは、[eVar](/help/components/dimensions/evar.md) をディメンションとして使用します。

## カスタムトラフィック

実装に固有のレポートが含まれます。カスタムトラフィックレポートでは、[prop](/help/components/dimensions/prop.md) をディメンションとして使用します。

## マーケティングチャネル

[マーケティングチャネル](/help/components/c-marketing-channels/c-getting-started-mchannel.md)に関するレポートが含まれます。

* チャネルの概要レポート：Reports &amp; Analytics に固有のカスタムレポート。ファーストタッチまたはラストタッチのアトリビューションを使用する指標と共に、ディメンション項目としてマーケティングチャネルを使用します。
* ファーストタッチチャネル：[First touch channel](/help/components/dimensions/first-touch-channel.md) ディメンションを使用します。
* ファーストタッチチャネルの詳細：[First touch channel detail](/help/components/dimensions/first-touch-detail.md) ディメンションを使用します。
* ラストタッチチャネル：[Last touch channel](/help/components/dimensions/last-touch-channel.md) ディメンションを使用します。
* ラストタッチチャネルの詳細：[Last touch channel detail](/help/components/dimensions/last-touch-detail.md) ディメンションを使用します。

## ブックマーク

ブックマークを付けたレポートが含まれます。詳しくは、「[ブックマーク](bookmarks.md)」を参照してください。

## ダッシュボード

作成したダッシュボードが含まれます。詳しくは、「[ダッシュボード](dashboard.md)」を参照してください。

## ターゲット

作成したターゲットが含まれます。詳しくは、「[ターゲット](targets.md)」を参照してください。

>[!NOTE]
>
>このヘルプページでレポートが見つからない場合は、管理者がフォルダーの名前を変更したり、調整したりした可能性があります。詳しくは、『管理者ユーザーガイド』の「[メニューのカスタマイズ](/help/admin/admin/customize-menus.md)」を参照してください。
