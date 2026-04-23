---
title: Analytics のディメンションの互換性
description: Analytics のディメンションおよびレポートに関するリファレンス。
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 53%

---

# Analytics のディメンションの互換性

このページには、それぞれのAnalytics機能でサポートされている[&#x200B; ディメンション &#x200B;](overview.md)が一覧表示されます。

>[!NOTE]
>
>カスタム変数名、分類、訪問者属性は、このリストには含まれません。これらのディメンション項目は、個々のレポートスイートに固有の値です。

## Analysis Workspaceでサポートされるディメンション

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|---|---|
| Analytics for Target | `targetraw` |
| オーディエンス ID | `mcaudiences` |
| [ブラウザー](browser.md) | `browser` |
| [ブラウザータイプ](browser-type.md) | `browsertype` |
| [カテゴリ](category.md) | `category` |
| [市区町村](cities.md) | `geocity` |
| [画面の色](color-depth.md) | `colordepth` |
| [接続のタイプ](connection-type.md) | `connectiontype` |
| [Cookie サポート &#x200B;](cookie-support.md) | `cookie` |
| [国](countries.md) | `geocountry` |
| [顧客の忠誠度](customer-loyalty.md) | `customerloyalty` |
| [&#x200B; カスタムコンバージョン変数](evar.md) | `evar1`, `evar2`, etc. |
| [Custom Insight Vars](prop.md) | `prop1`, `prop2`, etc. |
| [カスタムリンク](custom-link.md) | `customlink` |
| [初回購入までの日数](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [前回購入からの日数](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [ドメイン](domain.md) | `filtereddomain` |
| [&#x200B; ダウンロードリンク &#x200B;](download-link.md) | `downloadlink` |
| [入口ページ &#x200B;](entry-dimensions.md) | `entrypage` |
| [入口ページのオリジナル &#x200B;](entry-dimensions.md) | `entrypageoriginal` |
| [&#x200B; リンクを終了](exit-link.md) | `exitlink` |
| [&#x200B; ファーストタッチチャネル &#x200B;](first-touch-channel.md) | `firsttouchchannel` |
| [&#x200B; ファーストタッチチャネルの詳細](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java 有効](java-enabled.md) | `javaenabled` |
| [言語](language.md) | `language` |
| [最後のタッチチャネル &#x200B;](last-touch-channel.md) | `lasttouchchannel` |
| [&#x200B; ラストタッチチャネルの詳細](last-touch-detail.md) | `lasttouchchanneldetail` |
| リスト変数 | `listvariables` |
| [&#x200B; マーケティングチャネル &#x200B;](marketing-channel.md) | `marketingchannel` |
| [&#x200B; モバイルオーディオサポート &#x200B;](mobile-dimensions.md) | `mobileaudiosupport` |
| [携帯電話会社](mobile-dimensions.md) | `mobilecarrier` |
| [&#x200B; モバイル色深度](mobile-dimensions.md) | `mobilecolordepth` |
| [&#x200B; モバイル Cookie サポート &#x200B;](mobile-dimensions.md) | `mobilecookiesupport` |
| [&#x200B; モバイルデバイス &#x200B;](mobile-dimensions.md) | `mobiledevicename` |
| [&#x200B; モバイルデバイスタイプ &#x200B;](mobile-dimensions.md) | `mobiledevicetype` |
| [&#x200B; モバイルのメールの最大長](mobile-dimensions.md) | `mobileemaillength` |
| [&#x200B; モバイル画像サポート &#x200B;](mobile-dimensions.md) | `mobileimagesupport` |
| [&#x200B; モバイルメーカー](mobile-dimensions.md) | `mobilemanufacturer` |
| [&#x200B; モバイル オペレーティング システム （非推奨） &#x200B;](mobile-dimensions.md) | `mobileos` |
| [&#x200B; モバイル画面の高さ](mobile-dimensions.md) | `mobilescreenheight` |
| [&#x200B; モバイル画面サイズ &#x200B;](mobile-dimensions.md) | `mobilescreensize` |
| [&#x200B; モバイル画面の幅](mobile-dimensions.md) | `mobilescreenwidth` |
| [&#x200B; モバイル最大ブラウザーURL長](mobile-dimensions.md) | `mobileurllength` |
| [&#x200B; モバイルビデオのサポート &#x200B;](mobile-dimensions.md) | `mobilevideosupport` |
| [画面の解像度](monitor-resolution.md) | `monitorresolution` |
| [オペレーティングシステム](operating-systems.md) | `operatingsystem` |
| [元の参照ドメイン &#x200B;](original-referring-domain.md) | `referringdomainoriginal` |
| [ページ](page.md) | `page` |
| [エラーページ (404)](pages-not-found.md) | `pagesnotfound` |
| [製品](product.md) | `product` |
| [リファラー](referrer.md) | `referrer` |
| [リファラータイプ](referrer-type.md) | `referrertype` |
| [参照ドメイン](referring-domain.md) | `referringdomain` |
| [地域](regions.md) | `georegion` |
| [再来訪頻度](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [検索エンジン](search-engine.md) | `searchengine` |
| [検索キーワード](search-keyword.md) | `searchenginekeyword` |
| [検索エンジン – ナチュラル &#x200B;](search-engine.md) | `searchenginenatural` |
| [検索エンジン – 有料](search-engine.md) | `searchenginepaid` |
| [検索キーワード – ナチュラル &#x200B;](search-keyword.md) | `searchenginenaturalkeyword` |
| [検索キーワード – 有料](search-keyword.md) | `searchenginepaidkeyword` |
| [すべての検索ページのランク &#x200B;](all-search-page-rank.md) | `searchenginepagerank` |
| [サーバー](server.md) | `server` |
| [直帰数](single-page-visits.md) | `singlepagevisits` |
| [&#x200B; サイトセクション &#x200B;](site-section.md) | `sitesections` |
| [1訪問あたりの滞在時間 – 詳細](time-spent-per-visit.md) | `sitetime` |
| [トラッキングコード](tracking-code.md) | `campaign` |
| [米国 DMA](us-dma.md) | `geodma` |
| [米国](us-states.md) | `state` |
| [イベント前の時間](time-prior-to-event.md) | `timeprior` |
| [訪問当たりの滞在時間 – バケット化](time-spent-per-visit.md) | `timespent` |
| [訪問の深さ](visit-depth.md) | `pathlength` |
| [訪問回数](visit-number.md) | `visitnumber` |
| [郵便番号](zip-code.md) | `zip` |
| [AM / PM](am-pm.md) | `timepartampm` |
| [&#x200B; ブラウザーの高さ – バケット化](browser-height.md) | `browserheightbucketed` |
| [&#x200B; ブラウザー幅 – バケット化](browser-width.md) | `browserwidthbucketed` |
| [日](day.md) | `daterangeday` |
| [月間通算日](day-of-month.md) | `timepartdayofmonth` |
| [曜日](day-of-week.md) | `dayofweek` |
| [曜日](day-of-week.md) | `timepartdayofweek` |
| [年間通算日](day-of-year.md) | `timepartdayofyear` |
| [最終訪問からの日数](days-since-last-visit.md) | `dayssincelastvisit` |
| [&#x200B; カスタムインサイトの入力](entry-dimensions.md) | `entryprops` |
| [&#x200B; エントリリスト変数](entry-dimensions.md) | `entrylistvariables` |
| [&#x200B; エントリサーバー](entry-dimensions.md) | `entryserver` |
| [入口サイトセクション &#x200B;](entry-dimensions.md) | `entrysitesections` |
| [&#x200B; カスタムインサイトを終了](exit-dimensions.md) | `exitprops` |
| [&#x200B; リスト変数を終了](exit-dimensions.md) | `exitlistvariables` |
| [&#x200B; ページを終了](exit-dimensions.md) | `exitpage` |
| [&#x200B; サーバーを終了](exit-dimensions.md) | `exitserver` |
| [&#x200B; サイトセクションを終了](exit-dimensions.md) | `exitsitesections` |
| [&#x200B; ヒット深度](hit-depth.md) | `hitdepth` |
| [ヒットタイプ](hit-type.md) | `hittype` |
| [時間](hour.md) | `daterangehour` |
| [時間帯](hour-of-day.md) | `timeparthourofday` |
| [&#x200B; マーケティングチャネルの詳細](marketing-detail.md) | `marketingchanneldetail` |
| [分](minute.md) | `daterangeminute` |
| [&#x200B; モバイル最大ブックマーク長](mobile-dimensions.md) | `mobilebookmarklength` |
| [&#x200B; モバイルデバイス番号](mobile-dimensions.md) | `mobiledevicenumber` |
| [&#x200B; モバイル DRM](mobile-dimensions.md) | `mobiledrm` |
| [&#x200B; モバイル インフォメーション サービス &#x200B;](mobile-dimensions.md) | `mobileinformationservices` |
| [&#x200B; モバイル Java VM](mobile-dimensions.md) | `mobilejavavm` |
| [&#x200B; モバイルメールの装飾](mobile-dimensions.md) | `mobilemaildecoration` |
| [&#x200B; モバイルネットプロトコル &#x200B;](mobile-dimensions.md) | `mobilenetprotocols` |
| [&#x200B; モバイルプッシュ通知](mobile-dimensions.md) | `mobilepushtotalk` |
| [月](month.md) | `daterangemonth` |
| [年間通算月](month-of-year.md) | `timepartmonthofyear` |
| [オペレーティングシステムの種類](operating-system-types.md) | `operatingsystemgroup` |
| [有料検索](paid-search.md) | `paidsearch` |
| [永続的なCookie サポート &#x200B;](persistent-cookie-support.md) | `persistentcookie` |
| [四半期](quarter.md) | `daterangequarter` |
| [四半期](quarter-of-year.md) | `timepartquarterofyear` |
| 調査 | `surveybase` |
| [&#x200B; ページ滞在時間 – バケット化](time-spent-on-page.md) | `averagepagetime` |
| [&#x200B; ページ滞在時間 – 詳細](time-spent-on-page.md) | `pagetimeseconds` |
| [&#x200B; オプトアウトのトラッキング理由](tracking-opt-out-reason.md) | `optoutreason` |
| [平日/週末](weekday-weekend.md) | `timepartweekdayweekend` |
| [週](week.md) | `daterangeweek` |
| [年](year.md) | `daterangeyear` |

## Analysis Workspace のみでサポートされているコンテンツに応じたディメンション

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| ACTIVITY MAP XY | `clickmapxy` |
| メディアセッション ID | `videosessionid` |
| Nielsen アクセス方法 | `nielsenaccmethod` |
| Nielsen アプリ ID | `nielsenappid` |
| Nielsen チャネルアセット | `nielsenchannelasset` |
| Nielsen コンテンツタイプ | `nielsencontenttype` |

## Analysis Workspaceがサポートするコンテンツ対応ディメンション

### 動画（ストリーミングメディアサービス）

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| [コンテンツ](sm-core.md) | `video` |
| [&#x200B; コンテンツセグメント &#x200B;](sm-core.md) | `videosegment` |
| [&#x200B; コンテンツの種類](sm-core.md) | `videocontenttype` |
| [広告プレイヤー名](sm-ads.md) | `videoadplayername` |
| ポッド位置[の](sm-ads.md)広告 | `videoadinpod` |
| [削除されたフレーム &#x200B;](sm-quality.md) | `videoqoedroppedframecountevar` |
| [エラー](sm-quality.md) | `videoqoeerrorcountevar` |
| [平均ビットレート &#x200B;](sm-quality.md) | `videoqoebitrateaverageevar` |
| [&#x200B; ビットレートの変更](sm-quality.md) | `videoqoebitratechangecountevar` |
| [合計バッファー期間](sm-quality.md) | `videoqoebuffertimeevar` |
| [&#x200B; バッファーイベント &#x200B;](sm-quality.md) | `videoqoebuffercountevar` |
| [開始までの時間](sm-quality.md) | `videoqoetimetostartevar` |
| [広告ポッド &#x200B;](sm-ads.md) | `videoadpod` |
| [&#x200B; メディアパス &#x200B;](sm-core.md) | `videopath` |
| [Ad](sm-ads.md) | `videoad` |
| [&#x200B; コンテンツプレーヤー名](sm-core.md) | `videoplayername` |
| [&#x200B; コンテンツチャネル &#x200B;](sm-core.md) | `videochannel` |
| [章](sm-chapters.md) | `videochapter` |
| [&#x200B; コンテンツ名（変数） &#x200B;](sm-core.md) | `videoname` |
| [&#x200B; コンテンツの長さ（変数） &#x200B;](sm-core.md) | `videolength` |
| [広告名（変数） &#x200B;](sm-ads.md) | `videoadname` |
| [広告の長さ（変数） &#x200B;](sm-ads.md) | `videoadlength` |
| [表示](sm-video-metadata.md) | `videoshow` |
| [&#x200B; シーズン &#x200B;](sm-video-metadata.md) | `videoseason` |
| [&#x200B; エピソード &#x200B;](sm-video-metadata.md) | `videoepisode` |
| [ネットワーク](sm-video-metadata.md) | `videonetwork` |
| [&#x200B; タイプを表示](sm-video-metadata.md) | `videoshowtype` |
| [広告読み込み](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [日パート &#x200B;](sm-video-metadata.md) | `videodaypart` |
| [広告主](sm-ads.md) | `videoadadvertiser` |
| [キャンペーン ID](sm-ads.md) | `videoadcampaign` |
| [&#x200B; ジャンル &#x200B;](sm-video-metadata.md) | `videogenre` |
| [&#x200B; ストリームタイプ &#x200B;](sm-core.md) | `videostreamtype` |
| [Player SDK エラーID](sm-quality.md) | `videoqoeplayersdkerrors` |
| [外部エラーID](sm-quality.md) | `videoqoeextneralerrors` |
| [&#x200B; メディアフィードの種類](sm-video-metadata.md) | `videofeedtype` |
| [&#x200B; エントリメディアパス &#x200B;](entry-dimensions.md) | `entryvideopath` |
| [&#x200B; メディアパスを終了](exit-dimensions.md) | `exitvideopath` |
| [&#x200B; エントリジャンル &#x200B;](entry-dimensions.md) | `entryvideogenre` |
| [&#x200B; ジャンルを終了](exit-dimensions.md) | `exitvideogenre` |
| [Entry Player SDK エラーID](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [&#x200B; プレイヤーの終了SDK エラーID](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [&#x200B; エントリ外部エラーID](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [外部エラーIDを終了](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Socialは引退しました。

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| 条件 | `socialterm` |
| Social プラットフォーム／プロパティ | `socialcontentprovider` |
| 発言者 | `socialauthor` |
| 言語 | `sociallanguage` |
| 緯度 / 経度 | `sociallatlong` |
| トラッキングコード | `socialassettrackingcode` |
| 所有ソーシャルプロパティ | `socialaccountandappids` |
| 所有投稿 ID | `socialownedpostids` |
| 所有ソーシャル定義 | `socialinteractiontype` |
| 所有プロパティ ID | `socialownedpropertyid` |
| 所有プロパティとアプリケーション | `socialownedpropertypropertyvsapp` |
| 所有プロパティ名 | `socialownedpropertyname` |
| 所有定義プロパティと投稿 | `socialowneddefinitionpropertyvspost` |
| 所有定義インサイトの種類 | `socialowneddefinitioninsighttype` |
| 所有定義インサイト値 | `socialowneddefinitioninsightvalue` |
| 所有定義指標 | `socialowneddefinitionmetric` |
| アセット | `socialmediaid` |

### モバイル SDK

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| [初回起動日](lifecycle-dimensions.md) | `mobileinstalldate` |
| [&#x200B; アプリ ID](lifecycle-dimensions.md) | `mobileappid` |
| [起動回数](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [初回使用からの日数](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [前回使用からの日数](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [時間帯（SDK） &#x200B;](lifecycle-dimensions.md) | `mobilehourofday` |
| [曜日（SDK） &#x200B;](lifecycle-dimensions.md) | `mobiledayofweek` |
| [&#x200B; オペレーティングシステム （SDK） &#x200B;](lifecycle-dimensions.md) | `mobileosenvironment` |
| [前回アップグレードからの日数](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [前回アップグレードからの起動回数](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [&#x200B; デバイス名（SDK） &#x200B;](lifecycle-dimensions.md) | `mobiledevice` |
| [&#x200B; オペレーティングシステムのバージョン（SDK） &#x200B;](lifecycle-dimensions.md) | `mobileosversion` |
| [&#x200B; ビーコン メジャー](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [&#x200B; ビーコン マイナー](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [&#x200B; ビーコン UUID](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [&#x200B; ビーコン近接](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [ロケーション（半径 10 km 以内）](lifecycle-dimensions.md) | `latlon1` |
| [ロケーション（半径 100 m 以内）](lifecycle-dimensions.md) | `latlon23` |
| [ロケーション（半径 1 m 以内）](lifecycle-dimensions.md) | `latlon45` |
| [目標点名](lifecycle-dimensions.md) | `pointofinterest` |
| [目標地点の中心までの距離](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [場所の精度](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [&#x200B; カテゴリを配置](lifecycle-dimensions.md) | `mobileplacecategory` |
| [&#x200B; プレース ID](lifecycle-dimensions.md) | `mobileplaceid` |
| [&#x200B; エントリビーコンのメジャー](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [&#x200B; ビーコン メジャーを終了](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [&#x200B; エントリ ビーコン マイナー](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [小ビーコンを終了](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [&#x200B; エントリビーコン UUID](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [&#x200B; ビーコン UUIDを終了](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [&#x200B; エントリビーコン近接](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [&#x200B; ビーコン近接を終了](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| AMO ID | `amo_cid` |

### Activity Map

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| [Activity Map 地域別リンク](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Activity Map 地域](activity-map-region.md) | `clickmapregion` |
| [Activity Map リンク](activity-map-link.md) | `clickmaplink` |
| [Activity Map ページ](activity-map-page.md) | `clickmappage` |

### Nielsen 統合

この統合を実装する方法について詳しくは、Adobe Exchangeの[Nielsen拡張機能](https://exchange.adobe.com/apps/ec/101361)を参照してください。

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| Nielsen Ad Model | `nielsenadmodel` |
| Nielsen セグメント C | `nielsensegmentc` |
| Nielsen セグメント B | `nielsensegmentb` |
| Nielsen セグメント A | `nielsensegmenta` |
| Nielsen コンテンツ ID | `nielsencontentid` |
| Nielsen Asset / Program | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Nielsen オプトアウト | `nielsenoptout` |
| Nielsen クライアント ID + VCID | `nielsenclientidvcid` |
| Nielsen クライアント ID | `nielsenclientid` |
| 入口 Nielsen オプトアウト | `entrynielsenoptout` |
| 出口 Nielsen オプトアウト | `exitnielsenoptout` |
| 入口 Nielsen クライアント ID + VCID | `entrynielsenclientidvcid` |
| 出口 Nielsen クライアント ID + VCID | `exitnielsenclientidvcid` |
| 入口 Nielsen クライアント ID | `entrynielsenclientid` |
| 出口 Nielsen クライアント ID | `exitnielsenclientid` |

### Adobe Experience Manager（AEM）

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| アセット ID | `aemassetid` |
| アセットソース | `aemassetsource` |
| クリックされたアセット ID | `aemclickedassetid` |
| 入口アセット ID | `entryaemassetid` |
| 出口アセット ID | `exitaemassetid` |

### Adobe Campaign

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| Adobe Campaignが実行した配信ID | `ac_delivery_internal_name` |
