---
description: データフィードの各列について説明するテーブルデータです。
keywords: データフィード;列
subtopic: data feeds
title: データ列リファレンス
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: fd5a38ca3c621e67f7a670f361e73b439ce9861a
workflow-type: tm+mt
source-wordcount: '3652'
ht-degree: 92%

---

# データ列リファレンス

このページでは、各列に含まれるデータを確認できます。ほとんどの実装ではすべての列を使用していないので、データフィードの書き出しに含める列を決定する際には、このページを参考にすることができます。

>[!IMPORTANT]
>
>指定された列（例えば、255 文字として定義された列）では、文字列内の値をエスケープする文字の追加により、データフィードは追加の文字を送信する可能性があります。実装によって文字制限を超える値を定期的に送信する場合は、これらの追加の文字の可能性に注意してください。

## 列、説明、データタイプ

>[!NOTE]
>
>ほとんどの列には、`post_` という接頭辞が付く類似の列が含まれています。post 列には、サーバーサイドロジック、処理ルール、VISTA ルールの適用後の値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。詳しくは、[データフィードに関する FAQ](../df-faq.md) を参照してください。

このテーブルの以前の更新は、このページの [GitHub のコミット履歴](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)で確認できます。

| 投稿 | 列名 | 列の説明 | データタイプ |
| ---: | :--- | --- | --- |
| | **`accept_language`** | イメージリクエストの Accept-Language HTTP ヘッダーで指定されている受け入れ可能なすべての言語のリスト。 | char(20) |
| **`post_`** | **`adload`** | メディア広告の読み込み | varchar(255) |
| **`post_`** | **`aemassetid`** | 一連の Adobe Experience Manager Assets のアセット ID（GUID）に対応する複数値の変数。インプレッションイベントを増分します。 | text |
| **`post_`** | **`aemassetsource`** | アセットイベントのソースを識別します。Adobe Experience Manager で使用されます。 | varchar(255) |
| **`post_`** | **`aemclickedassetid`** | Adobe Experience Manager アセットのアセット ID。クリックイベントを増分します。 | varchar(255) |
| **`post_`** | **`amo_cid`** | [AMO ID](/help/components/dimensions/amo-id.md) ディメンションは、Adobe Advertising統合で使用されます。 | varchar(255) |
| **`post_`** | **`amo_ef_id`** | [AMO EF ID](/help/components/dimensions/amo-ef-id.md) ディメンションは、Adobe Advertising統合で使用されます。 | varchar(255) |
| | **`browser`** | ブラウザーを表す数値 ID。 `browser.tsv` ルックアップテーブルを参照します。 | int unsigned |
| **`post_`** | **`browser_height`** | 「[ブラウザーの高さ](/help/components/dimensions/browser-height.md)」ディメンション。 | smallint unsigned |
| **`post_`** | **`browser_width`** | [ブラウザーの幅](/help/components/dimensions/browser-width.md) | smallint unsigned |
| **`post_`** | **`campaign`** | 「[トラッキングコード](/help/components/dimensions/tracking-code.md)」ディメンション。 | varchar(255) |
| | **`carrier`** | Adobe Advertising 統合変数。携帯電話会社を指定します。`carrier.tsv` [動的検索](dynamic-lookups.md)のキー値。 | varchar(100) |
| **`post_`** | **`channel`** | 「[サイトセクション](/help/components/dimensions/site-section.md)」ディメンション。 | varchar(100) |
| | **`ch_hdr`** | HTTP リクエストヘッダーを通じて収集されたクライアントヒント。 | text |
| | **`ch_js`** | User-Agent クライアントヒント JavaScript API を通じて収集されたクライアントヒント。 | text |
| **`post_`** | **`clickmaplink`** | [Activity Map リンク ](/help/components/dimensions/activity-map-link.md) ディメンション。 | varchar(255) |
| **`post_`** | **`clickmaplinkbyregion`** | [Activity Map リンク （地域別 ](/help/components/dimensions/activity-map-link-by-region.md) ディメンション。 | varchar(255) |
| **`post_`** | **`clickmappage`** | [Activity Mapページ ](/help/components/dimensions/activity-map-page.md) ディメンション。 | varchar(255) |
| **`post_`** | **`clickmapregion`** | [Activity Map地域 ](/help/components/dimensions/activity-map-region.md) ディメンション。 | varchar(255) |
| | **`code_ver`** | イメージリクエストのコンパイルと送信に使用される API またはクライアント SDK のバージョン。 | char(16) |
| | **`color`** | `c_color` 列の値に基づいく色深度 ID。`color_depth.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| | **`connection_type`** | [ 接続タイプ ](/help/components/dimensions/connection-type.md) ディメンションを表す数値 ID。 `connection_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| **`post_`** | **`cookies`** | 「[cookie サポート](/help/components/dimensions/cookie-support.md)」ディメンション。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| | **`country`** | 訪問者の国を表す数値 ID。`country.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| **`post_`** | **`currency`** | 取引で使用された通貨のコード。[`currencyCode`](/help/implement/vars/config-vars/currencycode.md) を使用して設定します。 | char(8) |
| | **`ct_connect_type`** | `connection_type` 列と関連しています。よく使用される値は LAN/Wi-Fi、Mobile Carrier、Modem です。 | char(20) |
| | **`curr_factor`** | 通貨の小数点以下の桁数を指定します。 通貨換算に使用されます。 例えば、USD では小数点以下 2 桁が使用されるので、この列の値は `2` になります。 | tinyint |
| | **`curr_rate`** | 取引が発生した際の為替レート。アドビは、XE と提携して、当日の為替レートを判定します。 | decimal(24,12) |
| **`post_`** | **`customer_perspective`** | ヒットがモバイルバックグラウンドヒットかどうかを判定します。詳しくは、[コンテキスト対応セッション](/help/components/vrs/vrs-mobile-visit-processing.md)を参照してください。 | tinyint unsigned |
| **`post_`** | **`cust_hit_time_gmt`** | タイムスタンプに対応するレポートスイートの場合のみ。ヒットと共に送信されたタイムスタンプ（UNIX® 時間に基づく）。 | int |
| **`post_`** | **`cust_visid`** | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) を使用して設定されている場合のカスタム訪問者 ID。 | varchar(255) |
| | **`c_color`** | カラーパレットのビット深度。「[色深度](/help/components/dimensions/color-depth.md)」ディメンションの計算の一環として使用されます。AppMeasurement では JavaScript 関数 `screen.colorDepth()` が使用されます。 | char(20) |
| | **`daily_visitor`** | ヒットが新しい日別訪問者であるかどうかを判定するフラグ。 | tinyint unsigned |
| | **`dataprivacyconsentoptin`** | 「[同意管理のオプトイン](/help/components/dimensions/cm-opt-in.md)」ディメンション。 ヒットごとに複数の値が存在する可能性があります（パイプ（`\|`）区切り）。有効な値には、`DMP` および `SELL` などがあります。 | varchar(100) |
| | **`dataprivacyconsentoptout`** | 「[同意管理のオプトアウト](/help/components/dimensions/cm-opt-out.md)」ディメンション。ヒットごとに複数の値が存在する可能性があります（パイプ（`\|`）区切り）。有効な値には、`SSF`、`DMP`、`SELL` などがあります。 | varchar(100) |
| | **`date_time`** | レポートスイートのタイムゾーンに基づいて判読可能な形式で表現されたヒットの時刻。 | 日時 |
| | **`domain`** | 「[ドメイン](/help/components/dimensions/domain.md)」ディメンション。訪問者のインターネットアクセスポイントに基づいています。 | varchar(100) |
| | **`duplicated_from`** | ヒットコピー VISTA ルールを含んだレポートスイートでのみ使用されます。ヒットがどのレポートスイートからコピーされたかを示します。 | varchar(40) |
| | **`duplicate_events`** | 重複としてカウントされた各イベントを一覧表示します。 | varchar(255) |
| | **`duplicate_purchase`** | このヒットの購入イベントが重複しているので無視されるかどうかを判定するフラグ。 | tinyint unsigned |
| **`post_`** | **`ef_id`** | Adobe Advertising統合で使用される EF ID。 | varchar(255) |
| **`post_`** | **`evar1 - evar250`** | カスタム変数 1 ～ 250。「[eVar](/help/components/dimensions/evar.md)」ディメンションで使用されます。eVar の使用方法は組織ごとに異なります。組織における各 eVar への値の設定方法について詳しくは、それぞれの組織に固有の[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)を参照してください。 | varchar(255) |
| **`post_`** | **`event_list`** | ヒット時にトリガーされたイベントを表す数値 ID のコンマ区切りリスト。コマースイベントと [ カスタムイベント 1 ～ 1000](/help/components/metrics/custom-events.md) の両方が含まれます。 `event.tsv` ルックアップを使用します。 | text |
| | **`exclude_hit`** | ヒットがレポートから除外されるかどうかを判定するフラグ。 除外されたヒットに対しては `visit_num` 列が増分されません。<br>1：未使用。削除されたフィーチャの一部。<br>2：未使用。削除されたフィーチャの一部。<br>3：廃止。ユーザーエージェントの除外<br>4：IP アドレスに基づく除外<br>5：重要なヒット情報が欠落しています。例：`page_url`、`pagename`、`page_event`、`event_list`<br> 6：JavaScript でヒットが正しく処理されませんでした<br>7：アカウント固有の除外（VISTA ルールなど）<br>8：未使用。代替のアカウント固有の除外。<br>9：未使用。削除されたフィーチャの一部。<br>10：無効な通貨コード<br>11：タイムスタンプのみのレポートスイートでヒットにタイムスタンプが含まれていない、またはタイムスタンプ以外のレポートスイートでヒットにタイムスタンプが含まれている<br>12:未使用。削除されたフィーチャの一部。<br>13：未使用。削除されたフィーチャの一部。<br>14：Analytics と一致しないターゲットヒット<br>15：現在は使用されていません。<br>16：Analytics ヒットと一致しない Advertising Cloud ヒット | tinyint unsigned |
| | **`first_hit_pagename`** | 「[入口ページのオリジナル](/help/components/dimensions/entry-dimensions.md)」ディメンション。訪問者のオリジナルの入口ページ名。 | varchar(100) |
| | **`first_hit_page_url`** | 訪問者の本当に最初の URL。 | varchar(255) |
| | **`first_hit_referrer`** | 訪問者の本当に最初の参照 URL。 | varchar(255) |
| | **`first_hit_ref_domain`** | 「[オリジナルの参照ドメイン](/help/components/dimensions/original-referring-domain.md)」ディメンション。`first_hit_referrer` に基づきます。訪問者の本当に最初の参照ドメイン。 | varchar(100) |
| | **`first_hit_ref_type`** | 訪問者の本当に最初のリファラーのリファラータイプを表す数値 ID。`referrer_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| | **`first_hit_time_gmt`** | 訪問者の最初のヒットのタイムスタンプ（UNIX® 時間）。 | int |
| | **`geo_city`** | ヒットが発生した市区町村の名前（IP アドレスに基づく）。「[市区町村](/help/components/dimensions/cities.md)」ディメンションで使用されます。 | char(32) |
| | **`geo_country`** | ヒットが発生した国の略称（IP アドレスに基づく）。[国](/help/components/dimensions/countries.md)ディメンションで使用します。 | char(4) |
| | **`geo_dma`** | ヒットが発生したデモグラフィック地域の数値 ID（IP アドレスに基づく）。「[米国 DMA](/help/components/dimensions/us-dma.md)」ディメンションで使用されます。 | int unsigned |
| | **`geo_region`** | ヒットが発生した州または地域の名前（IP アドレスに基づく）。「[地域](/help/components/dimensions/regions.md)」ディメンションで使用されます。 | char(32) |
| | **`geo_zip`** | ヒットが発生した場所の郵便番号（IP アドレスに基づく）。「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンションの入力に役立ちます。関連トピック「 `zip`」を参照してください。 | varchar(16) |
| | **`hitid_high`** | `hitid_low` と共に使用し、ヒットを識別します。 | bigint unsigned |
| | **`hitid_low`** | `hitid_high` と共に使用し、ヒットを識別します。 | bigint unsigned |
| | **`hit_source`** | ヒットソース。ヒットソース 1 および 2 は請求されます。 <br>1：タイムスタンプのない標準画像リクエスト <br>2：タイムスタンプのある標準画像リクエスト <br>3：タイムスタンプのあるライブデータソースアップロード <br>4：未使用 <br>5：一般的なデータソースアップロード <br>6：使用されなくなった、フル処理のデータソースアップロード <br>7:TransactionID データソースのアップロード <br>8：使用されなくなった、Adobe Advertising データソースの以前のバージョン <br>9：使用されなくなった、Adobe Social 概要指標 <br>10:Audience Manager サーバーサイド転送が使用された | tinyint unsigned |
| | **`hit_time_gmt`** | ヒットを受信したアドビデータ収集サーバーのタイムスタンプ（UNIX® 時間に基づく）。 | int |
| | **`hourly_visitor`** | ヒットが新しい時間別訪問者であるかどうかを判定するフラグ。 | tinyint unsigned |
| | **`ip`** | イメージリクエストの HTTP ヘッダーに基づく IPv4 アドレス。`ipv6` とは相互排他的です。難読化されていない IP アドレスがこの列に含まれている場合、`ipv6` は空白になります。 | char(20) |
| | **`ipv6`** | 圧縮された IPv6 アドレス（使用可能な場合）。`ip` とは相互排他的です。難読化されていない IP アドレスがこの列に含まれている場合、`ip` は空白になります。 | varchar(40) |
| | **`javascript`** | JavaScript のバージョンのルックアップ ID（`j_jscript` に基づく）。`javascript_version`ルックアップテーブルを参照します。 | tinyint unsigned |
| **`post_`** | **`java_enabled`** | [[!UICONTROL Java 有効]](/help/components/dimensions/java-enabled.md)。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| | **`j_jscript`** | ブラウザーでサポートされている JavaScript のバージョン。 | char(5) |
| | **`language`** | 訪問者の言語を表す数値 ID。`languages.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| | **`last_hit_time_gmt`** | 前回のヒットのタイムスタンプ（UNIX® 時間）。「[[!UICONTROL 最終訪問からの日数]](/help/components/dimensions/days-since-last-visit.md)」ディメンションの計算に使用されます。 | int |
| | **`last_purchase_num`** | 「[ 顧客の忠誠度](/help/components/dimensions/customer-loyalty.md)」ディメンション。 訪問者がこれまでに行った購入の回数。<br>0：過去に購入したことがない（顧客以外）<br>1：過去に 1 回購入したことがある（新規顧客）<br>2：過去に 2 回購入したことがある（リターン顧客）<br>3：過去に 3 回以上購入したことがある（常連客） | int unsigned |
| | **`last_purchase_time_gmt`** | 「[[!UICONTROL 前回購入からの日数]](/help/components/dimensions/days-since-last-purchase.md)」ディメンションで使用されます。前回行った購入のタイムスタンプ（UNIX® 時間）。初回の購入やこれまでに購入を行っていない訪問者の場合、この値は `0` になります。 | int |
| | **`latlon1`** | ロケーション（半径 10 km 以内） | varchar(255) |
| | **`latlon23`** | ロケーション（半径 100 m 以内） | varchar(255) |
| | **`latlon45`** | ロケーション（半径 1 m 以内） | varchar(255) |
| | **`mcvisid`** | Experience Cloud 訪問者 ID。2 つの連結された 64 ビットの数値から構成され、19 桁にパディングされた 128 ビットの数値。 | varchar(255) |
| **`post_`** | **`mc_audiences`** | 訪問者が属している Audience Manager セグメント ID のリスト。`post_mc_audiences` 列の区切り文字が `--**--` に変更されます。 | text |
| **`post_`** | **`mobileaction`** | モバイルアクション。モバイル実装で `trackAction` が呼び出されると、自動的に収集されます。アプリケーション内で自動的にアクションを渡すことができるようにします。 | varchar(100) |
| **`post_`** | **`mobileappid`** | モバイルアプリケーション ID。アプリケーションの名前とバージョンを次の形式で格納します。`[AppName] [BundleVersion]` | varchar(255) |
| | **`mobileappperformanceappid`** | Apteligent データコネクタで使用されます。Apteligent で使用されるアプリケーション ID。 | varchar(255) |
| | **`mobileappperformancecrashid`** | Apteligent データコネクタで使用されます。Apteligent で使用されるクラッシュ ID。 | varchar(255) |
| | **`mobileappstoreobjectid`** | [!DNL Appfigures] データコネクタで使用されます。App Store オブジェクト ID。 | varchar(255) |
| | **`mobilebeaconmajor`** | Mobile Services ビーコンのメジャー番号 | varchar(100) |
| | **`mobilebeaconminor`** | Mobile Services ビーコンのマイナー番号 | varchar(100) |
| | **`mobilebeaconproximity`** | Mobile Services ビーコンの近接性 | varchar(255) |
| | **`mobilebeaconuuid`** | Mobile Services ビーコンの UUID | varchar(100) |
| **`post_`** | **`mobilecampaigncontent`** | リンクを表示したコンテンツの名前または ID。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`post_`** | **`mobilecampaignmedium`** | マーケティングメディア（バナー、電子メールなど）。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`post_`** | **`mobilecampaignname`** | キャンペーンの名前。キャンペーン変数にも格納されます。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`post_`** | **`mobilecampaignsource`** | オリジナルリファラー（ニュースレターやソーシャルメディアネットワークなど）。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`post_`** | **`mobilecampaignterm`** | この獲得で追跡する有料キーワードまたはその他の用語。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| **`post_`** | **`mobiledayofweek`** | アプリが起動された曜日を表す数値。 | varchar(255) |
| **`post_`** | **`mobiledayssincefirstuse`** | アプリの初回実行時からの経過日数。 | varchar(255) |
| **`post_`** | **`mobiledayssincelastuse`** | アプリの前回実行時からの経過日数。 | varchar(255) |
| | **`mobiledeeplinkid`** | コンテキストデータ変数 `a.deeplink.id` から収集します。獲得レポートで、モバイル獲得リンクの識別子として使用されます。 | varchar(255) |
| **`post_`** | **`mobiledevice`** | モバイルデバイス名。iOS の場合は、コンマ区切りの 2 桁の文字列として格納されます。最初の数字はデバイスの世代を表し、2 番目の数字はデバイスファミリーを表します。 | varchar(255) |
| **`post_`** | **`mobilehourofday`** | アプリが起動された時刻を定義します。24 時間形式で示します。 | varchar(255) |
| **`post_`** | **`mobileinstalldate`** | モバイルインストール日。モバイルアプリをユーザーが最初に開いた日を示します。 | varchar(255) |
| **`post_`** | **`mobilelaunchnumber`** | モバイルアプリが起動されるたびに 1 ずつ増分されます。 | varchar(255) |
| **`post_`** | **`mobilemessagebuttonname`** | コンテキストデータ変数 `a.message.button.id` から収集します。メッセージを閉じたボタンを識別するために、アプリ内メッセージで使用します。 | varchar(100) |
| **`post_`** | **`mobilemessageid`** | アプリ内メッセージ ID | varchar(255) |
| **`post_`** | **`mobilemessageonline`** | アプリ内メッセージオンライン | varchar(255) |
| **`post_`** | **`mobilemessagepushoptin`** | コンテキストデータ変数 `a.push.optin` から収集します。ユーザーがプッシュメッセージをオプトインする場合は「true」に設定します。それ以外の場合、値は「false」です。 | varchar(255) |
| **`post_`** | **`mobilemessagepushpayloadid`** | コンテキストデータ変数 `a.push.payloadid` から収集します。ペイロード識別子としてプッシュメッセージで使用します。 | varchar(255) |
| **`post_`** | **`mobileosversion`** | Mobile Services のオペレーティングシステムのバージョン。 | varchar(255) |
| | **`mobileplaceaccuracy`** | コンテキストデータ変数 `a.loc.acc` から収集します。収集時の GPS の精度をメートル単位で示します。 | varchar(255) |
| | **`mobileplacecategory`** | コンテキストデータ変数 `a.loc.category` から収集します。特定の場所のカテゴリを示します。 | varchar(255) |
| | **`mobileplaceid`** | コンテキストデータ変数 `a.loc.id` から収集します。特定の対象地点の識別子。 | varchar(255) |
| **`post_`** | **`mobilepushoptin`** | Mobile Services Push オプトイン | varchar(255) |
| **`post_`** | **`mobilepushpayloadid`** | Mobile Services Push ペイロード ID | varchar(255) |
| | **`mobilerelaunchcampaigncontent`** | Mobile Services の起動コンテンツ | varchar(255) |
| | **`mobilerelaunchcampaignmedium`** | Mobile Services の起動メディア | varchar(255) |
| | **`mobilerelaunchcampaignsource`** | Mobile Services の起動ソース | varchar(255) |
| | **`mobilerelaunchcampaignterm`** | Mobile Services の起動条件 | varchar(255) |
| | **`mobilerelaunchcampaigntrackingcode`** | コンテキストデータ変数 `a.launch.campaign.trackingcode` から収集します。キャンペーン立ち上げのトラッキングコードとして、獲得で使用します。 | varchar(255) |
| **`post_`** | **`mobileresolution`** | モバイルデバイスの解像度。`[Width] x [Height]` 画素数. | varchar(255) |
| | **`mobile_id`** | ユーザーがモバイルデバイスを使用している場合は、そのデバイスの数値 ID。`mobile_attributes.tsv` [動的検索](dynamic-lookups.md)のキー値。 | int |
| | **`monthly_visitor`** | 訪問者が当月固有であるかどうかを判定するフラグ。 | tinyint unsigned |
| **`post_`** | **`mvvar1`**～**`mvvar3`** | [リスト変数](/help/implement/vars/page-vars/list.md)値。実装に応じたカスタム値の区切りリストを含んでいます。`post_mvvar1`〜`post_mvvar3` の列は元の区切り文字を `--**--` に置き換えます。 | text |
| **`post_`** | **`mvvar1_instances`**～**`mvvar3_instances`** | 現在のヒットに設定されたリスト変数値。元の区切り文字を `--**--` に置き換えます。通常、`post` 列にはデータは含まれません。 | text |
| | **`new_visit`** | 現在のヒットが新しい訪問であるかどうかを判定するフラグ。訪問後 30 分間非アクティブであった場合にアドビによって設定されます。 | tinyint unsigned |
| | **`os`** | 訪問者のオペレーティングシステムを表す数値 ID。`user_agent` 列に基づきます。`operating_system.tsv` 標準検索と `operating_system_type.tsv` [動的検索](dynamic-lookups.md)のキー値。 | int unsigned |
| **`post_`** | **`pagename`** | 「[ページ](/help/components/dimensions/page.md)」ディメンション。[`pagename`](/help/implement/vars/page-vars/pagename.md) 変数が空の場合、Analytics では代わりに `page_url` が使用されます。 | varchar(100) |
| **`post_`** | **`pagename_no_url`** | `pagename` に似ていますが、`page_url` にフォールバックされません。`post` 列のみが使用できます。 | varchar(100) |
| **`post_`** | **`page_event`** | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、カスタムリンク、離脱リンク）。[ページイベント参照](datafeeds-page-event.md)を参照してください。 | tinyint unsigned |
| **`post_`** | **`page_event_var1`** | リンクトラッキングのイメージリクエストでのみ使用されます。 ダウンロードリンク、離脱リンクまたはクリックされたカスタムリンクの URL。 | text |
| **`post_`** | **`page_event_var2`** | リンクトラッキングのイメージリクエストでのみ使用されます。 リンクのカスタム名（指定した場合）。[カスタムリンク](/help/components/dimensions/custom-link.md)、[ダウンロードリンク](/help/components/dimensions/download-link.md)、または[離脱リンク](/help/components/dimensions/exit-link.md)を設定します（`page_event` の値によって異なります）。 | varchar(100) |
| **`post_`** | **`page_type`** | 「[ページが見つかりません](/help/components/dimensions/pages-not-found.md)」ディメンション。通常、404 ページに使用されます。 | char(20) |
| **`post_`** | **`page_url`** | **`page_url`**：ヒットの URL。 テキストのデータタイプを使用します。<br>**`post_page_url`**: リンクトラッキング イメージリクエスト（[`tl()`](/help/implement/vars/functions/tl-method.md)）では削除されました。 varchar （255）のデータ型を使用します。 | text<br>varchar （255） |
| | **`paid_search`** | ヒットが有料検索の検出に一致するかどうかを判定するフラグ。 | tinyint unsigned |
| **`post_`** | **`persistent_cookie`** | 「[永続的な cookie のサポート](/help/components/dimensions/persistent-cookie-support.md)」ディメンションで使用されます。各ヒット後に破棄されない Cookie を訪問者がサポートしているかどうかを示します。 | char(1) |
| **`post_`** | **`pointofinterest`** | Mobile Services 目標地点の名前 | varchar(255) |
| **`post_`** | **`pointofinterestdistance`** | 目標地点中心までの Mobile Services の距離 | varchar(255) |
| **`post_`** | **`product_list`** | [`products`](/help/implement/vars/page-vars/products.md) ページ変数。 [カテゴリ](/help/components/dimensions/category.md)、[製品](/help/components/dimensions/product.md)、[単位](/help/components/metrics/units.md)、[売上高](/help/components/metrics/revenue.md)など、複数のディメンションと指標の入力に役立ちます。 | text |
| **`post_`** | **`prop1`**～**`prop75`** | カスタムトラフィック変数 1 ～ 75。「[Prop](/help/components/dimensions/prop.md)」ディメンションで使用されます。 | varchar(100) |
| **`post_`** | **`purchaseid`** | 購入の一意な識別子（[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) 変数を使用して設定）。`duplicate_purchase` 列で使用されます。 | char(20) |
| | **`quarterly_visitor`** | ヒットが新しい四半期別訪問者であるかどうかを判定するフラグ。 | tinyint unsigned |
| **`post_`** | **`referrer`** | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。`referrer` のデータ型は varchar(255)、`post_referrer` のデータ型は varchar(244) です。 | varchar （255） <br>varchar （244） |
| | **`ref_domain`** | 「[参照ドメイン](/help/components/dimensions/referring-domain.md)」ディメンション。`referrer` 列に基づきます。 | varchar(100) |
| | **`ref_type`** | ヒットのリファラルのタイプを表す数値 ID。「[リファラータイプ](/help/components/dimensions/referrer-type.md)」ディメンションで使用されます。<br>1：サイト内 <br>2：その他の Web サイト <br>3：検索エンジン <br>4：ハードドライブ <br>5:USENET<br>6：型指定/ブックマーク（リファラーなし） <br>7：電子メール <br>8:JavaScriptなし <br>9：ソーシャルネットワーク <br>10：対話型 AI ツール | tinyint unsigned |
| | **`resolution`** | モニターの解像度を表す数値 ID。「[画面の解像度](/help/components/dimensions/monitor-resolution.md)」ディメンションで使用されます。`resolution.tsv` ルックアップテーブルを使用します。 | smallint unsigned |
| **`post_`** | **`search_engine`** | サイトに訪問者を誘導した検索エンジンを表す数値 ID。「[検索エンジン](/help/components/dimensions/search-engine.md)」ディメンションで使用されます。 `search_engines.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| | **`search_page_num`** | 「[すべての検索ページのランク](/help/components/dimensions/all-search-page-rank.md)」ディメンションで使用されます。ユーザーがクリックスルーしてサイトに到達する前にサイトが表示された検索結果ページを示します。 | smallint unsigned |
| | **`secondary_hit`** | ヒットがセカンダリヒットかどうかを判定するフラグ。 このフラグは通常、ヒットをコピーするマルチスイートタグ付けおよび VISTA ルールで発生します。 | tinyint unsigned |
| | **`sourceid`** | ソース ID | int unsigned |
| | **`stats_server`** | 未使用。ヒットを処理したアドビの内部サーバー。 | char(30) |
| **`post_`** | **`s_kwcid`** | Adobe Advertising 統合で使用されるキーワード ID。 | varchar(255) |
| | **`s_resolution`** | 画面解像度の未処理の値。JavaScript 関数 `screen.width x screen.height` を使用して収集します。 | char(20) |
| **`post_`** | **`tnt`** | Adobe Target 統合で使用されます。現在認定されているすべてのテストを表します。形式は次のとおりです。`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action` | text |
| **`post_`** | **`tnt_action`** | Adobe Target 統合で使用されます。ヒットが認定されるすべてのテストを表します。 | text |
| | **`tnt_instances`** | Adobe Target 統合で使用されます。Target インスタンス変数。 | text |
| **`post_`** | **`transactionid`** | 様々なデータポイントをデータソースから後でアップロードできる一意の識別子。 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 変数を使用して収集します。 | text |
| | **`truncated_hit`** | イメージリクエストが切り捨てられた（部分的なヒットを受信した）ことを示すフラグ。 <br>Y：ヒットが切り捨てられました。ヒットの一部を受信しました。<br>N：ヒットが切り捨てられませんでした。すべてのヒットを受信しました。 | char(1) |
| **`post_`** | **`t_time_info`** | 訪問者の現地時刻。形式：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| | **`userid`** | 未使用。レポートスイート ID の数値 ID。代わりに、`username` を使用してください。 | int unsigned |
| | **`username`** | ヒットのレポートスイート ID。 | char(40) |
| | **`user_agent`** | イメージリクエストの HTTP ヘッダーで送信されるユーザーエージェント文字列。 | text |
| | **`user_hash`** | 未使用。 レポートスイート ID のハッシュ。代わりに、`username` を使用してください。 | int unsigned |
| **`post_`** | **`user_server`** | 「[サーバー](/help/components/dimensions/server.md)」ディメンションで使用されます。 | varchar(100) |
| | **`va_closer_detail`** | 「[ラストタッチの詳細](/help/components/dimensions/last-touch-detail.md)」ディメンション。 | varchar(255) |
| | **`va_closer_id`** | 「[ラストタッチチャネル](/help/components/dimensions/last-touch-channel.md)」ディメンションを識別する数値 ID。この ID のルックアップは、マーケティングチャネルマネージャーで確認できます。 | tinyint unsigned |
| | **`va_finder_detail`** | 「[ファーストタッチの詳細](/help/components/dimensions/first-touch-detail.md)」ディメンション。 | varchar(255) |
| | **`va_finder_id`** | 「[ファーストタッチチャネル](/help/components/dimensions/first-touch-channel.md)」ディメンションを識別する数値 ID。この ID のルックアップは、マーケティングチャネルマネージャーで確認できます。 | tinyint unsigned |
| | **`va_instance_event`** | マーケティングチャネル[インスタンス](/help/components/metrics/instances.md)を識別するフラグ。 | tinyint unsigned |
| | **`va_new_engagement`** | マーケティングチャネル[新規エンゲージメント](/help/components/metrics/new-engagements.md)を識別するフラグ。 | tinyint unsigned |
| **`post_`** | **`video`** | 「[コンテンツ](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoad`** | 「[広告](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoadinpod`** | 「[ポッド位置の広告](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoadlength`** | 「[広告の長さ（変数）](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | integer |
| **`post_`** | **`videoadname`** | 「[広告名（変数）](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoadplayername`** | 「[広告プレーヤー名](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoadpod`** | 「[広告ポッド](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoadvertiser`** | 「[広告主](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoaudioalbum`** | 「[アルバム](/help/components/dimensions/sm-audio-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoaudioartist`** | 「[アーティスト](/help/components/dimensions/sm-audio-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoaudioauthor`** | 「[オーサー](/help/components/dimensions/sm-audio-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoaudiolabel`** | 「[ラベル](/help/components/dimensions/sm-audio-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoaudiopublisher`** | 「[パブリッシャー](/help/components/dimensions/sm-audio-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoaudiostation`** | 「[ステーション](/help/components/dimensions/sm-audio-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videocampaign`** | 「[キャンペーン ID](/help/components/dimensions/sm-ads.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videochannel`** | 「[コンテンツチャネル](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videochapter`** | 「[チャプター](/help/components/dimensions/sm-chapters.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videocontenttype`** | 「[コンテンツタイプ](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videodaypart`** | 「[日分割](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoepisode`** | 「[エピソード](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videofeedtype`** | 「[メディアフィードのタイプ](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videogenre`** | 「[ジャンル](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 このディメンションでは、コンマで区切られた複数の値が同じヒットに許可されます。 | text |
| **`post_`** | **`videolength`** | 「[コンテンツの長さ（変数）](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | integer |
| **`post_`** | **`videomvpd`** | 「[MVPD](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoname`** | 「[コンテンツ名（変数）](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videonetwork`** | 「[ネットワーク](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videopath`** | 「[メディアパス](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(100) |
| **`post_`** | **`videoplayername`** | 「[コンテンツプレーヤー名](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoqoebitrateaverageevar`** | 「[平均ビットレート](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoqoebitratechangecountevar`** | 「[ビットレートの変更](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoqoebuffercountevar`** | 「[バッファーイベント](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoqoebuffertimeevar`** | 「[合計バッファー時間](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoqoedroppedframecountevar`** | 「[ドロップフレーム](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoqoeerrorcountevar`** | 「[エラー](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videoqoeextneralerrors`** | 「[外部エラー ID](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。このディメンションでは、複数の値が同じヒットに許可されます。 | text |
| **`post_`** | **`videoqoeplayersdkerrors`** | 「[プレーヤー SDK エラー ID](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。このディメンションでは、複数の値が同じヒットに許可されます。 | text |
| **`post_`** | **`videoqoetimetostartevar`** | 「[開始時間](/help/components/dimensions/sm-quality.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoseason`** | 「[シーズン](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videosegment`** | 「[コンテンツセグメント](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videosessionid`** | [ メディアセッション ID](/help/components/dimensions/sm-core.md) ストリーミングメディアサービス ディメンション。 | varchar(255) |
| **`post_`** | **`videoshow`** | 「[表示](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`videoshowtype`** | 「[表示タイプ](/help/components/dimensions/sm-video-metadata.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| | **`videostreamtype`** | 「[ストリームタイプ](/help/components/dimensions/sm-core.md)」ストリーミングメディアサービスディメンション。 | varchar(255) |
| **`post_`** | **`visid_high`** | `visid_low` と共に使用し、訪問者を一意に識別します。 | bigint unsigned |
| **`post_`** | **`visid_low`** | `visid_high` と共に使用し、訪問者を一意に識別します。 | bigint unsigned |
| | **`visid_new`** | ヒットに新しく生成された訪問者 ID が含まれているかどうかを判定するフラグ。 | char(1) |
| | **`visid_timestamp`** | 訪問者 ID が新しく生成された場合は、訪問者 ID が生成された時刻の UNIX® 時間でのタイムスタンプを示します。 | int |
| **`post_`** | **`visid_type`** | 内部使用のみ。処理の最適化のためにアドビが内部的に使用します。訪問者の識別に使用された方法を表す数値 ID。<br>`0`：カスタム訪問者 ID または不明／該当なし<br>`1`：IP およびユーザーエージェントのフォールバック<br>`2`：HTTP モバイル加入者ヘッダー<br>`3`：従来の cookie 値（`s_vi`）<br>`4`：フォールバック cookie の値（`s_fid`）<br>`5`：ID サービス | tinyint unsigned |
| **`post_`** | **`visit_keywords`** | 「[検索キーワード](/help/components/dimensions/search-keyword.md)」ディメンション。この列では、Adobeで使用されるバックエンドロジックに対応するために、varchar （244）という非標準の文字制限を使用します。 後処理列は `**post_keywords**` ではなく `**post_visit_keywords**` です。 | varchar(244) |
| | **`visit_num`** | 「[訪問回数](/help/components/dimensions/visit-number.md)」ディメンション。1 から始まり、各訪問者が新しい訪問を開始するたびに増分されます。 | int unsigned |
| | **`visit_page_num`** | 「[ヒット深度](/help/components/dimensions/hit-depth.md)」ディメンション。 訪問者が生成するヒットごとに 1 ずつ増加します。各訪問をリセットします。 | int unsigned |
| | **`visit_referrer`** | 訪問の最初のリファラー。 | varchar(255) |
| | **`visit_ref_domain`** | `visit_referrer` 列に基づきます。訪問の最初の参照ドメイン。 | varchar(100) |
| | **`visit_ref_type`** | 訪問の最初のリファラーのリファラータイプを表す数値 ID。`referrer_type.tsv`ルックアップテーブルを参照します。 | tinyint unsigned |
| | **`visit_search_engine`** | 訪問の最初の検索エンジンを表す数値 ID。`search_engines.tsv`ルックアップテーブルを参照します。 | smallint unsigned |
| | **`visit_start_pagename`** | 訪問の最初のヒットの [ ページ ](/help/components/dimensions/page.md)。 | varchar(100) |
| | **`visit_start_page_url`** | 訪問の最初のヒットの URL。 | varchar(255) |
| | **`visit_start_time_gmt`** | 訪問の最初のヒットのタイムスタンプ（UNIX® 時間）。 | int |
| | **`weekly_visitor`** | ヒットが新しい週別訪問者であるかどうかを判定するフラグ。 | tinyint unsigned |
| | **`yearly_visitor`** | ヒットが新しい年別訪問者であるかどうかを判定するフラグ。 | tinyint unsigned |
| **`post_`** | **`zip`** | 「[郵便番号](/help/components/dimensions/zip-code.md)」ディメンションの生成に役立ちます。関連トピック 「`geo_zip`」を参照してください。 | varchar(50) |

## 未使用または廃止された列

次の列のリストは、未使用、廃止、またはレポートに値が含まれません。これらの列の一部は廃止された機能に関連付けられていますが、他の列は新機能やより堅牢な機能により不要になりました。これらの列のほとんどにはデータが含まれていません。まだデータが含まれている可能性のある列は、現在のデータ収集ライブラリではサポートされておらず、Analysis Workspace で使用できるディメンションではありません。

| 投稿 | 列名 |
| ---: | :--- |
| `post_` | `adclassificationcreative` |
| | `click_action` |
| | `click_action_type` |
| | `click_context` |
| | `click_context_type` |
| | `click_sourceid` |
| | `click_tag` |
| | `dataprivacydmaconsent` |
| `post_` | `hier1` - `hier5` |
| | `homepage` |
| | `ip2` |
| | `mobileacquisitionclicks` |
| | `mobileactioninapptime` |
| | `mobileactiontotaltime` |
| | `mobileappperformanceaffectedusers` |
| | `mobileappperformanceappid.app-perf-app-name` |
| | `mobileappperformanceappid.app-perf-platform` |
| | `mobileappperformancecrashes` |
| | `mobileappperformancecrashid.app-perf-crash-name` |
| | `mobileappperformanceloads` |
| | `mobileappstoreavgrating` |
| | `mobileappstoredownloads` |
| | `mobileappstoreinapprevenue` |
| | `mobileappstoreinapproyalties` |
| | `mobileappstoreobjectid.app-store-user` |
| | `mobileappstoreobjectid.application-name` |
| | `mobileappstoreobjectid.application-version` |
| | `mobileappstoreobjectid.appstore-name` |
| | `mobileappstoreobjectid.category-name` |
| | `mobileappstoreobjectid.country-name` |
| | `mobileappstoreobjectid.device-manufacturer` |
| | `mobileappstoreobjectid.device-name` |
| | `mobileappstoreobjectid.in-app-name` |
| | `mobileappstoreobjectid.platform-name-version` |
| | `mobileappstoreobjectid.rank-category-type` |
| | `mobileappstoreobjectid.region-name` |
| | `mobileappstoreobjectid.review-comment` |
| | `mobileappstoreobjectid.review-title` |
| | `mobileappstoreoneoffrevenue` |
| | `mobileappstoreoneoffroyalties` |
| | `mobileappstorepurchases` |
| | `mobileappstorerank` |
| | `mobileappstorerankdivisor` |
| | `mobileappstorerating` |
| | `mobileappstoreratingdivisor` |
| | `mobileavgprevsessionlength` |
| | `mobilecrashes` |
| | `mobilecrashrate` |
| | `mobiledailyengagedusers` |
| | `mobiledayssincelastupgrade` |
| | `mobiledeeplinkid.name` |
| | `mobileinstalls` |
| | `mobilelaunches` |
| | `mobilelaunchessincelastupgrade` |
| `post_` | `mobileltv` |
| | `mobileltvtotal` |
| `post_` | `mobilemessageclicks` |
| `post_` | `mobilemessageid.dest` |
| `post_` | `mobilemessageid.name` |
| `post_` | `mobilemessageid.type` |
| `post_` | `mobilemessageimpressions` |
| `post_` | `mobilemessagepushpayloadid.name` |
| `post_` | `mobilemessageviews` |
| | `mobilemonthlyengagedusers` |
| | `mobileosenvironment` |
| | `mobileplacedwelltime` |
| | `mobileplaceentry` |
| | `mobileplaceexit` |
| | `mobileprevsessionlength` |
| | `mobilerelaunchcampaigntrackingcode.name` |
| | `mobileupgrades` |
| | `namespace` |
| | `p_plugins` |
| `post_` | `page_event_var3` |
| `post_` | `partner_plugins` |
| | `plugins` |
| | `prev_page` |
| | `product_merchandising` |
| | `sampled_hit` |
| | `service` |
| `post_` | `socialaccountandappids` |
| `post_` | `socialassettrackingcode` |
| `post_` | `socialauthor` |
| `post_` | `socialaveragesentiment` |
| `post_` | `socialaveragesentiment (deprecated)` |
| `post_` | `socialcontentprovider` |
| `post_` | `socialfbstories` |
| `post_` | `socialfbstorytellers` |
| `post_` | `socialinteractioncount` |
| `post_` | `socialinteractiontype` |
| `post_` | `sociallanguage` |
| `post_` | `sociallatlong` |
| `post_` | `sociallikeadds` |
| `post_` | `sociallink` |
| `post_` | `sociallink (deprecated)` |
| `post_` | `socialmentions` |
| `post_` | `socialowneddefinitioninsighttype` |
| `post_` | `socialowneddefinitioninsightvalue` |
| `post_` | `socialowneddefinitionmetric` |
| `post_` | `socialowneddefinitionpropertyvspost` |
| `post_` | `socialownedpostids` |
| `post_` | `socialownedpropertyid` |
| `post_` | `socialownedpropertyname` |
| `post_` | `socialownedpropertypropertyvsapp` |
| `post_` | `socialpageviews` |
| `post_` | `socialpostviews` |
| `post_` | `socialproperty` |
| `post_` | `socialproperty (deprecated)` |
| `post_` | `socialpubcomments` |
| `post_` | `socialpubposts` |
| `post_` | `socialpubrecommends` |
| `post_` | `socialpubsubscribers` |
| `post_` | `socialterm` |
| `post_` | `socialtermslist` |
| `post_` | `socialtermslist (deprecated)` |
| `post_` | `socialtotalsentiment` |
| `post_` | `state` |
| `post_` | `survey` |
| | `survey_instances` |
| | `tnt_post_vista` |
| | `ua_color` |
| | `ua_os` |
| | `ua_pixels` |
| | `videoadload` |
| `post_` | `videoauthorized` |
| | `videoaverageminuteaudience` |
| | `videochaptercomplete` |
| | `videochapterstart` |
| | `videochaptertime` |
| | `videopause` |
| | `videopausecount` |
| | `videopausetime` |
| | `videoplay` |
| | `videoprogress10` |
| | `videoprogress25` |
| | `videoprogress50` |
| | `videoprogress75` |
| | `videoprogress96` |
| | `videoqoebitrateaverage` |
| | `videoqoebitratechange` |
| | `videoqoebuffer` |
| | `videoqoedropbeforestart` |
| | `videoqoedroppedframes` |
| | `videoqoeerror` |
| | `videoresume` |
| | `videotime` |
| | `videototaltime` |
| | `videouniquetimeplayed` |

>[!MORELIKETHIS]
>
>[XDM オブジェクト変数のマッピング](/help/implement/aep-edge/xdm-var-mapping.md)
>[データオブジェクト変数のマッピング](/help/implement/aep-edge/data-var-mapping.md)
