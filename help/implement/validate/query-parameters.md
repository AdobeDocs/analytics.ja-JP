---
title: データ収集クエリパラメーター
description: イメージリクエストで使用されるすべてのクエリ文字列パラメータをリストします。
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# データ収集クエリパラメーター

次の表に、アドビがイメージリクエストで使用するすべてのクエリ文字列パラメーターを示します。 この情報は、パケットアナライザーを使用したデバッグ [、イメージ要求のハー](packet-monitor.md)ドコーディング [、または動的変数の使用時に](../other/hardcoded.md)使用できます [](../vars/page-vars/dynamic-variables.md)。

| パラメーター | Analytics実装変数 | 説明 |
| --- | --- | --- |
| `aamlh` | なし | Audience Managerの場所のヒントです。Experience cloud共有プロファイルの統合で使用されます。 |
| `aamb` | なし | Audience Manager BLOB。Experience cloud共有プロファイルの統合で使用されます。 |
| `aid` | なし | Analytics 訪問者 ID. |
| `AQB` | なし | イメージリクエストクエリ文字列の先頭を示します。 |
| `AQE` | なし | イメージリクエストの終わりを示します。これは、リクエストが切り捨てられなかったことを意味します。 |
| `bh` | なし | ブラウザーの高さ（ピクセル単位） ブラウザの高さディメンションで使用されます。 |
| `bw` | なし | ブラウザーの幅（ピクセル単位） ブラウザーの幅ディメンションで使用されます。 |
| `c` | なし | 色の画質（ビット）。 色深度ディメンションで使用されます。 |
| `c.` | `contextData` | コンテキストデータ変数の開始を示します。 値を含まない。 |
| `.c` | `contextData` | コンテキストデータ変数の終わりを示します。 値を含まない。 |
| `c1` - `c75` | `prop1` - `prop75` | カスタムトラフィック変数 ～. |
| `cc` | `currencyCode` | ヒットで使用される通貨のタイプ。 |
| `cdp` | `cookieDomainPeriods` | ドメイン内のピリオドの数。 cookieを正しく保存するのに使用します。 |
| `ce` | `charSet` | イメージリクエストの文字エンコーディング. |
| `cl` | `cookieLifetime` | 訪問者 cookie の存続期間。 |
| `ch` | `channel` | サイトセクションディメンションで使用されます。 |
| `cp` | なし | ヒットタイプディメンションで使用されます。 |
| `ct` | なし | Connection typeディメンションで使用されます。 |
| `D` | `dynamicVariablePrefix` | 動的変数に使用する内容を示します。 |
| `ev` | `events` | クエリ文字列 `events` の略記法。 |
| `events` | `events` | ページ上のイベントのコンマ区切りリスト。 |
| `g` | `pageURL` | ページの現在の URL（最大 255 バイト） |
| `-g` | `pageURL` | 255バイトを超えるURLは分割されます。 最初の255バイトがパラメーターに、残り `g` のすべてのバイトがパラメーターに表示さ `-g` れます。 |
| `gn` | `pageName` | クエリ文字列 `pageName` の略記法。 |
| `gt` | `pageType` | クエリ文字列 `pageType` の略記法。 |
| `h1` - `h5` | `hier1` - `hier5` | 階層変数. |
| `hp` | なし | 廃止。以前のバージョンのAdobe Analyticsでは、現在のURLがブラウザーのホームページであるかどうかが判別されました。 |
| `j` | なし | ブラウザーにインストールされるJavaScriptバージョン。 |
| `k` | なし | cookieサポートディメンションで使用されます。 |
| `l1` - `l3` | `list1` - `list3` | リスト変数。 |
| `mid` | なし | Experience cloud訪問者ID。 |
| `ndh` | なし | イメージリクエストがAppMeasurementから送信されたかどうかを示すフラグ。 |
| `ns` | `visitorNameSpace` | Cookieが設定されている場所を判断するのに役立ちます。 |
| `oid` | `objectID` | 最後のページのオブジェクト識別子。 Activity mapで使用されます。 |
| `ot` | なし | 最後のページのオブジェクト名。 以前のバージョンのActivity mapで使用されていました。 |
| `p` | なし | 廃止。ブラウザーで使用されるプラグインのリストです。 |
| `pageName` | `pageName` | Pageディメンションで使用されます。 |
| `pageType` | `pageType` | エラーページディメンションで使用されます。 |
| `pccr` | なし | 新規訪問者に対してのみ設定し、常ににに設定しま `true`す。 無限リダイレクトを防ぎます。 |
| `pe` | `linkType` | カスタムリンクのタイプを決定します。 |
| `pev1` | なし | カスタムリンクが発生したURL。 |
| `pev2` | なし | カスタムリンクのわかりやすい名前. |
| `pev3` | なし | 廃止。以前のバージョンのビデオレポートで追跡されたマイルストーン。 |
| `pf` | なし | プラットフォームフラグ；アドビでのみ使用する場合。 変更できません。 |
| `pid` | なし | 最後のページのページ識別子。 以前のバージョンのActivity mapで使用されていました。 |
| `pidt` | なし | 最後のページのページ識別子タイプ。 以前のバージョンのActivity mapで使用されていました。 |
| `pl` | `products` | クエリ文字列 `products` の略記法。 |
| `products` | `products` | products 変数. |
| `purchaseID` | `purchaseID` | 購入の重複を除外するために使用します。 |
| `r` | `referrer` | ヒットの参照URL。 |
| `s` | なし | Monitor Resolutionsディメンションで使用されます。 画面解像度( `width x height`)。 |
| `server` | `server` | サーバーディメンション。 |
| `sv` | `server` | クエリ文字列 `server` の略記法。 |
| `state` | `state` | 状態ディメンション。 |
| `t` | なし | ヒットの生成日時。 形式を使用しま `dd/mm/yyyy hh:mm:ss w o`す。<br>- `dd/mm/yyyy hh:mm:ss` JavaScriptの日付/時間。 月は1 `0` 月、月は12 `11` 月です。<br>- `w` は曜日です。 `0` は日曜日、は土曜日 `6` です。<br>— 負の `o` GMTオフセット（分単位）。 例えば、 `420` はGMT-7です。 |
| `ts` | `timestamp` | ヒットで設定されたカスタムタイムスタンプ。 通常、オフライントラッキングで使用されます。 |
| `v` | なし | Java対応ディメンションで使用されます。 |
| `v0` | `campaign` | トラッキングコードディメンション。 |
| `v1` - `v250` | `evar1` - `eVar250` | カスタムコンバージョンディメンション。 |
| `vid` | `visitorID` | 訪問者固有の ID。 |
| `vmk` | `vmk` | 廃止。サードパーティCookieからファーストパーティCookieへの移行を支援。 |
| `vvp` | `variableProvider` | Data Connectorsで使用されます。 |
| `xact` | `transactionID` | データソースと共に使用して、データをリンクします。 |
| `zip` | `zip` | 郵便番号ディメンションで使用されます。 |
