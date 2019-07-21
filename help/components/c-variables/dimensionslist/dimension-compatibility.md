---
title: Analyticsディメンションの互換性
seo-title: 分析ワークスペース、Reports& Analytics、またはその両方と互換性のあるAnalyticsディメンションおよびレポート。
description: Analyticsのディメンションおよびレポートのリファレンスです。
seo-description: Analysis Workspaceのディメンション、Reports& Analyticsのディメンション、ディメンション、R& Aディメンション、ワークスペースディメンション
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Analyticsディメンションの互換性

このリファレンス記事では、Reports&amp; AnalyticsとAnalysis Workspaceの両方でサポートされているディメンション/レポート、Analysis Workspaceのみ、Reports&amp; Analyticsでのみサポートされています。

次の点に注意してください。

* ここに提示するのは完全なリストではありません。各レポートスイートには、製品の変数が有効化された特定のセットが含まれることも、含まれないこともあります。また、特定のレポートスイートでは、任意の数のカスタム変数が有効化、無効化、または製品変数にマッピングされている場合があります。また、訪問者の属性と分類は、各レポートスイートに固有のため省略しています。

* There are some cases of overlap, where Analytics tools use different terms for what is essentially the same thing, for example: `browserwidth` and `browserwidthbucketed`.

## Reports &amp; Analytics と Analysis Workspace の両方でサポートされているディメンション

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|---|---|
| Analytics for Target | targetraw |
| オーディエンス ID | mcaudiences |
| ブラウザー | browser |
| ブラウザーのタイプ | browsertype |
| カテゴリ | category |
| 市区町村 | geocity |
| 画面の色 | colordepth |
| 接続のタイプ | connectiontype |
| cookie サポート | cookie |
| 国 | geocountry |
| 顧客の忠誠度 | customerloyalty |
| カスタムコンバージョン VAR | evar1、evar2など |
| カスタムインサイト VAR | prop1、prop2など |
| カスタムリンク | customlink |
| 初回購入までの日数 | daysbeforefirstpurchase |
| 前回購入からの日数 | dayssincelastpurchase |
| ドメイン | filtereddomain |
| ダウンロードリンク | downloadlink |
| 入口ページ | entrypage |
| オリジナルの入口ページ | entrypageoriginal |
| 離脱リンク | exitlink |
| ファーストタッチチャネル | firsttouchchannel |
| ファーストタッチチャネルの詳細 | firsttouchchanneldetail |
| Java有効 | javaenabled |
| 言語 | language |
| ラストタッチチャネル | lasttouchchannel |
| ラストタッチチャネルの詳細 | lasttouchchanneldetail |
| リスト変数 | listvariables |
| マーケティングチャネル | marketingchannel |
| モバイルのオーディオ サポート | mobileaudiosupport |
| 携帯電話会社 | mobilecarrier |
| モバイルの画面の色 | mobilecolordepth |
| モバイルの cookie サポート | mobilecookiesupport |
| モバイルデバイス | mobiledevicename |
| モバイルデバイスタイプ | mobiledevicetype |
| モバイルの電子メール最大長 | mobileemaillength |
| モバイルの画像サポート | mobileimagesupport |
| モバイルの製造元 | mobilemanufacturer |
| モバイルオペレーティングシステム (非推奨) | mobileos |
| モバイルの画面の高さ | mobilescreenheight |
| モバイルの画面のサイズ | mobilescreensize |
| モバイルの画面の幅 | mobilescreenwidth |
| モバイルのブラウザー URL 最大長 | mobileurllength |
| モバイルのビデオ サポート | mobilevideosupport |
| 画面の解像度 | monitorresolution |
| オペレーティングシステム | operatingsystem |
| オリジナルの参照ドメイン | referringdomainoriginal |
| ページ | page |
| エラーページ(404) | pagesnotfound |
| 製品 | product |
| リファラー | referrer |
| リファラータイプ | referrertype |
| 参照ドメイン | referringdomain |
| 地域 | georegion |
| 再来訪頻度 | returnfrequency |
| SC-TnT | tntbase |
| 検索エンジン | searchengine |
| 検索キーワード | searchenginekeyword |
| 検索エンジン - 自然 | searchenginenatural |
| 検索エンジン - 有料 | searchenginepaid |
| 検索キーワード - 自然 | searchenginenaturalkeyword |
| 検索キーワード - 有料 | searchenginepaidkeyword |
| すべての検索ページのランク | searchenginepagerank |
| サーバー | server |
| 直帰数 | singlepagevisits |
| サイトセクション | sitesections |
| 訪問別滞在時間 - 詳細 | sitetime |
| トラッキングコード | campaign |
| 米国 DMA | geodma |
| 米国の州 | state |
| イベント前の時間 | timeprior |
| 訪問別滞在時間 - グループ | timespent |
| 訪問の深さ | pathlength |
| 訪問回数 | visitnumber |
| 郵便番号 | zip |

## Analysis Workspace のみでサポートされているディメンション

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| 午前 / 午後 | timepartampm |
| ブラウザーの高さ - グループ | browserheightbucketed |
| ブラウザーの幅 - グループ | browserwidthbucketed |
| 日 | daterangeday |
| 月間通算日 | timepartdayofmonth |
| 曜日 | dayofweek |
| 曜日 | timepartdayofweek |
| 年間通算日 | timepartdayofyear |
| 最終訪問からの日数 | dayssincelastvisit |
| 入口カスタムインサイト | entryprops |
| 入口リスト変数 | entrylistvariables |
| 入口サーバー | entryserver |
| 入口サイトセクション | entrysitesections |
| 出口カスタムインサイト | exitprops |
| 出口リスト変数 | exitlistvariables |
| 出口ページ | exitpage |
| 出口サーバー | exitserver |
| 出口サイトセクション | exitsitesections |
| ヒットの深さ | hitdepth |
| ヒットタイプ | hittype |
| 時間 | daterangehour |
| 時刻 | timeparthourofday |
| マーケティングチャネル詳細 | marketingchanneldetail |
| 分 | daterangeminute |
| モバイルのブックマーク最大長 | mobilebookmarklength |
| Mobile Device Number | mobiledevicenumber |
| モバイル DRM | mobiledrm |
| モバイル情報サービス | mobileinformationservices |
| モバイル Java VM | mobilejavavm |
| モバイルデコレーションメール | mobilemaildecoration |
| モバイル インターネット プロトコル | mobilenetprotocols |
| モバイルプッシュトゥトーク | mobilepushtotalk |
| 月 | daterangemonth |
| 年間通算月 | timepartmonthofyear |
| オペレーティングシステムの種類 | operatingsystemgroup |
| 有料検索 | paidsearch |
| 永続的な cookie のサポート | persistentcookie |
| 四半期 | daterangequarter |
| 四半期 | timepartquarterofyear |
| 調査 | surveybase |
| ページでの滞在時間 - グループ | averagepagetime |
| ページでの平均滞在時間 - 詳細 | pagetimeseconds |
| トラッキングオプトアウト理由 | optoutreason |
| 平日 / 週末 | timepartweekdayweekend |
| 週 | daterangeweek |
| 年 | daterangeyear |

## Analysis Workspace のみでサポートされているコンテンツに応じたディメンション

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| Activity Map XY | clickmapxy |
| メディアセッション ID | videosessionid |
| Nielsen アクセス方法 | nielsenaccmethod |
| Nielsen アプリ ID | nielsenappid |
| Nielsen チャネルアセット | nielsenchannelasset |
| Nielsen コンテンツタイプ | nielsencontenttype |

## Reports &amp; Analytics のみでサポートされているディメンション

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| ブラウザーの高さ | browserheight |
| ブラウザーの幅 | browserwidth |
| 日別ユニーク顧客数 | dailyuniquecustomers |
| JavaScript | javascriptsupport |
| JavaScript のバージョン | javascriptversion |
| 月別ユニーク顧客数 | monthlyuniquecustomers |
| 四半期別ユニーク顧客数 | quarterlyuniquecustomers |
| タイムゾーン | timezone |
| トップレベルドメイン | topleveldomain |
| 訪問者の州 | legacystate |
| 週別ユニーク顧客数 | weeklyuniquecustomers |
| 年別ユニーク顧客数 | yearlyuniquecustomers |

## Reports &amp; Analytics での事前構成されたレポート

Reports &amp; Analytics には、特定のディメンションにマッピングされないか、レポートがディメンションのクラスを使用する、複数の事前構成されたレポートが含まれます。以下にレポートの一覧を示します。

* ブックマーク URL の長さ
* ブラウザー
* ブラウザータイプ
* キャンペーンコンバージョンファネル
* 買い物かごコンバージョンファネル
* 市区町村
* ページへのクリック数
* 国
* クロス販売
* カスタムイベントファネル
* デコメ対応
* 機体番号送信 (オン/オフ)
* ドメイン
* DRM
* 入口ページ
* 出口ページ
* フォールアウト
* フルパス
* ICities
* 情報配信
* Java バージョン
* 言語
* 最長パス
* メディア同時ビューア
* メディア視聴時間帯
* メディアの詳細
* メディアの概要
* 画面の解像度
* 通信方式
* Netscape プラグイン
* 次のページ
* 次ページのフロー
* オペレーティングシステム
* オペレーティングシステムの種類
* ページの深さ
* ページサマリ
* パスファインダー
* 前ページのフロー
* 前のページ
* PTT
* 製品コンバージョンファネル
* 購入コンバージョンファネル
* 参照ドメイン
* 地域
* リロード回数
* 検索エンジン - すべて
* 検索エンジン - 自然
* 検索エンジン - 有料
* 検索キーワード - すべて
* 検索キーワード - 自然
* 検索キーワード - 有料
* ターゲットアクティビティの詳細
* ページでの滞在時間
* タイムゾーン
* トップレベルドメイン
* 米国 DMA
* 米国の州
* 訪問回数
* 訪問者ホームページ

## Reports &amp; Analytics と Analysis Workspace の両方でサポートされているコンテンツに応じたディメンション

### ビデオ (メディア分析)

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| コンテンツ | video |
| コンテンツセグメント | videosegment |
| コンテンツタイプ | videocontenttype |
| 広告プレーヤー名 | videoadplayername |
| ポッド位置の広告 | videoadinpod |
| ドロップフレーム | videoqoedroppedframecountevar |
| エラー | videoqoeerrorcountevar |
| 平均ビットレート | videoqoebitrateaverageevar |
| ビットレート変更 | videoqoebitratechangecountevar |
| 合計バッファー時間 | videoqoebuffertimeevar |
| バッファーイベント | videoqoebuffercountevar |
| 開始時間 | videoqoetimetostartevar |
| 広告ポッド | videoadpod |
| メディアパス | videopath |
| 広告 | videoad |
| コンテンツプレイヤー名 | videoplayername |
| コンテンツチャネル | videochannel |
| チャプター | videochapter |
| コンテンツ名 (変数) | videoname |
| コンテンツの長さ (変数) | videolength |
| 広告名 (変数) | videoadname |
| 広告の長さ (変数) | videoadlength |
| 番組 | videoshow |
| シーズン | videoseason |
| エピソード | videoepisode |
| ネットワーク | videonetwork |
| 番組タイプ | videoshowtype |
| 広告読み込み | videoadload |
| MVPD | videomvpd |
| 日パート | videodaypart |
| 広告主 | videoadadvertiser |
| キャンペーン ID | videoadcampaign |
| ジャンル | videogenre |
| ストリームタイプ | videostreamtype |
| プレーヤー SDK のエラー ID | videoqoeplayersdkerrors |
| 外部エラー ID | videoqoeexternalerrors |
| メディアフィードのタイプ | videofeedtype |
| 入口メディアパス | entryvideopath |
| 出口メディアパス | exitvideopath |
| 入口ジャンル | entryvideogenre |
| 出口ジャンル | exitvideogenre |
| 入口プレーヤー SDK のエラー ID | entryvideoqoeplayersdkerrors |
| 出口プレーヤー SDK のエラー ID | exitvideoqoeplayersdkerrors |
| 入口外部エラー ID | entryvideoqoeexternalerrors |
| 出口外部エラー ID | exitvideoqoeexternalerrors |

### Adobe Social

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| キーワード | socialterm |
| Social プラットフォーム／プロパティ | socialcontentprovider |
| 発言者 | socialauthor |
| 言語 | sociallanguage |
| 緯度 / 経度 | sociallatlong |
| トラッキングコード | socialassettrackingcode |
| 所有ソーシャルプロパティ | socialaccountandappids |
| 所有投稿 ID | socialownedpostids |
| 所有ソーシャル定義 | socialinteractiontype |
| 所有プロパティ ID | socialownedpropertyid |
| 所有プロパティとアプリケーション | socialownedpropertypropertyvsapp |
| 所有プロパティ名 | socialownedpropertyname |
| 所有定義プロパティと投稿 | socialowneddefinitionpropertyvspost |
| 所有定義インサイトの種類 | socialowneddefinitioninsighttype |
| 所有定義インサイト値 | socialowneddefinitioninsightvalue |
| 所有定義指標 | socialowneddefinitionmetric |
| アセット | socialmediaid |

### モバイル SDK

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| 初回起動日 | mobileinstalldate |
| アプリケーション ID | mobileappid |
| 起動回数 | mobilelaunchnumber |
| 初回使用からの日数 | mobiledayssincefirstuse |
| 前回使用からの日数 | mobiledayssincelastuse |
| 時間帯 (SDK) | mobilehourofday |
| 曜日 (SDK) | mobiledayofweek |
| オペレーティングシステム (SDK) | mobileosenvironment |
| 前回アップグレードからの日数 | mobiledayssincelastupgrade |
| 前回アップグレードからの起動回数 | mobilelaunchessincelastupgrade |
| 機種名 (SDK) | mobiledevice |
| オペレーティングシステムのバージョン (SDK) | mobileosversion |
| ビーコンの Major | mobilebeaconmajor |
| ビーコンの Minor | mobilebeaconminor |
| ビーコンの UUID | mobilebeaconuuid |
| ビーコンの Proximity | mobilebeaconproximity |
| ロケーション (半径 10 km 以内) | latlon1 |
| ロケーション (半径 100 m 以内) | latlon23 |
| ロケーション (半径 1 m 以内) | latlon45 |
| 目標点名 | pointofinterest |
| 目標地点の中心までの距離 | pointofinterestdistance |
| ロケーション精度 | mobileplaceaccuracy |
| 場所のカテゴリ | mobileplacecategory |
| 場所 ID | mobileplaceid |
| 入口ビーコンの Major | entrymobilebeaconmajor |
| 出口ビーコンの Major | exitmobilebeaconmajor |
| 入口ビーコンの Minor | entrymobilebeaconminor |
| 出口ビーコンの Minor | exitmobilebeaconminor |
| 入口ビーコンの UUID | entrymobilebeaconuuid |
| 出口ビーコンの UUID | exitmobilebeaconuuid |
| 入口ビーコンの Proximity | entrymobilebeaconproximity |
| 出口ビーコンの Proximity | exitmobilebeaconproximity |

### Adobe Advertising Cloud（AMO）

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| AMO EF ID | amo_ef_id |
| AMO ID | amo_cid |

### Activity Map

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| Activity Map 地域別リンク | clickmaplinkbyregion |
| Activity Map 地域 | clickmapregion |
| Activity Map リンク | clickmaplink |
| Activity Map ページ | clickmappage |

### Nielsen 統合

この統合の実装方法の詳細については、[Nielsen パートナーシップ](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html)を参照してください。

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| Nielsen 広告モデル | nielsenadmodel |
| Nielsen セグメント C | nielsensegmentc |
| Nielsen セグメント B | nielsensegmentb |
| Nielsen セグメント A | nielsensegmenta |
| Nielsen コンテンツ ID | nielsencontentid |
| Nielsen アセット / プログラム | nielsenasset |
| Nielsen VCID | nielsenvcid |
| Nielsen オプトアウト | nielsenoptout |
| Nielsen クライアント ID + VCID | nielsenclientidvcid |
| Nielsen クライアント ID | nielsenclientid |
| 入口 Nielsen オプトアウト | entrynielsenoptout |
| 出口 Nielsen オプトアウト | exitnielsenoptout |
| 入口 Nielsen クライアント ID + VCID | entrynielsenclientidvcid |
| 出口 Nielsen クライアント ID + VCID | exitnielsenclientidvcid |
| 入口 Nielsen クライアント ID | entrynielsenclientid |
| 出口 Nielsen クライアント ID | exitnielsenclientid |

### Adobe Experience Manager  （AEM）

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| アセット ID | aemassetid |
| アセットソース | aemassetsource |
| クリックされたアセット ID | aemclickedassetid |
| 入口アセット ID | entryaemassetid |
| 出口アセット ID | exitaemassetid |

### Adobe Campaign

| ディメンション名（Analytics UIに表示） | ディメンション ID (API リクエストで使用) |
|--- |--- |
| Adobe Campaign 実行された配信 ID | ac_delivery_internal_name |
