---
title: フル処理データソースのサポート終了
description: 一括データ挿入 API とフル処理データソースの提供終了と比較の理由。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 27%

---

# フル処理データソースのサポート終了

数年間、フル処理データソースを使用して、ヒットレベルのデータをAdobe Analyticsに送信できました。 このデータは、JavaScript ライブラリおよびモバイルアプリ SDK で収集されたデータと同じ方法で処理されました。 2020 年、Adobeは [一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)：フル処理データソースと同じ機能を実行しますが、追加の機能も実行します。 このトピックでは、Bulk Data Insertion API で提供される追加機能の詳細とファイル形式の違いの概要を説明します。

2021 年 3 月 25 日以降、Adobeにより、新しいフル処理データソース接続が作成されませんでした。 このサービスが 2022 年 1 月 31 日に完全に廃止されるまで、既存の接続がサポートされていました。 アドビの標準ドキュメントに加えて、 [一括データ挿入 API を使用してデータを送信するために必要な手順](https://adobe.ly/aabdia).

## この機能の提供終了の理由を教えてください。

Bulk Data Insertion API(BDIA) は、追加機能を提供すると同時に、フル処理でサポートされるすべてのユースケースをカバーします。 一括データ挿入 API を使用した方が、処理が改善されました。

## フル処理データソースと一括データ挿入 API の主な違い

* 一括データ挿入を使用すると、複数のファイルを送信し、並行して処理できます。 訪問者グループを使用して、訪問者の継続性とeVar属性を確保できます。
* 一括データ挿入には、データ検証とエラー処理機能が備わっているので、ヒットデータの送信に関する管理作業の一部が削除されます。
* 一括データ挿入は、訪問者 ID に対して複数のオプションをサポートします。 Analytics ID とMarketing CloudID の両方を送信できます ( [ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja) を参照 )。 また、独自の ID を [ECID を生成するためのシード](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* 一括データ挿入では、リストおよびコンテキストデータ変数がサポートされます。
* 一括データ挿入は、Activity Mapデータをサポートしていません。

## ファイル形式とコンテンツの主な違い

* 「一括データ挿入」には、追加の必須フィールドがいくつかあります。 詳しくは、 [ドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 」を参照してください。
* 訪問者の継続性とアトリビューションを確保するために、Bulk Data Insertion では、ファイル内の行を時系列順に並べ替える必要があります。 詳しくは、 [訪問者グループ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) を参照して、ファイルをまたいだ訪問者アクティビティの順序を確認してください。
* 一括データ挿入では、ファイルを.gzip 形式で圧縮した.csv ファイルが必要です。
* BDIA では、「date」の代わりに「timestamp」が使用されます。

詳しくは、一括データ挿入 (BDIA) およびフル処理データソース (FPDS) で使用できるフィールド値の次の比較を参照してください。

## BDIA と FPDS で使用可能なフィールド値の比較

| BDIA 変数 | フル処理列の変数 | 説明 |
| --- | --- | --- |
| aamlh | サポートなし | Adobe Audience Managerのロケーションのヒント |
| browserHeight | browserHeight | ピクセル単位のブラウザーの高さ（例：768） |
| browserWidth | browserWidth | ピクセル単位のブラウザーの幅（例：1024） |
| キャンペーン | キャンペーン | コンバージョンキャンペーントラッキングコード |
| チャネル | チャネル | チャネル文字列（例：スポーツセクション） |
| colorDepth | colorDepth | 画面の色（ビット単位）（例：24） |
| connectionType | connectionType | 訪問者の接続タイプ（LAN またはモデム） |
| contextData.key | サポートなし | でキーと値のペアを指定するには、ヘッダーに「contextData.product」または「contextData.color」という名前を付けます。 |
| cookiesEnabled | cookiesEnabled | `Y` または `N` 訪問者がファーストパーティセッション cookie をサポートしているかどうか。 |
| currencyCode | currencyCode | 売上高の通貨コード ( 例： `USD`) |
| customerID。[customerIDType].authState | サポートなし | 訪問者の認証状態。 サポートされる値は、0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT、または&quot;（大文字と小文字を区別しない）です。 2 つ連続する一重引用符 (&quot;) は、クエリ文字列から値を省略します。ヒットがおこなわれると、0 に変換されます。 サポートされる authState の数値は、0 = UNKNOWN、1 = AUTHENTICATED、2 = LOGGED_OUT を表します。 customerIDType は任意の英数字文字列にすることができますが、大文字と小文字を区別する必要があります。 |
| customerID。[customerIDType].id | サポートなし | 使用する顧客 ID。 customerIDType は任意の英数字文字列にすることができますが、大文字と小文字を区別する必要があります。 |
| customerID。[customerIDType].isMCSeed | サポートなし | Marketing Cloud訪問者 ID のシードであるかどうか。 サポートされる値は、0、1、TRUE、FALSE、&quot;（大文字と小文字を区別しない）です。 0、FALSE、または 2 つの連続した一重引用符 (&quot;) を使用すると、クエリ文字列から値が省略されます。 customerIDType は任意の英数字文字列にすることができますが、大文字と小文字を区別する必要があります。 |
| eVarN | eVarN（例： ） `<eVar2>`...`<eVar>` | コンバージョン eVar 名。最大 75 個の eVar（ eVar1 -eVar75 )eVar名 (eVar12) またはわかりやすい名前（広告キャンペーン 3）を指定できます。 |
| events | イベント | [イベント文字列](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars)の形式設定は、 s.events 変数と同じ構文を使用しておこないます。 例：scAdd,event1,event7 |
| hierN | hierN、つまり `<hier2>`...`</hier2>` | 階層名。最大 5 つの階層を使用できます（ hier1 ～ hier5 )。 デフォルトの階層名を指定できます `hier2` またはわかりやすい名前 (Yankees)。 |
| homePage | homePage | 現在のページが訪問者のホームページであるかどうか（Y または N）。 |
| ipaddress | サポートなし | 訪問者の IP アドレス。 |
| javaEnabled | javaEnabled | 訪問者側で Java が有効かどうか（Y または N）。 |
| javaScriptVersion | javaScriptVersion | JavaScript のバージョン（例：1.3）。 |
| language | サポートなし | ブラウザーがサポートする言語。 例：`en-us`。 |
| linkName | linkName | リンク名。 |
| linkType | linkType | リンクのタイプ。次の値がサポートされています。 `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | リンクの HREF（リンク先 URL）。 |
| listn 例えば、list2。 | サポートなし | 変数に渡され、レポート用に個々の行項目としてレポートされる値の区切りリスト |
| marketingCloudVisitorID | サポートなし | Marketing Cloud ID. 詳しくは、 [訪問者の識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) とMarketing Cloud訪問者 ID サービス |
| サポートなし | charSet | Web サイトでサポートされる文字セット。 UTF-8、ISO-8859-1 などがあります。 |
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
| pageURL | pageURL | ページ URL です ( 例：https://www.example.com/index.html)。 |
| plugins | plugins | ブラウザープラグイン名をセミコロンで区切ったリスト。 |
| 製品 | 製品 | ページ上のすべての製品のリスト。 製品はコンマで区切ります。 例：スポーツ；ボール；1;5.95，おもちゃ；上；1:1.99. |
| prop1 ～ prop75 | propN( `<prop2>`...`</prop2>` | プロパティ#文字列（例：「スポーツセクション」）。 |
| propN | propN | プロパティのプロパティ値。 |
| purchaseID | purchaseID | 購入 ID 番号。 |
| リファラー | リファラー | ページリファラーの URL。 |
| reportSuiteID | s_account | データを送信するレポートスイートを指定します。複数のレポートスイート ID はコンマで区切る必要があります。 |
| resolution | resolution | 画面の解像度（例：1024x768）。 |
| サーバー | サーバー | サーバー文字列。 |
| 都道府県 | 都道府県 | コンバージョンの州の文字列。 |
| タイムスタンプ | 日付 | YYYY-MM-DDThh という ISO 8601 日付フォーマットを使用します。:mm:ss±UTC_offset ( 例：2021-09-01T12):00:00～07:00 )、または Unix 時間形式（1970 年 1 月 1 日から経過した秒数）。 |
| trackingServer | サポートなし | 列ヘッダーからのみ指定できます。 |
| transactionID | サポートなし | 複数チャネルのユーザーアクティビティを結び付けてレポートに利用する場合に使用される共通の値。詳しくは、 [データソースユーザガイド](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | サポートなし | ユーザーエージェント文字列 |
| visitorID | visitorID | 訪問者の Analytics ID。 詳しくは、 [訪問者の識別](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 郵便番号 | 郵便番号 | コンバージョンの郵便番号。 |
