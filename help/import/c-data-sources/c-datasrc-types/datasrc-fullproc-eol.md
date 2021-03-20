---
title: フル処理データソースの提供終了
description: 持続終了の理由およびバルクデータ挿入APIとフル処理データソースとの比較。
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 9%

---


# フル処理データソースの提供終了

フル処理データソースを使用すると、数年間、ヒットレベルのデータをAdobe Analyticsに送信できます。 このデータは、JavaScriptライブラリやモバイルアプリSDKで収集されたデータと同じ方法で処理されました。 2020年、Adobeは、フル処理データソースと同じ機能を果たす[Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)をリリースしましたが、機能が追加されました。 このトピックでは、Bulk Data Insertion APIが提供する追加機能の詳細と、ファイル形式の相違点について説明します。

2021年3月25日より、Adobeにより、フル処理データソースの新しい接続が作成されなくなります。 サービスが完全に非推奨になるまで、既存の接続は引き続きサポートされます。 廃止は2021年に行われますが、具体的な日付はまだ決まっていません。

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

| BDIA、FPDS、両方 | BDIA変数 | フル処理列の変数 | 説明 |
| --- | --- | --- | --- |
| BDIA | aamlh | サポートなし | Adobe Audience Managerの場所のヒント。 以下のAAM地域一覧表で、有効なIDの値を参照してください。 |
| Both | browserHeight | browserHeight | ピクセル単位のブラウザーの高さ（例：768） |
| 両方 | browserWidth | browserWidth | ピクセル単位のブラウザーの幅（例：1024） |
| 両方 | キャンペーン | キャンペーン | コンバージョンキャンペーントラッキングコード |
| 両方 | チャネル | チャネル | チャネル文字列（例：スポーツセクション） |
| 両方 | colorDepth | colorDepth | ビット単位の画面の色（例：24） |
| 両方 | connectionType | connectionType | 訪問者の接続タイプ（LANまたはモデム） |
| BDIA | contextData.key | サポートなし | キー値のペアは、ヘッダーに「contextData.product」または「contextData.color」という名前を付けることで指定します |
| 両方 | cookiesEnabled | cookiesEnabled | `Y` または、訪問者 `N` がファーストパーティセッションcookieをサポートしているかどうか |
| 両方 | currencyCode | currencyCode | 売上高の通貨コード（例：`USD`） |
| BDIA | customerID。[customerIDType].authState | サポートなし | 訪問者の認証状態。 サポートされる値は、0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUTまたは&quot;（大文字と小文字を区別しない）です。 2つの連続した一重引用符(&quot;)は、クエリ文字列から値を省略する原因となります。つまり、ヒットが行われるときに0になります。 サポートされるauthStateの数値は、0 = UNKNOWN、1 = AUTHENTICATED、2 = LOGGED_OUTを表します。 customerIDTypeは任意の英数字の文字列にすることができますが、大文字と小文字が区別される必要があります。 |
| BDIA | customerID。[customerIDType].id | サポートなし | 使用する顧客ID。 customerIDTypeは任意の英数字の文字列にすることができますが、大文字と小文字が区別される必要があります。 |
| BDIA | customerID。[customerIDType].isMCSeed | サポートなし | これがMarketing Cloud訪問者IDのシードかどうか。 サポートされる値は、0、1、TRUE、FALSE、&quot;（大文字と小文字を区別しない）です。 0、FALSE、または2つの連続した一重引用符(&quot;)を使用すると、値がクエリ文字列から省略されます。 customerIDTypeは任意の英数字の文字列にすることができますが、大文字と小文字が区別される必要があります。 |
