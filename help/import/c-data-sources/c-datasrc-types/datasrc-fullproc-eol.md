---
title: フル処理データソースの提供終了
description: Bulk Data Insertion API とフル処理データソースの提供終了と比較の理由。
feature: Data Sources
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 97%

---

# フル処理データソースの提供終了

フル処理データソースでは、数年にわたり、ヒットレベルのデータを Adobe Analytics に送信する機能を提供してきました。このデータは、JavaScript ライブラリおよびモバイルアプリ SDK で収集されたデータと同じ方法で処理されました。2020年、アドビは、フル処理データソースと同じ機能を実行しますが、追加機能も備えた [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) をリリースしました。このトピックでは、Bulk Data Insertion API で提供される追加機能の詳細とファイル形式の違いの概要を説明します。

2021年3月25日（PT）以降、アドビで新しいフル処理データソース接続が作成できなくなりました。2022年1月31日（PT）にサービスが完全に廃止されるまでは、既存の接続がサポートされていました。アドビの標準のドキュメントに加えて、 [Bulk Data Insertion API を使用してデータを送信するために必要な手順](https://adobe.ly/aabdia) について説明しています。

## この機能を提供終了する理由

Bulk Data Insertion API（BDIA）は、追加機能を提供すると同時に、フル処理でサポートされるすべてのユースケースをカバーします。Bulk Data Insertion API を使用すると、より適切にサービスを提供できます。

## フル処理データソースと Bulk Data Insertion API の主な違い

* Bulk Data Insertion では、並行して処理できる複数のファイルを送信できます。訪問者グループを使用すると、訪問者の継続性と eVar アトリビューションを確保できます。
* Bulk Data Insertion には、データ検証機能とエラー処理機能が備わっているので、ヒットデータの送信に関する管理作業の一部が削除されます。
* Bulk Data Insertion は、訪問者 ID に対して複数のオプションをサポートします。Analytics ID と Experience Cloud ID の両方を送信できます（詳しくは、 [ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja) を参照）。 さらに、 [ECID を生成するためのシード](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds) として独自の ID を使用できます。
* Bulk Data Insertion は、リストおよびコンテキストデータ変数をサポートします。
* Bulk Data Insertion は、Activity Map データをサポートしていません。

## ファイル形式とコンテンツの主な違い

* Bulk Data Insertion には、追加の必須フィールドがいくつかあります。詳しくは、 [ドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) を参照してください。
* 訪問者の継続性とアトリビューションを確保するために、Bulk Data Insertion では、ファイル内の行を時系列順に並べ替える必要があります。ファイル全体での訪問者アクティビティの順序については、 [訪問者グループ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) を参照してください。
* Bulk Data Insertion では、.csv ファイルを .gzip 形式で圧縮する必要があります。
* BDIA では、「日付」ではなく「タイムスタンプ」を使用します。

詳しくは、Bulk Data Insertion（BDIA）とフル処理データソース（FPDS）で使用可能なフィールド値の次の比較を参照してください。

## BDIA と FPDS で使用可能なフィールド値の比較

| BDIA の変数 | フル処理列の変数 | 説明 |
| --- | --- | --- |
| aamlh | サポートなし | Adobe Audience Manager の場所のヒント。 |
| browserHeight | browserHeight | ブラウザーの高さ（ピクセル単位）（例：768） |
| browserWidth | browserWidth | ブラウザーの幅（ピクセル単位）（例：1024） |
| キャンペーン | キャンペーン | コンバージョンキャンペーンのトラッキングコード |
| チャネル | チャネル | チャネル文字列（例：「スポーツセクション」） |
| colorDepth | colorDepth | 画面の色（ビット単位）（例：24） |
| connectionType | connectionType | 訪問者の接続タイプ（LAN またはモデム） |
| contextData.key | サポートなし | キーと値のペアを指定するには、ヘッダーに「contextData.product」または「contextData.color」という名前を付けます。 |
| cookiesEnabled | cookiesEnabled | 訪問者がファーストパーティセッション Cookie をサポートしている場合は `Y` または `N` |
| currencyCode | currencyCode | 売上高の通貨コード（例：`USD`） |
| customerID.[customerIDType].authState | サポートなし | 訪問者の認証状態。サポートされる値：0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT、または &#39;&#39;（大文字と小文字を区別しない）2 つの連続する一重引用符（&#39;&#39;）により、クエリー文字列から値が省略されます。ヒットが行われると 0 に変換されます。サポートされる authState の数値は、0 = UNKNOWN、1 = AUTHENTICATED、2 = LOGGED_OUT を表します。customerIDType は任意の英数字の文字列にすることができますが、大文字と小文字を区別する必要があります。 |
| customerID。[customerIDType].id | サポートなし | 使用する顧客 ID。customerIDType は任意の英数字の文字列にすることができますが、大文字と小文字を区別する必要があります。 |
| customerID。[customerIDType].isMCSeed | サポートなし | Experience Cloud 訪問者 ID のシードであるかどうか。サポートされる値：0、1、TRUE、FALSE、&#39;&#39;（大文字と小文字を区別しない）0、FALSE、または 2 つの連続する一重引用符（&#39;&#39;）を使用すると、クエリー文字列から値が省略されます。customerIDType は任意の英数字の文字列にすることができますが、大文字と小文字を区別する必要があります。 |
| eVarN | eVarN。例：`<eVar2>`...`<eVar>` | コンバージョン eVar 名。最大 75 個の eVar（eVar1 ～ eVar75）を使用できます。eVar 名（eVar12 など）や、わかりやすい名前（Ad Campaign 3 など）を指定できます。 |
| events | イベント | [イベント文字列](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html#vars)。書式設定には s.events 変数と同じ構文を使用しています。例：scAdd、event1、event7 |
| hierN | hierN。例：`<hier2>`...`</hier2>` | 階層名。最大 5 つの階層を使用できます（ hier1 ～ hier5）。デフォルトの階層名「`hier2`」や、わかりやすい名前（「Yankees」）を指定できます。 |
| homePage | homePage | 現在のページが訪問者のホームページであるかどうか（Y または N）。 |
| ipaddress | サポートなし | 訪問者の IP アドレス。 |
| javaEnabled | javaEnabled | 訪問者側で Java が有効かどうか（Y または N）。 |
| javaScriptVersion | javaScriptVersion | JavaScript のバージョン（例：1.3）。 |
| 言語 | サポートなし | ブラウザーでサポートされる言語。例：`en-us`。 |
| linkName | linkName | リンク名。 |
| linkType | linkType | リンクのタイプ。サポートされる値： `d: Download link`、`e: Exit link`、`o: Custom link` |
| linkURL | linkURL | リンクの HREF（リンク先 URL）。 |
| listn。例：list2。 | サポートなし | 変数に渡され、レポートの個別行項目としてレポートされる値の区切りリスト |
| marketingCloudVisitorID | サポートなし | Experience Cloud ID。詳しくは、 [訪問者の識別](https://experienceleague.adobe.com/docs/id-service/using/home.html#id-service-api) と Experience Cloud 訪問者 ID サービスを参照してください。 |
| サポートなし | charSet | web サイトでサポートされる文字セット。UTF-8、ISO-8859-1 などがあります。 |
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
| pageURL | pageURL | ページ URL（例：https://www.example.com/index.html）。 |
| plugins | plugins | ブラウザーのプラグイン名をセミコロンで区切ったリスト。 |
| 製品 | 製品 | ページ上のすべての製品のリスト。各製品をコンマで区切ります。例：Sports;Ball;1;5.95,Toys; Top;1:1.99 |
| prop1 ～ prop75 | propN。例：`<prop2>`...`</prop2>` | プロパティ番号の文字列（例：「スポーツセクション」）。 |
| propN | propN | プロパティのプロパティ値。 |
| purchaseID | purchaseID | 購入 ID 番号。 |
| リファラー | リファラー | ページリファラーの URL。 |
| reportSuiteID | s_account | データを送信するレポートスイートを指定します。レポートスイート ID が複数ある場合はコンマで区切る必要があります。 |
| resolution | resolution | 画面の解像度（例：1024x768）。 |
| サーバー | サーバー | サーバー文字列。 |
| 都道府県 | 都道府県 | コンバージョンの州の文字列。 |
| タイムスタンプ | 日付 | YYYY-MM-DDThh:mm:ss±UTC_offset という ISO 8601 日付形式（例：2021-09-01T12:00:00-07:00）、または Unix 時刻形式（1970年1月1日からの経過秒数）を使用します。 |
| trackingServer | サポートなし | 列ヘッダー経由でのみ指定できます。 |
| transactionID | サポートなし | 複数チャネルのユーザーアクティビティを結び付けてレポートに利用する場合に使用される共通の値。詳しくは、 [データソースユーザーガイド](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html#data-sources) を参照してください。 |
| userAgent | サポートなし | ユーザーエージェント文字列 |
| visitorID | visitorID | 訪問者の Analytics ID。詳しくは、 [訪問者の識別](https://experienceleague.adobe.com/docs/id-service/using/home.html) を参照してください。 |
| 郵便番号 | 郵便番号 | コンバージョンの郵便番号。 |
