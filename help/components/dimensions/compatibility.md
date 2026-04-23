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

このページには、それぞれのAnalytics機能でサポートされている[ ディメンション ](overview.md)が一覧表示されます。

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
| [Cookie サポート ](cookie-support.md) | `cookie` |
| [国](countries.md) | `geocountry` |
| [顧客の忠誠度](customer-loyalty.md) | `customerloyalty` |
| [ カスタムコンバージョン変数](evar.md) | `evar1`, `evar2`, etc. |
| [Custom Insight Vars](prop.md) | `prop1`, `prop2`, etc. |
| [カスタムリンク](custom-link.md) | `customlink` |
| [初回購入までの日数](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [前回購入からの日数](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [ドメイン](domain.md) | `filtereddomain` |
| [ ダウンロードリンク ](download-link.md) | `downloadlink` |
| [入口ページ ](entry-dimensions.md) | `entrypage` |
| [入口ページのオリジナル ](entry-dimensions.md) | `entrypageoriginal` |
| [ リンクを終了](exit-link.md) | `exitlink` |
| [ ファーストタッチチャネル ](first-touch-channel.md) | `firsttouchchannel` |
| [ ファーストタッチチャネルの詳細](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java 有効](java-enabled.md) | `javaenabled` |
| [言語](language.md) | `language` |
| [最後のタッチチャネル ](last-touch-channel.md) | `lasttouchchannel` |
| [ ラストタッチチャネルの詳細](last-touch-detail.md) | `lasttouchchanneldetail` |
| リスト変数 | `listvariables` |
| [ マーケティングチャネル ](marketing-channel.md) | `marketingchannel` |
| [ モバイルオーディオサポート ](mobile-dimensions.md) | `mobileaudiosupport` |
| [携帯電話会社](mobile-dimensions.md) | `mobilecarrier` |
| [ モバイル色深度](mobile-dimensions.md) | `mobilecolordepth` |
| [ モバイル Cookie サポート ](mobile-dimensions.md) | `mobilecookiesupport` |
| [ モバイルデバイス ](mobile-dimensions.md) | `mobiledevicename` |
| [ モバイルデバイスタイプ ](mobile-dimensions.md) | `mobiledevicetype` |
| [ モバイルのメールの最大長](mobile-dimensions.md) | `mobileemaillength` |
| [ モバイル画像サポート ](mobile-dimensions.md) | `mobileimagesupport` |
| [ モバイルメーカー](mobile-dimensions.md) | `mobilemanufacturer` |
| [ モバイル オペレーティング システム （非推奨） ](mobile-dimensions.md) | `mobileos` |
| [ モバイル画面の高さ](mobile-dimensions.md) | `mobilescreenheight` |
| [ モバイル画面サイズ ](mobile-dimensions.md) | `mobilescreensize` |
| [ モバイル画面の幅](mobile-dimensions.md) | `mobilescreenwidth` |
| [ モバイル最大ブラウザーURL長](mobile-dimensions.md) | `mobileurllength` |
| [ モバイルビデオのサポート ](mobile-dimensions.md) | `mobilevideosupport` |
| [画面の解像度](monitor-resolution.md) | `monitorresolution` |
| [オペレーティングシステム](operating-systems.md) | `operatingsystem` |
| [元の参照ドメイン ](original-referring-domain.md) | `referringdomainoriginal` |
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
| [検索エンジン – ナチュラル ](search-engine.md) | `searchenginenatural` |
| [検索エンジン – 有料](search-engine.md) | `searchenginepaid` |
| [検索キーワード – ナチュラル ](search-keyword.md) | `searchenginenaturalkeyword` |
| [検索キーワード – 有料](search-keyword.md) | `searchenginepaidkeyword` |
| [すべての検索ページのランク ](all-search-page-rank.md) | `searchenginepagerank` |
| [サーバー](server.md) | `server` |
| [直帰数](single-page-visits.md) | `singlepagevisits` |
| [ サイトセクション ](site-section.md) | `sitesections` |
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
| [ ブラウザーの高さ – バケット化](browser-height.md) | `browserheightbucketed` |
| [ ブラウザー幅 – バケット化](browser-width.md) | `browserwidthbucketed` |
| [日](day.md) | `daterangeday` |
| [月間通算日](day-of-month.md) | `timepartdayofmonth` |
| [曜日](day-of-week.md) | `dayofweek` |
| [曜日](day-of-week.md) | `timepartdayofweek` |
| [年間通算日](day-of-year.md) | `timepartdayofyear` |
| [最終訪問からの日数](days-since-last-visit.md) | `dayssincelastvisit` |
| [ カスタムインサイトの入力](entry-dimensions.md) | `entryprops` |
| [ エントリリスト変数](entry-dimensions.md) | `entrylistvariables` |
| [ エントリサーバー](entry-dimensions.md) | `entryserver` |
| [入口サイトセクション ](entry-dimensions.md) | `entrysitesections` |
| [ カスタムインサイトを終了](exit-dimensions.md) | `exitprops` |
| [ リスト変数を終了](exit-dimensions.md) | `exitlistvariables` |
| [ ページを終了](exit-dimensions.md) | `exitpage` |
| [ サーバーを終了](exit-dimensions.md) | `exitserver` |
| [ サイトセクションを終了](exit-dimensions.md) | `exitsitesections` |
| [ ヒット深度](hit-depth.md) | `hitdepth` |
| [ヒットタイプ](hit-type.md) | `hittype` |
| [時間](hour.md) | `daterangehour` |
| [時間帯](hour-of-day.md) | `timeparthourofday` |
| [ マーケティングチャネルの詳細](marketing-detail.md) | `marketingchanneldetail` |
| [分](minute.md) | `daterangeminute` |
| [ モバイル最大ブックマーク長](mobile-dimensions.md) | `mobilebookmarklength` |
| [ モバイルデバイス番号](mobile-dimensions.md) | `mobiledevicenumber` |
| [ モバイル DRM](mobile-dimensions.md) | `mobiledrm` |
| [ モバイル インフォメーション サービス ](mobile-dimensions.md) | `mobileinformationservices` |
| [ モバイル Java VM](mobile-dimensions.md) | `mobilejavavm` |
| [ モバイルメールの装飾](mobile-dimensions.md) | `mobilemaildecoration` |
| [ モバイルネットプロトコル ](mobile-dimensions.md) | `mobilenetprotocols` |
| [ モバイルプッシュ通知](mobile-dimensions.md) | `mobilepushtotalk` |
| [月](month.md) | `daterangemonth` |
| [年間通算月](month-of-year.md) | `timepartmonthofyear` |
| [オペレーティングシステムの種類](operating-system-types.md) | `operatingsystemgroup` |
| [有料検索](paid-search.md) | `paidsearch` |
| [永続的なCookie サポート ](persistent-cookie-support.md) | `persistentcookie` |
| [四半期](quarter.md) | `daterangequarter` |
| [四半期](quarter-of-year.md) | `timepartquarterofyear` |
| 調査 | `surveybase` |
| [ ページ滞在時間 – バケット化](time-spent-on-page.md) | `averagepagetime` |
| [ ページ滞在時間 – 詳細](time-spent-on-page.md) | `pagetimeseconds` |
| [ オプトアウトのトラッキング理由](tracking-opt-out-reason.md) | `optoutreason` |
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
| [ コンテンツセグメント ](sm-core.md) | `videosegment` |
| [ コンテンツの種類](sm-core.md) | `videocontenttype` |
| [広告プレイヤー名](sm-ads.md) | `videoadplayername` |
| ポッド位置[の](sm-ads.md)広告 | `videoadinpod` |
| [削除されたフレーム ](sm-quality.md) | `videoqoedroppedframecountevar` |
| [エラー](sm-quality.md) | `videoqoeerrorcountevar` |
| [平均ビットレート ](sm-quality.md) | `videoqoebitrateaverageevar` |
| [ ビットレートの変更](sm-quality.md) | `videoqoebitratechangecountevar` |
| [合計バッファー期間](sm-quality.md) | `videoqoebuffertimeevar` |
| [ バッファーイベント ](sm-quality.md) | `videoqoebuffercountevar` |
| [開始までの時間](sm-quality.md) | `videoqoetimetostartevar` |
| [広告ポッド ](sm-ads.md) | `videoadpod` |
| [ メディアパス ](sm-core.md) | `videopath` |
| [Ad](sm-ads.md) | `videoad` |
| [ コンテンツプレーヤー名](sm-core.md) | `videoplayername` |
| [ コンテンツチャネル ](sm-core.md) | `videochannel` |
| [章](sm-chapters.md) | `videochapter` |
| [ コンテンツ名（変数） ](sm-core.md) | `videoname` |
| [ コンテンツの長さ（変数） ](sm-core.md) | `videolength` |
| [広告名（変数） ](sm-ads.md) | `videoadname` |
| [広告の長さ（変数） ](sm-ads.md) | `videoadlength` |
| [表示](sm-video-metadata.md) | `videoshow` |
| [ シーズン ](sm-video-metadata.md) | `videoseason` |
| [ エピソード ](sm-video-metadata.md) | `videoepisode` |
| [ネットワーク](sm-video-metadata.md) | `videonetwork` |
| [ タイプを表示](sm-video-metadata.md) | `videoshowtype` |
| [広告読み込み](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [日パート ](sm-video-metadata.md) | `videodaypart` |
| [広告主](sm-ads.md) | `videoadadvertiser` |
| [キャンペーン ID](sm-ads.md) | `videoadcampaign` |
| [ ジャンル ](sm-video-metadata.md) | `videogenre` |
| [ ストリームタイプ ](sm-core.md) | `videostreamtype` |
| [Player SDK エラーID](sm-quality.md) | `videoqoeplayersdkerrors` |
| [外部エラーID](sm-quality.md) | `videoqoeextneralerrors` |
| [ メディアフィードの種類](sm-video-metadata.md) | `videofeedtype` |
| [ エントリメディアパス ](entry-dimensions.md) | `entryvideopath` |
| [ メディアパスを終了](exit-dimensions.md) | `exitvideopath` |
| [ エントリジャンル ](entry-dimensions.md) | `entryvideogenre` |
| [ ジャンルを終了](exit-dimensions.md) | `exitvideogenre` |
| [Entry Player SDK エラーID](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [ プレイヤーの終了SDK エラーID](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [ エントリ外部エラーID](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
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
| [ アプリ ID](lifecycle-dimensions.md) | `mobileappid` |
| [起動回数](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [初回使用からの日数](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [前回使用からの日数](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [時間帯（SDK） ](lifecycle-dimensions.md) | `mobilehourofday` |
| [曜日（SDK） ](lifecycle-dimensions.md) | `mobiledayofweek` |
| [ オペレーティングシステム （SDK） ](lifecycle-dimensions.md) | `mobileosenvironment` |
| [前回アップグレードからの日数](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [前回アップグレードからの起動回数](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [ デバイス名（SDK） ](lifecycle-dimensions.md) | `mobiledevice` |
| [ オペレーティングシステムのバージョン（SDK） ](lifecycle-dimensions.md) | `mobileosversion` |
| [ ビーコン メジャー](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [ ビーコン マイナー](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [ ビーコン UUID](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [ ビーコン近接](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [ロケーション（半径 10 km 以内）](lifecycle-dimensions.md) | `latlon1` |
| [ロケーション（半径 100 m 以内）](lifecycle-dimensions.md) | `latlon23` |
| [ロケーション（半径 1 m 以内）](lifecycle-dimensions.md) | `latlon45` |
| [目標点名](lifecycle-dimensions.md) | `pointofinterest` |
| [目標地点の中心までの距離](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [場所の精度](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [ カテゴリを配置](lifecycle-dimensions.md) | `mobileplacecategory` |
| [ プレース ID](lifecycle-dimensions.md) | `mobileplaceid` |
| [ エントリビーコンのメジャー](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [ ビーコン メジャーを終了](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [ エントリ ビーコン マイナー](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [小ビーコンを終了](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [ エントリビーコン UUID](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [ ビーコン UUIDを終了](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [ エントリビーコン近接](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [ ビーコン近接を終了](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

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
