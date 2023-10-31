---
title: AMP を使用した実装
description: AMP ページへの Adobe Analytics の実装
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
source-git-commit: 4c75275f9abbff6b9a5a25be370eabc2801eb7fb
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 73%

---

# AMP を使用した実装

[AMP](https://amp.dev) は、高速でスムーズな読み込みをおこなう Web ページを簡単に作成する方法を提供するオープンソース HTML フレームワークです。

Adobe Analytics は JavaScript ライブラリを使用してイメージリクエストをコンパイルおよび送信するので、AMP を使用しているページ上のデータをアドビに送信するには、実装で調整が必要です。

## AMP を使用しているページに Adobe Analytics を実装する方法を決定する

アドビは、AMP を使用しているページに Adobe Analytics を実装する 2 つの方法を作成しました。どちらも `<amp-analytics>` HTML タグを使用します。詳しくは、 [amp-analytics](https://amp.dev/ja/documentation/components/amp-analytics) （AMP のドキュメント）を参照してください。

* **以下を使用します。 `"adobeanalytics"` テンプレート**：ページ上で直接 Analytics リクエストを作成します
* **以下を使用します。 `"analytics_nativeConfig"` テンプレート**：通常のサイトにデプロイするのと同じAppMeasurementコードを含む iframe を使用します

次の表では、これら 2 つの方法を比較しています。

|   | **`"adobeanalytics"`編集** | **`"adobeanalytics_nativeConfig"`編集** |
|---|---|---|
| 既存のレポートスイートの訪問者数／訪問数 | 高い水増し | 最小の水増し |
| 別のレポートスイートの使用 | 推奨 | 不要 |
| 新規訪問者とリターン訪問者の比較 | サポートなし | サポート |
| 訪問者 ID サービス | サポートなし | サポート |
| ビデオとリンクのトラッキング | 部分的なサポート | 未サポート |
| 導入の困難さ | 難しい | 比較的簡単 |
| Adobe Experience Cloud 統合 | サポートなし | 部分的なサポート |

組織に最適な実装方法を選択できるように、長所と短所を考慮します。

>[!WARNING]
>
> AMP を使用している同じページで、`"adobeanalytics"` テンプレートと `"adobeanalytics_nativeConfig"` テンプレートの両方を使用しないでください。両方を使用すると、ブラウザーコンソールでエラーが発生し、訪問者が二重にカウントされる可能性があります。

## 方法 1：を使用します。 `<amp-analytics>` タグに `"adobeanalytics"` テンプレート

`"adobeanalytics"` トラッキングテンプレートは、`<amp-analytics>` HTML タグを使用して、トラッキングリクエストを直接作成します。表示されるページやクリック時など、特定のページイベントで発生するヒットリクエストを指定できます。クリックイベントは、セレクターを指定することで、特定の要素 ID またはクラスに適用するようにカスタマイズできます。amp-analytics タグに `type="adobeanalytics"` を追加することで、テンプレートを読み込むことができます。

次のコード例に、`pageLoad` および `click` が定義された 2 つのトリガーがあります。`pageLoad` トリガーは、ドキュメントが表示され、`vars` セクションで定義された `pageName` 変数が含まれると実行されます。2 番目のトリガー、`click` は、ボタンがクリックされると実行されます。The `eVar1` 変数がこのイベント用に設定され、値を持ちます。 `button clicked`.

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

The `<amp-analytics>` タグは、認識しているデータ値を AMP が提供できるように、変数の置換をサポートします。 詳しくは、GitHub の [ でサポートされる変数`amp-analytics`を参照してください。](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md)

>[!NOTE]
>
>この方法を使用してAdobeに送信されるイメージリクエストには、多くのデフォルトレポート（例えば、ブラウザー、画面サイズ、リファラー）のデータは含まれません。 この情報をヒットに含める場合は、これらの情報がイメージリクエストクエリ文字列の一部として含まれていることを確認します。 詳しくは、 [データ収集クエリのパラメーター](../validate/query-parameters.md) イメージリクエストのクエリパラメーターとそれに関連する変数の完全なリスト。

アドビは、組み込みの AMP 関数を使用して訪問者を識別し、`adobe_amp_id` Cookie を設定します。この訪問者 ID は、Adobe Analyticsが設定した他の ID と一意です。 訪問者がコンテンツを取得した CDN ごとに異なる個別訪問者がカウントされるので、個別訪問者数が水増しされる可能性があります。 AMP が個別訪問者を識別する方法を考慮して、AMP ページに対して別のレポートスイートを使用することを強くお勧めします。 Adobe Experience Cloud ID サービスはサポートされていません。

このソリューションは、既存のプライバシーポリシー制御が優先されるように、`host` プロパティで指定したトラッキングサーバーがメインサイトのトラッキングサーバーと一致している必要があるということです。それ以外の場合は、AMP を使用するページに対して別のプライバシーポリシーを作成します。

## 方法 2: `<amp-analytics>` タグに `"adobeanalytics_nativeConfig"` テンプレート

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

また、`"adobeanalytics_nativeConfig"` テンプレートも、 タグの `extraUrlParams` セクションにリストされた変数に基づいて、クエリ文字列パラメーターを追加します。`<amp-analytics>`上記の例では、`pageName` パラメーターと `v1` パラメーターが含まれます。

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
