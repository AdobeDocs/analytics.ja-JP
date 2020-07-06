---
title: レポート
description: 各レポートでReports &Analyticsが使用するディメンションと指標。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 1%

---


# レポート

Reports &amp;Analyticsの各レポートは、専用のディメンションとデフォルトの指標を使用します。 必要に応じて、各レポートの指標を変更し、分類を追加できます。 次のリストは、各レポートで使用されるディメンションを示します。

>[!NOTE]
>
>組織の管理者が行ったカスタマイズに応じて、レポートメニューの外観が変わります。 See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## サイト指標

通常、日付範囲を使用したトレンドを示すレポートが含まれます。 また、推奨レポートやリアルタイムレポートなどの個別レポートも含まれます。

* 推奨レポート： すぐにインサイトを得るための複数のレポートレットを含むダッシュボードを作成します。
* 主要指標： 一度に5つまでの指標のトレンドを表示できるレポート。 トレンド [ページの表示](/help/components/metrics/page-views.md)、 [訪問](/help/components/metrics/visits.md)、 [実訪問者](/help/components/metrics/unique-visitors.md) （デフォルト）。
* ページ表示: 経時的な [ページ表示](/help/components/metrics/page-views.md) 指標のトレンドを示します。
* 訪問回数： 経時的な [訪問回数](/help/components/metrics/visits.md) 指標のトレンドを示します。
* 訪問者: 様々な [個別訪問者](/help/components/metrics/unique-visitors.md) 指標の経時的なトレンドを示します。
   * 個別訪問者数： 選択した日付範囲全体で訪問者を1回だけカウントします。
   * 時間別訪問者数： 選択した日付範囲の異なる時間に訪問者が訪問した場合に複数回カウントします。
   * 日別訪問者数： 選択した日付範囲の異なる日に訪問した訪問者を複数回カウントします。
   * 週別訪問者数： 選択した日付範囲の別の週に訪問した訪問者を複数回カウントします。
   * 月別訪問者数： 選択した日付範囲の異なる月に訪問者が訪問した場合に複数回カウントします。
   * 四半期別訪問者数： 選択した日付範囲の異なる四半期に訪問した訪問者を複数回カウントします。 四半期は、1月から3月、4月から6月、7月から9月、10月から12月です。
   * 年別訪問者数： 選択した日付範囲の異なるカレンダー年間に訪問者が訪問した場合に複数回カウントします。
* 訪問別滞在時間： 訪問別滞在 [時間 — グループディメンションを使用し](/help/components/dimensions/time-spent-per-visit.md) ます。
* イベント前の時間： 「 [イベント前の](/help/components/dimensions/time-prior-to-event.md) 時間」ディメンションを使用します。
* 購入： 購入ベースの指標に関するレポートが含まれます。
   * 購入コンバージョンファネル： 訪問 [件数](/help/components/metrics/visits.md)、買い物かご件数 [、](/help/components/metrics/carts.md)注文件数 [、](/help/components/metrics/orders.md)売上高、 [](/help/components/metrics/revenue.md)[](/help/components/metrics/units.md) 売上高、ファネルレポート内の購入点数に関するレポートを作成します。 フォールアウトビジュアライゼーションを使用したAnalysis Workspaceでも、同様のビジュアライ [ゼーションを実現でき](../analysis-workspace/visualizations/fallout/fallout-flow.md)ます。
   * 売上高： 指標の [売上高の経時的な傾向](/help/components/metrics/revenue.md) 。
   * 注文件数： 指標の [注文の経時的なトレンド](/help/components/metrics/orders.md) 。
   * 数量： 指標の [単位数](/help/components/metrics/units.md) （単位数）の経時的なトレンドを示します。
* 買い物かご： 買い物かご指標に関するレポートが含まれます。
   * 買い物かごコンバージョンファネル： レポート [・](/help/components/metrics/instances.md)インスタンス [、](/help/components/metrics/carts.md)買い物かご [、チェックアウト注文件数、](/help/components/metrics/checkouts.md)注文件数、および売上高ファネル・レポート内の売上高 [](/help/components/metrics/orders.md)[](/help/components/metrics/revenue.md) の各レポート
   * 買い物かご： 指標の [買い物かごの経時的なトレンド](/help/components/metrics/carts.md) 。
   * 買い物かご表示: 指標 [買い物かご表示の経時的なトレンド](/help/components/metrics/cart-views.md) 。
   * 買い物かごへの追加： 経時的に指標 [買い物かごへの追加のトレンドを示します](/help/components/metrics/cart-additions.md) 。
   * 買い物かごからの削除： 指標 [買い物かごからの削除の傾向を経時的に示します](/help/components/metrics/cart-removals.md) 。
   * チェックアウト： 指標の [チェックアウトの経時的な傾向](/help/components/metrics/checkouts.md) 。
* カスタムイベント: お客様の実装に固有のカスタム [イベントに関するすべてのレポートが含まれ](/help/components/metrics/custom-events.md) ます。
* ボット： ボット関連のレポートを表示します。
   * ボット： サイトで最も頻繁に訪問するボットを表示します。 See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
   * ボットページ： ボットが最もヒットしたページを表示します。
* リアルタイム： データ収集後、特定のディメンションおよび指標を数秒以内で表示します。 See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## サイトコンテンツ

通常、サイトのコンテンツを表示するディメンションに関するレポートが含まれます。 分類は、これらのレポートの一部に適用できます。 分類を適用すると、レポートがソースレポートと分類レポートを含むメニューになります。

* ページ： [Page](/help/components/dimensions/page.md) （ページ）ディメンションを使用します。
* サイトセクション： [Site section](/help/components/dimensions/site-section.md) （サイトセクション）ディメンションを使用します。
* サーバー： [Server](/help/components/dimensions/server.md) ディメンションを使用します。
* リンク： リンクトラッキングを使用するレポートが含まれます。
   * 離脱リンク： 離脱リンク [ディメンションを使用し](/help/components/dimensions/exit-link.md) ます。
   * ファイルのダウンロード数： ダウンロード [リンク](/help/components/dimensions/download-link.md) ディメンションを使用します。
   * カスタムリンク： カス [タムリンク](/help/components/dimensions/custom-link.md) ディメンションを使用します。
   * エラーページ： エラー [ページ(404)ディメンションを使用します](/help/components/dimensions/pages-not-found.md) 。

## モバイル

レガシーモバイルレポートに関するレポートが含まれます。 これらのレポートは、ユーザーエージェント文字列に基づいてデータを作成します。 各レポートで様々な [モバイルディメンション](/help/components/dimensions/mobile-dimensions.md) を使用します。

* デバイス： モ [バイルデバイス](/help/components/dimensions/mobile-dimensions.md) (Mobile device)ディメンションを使用します。
* デバイスの種類： モ [バイルデバイスタイプ](/help/components/dimensions/mobile-dimensions.md) (Mobile device type)ディメンションを使用します。
* 製造元： モ [バイル製造元](/help/components/dimensions/mobile-dimensions.md) (Mobile Manufacturer)ディメンションを使用します。
* 画面サイズ： モ [バイルの画面サイズ](/help/components/dimensions/mobile-dimensions.md) 。
* 画面の高さ： モ [バイルの画面の高さ](/help/components/dimensions/mobile-dimensions.md) 。
* 画面の幅： モ [バイルの画面の幅](/help/components/dimensions/mobile-dimensions.md) 。
* cookieのサポート： モ [バイルcookieサポートディメンションを使用します](/help/components/dimensions/mobile-dimensions.md) 。
* 画像サポート： モ [バイル画像サポートのサイズ](/help/components/dimensions/mobile-dimensions.md) 。
* 画面の色： モ [バイルの画面の色](/help/components/dimensions/mobile-dimensions.md) 。
* オーディオサポート： モ [バイルオーディオサポート](/help/components/dimensions/mobile-dimensions.md) (Mobile audio support)ディメンションを使用します。
* ビデオサポート： モ [バイルビデオサポート](/help/components/dimensions/mobile-dimensions.md) ディメンションを使用します。
* オペレーティングシステム（非推奨）: [Mobileオペレーティングシステム（非推奨）ディメンションを使用し](/help/components/dimensions/mobile-dimensions.md) ます。

## パス

訪問者のパスデータを表示できるレポートが含まれます。

* 次ページのフロー： トップページのディメンション値に関するフローレポートを使用します。 パス表示ーは [インスタンスに似ています](/help/components/metrics/instances.md)。 レポートされたディメンション値は変更できます。 フ [ローのビジュアライゼーションを使用して、同様のAnalysis Workspaceのレポートを利用できます](../analysis-workspace/visualizations/c-flow/flow.md)。
* 次のページ： 最上位のページディメンションの値を取り、訪問者が次に閲覧したページを示します。
* 前ページのフロー： トップページのディメンション値に関するフローレポートを使用します。 [フロービジュアライゼーションを使用して、Analysis Workspaceの類似したレポートを利用できます](../analysis-workspace/visualizations/c-flow/flow.md)。
* 前のページ： 最上位のページディメンション値を取得し、前のページ訪問者の元を示します。
* フォールアウト： ページディメンションの値をステップ単位で選択でき、そのパスをたどった訪問者とたどらなかった訪問者の割合が表示されます。 フォールアウトビジュアライゼーションを使用しても、同様のAnalysis Workspaceの [レポートを利用でき](../analysis-workspace/visualizations/fallout/fallout-flow.md)ます。
* フルパス： 個々のパスをディメンション値として表示します。 Analysis Workspaceに引退。 代わりに、 [フロービジュアライゼーションを使用し](../analysis-workspace/visualizations/c-flow/flow.md) ます。
* パスファインダ： パスを分析(Analysis Workspaceで廃止)できる複数のタイプのレポートを提供します。
* パスの長さ： 訪問の深さ [ディメンションを使用し](/help/components/dimensions/visit-depth.md) ます。
* ページ分析
   * ページサマリ： 上位のページディメンション値を使用し、トレンド表示を表示します。 また、そのトップページのディメンション値の入口ポイント、前のページ、出口ポイントおよび次のページも表示します。
   * リロード回数： [Page](/help/components/dimensions/page.md) ( [ページ](/help/components/metrics/reloads.md) )ディメンションをリロード回数指標と共に使用します。
   * ページでの滞在時間： ページでの滞在 [時間 — グループディメンションを使用し](/help/components/dimensions/time-spent-on-page.md) ます。
   * ページへのクリック数： トップのページディメンション値を使用し、特定の訪問でそのページに到達するのに費やしたクリック数を示します。
* 入口と出口
   * 入口ページ： 入 [口ページ](/help/components/dimensions/entry-dimensions.md) ディメンションを使用します。
   * オリジナルの入口ページ： 入口ページの元の [ディメンションを使用し](/help/components/dimensions/entry-dimensions.md) ます。
   * 直帰数： アドビが提供する「 [ページ訪問回数」セグメントを適用したPage](/help/components/dimensions/page.md) （ページ）ディメンションを使用します。
   * 出口ページ： 出 [口ページ](/help/components/dimensions/exit-dimensions.md) ディメンションを使用します。

>[!NOTE]
>
>このフォルダーには、他のレポートも表示できます。 これらはpropなどの他のディメンションで、レポートスイートの設定で [パスを有効にしている](../../admin/admin/c-traffic-variables/traffic-var.md) 。

## トラフィックソース

訪問者がサイトに到着する前にどこから来たかを知ることができるレポートが含まれます。 これらのレポートは、レポートスイートの設定で [内部URLフィルターーを正しく設定しない限り、正しく機能しません](../../admin/admin/internal-url-filter-admin.md) 。

* 検索キーワード — すべて： Searchキーワード [](/help/components/dimensions/search-keyword.md) ディメンションを使用します。
* 検索キーワード — 有料： キーワード [検索 — 有料](/help/components/dimensions/search-keyword.md) ディメンションを使用します。
* 検索キーワード — 自然： 検索キーワード — 自然 [](/help/components/dimensions/search-keyword.md) ディメンションを使用します。
* 検索エンジン — すべて： 検索エンジン [ディメンションを使用します](/help/components/dimensions/search-engine.md) 。
* 検索エンジン — 有料： 検 [索エンジン — 有料](/help/components/dimensions/search-engine.md) ディメンションを使用します。
* 検索エンジン — 自然： [検索エンジン — 自然](/help/components/dimensions/search-engine.md) ディメンションを使用します。
* すべての検索ページのランク： 「 [すべての検索ページのランク](/help/components/dimensions/all-search-page-rank.md) 」ディメンションを使用します。
* 参照ドメイン： [参照ドメイン](/help/components/dimensions/referring-domain.md) ディメンションを使用
* オリジナルの参照ドメイン： オリジナルの参照ドメイン [ディメンションを使用](/help/components/dimensions/original-referring-domain.md) 。
* 転送者: [転送者](/help/components/dimensions/referrer.md) ディメンションを使用します。
* 転送者タイプ： [転送者タイプディメンションを使用し](/help/components/dimensions/referrer-type.md) ます。

## キャンペーン

主に [追跡コード](/help/components/dimensions/tracking-code.md) ディメンションに関するレポートが含まれます。

* キャンペーンコンバージョンファネル： ファネルレポートのクリックスルー数、 [チェックアウト](/help/components/metrics/checkouts.md)、 [注文](/help/components/metrics/orders.md)、 [売上高](/help/components/metrics/revenue.md) をレポートします。 クリックスルー指標は、トラッ [キングコード](/help/components/metrics/instances.md) ディメンションに関連するインスタンス [](/help/components/dimensions/tracking-code.md) 指標に似ています。 フォールアウトビジュアライゼーションを使用したAnalysis Workspaceでも、同様のビジュアライ [ゼーションを実現でき](../analysis-workspace/visualizations/fallout/fallout-flow.md)ます。
* トラッキングコード： ト [ラッキングコード](/help/components/dimensions/tracking-code.md) ディメンションを使用します。

## 製品

主に [Product](/help/components/dimensions/product.md) ディメンションに関するレポートが含まれます。

* 製品コンバージョンファネル： レポート [表示](/help/components/metrics/product-views.md)、買い物かご [、](/help/components/metrics/cart-additions.md)追加数 [、チェックアウト数、チェックアウト数](/help/components/metrics/checkouts.md)[](/help/components/metrics/orders.md)[](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) 、商品注文数、商品注文数、商品注文数、商品注文数、商品注文数レポート内の売上高を表示します。 フォールアウトビジュアライゼーションを使用したAnalysis Workspaceでも、同様のビジュアライ [ゼーションを実現でき](../analysis-workspace/visualizations/fallout/fallout-flow.md)ます。
* 製品： [Products](/help/components/dimensions/product.md) （製品）ディメンションを使用します。
* クロス販売： 共に販売される(Analysis Workspaceで廃止される)商品を表示します。
* カテゴリ: [カテゴリ](/help/components/dimensions/category.md) ディメンションを使用します。

## 訪問者保持率

サイトに戻る訪問者に関するレポートが含まれます。

* 再訪頻度： 再 [来訪頻度](/help/components/dimensions/return-frequency.md) (Return frequency)ディメンションを使用します。
* 再来訪： アドビが提供する「再来訪 [数](/help/components/metrics/visits.md) 」セグメントを適用した、経時的な訪問数指標のトレンドを示します。
* 訪問回数： 訪問回数 [ディメンションを使用し](/help/components/dimensions/visit-number.md) ます。
* 販売サイクル： 購入関連レポートのフォルダー。
   * 顧客の忠誠度： [顧客忠誠度](/help/components/dimensions/customer-loyalty.md) ディメンションを使用します。
   * 初回購入までの日数： 「 [Days before first purchase](/help/components/dimensions/days-before-first-purchase.md) 」ディメンションを使用します。
   * 前回購入からの日数： 前回購入からの [日数](/help/components/dimensions/days-since-last-purchase.md) (Days since last purchase)ディメンションを使用します。
   * 日別ユニーク顧客数： アドビが提供する「購入者」セグメントが適用された [](/help/components/metrics/unique-visitors.md) 日別訪問者数の経時的な推移を示します。
   * 週別ユニーク顧客数： アドビが提供する「購入者」セグメントが適用された [](/help/components/metrics/unique-visitors.md) 週別訪問者数の経時的なトレンドを示します。
   * 月別ユニーク顧客数： アドビが提供する「購入者」セグメントが適用された [](/help/components/metrics/unique-visitors.md) 月別訪問者数の経時的なトレンドを示します。
   * 四半期別ユニーク顧客数： アドビが提供する「購入者」セグメントを適用した [](/help/components/metrics/unique-visitors.md) 四半期別訪問者数の経時的なトレンドを示します。 四半期は、1月から3月、4月から6月、7月から9月、10月から12月です。
   * 年別ユニーク顧客数： アドビが提供する「購入者」セグメントを適用した [年別訪問者数](/help/components/metrics/unique-visitors.md) の経時的なトレンド。

## 訪問者プロファイル

サイトの訪問者に関するレポートが含まれます。

* 地理特性： 世界中のサイト訪問者がどこから来訪したかに関するレポートです。
   * 国： Countries [ディメンションを使用します](/help/components/dimensions/countries.md) 。
   * 地域： Regions [ディメンションを使用します](/help/components/dimensions/regions.md) 。
   * 市区町村： Cities [ディメンションを使用し](/help/components/dimensions/cities.md) ます。
   * 米国の州： 「 [US states](/help/components/dimensions/us-states.md) 」ディメンションを使用します。
   * 米国DMA: [US DMA](/help/components/dimensions/us-dma.md) （米国）ディメンションを使用します。
* 言語： Language [](/help/components/dimensions/language.md) （言語）ディメンションを使用します。
* タイムゾーン： タイムゾーンディメンションを使用します(Analysis Workspaceで削除)。 ディメンション値は、ヒットのGMTオフセットです。
* ドメイン： [Domain](/help/components/dimensions/domain.md) ディメンションを使用します。
* トップレベルドメイン： トップレベルのドメインディメンションを使用します(Analysis Workspaceから削除)。 このレポートは、 [domains](/help/components/dimensions/domain.md) dimensionを上位レベルのカテゴリ（通常、ドメインの国別）にグループ化します。
* 技術： 訪問者がサイトにアクセスする際に使用したレポートを含むフォルダ。
   * ブラウザー： Browsers [ディメンションを使用し](/help/components/dimensions/browser.md) ます。
   * ブラウザーのタイプ： ブ [ラウザータイプ](/help/components/dimensions/browser-type.md) (Browser type)ディメンションを使用します。
   * ブラウザーの幅： ブラウザーの [幅 — グループディメンションを使用し](/help/components/dimensions/browser-width.md) ます。
   * ブラウザーの高さ： ブ [ラウザーの高さ — グループディメンションを使用し](/help/components/dimensions/browser-height.md) ます。
   * オペレーティングシステム： オペレー [ティングシステム](/help/components/dimensions/operating-systems.md) (Operating systems)ディメンションを使用します。
   * オペレーティングシステムの種類： オペレー [ティングシステムタイプ](/help/components/dimensions/operating-system-types.md) (Operating system types)ディメンションを使用します。
   * 画面の色： 色深度( [Color depth](/help/components/dimensions/color-depth.md) )ディメンションを使用します。
   * 画面の解像度： [Monitor resolution](/help/components/dimensions/monitor-resolution.md) （画面の解像度）ディメンションを使用します。
   * Java: [Java対応ディメンションを使用します](/help/components/dimensions/java-enabled.md) 。
   * JavaScript: JavaScriptが有効なディメンションを使用します(Analysis Workspaceには使用されません)。 ブラウザーでJavaScriptが有効になっているかどうかに応じて、ディメンション値は「有効」、「無効」または「不明」です。
   * JavaScriptのバージョン： は、JavaScriptバージョンディメンションを使用します(Analysis Workspaceでは廃止されました)。 ディメンション値は、ブラウザーが使用するJavaScriptのバージョンを示します。
   * Cookie: Cookieサポート [ディメンションを使用します](/help/components/dimensions/cookie-support.md) 。
   * 接続の種類： 「 [接続タイプ](/help/components/dimensions/connection-type.md) 」ディメンションを使用します。
   * 携帯電話会社： 携帯電話会社 [ディメンションを使用し](/help/components/dimensions/mobile-dimensions.md) ます。
* 訪問者の状態： Stateディメンションを使用します(Analysis Workspaceには使用できません)。 ディメンション値は変数から始まり [`state`](../../implement/vars/page-vars/state.md) ます。
* 訪問者の郵便番号： 郵便番号 [ディメンションを使用し](/help/components/dimensions/zip-code.md) ます。

## カスタムコンバージョン

導入に固有のレポートが含まれます。 カスタムコンバージョンレポートでは、 [eVar](/help/components/dimensions/evar.md) をディメンションとして使用します。

## カスタムトラフィック

導入に固有のレポートが含まれます。 カスタムトラフィックレポートでは、ディメンションとして [prop](/help/components/dimensions/prop.md) を使用します。

## マーケティングチャネル

マー [ケティングチャネルに関するレポートが含まれます](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

* チャネルの概要レポート： レポートおよびAnalyticsに固有のカスタムレポート。 ファーストタッチまたはラストタッチのアトリビューションを使用する指標と共に、ディメンション値としてマーケティングチャネルを使用します。
* ファーストタッチチャネル: ファーストタッチ [チャネル](/help/components/dimensions/first-touch-channel.md) ディメンションを使用します。
* ファーストタッチチャネルの詳細： ファーストタッチ [チャネルの詳細](/help/components/dimensions/first-touch-detail.md) ディメンションを使用します。
* ラストタッチチャネル: ラストタッチ [チャネル](/help/components/dimensions/last-touch-channel.md) (Last touch)ディメンションを使用します。
* ラストタッチチャネルの詳細： ラストタッチ [チャネルの詳細](/help/components/dimensions/last-touch-detail.md) (Last touch Detail)ディメンションを使用します。

## ブックマーク

ブックマークを付けたレポートが含まれます。 See [Bookmarks](bookmarks.md) for more information.

## ダッシュボード

作成したダッシュボードが含まれます。 See [Dashboards](dashboard.md) for more information.

## ターゲット

作成したターゲットが含まれます。 See [Targets](targets.md) for more information.

>[!NOTE]
>
>このヘルプページでレポートが見つからない場合は、管理者がフォルダの名前を変更したり、調整したりした可能性があります。 See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
