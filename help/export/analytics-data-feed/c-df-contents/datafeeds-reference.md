---
description: データフィードの各列について説明するテーブルデータです。
keywords: データフィード;列
subtopic: data feeds
title: データ列リファレンス
feature: Reports & Analyticsの基本事項
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
exl-id: e1492147-6e7f-4921-b509-898e7efda596
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '3396'
ht-degree: 99%

---

# データ列リファレンス

このページを使用して、各列に含まれるデータを確認します。ほとんどの実装ではすべての列を使用していないので、データフィードの書き出しに含める列を決定する際には、このページを参考にすることができます。

>[!IMPORTANT]
>
>指定された列（例えば、255 文字として定義された列）では、文字列内の値をエスケープする文字の追加により、データフィードは追加の文字を送信する可能性があります。実装によって文字制限を超える値を定期的に送信する場合は、これらの追加の文字の可能性に注意してください。

## 列、説明、データタイプ

>[!NOTE]
>
>ほとんどの列には、`post_` というプレフィックスが付く類似の列が含まれています。post 列には、サーバー側ロジック、処理ルール、VISTA ルールの適用後の値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。詳しくは、[データフィードに関する FAQ](../df-faq.md) を参照してください。

| 列名 | 列の説明 | データタイプ |
| --- | --- | --- |
| `accept_language` | イメージリクエストの Accept-Language HTTP ヘッダーで指定されている受け入れ可能なすべての言語のリスト。 | char(20) |
| `aemassetid` | 一連の Adobe Experience Manager Assets のアセット ID（GUID）に対応する複数値変数。インプレッションイベント数が増分されます。 | テキスト |
| `aemassetsource` | アセットイベントのソースを識別します。Adobe Experience Manager で使用されます。 | varchar(255) |
| `aemclickedassetid` | Adobe Experience Manager アセットのアセット ID。クリックイベント数が増分されます。 | varchar(255) |
| `browser` | ブラウザーの数値 ID。`browser.tsv` ルックアップテーブルを参照します。 | int unsigned |
| `browser_height` | ブラウザーウィンドウの高さ（ピクセル単位）。 | smallint unsigned |
| `browser_width` | ブラウザーウィンドウの幅（ピクセル単位）。 | smallint unsigned |
| `c_color` | カラーパレットのビット深度。「[色深度](/help/components/dimensions/color-depth.md)」ディメンションの計算の一環として使用されます。AppMeasurement では JavaScript 関数 `screen.colorDepth()` が使用されます。 | char(20) |
| `campaign` | 「[トラッキングコード](/help/components/dimensions/tracking-code.md)」ディメンションで使用される変数。 | varchar(255) |
| `carrier` | Adobe Advertising Cloud 統合変数。携帯電話会社を指定します。`carrier`ルックアップテーブルを参照します。 | varchar(100) |
| `channel` | 「[サイトセクション](/help/components/dimensions/site-section.md)」ディメンションで使用される変数。 | varchar(100) |
| `click_action` | 廃止。レガシー ClickMap ツール内でクリックされたリンクのアドレス。 | varchar(100) |
| `click_action_type` | 廃止。レガシー ClickMap ツールのリンクタイプ。<br>0：HREF URL<br>1：カスタム ID<br>2：JavaScript onClick イベント<br>3：フォーム要素 | tinyint unsigned |
| `click_context` | 廃止。リンククリックが発生したページの名前。レガシー ClickMap ツールの一部。 | varchar(255) |
| `click_context_type` | 廃止。click_context の値がページ名であったかデフォルトのページ URL であったかを示します。<br>0：ページ URL<br>1：ページ名 | tinyint unsigned |
| `click_sourceid` | 廃止。クリックされたリンクが配置されているページ上の場所の数値 ID。レガシー ClickMap ツールの一部。 | int unsigned |
| `click_tag` | 廃止。クリックされた HTML 要素のタイプ。 | char(10) |
| `clickmaplink` | Activity Mapリンク | varchar(255) |
| `clickmaplinkbyregion` | Activity Map 地域別リンク | varchar(255) |
| `clickmappage` | Activity Map ページ | varchar(255) |
| `clickmapregion` | Activity Map 地域 | varchar(255) |
| `code_ver` | イメージリクエストのコンパイルと送信に使用される AppMeasurement Library のバージョン。 | char(16) |
| `color` | `c_color` 列の値に基づいく色深度 ID。`color_depth.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| `connection_type` | 接続タイプを表す数値 ID。「[接続タイプ](/help/components/dimensions/connection-type.md)」ディメンションで使用される変数。`connection_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| `cookies` | 「[cookie サポート](/help/components/dimensions/cookie-support.md)」ディメンションで使用される変数。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| `country` | ヒットの発生元となった国を表す数値 ID。「[国](/help/components/dimensions/countries.md)」ディメンションで使用されます。`country.tsv` ルックアップを使用します。 | smallint unsigned |
| `ct_connect_type` | `connection_type` 列と関連しています。よく使用される値は LAN/Wi-Fi、Mobile Carrier、Modem です。 | char(20) |
| `curr_factor` | 通貨の小数点以下の桁数を指定します。通貨の変換に使用されます。例えば、USD では小数点以下 2 桁を使用するので、この列の値は 2 になります。 | tinyint |
| `curr_rate` | トランザクションが発生した時点の為替レート。アドビでは XE 社との提携により、当日の為替レートを決定しています。 | decimal(24,12) |
| `currency` | 取引で使用された通貨のコード。 | char(8) |
| `cust_hit_time_gmt` | タイムスタンプに対応するレポートスイートの場合のみ。ヒットと共に送信されたタイムスタンプ（UNIX 時間）。 | int |
| `cust_visid` | カスタム訪問者 ID が設定されている場合は、それがこの列に格納されます。 | varchar(255) |
| `daily_visitor` | ヒットが新しい日別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| `date_time` | レポートスイートのタイムゾーンに基づいて判読可能な形式で表現されたヒットの時刻。 | 日時 |
| `domain` | 「[ドメイン](/help/components/dimensions/domain.md)」ディメンションで使用される変数。訪問者のインターネットアクセスポイントに基づいています。 | varchar(100) |
| `duplicate_events` | 重複としてカウントされた各イベントを列挙します。 | varchar(255) |
| `duplicate_purchase` | このヒットの購入イベントが重複しているので無視する必要があることを示すフラグ。 | tinyint unsigned |
| `duplicated_from` | ヒットコピー VISTA ルールを含んだレポートスイートでのみ使用されます。ヒットのコピー元となったレポートスイートを示します。 | varchar(40) |
| `ef_id` | Adobe Advertising Cloud 統合で使用される `ef_id` | varchar(255) |
| `evar1 - evar250` | カスタム変数 1 ～ 250。「[eVar](/help/components/dimensions/evar.md)」ディメンションで使用されます。eVar の使用方法は組織ごとに異なります。組織における各 eVar への値の設定方法について詳しくは、それぞれの組織に固有のソリューションデザインドキュメントを参照してください。 | varchar(255) |
| `event_list` | ヒットで発生したイベントを表す数値 ID のコンマ区切りリスト。デフォルトイベントもカスタムイベント 1 ～ 1000 も含まれています。`event.tsv` ルックアップを使用します。 | テキスト |
| `exclude_hit` | ヒットがレポートから除外されていることを示すフラグ。除外されたヒットに対しては `visit_num` 列が増分されません。<br>1：未使用。削除されたフィーチャの一部。<br>2：未使用。削除されたフィーチャの一部。<br>3：廃止。ユーザーエージェントの除外<br>4：IP アドレスに基づく除外<br>5：重要なヒット情報が欠落しています。例：`page_url`、`pagename`、`page_event`、`event_list`<br> 6：JavaScript でヒットが正しく処理されませんでした<br>7：アカウント固有の除外（VISTA ルールなど）<br>8：未使用。代替のアカウント固有の除外。<br>9：未使用。削除されたフィーチャの一部。<br>10：無効な通貨コード<br>11：タイムスタンプのみのレポートスイートでヒットにタイムスタンプが含まれていない、またはタイムスタンプ以外のレポートスイートでヒットにタイムスタンプが含まれている<br>12:未使用。削除されたフィーチャの一部。<br>13：未使用。削除されたフィーチャの一部。<br>14：Analytics と一致しないターゲットヒット<br>15：現在は使用されていません。<br>16：Analytics ヒットと一致しない Advertising Cloud ヒット | tinyint unsigned |
| `first_hit_page_url` | 訪問者の本当に最初の URL。 | varchar(255) |
| `first_hit_pagename` | 「[オリジナルの入口ページ](/help/components/dimensions/entry-dimensions.md)」ディメンションで使用される変数。訪問者のオリジナルの入口ページ名。 | varchar(100) |
| `first_hit_ref_domain` | 「[オリジナルの参照ドメイン](/help/components/dimensions/original-referring-domain.md)」ディメンションで使用される変数。`first_hit_referrer` に基づきます。訪問者の本当に最初の参照ドメイン。 | varchar(100) |
| `first_hit_ref_type` | 訪問者の本当に最初のリファラーのリファラータイプを表す数値 ID。`referrer_type.tsv` ルックアップを使用します。 | tinyint unsigned |
| `first_hit_referrer` | 訪問者の本当に最初の参照 URL。 | varchar(255) |
| `first_hit_time_gmt` | 訪問者の本当に最初のヒットのタイムスタンプ（UNIX 時間）。 | int |
| `geo_city` | ヒットの発生元となった市区町村の名前（IP アドレスに基づく）。「[市区町村](/help/components/dimensions/cities.md)」ディメンションで使用されます。 | char(32) |
| `geo_country` | ヒットの発生元となった国の略称（IP アドレスに基づく）。 | char(4) |
| `geo_dma` | ヒットの発生元となった人口分布地域の数値 ID（IP アドレスに基づく）。「[米国 DMA](/help/components/dimensions/us-dma.md)」ディメンションで使用されます。 | int unsigned |
| `geo_region` | ヒットの発生元となった州または地域の名前（IP アドレスに基づく）。「[地域](/help/components/dimensions/regions.md)」ディメンションで使用されます。 | char(32) |
| `geo_zip` | ヒットの発生元となった場所の郵便番号（IP アドレスに基づく）。「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンションの入力に役立ちます。関連トピック `zip`. | varchar(16) |
| `hier1 - hier5` | 階層変数で使用され、値の区切りリストが含まれます。区切り文字は、レポートスイートの設定に基づいて選択されます。 | varchar(255) |
| `hit_source` | ヒットの発生源を示します。ヒットソース 1、2、6 に対して請求が行われます。<br>1：標準的なイメージリクエスト（タイムスタンプなし）<br>2：標準的なイメージリクエスト（タイムスタンプあり）<br>3：ライブデータソースのアップロード（タイムスタンプあり）<br>4：未使用<br>5：汎用データソースのアップロード<br>6：完全な処理データソースのアップロード<br>7：TransactionID データソースのアップロード<br>8：廃止。Adobe Advertising Cloud の以前のバージョンのデータソース<br>9：廃止。Adobe Social サマリ指標<br>10：Audience Manager サーバーサイド転送を使用 | tinyint unsigned |
| `hit_time_gmt` | Unix 時間に基づく、ヒットを受け取ったアドビデータ収集サーバーのタイムスタンプ。 | int |
| `hitid_high` | `hitid_low` と組み合わせて使用し、ヒットを一意に識別します。 | bigint unsigned |
| `hitid_low` | `hitid_high` と組み合わせて使用し、ヒットを一意に識別します。 | bigint unsigned |
| `homepage` | 廃止。現在の URL がブラウザーのホームページかどうかを示します。 | char(1) |
| `hourly_visitor` | ヒットが新しい時間別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| `ip` | イメージリクエストの HTTP ヘッダーに基づく IP アドレス。 | char(20) |
| `ip2` | 未使用。IP アドレスに基づく VISTA ルールを含んだレポートスイートのバックエンド参照変数。 | char(20) |
| `j_jscript` | ブラウザーでサポートされている JavaScript のバージョン。 | char(5) |
| `java_enabled` | Java が有効かどうかを示すフラグ。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| `javascript` | JavaScript のバージョンの参照 ID（`j_jscript` に基づく）。参照テーブルを使用します。 | tinyint unsigned |
| `language` | 言語の数値 ID。`languages.tsv` ルックアップテーブルを使用します。 | smallint unsigned |
| `last_hit_time_gmt` | 前回のヒットのタイムスタンプ（UNIX 時間）。「[最終訪問からの日数](/help/components/dimensions/days-since-last-visit.md)」ディメンションの計算に使用されます。 | int |
| `last_purchase_num` | 「[顧客の忠誠度](/help/components/dimensions/customer-loyalty.md)」ディメンションで使用される変数。訪問者がこれまでにおこなった購入の回数。<br>0：過去に購入したことがない（顧客以外）<br>1：過去に 1 回購入したことがある（新規顧客）<br>2：過去に 2 回購入したことがある（リターン顧客）<br>3：過去に 3 回以上購入したことがある（常連客） | int unsigned |
| `last_purchase_time_gmt` | 「[前回購入からの日数](/help/components/dimensions/days-since-last-purchase.md)」ディメンションで使用されます。前回おこなった購入のタイムスタンプ（UNIX 時間）。初回の購入やこれまでに購入をおこなっていない訪問者の場合、この値は `0` になります。 | int |
| `latlon1` | ロケーション（半径 10 km 以内） | varchar(255) |
| `latlon23` | ロケーション（半径 100 m 以内） | varchar(255) |
| `latlon45` | ロケーション（半径 1 m 以内） | varchar(255) |
| `mc_audiences` | 訪問者が属している Audience Manager セグメント ID のリスト。 | テキスト |
| `mcvisid` | Experience Cloud 訪問者 ID。2 つの 64 ビット数値を連結して 19 桁にパディングした 128 ビット数値です。 | varchar(255) |
| `mobile_id` | ユーザーがモバイルデバイスを使用している場合は、そのデバイスの数値 ID。 | int |
| `mobileaction` | モバイルアクション。Mobile Services で `trackAction` が呼び出されると、自動的に収集されます。アプリケーション内で自動的にアクションを渡すことができるようにします。 | varchar(100) |
| `mobileappid` | モバイルアプリケーション ID。アプリケーションの名前とバージョンを次の形式で格納します。  `[AppName] [BundleVersion]` | varchar(255) |
| `mobileappperformanceappid` | Apteligent データコネクタで使用されます。Apteligent で使用されるアプリケーション ID。 | varchar(255) |
| `mobileappperformancecrashid` | Apteligent データコネクタで使用されます。Apteligent で使用されるクラッシュ ID。 | varchar(255) |
| `mobileappstoreobjectid` | Appfigures データコネクタで使用されます。App Store オブジェクト ID。 | varchar(255) |
| `mobilebeaconmajor` | Mobile Services ビーコンのメジャー番号 | varchar(100) |
| `mobilebeaconminor` | Mobile Services ビーコンのマイナー番号 | varchar(100) |
| `mobilebeaconproximity` | Mobile Services ビーコンの近接性 | varchar(255) |
| `mobilebeaconuuid` | Mobile Services ビーコンの UUID | varchar(100) |
| `mobilecampaigncontent` | リンクを表示したコンテンツの名前または ID。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignmedium` | マーケティングメディア（バナー、電子メールなど）。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignname` | キャンペーンの名前。キャンペーン変数にも格納されます。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignsource` | オリジナルリファラー（ニュースレターやソーシャルメディアネットワークなど）。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignterm` | この獲得で追跡する有料キーワードまたはその他の用語。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobiledayofweek` | アプリが起動された曜日を表す数値。 | varchar(255) |
| `mobiledayssincefirstuse` | アプリの初回実行時からの経過日数。 | varchar(255) |
| `mobiledayssincelastupgrade` | コンテキストデータ変数 a.DaysSinceLastUpgrade から収集されます。前回のセッションからの経過日数。 | varchar(255) |
| `mobiledayssincelastuse` | アプリの前回実行時からの経過日数。 | varchar(255) |
| `mobiledeeplinkid` | コンテキストデータ変数 `a.deeplink.id` から収集します。獲得レポートで、モバイル獲得リンクの識別子として使用されます。 | varchar(255) |
| `mobiledevice` | モバイルデバイス名。iOS の場合は、コンマ区切りの 2 桁の文字列として格納されます。最初の番号はデバイスの世代を表し、2 番目の番号はデバイスファミリーを表します。 | varchar(255) |
| `mobilehourofday` | アプリが起動された時刻を示します。24 時間形式に従います。 | varchar(255) |
| `mobileinstalldate` | モバイルインストール日。モバイルアプリをユーザーが最初に起動した日を示します。 | varchar(255) |
| `mobilelaunchessincelastupgrade` | コンテキストデータ変数 a.LaunchesSinceUpgrade から取得します。前回のアップグレード以降の起動回数を報告します。 | varchar(255) |
| `mobilelaunchnumber` | モバイルアプリが起動されるたびに 1 ずつ増分されます。 | varchar(255) |
| `mobileltv` | 廃止。trackLifetimeValue メソッドによって設定されます。 | varchar(255) |
| `mobilemessagebuttonname` | コンテキストデータ変数 `a.message.button.id` から収集します。メッセージを閉じたボタンを識別するために、アプリ内メッセージで使用します。 | varchar(100) |
| `mobilemessageid` | アプリ内メッセージ ID | varchar(255) |
| `mobilemessageonline` | アプリ内メッセージオンライン | varchar(255) |
| `mobilemessagepushoptin` | コンテキストデータ変数 `a.push.optin` から収集します。ユーザーがプッシュメッセージをオプトインする場合は「true」に設定します。それ以外の場合、値は「false」です。 | varchar(255) |
| `mobilemessagepushpayloadid` | コンテキストデータ変数 `a.push.payloadid` から収集します。ペイロード識別子としてプッシュメッセージで使用します。 | varchar(255) |
| `mobileosenvironment` | コンテキストデータ変数 `a.OSEnvironment` から収集します。Android や iOS などの OS 環境を示します。 | varchar(255) |
| `mobileosversion` | Mobile Services のオペレーティングシステムのバージョン。 | varchar(255) |
| `mobileplaceaccuracy` | コンテキストデータ変数 `a.loc.acc` から収集します。収集時の GPS の精度をメートル単位で示します。 | varchar(255) |
| `mobileplacecategory` | コンテキストデータ変数 `a.loc.category` から収集します。特定の場所のカテゴリを示します。 | varchar(255) |
| `mobileplaceid` | コンテキストデータ変数 `a.loc.id` から収集します。特定の目標地点の識別子。 | varchar(255) |
| `mobilerelaunchcampaigncontent` | Mobile Services の起動コンテンツ | varchar(255) |
| `mobilerelaunchcampaignmedium` | Mobile Services の起動メディア | varchar(255) |
| `mobilerelaunchcampaignsource` | Mobile Services の起動ソース | varchar(255) |
| `mobilerelaunchcampaignterm` | Mobile Services の起動条件 | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | コンテキストデータ変数 `a.launch.campaign.trackingcode` から収集します。キャンペーン立ち上げのトラッキングコードとして、獲得で使用します。 | varchar(255) |
| `mobileresolution` | モバイルデバイスの解像度。`[Width] x [Height]` 画素数. | varchar(255) |
| `monthly_visitor` | 当月の月別訪問者であることを示すフラグ。 | tinyint unsigned |
| `mvvar1`～`mvvar3` | リスト変数値。実装に応じて、カスタム値の区切りリストを格納します。 | テキスト |
| `namespace` | 未使用。削除されたフィーチャの一部。 | varchar(50) |
| `new_visit` | 現在のヒットが新しい訪問であるかどうかを指定するフラグ。訪問がアクティブでなくなった 30 分後にアドビのサーバーによって設定されます。 | tinyint unsigned |
| `os` | 訪問者のオペレーティングシステムを表す数値 ID。`user_agent` 列に基づきます。`os` ルックアップを使用します。 | int unsigned |
| `p_plugins` | 廃止。ブラウザーで使用可能なプラグインのリスト。JavaScript 関数 `navigator.plugins()` を使用します。 | テキスト |
| `page_event` | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、カスタムリンク、離脱リンク）。[ページイベント参照](datafeeds-page-event.md)を参照してください。 | tinyint unsigned |
| `page_event_var1` | リンクトラッキングイメージリクエストでのみ使用されます。クリックされたダウンロードリンク、離脱リンク、カスタムリンクの URL。 | テキスト |
| `page_event_var2` | リンクトラッキングイメージリクエストでのみ使用されます。リンクのカスタム名（指定された場合）。 | varchar(100) |
| `page_event_var3` | 廃止。調査モジュールやメディアモジュールのデータが格納されます。Adobe Analytics の以前のバージョンで設定されたレガシービデオレポート。 | テキスト |
| `page_type` | 「[エラーページ](/help/components/dimensions/pages-not-found.md)」ディメンションの入力に使用。404 エラーページにのみ使用されます。この変数の値は、空か「`ErrorPage`」である必要があります。 | char(20) |
| `page_url` | ヒットの URL。リンクトラッキング画像リクエストから削除されます。 | varchar(255) |
| `pagename` | 「[ページ](/help/components/dimensions/page.md)」ディメンションの入力に使用されます。[`pagename`](/help/implement/vars/page-vars/pagename.md) 変数が空の場合、Analytics では代わりに `page_url` が使用されます。 | varchar(100) |
| `paid_search` | ヒットが有料検索の検出に一致した場合に設定されるフラグ。 | tinyint unsigned |
| `partner_plugins` | 未使用。削除されたフィーチャの一部。 | varchar(255) |
| `persistent_cookie` | 「[永続的な cookie のサポート](/help/components/dimensions/persistent-cookie-support.md)」ディメンションで使用されます。各ヒットの後で破棄されない Cookie を訪問者がサポートしているかどうかを示します。 | char(1) |
| `plugins` | 廃止。ブラウザー内で使用可能なプラグインに対応する数値 ID のリスト。`plugins.tsv` ルックアップを使用します。 | varchar(180) |
| `pointofinterest` | Mobile Services 目標地点の名前 | varchar(255) |
| `pointofinterestdistance` | 目標地点中心までの Mobile Services の距離 | varchar(255) |
| `post_` 列 | レポートで最終的に使用された値が格納されます。各 post 列には、サーバー側ロジック、処理ルール、VISTA ルールの適用後に値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。 | post 以外の各列を参照してください。 |
| `prev_page` | 未使用。前のページの Adobe 独自の識別子。 | int unsigned |
| `product_list` | [`products`](/help/implement/vars/page-vars/products.md) 変数を通じて渡される製品リスト。製品はコンマで区切られますが、個々の製品プロパティはセミコロンで区切られます。 | テキスト |
| `product_merchandising` | 未使用。代わりに、`product_list` を使用してください。 | テキスト |
| `prop1`～`prop75` | カスタムトラフィック変数 1 ～ 75。「[Prop](/help/components/dimensions/prop.md)」ディメンションで使用されます。 | varchar(100) |
| `purchaseid` | 購入の一意な識別子（[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) 変数を使用して設定）。`duplicate_purchase` 列で使用されます。 | char(20) |
| `quarterly_visitor` | ヒットが新しい四半期別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| `ref_domain` | referrer 列に基づきます。ヒットの参照ドメイン。「[参照ドメイン](/help/components/dimensions/referring-domain.md)」ディメンションで使用されます。 | varchar(100) |
| `ref_type` | ヒットのリファラルのタイプを表す数値 ID。「[リファラータイプ](/help/components/dimensions/referrer-type.md)」ディメンションで使用されます。<br>1：サイト内<br>2：その他の Web サイト<br>3：検索エンジン<br>4：ハードドライブ<br>5：USENET<br>6：手動入力／ブックマーク（リファラーなし）<br>7：電子メール<br>8：JavaScript なし<br>9：ソーシャルネットワーク | tinyint unsigned |
| `referrer` | 前のページのページ URL。「[リファラー](/help/components/dimensions/referrer.md)」ディメンションで使用されます。`referrer` のデータ型は varchar(255)、`post_referrer` のデータ型は varchar(244) です。 | varchar(255) |
| `resolution` | モニターの解像度を表す数値 ID。「[画面の解像度](/help/components/dimensions/monitor-resolution.md)」ディメンションで使用されます。`resolution.tsv` ルックアップテーブルを使用します。 | smallint unsigned |
| `s_kwcid` | Adobe Advertising Cloud 統合で使用されるキーワード ID。 | varchar(255) |
| `s_resolution` | 画面解像度の生の値。JavaScript 関数 `screen.width x screen.height` を使用して収集します。 | char(20) |
| `search_engine` | サイトに訪問者を誘導した検索エンジンを表す数値 ID。`search_engines.tsv` ルックアップを使用します。 | smallint unsigned |
| `search_page_num` | 「[すべての検索ページのランク](/help/components/dimensions/all-search-page-rank.md)」ディメンションで使用されます。ユーザーがクリックスルーしてサイトに到達する前にサイトが表示された検索結果ページを示します。 | smallint unsigned |
| `secondary_hit` | 二次的なヒットを追跡するフラグ。通常、ヒットをコピーするマルチスイートタグ付けおよび VISTA ルールで発生します。 | tinyint unsigned |
| `service` | 未使用。代わりに、`page_event` を使用してください。 | char(2) |
| `socialaccountandappids` | 廃止。Social アカウントおよびアプリ ID | varchar(255) |
| `socialassettrackingcode` | 廃止。Social キャンペーン変数 | varchar(255) |
| `socialauthor` | 廃止。Social 発言者変数 | varchar(255) |
| `socialcontentprovider` | 廃止。Social プラットフォーム／プロパティ | varchar(255) |
| `socialinteractiontype` | 廃止。Social インタラクションタイプ | varchar(255) |
| `sociallanguage` | 廃止。Social 言語 | varchar(255) |
| `sociallatlong` | 廃止。Social 緯度／経度 | varchar(255) |
| `socialowneddefinitioninsighttype` | 廃止。Social 所有定義インサイトの種類 | varchar(255) |
| `socialowneddefinitioninsightvalue` | 廃止。Social 所有定義インサイト値 | varchar(255) |
| `socialowneddefinitionmetric` | 廃止。Social 所有定義指標 | varchar(255) |
| `socialowneddefinitionpropertyvspost` | 廃止。Social 所有定義プロパティと投稿 | varchar(255) |
| `socialownedpostids` | 廃止。Social 所有投稿 ID | varchar(255) |
| `socialownedpropertyid` | 廃止。Social 所有プロパティ ID | varchar(255) |
| `socialownedpropertyname` | 廃止。Social 所有プロパティ名 | varchar(255) |
| `socialownedpropertypropertyvsapp` | 廃止。Social 所有プロパティとアプリ | varchar(255) |
| `state` | 状態変数。 | varchar(50) |
| `stats_server` | 未使用。ヒットを処理したアドビの内部サーバー。 | char(30) |
| `t_time_info` | 訪問者の現地時刻。形式：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| `tnt` | Adobe Target 統合で使用されます。 | テキスト |
| `tnt_action` | Adobe Target 統合で使用されます。 | テキスト |
| `tnt_post_vista` | 廃止。代わりに、`post_tnt` を使用してください。 | テキスト |
| `transactionid` | データソースを使用して後から様々なデータポイントをアップロードするための一意の識別子。[`transactionID`](/help/implement/vars/page-vars/transactionid.md) 変数を使用して収集します。 | テキスト |
| `truncated_hit` | イメージリクエストが切り捨てられたことを示すフラグ。部分的なヒットを受信したことを示します。<br>Y：ヒットが切り捨てられました。ヒットの一部を受信しました。<br>N：ヒットが切り捨てられませんでした。すべてのヒットを受信しました。 | char(1) |
| `ua_color` | 廃止。以前、色深度のフォールバックとして使用されていました。 | char(20) |
| `ua_os` | 廃止。以前、オペレーティングシステムのフォールバックとして使用されていました。 | char(80) |
| `ua_pixels` | 廃止。以前、ブラウザーの高さと幅のフォールバックとして使用されていました。 | char(20) |
| `user_agent` | イメージリクエストの HTTP ヘッダーで送信されたユーザーエージェント文字列。 | テキスト |
| `user_hash` | 未使用。レポートスイート ID のハッシュ。代わりに、`username` を使用してください。 | int unsigned |
| `user_server` | 「[サーバー](/help/components/dimensions/server.md)」ディメンションで使用されます。 | varchar(100) |
| `userid` | 未使用。レポートスイート ID の数値 ID。代わりに、`username` を使用してください。 | int unsigned |
| `username` | ヒットのレポートスイート ID。 | char(40) |
| `va_closer_detail` | 「[ラストタッチの詳細](/help/components/dimensions/last-touch-detail.md)」ディメンションで使用される変数。 | varchar(255) |
| `va_closer_id` | 「[ラストタッチチャネル](/help/components/dimensions/last-touch-channel.md)」ディメンションを識別する数値 ID。この ID の参照はマーケティングチャネルマネージャーにあります。 | tinyint unsigned |
| `va_finder_detail` | 「[ファーストタッチの詳細](/help/components/dimensions/first-touch-detail.md)」ディメンションで使用される変数。 | varchar(255) |
| `va_finder_id` | 「[ファーストタッチチャネル](/help/components/dimensions/first-touch-channel.md)」ディメンションを識別する数値 ID。この ID の参照はマーケティングチャネルマネージャーにあります。 | tinyint unsigned |
| `va_instance_event` | マーケティングチャネル[インスタンス](/help/components/metrics/instances.md)を識別するフラグ。 | tinyint unsigned |
| `va_new_engagement` | マーケティングチャネルの[新規エンゲージメント](/help/components/metrics/new-engagements.md)を識別するフラグ。 | tinyint unsigned |
| `video` | ビデオコンテンツ | varchar(255) |
| `videoad` | ビデオ広告名 | varchar(255) |
| `videoadinpod` | ポッド位置のビデオ広告 | varchar(255) |
| `videoadlength` | ビデオ広告の長さ | varchar(255) |
| `videoadload` | ビデオ広告の読み込み | varchar(255) |
| `videoadname` | ビデオ広告名 | varchar(255) |
| `videoadplayername` | ビデオ広告プレイヤー名 | varchar(255) |
| `videoadpod` | ビデオ広告ポッド | varchar(255) |
| `videoadvertiser` | ビデオ広告主 | varchar(255) |
| `videoaudioalbum` | ビデオオーディオアルバム | varchar(255) |
| `videoaudioartist` | ビデオオーディオアーティスト | varchar(255) |
| `videoaudioauthor` | ビデオオーディオ作成者 | varchar(255) |
| `videoaudiolabel` | ビデオオーディオラベル | varchar(255) |
| `videoaudiopublisher` | ビデオオーディオ発行者 | varchar(255) |
| `videoaudiostation` | ビデオオーディオステーション | varchar(255) |
| `videocampaign` | ビデオキャンペーン | varchar(255) |
| `videochannel` | ビデオチャンネル | varchar(255) |
| `videochapter` | ビデオチャプター名 | varchar(255) |
| `videocontenttype` | ビデオコンテンツタイプ。すべてのビデオ視聴で、自動的に「ビデオ」に設定されます。 | varchar(255) |
| `videodaypart` | ビデオ日分割 | varchar(255) |
| `videoepisode` | ビデオのエピソード | varchar(255) |
| `videofeedtype` | ビデオフィードのタイプ | varchar(255) |
| `videogenre` | ビデオのジャンル | テキスト |
| `videolength` | ビデオの長さ | varchar(255) |
| `videomvpd` | ビデオ MVPD | varchar(255) |
| `videoname` | ビデオ名 | varchar(255) |
| `videonetwork` | ビデオネットワーク | varchar(255) |
| `videopath` | ビデオパス | varchar(100) |
| `videoplayername` | ビデオプレイヤー名 | varchar(255) |
| `videoqoebitrateaverageevar` | ビデオ画質平均ビットレート | varchar(255) |
| `videoqoebitratechangecountevar` | ビデオ画質変更回数 | varchar(255) |
| `videoqoebuffercountevar` | ビデオ画質バッファ数 | varchar(255) |
| `videoqoebuffertimeevar` | ビデオ画質バッファ時間 | varchar(255) |
| `videoqoedroppedframecountevar` | ビデオ画質ドロップフレーム数 | varchar(255) |
| `videoqoeerrorcountevar` | ビデオ画質エラー数 | varchar(255) |
| `videoqoeextneralerrors` | ビデオ画質の外部エラー | テキスト |
| `videoqoeplayersdkerrors` | ビデオ画質 SDK エラー | テキスト |
| `videoqoetimetostartevar` | ビデオ画質開始時間 | varchar(255) |
| `videoseason` | ビデオシーズン | varchar(255) |
| `videosegment` | ビデオセグメント | varchar(255) |
| `videoshow` | ビデオショー | varchar(255) |
| `videoshowtype` | ビデオショーのタイプ | varchar(255) |
| `videostreamtype` | ビデオストリームのタイプ | varchar(255) |
| `visid_high` | `visid_low` と組み合わせて使用し、訪問者を一意に識別します。 | bigint unsigned |
| `visid_low` | `visid_high` と組み合わせて使用し、訪問者を一意に識別します。 | bigint unsigned |
| `visid_new` | 新しく生成された訪問者 ID がヒットに含まれているかどうかを識別するフラグ。 | char(1) |
| `visid_timestamp` | 訪問者 ID が新しく生成された場合は、訪問者 ID が生成された時刻のタイムスタンプ（UNIX 時間）を示します。 | int |
| `visid_type` | 内部使用のみ。処理の最適化のためにアドビが内部的に使用します。訪問者の識別に使用された方法を表す数値 ID。<br>0：カスタム 訪問者 ID または不明／該当なし<br>1：IP およびユーザーエージェントのフォールバック<br>2：HTTP モバイル加入者ヘッダー<br>3：従来の cookie 値（`s_vi`）<br>4：フォールバック cookie の値（`s_fid`）<br>5：ID サービス | tinyint unsigned |
| `visit_keywords` | 「[検索キーワード](/help/components/dimensions/search-keyword.md)」ディメンションで使用される変数。この列では、アドビが使用するバックエンドロジックに対応するために、標準以外の文字制限である varchar(244) が使用されます。 | varchar(244) |
| `visit_num` | 「[訪問回数](/help/components/dimensions/visit-number.md)」ディメンションで使用される変数。1 から始まり、訪問者ごとに新しい訪問が開始されるたびに増分されます。 | int unsigned |
| `visit_page_num` | 「[ヒットの深度](/help/components/dimensions/hit-depth.md)」ディメンションで使用される変数。ユーザーがヒットを生成するたびに 1 ずつ増えます。訪問ごとにリセットされます。 | int unsigned |
| `visit_ref_domain` | `visit_referrer` 列に基づきます。訪問の最初の参照ドメイン。 | varchar(100) |
| `visit_ref_type` | 訪問の最初のリファラーのリファラータイプを表す数値 ID。`referrer_type.tsv` ルックアップテーブルを使用します。 | tinyint unsigned |
| `visit_referrer` | 訪問の最初のリファラー。 | varchar(255) |
| `visit_search_engine` | 訪問の最初の検索エンジンを表す数値 ID。`search_engines.tsv` ルックアップを使用します。 | smallint unsigned |
| `visit_start_page_url` | 訪問の最初の URL。 | varchar(255) |
| `visit_start_pagename` | 訪問の最初のページ名。 | varchar(100) |
| `visit_start_time_gmt` | 訪問の最初のヒットのタイムスタンプ（UNIX 時間）。 | int |
| `weekly_visitor` | ヒットが新しい週別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| `yearly_visitor` | ヒットが新しい年別訪問者であるかどうかを指定するフラグ。 | tinyint unsigned |
| `zip` | 「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンションの生成に役立ちます。関連トピック `geo_zip`. | varchar(50) |

## 空の列

次の列のリストは未使用で、データは含まれていません。

* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `sourceid`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`
