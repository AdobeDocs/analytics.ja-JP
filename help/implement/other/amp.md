---
title: AMP を使用した実装
description: AMP ページへの Adobe Analytics の実装
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 70%

---

# AMP を使用した実装

[AMP](https://amp.dev) は、高速でスムーズな読み込みをおこなう Web ページを簡単に作成する方法を提供するオープンソース HTML フレームワークです。

Adobe Analytics は JavaScript ライブラリを使用してイメージリクエストをコンパイルおよび送信するので、AMP を使用しているページ上のデータをアドビに送信するには、実装で調整が必要です。

## AMP を使用しているページに Adobe Analytics を実装する方法を決定する

アドビは、AMP を使用しているページに Adobe Analytics を実装する 2 つの方法を作成しました。どちらも `<amp-analytics>` HTML タグを使用します。詳しくは、AMP のドキュメントの [amp-analytics](https://amp.dev/ja/documentation/components/amp-analytics) を参照してください。

* **`"adobeanalytics"` テンプレートの使用**：ページ上で直接 Analytics リクエストを作成します
* **`"analytics_nativeConfig"` テンプレートを使用**：通常のサイトにデプロイするのと同じAppMeasurementコードを含んだ iframe を使用します

次の表では、これら 2 つの方法を比較しています。

|   | テンプレ **`"adobeanalytics"`ト** | テンプレ **`"adobeanalytics_nativeConfig"`ト** |
|---|---|---|
| 既存のレポートスイートの訪問者数／訪問数 | 高い水増し | 最小の水増し |
| 別のレポートスイートの使用 | 推奨 | 不要 |
| 新規訪問者とリターン訪問者の比較 | サポートなし | サポート |
| 訪問者 ID サービス | サポートなし | サポート |
| ビデオとリンクのトラッキング | 部分的なサポート | 未サポート |
| 導入の困難さ | 難しい | 比較的簡単 |
| Adobe Experience Cloud 統合 | サポートなし | 部分的なサポート |

長所と短所を比較検討して、組織に最適な実装方法を選択できるようにします。

>[!WARNING]
>
> AMP を使用している同じページで、`"adobeanalytics"` テンプレートと `"adobeanalytics_nativeConfig"` テンプレートの両方を使用しないでください。両方を使用すると、ブラウザーコンソールでエラーが発生し、訪問者が二重にカウントされる可能性があります。

## 方法 1:`"adobeanalytics"` テンプレートで `<amp-analytics>` タグを使用する

`"adobeanalytics"` トラッキングテンプレートは、`<amp-analytics>` HTML タグを使用して、トラッキングリクエストを直接作成します。表示されるページやクリック時など、特定のページイベントで発生するヒットリクエストを指定できます。クリックイベントは、セレクターを指定することで、特定の要素 ID またはクラスに適用するようにカスタマイズできます。amp-analytics タグに `type="adobeanalytics"` を追加することで、テンプレートを読み込むことができます。

次のコード例に、`pageLoad` および `click` が定義された 2 つのトリガーがあります。`pageLoad` トリガーは、ドキュメントが表示され、`vars` セクションで定義された `pageName` 変数が含まれると実行されます。2 番目のトリガー、`click` は、ボタンがクリックされると実行されます。`eVar1` 変数は、値が `button clicked` のこのイベントに対して設定されます。

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
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

`<amp-analytics>` タグは、AMP が認識しているデータ値を提供できるように、変数の置き換えをサポートしています。 詳しくは、GitHub の `amp-analytics`](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md) でサポートされている [ 変数を参照してください。

>[!NOTE]
>
>この方法を使用してAdobeに送信されるイメージリクエストには、多くのデフォルトレポート（ブラウザー、画面サイズ、リファラーなど）のデータが含まれていません。 この情報をヒットに含める場合は、イメージリクエストクエリ文字列の一部に含めてください。 イメージリクエストクエリパラメーターとそれに関連する変数の完全なリストについては、[ データ収集クエリパラメーター ](../validate/query-parameters.md) を参照してください。

アドビは、組み込みの AMP 関数を使用して訪問者を識別し、`adobe_amp_id` Cookie を設定します。この訪問者 ID は、Adobe Analyticsで設定された他の ID に対して一意です。 訪問者がコンテンツを取得した CDN ごとに異なるユニーク訪問者がカウントされるので、ユニーク訪問者数を増やす可能性があります。 AMP によるユニーク訪問者の識別方法の違いにより、AMP ページには別のレポートスイートを使用することを強くお勧めします。 Adobe Experience Cloud ID サービスはサポートされていません。

このソリューションは、既存のプライバシーポリシー制御が優先されるように、`host` プロパティで指定したトラッキングサーバーがメインサイトのトラッキングサーバーと一致している必要があるということです。それ以外の場合は、AMP を使用するページに対して別のプライバシーポリシーを作成します。

## 方法 2:`"adobeanalytics_nativeConfig"` テンプレートで `<amp-analytics>` タグを使用する

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
        "host": "example.data.adobedc.net"
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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

このアプローチは、`iframeMessage` リクエストパラメーターに追加された特別なクエリ文字列パラメーターを使用して、ユーティリティ web ページにデータを送信します。これらのクエリ文字列パラメーターは、それらから適切なデータを収集するように `stats.html` ページが設定されている限り、好きなように名前を付けることができます。

また、`"adobeanalytics_nativeConfig"` テンプレートは、`<amp-analytics>` タグの `extraUrlParams` セクションにリストされている変数に基づいてクエリ文字列パラメーターを追加します。 上記の例では、`pageName` パラメーターと `v1` パラメーターが含まれます。

>[!IMPORTANT]
>
> `stats.html` ページは、AMP 自体がホストされるドメインとは別のサブドメインでホストされる必要があります。AMP フレームワークは、AMP ページ自体が存在するのと同じサブドメインからの iFrames を許可しません。例えば、AMP が `amp.example.com` でホストされている場合は、`stats.html` ページを `ampmetrics.example.com` などの別のサブドメインでホストします。

この方法を使用すると、ユーザーがプライマリサイトのトラッキングをオプトアウトした場合、すべての AMP のトラッキングもオプトアウトされます。また、このユーティリティページを使用すると、AMP は Adobe Experience Cloud ID サービスをサポートできます。別のレポートスイートは必要ありません。

リンクトラッキングとビデオトラッキングは、このメソッドでは使用できません。AMP の `iframeMessage` タグは、ページごとに 1 回しか読み込めないので、フレームの読み込み後に他のイメージリクエストを送信することはできません。この方法を使用するには、実行する処理リソースが増えるので、スクロールのパフォーマンスに影響を及ぼす可能性があります。すべてのリソースが非同期的に読み込まれるので、このメソッドはページ読み込み時間に影響しません。

## FAQ

**AMP 訪問者をデータ内の他の訪問者と区別する方法を教えてください。**

すべての AMP ページに対して、[!UICONTROL JavaScript バージョン]ディメンションは、`AMP vX.X` に類似した値を収集します。また、カスタムディメンションを「AMP」に設定して、これらの訪問者をセグメント化することもできます。

**この実装方法は Facebook インスタント記事と比較してどうですか。**

Facebook インスタント記事は、`"adobeanalytics_nativeConfig"` 方法と同様のソリューションをサポートします。このメソッドの `stats.html` ページは、AMP と FIA の両方に対する分析ニーズに同時に対応できます。FIA でのトラッキングの実装について詳しくは、[Facebook インスタント記事](fb-instant-articles.md)を参照してください。
