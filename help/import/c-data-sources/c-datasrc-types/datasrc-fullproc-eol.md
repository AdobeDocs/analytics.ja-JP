---
title: フル処理データソースの提供終了
description: 持続終了の理由およびバルクデータ挿入APIとフル処理データソースとの比較。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
translation-type: tm+mt
source-git-commit: 53b15f9c5895e856ff627fbc520d4743fbc57eba
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 27%

---

# フル処理データソースの提供終了

フル処理データソースを使用すると、数年間、ヒットレベルのデータをAdobe Analyticsに送信できます。 このデータは、JavaScriptライブラリやモバイルアプリSDKで収集されたデータと同じ方法で処理されました。 2020年、Adobeは、フル処理データソースと同じ機能を果たす[Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)をリリースしましたが、機能が追加されました。 このトピックでは、Bulk Data Insertion APIが提供する追加機能の詳細と、ファイル形式の相違点について説明します。

2021年3月25日より、Adobeにより、フル処理データソースの新しい接続が作成されなくなります。 既存の接続は、2021年7月31日にサービスが完全に廃止されるまで、引き続きサポートされます。

## この機能の提供終了の理由を教えてください。

Bulk Data Insertion API(BDIA)は、フル処理でサポートされるすべての使用例をカバーすると共に、追加の機能を提供します。 Bulk Data Insertion APIを使用する方が、より適切なサービスが提供されると思います。

## フル処理データソースとバルクデータ挿入APIの主な違い

* Bulk Data Insertionを使用すると、複数のファイルを送信して並行処理できます。 訪問者グループを使用すると、訪問者の継続性とeVarアトリビューションを確保できます。
* Bulk Data Insertionには、エラー処理機能と共にデータ検証機能があるので、ヒットデータの送信に関する管理作業の一部が不要になります。
* Bulk Data Insertionは、訪問者IDの複数のオプションをサポートしています。 Analytics IDとMarketing CloudIDの両方を送信できます（詳しくは、[IDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)を参照）。 また、独自のIDをECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)を生成する[シードとして使用できます。
* Bulk Data Insertionは、リスト変数とコンテキストデータ変数をサポートします。
* Bulk Data InsertionはActivity Mapデータをサポートしていません。

## ファイル形式とコンテンツの主な違い

* バルクデータ挿入には、その他の必須フィールドがいくつかあります。 詳しくは、[ドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)を参照してください。
* 訪問者の継続性とアトリビューションを確保するために、Bulk Data Insertionでは、ファイル内の行を時系列で並べ替える必要があります。 ファイル間での訪問者アクティビティの順序については、[訪問者グループ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)を参照してください。
* Bulk Data Insertionでは、.gzip形式で圧縮されたファイルが.csvである必要があります。
* BDIAでは、「date」の代わりに「timestamp」を使用します。

詳しくは、バルクデータ挿入(BDIA)とフル処理データソース(FPDS)で使用できるフィールド値の次の比較を参照してください。

## BDIAとFPDSで使用できるフィールド値の比較

| BDIA変数 | フル処理列の変数 | 説明 |
| --- | --- | --- |
| aamlh | サポートなし | Adobe Audience Managerの場所のヒント。 |
| browserHeight | browserHeight | ピクセル単位のブラウザーの高さ（例：768） |
| browserWidth | browserWidth | ピクセル単位のブラウザーの幅（例：1024） |
| キャンペーン | キャンペーン | コンバージョンキャンペーントラッキングコード |
| チャネル | チャネル | チャネル文字列（例：スポーツセクション） |
| colorDepth | colorDepth | ビット単位の画面の色（例：24） |
| connectionType | connectionType | 訪問者の接続タイプ（LANまたはモデム） |
| contextData.key | サポートなし | キー値のペアは、ヘッダーに「contextData.product」または「contextData.color」という名前を付けることで指定します |
| cookiesEnabled | cookiesEnabled | `Y` または、訪問者 `N` がファーストパーティセッションcookieをサポートしているかどうか |
| currencyCode | currencyCode | 売上高の通貨コード（例：`USD`） |
| customerID。[customerIDType].authState | サポートなし | 訪問者の認証状態。 サポートされる値は、0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUTまたは&quot;（大文字と小文字を区別しない）です。 2つの連続した一重引用符(&quot;)は、クエリ文字列から値を省略する原因となります。つまり、ヒットが行われるときに0になります。 サポートされるauthStateの数値は、0 = UNKNOWN、1 = AUTHENTICATED、2 = LOGGED_OUTを表します。 customerIDTypeは任意の英数字の文字列にすることができますが、大文字と小文字が区別される必要があります。 |
| customerID。[customerIDType].id | サポートなし | 使用する顧客ID。 customerIDTypeは任意の英数字の文字列にすることができますが、大文字と小文字が区別される必要があります。 |
| customerID。[customerIDType].isMCSeed | サポートなし | これがMarketing Cloud訪問者IDのシードかどうか。 サポートされる値は、0、1、TRUE、FALSE、&quot;（大文字と小文字を区別しない）です。 0、FALSE、または2つの連続した一重引用符(&quot;)を使用すると、値がクエリ文字列から省略されます。 customerIDTypeは任意の英数字の文字列にすることができますが、大文字と小文字が区別される必要があります。 |
| eVarN | eVarN(例：`<eVar2>`...`<eVar>` | コンバージョン eVar 名。最大 75 個の eVar（ eVar1 -eVar75 )eVar名(eVar12)またはわかりやすい名前(広告キャンペーン3)を指定できます。 |
| events | イベント | [イベント文字列](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars)。s.イベント変数と同じ構文を使用して形式設定されます。次に例を示します。scAdd,イベント1,イベント7 |
| hierN | hierN、つまり`<hier2>`...`</hier2>` | 階層名。最大 5 つの階層を使用できます（ hier1 ～ hier5)。 デフォルトの階層名`hier2`またはわかりやすい名前(Yankees)を指定できます。 |
| homePage | homePage | 現在のページが訪問者のホームページであるかどうか（Y または N）。 |
| ipaddress | サポートなし | 訪問者のIPアドレス。 |
| javaEnabled | javaEnabled | 訪問者側で Java が有効かどうか（Y または N）。 |
| javaScriptVersion | javaScriptVersion | JavaScript のバージョン（例：1.3）。 |
| language | サポートなし | ブラウザーでサポートされている言語です。 例：`en-us`。 |
| linkName | linkName | リンク名。 |
| linkType | linkType | リンクのタイプ。次の値がサポートされています。  `d: Download link`、 `e: Exit link` 、  `o: Custom link`. |
| linkURL | linkURL | リンクの HREF（リンク先 URL）。 |
| 例えば、listnは「リスト2」です。 | サポートなし | 変数に渡され、レポートのために個々の行項目としてレポートされる値の区切りリスト |
| marketingCloudVisitorID | サポートなし | Marketing Cloud ID. 「[訪問者ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api)」および「Marketing Cloud訪問者IDサービス」を参照してください。 |
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
| pageType | pageType | ページのタイプ（「エラーページ」など）。 |
| pageURL | pageURL | ページURL(例：https://www.example.com/index.html)。 |
| plugins | plugins | ブラウザープラグイン名をセミコロンで区切ったリスト。 |
| 製品 | 製品 | ページ上のすべての製品のリスト。 製品はコンマで区切ります。 次に例を示します。スポーツ；ボール；1;5.95，玩具；Top;1:1.99. |
| prop1 ～ prop75 | propN(例：`<prop2>`...`</prop2>` | プロパティ番号の文字列（例：「スポーツセクション」）。 |
| propN | propN | プロパティのプロパティ値。 |
| purchaseID | purchaseID | 購入 ID 番号。 |
| リファラー | リファラー | ページリファラーの URL。 |
| reportSuiteID | s_account | データを送信するレポートスイートを指定します。複数のレポートスイートIDはコンマで区切る必要があります。 |
| resolution | resolution | 画面の解像度（例：1024x768）。 |
| サーバー | サーバー | サーバー文字列。 |
| 都道府県 | 都道府県 | コンバージョンの州の文字列。 |
| タイムスタンプ | 日付 | YYYY-MM-DDThh:mm:ss±UTC_offsetのISO 8601日付形式（例：2021-09-01T12:00:00-07:00）またはUnix時間形式（1月1日から経過した秒数）を使用します。、1970)。 |
| trackingServer | サポートなし | 列ヘッダーからのみ指定できます。 |
| transactionID | サポートなし | 複数チャネルのユーザーアクティビティを結び付けてレポートに利用する場合に使用される共通の値。詳しくは、『[データソースユーザーガイド](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources)』を参照してください。 |
| userAgent | サポートなし | ユーザーエージェント文字列 |
| visitorID | visitorID | 訪問者のAnalytics ID。 「[訪問者ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)」を参照してください。 |
| 郵便番号 | 郵便番号 | コンバージョンの郵便番号。 |
