---
description: Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。
keywords: Analytics Implementation;javascript;javascript implementation;appmeasurement;download appmeasurement;Identity Service;visitorapi.js;caching;appmeasurement compression
title: JavaScript 実装の概要
topic: Developer and implementation
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 実装の概要

Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。

[!DNL Analytics] にデータを送信する最も簡単でお勧めの方法は、[Launch](/help/implement/implement-with-launch/create-analytics-property.md) を使用することです。場合によっては、従来の JavaScript による導入方法を使用して Analytics を導入することが必要な場合もあります。

> [!NOTE]この節では、Analytics を導入するレガシーな方法について説明します。Analytics のすべてのお客様が [Launch](/help/implement/implement-with-launch/create-analytics-property.md) を利用することができます。これは、Experience Cloud タグを導入する標準の方法です。

## 実装手順 {#section_73961BAD5BB4430A95E073DE5C026277}

データを収集するコードをページに適切に導入するには、新しいファイルを Web サイトにアップロードするためにホストサーバーにアクセスできることが必要です。また、コードを導入するための既存のサイトがあると便利です。

以下の手順で、Analytics の基本的な導入方法を説明します。

| タスク | 説明 |
|--- |--- |
| 1. JavaScript 版 AppMeasurement と ID サービスをダウンロードします。 | Experience Cloud から Analytics にログインします。ダウンロードファイルは、Analytics／管理者／コードマネージャーで入手できます。ダウンロードするこの zip ファイルには、いくつかのファイルが含まれています。AppMeasurement.js および VisitorAPI.js は、Analytics の導入時に使用するファイルです。 |
| 2. ID サービスを設定します。（以前の訪問者 ID サービス） | See [Set up the Identity Service for Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 3. `AppMeasurement.js` を更新します。 | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. 以下の変数は必ず更新してください。<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>trackingServer変数とtrackingServerSecure [変数の適切な設定を参照するか](https://helpx.adobe.com/analytics/kb/determining-data-center.html) 、これらの値について不明な点がある場合はClientCareにお問い合わせください。 正しく設定されていないと、実装によってデータが収集されません。</br> |
| 4.`AppMeasurement.js` と `VisitorAPI.js` をホスティングします。 | この 2 つのコア JavaScript ファイルは、サイトのすべてのページから参照可能な Web サーバーでホストする必要があります。次の手順で、このファイルへのパス情報が必要になります。 |
| 5. すべてのサイトページで、`AppMeasurement.js` および`VisitorAPI.js` を参照します。 | <ul><li>各ページの `head` または `body` タグ内に次のコードを追加して、訪問者 ID サービスを含めます。（`VisitorAPI.js` は、`AppMeasurement.js` の前に含める必要があります）<br> `script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>各ページの `head` タグまたは `body` タグに次のコードを追加して、JavaScript 版 AppMeasurement を含めます。<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. ページコードを更新し、実装します。 | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. 以下の変数は必ず更新してください。<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s.pageName="INSERT-NAME-HERE" (for example, s.pageName=document.title)</li></ul> |
| 7. Experience Cloud デバッガーを使用して、データが送信されることを確認します。 | [ Experience Cloud デバッガーをインストールします。](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2)インストールしたら、ページコードを導入したページを読み込み、デバッガーを開きます。デバッガーに、送信された収集データの詳細情報が表示されます。 |

## キャッシュ {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは1 回のセッションで 2 回以上ダウンロードされることはありません。このファイルがサイトの各ページで使用されている場合でも、ページごとにダウンロードされることはありません。ほとんどの Web サイトでは、ユーザーは通常 1 回のセッションで複数のページを表示するので、何度も使用される JavaScript コードをこのファイルに記述しておくと、全体でダウンロードされるデータ量を削減できます。

## AppMeasurement 用 JavaScript の圧縮 {#section_C10BBC84C81C414088F97363D29E021B}

コアファイルのページの重さ（サイズ）が問題となっている場合（JavaScript 版 AppMeasurement 1.0 は事前に圧縮されています）、GZIP を使用してファイルを圧縮することを推奨します。GZIP はすべての主要なブラウザーでサポートされており、JavaScript の圧縮よりも高いパフォーマンスで、コア [!DNL s_code.js] JavaScript ファイルを圧縮および解凍します。

次のリンクでは、サイトで GZIP の機能を使用して [!DNL s_code.js] JavaScript コードを圧縮する方法について説明しています。

[Apache モジュール mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Tomcat および Flex による gzip 圧縮の有効化](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
