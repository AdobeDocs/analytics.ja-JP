---
description: サーバー側転送コールでの設定変数、HTTP ヘッダー、データ信号の完全な一覧と説明です。
seo-description: サーバー側転送コールでの設定変数、HTTP ヘッダー、データ信号の完全な一覧と説明です。
seo-title: サーバー側転送データとコードリファレンス
title: サーバー側転送データとコードリファレンス
uuid: 3eb3ea0f- a530-448d- bba5-6408b2490dc8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# サーバー側転送データとコードリファレンス

サーバー側転送コールでの設定変数、HTTP ヘッダー、データ信号の完全な一覧と説明です。

## 設定変数 {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) (DCS). [DCS API 呼び出しでサポートされる属性](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html)も参照してください。

| パラメーター | 説明 |
|--- |--- |
| d_rs | (Gets set with legacy/tracking-server-based server-side forwarding) <br>Set to the report suites passed in with the hit to Analytics. |
| d_dst_filter | (Gets set with report-suite-based server-side forwarding)  <br>Set to the report suite IDs passed in with the hit to Analytics. |
| d_dst | Analytics へのリクエストに対して宛先に関するコンテンツがクライアントに送り返されることを期待している場合は d_dst=1<br> を設定します。 |
| d_mid | Analytics に渡される Experience Cloud ID。 |

## HTTP ヘッダー {#section_0549705E76004F9585224AEF872066C0}

これらのヘッダーは、HTTP 呼び出し内のデータおよび応答のリクエストのような情報を格納するフィールドです。

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| HTTP ヘッダー | 説明 |
|--- |--- |
| ホスト | これは、Analytics ホスト設定ファイルで指定したクライアントの特定のデータ収集ホスト名に設定されます。`host name .demdex.net` と表示されます。Demdex ドメインの呼び出しについてを参照してください。 |
| User-Agent | Analytics に渡される User-Agent ヘッダーに設定します。 |
| X-Original-User-Agent | Only set if an alternate user agent was specified by one of these headers: </br>`X-Device-User-Agent\ `  </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-Forwarded-For | 要求元クライアントの IP アドレスに設定します。Analytics は、既に受信 `X-Forwarded-For` ヘッダーを解析して、使用する正しい IP アドレスを特定している可能性があります。 |
| Accept-Language | Analytics に渡される `Accept-Language` ヘッダーに設定します。 |
| 参照元 | Analytics に渡されるページ URL か、Analytics に渡される Referer ヘッダーから収集されるページ URL に設定します。 |

## カスタム定義のシグナル {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parameters prefixed with `c_` identify customer-defined variables. [DCS API 呼び出しでサポートされる属性](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html)も参照してください。

| シグナル | 説明 |
|--- |--- |
| c_browserWidth および c_browserHeight | ブラウザーウィンドウの幅と高さ。 |
| c_campaign | s.campaign によって設定されます。 |
| c_channel | s.channel によって設定されます。 |
| c_clientDateTime | dd/mm/yyy hh形式のタイムスタンプmm:ss W TZ.TZ は分単位で表され、Date.getTimezoneOffset メソッドの戻り値と一致します。 |
| c_colorDepth | 16 または 32 ビットカラーとして指定します。 |
| c_connectionType | 接続のタイプを指定します。オプションは以下のとおりです。<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | 例：<ul><li>AppMeasurement:s. contextData</li><li>["category»?=«news]</li><li>シグナル：c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Cookie を有効にできるかどうかを指定します。オプションは以下のとおりです。yes， no， unknown |
| c_currencyCode | トランザクションに使用する通貨のタイプ。 |
| c_evar# | カスタム evar。 |
| c_events | s.events によって設定されます。 |
| c_hier# | カスタム階層変数。 |
| c_javaEnabled | Java を有効にできるかどうかを指定します。オプションは以下のとおりです。yes， no， unknown |
| c_javaScriptVersion | ブラウザーでサポートされている JavaScript のバージョン。 |
| c_latitude | 緯度（数値）。 |
| c_linkClick | 次のオプションがあります。カスタム、ダウンロードの終了 |
| c_linkCustomName | リンクに指定されたカスタムの名前（存在する場合）。 |
| c_linkDownloadURL | ダウンロードリンクの URL。 |
| c_linkExitURL | 出口リンクの URL。 |
| c_list# | カスタムリスト変数。 |
| c_longitude | 経度（数値）。 |
| c_mediaPlayerType | メディアストリームトラッキングリクエスト用。オプションは以下のとおりです。other， meesttime |
| c_pageName | ページ名（設定されている場合）。 |
| c_pageURL | ブラウザーのアドレスバー内のページのアドレス。 |
| c_products | 製品文字列（s.products によって設定されます）。 |
| c_prop | カスタム prop。 |
| c_purchaseID | 購入の一意の ID。 |
| c_referrer | 現在のページの直前のページ。 |
| c_screenResolution | 画面の幅と高さ（ピクセル単位）。 |
| c_server | Web サーバー名（s.server によって設定されます）。 |
| c_state | 地理的地域（s.state によって設定されます）。 |
| c_timezone | 時間オフセット（時間単位）。 |
| c_transactionID | トランザクションの一意の ID。 |
| c_zip | 郵便番号（s.zip によって設定されます）。 |
