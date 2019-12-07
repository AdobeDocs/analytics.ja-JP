---
description: Adobe Analytics に Accelerated Mobile Pages（AMP）プロジェクトを導入します。
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
title: Accelerated Mobile Pages
topic: Developer and implementation
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Accelerated Mobile Pages

Adobe Analytics に Accelerated Mobile Pages（AMP）プロジェクトを導入します。

AMP は、すばやくレンダリングされる静的コンテンツの Web ページを構築できる[オープンソースプロジェクト](https://www.ampproject.org/)です。この機能は、モバイル用に最適化されたコンテンツを 1 度作成して、あらゆる場所に即座に読み込ませたい発行者に最適です。このリファレンスには次のトピックが含まれます。

* [仕組み](/help/implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [amp-analytics タグと「adobeanalytics」テンプレートの使用](/help/implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [amp-analytics タグと「adobeanalytics_nativeConfig」テンプレートの使用](/help/implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [概要](/help/implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [よくある質問](/help/implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**追加ドキュメントと例**

* 外部の、オープンソース AMP プロジェクト[ドキュメント](https://www.ampproject.org/docs/get_started/about-amp.html)
* セットアップ[例](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)

## 仕組み {#section_21C2836D63104794BCEBEECB6593AFBF}

AMP には、参加する技術パートナーおよび発行者の別のコンテンツ配信ネットワーク（CDN）上の Web にキャッシュされた、特別にタグ付けされた HTML ページがあります。そうすることで、AMP コンテンツは、可能な限り最も近いソースから可能な限り短い待ち時間で配信されます。この方法では、発行者のコンテンツの読み込み元が 100％確実ということは決してなく、サードパーティ cookie が訪問者の識別で問題になるので、分析は難しくなります。

さらに、ページの重さを劇的に軽減し、ページ読み込み時間を高速化するために、AMP は、JavaScript と cookie の使用を制限します。これは、処理量が減るのでモバイルデバイスにとっては好都合ですが、個別訪問者を正確に計測し、ユーザー獲得および保持率を把握するという課題が生じます。

これらの問題を解決するために、アドビは、発行者がビジネスニーズに最適になるように選択できる 2 つのオプションで AMP パートナーおよび発行者と連携しました。両方のオプションで `amp-analytics` タグを使用します。第 1 のアプローチは、`"adobeanalytics"` トラッキングテンプレートを使用して、AMP 内から直接 Analytics レポートを作成します。第 2 のアプローチは、通常のサイトにデプロイする AppMeasurement コードを含む iframe を使用する`"analytics_nativeConfig"` トラッキングテンプレートを使用します。次の表に、各アプローチの長所と短所を示します。

|  | **「adobeanalytics」テンプレート** | **「adobeanalytics_nativeConfig」テンプレート** |
|---|---|---|
| （既存のレポートスイートの）訪問者数／訪問数 | 高い水増し | 最小の水増し |
| 別のレポートスイートの使用 | 推奨 | 不要 |
| 新規訪問者とリターン訪問者の比較 | サポートなし | 対応 |
| 訪問者 ID サービス | サポートなし | 対応 |
| ビデオとリンクのトラッキング | 部分的なサポート | 未サポート |
| 導入の困難さ | やや困難 | 比較的簡単 |
| [!DNL Experience Cloud] 統合 | サポートなし | サポート（注意が必要） |

## amp-analytics タグと「adobeanalytics」テンプレートの使用 {#section_2E4EBF4EF623440D95DE98E78C47244E}

`"adobeanalytics"` トラッキングテンプレートは、`amp-analytics` タグを使用して、トラッキングリクエストを直接作成します。`"adobeanalytics"` タグでの`amp-analytics` テンプレートの使用により、ページが表示される、またはクリック時（および将来、ビデオが表示されるなど）のような、特定のページイベントで実行するヒットリクエストを指定できます。クリックイベントは、セレクターを指定することで、特定のエレメント ID またはクラスに適用するようにカスタマイズできます。アドビでは、[!DNL Adobe Analytics] 用に特別に設計された `"adobeanalytics"` テンプレートを使用して、簡単にセットアップできるようにしました。amp-analytics タグに `type="adobeanalytics"` を追加することで、テンプレートを読み込むことができます。

次のコード例に、`pageLoad` および `click` が定義された 2 つのトリガーがあります。`pageLoad` トリガーは、ドキュメントが表示されたら実行され、`pageName` で定義されたように `vars section` 変数を含めます。2 番目のトリガー、`click` は、ボタンがクリックされると実行されます。`eVar 1` がこのイベント用に設定され、値 `button clicked` を持ちます。

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
      }, 
      "click": { 
        "on": "click", 
        "selector": "button", 
        "request": "myClick", 
        "vars": { 
          "eVar1": "button clicked" 
        } 
      } 
    } 
  } 
  </script> 
  </amp-analytics> 
```

`click` トリガーでは、セレクターを指定して、特定の DOM エレメント（この場合、任意のボタン）がいつクリックされても、`buttonClick` リクエストが実行され、このヒットを非ステージイベント（つまり、`trackLink` 呼び出し）として示すように自動的に設定されるようにできます。

さらに、`amp-analytics` は、認識しているデータ値を AMP が提供できるように、多くの変数の置換をサポートします。[amp-analytics 変数ドキュメント](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)では、これらのすべておよびその他について学習できます。

任意のテクノロジーまたは DOM 変数（ブラウザー、画面サイズ、デバイス、リファラー、その他）を組み込みたい場合、自動的には生成されないので、リクエストに明示的に追加する必要があることに注意してください。トラッキングに使用される、利用可能な各クエリ文字列パラメーターのドキュメントは、[こちら](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html)を参照してください。

amp-analytics によって作成されたヒットを調査すると、アドビが各リクエストに `vid` クエリパラメーターを含めていることがわかります。組み込み AMP 関数に基づいて `vid` を設定し、`adobe_amp_id` という名前のカスタム Analytics cookie ID を設定します。この ID は、どこかで [!DNL Adobe Analytics] によって設定される他の ID（例：`s_vi cookie`）とは独立しており、ヒットが送信されるレポートスイートに新しい訪問者を作成します。

注意が必要な点がいくつかあります。amp-analytics タグを前述のように使用する場合、訪問者は通常のトラッキングとは独立しており、AMP は任意のコンテンツ配信ネットワークから読み込めるので、訪問者がこの AMP を表示した各 CDN の個別訪問者を取得します（そのため、前述のとおり、訪問者が水増しされます）。このため、アドビでは、`"adobeanalytics"` に`amp-analytics` テンプレートを使用する場合、AMP 専用の個別のレポートスイートにデータを配置することをお勧めします。また、[!DNL Experience Cloud] ID サービス（以前の *`visitor ID service`*）は、この方法の使用をサポートしていません。そのため、お客様のビジネスで追加の [!DNL Experience Cloud] 統合が必要な場合、または将来必要になる場合はおそらく、これは選択肢とはなりません。

最後に、そしておそらく最も重要なことは、この `amp-analytics` ソリューションは、既存のプライバシーポリシー制御が優先されるように、`vars` セクションで指定したトラッキングサーバーがメインサイトのトラッキングサーバーと一致している必要があるということです。そうでない場合、AMP 用に個別のプライバシーポリシーを作成する必要があります。

## amp-analytics タグと「adobeanalytics_nativeConfig」テンプレートの使用 {#section_3556B68304A4492991F439885727E9FF}

`"adobeanalytics_nativeConfig"` タグは、通常の Web ページで使用するのと同じタグ付け手法を使用するので、導入がより簡単です。これを遂行するには、`amp-analytics` タグに次を追加します。

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

このアプローチは、`iframeMessage` リクエストパラメーターに追加された特別なクエリ文字列パラメーターを使用して、ユーティリティ Web ページにデータを送信します。ここでは、`ampdocUrl AMP` 変数と `documentReferrer` をクエリ文字列パラメーター `pageURL` に追加し、それぞれ上の `iframeMessage` リクエストを参照しています。これらの追加のクエリ文字列パラメーターは、それらから適切なデータを収集するように [!DNL stats.html] ページ（下記を参照）が設定されている限り、好きなように名前を付けることができます。

また、`"adobeanalytics_nativeConfig"` テンプレートも、amp-analytics タグの `extraUrlParams` セクションにリストされた変数に基づいて、クエリ文字列パラメーターを追加します。この場合、`pageName` ページで使用される `v1` および [!DNL stats.html] パラメーターを指定していることを確認できます。

一度に 1 つの `amp-analytics` テンプレートのみを使用できることと、同じ AMP にある`"adobeanalytics"` テンプレートおよび`"adobeanalytics_nativeConfig"` テンプレートを使用できないことに注意してください。そのような場合、ブラウザーコンソールにエラーが表示され、訪問者数が誤って水増しされます。

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam("ref"); 
s.t(); 
</script> 
</body> 
</html> 
```

前述のとおり、既存の [!DNL VisitorAPI.js] および [!DNL AppMeasurement.js]（例を参照）を使用したりリンクしたりすることができます。または、既存の実装が何を使用していても、正しい設定パラメーターを追加できます。正しい値を正しい変数に取得するには、提供された `s.Util.getQueryParam` 関数を使用して、通常のページでおこなうように、`iframeMessage` URL から渡した値を取得して、適切な変数を設定できます。If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. この場合、`s.pageName` は、クエリ文字列パラメーター `pageName` で渡した値に設定します。ここで、ページ名は「*`Adobe Analytics Example 2`*」に設定する必要があります。

>[!IMPORTANT]
>
>AMP フレームワークでの iframes の制限により、[!DNL stats.html] ページは、AMP 自体がホストされているドメインとは別のサブドメインでホストされる必要があります。AMP フレームワークは、AMP ページ自体が存在するのと同じサブドメインからの iframes を許可しません。例えば、AMP が [!DNL amp.example.com] でホストされる場合、[!DNL stats.html] ページを [!DNL ampmetrics.example.com] などの別のサブドメインでホストするようにします。

ユーティリティページは元のサイトでホストされるので、すべての AMP にわたる既存のプライバシーポリシーをサポートするために、追加の作業は不要です。これは、エンドユーザーがプライマリサイトのトラッキングをオプトアウトする場合、追加の手順を必要としないで、すべての AMP のトラッキングもオプトアウトされることを意味します。また、このユーティリティページの使用は、AMP で取得した測定をその他の [!DNL Experience Cloud] と（例えば [!DNL Experience Cloud] を使用したターゲット化した広告のために）統合できるように、AMP がアドビの [!DNL Adobe Audience Manager] ID サービスをサポートできることを意味します。

繰り返しますが、組織がまだ [!DNL Experience Cloud] ID サービスを使用していない（または、アドビの [!DNL Dynamic Tag Manager] のようなタグ管理ソフトウェアを持っている）場合、必要に応じて [!DNL stats.html] ページにタグ付けできます。基準点として、既存の実装を使用します。標準の実装との唯一の違いは、設定したい各変数について、適用できるデータポイントを amp-analytics `iframeMessage` URLから（または [!DNL document.URL] を [!DNL stats.html] ページ内から）取得するということです。また、（前述のように）AMP リファラーや AMP ページ URL のような、任意の [AMP 用変数](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)を使用したい場合、前述の例に示したように、iframeMessage オブジェクトに含めてください。

このソリューションは柔軟なので、注意点があります。`amp-analytics``iframeMessage` に特有の制限により、ページ読み込み時に 1 回だけ読み込まれます。これは、`"adobeanalytics_nativeConfig"` テンプレートを使用してリンクトラッキングやビデオトラッキングをおこなえないということを意味します。さらに、[!DNL AppMeasurement]（検索エンジンキーワードレポート、リファラー、およびリファラータイプレポートに影響する、またはマーケティングキャンペーントラッキングコードに含まれる）など、通常、`referrer` コードによって自動的に取得される一部の DOM 値は、AMP 変数で`iframeMessage`利用可能[な任意の手段を使用して、](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) に手動で渡す必要があります。このため、アドビでは、AMP データを既存のレポートスイートに配置している場合、前述のレポートを表示する際に AMP トラフィックをセグメントで除外できるように、カスタム変数を値 AMP で設定することをお勧めします。とはいえ、標準的な技術のレポート（ブラウザー、デバイス、画面サイズまたは解像度など）は、自動的に機能します。

最後に、iframe は個別のページとして読み込み、そのページの JavaScript を完全に実行するので、AMP は、AMP 標準が意図したよりも重くなります。ただし、これはページ読み込み時間には影響しません（iframe はページの読み込み終了後に読み込まれます）が、CPU およびネットワークは、使用しない場合に比べてわずかに影響を受け、スクロールのスムーズさに影響します。実際のところ、大きな影響は確認していませんが、このアプローチのユーザーエクスペリエンスに与える影響を最小化するために、Google と提携しています。

## 概要{#section_4D8ED26084F249738A5C2BC66B933A07}

クリックトラッキングが必要で、訪問者がサイトとは区別されたまったく新しい訪問者としてカウントされることを気にしない場合は、`"adobeanalytics"` トラッキングテンプレートを、データを *`separate report suite`* に配置することをお勧めします。[!DNL Experience Cloud] ID サービスが必要で、訪問者または訪問の水増しを望まず、ページ読み込み時にのみ Analytics を実行するので問題ない場合は、`"adobeanalytics_nativeConfig"` ソリューションの使用をお勧めします。

Adobe Analytics は、Google および発行者と提携して、モバイル Web の発行者に業界最先端の分析機能を提供し、超高速ユーザーエクスペリエンスを実現します。これら 2 つのソリューションは、現在、トレードオフの関係ですが、アドビは、長期的な最高のソリューションを構築し、お客様が抱える分析ニーズの発展に応えることに取り組んでいきます。

AMP プロジェクトは、動きが速く頻繁に変更されるので、[こちら](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)で例の更新を頻繁に確認してください。こちらで示す例は、開始するのに十分なものですが、統合をさらに向上させ、時間と共により多くの発行者が AMP を採用するので、変更されることが予期されます。

質問や問題がある場合は、アドビコンサルタントまたはアドビカスタマーケアにお問い合わせください。

## よくある質問 {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> 残念ですが、まだできません。AMP 標準は、「visible」、「click」、「timer」のトリガーのみをサポートし、amp-analytics タグでリッスンできるビデオトラッキングの明示的なトリガーをまだサポートしていません。Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>比較すると、<code> adobeanalytics_nativeConfig </code>「」テンプレートの方が訪問者の水増しが少ないということですが、これはどういう意味ですか。What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> "adobeanalytics_nativeConfig" </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> "adobeanalytics" </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> "adobeanalytics_nativeConfig" </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. つまり、以前に投稿者のサイトを訪問したことのないSafariからの訪問者は、Adobe Analyticsレポートで水増しされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMP に個別のレポートスイートを使用すべきですか。 </p> </td> 
   <td colname="col2"> <p>訪問者／訪問の水増しの問題により、アドビでは、adobeanalytics テンプレートを使用する場合、AMP 用の個別のレポートスイートを使用することをお勧めします。ただし、必要に応じて、組み合わせたレポートスイートからのトラフィックをセグメント化できるように、amp-analytics タグテンプレートから JavaScript バージョンを「AMP vX.X」に設定することもお勧めしています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="keyword">Experience Cloud</span> ID サービスとは何ですか。必要ですか。 </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"  >ID サービス</a>（以前の<span class="term">訪問者 ID サービス</span>）を使用すると、<span class="keyword">Experience Cloud </span> コアサービスが有効になり、別の Adobe <span class="keyword"> Experience Cloud </span> ソリューションと統合できるようになります。<span class="keyword">Adobe Audience Manager</span> または <span class="keyword">Adobe Target</span> と統合している場合、おそらくこのサービスを使用しています。また、このサービスは、今後提供される多くの <span class="keyword">Adobe Analytics</span> 機能の基盤でもあります。ID サービスのサポートが必要な場合、または将来必要になる場合、<code> iframeMessage </code> ソリューションを使用することをお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>AMP 標準は、iframes がAMP 自体のドメインおよびサブドメインから読み込むことを許可していません。そのため、特に会社が AMP のキャッシュを計画している独自の CDN を持っている場合、ユーティリティページをメインサイトとは別のサブドメインでホストすることをお勧めします。互換性を最大化するために、実際の AMP コンテンツが存在するのとは別の <span class="filepath">ampmetrics.publisher.com</span> のようなサブドメインを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>これは <span class="keyword">Facebook インスタント記事</span>と同じではありませんか。<span class="keyword">Adobe Analytics</span> を Facebook インスタント記事と共にセットアップするにはどうしたらよいですか。 </p> </td> 
   <td colname="col2"> <p> Facebook インスタント記事は、前述の nativeConfig ソリューションと同様のソリューションをサポートします。実際、前に作成した stats.html ページは、AMP と FIA の分析ニーズに同時に応えることができます。FIA でのトラッキングの導入について詳しくは、<a href="/help/implement/js-implementation/analytics-facebook-instant-articles.md"  > Facebook インスタント記事 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

