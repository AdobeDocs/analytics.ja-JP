---
title: AMP を使用した実装
description: AMP ページへの Adobe Analytics の実装
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 100%

---


# AMP を使用した実装

[AMP](https://amp.dev) は、高速でスムーズな読み込みをおこなう Web ページを簡単に作成する方法を提供するオープンソース HTML フレームワークです。

Adobe Analytics は JavaScript ライブラリを使用してイメージリクエストをコンパイルおよび送信するので、AMP を使用しているページ上のデータをアドビに送信するには、実装で調整が必要です。

## AMP を使用しているページに Adobe Analytics を実装する方法を決定する

アドビは、AMP を使用しているページに Adobe Analytics を実装する 2 つの方法を作成しました。どちらも `<amp-analytics>` HTML タグを使用します。詳しくは、GitHub ampproject の [amp-analytics タグ](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics)を参照してください。

* **`"adobeanalytics"` トラッキングテンプレート**&#x200B;の使用：ページ上で直接 Analytics リクエストを作成します
* **`"analytics_nativeConfig"` トラッキングテンプレート**&#x200B;の使用：通常のサイトにデプロイするのと同じ AppMeasurement コードを含む iframe を使用します

次の表では、これら 2 つの方法を比較しています。

|  | **「adobeanalytics」テンプレート** | **「adobeanalytics_nativeConfig」テンプレート** |
|---|---|---|
| 既存のレポートスイートの訪問者数／訪問数 | 高い水増し | 最小の水増し |
| 別のレポートスイートの使用 | 推奨 | 不要 |
| 新規訪問者とリターン訪問者の比較 | サポートなし | サポート |
| 訪問者 ID サービス | サポートなし | サポート |
| ビデオとリンクのトラッキング | 部分的なサポート | 未サポート |
| 導入の困難さ | やや困難 | 比較的簡単 |
| Adobe Experience Cloud 統合 | サポートなし | 部分的なサポート |

組織内で長所と短所を考慮して、使用する方法を決定します。サンプルコードについては、アドビ GitHub リポジトリーの[ AMP サンプル](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web)を参照してください。

>[!WARNING]
>
> AMP を使用している同じページで、`"adobeanalytics"` テンプレートと `"adobeanalytics_nativeConfig"` テンプレートの両方を使用しないでください。両方を使用すると、ブラウザーコンソールでエラーが発生し、訪問者が二重にカウントされる可能性があります。

## メソッド 1：amp-analytics タグと「adobeanalytics」テンプレートの使用

`"adobeanalytics"` トラッキングテンプレートは、`<amp-analytics>` HTML タグを使用して、トラッキングリクエストを直接作成します。表示されるページやクリック時など、特定のページイベントで発生するヒットリクエストを指定できます。クリックイベントは、セレクターを指定することで、特定のエレメント ID またはクラスに適用するようにカスタマイズできます。amp-analytics タグに `type="adobeanalytics"` を追加することで、テンプレートを読み込むことができます。

次のコード例に、`pageLoad` および `click` が定義された 2 つのトリガーがあります。`pageLoad` トリガーは、ドキュメントが表示され、`vars` セクションで定義された `pageName` 変数が含まれると実行されます。2 番目のトリガー、`click` は、ボタンがクリックされると実行されます。`eVar1` がこのイベント用に設定され、値 `button clicked` を持ちます。

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.adobedc.net",
        "reportSuites": "reportSuiteID",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
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

`click` トリガーでは、セレクターを指定して、特定の DOM エレメント（この場合、任意のボタン）がいつクリックされても、`buttonClick` リクエストが実行され、このヒットをリンクトラッキング呼び出しとして示すように自動的に設定されるようにできます。

さらに、`amp-analytics` は、認識しているデータ値を AMP が提供できるように、多くの変数の置換をサポートします。詳しくは、GitHub の [amp-analytics でサポートされる変数](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)を参照してください。

>[!NOTE]
>
> この方法を使用してアドビに送信されるイメージリクエストには、多くのデフォルトレポート（例えば、ブラウザー、画面サイズ、リファラー）のデータは含まれません。この情報をヒットに含める場合は、これらの情報がイメージリクエストクエリー文字列の一部として含まれていることを確認します。詳しくは、[データ収集クエリーのパラメーター](../validate/query-parameters.md)を参照してください。

アドビは、組み込みの AMP 関数を使用して訪問者を識別し、`adobe_amp_id` Cookie を設定します。この訪問者 ID は、Adobe Analytics によって設定された他の ID（例えば、「`s_vi`」Cookie）と一意です。Adobe Experience Cloud ID サービスは、この実装方法ではサポートされていません。

>[!NOTE]
>
> AMP は、CDN を使用してコンテンツを配信します。訪問者がコンテンツを取得する CDN ごとに異なる個別訪問者をカウントするように構造化されているので、個別訪問者数が水増しされる可能性があります。

AMP が個別訪問者を識別する方法を考慮して、AMP ページに対して別のレポートスイートを使用することをお勧めします。

このソリューションは、既存のプライバシーポリシー制御が優先されるように、`host` プロパティで指定したトラッキングサーバーがメインサイトのトラッキングサーバーと一致している必要があるということです。それ以外の場合は、AMP を使用するページに対して別のプライバシーポリシーを作成します。

## メソッド 2：amp-analytics タグと「adobeanalytics_nativeConfig」テンプレートの使用

`"adobeanalytics_nativeConfig"` タグは、通常の Web ページで使用するのと同じタグ付け手法を使用するので、実装がより簡単です。`amp-analytics` タグに次を追加します。

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.adobedc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

Web サーバーでホストする HTML ページも必要です。

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
      var s_trackingServer = "example.sc.adobedc.net";
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

このアプローチは、`iframeMessage` リクエストパラメーターに追加された特別なクエリー文字列パラメーターを使用して、ユーティリティ Web ページにデータを送信します。これらのクエリー文字列パラメーターは、それらから適切なデータを収集するように `stats.html` ページが設定されている限り、好きなように名前を付けることができます。

また、`"adobeanalytics_nativeConfig"` テンプレートも、amp-analytics タグの `extraUrlParams` セクションにリストされた変数に基づいて、クエリー文字列パラメーターを追加します。上記の例では、`pageName` パラメーターと `v1` パラメーターが含まれます。

>[!IMPORTANT]
>
> `stats.html` ページは、AMP 自体がホストされるドメインとは別のサブドメインでホストされる必要があります。AMP フレームワークは、AMP ページ自体が存在するのと同じサブドメインからの iframes を許可しません。例えば、AMP が `amp.example.com` でホストされている場合は、`stats.html` ページを `ampmetrics.example.com` などの別のサブドメインでホストします。

この方法を使用すると、ユーザーがプライマリサイトのトラッキングをオプトアウトした場合、すべての AMP のトラッキングもオプトアウトされます。また、このユーティリティページを使用すると、AMP は Adobe Experience Cloud ID サービスをサポートできます。別のレポートスイートは必要ありません。

リンクトラッキングとビデオトラッキングは、このメソッドでは使用できません。AMP の `iframeMessage` タグは、ページごとに 1 回しか読み込めないので、フレームの読み込み後に他のイメージリクエストを送信することはできません。この方法を使用するには、実行する処理リソースが増えるので、スクロールのパフォーマンスに影響を及ぼす可能性があります。すべてのリソースが非同期的に読み込まれるので、このメソッドはページ読み込み時間に影響しません。

## FAQ

**ビデオトラッキングはどちらかの方法で利用できますか。**

いいえ。AMP 標準は、「visible」、「click」、「timer」のトリガーのみをサポートします。`amp-analytics` タグがリッスンできるビデオトラッキングの明示的なトリガーは、まだサポートされていません。また、`"adobeanalytics_nativeConfig"` テンプレートは 1 回しか読み込めないので、ページの読み込み後にはイメージリクエストは実行できません。

**AMP 訪問者をデータ内の他の訪問者と区別する方法を教えてください。**

すべての AMP ページに対して、[!UICONTROL JavaScript バージョン]ディメンションは、`AMP vX.X` に類似した値を収集します。また、カスタムディメンションを「AMP」に設定して、これらの訪問者をセグメント化することもできます。

**この実装方法は Facebook インスタント記事と比較してどうですか。**

Facebook インスタント記事は、`"adobeanalytics_nativeConfig"` 方法と同様のソリューションをサポートします。このメソッドの `stats.html` ページは、AMP と FIA の両方に対する分析ニーズに同時に対応できます。FIA でのトラッキングの実装について詳しくは、[Facebook インスタント記事](fb-instant-articles.md)を参照してください。
