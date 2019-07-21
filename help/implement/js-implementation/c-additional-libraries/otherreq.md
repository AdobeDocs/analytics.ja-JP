---
description: JavaScript を使用せずに Analytics を導入する場合、追加の要件と設定があります。
keywords: Analyticsの導入;大文字と小文字が区別されます。encodeクエリパラメーター;無効な文字;セキュアイメージリクエスト;maximum variable length;参照、url;キャッシング;namespace
seo-description: JavaScript を使用せずに Analytics を導入する場合、追加の要件と設定があります。
seo-title: JavaScriptのガイドラインを使用しない実装
solution: Analytics
title: JavaScriptのガイドラインを使用しない実装
topic: 開発者と導入
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScriptのガイドラインを使用しない実装

JavaScript を使用せずに Analytics を導入する場合、追加の要件と設定があります。

導入の詳細については、サンプルコードを参照してください。以下に、その他の要件と設定について説明します。

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**大文字と小文字の区別**

The parameter names (`pageName`, `purchaseID`, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in [Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md).

**クエリパラメーターのエンコード**

各クエリ文字列パラメーターの値は、URL エンコードする必要があります。URL encoding converts characters that are normally illegal when appearing in a query string, such as a space character, into an encoded character beginning with `%`. For example, a space character is converted into `%20`.

この機能の JavaScript 版は、escape 関数です（デコードは unescape 関数）。Microsoft IIS バージョン 5.0 にも、クエリ文字列のエンコードに関する Escape と Unescape 関数があります。他の Web サーバースクリプト言語でも、エンコード／デコードユーティリティが用意されています。

**変数の最大長**

各変数には、最大の長さがあります。この長さは、 [Analytics 変数](../../../implement/js-implementation/c-variables/sc-variables.md). 変数の最大長を超えると、Analytics で保存や表示をするときに、変数の値が切り詰められることがあります。

**無効な文字**

10 進法表記で 128 以上の文字コードを持つ文字、および 127 以下の非印字文字コードは無効です。HTML の書式（&lt;h1&gt;）や、商標、登録商標および著作権の記号も無効です。

**セキュリティ（&lt; https:/非セキュア（&lt; http:&gt;イメージリクエスト**

https（セキュリティで保護されたプロトコル）を介してアクセスされるページでは、イメージリクエストの URL 部分が、データ収集サーバーの別のセットに対応するように変更されます。

次の情報は、安全で保護されていないイメージリクエストに使用される様々なURLを示しています。

* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. アドビでは複数のデータセンターを使用しており、お客様の組織が割り当てられている正しい URL を導入する必要があります。貴社のアカウントで Admin Console からダウンロードされたコードには、正しいデータセンターが自動的に指定されています。外部ソースから提供されたコードは、場合によっては、正しいデータセンターを指定するように修正する必要があります。
* 複数のレポートスイートを使用する場合は、次のように、URL のドメイン部分ではなく、ディレクトリ部分で示す必要があります。
* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. アドビでは複数のデータセンターを使用しており、お客様の組織が割り当てられている正しい URL を導入する必要があります。

**URL および参照 URL**

The URL and Referring URL may be populated from the server in the `g=` and `r=` variables. Use the Request ServerVariables (`HTTP\_REFERRER`) or Request ServerVariables `(URL) (IIS/ASP)`, or the appropriate variable for your server/scripting technology. The referring URL `( r=)` is extremely important for tracking referring URLs, domains, search engines, and search terms.

pageNameを使用しない場合は、「現在のURL"フィールドに一意の値が入力されていることが前提となります。If neither pageName nor Current URL `(g=)` is populated, the record is invalid and is not processed. 少なくとも、記録を処理するために、URL は必須のフィールドです。

**キャッシュの効果**

HTML および他の Web ページは、訪問者とコンテンツを提供する Web サイトとの間をつなぐブラウザーまたはサーバーによってキャッシュされることがあります。「キャッシュバスティング」手法を使用しない限り、キャッシュによってページビューおよびその他のイベントの正確なカウントが妨げられます。

アドビの標準 JavaScript には、ページおよびイメージのキャッシュがおこなわれないようにするために、イメージリクエストを変更する動的な方法が採用されています。これにより、ページビューの正確なカウントが可能になります。

ただし、サーバーサイドでイメージリクエストを生成する場合は、このようなランダム化はおこなわれません。ページのリロードと（ブラウザーのキャッシュ内またはプロキシサーバー内に）キャッシュされたページは、サーバーサイドのイメージリクエストを使用したときに、カウントされない場合があります。

SSL (`https:`) pages are not, by definition, ever cached so this warning applies only to non-secure (`http:`) pages. Additionally, pages with parameters (`https://www.samplesite.com/page.asp?parameter=1`) or certain file extensions (`.asp`, `.jsp`, etc.) もキャッシュされません。

以下の例でも、最小限の JavaScript ソリューションを示します。このソリューションでは、サーバーサイドのイメージリクエストを主に作成し、ブラウザーでの乱数に基づいて追跡をおこないます。このメソッドは、httpsを介してアクセスされる静的HTMLページで発生するキャッシュを克服します。プロトコルを使用します。

**nameSpace 変数**

nameSpace クエリ文字列パラメーターは、JavaScript を使用しない導入で必要になります。

例：ns=nameSpace

貴社の nameSpace 値を入手するには、アドビコンサルタントまたはアカウントマネージャーにご連絡ください。
