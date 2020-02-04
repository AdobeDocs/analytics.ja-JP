---
title: AMPを使用した実装
description: AMPページへのAdobe Analyticsの実装を参照してください。
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# AMPを使用した実装

[AMPは](https://amp.dev) 、高速でスムーズな読み込みを行うWebページを簡単に作成する方法を提供するオープンソースHTMLフレームワークです。

Adobe AnalyticsはJavaScriptライブラリを使用してイメージリクエストをコンパイルおよび送信するので、AMPを使用してページ上のアドビにデータを送信するように、実装で調整が必要です。

## AMPを使用してページにAdobe Analyticsを実装する方法を決定する

アドビは、AMPを使用してページにAdobe Analyticsを実装する2つの方法を作成しました。 どちらも `<amp-analytics>` HTMLタグを使用します。 詳しく [は、GitHubアンププロジェクトの](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) amp-analyticsタグを参照してください。

* **トラッキングテン`"adobeanalytics"`プレートの使用**:ページ上で直接Analyticsリクエストを作成する
* **トラッキングテン`"analytics_nativeConfig"`プレートの使用**:通常のサイトにデプロイするのと同じAppMeasurementコードを含むiframeを使用します

次の表では、これら2つの方法を比較しています。

|  | **「adobeanalytics」テンプレート** | **「adobeanalytics_nativeConfig」テンプレート** |
|---|---|---|
| 既存のレポートスイートでの訪問者数/訪問数 | 高い水増し | 最小の水増し |
| 別のレポートスイートの使用 | 推奨 | 不要 |
| 新規訪問者とリターン訪問者の比較 | サポートなし | サポート |
| 訪問者 ID サービス | サポートなし | サポート |
| ビデオとリンクのトラッキング | 部分的なサポート | 未サポート |
| 導入の困難さ | やや困難 | 比較的簡単 |
| Adobe Experience cloudの統合 | サポートなし | 部分的なサポート |

組織内の長所と短所を考慮して、使用する方法を決定します。 サンプ [ルコードについては](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) 、アドビのGitHubリポジトリのAMPサンプルを参照してください。

> [!WARNING] AMPを使用して同じページで `"adobeanalytics"` とテンプ `"adobeanalytics_nativeConfig"` レートの両方を使用しないでください。 このようにすると、ブラウザーコンソールでエラーが発生し、訪問者が二重にカウントされる可能性があります。

## 方法1:amp-analyticsタグを「adobeanalytics」テンプレートと共に使用します。

The `"adobeanalytics"` tracking template uses the `<amp-analytics>` HTML tag to construct a tracking request directly. 表示されるページやクリック時など、特定のページイベントで発生するヒットリクエストを指定できます。 クリックイベントは、セレクターを指定することで、特定のエレメント ID またはクラスに適用するようにカスタマイズできます。amp-analytics タグに `type="adobeanalytics"` を追加することで、テンプレートを読み込むことができます。

次のコード例に、`pageLoad` および `click` が定義された 2 つのトリガーがあります。トリガ `pageLoad` ーは、ドキュメントが表示され、セクションで定義された変 `pageName` 数が含まれると起動 `vars` します。 The second trigger `click` fires when a button is clicked. `eVar1` が値を持つこのイベントに対して設定されている場合にのみ有効で `button clicked`す。

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
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

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and is automatically set to denote this hit as a link tracking call.

さらに、`amp-analytics` は、認識しているデータ値を AMP が提供できるように、多くの変数の置換をサポートします。詳しく [は、GitHubのamp-analyticsでサポートされる変数](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) を参照してください。

> [!NOTE] この方法を使用してアドビに送信されるイメージリクエストには、多くのデフォルトレポート（例えば、ブラウザー、画面サイズ、リファラー）のデータは含まれません。 この情報をヒットに含める場合は、これらの情報がイメージリクエストクエリ文字列の一部として含まれていることを確認します。 詳しくは、[データ収集クエリのパラメーター](../validate/query-parameters.md)ーを参照してください。

アドビは、組み込みのAMP関数を使用して訪問者を識別し、cookieを設定しま `adobe_amp_id`す。 この訪問者IDは、Adobe Analyticsによって設定された他のID（例えば、cookie）と一意 `s_vi` です。 Adobe Experience Cloud IDサービスは、この実装方法の使用はサポートされていません。

> [!NOTE] AMPは、CDNを使用してコンテンツを配信します。 訪問者がコンテンツを取得するCDNごとに異なる個別訪問者をカウントするように構造化されているので、個別訪問者数が水増しされる可能性があります。

AMPが個別訪問者を識別する方法があるので、AMPページに対して別のレポートスイートを使用することをお勧めします。

This solution requires that the tracking server you specify in the `host` property matches the tracking server on your main site, so that your existing privacy policy controls are respected. それ以外の場合は、AMPを使用するページに対して別のプライバシーポリシーを作成します。

## 方法2:amp-analyticsタグを「adobeanalytics_nativeConfig」テンプレートと共に使用します。

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it uses the same tagging methodology you use on your normal web pages. タグに次を追加し `amp-analytics` ます。

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

WebサーバーでホストするHTMLページも必要です。

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;
      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

This approach sends data to a utility web page through query string parameters added to the `iframeMessage` request parameter. These query string parameters can be named whatever you like, as long as your `stats.html` page is configured to collect data from them.

また、`"adobeanalytics_nativeConfig"` テンプレートも、amp-analytics タグの `extraUrlParams` セクションにリストされた変数に基づいて、クエリー文字列パラメーターを追加します。上記の例では、とのパラメ `pageName` ータ `v1` ーが含まれます。

> [!IMPORTANT] ページ `stats.html` は、AMP自体がホストされるドメインとは別のサブドメインでホストされる必要があります。 AMP フレームワークは、AMP ページ自体が存在するのと同じサブドメインからの iframes を許可しません。例えば、AMPがでホストされている場合は、 `amp.example.com`ページをな `stats.html` どの別のサブドメインでホストします `ampmetrics.example.com`。

この方法を使用すると、ユーザーがプライマリサイトのトラッキングをオプトアウトした場合、すべてのAMPのトラッキングもオプトアウトされます。 また、このユーティリティページを使用すると、AMPがAdobe Experience Cloud IDサービスをサポートできます。 別のレポートスイートは必要ありません。

リンクトラッキングとビデオトラッキングは、このメソッドでは使用できません。 AMPのタ `iframeMessage` グは、ページごとに1回しか読み込めないので、フレームの読み込み後に他のイメージリクエストを送信することはできません。 この方法を使用するには、実行する処理リソースが増えるので、スクロールのパフォーマンスに影響を及ぼす可能性があります。 すべてのリソースが非同期的に読み込まれるので、このメソッドはページ読み込み時間に影響しません。

## FAQ

**ビデオトラッキングはどちらの方法でも利用できますか。**

いいえ。AMP標準は、「visible」、「click」および「timer」のトリガーのみをサポートします。 タグがリッスンできるビデオトラッキングの明示的なトリガーは、ま `amp-analytics` だサポートされていません。 また、テンプレート `"adobeanalytics_nativeConfig"` は1回しか読み込めないので、ページの読み込み後に行われる以降のイメージリクエストはできません。

**AMP訪問者をデータ内の他の訪問者と区別する方法を教えてください。**

すべてのAMPページに対して、 [!UICONTROL JavaScriptのバージョンディメンションは] 、に類似した値を収集しま `AMP vX.X`す。 また、カスタムディメンションを「AMP」に設定して、これらの訪問者をセグメント化することもできます。

**この実装方法はFacebookインスタント記事と比較してどのようですか。**

Facebookインスタント記事は、この方法と同様のソリューションをサポート `"adobeanalytics_nativeConfig"` します。 このメ `stats.html` ソッドのページは、AMPとFIAの両方に対する分析ニーズに同時に対応できます。 FIAでのトラッキングの導入について詳しくは、 [Facebookインスタント記事を参照してください](fb-instant-articles.md)。
