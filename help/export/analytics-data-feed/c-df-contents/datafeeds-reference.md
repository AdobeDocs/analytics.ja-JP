---
description: データフィードの各列について説明するテーブルデータです。
keywords: データフィード;列
seo-description: データフィードの各列について説明するテーブルデータです。
seo-title: データ列リファレンス
solution: Analytics
subtopic: データフィード
title: データ列リファレンス
topic: Reports and Analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# データ列リファレンス

このページを使用して、各列に含まれるデータを学習します。ほとんどの実装ではすべての列を使用しないので、データフィードエクスポートに含める列を決定するときにこのページを参照できます。

> [!IMPORTANT] 任意の列（255文字として定義されている）の場合、文字列内の値がエスケープされた文字が追加されるので、データフィードは追加の文字を送信できます。実装で文字制限を超える値を定期的に送信する場合は、このトピックに注意してください。

## 列、説明、データタイプ

> [!NOTE] ほとんどの列には、プレフィックス付きの類似の列があり `post_`ます。post 列には、サーバー側ロジック、処理ルール、VISTA ルールの適用後の値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。

| 列名 | 列の説明 | データタイプ |
| --- | --- | --- |
| accept_language | イメージリクエストの Accept-Language HTTP ヘッダーで指定されている受け入れ可能なすべての言語のリスト。 | char(20) |
| aemassetid | 一連の Adobe Experience Manager Assets のアセット ID（GUID）に対応する複数値変数。インプレッションイベント数が増分されます。 | text |
| aemassetsource | アセットイベントのソースを識別します。Adobe Experience Manager で使用されます。 | varchar(255) |
| aemclickedassetid | Adobe Experience Manager アセットのアセット ID。クリックイベント数が増分されます。 | varchar(255) |
| browser | ブラウザーの数値 ID。browser.tsv 参照テーブルを参照します。 | int unsigned |
| browser_height | ブラウザーウィンドウの高さ（ピクセル単位）。 | smallint unsigned |
| browser_width | ブラウザーウィンドウの幅（ピクセル単位）。 | smallint unsigned |
| c_color | カラーパレットのビット深度。「色深度」ディメンションの計算の一環として使用されます。JavaScript 関数 screen.colorDepth() を使用します。 | char(20) |
| campaign | 「トラッキングコード」ディメンションで使用される変数。 | varchar(255) |
| carrier | Adobe Advertising Cloud 統合変数。携帯電話会社を指定します。carrier 参照テーブルを参照します。 | varchar(100) |
| channel | 「サイトセクション」ディメンションで使用される変数。 | varchar(100) |
| click_action | 廃止。レガシー ClickMap ツール内でクリックされたリンクのアドレス。 | varchar(100) |
| click_action_type | 廃止。レガシー ClickMap ツールのリンクタイプ。<br>0:HREF URL<br>1:カスタムID<br>2:JavaScript onClickイベント<br>3:フォーム要素 | tinyint unsigned |
| click_context | 廃止。リンククリックが発生したページの名前。レガシー ClickMap ツールの一部。 | varchar(255) |
| click_context_type | 廃止。click_context の値がページ名であったかデフォルトのページ URL であったかを示します。<br>0:ページURL<br>1:ページ名 | tinyint unsigned |
| click_sourceid | 廃止。クリックされたリンクが配置されているページ上の場所の数値 ID。レガシー ClickMap ツールの一部。 | int unsigned |
| click_tag | 廃止。クリックされた HTML 要素のタイプ。 | char(10) |
| clickmaplink | Activity Mapリンク | varchar(255) |
| clickmaplinkbyregion | 地域別のActivity Mapリンク | varchar(255) |
| clickmappage | Activity Mapページ | varchar(255) |
| clickmapregion | Activity Map地域 | varchar(255) |
| code_ver | イメージリクエストのコンパイルと送信に使用される AppMeasurement Library のバージョン。 | char(16) |
| color | c_color 列の値に基づいた色深度 ID。color_depth.tsv 参照テーブルを参照します。 | smallint unsigned |
| connection_type | 接続タイプを表す数値 ID。「接続タイプ」ディメンションで使用される変数。connection_type.tsv 参照テーブルを参照します。 | tinyint unsigned |
| cookie | 「cookie サポート」ディメンションで使用される変数。<br>Y:enableDN<br>:disabledU<br>:不明 | char(1) |
| country | ヒットの発生元となった国を表す数値 ID。アドビでは Digital Envoy 社との提携により、IP アドレスと国を対応させることができます。country.tsv 参照テーブルを使用します。 | smallint unsigned |
| ct_connect_type | connection_type 列と関連しています。よく使用される値は LAN/Wi-Fi、Mobile Carrier、Modem です。 | char(20) |
| curr_factor | 通貨の小数点以下の桁数を指定します。通貨の変換に使用されます。例えば、USD では小数点以下 2 桁を使用するので、この列の値は 2 になります。 | tinyint |
| curr_rate | トランザクションが発生した時点の為替レート。アドビでは XE 社との提携により、当日の為替レートを決定しています。 | decimal(24,12) |
| currency | 取引で使用された通貨のコード。 | char(8) |
| cust_hit_time_gmt | タイムスタンプに対応するレポートスイートの場合のみ。ヒットと共に送信されたタイムスタンプ（UNIX 時間）。 | int |
| cust_visid | カスタム訪問者 ID が設定されている場合は、それがこの列に格納されます。 | varchar(255) |
| daily_visitor | ヒットが新しい日別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| date_time | レポートスイートのタイムゾーンに基づいて判読可能な形式で表現されたヒットの時刻。 | 日時 |
| domain | 「ドメイン」ディメンションで使用される変数。ユーザーのインターネットサービスプロバイダー（ISP）に基づきます。 | varchar(100) |
| duplicate_events | 重複としてカウントされた各イベントを列挙します。 | varchar(255) |
| duplicate_purchase | このヒットの購入イベントが重複しているので無視する必要があることを示すフラグ。 | tinyint unsigned |
| duplicated_from | ヒットコピー VISTA ルールを含んだレポートスイートでのみ使用されます。ヒットのコピー元となったレポートスイートを示します。 | varchar(40) |
| ef_id | Adobe Advertising Cloud 統合で使用される ef_id。 | varchar(255) |
| evar1 ～ evar250 | カスタム変数 1 ～ 250。eVar の使用方法は組織ごとに異なります。組織における各 eVar への値の設定方法について詳しくは、それぞれの組織に固有のソリューションデザインドキュメントを参照してください。 | varchar(255) |
| event_list | ヒットで発生したイベントを表す数値 ID のコンマ区切りリスト。デフォルトイベントもカスタムイベント 1 ～ 1000 も含まれています。event.tsv 参照テーブルを使用します。 | text |
| exclude_hit | ヒットがレポートから除外されていることを示すフラグ。visit_ num列は、除外されたヒットに対してはインクリメントされません。<br>1：未使用. Scraped機能の一部。<br>2：未使用. Scraped機能の一部。<br>3:使用されなくなりました。User agent exclusion<br>4: Exclusion based on IP address<br>5: Vital hit info missing, such as page_url, pagename, page_event, or event_list<br>6: JavaScript did not correctly process hit<br>7: Account-specific exclusion, such as in a VISTA rules<br>8: Not used. アカウント固有の除外除外。<br>9：未使用. Scraped機能の一部。<br>10:無効な通貨コード<br>11:タイムスタンプのみのレポートスイートにタイムスタンプがないか、タイムスタンプのないレポートスイート<br>12のタイムスタンプが含まれているヒットがヒットに含まれていました。未使用。Scraped機能の一部。<br>13：未使用. Scraped機能の一部。<br>14:Analyticsのヒット<br>15と一致しなかったTargetヒット:現在使用されていません。<br>16:Analyticsヒットに適合しなかった広告クラウドヒット | tinyint unsigned |
| first_hit_page_url | 訪問者の本当に最初の URL。 | varchar(255) |
| first_hit_pagename | 「オリジナルの入口ページ」ディメンションで使用される変数。訪問者のオリジナルの入口ページ名。 | varchar(100) |
| first_hit_ref_domain | 「オリジナルの参照ドメイン」ディメンションで使用される変数。first_hit_referrer に基づいています。訪問者の本当に最初の参照ドメイン。 | varchar(100) |
| first_hit_ref_type | 訪問者の本当に最初のリファラーのリファラータイプを表す数値 ID。referrer_type.tsv 参照テーブルを使用します。 | tinyint unsigned |
| first_hit_referrer | 訪問者の本当に最初の参照 URL。 | varchar(255) |
| first_hit_time_gmt | 訪問者の本当に最初のヒットのタイムスタンプ（UNIX 時間）。 | int |
| geo_city | ヒットの発生元となった市区町村の名前（IP アドレスに基づく）。アドビでは Digital Envoy 社との提携により、IP アドレスと市区町村を対応させることができます。 | char(32) |
| geo_country | ヒットの発生元となった国の略称（IP アドレスに基づく）。アドビでは Digital Envoy 社との提携により、IP アドレスと国を対応させることができます。 | char(4) |
| geo_dma | ヒットの発生元となった人口分布地域の数値 ID（IP アドレスに基づく）。アドビでは Digital Envoy 社との提携により、IP アドレスと人口分布地域を対応させることができます。 | int unsigned |
| geo_region | ヒットの発生元となった州または地域の名前（IP アドレスに基づく）。アドビでは Digital Envoy 社との提携により、IP アドレスと州または地域を対応させることができます。 | char(32) |
| geo_zip | IPに基づいて送信された郵便番号。アドビでは Digital Envoy 社との提携により、IP アドレスと郵便番号を対応させることができます。 | varchar(16) |
| hier1 ～ hier5 | 階層変数で使用。値の区切りリストが格納されます。区切り文字は、レポートスイートの設定に基づいて選択されます。 | varchar(255) |
| hit_source | ヒットの発生源を示します。<br>1:タイムスタンプ <br>2のない標準イメージリクエスト:タイムスタンプ <br>3の標準イメージリクエスト:タイムスタンプ <br>4を使用したライブデータソースのアップロード:未使用 <br>5:汎用データソースアップロード <br>6:フル処理データソースアップロード <br>7:transactionIDデータソースのアップロード <br>8:使用されなくなりました。Adobe Advertising Cloudデータソース <br>9の以前のバージョン:使用されなくなりました。Adobe Socialサマリ指標 | tinyint unsigned |
| hit_time_gmt | Adobeデータ収集サーバーのタイムスタンプが、Unix時間に基づいてヒットを受け取りました。 | int |
| hitid_high | hitid_low と組み合わせて使用し、ヒットを一意に識別します。 | bigint unsigned |
| hitid_low | hitid_high と組み合わせて使用し、ヒットを一意に識別します。 | bigint unsigned |
| homepage | 廃止。現在の URL がブラウザーのホームページかどうかを示します。 | char(1) |
| hourly_visitor | ヒットが新しい時間別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| ip | イメージリクエストの HTTP ヘッダーに基づく IP アドレス。 | char(20) |
| ip2 | 未使用。IP アドレスに基づく VISTA ルールを含んだレポートスイートのバックエンド参照変数。 | char(20) |
| j_jscript | ブラウザーでサポートされている JavaScript のバージョン。 | char(5) |
| java_enabled | Java が有効かどうかを示すフラグ。<br>Y:有効にする <br>N:無効 <br>なU:不明 | char(1) |
| javascript | JavaScript のバージョンの参照 ID（j_jscript に基づく）。参照テーブルを使用します。 | tinyint unsigned |
| language | 言語の数値 ID。languages.tsv 参照テーブルを使用します。 | smallint unsigned |
| last_hit_time_gmt | 前回のヒットのタイムスタンプ（UNIX 時間）。「前回訪問からの日数」ディメンションの計算に使用されます。 | int |
| last_purchase_num | 「顧客の忠誠度」ディメンションで使用される変数。訪問者がこれまでにおこなった購入の回数を示します。<br>0:以前の購入なし（顧客ではない） <br>1:2回前の購入（新規顧客） <br>2:3回前の購入（リターン顧客） <br>3:3回以上の購入（常連客） | int unsigned |
| last_purchase_time_gmt | 「前回購入からの日数」ディメンションで使用されます。前回おこなった購入のタイムスタンプ（UNIX 時間）。初回の購入やこれまでに購入をおこなっていない訪問者の場合、この値は 0 になります。 | int |
| latlon1 | ロケーション (半径 10 km 以内) | varchar(255) |
| latlon23 | ロケーション (半径 100 m 以内) | varchar(255) |
| latlon45 | ロケーション (半径 1 m 以内) | varchar(255) |
| mc_audiences | 訪問者が属している Audience Manager セグメント ID のリスト。 | text |
| mcvisid | Experience Cloud 訪問者 ID.2 つの 64 ビット数値を連結して 19 桁にパディングした 128 ビット数値です。 | varchar(255) |
| mobile_id | ユーザーがモバイルデバイスを使用している場合、デバイスの数値ID。 | int |
| mobileaction | モバイルアクション。Mobile ServicesでtrackActionが呼び出されると自動的に収集されます。アプリ内で自動的にアクションを渡すことができるようにします。 | varchar(100) |
| mobileappid | モバイルアプリ ID。アプリの名前とバージョンを次の形式で格納します。[appName] [BundleVersion] | varchar(255) |
| mobileappperformance appid | Apteligentデータコネクタで使用します。Apteligentで使用されるアプリID。 | varchar(255) |
| mobilepappperformancerashd | Apteligentデータコネクタで使用します。Apteligentで使用されるクラッシュID。 | varchar(255) |
| mobileapprestoreobjectid | appFiguresデータコネクタで使用します。App StoreオブジェクトID | varchar(255) |
| mobilebeaconmajor | Mobile Servicesビーコンメジャー | varchar(100) |
| mobilebeaconminor | Mobile Servicesビーコンマイナー | varchar(100) |
| mobilebeaconproximity | Mobile Servicesビーコンの近接性 | varchar(255) |
| mobilebeaconuuid | Mobile ServicesビーコンのUUID | varchar(100) |
| mobilecampaigncontent | リンクを表示するコンテンツの名前または ID。モバイルアプリの獲得によって設定されます。 | varchar(255) |
| mobilecampaignmedium | バナーや電子メールなどのマーケティングメディア。モバイルアプリの獲得によって設定されます。 | varchar(255) |
| mobilecampaignname | キャンペーンの名前。キャンペーン変数にも格納されます。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| mobilecampaignsource | ニュースレターやソーシャルメディアネットワークなどのオリジナルリファラー。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| mobilecampaignterm | この獲得で追跡する有料検索キーワードやその他の語句。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| mobiledayofweek | アプリが起動された曜日を表す数値。 | varchar(255) |
| mobiledayssincefirstuse | アプリの初回実行時からの経過日数。 | varchar(255) |
| mobiledayssincelastupgrade | コンテキストデータ変数a. DaysSinceLastUpgradeから収集されます。前回のセッションから経過した日数。 | varchar(255) |
| mobiledayssincelastuse | アプリの前回実行時からの経過日数。 | varchar(255) |
| mobiledeepinkid | Collected from the context data variable a.<span>deeplink</span>.id. 獲得レポートで、モバイル獲得リンクの識別子として使用されます。 | varchar(255) |
| mobiledevice | モバイルデバイス名。iOS の場合は、コンマ区切りの 2 桁の文字列として格納されます。最初の番号はデバイスの世代を表し、2 番目の番号はデバイスファミリーを表します。 | varchar(255) |
| mobilehourofday | アプリが起動された時刻を示します。24 時間形式に従います。 | varchar(255) |
| mobileinstalldate | モバイルインストール日。モバイルアプリをユーザーが最初に起動した日を示します。 | varchar(255) |
| mobilelaunchessincelastupgrade | コンテキストデータ変数a. LaunchesSinceUpgradeから収集されます。前回アップグレードからの起動回数をレポートします。 | varchar(255) |
| mobilelaunchnumber | モバイルアプリが起動されるたびに 1 ずつ増分されます。 | varchar(255) |
| mobileltv | 廃止。trackLifetimeValue メソッドによって設定されます。 | varchar(255) |
| mobilemessagebuttonname | Collected from the context data variable a.<span>message</span>.button.id. メッセージを閉じるボタンを識別するためにアプリ内メッセージに使用します。 | varchar(100) |
| mobilemessageid | アプリ内メッセージID | varchar(255) |
| mobilemessageonline | アプリ内メッセージオンライン | varchar(255) |
| mobilemessagepushoptin | コンテキストデータ変数a. push. optinから収集されます。ユーザーがプッシュメッセージにオプトインするときに"true"に設定します。そうでない場合、値は"false"になります。 | varchar(255) |
| mobilemessagepushpayloadid | コンテキストデータ変数a. push. payloadidから収集されました。ペイロード識別子としてプッシュメッセージで使用されます。 | varchar(255) |
| mobileosenvironment | コンテキストデータ変数a. oSEnvironmentから収集されます。AndroidやiOSなどのステートOS環境。 | varchar(255) |
| mobileosversion | Mobile Servicesオペレーティングシステムのバージョン | varchar(255) |
| mobileplaceaccuracy | コンテキストデータ変数a. loc. utilsから収集されます。収集時のGPSの精度をメートル単位で示します。 | varchar(255) |
| mobileplacecategory | コンテキストデータ変数a. loc. categoryから収集されます。特定の場所のカテゴリについて説明します。 | varchar(255) |
| mobileplaceid | Collected from the context data variable a.<span>loc</span>.id. 特定の目標地点の識別子。 | varchar(255) |
| mobilerelaunchampaigncontent | Mobile Servicesの起動コンテンツ | varchar(255) |
| mobilerelaunchampaignmedium | Mobile Services起動メディア | varchar(255) |
| mobilerelaunchampaignsource | Mobile Servicesの起動ソース | varchar(255) |
| mobilerelaunchampaignterm | Mobile Servicesの開始用語 | varchar(255) |
| mobilerelaunchampaigntrackingcode | コンテキストデータ変数a. launch. campaign. trackingcodeから収集されます。獲得キャンペーンのトラッキングコードとして、獲得で使用されます。 | varchar(255) |
| mobileresolution | モバイルデバイスの解像度。幅 x 高さ（ピクセル単位）。 | varchar(255) |
| monthly_visitor | 当月の月別訪問者であることを示すフラグ。 | tinyint unsigned |
| mvvar1~ mvvar3 | リスト変数値。実装に応じて、カスタム値の区切りリストを格納します。 | text |
| namespace | 未使用。以前に廃止された機能の一部。 | varchar(50) |
| new_visit | 現在のヒットが新しい訪問であるかどうかを指定するフラグ。訪問がアクティブでなくなった 30 分後にアドビのサーバーによって設定されます。 | tinyint unsigned |
| os | 訪問者のオペレーティングシステムを表す数値 ID。user_agent 列に基づきます。os 参照テーブルを使用します。 | int unsigned |
| p_plugins | 廃止。ブラウザーで使用可能なプラグインのリスト。JavaScript 関数 navigator.plugins() を使用します。 | text |
| page_event | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、カスタムリンク、離脱リンク）。 | tinyint unsigned |
| page_event_var1 | リンクトラッキングイメージリクエストでのみ使用されます。クリックされたダウンロードリンク、離脱リンク、カスタムリンクの URL。 | text |
| page_event_var2 | リンクトラッキングイメージリクエストでのみ使用されます。リンクのカスタム名（指定された場合）。 | varchar(100) |
| page_event_var3 | 廃止。調査モジュールやメディアモジュールのデータが格納されます。Adobe Analytics の以前のバージョンで設定されたレガシービデオレポート。 | text |
| page_type | 「エラーページ」ディメンションの設定に使用。404 エラーページにのみ使用されます。この変数の値は、空か「ErrorPage」である必要があります。 | char(20) |
| page_url | ヒットの URL。リンクトラッキングイメージリクエストでは使用されません。 | varchar(255) |
| pagename | 「ページ」ディメンションの設定に使用されます。pagename 変数が空の場合、Analytics では代わりに page_url を使用します。 | varchar(100) |
| paid_search | ヒットが有料検索の検出に一致した場合に設定されるフラグ。 | tinyint unsigned |
| partner_plugins | 未使用。以前に廃止された機能の一部。 | varchar(255) |
| persistent_cookie | 「永続的な cookie のサポート」ディメンションで使用されます。各ヒットの後で破棄されない Cookie を訪問者がサポートしているかどうかを示します。 | char(1) |
| plugins | 廃止。ブラウザー内で使用可能なプラグインに対応する数値 ID のリスト。plugins.tsv 参照テーブルを使用します。 | varchar(180) |
| pointofinterest | Mobile Servicesの目標地点名 | varchar(255) |
| pointofinterestdistance | Mobile Servicesの目標地点までの距離 | varchar(255) |
| post_ プレフィックスの付いた列 | レポートで最終的に使用された値が格納されます。各 post 列には、サーバー側ロジック、処理ルール、VISTA ルールの適用後に値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。 | post 以外の各列を参照してください。 |
| prev_page | 未使用。前のページを表すアドビ独自の識別子。 | int unsigned |
| product_list | 製品変数を通じて渡される製品リスト。製品はコンマで区切られますが、個々の製品プロパティはセミコロンで区切られます。 | text |
| product_merchandising | 未使用。代わりに product_list を使用してください。 | text |
| prop1 ～ prop75 | カスタムトラフィック変数 1 ～ 75。 | varchar(100) |
| purchaseid | 購入の一意な識別子（s_purchaseID 変数を使用して設定）。duplicate_purchase 列で使用されます。 | char(20) |
| quarterly_visitor | ヒットが新しい四半期別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| ref_domain | referrer 列に基づきます。ヒットの参照ドメイン。 | varchar(100) |
| ref_type | ヒットのリファラルのタイプを表す数値 ID。<br>1:サイト<br>2内:その他のウェブサイト <br>3:検索エンジン <br>4:ハードドライブ <br>5:USENET <br>6:手動入力/ブックマーク（リファラーなし） <br>7:Email <br>8:No JavaScript <br>9:ソーシャルネットワーク | tinyint unsigned |
| referrer | 前のページのページ URL。 | varchar(255) |
| resolution | モニターの解像度を表す数値 ID。「画面の解像度」ディメンションの値を設定します。resolution.tsv 参照テーブルを使用します。 | smallint unsigned |
| s_kwcid | Adobe Advertising Cloud統合で使用されるキーワードID。 | varchar(255) |
| s_resolution | 画面解像度の生の値。JavaScript 関数 screen.width および screen.height を使用して収集されます。 | char(20) |
| sampled_hit | 廃止。以前 Ad Hoc Analysis でサンプリングに使用されていました。 | char(1) |
| search_engine | サイトに訪問者を誘導した検索エンジンを表す数値 ID。search_engines.tsv 参照テーブルを使用します。 | smallint unsigned |
| search_page_num | 「すべての検索ページのランク」ディメンションで使用されます。ユーザーがサイトにクリックスルーする前にサイトが表示された検索結果ページを示します。 | smallint unsigned |
| secondary_hit | 二次的なヒットを追跡するフラグ。通常、ヒットをコピーするマルチスイートタギングおよび VISTA ルールで生じます。 | tinyint unsigned |
| service | 未使用。代わりに page_event を使用してください。 | char(2) |
| socialaccountandappids | 廃止。Social アカウントおよびアプリ ID | varchar(255) |
| socialassettrackingcode | 廃止。Social キャンペーン変数 | varchar(255) |
| socialauthor | 廃止。Social 発言者変数 | varchar(255) |
| socialcontentprovider | 廃止。Social プラットフォーム／プロパティ | varchar(255) |
| socialinteractiontype | 廃止。Social インタラクションタイプ | varchar(255) |
| sociallanguage | 廃止。Social 言語 | varchar(255) |
| sociallatlong | 廃止。Social 緯度／経度 | varchar(255) |
| socialowneddefinitioninsighttype | 廃止。Social 所有定義インサイトの種類 | varchar(255) |
| socialowneddefinitioninsightvalue | 廃止。Social 所有定義インサイト値 | varchar(255) |
| socialowneddefinitionmetric | 廃止。Social 所有定義指標 | varchar(255) |
| socialowneddefinitionpropertyvspost | 廃止。Social 所有定義プロパティと投稿 | varchar(255) |
| socialownedpostids | 廃止。Social 所有投稿 ID | varchar(255) |
| socialownedpropertyid | 廃止。Social 所有プロパティ ID | varchar(255) |
| socialownedpropertyname | 廃止。Social 所有プロパティ名 | varchar(255) |
| socialownedpropertypropertyvsapp | 廃止。Social 所有プロパティとアプリ | varchar(255) |
| state | 状態変数。 | varchar(50) |
| stats_server | 未使用。ヒットを処理したアドビの内部サーバー。 | char(30) |
| t_time_info | 訪問者の現地時刻。形式を次に示します。M/D/YYYY HH:MM:SS Month（0-11，0=1月）タイムゾーンのオフセット（分単位） | varchar(100) |
| tnt | Adobe Target 統合で使用されます。 | text |
| tnt_action | Adobe Target 統合で使用されます。 | text |
| tnt_post_vista | 廃止。代わりに post_tnt を使用してください。 | text |
| transactionid | データソースを使用して後から様々なデータポイントをアップロードするための一意の識別子。 | text |
| truncated_hit | イメージリクエストが切り捨てられたことを示すフラグ。部分的なヒットを受信したことを示します。<br>Y:ヒットが切り捨てられました。部分的なヒット数 <br>N:ヒットが切り捨てられなかった問題を修正しました。全ヒット受信 | char(1) |
| ua_color | 廃止。以前、色深度のフォールバックとして使用されていました。 | char(20) |
| ua_os | 廃止。以前、オペレーティングシステムのフォールバックとして使用されていました。 | char(80) |
| ua_pixels | 廃止。以前、ブラウザーの高さと幅のフォールバックとして使用されていました。 | char(20) |
| user_agent | イメージリクエストの HTTP ヘッダーで送信されたユーザーエージェント文字列。 | text |
| user_hash | 未使用。レポートスイート ID のハッシュ。代わりに username を使用してください。 | int unsigned |
| user_server | 「サーバー」ディメンションで使用される変数。 | varchar(100) |
| userid | 未使用。レポートスイート ID の数値 ID。代わりに username を使用してください。 | int unsigned |
| username | ヒットのレポートスイート ID。 | char(40) |
| va_closer_detail | 「ラストタッチの詳細」ディメンションで使用される変数。 | varchar(255) |
| va_closer_id | 「ラストタッチチャネル」ディメンションを識別する数値 ID。この ID の参照はマーケティングチャネルマネージャーにあります。 | tinyint unsigned |
| va_finder_detail | 「ファーストタッチの詳細」ディメンションで使用される変数。 | varchar(255) |
| va_finder_id | 「ファーストタッチチャネル」ディメンションを識別する数値 ID。この ID の参照はマーケティングチャネルマネージャーにあります。 | tinyint unsigned |
| va_instance_event | マーケティングチャネルインスタンスを識別するフラグ。「マーケティングチャネルラストタッチインスタンス」指標で使用されます。 | tinyint unsigned |
| va_new_engagement | マーケティングチャネルの新規エンゲージメントを識別するフラグ。「新規エンゲージメント」指標で使用されます。 | tinyint unsigned |
| video | ビデオコンテンツ | varchar(255) |
| videoad | ビデオ広告名 | varchar(255) |
| videoadinpod | ポッド位置のビデオ広告 | varchar(255) |
| videoadlength | ビデオ広告の長さ | varchar(255) |
| videoadload | ビデオ広告の読み込み | varchar(255) |
| videoadname | ビデオ広告名 | varchar(255) |
| videoadplayername | ビデオ広告プレーヤー名 | varchar(255) |
| videoadpod | ビデオ広告ポッド | varchar(255) |
| videoadvertiser | ビデオ広告主 | varchar(255) |
| videoaudioalbum | ビデオオーディオアルバム | varchar(255) |
| videoaudioartist | ビデオオーディオアーティスト | varchar(255) |
| videoauditoauthor | ビデオオーディオ作成者 | varchar(255) |
| videoaudiolabel | ビデオオーディオラベル | varchar(255) |
| videoaudiopuubler | ビデオオーディオパブリッシャー | varchar(255) |
| videoaudiostation | ビデオオーディオステーション | varchar(255) |
| videocampaign | ビデオキャンペーン | varchar(255) |
| videochannel | ビデオチャネル | varchar(255) |
| videochapter | ビデオチャプター名 | varchar(255) |
| videocontenttype | ビデオコンテンツタイプ。すべてのビデオ視聴で、自動的に「ビデオ」に設定されます。 | varchar(255) |
| videodaypart | ビデオ日パート | varchar(255) |
| videoepisode | ビデオエピソード | varchar(255) |
| videofeedtype | ビデオフィードのタイプ | varchar(255) |
| videogenre | ビデオジャンル | text |
| videolength | ビデオの長さ | varchar(255) |
| videomvpd | ビデオMVPD | varchar(255) |
| videoname | ビデオ名 | varchar(255) |
| videonetwork | ビデオネットワーク | varchar(255) |
| videopath | ビデオパス | varchar(100) |
| videoplayername | ビデオプレイヤー名 | varchar(255) |
| videoqoebitrateaverageevar | ビデオ画質平均ビットレート | varchar(255) |
| videoqoebitratechangecountevar | ビデオ画質変更回数 | varchar(255) |
| videoqoebuffercountevar | ビデオ画質バッファ数 | varchar(255) |
| videoqoebuffertimeevar | ビデオ画質バッファー時間 | varchar(255) |
| videoqoedroppedframecountevar | ビデオ画質ドロップフレーム数 | varchar(255) |
| videoqoeerrorcountevar | ビデオ画質エラー数 | varchar(255) |
| videoqoeexternalerrors | ビデオ画質外部エラー | text |
| videoqoeplayersdkerrors | ビデオ画質SDKエラー | text |
| videoqoetimetostartevar | ビデオ画質開始時間 | varchar(255) |
| videoseason | ビデオシーズン | varchar(255) |
| videosegment | ビデオセグメント | varchar(255) |
| videoshow | ビデオショー | varchar(255) |
| videoshowtype | ビデオショータイプ | varchar(255) |
| videostreamtype | ビデオストリームタイプ | varchar(255) |
| visid_high | visid_low と組み合わせて使用し、訪問を一意に識別します。 | bigint unsigned |
| visid_low | visid_high と組み合わせて使用し、訪問を一意に識別します。 | bigint unsigned |
| visid_new | 新しく生成された訪問者 ID がヒットに含まれているかどうかを識別するフラグ。 | char(1) |
| visid_timestamp | 訪問者 ID が新しく生成された場合は、訪問者 ID が生成された時刻のタイムスタンプ（UNIX 時間）を示します。 | int |
| visid_type | 訪問者の識別に使用された方法を表す数値 ID。<br>0:カスタムvisitorID <br>1:IPおよびユーザーエージェントフォールバック <br>2:HTTPモバイル加入者ヘッダー <br>3:レガシーcookieの値（s_ vi） <br>4:フォールバックcookieの値（s_ fid） <br>5:IDサービス | tinyint unsigned |
| visit_keywords | 「検索キーワード」ディメンションで使用される変数。この列では、アドビが使用するバックエンドロジックに対応するために、標準以外の文字制限を使用します。 | varchar(244) |
| visit_num | 「通算訪問回数」ディメンションで使用される変数。1 から始まり、訪問者ごとに新しい訪問が開始されるたびに増分されます。 | int unsigned |
| visit_page_num | 「ヒットの深さ」ディメンションで使用される変数。ユーザーがヒットを生成するたびに 1 ずつ増えます。訪問ごとにリセットされます。 | int unsigned |
| visit_ref_domain | visit_referrer 列に基づきます。訪問の最初の参照ドメイン。 | varchar(100) |
| visit_ref_type | 訪問の最初のリファラーのリファラータイプを表す数値 ID。referrer_type.tsv 参照テーブルを使用します。 | tinyint unsigned |
| visit_referrer | 訪問の最初のリファラー。 | varchar(255) |
| visit_search_engine | 訪問の最初の検索エンジンを表す数値 ID。search_engines.tsv 参照テーブルを使用します。 | smallint unsigned |
| visit_start_page_url | 訪問の最初の URL。 | varchar(255) |
| visit_start_pagename | 訪問の最初のページ名。 | varchar(100) |
| visit_start_time_gmt | 訪問の最初のヒットのタイムスタンプ（UNIX 時間）。 | int |
| weekly_visitor | ヒットが新しい週別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| yearly_visitor | ヒットが新しい年別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| zip | 「郵便番号」ディメンションの設定に使用されます。 | varchar(50) |