---
title: データ収集クエリパラメーター
description: イメージリクエストで使用されるすべてのクエリ文字列パラメーターのリストです。
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 1079
ht-degree: 44%

---

# データ収集クエリパラメーター

次の表に、アドビがイメージリクエストで使用するすべてのクエリ文字列パラメーターを示します。 この情報は、[ パケットアナライザー](packet-monitor.md)でのデバッグ、[画像リクエスト ](../other/hardcoded.md)のハードコーディング、[動的変数](../vars/page-vars/dynamic-variables.md)の使用時に役立ちます。

| パラメーター | Analytics 実装変数 | 説明 |
| --- | --- | --- |
| `aamlh` | なし | Audience Managerの場所のヒント。 Experience Cloud ID サービスを介したAudience Manager IDの同期に使用される地域データセンターを識別します。 |
| `aamb` | なし | Audience Manager blob. Experience Cloud ID サービスを介したID同期中に渡されたエンコードされたAudience Manager プロファイルデータ。 |
| `aid` | なし | `s_vi` Cookieに保存されている従来のAnalytics訪問者ID。 最新の実装では、`mid` パラメーターに置き換えられています。 |
| `AQB` | なし | イメージリクエストクエリ文字列の開始を示します。 |
| `AQE` | なし | イメージリクエストの終了を示します。これは、リクエストが切り捨てられていないことを表しています。 |
| `bh` | なし | ブラウザーの高さ（ピクセル単位）。 「[[!UICONTROL ブラウザーの高さ]](/help/components/dimensions/browser-height.md)」ディメンションで使用されます。 |
| `bw` | なし | ブラウザーの幅（ピクセル単位）。 「[[!UICONTROL ブラウザーの幅]](/help/components/dimensions/browser-width.md)」ディメンションで使用されます。 |
| `c` | なし | カラー画像画質（ビット単位）。 「[[!UICONTROL 色深度]](/help/components/dimensions/color-depth.md)」ディメンションで使用されます。 |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | コンテキストデータ変数の開始を示します。 値を含みません。 |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | コンテキストデータ変数の終了を示します。 値を含みません。 |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [prop](/help/components/dimensions/prop.md)、またはカスタムトラフィック変数。 |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | ヒットで使用される通貨の種類。 |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **使用されていません。** ドメイン内のピリオドの数。 |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | イメージリクエストの文字エンコーディング。 |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | 訪問者 Cookie の存続期間。 |
| `ch` | [`channel`](../vars/page-vars/channel.md) | 「[[!UICONTROL サイトセクション]](/help/components/dimensions/site-section.md)」ディメンションで使用されます。 |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | アプリが前景または背景にあるときにモバイルアプリのヒットが発生したかどうかを指定します。 [[!UICONTROL  ヒットタイプ ]](/help/components/dimensions/hit-type.md) ディメンションで使用されます。 |
| `ct` | なし | [[!UICONTROL 接続タイプ ]](/help/components/dimensions/connection-type.md) ディメンションで使用されます。 |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | 動的変数に使用する内容を示します。 |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | `events` パラメーターの短縮形。 |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | ページ上のイベントのコンマ区切りリスト。 ほとんどの[指標](/help/components/metrics/overview.md)で使用されます。 |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | ページの現在の URL（最大 255 バイト）。 [[!UICONTROL ページ URL]](/help/components/dimensions/page-url.md) ディメンションで使用されます。 |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | 255 バイトを超える URL は分割されます。 最初の 255 バイトが `g` パラメーターに、残りのすべてのバイトが `-g` パラメーターに表示されます。 |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | `pageName` パラメーターの短縮形。 |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | `pageType` パラメーターの短縮形。 |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | [クライアント ヒント](/help/technotes/client-hints.md)を表す様々な変数の接頭辞。 |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **使用されていません。** 階層ディメンション。 |
| `hp` | なし | **使用されていません。** 以前のバージョンの Adobe Analytics では、現在の URL がブラウザーのホームページであるかどうかが判別されました。 |
| `j` | なし | **使用されていません。** ブラウザーにインストールされている JavaScript バージョン。 |
| `k` | なし | [[!UICONTROL Cookie サポート]](/help/components/dimensions/cookie-support.md)ディメンションで使用されます。 |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | リスト変数。 |
| `lat` | なし | **使用されていません。** 自由度： 従来のモバイル SDKの実装で設定されます。現在のモバイルの実装では、データストリームを介して位置情報が送信されます。 |
| `lon` | なし | **使用されていません。** 経度： 従来のモバイル SDKの実装で設定されます。現在のモバイルの実装では、データストリームを介して位置情報が送信されます。 |
| `lrt` | なし | 最後のリクエストが往復する時間である「最後のリクエストタイミング」（ミリ秒）。 シングルページアプリケーション（SPA）など、1つのページから複数のリクエストが送信された場合にのみ送信されます。 |
| `mcorgid` | なし | Experience Cloud ID サービスに対する組織を識別するExperience Cloud組織ID。 |
| `mid` | なし | [[!UICONTROL Experience Cloud訪問者ID]](/help/components/dimensions/experience-cloud-visitor-id.md) ディメンションで使用されます。 |
| `ms_a` | なし | トラッキング対象のストリーミングメディアがビデオではなくオーディオの場合、Media SDKで`1`に設定されます。 |
| `ndh` | なし | AppMeasurementによって生成されるすべての画像リクエストに追加されます。 ハードコードされたリクエストでは通常は省略されるので、ヒットがAppMeasurementから来たことを示します。 |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **使用されていません。** Cookie が設定されている場所を判断するのに役立ちます。 |
| `oi` | なし | **使用されていません。** 最後のページのオブジェクトインスタンス。 以前のバージョンの Activity Map で使用されていました。 |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | 最後のページのオブジェクト識別子。 現在のバージョンのActivity Mapで使用されます。 |
| `oidt` | なし | **使用されていません。** 最後のページのオブジェクト識別子タイプ。 以前のバージョンの Activity Map で使用されていました。 |
| `ot` | なし | **使用されていません。** 最後のページのオブジェクト名。 以前のバージョンの Activity Map で使用されていました。 |
| `p` | なし | **使用されていません。** ブラウザーで使用されるプラグインのリスト。 |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | [[!UICONTROL ページ]](/help/components/dimensions/page.md)ディメンションで使用されます。 |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | [[!UICONTROL エラーページ]](/help/components/dimensions/pages-not-found.md)ディメンションで使用されます。 |
| `pccr` | なし | 永続的なCookie チェックリダイレクトフラグ。 Adobe データ収集サーバーによって新規ビジター用に設定され、常に`true`に設定されます。 新しい訪問者のCookieのサポートが不明な場合、データ収集サーバーは、既に発生した永続的なCookie チェックを確認するために、このフラグを使用してイメージリクエストを自分自身にリダイレクトします。 このパラメーターは、訪問者がCookieを拒否した場合の無限リダイレクトを防ぎます。 |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | ヒットのタイプを指定します。 有効な値には、`lnk_o` （[[!UICONTROL  カスタムリンク ]](/help/components/dimensions/custom-link.md)）、`lnk_d` （[[!UICONTROL  ダウンロードリンク ]](/help/components/dimensions/download-link.md)）、`lnk_e` （[[!UICONTROL 終了リンク ]](/help/components/dimensions/exit-link.md)）および`tnt` （Target ヒットのAnalytics）が含まれます。 |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | カスタムリンクが発生したURL。 |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | [ カスタムリンク ](/help/components/dimensions/custom-link.md)のわかりやすい名前。 |
| `pev3` | なし | **使用されていません。** 以前のバージョンのビデオレポートで追跡されたマイルストーン。 |
| `pf` | なし | プラットフォームフラグ（アドビでのみ使用）。 変更できません。 |
| `pid` | なし | **使用されていません。** 最後のページのページ識別子。 以前のバージョンの Activity Map で使用されていました。 |
| `pidt` | なし | **使用されていません。** 最後のページのページ識別子タイプ。 以前のバージョンの Activity Map で使用されていました。 |
| `pl` | [`products`](../vars/page-vars/products.md) | `products` パラメーターの短縮形。 |
| `products` | [`products`](../vars/page-vars/products.md) | products 変数。 [[!UICONTROL 製品]](/help/components/dimensions/product.md)および[[!UICONTROL カテゴリ]](/help/components/dimensions/category.md)ディメンションで使用されます。 |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | [[!UICONTROL 購入ID]](/help/components/dimensions/purchase-id.md) ディメンションで使用されます。 |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | ヒットのリファラー URL。 [[!UICONTROL Referrer]](/help/components/dimensions/referrer.md)や[[!UICONTROL Referring domain]](/help/components/dimensions/referring-domain.md)などのトラフィックソースディメンションで使用されます。 |
| `s` | なし | 画面解像度（`width x height`）。 [[!UICONTROL モニター解析度]](/help/components/dimensions/monitor-resolution.md)ディメンションで使用されます。 |
| `sdid` | なし | 補足データ ID。 Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html)統合の[AnalyticsとTarget ヒットなど、同じイベントを記述する複数のヒットをリンクします。 |
| `server` | [`server`](../vars/page-vars/server.md) | 「[[!UICONTROL サーバー]](/help/components/dimensions/server.md)」ディメンションで使用されます。 |
| `sv` | [`server`](../vars/page-vars/server.md) | `server` パラメーターの短縮形。 |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **使用されていません。** 一般的に郵送または請求フォームを通じて、訪問者が入力した米国の州をキャプチャします。 |
| `t` | なし | ヒットの生成日時。 JavaScriptでは、`dd/mm/yyyy hh:mm:ss w o`.<br>～`dd/mm/yyyy hh:mm:ss`の形式が日時です。 月`0`は1月、月`11`は12月です。<br> ～ `w`は曜日です。 `0`は日曜日で、`6`は土曜日です。<br>- `o`は分単位の負のGMT オフセットです。 例えば、`420` は GMT-7 です。 |
| `tnt` | なし | Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html)統合の[Analyticsで使用されるTarget データペイロード。 `pe=tnt`時に送信されました。 |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | ヒットで設定されたカスタムタイムスタンプ。 通常、オフライントラッキングで使用されます。 |
| `u` | なし | **使用されていません。** 以前のバージョンのActivity Mapで使用されるアカウントマーカー。 |
| `v` | なし | [[!UICONTROL Java 対応]](/help/components/dimensions/java-enabled.md)ディメンションで使用されます。 |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [[!UICONTROL  トラッキングコード ]](/help/components/dimensions/tracking-code.md) ディメンションで使用されます。 |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md)、またはカスタムコンバージョンディメンション。 |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | 訪問者IDの上書き変数。 |
| `vidn` | なし | リダイレクトされたイメージリクエストに`pccr` パラメーターを伴う、新しい訪問者に対してAdobe データ収集サーバーによって設定されます。 訪問者Cookieに保存されている訪問者ID値が含まれます。 |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **使用されていません。** サードパーティ Cookieからファーストパーティ Cookieへの移行時に使用される訪問者移行サーバー。 |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **使用されていません。** 訪問者の移行キー。サードパーティ Cookieからファーストパーティ Cookieへの実装の移行に役立ちました。 |
| `vvp` | なし | **使用されていません。** Data Connectorsで使用されるバリアブルプロバイダー。 |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | データソースと共に使用して、オンラインデータとオフラインデータを結び付けます。 |
| `zip` | [`zip`](../vars/page-vars/zip.md) | [郵便番号](/help/components/dimensions/zip-code.md)ディメンションで使用されます。 |
