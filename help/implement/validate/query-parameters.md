---
title: データ収集クエリーパラメーター
description: イメージリクエストで使用されるすべてのクエリー文字列パラメーターをリストします。
translation-type: ht
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: ht
source-wordcount: '648'
ht-degree: 100%

---


# データ収集クエリーパラメーター

次の表に、アドビがイメージリクエストで使用するすべてのクエリー文字列パラメーターを示します。この情報は、[パケットアナライザー](packet-monitor.md)を使用したデバッグ、[イメージリクエストのハードコーディング](../other/hardcoded.md)、[動的変数](../vars/page-vars/dynamic-variables.md)の使用時に使用できます。

| パラメーター | Analytics 実装変数 | 説明 |
| --- | --- | --- |
| `aamlh` | なし | Audience Manager のロケーションヒント。Experience Cloud 共有プロファイルの統合で使用。 |
| `aamb` | なし | Audience Manager Blob。Experience Cloud 共有プロファイルの統合で使用。 |
| `aid` | なし | Analytics 訪問者 ID。 |
| `AQB` | なし | イメージリクエストクエリー文字列の開始を示します。 |
| `AQE` | なし | イメージリクエストの終了を示します。これは、リクエストが切り捨てられていないことを表しています。 |
| `bh` | なし | ブラウザーの高さ（ピクセル単位）。「[ブラウザーの高さ](/help/components/dimensions/browser-height.md)」ディメンションで使用されます。 |
| `bw` | なし | ブラウザーの幅（ピクセル単位）。「[ブラウザーの幅](/help/components/dimensions/browser-width.md)」ディメンションで使用されます。 |
| `c` | なし | カラー画像画質（ビット単位）。「[色深度](/help/components/dimensions/color-depth.md)」ディメンションで使用されます。 |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | コンテキストデータ変数の開始を示します。値を含みません。 |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | コンテキストデータ変数の終了を示します。値を含みません。 |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [prop](/help/components/dimensions/prop.md)、またはカスタムトラフィック変数。 |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | ヒットで使用される通貨の種類。 |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | ドメイン内のピリオドの数。Cookie を正しく保存するのに使用します。 |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | イメージリクエストの文字エンコーディング。 |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | 訪問者 Cookie の存続期間。 |
| `ch` | [`channel`](../vars/page-vars/channel.md) | 「[サイトセクション](/help/components/dimensions/site-section.md)」ディメンションで使用されます。 |
| `cp` | なし | 「[ヒットタイプ](/help/components/dimensions/hit-type.md)」ディメンションで使用されます。 |
| `ct` | なし | 「[接続タイプ](/help/components/dimensions/connection-type.md)」ディメンションで使用されます。 |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | 動的変数に使用する内容を示します。 |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | `events` クエリー文字列の略記法。 |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | ページ上のイベントのコンマ区切りリスト。ほとんどの[指標](/help/components/metrics/overview.md)で使用されます。 |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | ページの現在の URL（最大 255 バイト）。[ページ URL](/help/components/dimensions/page-url.md) ディメンションで使用されます。 |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | 255 バイトを超える URL は分割されます。最初の 255 バイトが `g` パラメーターに、残りのすべてのバイトが `-g` パラメーターに表示されます。 |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | `pageName` クエリー文字列の略記法。 |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | `pageType` クエリー文字列の略記法。 |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | 階層ディメンション。 |
| `hp` | なし | 廃止。以前のバージョンの Adobe Analytics では、現在の URL がブラウザーのホームページであるかどうかが判別されました。 |
| `j` | なし | ブラウザーにインストールされている JavaScript バージョン。 |
| `k` | なし | [Cookie サポート](/help/components/dimensions/cookie-support.md)ディメンションで使用されます。 |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | リスト変数。 |
| `mid` | なし | Experience Cloud 訪問者 ID。 |
| `ndh` | なし | イメージリクエストが AppMeasurement から送信されたかどうかを示すフラグ。 |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Cookie が設定されている場所を判断するのに役立ちます。 |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | 最後のページのオブジェクト識別子。Activity Map で使用されます。 |
| `ot` | なし | 最後のページのオブジェクト名。以前のバージョンの Activity Map で使用されていました。 |
| `p` | なし | 廃止。ブラウザーで使用されるプラグインのリスト。 |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | [ページ](/help/components/dimensions/page.md)ディメンションで使用されます。 |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | [エラーページ](/help/components/dimensions/pages-not-found.md)ディメンションで使用されます。 |
| `pccr` | なし | 新規訪問者に対してのみ設定し、常に `true` に設定します。無限リダイレクトを防ぐのに役立ちます。 |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | カスタムリンクのタイプを決定します。[カスタムリンク](/help/components/dimensions/custom-link.md)、[ダウンロードリンク](/help/components/dimensions/download-link.md)、[離脱リンク](/help/components/dimensions/exit-link.md)に必須です。 |
| `pev1` | なし | カスタムリンクが発生した URL。 |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | カスタムリンクのわかりやすい名前。 |
| `pev3` | なし | 廃止。以前のバージョンのビデオレポートで追跡されたマイルストーン。 |
| `pf` | なし | プラットフォームフラグ（アドビでのみ使用）。変更できません。 |
| `pid` | なし | 最後のページのページ識別子。以前のバージョンの Activity Map で使用されていました。 |
| `pidt` | なし | 最後のページのページ識別子タイプ。以前のバージョンの Activity Map で使用されていました。 |
| `pl` | [`products`](../vars/page-vars/products.md) | `products` クエリー文字列の略記法。 |
| `products` | [`products`](../vars/page-vars/products.md) | products 変数。[製品](/help/components/dimensions/product.md)および[カテゴリ](/help/components/dimensions/category.md)ディメンションで使用されます。 |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | 購入の重複を除外するために使用します。 |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | ヒットのリファラー URL。トラフィックソースディメンション（[リファラー](/help/components/dimensions/referrer.md)、[参照ドメイン](/help/components/dimensions/referring-domain.md)など）で使用されます。 |
| `s` | なし | 画面解像度（`width x height`）。[モニター解析度](/help/components/dimensions/monitor-resolution.md)ディメンションで使用されます。 |
| `server` | [`server`](../vars/page-vars/server.md) | [サーバー](/help/components/dimensions/server.md)ディメンション。 |
| `sv` | [`server`](../vars/page-vars/server.md) | `server` クエリー文字列の略記法。 |
| `state` | [`state`](../vars/page-vars/state.md) | 状態ディメンション。 |
| `t` | なし | ヒットの生成日時。`dd/mm/yyyy hh:mm:ss w o` 形式を使用します。<br> - `dd/mm/yyyy hh:mm:ss` JavaScript の日時。`0` は 1 月、`11` は 12 月です。<br> - `w` は曜日です。`0` は日曜日、`6` は土曜日です。<br> - `o` は負の GMT オフセット（分単位）。例えば、`420` は GMT-7 です。 |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | ヒットで設定されたカスタムタイムスタンプ。通常、オフライントラッキングで使用されます。 |
| `v` | なし | [Java 対応](/help/components/dimensions/java-enabled.md)ディメンションで使用されます。 |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [トラッキングコードデ](/help/components/dimensions/tracking-code.md)ィメンション。 |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md)、またはカスタムコンバージョンディメンション。 |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | 訪問者固有の ID。 |
| `vmk` | `vmk` | 廃止。訪問者移行キー。サードパーティ Cookie からファーストパーティ Cookie への実装を移行するのに役立ちました。 |
| `vvp` | `variableProvider` | Data Connectors で使用されます。 |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | データソースと共に使用して、オンラインデータとオフラインデータを結び付けます。 |
| `zip` | [`zip`](../vars/page-vars/zip.md) | [郵便番号](/help/components/dimensions/zip-code.md)ディメンションで使用されます。 |
