---
description: データフィードの各列について説明するテーブルデータです。
keywords: データフィード;列
subtopic: data feeds
title: データ列リファレンス
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 808ab76ee3f7c7451f8b3569c282abebbc9ac32f
workflow-type: tm+mt
source-wordcount: '3617'
ht-degree: 67%

---

# データ列リファレンス

このページでは、各列に含まれるデータを確認できます。ほとんどの実装ではすべての列を使用していないので、データフィードの書き出しに含める列を決定する際には、このページを参考にすることができます。

>[!IMPORTANT]
>
>指定された列（例えば、255 文字として定義された列）では、文字列内の値をエスケープする文字の追加により、データフィードは追加の文字を送信する可能性があります。実装によって文字制限を超える値を定期的に送信する場合は、これらの追加の文字の可能性に注意してください。

## 列、説明、データタイプ

>[!NOTE]
>
>ほとんどの列には、`post_` というプレフィックスが付く類似の列が含まれています。post 列には、サーバーサイドロジック、処理ルール、VISTA ルールの適用後の値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。詳しくは、[データフィードに関する FAQ](../df-faq.md) を参照してください。

このテーブルの以前の更新は、このページの [GitHub のコミット履歴](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)で確認できます。

| 列名 | 列の説明 | データタイプ |
| --- | --- | --- |
| **`accept_language`** | イメージリクエストの Accept-Language HTTP ヘッダーで指定されている受け入れ可能なすべての言語のリスト。 | char(20) |
| **`adload`** | メディア広告の読み込み | varchar(255) |
| **`aemassetid`** | 一連のAdobe Experience Manager Assetsのアセット ID （GUID）に対応する複数値の変数。 インプレッションイベント数が増分されます。 | テキスト |
| **`aemassetsource`** | アセットイベントのソースを識別します。Adobe Experience Manager で使用されます。 | varchar(255) |
| **`aemclickedassetid`** | Adobe Experience Manager アセットのアセット ID。クリックイベント数が増分されます。 | varchar(255) |
| **`browser`** | ブラウザーを表す数値 ID。 `browser.tsv` ルックアップテーブルを参照します。 | int unsigned |
| **`browser_height`** | 「[ ブラウザーの高さ ](/help/components/dimensions/browser-height.md)」ディメンション。 | smallint unsigned |
| **`browser_width`** | [ ブラウザーの幅 ](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`c_color`** | カラーパレットのビット深度。「[色深度](/help/components/dimensions/color-depth.md)」ディメンションの計算の一環として使用されます。AppMeasurement では JavaScript 関数 `screen.colorDepth()` が使用されます。 | char(20) |
| **`campaign`** | 「トラッキングCode](/help/components/dimensions/tracking-code.md)[ディメンション。 | varchar(255) |
| **`carrier`** | Adobe Advertising 統合変数。携帯電話会社を指定します。`carrier.tsv` [動的検索](dynamic-lookups.md)のキー値。 | varchar(100) |
| **`ch_hdr`** | HTTP リクエストヘッダーを通じて収集されたクライアントヒント。 | テキスト |
| **`ch_js`** | User-Agent クライアントヒント JavaScript API を通じて収集されたクライアントヒント。 | テキスト |
| **`channel`** | [ サイトセクション ](/help/components/dimensions/site-section.md) ディメンション。 | varchar(100) |
| **`clickmaplink`** | Activity Map リンク | varchar(255) |
| **`clickmaplinkbyregion`** | Activity Map 地域別リンク | varchar(255) |
| **`clickmappage`** | Activity Map ページ | varchar(255) |
| **`clickmapregion`** | Activity Map 地域 | varchar(255) |
| **`code_ver`** | イメージリクエストのコンパイルと送信に使用される API またはクライアント SDK のバージョン。 | char(16) |
| **`color`** | `c_color` 列の値に基づいく色深度 ID。`color_depth.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| **`connection_type`** | 接続タイプを表す数値 ID。 [ 接続タイプ ](/help/components/dimensions/connection-type.md) ディメンション。 `connection_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| **`cookies`** | [Cookie サポート ](/help/components/dimensions/cookie-support.md) ディメンション。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| **`country`** | 訪問者の国を表す数値 ID。 `country.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| **`ct_connect_type`** | `connection_type` 列と関連しています。最も一般的な値は、LAN/Wifi、モバイル キャリア、およびモデムです。 | char(20) |
| **`curr_factor`** | 通貨の小数点以下の桁数を指定します。通貨の変換に使用されます。例えば、USD は小数点以下 2 桁を使用しているので、この列の値は `2` になります。 | tinyint |
| **`curr_rate`** | トランザクションが発生した時点の為替レート。アドビでは XE 社との提携により、当日の為替レートを決定しています。 | decimal(24,12) |
| **`currency`** | トランザクション中に使用された通貨コード。 [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) を使用して設定します。 | char(8) |
| **`cust_hit_time_gmt`** | タイムスタンプに対応するレポートスイートの場合のみ。ヒットと共に送信されたタイムスタンプ（UNIX® 時間に基づく）。 | int |
| **`cust_visid`** | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) を使用して設定されている場合は、カスタム訪問者 ID。 | varchar(255) |
| **`daily_visitor`** | ヒットが新しい日別訪問者かどうかを決定するフラグ。 | tinyint unsigned |
| **`dataprivacyconsentoptin`** | [ 同意管理のオプトイン ](/help/components/dimensions/cm-opt-in.md) ディメンション。 ヒットごとに複数の値が存在する可能性があります（パイプ（`\|`）区切り）。有効な値には、`DMP` および `SELL` などがあります。 | varchar(100) |
| **`dataprivacyconsentoptout`** | [ 同意管理のオプトアウト ](/help/components/dimensions/cm-opt-out.md) ディメンション。 ヒットごとに複数の値が存在する可能性があります（パイプ（`\|`）区切り）。有効な値には、`SSF`、`DMP`、`SELL` などがあります。 | varchar(100) |
| **`dataprivacydmaconsent`** | Adobe Advertisingを通じてサードパーティの広告業者（Googleなど）にAdobe Analyticsからデータを送信することに対して同意が得られるかどうかを識別する値。 詳しくは、[広告の同意](/help/components/dimensions/ad-consent.md)を参照してください。 | varchar(100) |
| **`date_time`** | レポートスイートのタイムゾーンに基づいて判読可能な形式で表現されたヒットの時刻。 | 日時 |
| **`domain`** | [ドメイン](/help/components/dimensions/domain.md)ディメンション。訪問者のインターネット アクセス ポイントに基づきます。 | varchar(100) |
| **`duplicate_events`** | 重複としてカウントされた各イベントを列挙します。 | varchar(255) |
| **`duplicate_purchase`** | このヒットの購入イベントが重複しているので無視されるかどうかを決定するフラグ。 | tinyint unsigned |
| **`duplicated_from`** | ヒットコピー VISTA ルールを含んだレポートスイートでのみ使用されます。ヒットがどのレポートスイートからコピーされたかを示します。 | varchar(40) |
| **`ef_id`** | Adobe Advertising 統合で使用される `ef_id`。 | varchar(255) |
| **`evar1 - evar250`** | カスタム変数 1 ～ 250。「[eVar](/help/components/dimensions/evar.md)」ディメンションで使用されます。eVar の使用方法は組織ごとに異なります。組織における各 eVar への値の設定方法について詳しくは、組織に固有の [ ソリューションデザインドキュメント ](/help/implement/prepare/solution-design.md) を参照してください。 | varchar(255) |
| **`event_list`** | ヒットでトリガーされるイベントを表す数値 ID のコンマ区切りリスト。 デフォルトイベントと [カスタムイベント 1-1000](/help/components/metrics/custom-events.md) の両方が含まれます。 `event.tsv` ルックアップを使用します。 | テキスト |
| **`exclude_hit`** | ヒットをレポートから除外するかどうかを決定するフラグ。 除外されたヒットに対しては `visit_num` 列が増分されません。<br>1：未使用。削除されたフィーチャの一部。<br>2：未使用。削除されたフィーチャの一部。<br>3：廃止。ユーザーエージェントの除外<br>4：IP アドレスに基づく除外<br>5：重要なヒット情報が欠落しています。例：`page_url`、`pagename`、`page_event`、`event_list`<br> 6：JavaScript でヒットが正しく処理されませんでした<br>7：アカウント固有の除外（VISTA ルールなど）<br>8：未使用。代替のアカウント固有の除外。<br>9：未使用。削除されたフィーチャの一部。<br>10：無効な通貨コード<br>11：タイムスタンプのみのレポートスイートでヒットにタイムスタンプが含まれていない、またはタイムスタンプ以外のレポートスイートでヒットにタイムスタンプが含まれている<br>12:未使用。削除されたフィーチャの一部。<br>13：未使用。削除されたフィーチャの一部。<br>14：Analytics と一致しないターゲットヒット<br>15：現在は使用されていません。<br>16：Analytics ヒットと一致しない Advertising Cloud ヒット | tinyint unsigned |
| **`first_hit_page_url`** | 訪問者の本当に最初の URL。 | varchar(255) |
| **`first_hit_pagename`** | [ オリジナルの入口ページ ](/help/components/dimensions/entry-dimensions.md) ディメンション。 訪問者のオリジナルの入口ページ名。 | varchar(100) |
| **`first_hit_ref_domain`** | [ オリジナルの参照ドメイン ](/help/components/dimensions/original-referring-domain.md) ディメンション。 `first_hit_referrer` に基づきます。訪問者の本当に最初の参照ドメイン。 | varchar(100) |
| **`first_hit_ref_type`** | 訪問者の最初のリファラーのリファラータイプを表す数値 ID。 `referrer_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| **`first_hit_referrer`** | 訪問者の本当に最初の参照 URL。 | varchar(255) |
| **`first_hit_time_gmt`** | 訪問者の最初のヒットのタイムスタンプ（UNIX® 時間）。 | int |
| **`geo_city`** | ヒットが発生した市区町村の名前（IP アドレスに基づく）。 「[市区町村](/help/components/dimensions/cities.md)」ディメンションで使用されます。 | char(32) |
| **`geo_country`** | ヒットが発生した国の略称（IP アドレスに基づく）。 [国](/help/components/dimensions/countries.md)ディメンションで使用します。 | char(4) |
| **`geo_dma`** | ヒットが発生したデモグラフィック地域の数値 ID （IP アドレスに基づく）。 「[米国 DMA](/help/components/dimensions/us-dma.md)」ディメンションで使用されます。 | int unsigned |
| **`geo_region`** | ヒットが発生した州または地域の名前（IP アドレスに基づく）。 「[地域](/help/components/dimensions/regions.md)」ディメンションで使用されます。 | char(32) |
| **`geo_zip`** | ヒットが発生した場所の郵便番号（IP アドレスに基づく）。「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンションの入力に役立ちます。関連トピック「 `zip`」を参照してください。 | varchar(16) |
| **`hit_source`** | ヒットが発生したソース。 ヒットソース 1、2、6 に対して請求が行われます。<br>1：標準的なイメージリクエスト（タイムスタンプなし）<br>2：標準的なイメージリクエスト（タイムスタンプあり）<br>3：ライブデータソースのアップロード（タイムスタンプあり）<br>4：未使用<br>5：汎用データソースのアップロード<br>6：完全な処理データソースのアップロード<br>7：TransactionID データソースのアップロード<br>8：廃止。Adobe Advertising Cloud の以前のバージョンのデータソース<br>9：廃止。Adobe Social サマリ指標<br>10：Audience Manager サーバーサイド転送を使用 | tinyint unsigned |
| **`hit_time_gmt`** | ヒットを受信したアドビデータ収集サーバーのタイムスタンプ（UNIX® 時間に基づく）。 | int |
| **`hitid_high`** | `hitid_low` と共に使用し、ヒットを識別します。 | bigint unsigned |
| **`hitid_low`** | `hitid_high` と共に使用し、ヒットを識別します。 | bigint unsigned |
| **`hourly_visitor`** | ヒットが新しい時間別の訪問者かどうかを決定するフラグ。 | tinyint unsigned |
| **`ip`** | イメージリクエストの HTTP ヘッダーに基づく IPv4 アドレス。`ipv6` とは相互排他的です。難読化されていない IP アドレスがこの列に含まれている場合、`ipv6` は空白になります。 | char(20) |
| **`ipv6`** | 圧縮された IPv6 アドレス（使用可能な場合）。`ip` とは相互排他的です。難読化されていない IP アドレスがこの列に含まれている場合、`ip` は空白になります。 | varchar(40) |
| **`j_jscript`** | ブラウザーでサポートされている JavaScript のバージョン。 | char(5) |
| **`java_enabled`** | [[!UICONTROL Java 有効 ]](/help/components/dimensions/java-enabled.md)。 <br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| **`javascript`** | `j_jscript`に基づくJavaScriptバージョンの参照 ID。`javascript_version`ルックアップテーブルを参照します。 | tinyint unsigned |
| **`language`** | 訪問者の言語を表す数値 ID。 `languages.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| **`last_hit_time_gmt`** | 前回のヒットのタイムスタンプ（UNIX® 時間）。「[[!UICONTROL 最終訪問からの日数]](/help/components/dimensions/days-since-last-visit.md)」ディメンションの計算に使用されます。 | int |
| **`last_purchase_num`** | 「[ 顧客ロイヤルティ ](/help/components/dimensions/customer-loyalty.md)」ディメンション。 訪問者がこれまでに行った購入の回数。<br>0：過去に購入したことがない（顧客以外）<br>1：過去に 1 回購入したことがある（新規顧客）<br>2：過去に 2 回購入したことがある（リターン顧客）<br>3：過去に 3 回以上購入したことがある（常連客） | int unsigned |
| **`last_purchase_time_gmt`** | 「[[!UICONTROL 前回購入からの日数]](/help/components/dimensions/days-since-last-purchase.md)」ディメンションで使用されます。前回行った購入のタイムスタンプ（UNIX® 時間）。初回の購入やこれまでに購入を行っていない訪問者の場合、この値は `0` になります。 | int |
| **`latlon1`** | ロケーション（半径 10 km 以内） | varchar(255) |
| **`latlon23`** | ロケーション（半径 100 m 以内） | varchar(255) |
| **`latlon45`** | ロケーション（半径 1 m 以内） | varchar(255) |
| **`mc_audiences`** | 訪問者が属している Audience Manager セグメント ID のリスト。`post_mc_audiences` 列の区切り文字が `--**--` に変更されます。 | テキスト |
| **`mcvisid`** | Experience Cloud 訪問者 ID。2 つの 64 ビット数値を連結して 19 桁にパディングした 128 ビット数値です。 | varchar(255) |
| **`mobile_id`** | ユーザーがモバイルデバイスを使用している場合は、そのデバイスの数値 ID。`mobile_attributes.tsv` [動的検索](dynamic-lookups.md)のキー値。 | int |
| **`mobileaction`** | モバイルアクション。モバイル実装で `trackAction` が呼び出されると、自動的に収集されます。 アプリケーション内で自動的にアクションを渡すことができるようにします。 | varchar(100) |
| **`mobileappid`** | モバイルアプリケーション ID。アプリケーションの名前とバージョンを次の形式で格納します。`[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Apteligent データコネクタで使用されます。Apteligent で使用されるアプリケーション ID。 | varchar(255) |
| **`mobileappperformancecrashid`** | Apteligent データコネクタで使用されます。Apteligent で使用されるクラッシュ ID。 | varchar(255) |
| **`mobileappstoreobjectid`** | [!DNL Appfigures] データコネクタで使用されます。 App Store オブジェクト ID。 | varchar(255) |
| **`mobilebeaconmajor`** | Mobile Services ビーコンのメジャー番号 | varchar(100) |
| **`mobilebeaconminor`** | Mobile Services ビーコンのマイナー番号 | varchar(100) |
| **`mobilebeaconproximity`** | Mobile Services ビーコンの近接性 | varchar(255) |
| **`mobilebeaconuuid`** | Mobile Services ビーコンの UUID | varchar(100) |
| **`mobilecampaigncontent`** | リンクを表示したコンテンツの名前または ID。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`mobilecampaignmedium`** | マーケティングメディア（バナー、電子メールなど）。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`mobilecampaignname`** | キャンペーンの名前。キャンペーン変数にも格納されます。 モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`mobilecampaignsource`** | オリジナルリファラー（ニュースレターやソーシャルメディアネットワークなど）。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`mobilecampaignterm`** | この獲得で追跡する有料キーワードまたはその他の用語。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`mobiledayofweek`** | アプリが起動された曜日を表す数値。 | varchar(255) |
| **`mobiledayssincefirstuse`** | アプリの初回実行時からの経過日数。 | varchar(255) |
| **`mobiledayssincelastuse`** | アプリの前回実行時からの経過日数。 | varchar(255) |
| **`mobiledeeplinkid`** | コンテキストデータ変数 `a.deeplink.id` から収集します。獲得レポートで、モバイル獲得リンクの識別子として使用されます。 | varchar(255) |
| **`mobiledevice`** | モバイルデバイス名。iOS の場合は、コンマ区切りの 2 桁の文字列として格納されます。最初の番号はデバイスの世代を表し、2 番目の番号はデバイスファミリーを表します。 | varchar(255) |
| **`mobilehourofday`** | アプリが起動された時刻を定義します。24 時間形式で示します。 | varchar(255) |
| **`mobileinstalldate`** | モバイルインストール日。モバイルアプリをユーザーが最初に開いた日を示します。 | varchar(255) |
| **`mobilelaunchnumber`** | モバイルアプリが起動されるたびに 1 ずつ増分されます。 | varchar(255) |
| **`mobilemessagebuttonname`** | コンテキストデータ変数 `a.message.button.id` から収集します。メッセージを閉じたボタンを識別するために、アプリ内メッセージで使用します。 | varchar(100) |
| **`mobilemessageid`** | アプリ内メッセージ ID | varchar(255) |
| **`mobilemessageonline`** | アプリ内メッセージオンライン | varchar(255) |
| **`mobilemessagepushoptin`** | コンテキストデータ変数 `a.push.optin` から収集します。ユーザーがプッシュメッセージをオプトインする場合は「true」に設定します。それ以外の場合、値は「false」です。 | varchar(255) |
| **`mobilemessagepushpayloadid`** | コンテキストデータ変数 `a.push.payloadid` から収集します。ペイロード識別子としてプッシュメッセージで使用します。 | varchar(255) |
| **`mobileosversion`** | Mobile Services のオペレーティングシステムのバージョン。 | varchar(255) |
| **`mobileplaceaccuracy`** | コンテキストデータ変数 `a.loc.acc` から収集します。収集時の GPS の精度をメートル単位で示します。 | varchar(255) |
| **`mobileplacecategory`** | コンテキストデータ変数 `a.loc.category` から収集します。特定の場所のカテゴリを示します。 | varchar(255) |
| **`mobileplaceid`** | コンテキストデータ変数 `a.loc.id` から収集します。特定の対象地点の識別子。 | varchar(255) |
| **`mobilepushoptin`** | Mobile Services Push オプトイン | varchar(255) |
| **`mobilepushpayloadid`** | Mobile Services Push ペイロード ID | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Mobile Services の起動コンテンツ | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Mobile Services の起動メディア | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Mobile Services の起動ソース | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Mobile Services の起動条件 | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | コンテキストデータ変数 `a.launch.campaign.trackingcode` から収集します。キャンペーン立ち上げのトラッキングコードとして、獲得で使用します。 | varchar(255) |
| **`mobileresolution`** | モバイルデバイスの解像度。`[Width] x [Height]` 画素数. | varchar(255) |
| **`monthly_visitor`** | 訪問者が当月固有かどうかを決定するフラグ。 | tinyint unsigned |
| **`mvvar1`**～`mvvar3` | [ リスト変数 ](/help/implement/vars/page-vars/list.md) 値。 実装に応じたカスタム値の区切りリストを含んでいます。`post_mvvar1`〜`post_mvvar3` の列は元の区切り文字を `--**--` に置き換えます。 | テキスト |
| **`mvvar1_instances`**～`mvvar3_instances` | 現在のヒットに設定されたリスト変数値。元の区切り文字を `--**--` に置き換えます。通常、 `post` 列にはデータが含まれません。 | テキスト |
| **`new_visit`** | 現在のヒットが新しい訪問かどうかを判断するフラグ。 訪問が無操作状態になってから 30 分後にAdobeが設定します。 | tinyint unsigned |
| **`os`** | 訪問者のオペレーティングシステムを表す数値 ID。 `user_agent` 列に基づきます。`operating_system.tsv` 標準検索と `operating_system_type.tsv` [動的検索](dynamic-lookups.md)のキー値。 | int unsigned |
| **`page_event`** | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、カスタムリンク、離脱リンク）。[ページイベント参照](datafeeds-page-event.md)を参照してください。 | tinyint unsigned |
| **`page_event_var1`** | リンクトラッキングイメージリクエストでのみ使用されます。クリックされたダウンロードリンク、離脱リンク、カスタムリンクの URL。 | テキスト |
| **`page_event_var2`** | リンクトラッキングイメージリクエストでのみ使用されます。リンクのカスタム名（指定した場合）。 `page_event` の値に応じて [ カスタムリンク ](/help/components/dimensions/custom-link.md)、[ ダウンロードリンク ](/help/components/dimensions/download-link.md) または [ 離脱リンク ](/help/components/dimensions/exit-link.md) を設定します。 | varchar(100) |
| **`page_type`** | [ページ見つかりません](/help/components/dimensions/pages-not-found.md)ディメンション。通常は 404 ページに使用されます。 | char(20) |
| **`page_url`** | ヒットの URL。リンクトラッキングイメージ要求([`tl()`](/help/implement/vars/functions/tl-method.md))に対して`post_page_url`が削除され、varchar(255) のデータ型が使用されることに注意してください。 | テキスト |
| **`pagename`** | 「[ ページ ](/help/components/dimensions/page.md)」ディメンション。 [`pagename`](/help/implement/vars/page-vars/pagename.md) 変数が空の場合、Analytics では代わりに `page_url` が使用されます。 | varchar(100) |
| **`pagename_no_url`** | `pagename` に似ていますが、`page_url` にフォールバックされません。`post` 列のみが使用できます。 | varchar(100) |
| **`paid_search`** | ヒットが有料検索検知に一致するかどうかを決定するフラグ。 | tinyint unsigned |
| **`persistent_cookie`** | 「[永続的な cookie のサポート](/help/components/dimensions/persistent-cookie-support.md)」ディメンションで使用されます。各ヒットの後で破棄されない Cookie を訪問者がサポートしているかどうかを示します。 | char(1) |
| **`pointofinterest`** | Mobile Services 目標地点の名前 | varchar(255) |
| **`pointofinterestdistance`** | 目標地点中心までの Mobile Services の距離 | varchar(255) |
| **`post_`** 列 | レポートで最終的に使用された値が格納されます。各 post 列には、サーバーサイドロジック、処理ルール、VISTA ルールの適用後に値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。 | post 以外の各列を参照してください。 |
| **`product_list`** | [`products`](/help/implement/vars/page-vars/products.md) ページ変数。 [ カテゴリ ](/help/components/dimensions/category.md)、[ 製品 ](/help/components/dimensions/product.md)、[ 単位 ](/help/components/metrics/units.md)、[ 売上高 ](/help/components/metrics/revenue.md) など、複数のディメンションおよび指標の入力に役立ちます。 | テキスト |
| **`prop1`**～`prop75` | カスタムトラフィック変数 1 ～ 75。「[Prop](/help/components/dimensions/prop.md)」ディメンションで使用されます。 | varchar(100) |
| **`purchaseid`** | 購入の一意な識別子（[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) 変数を使用して設定）。`duplicate_purchase` 列で使用されます。 | char(20) |
| **`quarterly_visitor`** | ヒットが新しい四半期ごとの訪問者かどうかを判断するフラグ。 | tinyint unsigned |
| **`ref_domain`** | [ 参照ドメイン ](/help/components/dimensions/referring-domain.md) ディメンション。 `referrer` 列に基づいています。 | varchar(100) |
| **`ref_type`** | ヒットのリファラルのタイプを表す数値 ID。 「[リファラータイプ](/help/components/dimensions/referrer-type.md)」ディメンションで使用されます。<br>1：サイト内<br>2：その他の Web サイト<br>3：検索エンジン<br>4：ハードドライブ<br>5：USENET<br>6：手動入力／ブックマーク（リファラーなし）<br>7：電子メール<br>8：JavaScript なし<br>9：ソーシャルネットワーク | tinyint unsigned |
| **`referrer`** | 「[ リファラー ](/help/components/dimensions/referrer.md)」ディメンション。 `referrer` のデータ型は varchar(255)、`post_referrer` のデータ型は varchar(244) です。 | varchar(255) |
| **`resolution`** | モニターの解像度を表す数値 ID。 「[画面の解像度](/help/components/dimensions/monitor-resolution.md)」ディメンションで使用されます。`resolution.tsv` ルックアップテーブルを使用します。 | smallint unsigned |
| **`s_kwcid`** | Adobe Advertising 統合で使用されるキーワード ID。 | varchar(255) |
| **`s_resolution`** | 画面解像度の未処理の値。JavaScript 関数 `screen.width x screen.height` を使用して収集します。 | char(20) |
| **`search_engine`** | 訪問者をサイトに誘導した検索エンジンを表す数値 ID。 [ 検索エンジン ](/help/components/dimensions/search-engine.md) ディメンションで使用されます。 `search_engines.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| **`search_page_num`** | 「[すべての検索ページのランク](/help/components/dimensions/all-search-page-rank.md)」ディメンションで使用されます。ユーザーがクリックスルーしてサイトに到達する前にサイトが表示された検索結果ページを示します。 | smallint unsigned |
| **`secondary_hit`** | ヒットがセカンダリヒットかどうかを判断するフラグ。 このフラグは、通常、ヒットをコピーするマルチスイートタグ付けおよび VISTA ルールから発生します。 | tinyint unsigned |
| **`sourceid`** | ソース ID | int unsigned |
| **`state`** | 状態変数。 | varchar(50) |
| **`stats_server`** | 未使用。ヒットを処理したアドビの内部サーバー。 | char(30) |
| **`t_time_info`** | 訪問者の現地時刻。形式：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Adobe Target 統合で使用されます。現在認定されているすべてのテストを表します。形式は次のとおりです。`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action` | テキスト |
| **`tnt_action`** | Adobe Target 統合で使用されます。ヒットが認定されるすべてのテストを表します。 | テキスト |
| **`tnt_instances`** | Adobe Target 統合で使用されます。Target インスタンス変数。 | テキスト |
| **`transactionid`** | データソースを使用して後から様々なデータポイントをアップロードするための一意の識別子。[`transactionID`](/help/implement/vars/page-vars/transactionid.md) 変数を使用して収集します。 | テキスト |
| **`truncated_hit`** | イメージリクエストが切り捨てられたことを示すフラグ。 部分的なヒットを受信したことを示します。<br>Y：ヒットが切り捨てられました。ヒットの一部を受信しました。<br>N：ヒットが切り捨てられませんでした。すべてのヒットを受信しました。 | char(1) |
| **`user_agent`** | イメージリクエストの HTTP ヘッダーで送信されるユーザーエージェント文字列。 | テキスト |
| **`user_hash`** | 未使用。レポートスイート ID のハッシュ。代わりに、`username` を使用してください。 | int unsigned |
| **`user_server`** | 「[サーバー](/help/components/dimensions/server.md)」ディメンションで使用されます。 | varchar(100) |
| **`userid`** | 未使用。レポートスイート ID の数値 ID。代わりに、`username` を使用してください。 | int unsigned |
| **`username`** | ヒットのレポートスイート ID。 | char(40) |
| **`va_closer_detail`** | [ ラストタッチの詳細 ](/help/components/dimensions/last-touch-detail.md) ディメンション。 | varchar(255) |
| **`va_closer_id`** | [ ラストタッチチャネル ](/help/components/dimensions/last-touch-channel.md) ディメンションを識別する数値 ID。 この ID のルックアップは、マーケティングチャネルマネージャーで確認できます。 | tinyint unsigned |
| **`va_finder_detail`** | [ ファーストタッチの詳細 ](/help/components/dimensions/first-touch-detail.md) ディメンション。 | varchar(255) |
| **`va_finder_id`** | [ ファーストタッチチャネル ](/help/components/dimensions/first-touch-channel.md) ディメンションを識別する数値 ID。 この ID のルックアップは、マーケティングチャネルマネージャーで確認できます。 | tinyint unsigned |
| **`va_instance_event`** | マーケティングチャネル [ インスタンス ](/help/components/metrics/instances.md) を識別するフラグ。 | tinyint unsigned |
| **`va_new_engagement`** | マーケティングチャネル [ 新規エンゲージメント ](/help/components/metrics/new-engagements.md) を識別するフラグ。 | tinyint unsigned |
| **`video`** | [ コンテンツ ](/help/components/dimensions/sm-core.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoad`** | 「[ 広告 ](/help/components/dimensions/sm-ads.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videoadinpod`** | [ ポッド位置の広告 ](/help/components/dimensions/sm-ads.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoadlength`** | [ 広告の長さ（可変） ](/help/components/dimensions/sm-ads.md) ストリーミングメディア ディメンション。 | 整数 |
| **`videoadload`** | [ 広告の読み込み ](/help/components/dimensions/sm-ads.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoadname`** | [ 広告名（変数） ](/help/components/dimensions/sm-ads.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoadplayername`** | 「[ 広告プレーヤー名 ](/help/components/dimensions/sm-ads.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videoadpod`** | [ 広告ポッド ](/help/components/dimensions/sm-ads.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoadvertiser`** | [広告主](/help/components/dimensions/sm-ads.md)ストリーミングメディアディメンション。 | varchar(255) |
| **`videoaudioalbum`** | [アルバム](/help/components/dimensions/sm-audio-metadata.md)ストリーミングメディアディメンション。 | varchar(255) |
| **`videoaudioartist`** | [ アーティスト ](/help/components/dimensions/sm-audio-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoaudioauthor`** | [ オーサー ](/help/components/dimensions/sm-audio-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoaudiolabel`** | [ ラベル ](/help/components/dimensions/sm-audio-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoaudiopublisher`** | [ パブリッシャー ](/help/components/dimensions/sm-audio-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoaudiostation`** | [ ステーション ](/help/components/dimensions/sm-audio-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videocampaign`** | [ キャンペーン ID](/help/components/dimensions/sm-ads.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videochannel`** | [ コンテンツチャネル ](/help/components/dimensions/sm-core.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videochapter`** | [ チャプター ](/help/components/dimensions/sm-chapters.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videocontenttype`** | [コンテンツタイプ](/help/components/dimensions/sm-core.md)ストリーミングメディアディメンション。 | varchar(255) |
| **`videodaypart`** | [日部分](/help/components/dimensions/sm-video-metadata.md)ストリーミングメディアディメンション。 | varchar(255) |
| **`videoepisode`** | [ エピソード ](/help/components/dimensions/sm-video-metadata.md) ストリーミングメディアディメンション。 | varchar(255) |
| **`videofeedtype`** | 「[ メディアフィードのタイプ ](/help/components/dimensions/sm-video-metadata.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videogenre`** | [ジャンル](/help/components/dimensions/sm-video-metadata.md)ストリーミングメディアディメンション。このディメンションでは、同じヒットに複数の値をコンマで区切って指定できます。 | テキスト |
| **`videolength`** | 「[ コンテンツの長さ（変数） ](/help/components/dimensions/sm-core.md) ストリーミングメディア」ディメンション。 | 整数 |
| **`videomvpd`** | [MVPD](/help/components/dimensions/sm-video-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoname`** | [ コンテンツ名（変数） ](/help/components/dimensions/sm-core.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videonetwork`** | [ ネットワーク ](/help/components/dimensions/sm-video-metadata.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videopath`** | [ メディアパス ](/help/components/dimensions/sm-core.md) ストリーミングメディア ディメンション。 | varchar(100) |
| **`videoplayername`** | 「[ コンテンツプレーヤー名 ](/help/components/dimensions/sm-core.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videotime`** | ストリーミングメディア指標 [ コンテンツ視聴時間 ](/help/components/metrics/sm-core.md)。 | 整数 |
| **`videoqoebitrateaverageevar`** | [ 平均ビットレート ](/help/components/dimensions/sm-quality.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoqoebitratechangecountevar`** | [ ビットレート変更 ](/help/components/dimensions/sm-quality.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoqoebuffercountevar`** | [ バッファーイベント ](/help/components/dimensions/sm-quality.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoqoebuffertimeevar`** | [ ストリーミングメディアの合計バッファー時間 ](/help/components/dimensions/sm-quality.md) ディメンション。 | varchar(255) |
| **`videoqoedroppedframecountevar`** | 「[ ドロップフレーム ](/help/components/dimensions/sm-quality.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videoqoeerrorcountevar`** | [ エラー ](/help/components/dimensions/sm-quality.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoqoeextneralerrors`** | [ 外部エラー ID](/help/components/dimensions/sm-quality.md) ストリーミングメディア ディメンション。 このディメンションでは、同じヒットに複数の値を含めることができます。 | テキスト |
| **`videoqoeplayersdkerrors`** | [プレーヤー SDK のエラー ID](/help/components/dimensions/sm-quality.md)ストリーミングメディアディメンション。このディメンションでは、同じヒットに複数の値を使用できます。 | テキスト |
| **`videoqoetimetostartevar`** | [時間から開始](/help/components/dimensions/sm-quality.md)ストリーミングメディアディメンション。 | varchar(255) |
| **`videoseason`** | [シーズン](/help/components/dimensions/sm-video-metadata.md)ストリーミングメディアディメンション。 | varchar(255) |
| **`videosegment`** | [ コンテンツセグメント ](/help/components/dimensions/sm-core.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`videoshow`** | 「ストリーミングメディア [ 表示 ](/help/components/dimensions/sm-video-metadata.md)」ディメンション。 | varchar(255) |
| **`videoshowtype`** | 「[ 表示タイプ ](/help/components/dimensions/sm-video-metadata.md) ストリーミングメディア」ディメンション。 | varchar(255) |
| **`videostreamtype`** | [ ストリームタイプ ](/help/components/dimensions/sm-core.md) ストリーミングメディア ディメンション。 | varchar(255) |
| **`visid_high`** | `visid_low` と共に使用し、訪問者を一意に識別します。 | bigint unsigned |
| **`visid_low`** | `visid_high` と共に使用し、訪問者を一意に識別します。 | bigint unsigned |
| **`visid_new`** | ヒットに新しく生成された訪問者 ID が含まれるかどうかを決定するフラグ。 | char(1) |
| **`visid_timestamp`** | 訪問者 ID を新たに生成する場合、は訪問者 ID が生成された時刻のタイムスタンプを UNIX® 単位で指定します。 | int |
| **`visid_type`** | 内部使用のみ。処理の最適化のためにアドビが内部的に使用します。訪問者の識別に使用される方法を表す数値 ID。<br>`0`：カスタム訪問者 ID または不明／該当なし<br>`1`：IP およびユーザーエージェントのフォールバック<br>`2`：HTTP モバイル加入者ヘッダー<br>`3`：従来の cookie 値（`s_vi`）<br>`4`：フォールバック cookie の値（`s_fid`）<br>`5`：ID サービス | tinyint unsigned |
| **`visit_keywords`** | 「[ 検索キーワード ](/help/components/dimensions/search-keyword.md)」ディメンション。 この列では、アドビが使用するバックエンドロジックに対応するために、標準以外の文字制限である varchar(244) が使用されます。 | varchar(244) |
| **`visit_num`** | [訪問回数](/help/components/dimensions/visit-number.md)ディメンション。1 から始まり、各訪問者が新しい訪問を開始するたびに増分されます。 | int unsigned |
| **`visit_page_num`** | [ヒットの深さ](/help/components/dimensions/hit-depth.md)ディメンション。訪問者でヒットが発生するごとに 1 ずつ増えます。 訪問ごとにリセットされます。 | int unsigned |
| **`visit_ref_domain`** | `visit_referrer` 列に基づきます。訪問の最初の参照ドメイン。 | varchar(100) |
| **`visit_ref_type`** | 訪問の最初の転送者の転送者の種類を表す数値 ID。 `referrer_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| **`visit_referrer`** | 訪問の最初のリファラー。 | varchar(255) |
| **`visit_search_engine`** | 訪問の最初の検索エンジンを表す数値 ID。 `search_engines.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| **`visit_start_page_url`** | 訪問の最初の URL。 | varchar(255) |
| **`visit_start_pagename`** | 訪問の最初のヒットにおけるページ名の値。 | varchar(100) |
| **`visit_start_time_gmt`** | 訪問の最初のヒットのタイムスタンプ（UNIX® 時間）。 | int |
| **`weekly_visitor`** | ヒットが新しい週別訪問者かどうかを判断するフラグ。 | tinyint unsigned |
| **`yearly_visitor`** | ヒットが新しい年間訪問者かどうかを決定するフラグ。 | tinyint unsigned |
| **`zip`** | 「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンションの生成に役立ちます。関連トピック 「`geo_zip`」を参照してください。 | varchar(50) |

{style="table-layout:auto"}

## 未使用または廃止された列

次の列リストは、未使用、廃止済み、またはレポートに値が含まれない列です。 これらの列の一部は、廃止された機能に関連付けられていますが、その他の列は、新機能や堅牢な機能のために不要になりました。 これらの列のほとんどはデータを含みません。データを含む可能性のある列は、現在のデータ収集ライブラリではサポートされておらず、Analysis Workspaceでは使用できないディメンションです。

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
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
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `sampled_hit`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
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
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
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
