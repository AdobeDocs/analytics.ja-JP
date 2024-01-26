---
title: Adobe Experience Edge での Analytics 変数のマッピング
description: Edge が Analytics 変数に自動的にマッピングする XDM フィールドを表示します。
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 83%

---

# Adobe Experience Edge での Analytics 変数のマッピング

次の表に、Adobe Experience Platform Edge Network が Adobe Analytics に自動的にマッピングする変数を示します。これらの XDM フィールドパスを使用する場合、Adobe Analyticsにデータを送信するための追加の設定は必要ありません。 これらのフィールドは、 **[!UICONTROL Adobe Analytics ExperienceEvent テンプレート]** フィールドグループを使用します。

このテーブルの以前の更新は、このページの [GitHub のコミット履歴](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/variable-mapping.md)で確認できます。

| XDM フィールドパス | Analytics のディメンションと説明 |
| --- | --- |
| `application.isClose` | モバイルのライフサイクル指標の定義に役立ちます [クラッシュ](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.isInstall` | モバイルのライフサイクル指標を増やすタイミングを判断するのに役立ちます [初回起動](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.isLaunch` | モバイルのライフサイクル指標を増やすタイミングを判断するのに役立ちます [初回起動](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.closeType` | 終了イベントがクラッシュであるかどうかを判断します。有効な値は `close`（ライフサイクルセッションが終了し、前のセッションで一時停止イベントを受け取った場合）、`unknown`（ライフサイクルセッションは一時停止イベントなしで終了する）です。モバイルのライフサイクル指標の設定に役立ちます [クラッシュ](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) 指標。 |
| `application.isInstall` | モバイルのライフサイクル指標 [インストール数](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.isLaunch` | モバイルのライフサイクル指標 [起動回数](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.name` | モバイルライフサイクルディメンションの設定に役立ちます [アプリ ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.isUpgrade` | モバイルのライフサイクル指標 [アップグレード](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.version` | モバイルライフサイクルディメンションの設定に役立ちます [アプリ ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `application.sessionLength` | モバイルのライフサイクル指標 [以前のセッションの長さ](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `commerce.checkouts.id` | [イベントのシリアル化](../vars/page-vars/events/event-serialization.md)を「[チェックアウト](../../components/metrics/checkouts.md)」指標に適用します。 |
| `commerce.checkouts.value` | 「[チェックアウト](../../components/metrics/checkouts.md)」指標を必要な量だけ増分します。 |
| `commerce.order.currencyCode` | [currencyCode](../vars/config-vars/currencycode.md) 設定変数を設定します。 |
| `commerce.order.purchaseID` | [purchaseID](../vars/page-vars/purchaseid.md) ページ変数を設定します。 |
| `commerce.order.payments[0].transactionID` | [transactionID](../vars/page-vars/transactionid.md) ページ変数を設定します。 |
| `commerce.productListAdds.id` | [イベントのシリアル化](../vars/page-vars/events/event-serialization.md)を「[買い物かごへの追加](../../components/metrics/cart-additions.md)」指標に適用します。 |
| `commerce.productListAdds.value` | 「[買い物かごへの追加件数](../../components/metrics/cart-additions.md)」指標を増分します。 |
| `commerce.productListOpens.id` | [イベントのシリアル化](../vars/page-vars/events/event-serialization.md)を「[買い物かご](../../components/metrics/carts.md)」指標に適用します。 |
| `commerce.productListOpens.value` | 「[買い物かご](../../components/metrics/carts.md)」指標を増分します。 |
| `commerce.productListRemovals.id` | [イベントのシリアル化](../vars/page-vars/events/event-serialization.md)を「[買い物かごからの削除件数](../../components/metrics/cart-removals.md)」指標に適用します。 |
| `commerce.productListRemovals.value` | 「[買い物かごからの削除件数](../../components/metrics/cart-removals.md)」指標を増分します。 |
| `commerce.productListViews.id` | [イベントのシリアル化](../vars/page-vars/events/event-serialization.md)を「[買い物かごの表示回数](../../components/metrics/cart-views.md)」指標に適用します。 |
| `commerce.productListViews.value` | 「[買い物かごの表示回数](../../components/metrics/cart-views.md)」指標を増分します。 |
| `commerce.productViews.id` | [イベントのシリアル化](../vars/page-vars/events/event-serialization.md)を「[製品表示回数](../../components/metrics/product-views.md)」指標に適用します。 |
| `commerce.productViews.value` | 「[製品表示回数](../../components/metrics/product-views.md)」指標を増分します。 |
| `commerce.purchases.value` | 「[注文件数](../../components/metrics/orders.md)」指標を増分します。 |
| `device.model` | モバイルライフサイクルディメンション [デバイス名](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `device.colorDepth` | 「[色深度](../../components/dimensions/color-depth.md)」ディメンションの設定に役立ちます。 |
| `device.screenHeight` | 「[画面の解像度](../../components/dimensions/monitor-resolution.md)」ディメンションの設定に役立ちます。 |
| `device.screenWidth` | 「[画面の解像度](../../components/dimensions/monitor-resolution.md)」ディメンションの設定に役立ちます。 |
| `device.type` | モバイルデバイスのタイプ。 |
| `environment.browserDetails.acceptLanguage` | [言語](../../components/dimensions/language.md)ディメンションの設定に役立ちます。 |
| `environment.browserDetails.cookiesEnabled` | [cookie サポート](../../components/dimensions/cookie-support.md)ディメンションを設定します。有効な値は `Y` （ブラウザーが cookie を受け入れる）および `N` （ブラウザーが cookie を拒否する）です。 |
| `environment.browserDetails.javaEnabled` | [Java 対応](../../components/dimensions/java-enabled.md)ディメンションを設定します。有効な値は `Y` (Java が有効) と `N` (Java が無効) です。 |
| `environment.browserDetails.userAgent` | フォールバックの[ユニーク訪問者](../../components/metrics/unique-visitors.md)識別方法として使用します。通常、`User-Agent` HTTP リクエストヘッダーを使用して生成します。このフィールドをレポートで使用する場合は、eVar にマッピングできます。 |
| `environment.browserDetails.viewportHeight` | [ブラウザーの高さ](../../components/dimensions/browser-height.md)ディメンションを設定します。 |
| `environment.browserDetails.viewportWidth` | [ブラウザーの幅](../../components/dimensions/browser-width.md)ディメンションを設定します。 |
| `environment.carrier` | モバイルライフサイクルディメンション [通信事業者名](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `environment.connectionType` | [接続タイプ](../../components/dimensions/connection-type.md)ディメンションの設定に役立ちます。 |
| `environment.ipV4` | フォールバックの[ユニーク訪問者](../../components/metrics/unique-visitors.md)識別方法として使用します。通常、`X-Forwarded-For` HTTP ヘッダーを使用して生成します。 |
| `environment.language` | モバイルディメンション「ロケール」。 |
| `environment.operatingSystem` | モバイルライフサイクルディメンション [オペレーティングシステム](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `environment.operatingSystemVersion` | モバイルライフサイクルディメンションの設定に役立ちます [オペレーティングシステムのバージョン](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | それぞれの [eVar](../../components/dimensions/evar.md) ディメンションを設定します。 |
| `_experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`_experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | それぞれの[階層](/help/components/dimensions/hierarchy.md)ディメンションを設定します。 |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | リスト prop の区切り文字の上書き。区切り文字はレポートスイート設定の[トラフィック変数管理](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)から自動的に取得されるので、このフィールドの使用はお勧めしません。このフィールドを使用すると、使用される区切り文字と Analytics が想定する区切り文字との間に不一致が発生する可能性があります。 |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | それぞれの[リスト prop](../vars/page-vars/prop.md#list-props) 値を含む文字列配列。 |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | それぞれの `value` 配列内のすべての `list[]` 文字列をそれぞれの[リスト変数](../vars/page-vars/list.md)に連結します。区切り文字は、[レポートスイート設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)で設定された値に基づいて自動的に選択されます。 |
| `_experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | それぞれの [prop](../../components/dimensions/prop.md) ディメンションを設定します。 |
| `_experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | 適用 [イベントのシリアル化](../vars/page-vars/events/event-serialization.md) それぞれの [カスタムイベント](../../components/metrics/custom-events.md) 指標。 各イベント ID は、100 グループの親に存在します。 例えば、にシリアル化を適用するには、次のようにします。 `event678`，使用 `_experience.analytics.event601to700.event678.id`. |
| `_experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | それぞれ [カスタムイベント](../../components/metrics/custom-events.md) 指標を必要な量で絞り込みます。 各イベントは、100 グループの親に存在します。 例えば、 `event567` 次に該当 `_experience.analytics.event501to600.event567.value`. |
| `identityMap.ECID[0].id` | [Adobe Experience Cloud ID サービスの ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)。 |
| `marketing.trackingCode` | [トラッキングコード](../../components/dimensions/tracking-code.md)ディメンションを設定します。 |
| `media.mediaTimed.completes.value` | Media Analytics 指標「[コンテンツ完了](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-complete)」。 |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`、`c.a.media.timePlayed`、`c.a.media.play` |
| `media.mediaTimed.federated.value` | Media Analytics 指標「[Federated Data](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#federated-data)」。 |
| `media.mediaTimed.firstQuartiles.value` | Media Analytics 指標「[25％進捗マーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#twenty-five-progress-marker)」。 |
| `media.mediaTimed.mediaSegmentView.value` | Media Analytics 指標「[コンテンツセグメント閲覧回数](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-segment-views)」。 |
| `media.mediaTimed.midpoints.value` | Media Analytics 指標「[50％進捗マーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#fifty-progress-marker)」。 |
| `media.mediaTimed.pauseTime.value` | Media Analytics 指標「[一時停止時間合計](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#total-pause-duration)」。 |
| `media.mediaTimed.pauses.value` | Media Analytics 指標「[一時停止イベント](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#pause-events)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | Media Analytics ディメンション「[アセット ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#asset-id)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Media Analytics ディメンション「[ビデオ名](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#video-name)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Media Analytics ディメンション「[作成者](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#originator)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Media Analytics ディメンション「[エピソード](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#episode)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Media Analytics ディメンション「[ジャンル](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#genre)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Media Analytics ディメンション「[コンテンツ評価](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-rating)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Media Analytics ディメンション「[シーズン](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#season)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Media Analytics ディメンション「[コンテンツ ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-id)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Media Analytics ディメンション「[表示](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#show)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | Media Analytics ディメンション「[タイプ表示](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#show-type)」。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Media Analytics ディメンション「[ビデオの長さ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#video-length)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Media Analytics ディメンション「[メディアセッション ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#media-session-id)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Media Analytics ディメンション「[コンテンツチャネル](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-channel)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Media Analytics ディメンション「[コンテンツタイプ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-type)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Media Analytics ディメンション「[ネットワーク](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#network)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Media Analytics ディメンション「[コンテンツセグメント](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-segment)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Media Analytics ディメンション「[コンテンツプレイヤー名](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-player-name)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Media Analytics ディメンション「[SDK のバージョン](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#sdk-version)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Media Analytics ディメンション「[メディアフィードのタイプ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#media-feed-type)」。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Media Analytics ディメンション「[ストリーム形式](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#stream-format)」。 |
| `media.mediaTimed.progress10.value` | Media Analytics 指標「[10％進捗マーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#ten-progress-marker)」。 |
| `media.mediaTimed.progress95.value` | Media Analytics 指標「[95％進捗マーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#ninety-five-progress-marker)」。 |
| `media.mediaTimed.resumes.value` | Media Analytics 指標「[コンテンツ再開](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-resumes)」。 |
| `media.mediaTimed.starts.value` | Media Analytics 指標「[メディア開始](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#media-starts)」。 |
| `media.mediaTimed.thirdQuartiles.value` | Media Analytics 指標「[75％進捗マーカー](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#seventy-five-progress-marker)」。 |
| `media.mediaTimed.timePlayed.value` | Media Analytics 指標「[コンテンツ滞在時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#content-time-spent)」。 |
| `media.mediaTimed.totalTimePlayed.value` | Media Analytics 指標「[メディア閲覧時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=ja#media-time-spent)」。 |
| `placeContext.geo._schema.latitude` | Mobile ディメンション「緯度」。 |
| `placeContext.geo._schema.longitude` | モバイルディメンション「経度」。 |
| `placeContext.geo.postalCode` | 「[郵便番号](../../components/dimensions/zip-code.md)」ディメンション。 |
| `placeContext.geo.stateProvince` | 「[米国の州](../../components/dimensions/us-states.md)」ディメンション。 |
| `placeContext.localTime` | [データフィード](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)では `t_time_info` として表示されます。 |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | eVars に [product 構文](../vars/page-vars/products.md)マーチャンダイジングを適用します。 |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | イベントに [product 構文](../vars/page-vars/products.md)マーチャンダイジングを適用します。 |
| `productListItems[].productCategories[].categoryID` | 「[カテゴリ](../../components/dimensions/category.md)」ディメンション。[product](../vars/page-vars/products.md) ページ変数も参照してください。 |
| `productListItems[].name` | 「[製品](../../components/dimensions/product.md)」ディメンション。[product](../vars/page-vars/products.md) ページ変数も参照してください。`productListItems[].SKU` と `productListItems[].name` の両方にデータが含まれている場合、`productListItems[].SKU` の値が使用されます。 |
| `productListItems[].priceTotal` | 「[売上高](../../components/metrics/revenue.md)」指標を判断するのに役立ちます。[product](../vars/page-vars/products.md) ページ変数も参照してください。 |
| `productListItems[].quantity` | 「[単位](../../components/metrics/units.md)」指標を判断するのに役立ちます。[product](../vars/page-vars/products.md) ページ変数も参照してください。 |
| `productListItems[].SKU` | 「[製品](../../components/dimensions/product.md)」ディメンション。[product](../vars/page-vars/products.md) ページ変数も参照してください。`productListItems[].SKU` と `productListItems[].name` の両方にデータが含まれている場合、`productListItems[].SKU` の値が使用されます。 |
| `web.webInteraction.URL` | [linkURL](../vars/config-vars/linkurl.md) 実装変数。 |
| `web.webInteraction.name` | [カスタムリンク](../../components/dimensions/custom-link.md)、[ダウンロードリンク](../../components/dimensions/download-link.md)、または[離脱リンク](../../components/dimensions/exit-link.md)ディメンション（`web.webInteraction.type` の値によって異なります）。 |
| `web.webInteraction.type` | クリックされたリンクのタイプを判断します。有効な値は `other`（カスタムリンク）、`download`（ダウンロードリンク）、`exit`（離脱リンク）です。 |
| `web.webPageDetails.URL` | 「[ページ URL](../../components/dimensions/page-url.md)」ディメンション。 |
| `web.webPageDetails.isErrorPage` | 「ページが見つかりませんでした」[ディメンション](../../components/dimensions/pages-not-found.md)および[指標](../../components/metrics/pages-not-found.md)を判断するのに役立つフラグ。 |
| `web.webPageDetails.name` | 「[ページ](../../components/dimensions/page.md)」ディメンション。 |
| `web.webPageDetails.server` | 「[サーバー](../../components/dimensions/server.md)」ディメンション。 |
| `web.webPageDetails.siteSection` | 「[サイトセクション](../../components/dimensions/site-section.md)」ディメンション。 |
| `web.webReferrer.URL` | 「[リファラー](../../components/dimensions/referrer.md)」ディメンション。 |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## 他の XDM フィールドを Analytics 変数にマッピングする

Adobe Analytics に追加するディメンションまたは指標がある場合は、[コンテキストデータ変数](../vars/page-vars/contextdata.md)を通じて行うことができます。自動的にマッピングされない XDM フィールド要素は、接頭辞 a.x を持つコンテキストデータとして Adobe Analytics に送信されます。その後、[処理ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=ja)を使用すると、このコンテキストデータ変数を目的の Analytics 変数にマップできます。例えば、次のイベントを送信した場合：

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

Web SDK は、そのデータをコンテキストデータ変数 `a.x._atag.search.term` として Adobe Analytics に送信します。その後、処理ルールを使用して、そのコンテキスト eVar 変数値を目的の Analytics 変数（データなど）に割り当てることができます。

![検索語句の処理ルール](assets/examplerule.png)
