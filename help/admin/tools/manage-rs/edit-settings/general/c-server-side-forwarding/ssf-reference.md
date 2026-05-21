---
description: サーバーサイド転送コールでの設定変数、HTTP ヘッダー、データ信号の完全な一覧と説明です。
title: サーバーサイド転送のデータとコードのリファレンス
feature: Report Suite Settings
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
TQID: https://experienceleague.adobe.com/DuHi1F4wU6EfxGe8s9EWZ54TX7KnkN3MmAOUE8a9oqw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 561
ht-degree: 91%

---

# サーバーサイド転送のデータとコードのリファレンス

サーバーサイド転送コールでの設定変数、HTTP ヘッダー、データ信号の完全な一覧と説明です。

## 設定変数 {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

接頭辞 `d_*` が付いたパラメーターは、[データ収集サーバー](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=ja)（DCS）によって使用される特殊なシステムレベルのキーと値のペアを示します。 [DCS API 呼び出しでサポートされる属性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=ja) も参照してください。

| パラメーター | 説明 |
|--- |--- |
| `d_rs` | （レガシー／トラッキングサーバーベースのサーバーサイド転送で設定） <br>Analytics にヒットと共に渡されるレポートスイートに設定します。 |
| `d_dst_filter` | （レポートスイートベースのサーバーサイド転送で設定）<br>Analytics にヒットと共に渡されるレポートスイート ID に設定します。 |
| `d_dst` | クライアントに送り返される宛先に関する内容を Analytics へのリクエストが想定している場合は、`d_dst=1` <br> を設定します。 |
| `d_mid` | Analytics に渡される Experience Cloud ID。 |

## HTTP ヘッダー {#section_0549705E76004F9585224AEF872066C0}

これらのヘッダーは、HTTP呼び出しのデータ要求や応答などの情報を含むフィールドです。

| HTTP ヘッダー | 説明 | Audience Manager が受け取る h_キー |
| --- | --- | --- |
| ホスト | これは、Analytics ホスト設定ファイルで指定したクライアントの特定のデータ収集ホスト名に設定されます。 `host name .demdex.net` と表示されます。 [Demdex ドメインへの呼び出しについて](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=ja) を参照してください。 | `h_host` |
| User-Agent | Analytics に渡される User-Agent ヘッダーに設定します。 | `h_user-agent` |
| Accept-Language | Analytics に渡される `Accept-Language` ヘッダーに設定します。 | `h_accept-language` |
| 参照元 | Analytics に渡されるページ URL か、Analytics に渡される `Referer` ヘッダーから収集されるページ URL に設定します。 | `h_referer` |
| リファラー | Analytics に渡されるページ URL か、Analytics に渡される `Referrer` ヘッダーから収集されるページ URL に設定します。 | `h_referrer` |
| 日付 | Analytics に渡される `Date` ヘッダーに設定します。 | `h_date` |

また、`h_ip` シグナルが、DCS にリクエストを送信するホストの IP から生成されます。

## 顧客定義のシグナル {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

接頭辞 `c_` が付いたパラメーターは、カスタム定義の変数を示します。 [DCS API 呼び出しでサポートされる属性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=ja) も参照してください。

| シグナル | 説明 |
| --- |--- |
| `c_browserWidth` と `c_browserHeight` | ブラウザーウィンドウの幅と高さ。 |
| `c_campaign` | `s.campaign` で設定。 |
| `c_channel` | `s.channel` で設定。 |
| `c_clientDateTime` | `dd/mm/yyy hh:mm:ss  W TZ` として書式設定されたタイムスタンプ。 `TZ` は分単位であり、`Date.getTimezoneOffset` メソッドの戻り値と一致します。 |
| `c_colorDepth` | 16 ビットまたは 32 ビットカラーとして指定します。 |
| `c_connectionType` | 接続タイプを指定します。 次に、オプションを示します。<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | 例：<ul><li>AppMeasurement：`s.contextData`</li><li>[category] = &quot;news&quot;;</li><li>シグナル：`c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Cookieを有効にできるかどうかを指定します。 オプションは次のとおりです：はい、いいえ、不明 |
| `c_currencyCode` | トランザクションに使用する通貨のタイプ。 |
| `c_evar#` | カスタム eVar |
| `c_events` | `s.events` で設定。 |
| `c_hier#` | カスタム階層変数。 |
| `c_javaEnabled` | Javaを有効にできるかどうかを指定します。 オプションは次のとおりです：はい、いいえ、不明 |
| `c_javaScriptVersion` | ブラウザーでサポートされている JavaScript のバージョン。 |
| `c_latitude` | 緯度（数値） |
| `c_linkClick` | オプション：カスタム、ダウンロード終了 |
| `c_linkCustomName` | リンクに指定されたカスタム名（存在する場合）。 |
| `c_linkDownloadURL` | ダウンロードリンクの URL。 |
| `c_linkExitURL` | 離脱リンクの URL。 |
| `c_list#` | カスタムリスト変数。 |
| `c_longitude` | 経度（数値）。 |
| `c_mediaPlayerType` | メディアストリームトラッキングリクエスト用。 オプションには、その他、primetimeなどがあります。 |
| `c_pageName` | ページ名（設定されている場合）。 |
| `c_pageURL` | ブラウザーのアドレスバーに表示されるページのアドレス。 |
| `c_products` | 製品文字列（`s.products` で設定）。 |
| `c_prop` | カスタムプロパティ。 |
| `c_purchaseID` | 購入の一意の ID。 |
| `c_referrer` | 現在のページの直前のページ。 |
| `c_screenResolution` | 画面の幅と高さ（ピクセル単位）。 |
| `c_server` | Web サーバー名（`s.server` で設定）。 |
| `c_state` | 地理的地域（`s.state` で設定）。 |
| `c_timezone` | 時間オフセット（時間単位）。 |
| `c_transactionID` | トランザクションの一意の ID。 |
| `c_zip` | 郵便番号（`s.zip` で設定）。 |
