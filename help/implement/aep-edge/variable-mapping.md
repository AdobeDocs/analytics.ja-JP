---
title: Adobe Experience Edge での Analytics 変数のマッピング
description: Edge が Analytics 変数に自動的にマッピングする XDM フィールドを表示します。
source-git-commit: 984d62f6ece15ebbd41dbbd1e3cb800faa7f323b
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---


# Adobe Experience Edge での Analytics 変数のマッピング

次の表に、Adobe Experience Platform Edge Network がAdobe Analyticsに自動的にマッピングする変数を示します。 これらの XDM フィールドパスを使用する場合、Adobe Analyticsにデータを送信するための追加の設定は必要ありません。

| XDM フィールドパス | Analytics ディメンションと説明 |
| --- | --- |
| `application.id` | モバイルディメンション [アプリ ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.isClose` | モバイル指標の定義に役立ちます [クラッシュ](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | 終了イベントがクラッシュであるかどうかを判断します。 有効な値は次のとおりです。 `close` （ライフサイクルセッションが終了し、前のセッションで一時停止イベントを受け取った場合） `unknown` （ライフサイクルセッションは一時停止イベントなしで終了します）。 |
| `application.isInstall` | モバイル指標 [インストール](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | モバイル指標 [起動回数](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | モバイルディメンションの設定に役立ちます [アプリ ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.launches.value` | モバイル指標 [起動回数](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isUpgrade` | モバイル指標 [アップグレード](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | モバイルディメンションの設定に役立ちます [アプリ ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | モバイル指標 [セッションの長さの合計](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) から [チェックアウト](../../components/metrics/checkouts.md) 指標。 |
| `commerce.checkouts.value` | インクリメント [チェックアウト](../../components/metrics/checkouts.md) 指標を必要な量で示します。 |
| `commerce.order.currencyCode` | を設定します。 [currencyCode](../vars/config-vars/currencycode.md) 設定変数。 |
| `commerce.order.purchaseID` | を設定します。 [purchaseID](../vars/page-vars/purchaseid.md) ページ変数を使用します。 |
| `commerce.productListAdds.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) から [買い物かごへの追加](../../components/metrics/cart-additions.md) 指標。 |
| `commerce.productListAdds.value` | インクリメント [買い物かごへの追加](../../components/metrics/cart-additions.md) 指標を必要な量で示します。 |
| `commerce.productListOpens.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) から [買い物かご](../../components/metrics/carts.md) 指標。 |
| `commerce.productListOpens.value` | インクリメント [買い物かご](../../components/metrics/carts.md) 指標を必要な量で示します。 |
| `commerce.productListRemovals.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) から [買い物かごからの削除](../../components/metrics/cart-removals.md) 指標。 |
| `commerce.productListRemovals.value` | インクリメント [買い物かごからの削除](../../components/metrics/cart-removals.md) 指標を必要な量で示します。 |
| `commerce.productListViews.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) から [買い物かご表示](../../components/metrics/cart-views.md) 指標。 |
| `commerce.productListViews.value` | インクリメント [買い物かご表示](../../components/metrics/cart-views.md) 指標を必要な量で示します。 |
| `commerce.productViews.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) から [製品表示](../../components/metrics/product-views.md) 指標。 |
| `commerce.productViews.value` | インクリメント [製品表示](../../components/metrics/product-views.md) 指標を必要な量で示します。 |
| `commerce.purchases.value` | インクリメント [注文](../../components/metrics/orders.md) 指標を必要な量で示します。 |
| `device.manufacturer` | モバイルデバイスの製造元。 |
| `device.model` | モバイルディメンション [デバイス名](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.modelNumber` | モバイルデバイスのモデル番号。 |
| `device.colorDepth` | 設定に役立つ [色深度](../../components/dimensions/color-depth.md) ディメンション。 |
| `device.screenHeight` | 設定に役立つ [画面の解像度](../../components/dimensions/monitor-resolution.md) ディメンション。 XDM フィールドも必ず設定してください `device.screenWidth`. |
| `device.screenWidth` | 設定に役立つ [画面の解像度](../../components/dimensions/monitor-resolution.md) ディメンション。 XDM フィールドも必ず設定してください `device.screenHeight`. |
| `device.type` | モバイルデバイスタイプ。 |
| `environment.browserDetails.acceptLanguage` | 設定に役立つ [言語](../../components/dimensions/language.md) ディメンション。 |
| `environment.browserDetails.cookiesEnabled` | を設定します。 [cookie サポート](../../components/dimensions/cookie-support.md) ディメンション。 有効な値は次のとおりです。 `Y` （ブラウザーが cookie を受け入れる）および `N` （ブラウザーは Cookie を拒否します）。 |
| `environment.browserDetails.javaEnabled` | を設定します。 [Java 有効](../../components/dimensions/java-enabled.md) ディメンション。 有効な値は次のとおりです。 `Y` （Java が有効になっている）と `N` （Java は無効です）。 |
| `environment.browserDetails.userAgent` | フォールバックとして使用されます [ユニーク訪問者](../../components/metrics/unique-visitors.md) 識別方法。 通常、 `User-Agent` HTTP リクエストヘッダー。 このフィールドをレポートで使用する場合は、eVarにマッピングできます。 |
| `environment.browserDetails.viewportHeight` | を設定します。 [ブラウザーの高さ](../../components/dimensions/browser-height.md) ディメンション。 |
| `environment.browserDetails.viewportWidth` | を設定します。 [ブラウザーの幅](../../components/dimensions/browser-width.md) ディメンション。 |
| `environment.carrier` | モバイルディメンション [通信事業者名](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | 設定に役立つ [接続タイプ](../../components/dimensions/connection-type.md) ディメンション。 |
| `environment.ipV4` | フォールバックとして使用されます [ユニーク訪問者](../../components/metrics/unique-visitors.md) 識別方法。 通常、 `X-Forwarded-For` HTTP ヘッダー。 |
| `environment.language` | モバイルディメンションのロケール。 |
| `environment.operatingSystem` | モバイルディメンション [オペレーティングシステム](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | モバイルディメンション [オペレーティングシステムのバージョン](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.type` | イベントが [着用できる](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/c-android-wearables--additional-notes.html) デバイス。 有効な値は次のとおりです。 `Application` （このイベントはアプリから来たものです）、 `Extension` （イベントはウェアラブルアプリから来たもの）、または `Widget` （イベントはモバイルウィジェットから来たものです）。 |
| `identityMap.ECID[0].id` | この [Adobe Experience Cloud Identity Service ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja). |
| `marketing.trackingCode` | を設定します。 [トラッキングコード](../../components/dimensions/tracking-code.md) ディメンション。 |
| `media.mediaTimed.completes.value` | Media Analytics 指標 [コンテンツ完了](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`、`c.a.media.timePlayed`、`c.a.media.play` |
| `media.mediaTimed.federated.value` | Media Analytics 指標 [Federated Data](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | Media Analytics 指標 [25%プログレスマーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | Media Analytics 指標 [コンテンツセグメント視聴回数](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `media.mediaTimed.midpoints.value` | Media Analytics 指標 [50%プログレスマーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | Media Analytics 指標 [一時停止時間合計](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `media.mediaTimed.pauses.value` | Media Analytics 指標 [一時停止イベント](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `media.mediaTimed.primaryAssetReference.@id` | Media Analytics ディメンション [アセット ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `media.mediaTimed.primaryAssetReference.dc:title` | Media Analytics ディメンション [ビデオ名](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Media Analytics ディメンション [作成者](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Episode.iptc4xmpExt:Number` | Media Analytics ディメンション [エピソード](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Genre` | Media Analytics ディメンション [ジャンル](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Media Analytics ディメンション [コンテンツ評価](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Season.iptc4xmpExt:Number` | Media Analytics ディメンション [シーズン](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Media Analytics ディメンション [コンテンツ ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Series.iptc4xmpExt:Name` | Media Analytics ディメンション [表示](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `media.mediaTimed.primaryAssetReference.showType` | Media Analytics ディメンション [番組タイプ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `media.mediaTimed.primaryAssetReference.xmpDM:duration` | Media Analytics ディメンション [ビデオの長さ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.@id` | Media Analytics ディメンション [メディアセッション ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.broadcastChannel` | Media Analytics ディメンション [コンテンツチャネル](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.broadcastContentType` | Media Analytics ディメンション [コンテンツタイプ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.broadcastNetwork` | Media Analytics ディメンション [ネットワーク](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `media.mediaTimed.primaryAssetViewDetails.mediaSegmentView.value` | Media Analytics ディメンション [コンテンツセグメント](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.playerName` | Media Analytics ディメンション [コンテンツプレイヤー名](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.playerSDKVersion.version` | Media Analytics ディメンション [SDK のバージョン](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.sourceFeed` | Media Analytics ディメンション [メディアフィードのタイプ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.streamFormat` | Media Analytics ディメンション [ストリーム形式](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `media.mediaTimed.progress10.value` | Media Analytics 指標 [10%プログレスマーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | Media Analytics 指標 [95%プログレスマーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | Media Analytics 指標 [コンテンツ再開](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `media.mediaTimed.starts.value` | Media Analytics 指標 [メディア開始](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | Media Analytics 指標 [75%プログレスマーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | Media Analytics 指標 [コンテンツ視聴時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | Media Analytics 指標 [メディア視聴時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `placeContext.geo.latitude` | Mobile ディメンションの緯度。 |
| `placeContext.geo.longitude` | モバイルディメンションの経度。 |
| `placeContext.geo.postalCode` | この [郵便番号](../../components/dimensions/zip-code.md) ディメンション。 |
| `placeContext.geo.stateProvince` | この [米国の州](../../components/dimensions/us-states.md) ディメンション。 |
| `productListItems[N].lineItemId` | この [カテゴリ](../../components/dimensions/category.md) ディメンション。 |
| `productlistitems[N].name` | この [製品](../../components/dimensions/product.md) ディメンション。 |
| `productlistitems[N].priceTotal` | を判断するのに役立ちます [売上高](../../components/metrics/revenue.md) 指標。 |
| `productlistitems[N].quantity` | を判断するのに役立ちます [単位](../../components/metrics/units.md) 指標。 |
| `web.webInteraction.URL` | この [linkURL](../vars/config-vars/linkurl.md) 実装変数。 |
| `web.webInteraction.name` | この [カスタムリンク](../../components/dimensions/custom-link.md), [ダウンロードリンク](../../components/dimensions/download-link.md)または [出口リンク](../../components/dimensions/exit-link.md) ディメンション ( `web.webInteraction.type` |
| `web.webInteraction.type` | クリックされたリンクのタイプを決定します。 有効な値は次のとおりです。 `lnk_o` （カスタムリンク） `lnk_d` （ダウンロードリンク）、 `lnk_e` （出口リンク）。 |
| `web.webPageDetails.URL` | この [ページ URL](../../components/dimensions/page-url.md) ディメンション。 |
| `web.webPageDetails.errorPage` | 「エラーページ (404)」を判断するのに役立つフラグ [ディメンション](../../components/dimensions/pages-not-found.md) および [指標](../../components/metrics/pages-not-found.md). |
| `web.webPageDetails.name` | この [ページ](../../components/dimensions/page.md) ディメンション。 |
| `web.webPageDetails.server` | この [サーバー](../../components/dimensions/server.md) ディメンション。 |
| `web.webPageDetails.siteSection` | この [サイトセクション](../../components/dimensions/site-section.md) ディメンション。 |
| `web.webReferrer.URL` | この [リファラー](../../components/dimensions/referrer.md) ディメンション。 |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## 他の XDM フィールドの Analytics 変数へのマッピング

Adobe Analyticsに追加するディメンションまたは指標がある場合は、 [コンテキストデータ変数](../vars/page-vars/contextdata.md). すべての XDM フィールド要素は、プレフィックスを持つコンテキストデータとしてAdobe Analyticsに送信されます `a.x`. その後、 [処理ルール](../../admin/admin/c-processing-rules/processing-rules.md). 例えば、次のイベントを送信する場合：

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

Web SDK は、そのデータをコンテキストデータ変数としてAdobe Analyticsに送信します `a.x._atag.search.term`. その後、処理ルールを使用して、そのコンテキストeVar変数値を目的の Analytics 変数（データなど）に割り当てることができます。

![検索語句の処理ルール](assets/examplerule.png)
