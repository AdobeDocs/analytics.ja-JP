---
title: Analytics のディメンションの互換性
description: Analytics のディメンションおよびレポートに関するリファレンス。
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 60%

---

# Analytics のディメンションの互換性

このページには、それぞれの Analytics 機能でサポートされている [&#x200B; ディメンション &#x200B;](overview.md) が一覧表示されます。

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
| [&#x200B; カスタムコンバージョン変数 &#x200B;](evar.md) | `evar1`, `evar2`, etc. |
| [Custom Insight変数 &#x200B;](prop.md) | `prop1`, `prop2`, etc. |
| [カスタムリンク](custom-link.md) | `customlink` |
| [初回購入までの日数](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [前回購入からの日数](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [ドメイン](domain.md) | `filtereddomain` |
| [&#x200B; ダウンロードリンク &#x200B;](download-link.md) | `downloadlink` |
| [&#x200B; 入口ページ &#x200B;](entry-dimensions.md) | `entrypage` |
| [&#x200B; オリジナルの入口ページ &#x200B;](entry-dimensions.md) | `entrypageoriginal` |
| [&#x200B; 離脱リンク &#x200B;](exit-link.md) | `exitlink` |
| [&#x200B; ファーストタッチチャネル &#x200B;](first-touch-channel.md) | `firsttouchchannel` |
| [&#x200B; ファーストタッチチャネルの詳細 &#x200B;](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java 有効](java-enabled.md) | `javaenabled` |
| [言語](language.md) | `language` |
| [&#x200B; ラストタッチチャネル &#x200B;](last-touch-channel.md) | `lasttouchchannel` |
| [&#x200B; ラストタッチチャネルの詳細 &#x200B;](last-touch-detail.md) | `lasttouchchanneldetail` |
| リスト変数 | `listvariables` |
| [&#x200B; マーケティングチャネル &#x200B;](marketing-channel.md) | `marketingchannel` |
| [&#x200B; モバイルオーディオのサポート &#x200B;](mobile-dimensions.md) | `mobileaudiosupport` |
| [携帯電話会社](mobile-dimensions.md) | `mobilecarrier` |
| [&#x200B; モバイルの色深度 &#x200B;](mobile-dimensions.md) | `mobilecolordepth` |
| [&#x200B; モバイル Cookie サポート &#x200B;](mobile-dimensions.md) | `mobilecookiesupport` |
| [&#x200B; モバイルデバイス &#x200B;](mobile-dimensions.md) | `mobiledevicename` |
| [&#x200B; モバイルデバイスタイプ &#x200B;](mobile-dimensions.md) | `mobiledevicetype` |
| [&#x200B; モバイルの最大メール長 &#x200B;](mobile-dimensions.md) | `mobileemaillength` |
| [&#x200B; モバイル画像のサポート &#x200B;](mobile-dimensions.md) | `mobileimagesupport` |
| [&#x200B; モバイル製造元 &#x200B;](mobile-dimensions.md) | `mobilemanufacturer` |
| [&#x200B; モバイルオペレーティングシステム（非推奨） &#x200B;](mobile-dimensions.md) | `mobileos` |
| [&#x200B; モバイルの画面の高さ &#x200B;](mobile-dimensions.md) | `mobilescreenheight` |
| [&#x200B; モバイルの画面サイズ &#x200B;](mobile-dimensions.md) | `mobilescreensize` |
| [&#x200B; モバイルの画面の幅 &#x200B;](mobile-dimensions.md) | `mobilescreenwidth` |
| [&#x200B; モバイルのブラウザー URL の最大長 &#x200B;](mobile-dimensions.md) | `mobileurllength` |
| [&#x200B; モバイルビデオのサポート &#x200B;](mobile-dimensions.md) | `mobilevideosupport` |
| [画面の解像度](monitor-resolution.md) | `monitorresolution` |
| [オペレーティングシステム](operating-systems.md) | `operatingsystem` |
| [&#x200B; オリジナルの参照ドメイン &#x200B;](original-referring-domain.md) | `referringdomainoriginal` |
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
| [&#x200B; 検索エンジン – 自然 &#x200B;](search-engine.md) | `searchenginenatural` |
| [&#x200B; 検索エンジン – 有料 &#x200B;](search-engine.md) | `searchenginepaid` |
| [&#x200B; 検索キーワード – 自然 &#x200B;](search-keyword.md) | `searchenginenaturalkeyword` |
| [&#x200B; 検索キーワード – 有料 &#x200B;](search-keyword.md) | `searchenginepaidkeyword` |
| [&#x200B; すべての検索ページのランク &#x200B;](all-search-page-rank.md) | `searchenginepagerank` |
| [サーバー](server.md) | `server` |
| [直帰数](single-page-visits.md) | `singlepagevisits` |
| [サイトセクション](site-section.md) | `sitesections` |
| [&#x200B; 訪問あたりの滞在時間 – 詳細 &#x200B;](time-spent-per-visit.md) | `sitetime` |
| [トラッキングコード](tracking-code.md) | `campaign` |
| [米国 DMA](us-dma.md) | `geodma` |
| [&#x200B; 米国の州 &#x200B;](us-states.md) | `state` |
| [イベント前の時間](time-prior-to-event.md) | `timeprior` |
| [&#x200B; 訪問あたりの滞在時間 – バケット化 &#x200B;](time-spent-per-visit.md) | `timespent` |
| [&#x200B; 訪問の深度 &#x200B;](visit-depth.md) | `pathlength` |
| [訪問回数](visit-number.md) | `visitnumber` |
| [郵便番号](zip-code.md) | `zip` |
| [&#x200B; 午前/午後 &#x200B;](am-pm.md) | `timepartampm` |
| [&#x200B; ブラウザーの高さ – バケット化 &#x200B;](browser-height.md) | `browserheightbucketed` |
| [&#x200B; ブラウザーの幅 – バケット化 &#x200B;](browser-width.md) | `browserwidthbucketed` |
| [日](day.md) | `daterangeday` |
| [月間通算日](day-of-month.md) | `timepartdayofmonth` |
| [曜日](day-of-week.md) | `dayofweek` |
| [曜日](day-of-week.md) | `timepartdayofweek` |
| [年間通算日](day-of-year.md) | `timepartdayofyear` |
| [最終訪問からの日数](days-since-last-visit.md) | `dayssincelastvisit` |
| [&#x200B; 入口カスタムインサイト &#x200B;](entry-dimensions.md) | `entryprops` |
| [&#x200B; 入口リスト変数 &#x200B;](entry-dimensions.md) | `entrylistvariables` |
| [&#x200B; 入口サーバー &#x200B;](entry-dimensions.md) | `entryserver` |
| [&#x200B; 立ち入りサイトセクション &#x200B;](entry-dimensions.md) | `entrysitesections` |
| [&#x200B; カスタムインサイトの終了 &#x200B;](exit-dimensions.md) | `exitprops` |
| [&#x200B; 終了リスト変数 &#x200B;](exit-dimensions.md) | `exitlistvariables` |
| [&#x200B; 出口ページ &#x200B;](exit-dimensions.md) | `exitpage` |
| [&#x200B; サーバーを終了 &#x200B;](exit-dimensions.md) | `exitserver` |
| [&#x200B; 出口サイトセクション &#x200B;](exit-dimensions.md) | `exitsitesections` |
| [&#x200B; ヒットの深度 &#x200B;](hit-depth.md) | `hitdepth` |
| [ヒットタイプ](hit-type.md) | `hittype` |
| [時間](hour.md) | `daterangehour` |
| [時間帯](hour-of-day.md) | `timeparthourofday` |
| [&#x200B; マーケティングチャネルの詳細 &#x200B;](marketing-detail.md) | `marketingchanneldetail` |
| [分](minute.md) | `daterangeminute` |
| [&#x200B; モバイルの最大ブックマーク長 &#x200B;](mobile-dimensions.md) | `mobilebookmarklength` |
| [&#x200B; モバイルデバイス番号 &#x200B;](mobile-dimensions.md) | `mobiledevicenumber` |
| [&#x200B; モバイル DRM](mobile-dimensions.md) | `mobiledrm` |
| [&#x200B; モバイル情報サービス &#x200B;](mobile-dimensions.md) | `mobileinformationservices` |
| [&#x200B; モバイル Java VM](mobile-dimensions.md) | `mobilejavavm` |
| [&#x200B; モバイルメールの装飾 &#x200B;](mobile-dimensions.md) | `mobilemaildecoration` |
| [Mobile Net プロトコル &#x200B;](mobile-dimensions.md) | `mobilenetprotocols` |
| [&#x200B; モバイルプッシュ通知 &#x200B;](mobile-dimensions.md) | `mobilepushtotalk` |
| [月](month.md) | `daterangemonth` |
| [年間通算月](month-of-year.md) | `timepartmonthofyear` |
| [オペレーティングシステムの種類](operating-system-types.md) | `operatingsystemgroup` |
| [有料検索](paid-search.md) | `paidsearch` |
| [&#x200B; 永続的な Cookie のサポート &#x200B;](persistent-cookie-support.md) | `persistentcookie` |
| [四半期](quarter.md) | `daterangequarter` |
| [四半期](quarter-of-year.md) | `timepartquarterofyear` |
| 調査 | `surveybase` |
| [&#x200B; ページでの滞在時間 – バケット化 &#x200B;](time-spent-on-page.md) | `averagepagetime` |
| [&#x200B; ページでの滞在時間 – 詳細 &#x200B;](time-spent-on-page.md) | `pagetimeseconds` |
| [&#x200B; トラッキングオプトアウト理由 &#x200B;](tracking-opt-out-reason.md) | `optoutreason` |
| [&#x200B; 平日/週末 &#x200B;](weekday-weekend.md) | `timepartweekdayweekend` |
| [週](week.md) | `daterangeweek` |
| [年](year.md) | `daterangeyear` |

## Analysis Workspace のみでサポートされているコンテンツに応じたディメンション

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| メディアセッション ID | `videosessionid` |
| Nielsen アクセス方法 | `nielsenaccmethod` |
| Nielsen アプリ ID | `nielsenappid` |
| Nielsen チャネルアセット | `nielsenchannelasset` |
| Nielsen コンテンツタイプ | `nielsencontenttype` |

## Analysis Workspaceでサポートされるコンテンツ対応のディメンション

### ビデオ（ストリーミングメディアサービス）

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| [コンテンツ](sm-core.md) | `video` |
| [コンテンツセグメント](sm-core.md) | `videosegment` |
| [コンテンツタイプ](sm-core.md) | `videocontenttype` |
| [広告プレーヤー名](sm-ads.md) | `videoadplayername` |
| [ポッド位置の広告](sm-ads.md) | `videoadinpod` |
| [ドロップフレーム](sm-quality.md) | `videoqoedroppedframecountevar` |
| [エラー](sm-quality.md) | `videoqoeerrorcountevar` |
| [平均ビットレート](sm-quality.md) | `videoqoebitrateaverageevar` |
| [ビットレート変更](sm-quality.md) | `videoqoebitratechangecountevar` |
| [合計バッファー時間](sm-quality.md) | `videoqoebuffertimeevar` |
| [バッファーイベント](sm-quality.md) | `videoqoebuffercountevar` |
| [開始時間](sm-quality.md) | `videoqoetimetostartevar` |
| [広告ポッド](sm-ads.md) | `videoadpod` |
| [&#x200B; メディアパス &#x200B;](sm-core.md) | `videopath` |
| [広告](sm-ads.md) | `videoad` |
| [コンテンツプレーヤー名](sm-core.md) | `videoplayername` |
| [コンテンツチャネル](sm-core.md) | `videochannel` |
| [チャプター](sm-chapters.md) | `videochapter` |
| [コンテンツ名 (変数)](sm-core.md) | `videoname` |
| [コンテンツの長さ (変数)](sm-core.md) | `videolength` |
| [&#x200B; 広告名（変数） &#x200B;](sm-ads.md) | `videoadname` |
| [&#x200B; 広告の長さ（可変） &#x200B;](sm-ads.md) | `videoadlength` |
| [番組](sm-video-metadata.md) | `videoshow` |
| [シーズン](sm-video-metadata.md) | `videoseason` |
| [エピソード](sm-video-metadata.md) | `videoepisode` |
| [ネットワーク](sm-video-metadata.md) | `videonetwork` |
| [番組タイプ](sm-video-metadata.md) | `videoshowtype` |
| [&#x200B; 広告読み込み &#x200B;](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [日パート](sm-video-metadata.md) | `videodaypart` |
| [広告主](sm-ads.md) | `videoadadvertiser` |
| [キャンペーン ID](sm-ads.md) | `videoadcampaign` |
| [ジャンル](sm-video-metadata.md) | `videogenre` |
| [ストリームタイプ](sm-core.md) | `videostreamtype` |
| [プレーヤー SDK のエラー ID](sm-quality.md) | `videoqoeplayersdkerrors` |
| [外部エラー ID](sm-quality.md) | `videoqoeextneralerrors` |
| [メディアフィードのタイプ](sm-video-metadata.md) | `videofeedtype` |
| [&#x200B; エントリメディアパス &#x200B;](entry-dimensions.md) | `entryvideopath` |
| [&#x200B; メディア パスの終了 &#x200B;](exit-dimensions.md) | `exitvideopath` |
| [&#x200B; 応募ジャンル &#x200B;](entry-dimensions.md) | `entryvideogenre` |
| [&#x200B; ジャンルを終了 &#x200B;](exit-dimensions.md) | `exitvideogenre` |
| [Entry Player のSDK エラー ID](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [Player SDKの終了エラー ID](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [&#x200B; エントリ外部エラー ID](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [&#x200B; 外部エラー ID を終了 &#x200B;](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social は廃止されました。

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| キーワード | `socialterm` |
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
| [&#x200B; 初回開始日 &#x200B;](lifecycle-dimensions.md) | `mobileinstalldate` |
| [&#x200B; アプリ Id](lifecycle-dimensions.md) | `mobileappid` |
| [起動回数](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [初回使用からの日数](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [前回使用からの日数](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [&#x200B; 時刻（SDK） &#x200B;](lifecycle-dimensions.md) | `mobilehourofday` |
| [&#x200B; 曜日（SDK） &#x200B;](lifecycle-dimensions.md) | `mobiledayofweek` |
| [&#x200B; オペレーティングシステム（SDK） &#x200B;](lifecycle-dimensions.md) | `mobileosenvironment` |
| [前回アップグレードからの日数](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [前回アップグレードからの起動回数](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [&#x200B; デバイス名（SDK） &#x200B;](lifecycle-dimensions.md) | `mobiledevice` |
| [&#x200B; オペレーティングシステムのバージョン（SDK） &#x200B;](lifecycle-dimensions.md) | `mobileosversion` |
| [&#x200B; ビーコンのメジャー &#x200B;](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [&#x200B; ビーコンのマイナー &#x200B;](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [&#x200B; ビーコン UUID](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [&#x200B; ビーコンの近接性 &#x200B;](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [ロケーション（半径 10 km 以内）](lifecycle-dimensions.md) | `latlon1` |
| [ロケーション（半径 100 m 以内）](lifecycle-dimensions.md) | `latlon23` |
| [ロケーション（半径 1 m 以内）](lifecycle-dimensions.md) | `latlon45` |
| [目標点名](lifecycle-dimensions.md) | `pointofinterest` |
| [目標地点の中心までの距離](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [&#x200B; 位置精度 &#x200B;](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [&#x200B; 場所カテゴリ &#x200B;](lifecycle-dimensions.md) | `mobileplacecategory` |
| [&#x200B; 場所 ID](lifecycle-dimensions.md) | `mobileplaceid` |
| [&#x200B; 進入灯台メジャー &#x200B;](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [&#x200B; ビーコンを終了メジャー &#x200B;](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [&#x200B; 進入灯台マイナー &#x200B;](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [&#x200B; 離脱ビーコンのマイナー &#x200B;](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [&#x200B; エントリビーコン UUID](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [&#x200B; 離脱ビーコン UUID](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [&#x200B; 進入ビーコンの近接性 &#x200B;](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [&#x200B; 出口ビーコンの近接性 &#x200B;](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| AMO ID | `amo_cid` |

### Activity Map

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| [Activity Map リンク （地域別） &#x200B;](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Activity Map地域 &#x200B;](activity-map-region.md) | `clickmapregion` |
| [Activity Map リンク &#x200B;](activity-map-link.md) | `clickmaplink` |
| [Activity Mapページ &#x200B;](activity-map-page.md) | `clickmappage` |

### Nielsen 統合

この統合の実装方法について詳しくは、Adobe Exchangeの [Nielsen 拡張機能 &#x200B;](https://exchange.adobe.com/apps/ec/101361) を参照してください。

| ディメンション名（Analytics UI で確認可能） | ディメンション ID（API リクエストで使用） |
|--- |--- |
| Nielsen 広告モデル | `nielsenadmodel` |
| Nielsen セグメント C | `nielsensegmentc` |
| Nielsen セグメント B | `nielsensegmentb` |
| Nielsen セグメント A | `nielsensegmenta` |
| Nielsen コンテンツ ID | `nielsencontentid` |
| Nielsen Asset/プログラム | `nielsenasset` |
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
| Adobe Campaign 実行された配信 ID | `ac_delivery_internal_name` |
