---
title: フル処理データソースのサポート終了
description: 一括データ挿入APIとフル処理データソースの提供終了と比較の理由。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: f120c189228892e57e38e4d0e106eb3190326ff1
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 27%

---

# フル処理データソースのサポート終了

数年の間、フル処理データソースを使用することで、ヒットレベルのデータをAdobe Analyticsに送信できました。 このデータは、アドビのJavaScriptライブラリおよびモバイルアプリSDKで収集されたデータと同じ方法で処理されました。 2020年に、Adobeは、フル処理データソースと同じ機能を実行する[Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)をリリースしましたが、追加機能も追加されました。 このトピックでは、Bulk Data Insertion APIが提供する追加機能の詳細とファイル形式の違いの概要を説明します。

2021年3月26日以降、Adobeにより、新しいフル処理データソース接続の作成が禁止されます。 サービスが2021年7月31日に完全に廃止されるまで、既存の接続は引き続きサポートされます。 アドビの標準的なドキュメントに加え、Bulk Data Insertion API](http://adobe.ly/aabdia)を使用してデータを送信するために必要な[手順のウォークスルーを提供しています。

## この機能の提供終了の理由を教えてください。

Bulk Data Insertion API(BDIA)は、フル処理でサポートされるすべての使用例をカバーしながら、追加機能を提供します。 一括データ挿入APIを使用する方が、より良い機能が提供されると考えています。

## フル処理データソースと一括データ挿入APIの主な違い

* 一括データ挿入を使用すると、複数のファイルを送信し、同時に処理できます。 訪問者グループを使用して、訪問者の連続性とeVarアトリビューションを確保できます。
* 一括データ挿入には、データ検証機能とエラー処理機能が備わっているので、ヒットデータを送信する際の管理作業の一部が削除されます。
* 一括データ挿入は、訪問者IDに対して複数のオプションをサポートします。 Analytics IDとMarketing CloudIDの両方を送信できます（詳しくは、[IDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を参照してください）。 また、独自のIDを[シードとして使用し、ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)を生成することもできます。
* 一括データ挿入では、リストおよびコンテキストデータ変数がサポートされます。
* 一括データ挿入は、Activity Mapデータをサポートしません。

## ファイル形式とコンテンツの主な違い

* 「一括データ挿入」には、追加の必須フィールドがいくつかあります。 詳しくは、[ドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)を参照してください。
* 訪問者の継続性とアトリビューションを確保するために、Bulk Data Insertionでは、ファイル内の行を時系列順に並べ替える必要があります。 複数のファイルにわたる訪問者アクティビティの順序については、[訪問者グループ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)を参照してください。
* 一括データ挿入では、ファイルを.csv形式で圧縮する必要があります。
* BDIAは、「date」の代わりに「timestamp」を使用します。

詳しくは、次のBulk Data Insertion(BDIA)とFull Processing Data Sources(FPDS)で使用できるフィールド値の比較を参照してください。

## BDIAとFPDSで使用可能なフィールド値の比較

| BDIA変数 | フル処理列の変数 | 説明 |
| --- | --- | --- |
| aamlh | サポートなし | Adobe Audience Managerの場所のヒント |
| browserHeight | browserHeight | ブラウザーの高さ（ピクセル単位、例：768） |
| browserWidth | browserWidth | ピクセル単位のブラウザーの幅（例：1024） |
| キャンペーン | キャンペーン | コンバージョンキャンペーントラッキングコード |
| チャネル | チャネル | チャネル文字列（例：スポーツセクション） |
| colorDepth | colorDepth | ビット単位の画面の色（例：24） |
| connectionType | connectionType | 訪問者の接続タイプ（LANまたはモデム） |
| contextData.key | サポートなし | キーと値のペアは、ヘッダーの名前を「contextData.product」または「contextData.color」にすることで指定します。 |
| cookiesEnabled | cookiesEnabled | `Y` 訪問者が `N` ファーストパーティセッションcookieをサポートしているかどうか。 |
| currencyCode | currencyCode | 売上高通貨コード（例：`USD`） |
| customerID。[customerIDType].authState | サポートなし | 訪問者の認証済み状態。 サポートされる値は、0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT、「」（大文字と小文字を区別しない）のいずれかです。 2つの連続した一重引用符(&quot;)は、クエリ文字列から値を省略します。これは、ヒットがおこなわれると0に変換されます。 サポートされているauthStateの数値は、0 = UNKNOWN、1 = AUTHENTICATED、2 = LOGGED_OUTを表します。 customerIDTypeは任意の英数字文字列で指定できますが、大文字と小文字を区別する必要があります。 |
| customerID。[customerIDType].id | サポートなし | 使用する顧客ID。 customerIDTypeは任意の英数字文字列で指定できますが、大文字と小文字を区別する必要があります。 |
| customerID。[customerIDType].isMCSeed | サポートなし | Marketing Cloud訪問者IDのシードであるかどうか。 サポートされている値は、0、1、TRUE、FALSE、&quot;（大文字と小文字を区別しない）です。 0、FALSE、または2つの連続した一重引用符(&quot;)を使用すると、クエリ文字列から値が省略されます。 customerIDTypeは任意の英数字文字列で指定できますが、大文字と小文字を区別する必要があります。 |
| eVarN | eVarN（例： ）`<eVar2>`...`<eVar>` | コンバージョン eVar 名。最大 75 個の eVar（ eVar1 -eVar75 )eVar名(eVar12)またはわかりやすい名前（広告キャンペーン3）を指定できます。 |
| events | events | [イベント文字列](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars)。形式設定にはs.events変数と同じ構文を使用します。例：scAdd,event1,event7 |
| hierN | hierN、つまり`<hier2>`...`</hier2>` | 階層名。最大 5 つの階層を使用できます（ hier1 ～ hier5 )。 デフォルトの階層名`hier2`や、わかりやすい名前(Yankees)を指定できます。 |
| homePage | homePage | 現在のページが訪問者のホームページであるかどうか（Y または N）。 |
| ipaddress | サポートなし | 訪問者のIPアドレス。 |
| javaEnabled | javaEnabled | 訪問者側で Java が有効かどうか（Y または N）。 |
| javaScriptVersion | javaScriptVersion | JavaScript のバージョン（例：1.3）。 |
| language | サポートなし | ブラウザーでサポートされている言語。 例：`en-us`。 |
| linkName | linkName | リンク名。 |
| linkType | linkType | リンクのタイプ。次の値がサポートされています。`d: Download link`、`e: Exit link`、`o: Custom link`。 |
| linkURL | linkURL | リンクの HREF（リンク先 URL）。 |
| listn例えば、list2。 | サポートなし | 変数に渡され、レポート用に個々の行項目としてレポートされる値の区切りリスト |
| marketingCloudVisitorID | サポートなし | Marketing Cloud ID. [訪問者ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api)とMarketing Cloud訪問者IDサービスを参照してください。 |
| サポートなし | charSet | Webサイトでサポートされる文字セット。 UTF-8、ISO-8859-1 などがあります。 |
| サポートなし | clickAction | Visitor Click Map のオブジェクト識別子（oid） |
| サポートなし | clickActionType | Visitor Click Map のオブジェクト識別子タイプ（oidt） |
| サポートなし | clickContext | Visitor Click Map のページ識別子（pid） |
| サポートなし | clickContextType | Visitor Click Map のページ識別子タイプ（pidt） |
| サポートなし | clickSourceID | Visitor Click Map のソースインデックス（oi） |
| サポートなし | clickTag | Visitor Click Map のオブジェクトタグ名（ot） |
| サポートなし | scXmlVer | マーケティングレポートの XML リクエストのバージョン番号（例：1.0）。 |
| サポートなし | timezone | 訪問者のタイムゾーンの GMT との時差（例：-8）。 |
| pageName | pageName | ページの名前 |
| pageType | pageType | ページのタイプ（例：「エラーページ」）。 |
| pageURL | pageURL | ページURL(例：https://www.example.com/index.html)。 |
| plugins | plugins | ブラウザープラグイン名をセミコロンで区切ったリスト。 |
| 製品 | 製品 | ページ上のすべての製品のリスト。 製品はコンマで区切ります。 例：スポーツ；ボール；1;5.95，玩具；上；1:1.99。 |
| prop1 ～ prop75 | propN(例：`<prop2>`...`</prop2>` | プロパティ#文字列（例：「スポーツセクション」）。 |
| propN | propN | プロパティのプロパティ値。 |
| purchaseID | purchaseID | 購入 ID 番号。 |
| referrer | リファラー | ページリファラーの URL。 |
| reportSuiteID | s_account | データを送信するレポートスイートを指定します。複数のレポートスイートIDはコンマで区切る必要があります。 |
| resolution | resolution | 画面の解像度（例：1024x768）。 |
| サーバー | サーバー | サーバー文字列。 |
| 都道府県 | 都道府県 | コンバージョンの州の文字列。 |
| タイムスタンプ | 日付 | YYYY-MM-DDThh:mm:ss±UTC_offsetというISO 8601の日付フォーマット(例： 2021-09-01T12:00:00-07:00 )またはUnixの時間フォーマット（1970年1月1日から経過した秒数）を使用します。 |
| trackingServer | サポートなし | 列ヘッダー経由でのみ指定できます。 |
| transactionID | サポートなし | 複数チャネルのユーザーアクティビティを結び付けてレポートに利用する場合に使用される共通の値。詳しくは、『[データソースユーザーガイド](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources)』を参照してください。 |
| userAgent | サポートなし | ユーザーエージェント文字列 |
| visitorID | visitorID | 訪問者のAnalytics ID。 [訪問者の識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)を参照してください。 |
| 郵便番号 | 郵便番号 | コンバージョンの郵便番号。 |
