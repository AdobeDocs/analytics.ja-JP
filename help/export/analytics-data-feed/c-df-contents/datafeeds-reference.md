---
description: データフィードの各列について説明するテーブルデータです。
keywords: Data Feed;columns
subtopic: data feeds
title: データ列リファレンス
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# データ列リファレンス

このページを使用して、各列に含まれるデータを確認します。ほとんどの実装ではすべての列を使用していないので、データフィードの書き出しに含める列を決定する際には、このページを参考にすることができます。

>[!IMPORTANT]指定された列（例えば、255 文字として定義された列）では、文字列内の値をエスケープする文字の追加により、データフィードは追加の文字を送信する可能性があります。実装によって文字制限を超える値を定期的に送信する場合は、これらの追加の文字の可能性に注意してください。

## 列、説明、データタイプ

>[!NOTE]ほとんどの列には、`post_` というプレフィックスが付く類似の列が含まれています。post 列には、サーバー側ロジック、処理ルール、VISTA ルールの適用後の値が格納されます。ほとんどの場合、post 列を使用することをお勧めします。詳しくは、[データフィードに関する FAQ](../df-faq.md) を参照してください。

| 列名 | 列の説明 | データタイプ |
| --- | --- | --- |
| `accept_language` | リスト要求のAccept-Language HTTPヘッダーに示される、許可されたすべての言語。 | char(20) |
| `aemassetid` | 一連のAdobe Experience Manager AssetsのアセットID(GUID)に対応する複数値の変数。 インプレッションイベントを増分 | text |
| `aemassetsource` | アセットのソースを識別します。イベント。 Adobe Experience Managerで使用されます。 | varchar(255) |
| `aemclickedassetid` | Adobe Experience ManagerアセットのアセットID。 増分クリックイベント | varchar(255) |
| `browser` | ブラウザーの数値ID。 browser.tsv参照テーブルを参照します。 | int unsigned |
| `browser_height` | ブラウザーウィンドウの高さ（ピクセル単位）。 | smallint unsigned |
| `browser_width` | ブラウザーウィンドウの幅（ピクセル単位）。 | smallint unsigned |
| `c_color` | カラーパレットのビット深度。 色深度ディメンションの計算の一部として使用されます。 JavaScript関数screen.colorDepth()を使用します。 | char(20) |
| `campaign` | トラッキングコードディメンションで使用される変数。 | varchar(255) |
| `carrier` | Adobe Advertising Cloud統合変数。 携帯電話会社を指定します。 配送業者の参照テーブルを参照します。 | varchar(100) |
| `channel` | サイトセクションディメンションで使用される変数。 | varchar(100) |
| `click_action` | 廃止。レガシーのClickmapツールでリンクされたクリックのアドレス。 | varchar(100) |
| `click_action_type` | 廃止。従来のClickmapツールのリンクタイプ。<br>0：HREF URL<br>1：カスタム ID<br>2：JavaScript onClick イベント<br>3：フォーム要素 | tinyint unsigned |
| `click_context` | 廃止。リンクがクリックされたページ名。 従来のClickMapツールの一部。 | varchar(255) |
| `click_context_type` | 廃止。click_contextにページ名があったか、デフォルトでページURLが設定されているかを示します。<br>0：ページ URL<br>1：ページ名 | tinyint unsigned |
| `click_sourceid` | 廃止。クリックされたリンクのページ上の場所の数値ID。 従来のClickMapツールの一部。 | int unsigned |
| `click_tag` | 廃止。クリックされたHTML要素のタイプ。 | char(10) |
| `clickmaplink` | Activity Maplink | varchar(255) |
| `clickmaplinkbyregion` | Activity Map 地域別リンク | varchar(255) |
| `clickmappage` | Activity Map ページ | varchar(255) |
| `clickmapregion` | Activity Map 地域 | varchar(255) |
| `code_ver` | イメージリクエストのコンパイルと送信に使用するAppMeasurement Libraryのバージョン。 | char(16) |
| `color` | c_color列の値に基づく色深度ID。 color_depth.tsv参照テーブルを参照します。 | smallint unsigned |
| `connection_type` | 接続タイプを表す数値ID。 Connection Typeディメンションで使用される変数。 connection_type.tsv参照テーブルを参照します。 | tinyint unsigned |
| `cookies` | cookieサポートディメンションで使用される変数。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| `country` | ヒット元の国を表す数値ID。 アドビはDigital Envoyと提携し、IPアドレスを国と照合します。 country.tsv参照を使用します。 | smallint unsigned |
| `ct_connect_type` | connection_type列に関連します。 最も一般的な値は、LAN/Wi-Fi、Mobile Carrier、Modemです。 | char(20) |
| `curr_factor` | 通貨の小数点以下の桁数を決定し、通貨の換算に使用します。 例えば、USDでは小数点第3位が2桁使用されるので、この列の値は2となります。 | tinyint |
| `curr_rate` | トランザクションが発生したときの為替レート。 アドビはXEと提携し、現在の日の為替レートを決定します。 | decimal(24,12) |
| `currency` | トランザクション中に使用された通貨コード。 | char(8) |
| `cust_hit_time_gmt` | タイムスタンプが有効なレポートスイートのみ。 Unix時間に基づく、ヒットと共に送信されるタイムスタンプ。 | int |
| `cust_visid` | カスタム訪問者IDが設定されている場合は、この列に入力されます。 | varchar(255) |
| `daily_visitor` | ヒットが新しい日別訪問者かどうかを指定するフラグ。 | tinyint unsigned |
| `date_time` | レポートスイートのタイムゾーンに基づく、読み取り可能な形式のヒットの時間。 | 日時 |
| `domain` | Domainディメンションで使用される変数。 ユーザーのインターネットサービスプロバイダー(ISP)に基づきます。 | varchar(100) |
| `duplicate_events` | リストとしてカウントされた各イベント。重複。 | varchar(255) |
| `duplicate_purchase` | このヒットの購入イベントが重複であるため無視する必要があることを示すフラグ。 | tinyint unsigned |
| `duplicated_from` | ヒットコピーVISTAルールを含むレポートスイートでのみ使用されます。 ヒットのコピー元のレポートスイートを示します。 | varchar(40) |
| `ef_id` | Adobe Advertising Cloud統合で使用されるef_id。 | varchar(255) |
| `evar1 - evar250` | カスタム変数1 ～ 250。 eVarの使用方法は組織によって異なります。 組織が各eVarをどのように入力するかに関する詳細を得るには、組織固有のソリューションデザインドキュメントが最適です。 | varchar(255) |
| `event_list` | ヒットでトリガーされるリストを表す数値IDのイベントをコンマで区切って表します。 デフォルトのイベントとカスタムイベント1 ～ 1000が含まれます。 イベント.tsv参照を使用します。 | text |
| `exclude_hit` | ヒットを示すフラグがレポートから除外 除外されたヒットに対しては visit_num 列は増分されません。<br>1：未使用。削除されたフィーチャの一部。<br>2：未使用。削除されたフィーチャの一部。<br>3：廃止。ユーザーエージェントの除外<br>4：IP アドレスに基づく除外<br>5：重要なヒット情報（page_url、pagename、page_event、event_listなどがない）<br>6：JavaScript でヒットが正しく処理されませんでした<br>7：アカウント固有の除外（VISTA ルールなど）<br>8：未使用。代替のアカウント固有の除外。<br>9：未使用。削除されたフィーチャの一部。<br>10：無効な通貨コード<br>11：タイムスタンプのみのレポートスイートでヒットにタイムスタンプが含まれていない、またはタイムスタンプ以外のレポートスイートでヒットにタイムスタンプが含まれている<br>12:未使用。削除されたフィーチャの一部。<br>13：未使用。削除されたフィーチャの一部。<br>14：Analytics と一致しないターゲットヒット<br>15：現在は使用されていません。<br>16：Analytics ヒットと一致しない Advertising Cloud ヒット | tinyint unsigned |
| `first_hit_page_url` | 訪問者の最初のURL。 | varchar(255) |
| `first_hit_pagename` | 入口ページの元のディメンションで使用される変数。 オリジナルのエントリページ名(訪問者)。 | varchar(100) |
| `first_hit_ref_domain` | 元の参照ドメインディメンションで使用される変数。 first_hit_転送者。 ドメインの最初の参照訪問者。 | varchar(100) |
| `first_hit_ref_type` | 最初の転送者の転送者タイプを表す数値ID。 転送者タイプ.tsv参照を使用します。 | tinyint unsigned |
| `first_hit_referrer` | 訪問者の最初の参照URL。 | varchar(255) |
| `first_hit_time_gmt` | Unix時間での訪問者の最初のヒットのタイムスタンプ。 | int |
| `geo_city` | IPに基づく、ヒット元の市区町村の名前。 アドビはDigital Envoyと提携し、IPアドレスを市区町村と照合します。 | char(32) |
| `geo_country` | IPに基づく、ヒット元の国の略称。 アドビはDigital Envoyと提携し、IPアドレスを国と照合します。 | char(4) |
| `geo_dma` | IPに基づく、ヒット元の人口統計領域の数値ID。 アドビはDigital Envoyと提携し、IPアドレスを人口統計領域と照合します。 | int unsigned |
| `geo_region` | IPに基づく、ヒット元の州または地域の名前。 アドビはDigital Envoyと提携し、IPアドレスを州/地域と照合します。 | char(32) |
| `geo_zip` | ヒットの発生元となった場所の郵便番号（IP アドレスに基づく）。アドビはDigital Envoyと提携し、IPアドレスと郵便番号を照合します。 | varchar(16) |
| `hier1 - hier5` | 階層変数で使用されます。 値の区切りリストが含まれます。 区切り文字は、レポートスイートの設定で選択されます。 | varchar(255) |
| `hit_source` | ヒットの発生源を示します。<br>1：標準的な画像リクエスト（タイムスタンプなし）<br>2：標準的な画像リクエスト（タイムスタンプあり）<br>3：ライブデータソースのアップロード（タイムスタンプあり）<br>4：未使用<br>5：汎用データソースのアップロード<br>6：完全な処理データソースのアップロード<br>7：TransactionID データソースのアップロード<br>8：廃止。Adobe Advertising Cloud の以前のバージョンのデータソース<br>9：廃止。Adobe Social サマリ指標 | tinyint unsigned |
| `hit_time_gmt` | Unix 時間に基づく、ヒットを受け取ったアドビデータ収集サーバーのタイムスタンプ。 | int |
| `hitid_high` | hitid_lowと組み合わせて使用し、ヒットを一意に識別します。 | bigint unsigned |
| `hitid_low` | hitid_highと組み合わせて使用し、ヒットを一意に識別します。 | bigint unsigned |
| `homepage` | 廃止。現在のURLがブラウザーのホームページであるかどうかを示します。 | char(1) |
| `hourly_visitor` | ヒットが新しい時間別訪問者かどうかを指定するフラグ。 | tinyint unsigned |
| `ip` | イメージリクエストのHTTPヘッダーに基づくIPアドレス。 | char(20) |
| `ip2` | 未使用。IPアドレスに基づくVISTAルールを含むレポートスイートのバックエンド参照変数。 | char(20) |
| `j_jscript` | ブラウザーでサポートされているJavaScriptのバージョン。 | char(5) |
| `java_enabled` | Java が有効かどうかを示すフラグ。<br>Y：有効<br>N：無効<br>U：不明 | char(1) |
| `javascript` | j_jscriptに基づくJavaScriptバージョンの参照ID。 参照テーブルを使用します。 | tinyint unsigned |
| `language` | 言語の数値ID。 languages.tsv参照テーブルを使用します。 | smallint unsigned |
| `last_hit_time_gmt` | 以前のヒットのタイムスタンプ（Unix時間）。 前回の訪問からの日数ディメンションの計算に使用されます。 | int |
| `last_purchase_num` | 顧客忠誠度ディメンションで使用される変数。 訪問者がこれまでにおこなった購入の回数を示します。<br>0：過去に購入したことがない（顧客以外）<br>1：過去に 1 回購入したことがある（新規顧客）<br>2：過去に 2 回購入したことがある（リターン顧客）<br>3：過去に 3 回以上購入したことがある（常連客） | int unsigned |
| `last_purchase_time_gmt` | 前回購入からの日数ディメンションで使用されます。 最後に行われた購入のタイムスタンプ（Unix時間）。 初回の購入時および訪問者が以前に購入していない場合、この値は0です。 | int |
| `latlon1` | ロケーション（半径 10 km 以内） | varchar(255) |
| `latlon23` | ロケーション（半径 100 m 以内） | varchar(255) |
| `latlon45` | ロケーション（半径 1 m 以内） | varchar(255) |
| `mc_audiences` | リストが属するオーディエンスマネージャーセグメントIDの訪問者。 | text |
| `mcvisid` | Experience Cloud 訪問者 ID。19桁に埋め込まれた2つの64ビットの連結番号で構成される128ビットの数値。 | varchar(255) |
| `mobile_id` | ユーザーがモバイルデバイスを使用している場合は、そのデバイスの数値 ID。 | int |
| `mobileaction` | モバイルアクション。 Mobile Services で trackAction が呼び出されると、自動的に収集されます。アプリケーション内で自動的にアクションを渡すことができるようにします。 | varchar(100) |
| `mobileappid` | モバイルアプリケーション ID。アプリケーションの名前とバージョンを次の形式で格納します。[AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | Apteligent データコネクタで使用されます。Apteligent で使用されるアプリケーション ID。 | varchar(255) |
| `mobileappperformancecrashid` | Apteligent データコネクタで使用されます。Apteligent で使用されるクラッシュ ID。 | varchar(255) |
| `mobileappstoreobjectid` | Appfigures データコネクタで使用されます。App Store オブジェクト ID | varchar(255) |
| `mobilebeaconmajor` | Mobile Services ビーコンのメジャー番号 | varchar(100) |
| `mobilebeaconminor` | Mobile Services ビーコンのマイナー番号 | varchar(100) |
| `mobilebeaconproximity` | Mobile Services ビーコンの近接性 | varchar(255) |
| `mobilebeaconuuid` | Mobile Services ビーコンの UUID | varchar(100) |
| `mobilecampaigncontent` | リンクを表示したコンテンツの名前またはID。 モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignmedium` | マーケティングメディア（バナーや電子メールなど）。 モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignname` | キャンペーンの名前。キャンペーン変数にも格納されます。モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignsource` | 元の転送者（ニュースレターやソーシャルメディアネットワークなど）。 モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobilecampaignterm` | この獲得で追跡する有料キーワードまたはその他のキーワード。 モバイルアプリケーションの獲得によって設定されます。 | varchar(255) |
| `mobiledayofweek` | アプリが起動された曜日の数です。 | varchar(255) |
| `mobiledayssincefirstuse` | アプリが初めて実行されてからの日数。 | varchar(255) |
| `mobiledayssincelastupgrade` | コンテキストデータ変数 a.DaysSinceLastUpgrade から収集されます。前回のセッションからの経過日数。 | varchar(255) |
| `mobiledayssincelastuse` | アプリが最後に実行されてからの日数。 | varchar(255) |
| `mobiledeeplinkid` | コンテキストデータ変数 a.<span>deeplink</span>.id から収集します。獲得レポートで、モバイル獲得リンクの識別子として使用されます。 | varchar(255) |
| `mobiledevice` | モバイルデバイス名。 iOSでは、コンマ区切りの2桁の文字列として保存されます。 最初の数はデバイスの生成を表し、2番目の数はデバイスのファミリを表します。 | varchar(255) |
| `mobilehourofday` | アプリが起動された日の時間を定義します。 24時間形式に従います。 | varchar(255) |
| `mobileinstalldate` | モバイルインストール日。 ユーザーがモバイルアプリを初めて開いた日付を指定します。 | varchar(255) |
| `mobilelaunchessincelastupgrade` | コンテキストデータ変数 a.LaunchesSinceUpgrade から取得します。前回のアップグレード以降の起動回数を報告します。 | varchar(255) |
| `mobilelaunchnumber` | モバイルアプリが起動されるたびに1増分されます。 | varchar(255) |
| `mobileltv` | 廃止。trackLifetimeValue メソッドによって設定されます。 | varchar(255) |
| `mobilemessagebuttonname` | コンテキストデータ変数 a.<span>message</span>.button.id から収集します。メッセージを閉じたボタンを識別するために、アプリ内メッセージで使用します。 | varchar(100) |
| `mobilemessageid` | アプリ内メッセージ ID | varchar(255) |
| `mobilemessageonline` | アプリ内メッセージオンライン | varchar(255) |
| `mobilemessagepushoptin` | コンテキストデータ変数 a.push.optin から収集されます。ユーザーがプッシュメッセージをオプトインする場合は「true」に設定します。それ以外の場合、値は「false」です。 | varchar(255) |
| `mobilemessagepushpayloadid` | コンテキストデータ変数 a.push.payloadid から収集します。ペイロード識別子としてプッシュメッセージで使用します。 | varchar(255) |
| `mobileosenvironment` | コンテキストデータ変数 a.OSEnvironment から収集します。Android や iOS などの OS 環境を示します。 | varchar(255) |
| `mobileosversion` | Mobile Services のオペレーティングシステムのバージョン。 | varchar(255) |
| `mobileplaceaccuracy` | コンテキストデータ変数 a.loc.acc から収集します。収集時の GPS の精度をメートル単位で示します。 | varchar(255) |
| `mobileplacecategory` | コンテキストデータ変数 a.loc.category から収集します。特定の場所のカテゴリを示します。 | varchar(255) |
| `mobileplaceid` | コンテキストデータ変数 a.<span>loc</span>.id から収集します。特定の目標地点の識別子。 | varchar(255) |
| `mobilerelaunchcampaigncontent` | Mobile Services の起動コンテンツ | varchar(255) |
| `mobilerelaunchcampaignmedium` | Mobile Services の起動メディア | varchar(255) |
| `mobilerelaunchcampaignsource` | Mobile Services の起動ソース | varchar(255) |
| `mobilerelaunchcampaignterm` | Mobile Services の起動条件 | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | コンテキストデータ変数 a.launch.campaign.trackingcode から収集します。キャンペーン立ち上げのトラッキングコードとして、獲得で使用します。 | varchar(255) |
| `mobileresolution` | モバイルデバイスの解像度。 幅x高さ（ピクセル単位） | varchar(255) |
| `monthly_visitor` | 訪問者が現在の月に固有であることを示すフラグ。 | tinyint unsigned |
| `mvvar1`～`mvvar3` | リスト変数の値。 実装に応じて、リスト区切り形式のカスタム値が含まれます。 | text |
| `namespace` | 未使用。何年も前に削られた特集の一部だ。 | varchar(50) |
| `new_visit` | 現在のヒットが新しい訪問であるかどうかを指定するフラグ。 30分間無操作状態が続くと、アドビのサーバーによって設定されます。 | tinyint unsigned |
| `os` | オペレーティングシステムを表す数値ID訪問者。 user_agent列に基づきます。 OS参照を使用します。 | int unsigned |
| `p_plugins` | 廃止。リストで使用できるプラグインのブラウザー。 JavaScript関数navigator.plugins()を使用。 | text |
| `page_event` | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、カスタムリンク、離脱リンク）。[ページイベント参照](datafeeds-page-event.md)を参照してください。 | tinyint unsigned |
| `page_event_var1` | リンクトラッキングイメージリクエストでのみ使用されます。 クリックされたダウンロードリンク、離脱リンクまたはカスタムリンクのURL。 | text |
| `page_event_var2` | リンクトラッキングイメージリクエストでのみ使用されます。 リンクのカスタム名（指定されている場合）。 | varchar(100) |
| `page_event_var3` | 廃止。調査とメディアモジュールのデータが含まれていました。 以前のバージョンのAdobe Analyticsで、レガシービデオレポートに入力されました。 | text |
| `page_type` | 404ページのみに使用される、エラーページディメンションの入力に使用されます。 この変数は、空か、「ErrorPage」を含む必要があります。 | char(20) |
| `page_url` | ヒットのURL。 リンクトラッキングイメージリクエストでは使用されません。 | varchar(255) |
| `pagename` | ページディメンションの入力に使用されます。 pagename変数が空の場合、Analyticsはpage_urlを代わりに使用します。 | varchar(100) |
| `paid_search` | ヒットが有料検索検知と一致した場合に設定されるフラグ。 | tinyint unsigned |
| `partner_plugins` | 未使用。何年も前に削られた特集の一部だ。 | varchar(255) |
| `persistent_cookie` | 永続的なcookieサポートディメンションで使用されます。 各ヒットの後に破棄されないcookieが訪問者でサポートされているかどうかを示します。 | char(1) |
| `plugins` | 廃止。リストー内で使用可能なプラグインに対応する数値ID。 plugins.tsv参照を使用します。 | varchar(180) |
| `pointofinterest` | Mobile Services 目標地点の名前 | varchar(255) |
| `pointofinterestdistance` | 目標地点中心までの Mobile Services の距離 | varchar(255) |
| `post_ columns` | レポートで最終的に使用される値が含まれます。 各post列は、サーバー側のロジック、処理ルールおよびVISTAルールの後に設定されます。 ほとんどの場合、post 列を使用することをお勧めします。 | それぞれの非投稿列を参照 |
| `prev_page` | 未使用。前のページのアドビ固有の識別子。 | int unsigned |
| `product_list` | 製品リストを渡す製品変数。 製品はコンマで区切り、個々の製品プロパティはセミコロンで区切ります。 | text |
| `product_merchandising` | 未使用。代わりに、product_リストを使用します。 | text |
| `prop1`～`prop75` | カスタムトラフィック変数1 ～ 75。 | varchar(100) |
| `purchaseid` | s_purchaseID変数を使用して設定された、購入の一意の識別子。 重複_購入列で使用されます。 | char(20) |
| `quarterly_visitor` | ヒットが新しい四半期別訪問者かどうかを指定するフラグ。 | tinyint unsigned |
| `ref_domain` | 転送者列 ヒットの参照ドメイン。 | varchar(100) |
| `ref_type` | ヒットの参照のタイプを表す数値ID。<br>1：サイト内<br>2：その他の Web サイト<br>3：検索エンジン<br>4：ハードドライブ<br>5：USENET<br>6：手動入力／ブックマーク（リファラーなし）<br>7：電子メール<br>8：JavaScript なし<br>9：ソーシャルネットワーク | tinyint unsigned |
| `referrer` | 前のページのページURL。 データ型 `referrer` はvarchar(255)ですが、データ型 `post_referrer` はvarchar(244)です。 | varchar(255) |
| `resolution` | モニターの解像度を表す数値ID。 Monitor Resolutionディメンションを設定します。 resolution.tsv参照テーブルを使用します。 | smallint unsigned |
| `s_kwcid` | Adobe Advertising Cloud 統合で使用されるキーワード ID。 | varchar(255) |
| `s_resolution` | 生の画面解像度の値。 JavaScript関数screen.width x screen.heightを使用して収集されます。 | char(20) |
| `sampled_hit` | 廃止。以前は、Ad Hoc分析でのサンプリングに使用されていました。 | char(1) |
| `search_engine` | サイトに訪問者を導いた検索エンジンを表す数値ID。 search_engines.tsv参照を使用します。 | smallint unsigned |
| `search_page_num` | すべての検索ページのランクディメンションで使用されます。 ユーザがクリックスルーしてサイトに到達する前に、サイトが表示された検索結果のページを示します。 | smallint unsigned |
| `secondary_hit` | セカンダリヒットを追跡するフラグ。 通常、ヒットをコピーするマルチスイートタギングおよびVISTAルールに由来します。 | tinyint unsigned |
| `service` | 未使用。代わりにpage_イベントを使用します。 | char(2) |
| `socialaccountandappids` | 廃止。SocialアカウントとアプリID | varchar(255) |
| `socialassettrackingcode` | 廃止。ソーシャルキャンペーン変数 | varchar(255) |
| `socialauthor` | 廃止。発言者変数 | varchar(255) |
| `socialcontentprovider` | 廃止。ソーシャルプラットフォーム/プロパティ | varchar(255) |
| `socialinteractiontype` | 廃止。Socialインタラクションタイプ | varchar(255) |
| `sociallanguage` | 廃止。ソーシャル言語 | varchar(255) |
| `sociallatlong` | 廃止。ソーシャル緯度/経度 | varchar(255) |
| `socialowneddefinitioninsighttype` | 廃止。Social所有定義インサイトタイプ | varchar(255) |
| `socialowneddefinitioninsightvalue` | 廃止。Social所有定義インサイト値 | varchar(255) |
| `socialowneddefinitionmetric` | 廃止。Social所有定義指標 | varchar(255) |
| `socialowneddefinitionpropertyvspost` | 廃止。Social所有定義プロパティと投稿 | varchar(255) |
| `socialownedpostids` | 廃止。Social所有投稿ID | varchar(255) |
| `socialownedpropertyid` | 廃止。Social所有プロパティID | varchar(255) |
| `socialownedpropertyname` | 廃止。Social所有プロパティ名 | varchar(255) |
| `socialownedpropertypropertyvsapp` | 廃止。Social所有プロパティとアプリ | varchar(255) |
| `state` | 状態変数。 | varchar(50) |
| `stats_server` | 使用されません。 ヒットを処理したアドビの内部サーバー。 | char(30) |
| `t_time_info` | 訪問者のローカル時間。 形式は次のとおりです。M/D/YYYY HH:MM:SS Month （0-11, 0=1月）タイムゾーンのオフセット（分単位） | varchar(100) |
| `tnt` | アドビのターゲット統合で使用。 | text |
| `tnt_action` | アドビのターゲット統合で使用。 | text |
| `tnt_post_vista` | 廃止。代わりにpost_tntを使用します。 | text |
| `transactionid` | 様々なデータポイントを後でデータソースを介してアップロードできる一意の識別子。 | text |
| `truncated_hit` | イメージリクエストが切り捨てられたことを示すフラグ。 部分的なヒットを受信したことを示します。<br>Y：ヒットが切り捨てられました。ヒットの一部を受信しました。<br>N：ヒットが切り捨てられませんでした。すべてのヒットを受信しました。 | char(1) |
| `ua_color` | 廃止。以前は、色深度の代替として使用されていました。 | char(20) |
| `ua_os` | 廃止。以前は、オペレーティングシステムのフォールバックとして使用されていました。 | char(80) |
| `ua_pixels` | 廃止。以前は、ブラウザーの高さと幅のフォールバックとして使用されていました。 | char(20) |
| `user_agent` | イメージリクエストのHTTPヘッダーで送信されるユーザーエージェント文字列。 | text |
| `user_hash` | 使用されません。 レポートスイートIDのハッシュ。 代わりに、usernameを使用します。 | int unsigned |
| `user_server` | Serverディメンションで使用される変数。 | varchar(100) |
| `userid` | 使用されません。 レポートスイートIDの数値ID。 代わりに、usernameを使用します。 | int unsigned |
| `username` | ヒットのレポートスイートID。 | char(40) |
| `va_closer_detail` | ラストタッチの詳細ディメンションで使用される変数。 | varchar(255) |
| `va_closer_id` | ラストタッチディメンションを識別するチャネルID。 このIDの参照は、マーケティングチャネルマネージャーで確認できます。 | tinyint unsigned |
| `va_finder_detail` | ファーストタッチの詳細ディメンションで使用される変数。 | varchar(255) |
| `va_finder_id` | ファーストタッチディメンションを識別するチャネルID。 このIDの参照は、マーケティングチャネルマネージャーで確認できます。 | tinyint unsigned |
| `va_instance_event` | マーケティングチャネルインスタンスを識別するフラグ。 マーケティングチャネルのラストタッチインスタンス指標で使用されます。 | tinyint unsigned |
| `va_new_engagement` | マーケティングチャネルの新規エンゲージメントを識別するフラグ。 新規エンゲージメント指標で使用されます。 | tinyint unsigned |
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
| `videogenre` | ビデオのジャンル | text |
| `videolength` | ビデオの長さ | varchar(255) |
| `videomvpd` | ビデオ MVPD | varchar(255) |
| `videoname` | ビデオ名 | varchar(255) |
| `videonetwork` | ビデオネットワーク | varchar(255) |
| `videopath` | ビデオパス | varchar(100) |
| `videoplayername` | ビデオプレーヤー名 | varchar(255) |
| `videoqoebitrateaverageevar` | ビデオ画質の平均ビットレート | varchar(255) |
| `videoqoebitratechangecountevar` | ビデオ画質の変更数 | varchar(255) |
| `videoqoebuffercountevar` | ビデオ画質のバッファー数 | varchar(255) |
| `videoqoebuffertimeevar` | ビデオ画質バッファ時間 | varchar(255) |
| `videoqoedroppedframecountevar` | ビデオ画質のドロップフレーム数 | varchar(255) |
| `videoqoeerrorcountevar` | ビデオ画質エラー数 | varchar(255) |
| `videoqoeextneralerrors` | ビデオ画質の外部エラー | text |
| `videoqoeplayersdkerrors` | ビデオ画質 SDK エラー | text |
| `videoqoetimetostartevar` | ビデオ画質の開始 | varchar(255) |
| `videoseason` | ビデオシーズン | varchar(255) |
| `videosegment` | ビデオセグメント | varchar(255) |
| `videoshow` | ビデオショー | varchar(255) |
| `videoshowtype` | ビデオショーのタイプ | varchar(255) |
| `videostreamtype` | ビデオストリームのタイプ | varchar(255) |
| `visid_high` | visid_lowと組み合わせて使用し、訪問を一意に識別します。 | bigint unsigned |
| `visid_low` | visid_highと組み合わせて、訪問を一意に識別するために使用します。 | bigint unsigned |
| `visid_new` | ヒットに新しく生成された訪問者IDが含まれるかどうかを示すフラグ。 | char(1) |
| `visid_timestamp` | 訪問者IDが新しく生成された場合は、訪問者IDが生成された時点のタイムスタンプ（Unix時間）を示します。 | int |
| `visid_type` | 訪問者の識別に使用された方法を表す数値 ID。<br>0：カスタム 訪問者 ID<br>1：IP およびユーザーエージェントのフォールバック<br>2：HTTP モバイル加入者ヘッダー<br>3：従来のcookie値（s_vi）<br>4：フォールバックcookieの値（s_fid）<br>5：ID サービス | tinyint unsigned |
| `visit_keywords` | 「検索キーワード」ディメンションで使用される変数。この列では、アドビが使用するバックエンドロジックに対応するために、標準以外の文字制限が使用されます。 | varchar(244) |
| `visit_num` | 訪問回数ディメンションで使用される変数。 開始は1で、新しい訪問開始が発生するたびに増分されます。 | int unsigned |
| `visit_page_num` | ヒットの深さディメンションで使用される変数。 ユーザーが生成するヒットごとに1ずつ増加します。 各訪問をリセットします。 | int unsigned |
| `visit_ref_domain` | visit_転送者列 訪問の最初の参照ドメイン。 | varchar(100) |
| `visit_ref_type` | 訪問の最初の転送者の転送者タイプを表す数値ID。 転送者タイプ.tsv参照テーブルを使用します。 | tinyint unsigned |
| `visit_referrer` | 訪問の最初の転送者。 | varchar(255) |
| `visit_search_engine` | 訪問の最初の検索エンジンの数値ID。 search_engines.tsv参照テーブルを使用します。 | smallint unsigned |
| `visit_start_page_url` | 訪問の最初のURL。 | varchar(255) |
| `visit_start_pagename` | 訪問の最初のページ名。 | varchar(100) |
| `visit_start_time_gmt` | 訪問の最初のヒットのタイムスタンプ（UNIX時間）。 | int |
| `weekly_visitor` | ヒットが新しい週別訪問者かどうかを指定するフラグ。 | tinyint unsigned |
| `yearly_visitor` | ヒットが新しい年別訪問者かどうかを指定するフラグ。 | tinyint unsigned |
| `zip` | 郵便番号ディメンションの入力に使用されます。 | varchar(50) |

## 空の列

次の列のリストは未使用で、データは含まれていません。

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformancecrashes
* mobileappperformancecrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinapproyalties
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>device-manufacturer
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rank-category-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalties
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstoreratingdivisor
* mobileavgprevsessionlength
* mobilecrashes
* mobilecrashrate
* mobiledailyengagedusers
* mobiledeeplinkid<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageimpressions
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessageviews
* mobilemonthlyengagedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (deprecated)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink（非推奨）
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty（非推奨）
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist（非推奨）
* socialtotalsentiment
* sourceid
* videoauthorized
* videoaverageminuteaudience
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopause
* videopausecount
* videopausetime
* videoplay
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateaverage
* videoqoebitratechange
* videoqoebuffer
* videoqoedropbeforestart
* videoqoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplayed
