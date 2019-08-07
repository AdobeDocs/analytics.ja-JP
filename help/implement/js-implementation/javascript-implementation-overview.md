---
description: Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。
keywords: Analyticsの導入;javascript;javascript実装;appMeasurement;ダウンロード測定、IDサービス;visitorapi. js;キャッシング;AppMeasurement圧縮
seo-description: Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。
seo-title: JavaScript導入の概要
solution: Analytics
title: JavaScript導入の概要
topic: 開発者と導入
uuid: bb661d8c- faf9-4454- ac3c-0c1a4c0a9336
translation-type: tm+mt
source-git-commit: 883eb12c6c0f9b566dd485227d19cee16d9cfadc

---


# JavaScript導入の概要

Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。

The easiest and recommended way to send data to [!DNL Analytics] is by using [Launch](/help/implement/implement-with-launch/create-analytics-property.md). 場合によっては、従来の JavaScript による導入方法を使用して Analytics を導入することが必要な場合もあります。

>[!NOTE]
>
>ここでは、Analyticsの導入方法について説明します。All Analytics customers have access to [Launch](/help/implement/implement-with-launch/create-analytics-property.md), which is the standard method to deploy Experience Cloud tags.

## 実装手順 {#section_73961BAD5BB4430A95E073DE5C026277}

データを収集するコードをページに適切に導入するには、新しいファイルを Web サイトにアップロードするためにホストサーバーにアクセスできることが必要です。また、コードを導入するための既存のサイトがあると便利です。

以下の手順で、Analytics の基本的な導入方法を説明します。

| タスク | 説明 |
|--- |--- |
| 1. JavaScript版AppMeasurementとIDサービスをダウンロードします。 | Experience Cloudを使用してAnalyticsにログインします。ダウンロードファイルは、Analytics/管理者/コードマネージャーから利用できます。ダウンロードするこの zip ファイルには、いくつかのファイルが含まれています。AppMeasurement.js および VisitorAPI.js は、Analytics の導入時に使用するファイルです。 |
| 2. IDサービスを設定します。（以前の訪問者IDサービス） | "Analytics用IDサービスの [設定」を参照してください](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 更新 `AppMeasurement.js`. | [サンプルのAppMeasurement. jsコード](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) をコピーして `AppMeasurement.js` 、ファイルの先頭に貼り付けます。以下の変数は必ず更新してください。<ul><li>s.account="INSERT-RSID-HERE" var s=s_gi(s_account)</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>これらの値について不明な点がある場合は、trackingServer変数とtrackingServerSecure変数に [適切に入力](https://helpx.adobe.com/analytics/kb/determining-data-center.html) するか、ClientCareにお問い合わせください。正しく設定されていないと、実装によってデータが収集されません。</br> |
| 3. ホスト `AppMeasurement.js` および`VisitorAPI.js` | この 2 つのコア JavaScript ファイルは、サイトのすべてのページから参照可能な Web サーバーでホストする必要があります。次の手順で、このファイルへのパス情報が必要になります。 |
| 4. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Include the Visitor ID Service by adding the following line of code in the `head` or `body` tag on each page. `VisitorAPI.js``AppMeasurement.js`を含める必要があります。`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page: `script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</li></ul> |
| 5. ページコードを更新して導入します。 | [サンプルページコード](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) をコピーして、追跡する各ページの開始 `body` タグの直後に貼り付けます。以下の変数は必ず更新してください。<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s. pageName="INSERT- NAME- HERE"（例: s. pageName= document. title）</li></ul> |
| 6. Experience Cloudデバッガーを使用して、データが送信されていることを確認します。 | [Experience Cloudデバッガー](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2)をインストールします。インストールしたら、ページコードを導入したページを読み込み、デバッガーを開きます。デバッガーに、送信された収集データの詳細情報が表示されます。 |

## キャッシュ {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは1 回のセッションで 2 回以上ダウンロードされることはありません。このファイルがサイトの各ページで使用されている場合でも、ページごとにダウンロードされることはありません。ほとんどの Web サイトでは、ユーザーは通常 1 回のセッションで複数のページを表示するので、何度も使用される JavaScript コードをこのファイルに記述しておくと、全体でダウンロードされるデータ量を削減できます。

## AppMeasurement 用 JavaScript の圧縮 {#section_C10BBC84C81C414088F97363D29E021B}

コアファイルのページの重さ（サイズ）が問題となっている場合（JavaScript 版 AppMeasurement 1.0 は事前に圧縮されています）、GZIP を使用してファイルを圧縮することを推奨します。GZIP はすべての主要なブラウザーでサポートされており、JavaScript の圧縮よりも高いパフォーマンスで、コア [!DNL s_code.js] JavaScript ファイルの圧縮と解凍が行われます。

次のリンクでは、サイトで GZIP の機能を使用して [!DNL s_code.js] JavaScript コードを圧縮する方法について説明しています。

[Apache モジュール mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Tomcat および Flex による gzip 圧縮の有効化](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
