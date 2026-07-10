---
title: AMP を使用した実装
description: AMP ページへの Adobe Analytics の実装
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
TQID: https://experienceleague.adobe.com/lEnXPmYFhMOlvL-au9C-MtGiKY5b84ojYska3urtH1M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: e6c28e30-8689-4bf4-8fa8-561343d308a9id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 939
ht-degree: 66%

---

# AMP を使用した実装

[AMP](https://amp.dev) は、高速でスムーズな読み込みをおこなう Web ページを簡単に作成する方法を提供するオープンソース HTML フレームワークです。

Adobe Analytics は JavaScript ライブラリを使用してイメージリクエストをコンパイルおよび送信するので、AMP を使用しているページ上のデータをアドビに送信するには、実装で調整が必要です。

## AMP を使用しているページに Adobe Analytics を実装する方法を決定する

アドビは、AMP を使用しているページに Adobe Analytics を実装する 2 つの方法を作成しました。 どちらも `<amp-analytics>` HTML タグを使用します。 詳しくは、AMPのドキュメントの[amp-analytics](https://amp.dev/ja/documentation/components/amp-analytics)を参照してください。

* **`"adobeanalytics"` テンプレートを使用**: Analytics リクエストをページに直接作成します
* **`"analytics_nativeConfig"` テンプレートを使用**：通常のサイトにデプロイするのと同じAppMeasurement コードを含むiframeを使用します

次の表では、これら 2 つの方法を比較しています。

|   | **`"adobeanalytics"`テンプレート** | **`"adobeanalytics_nativeConfig"`テンプレート** |
|---|---|---|
| 既存のレポートスイートの訪問者数／訪問数 | 高インフレ | 最小限のインフレ |
| 別のレポートスイートの使用 | 推奨 | 不要 |
| 新規訪問者と再訪問者 | サポートなし | サポート |
| 訪問者ID サービス （`VisitorAPI.js`） | サポートなし | サポート |
| ビデオとリンクのトラッキング | 部分的なサポート | まだサポートされていません |
| 導入の困難 | 困難 | 比較的簡単 |
| Adobe CX Enterpriseとの統合 | サポートなし | 部分的なサポート |

自社に最適な導入方法を選択できるように、長所と短所を比較検討しましょう。

>[!WARNING]
>
>AMP を使用している同じページで、`"adobeanalytics"` テンプレートと `"adobeanalytics_nativeConfig"` テンプレートの両方を使用しないでください。 両方を使用すると、ブラウザーコンソールでエラーが発生し、訪問者が二重にカウントされる可能性があります。

## 方法1: `"adobeanalytics"` テンプレートで`<amp-analytics>` タグを使用する

`"adobeanalytics"` トラッキングテンプレートは、`<amp-analytics>` HTML タグを使用して、トラッキングリクエストを直接作成します。 表示されるページやクリック時など、特定のページイベントで発生するヒットリクエストを指定できます。 クリックイベントは、セレクターを指定することで、特定の要素 ID またはクラスに適用するようにカスタマイズできます。 amp-analytics タグに `type="adobeanalytics"` を追加することで、テンプレートを読み込むことができます。

次のコード例に、`pageLoad` および `click` が定義された 2 つのトリガーがあります。 `pageLoad` トリガーは、ドキュメントが表示され、`vars` セクションで定義された `pageName` 変数が含まれると実行されます。 2 番目のトリガー、`click` は、ボタンがクリックされると実行されます。 このイベントには、値`button clicked`を持つ`eVar1`変数が設定されています。

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

`<amp-analytics>` タグは、AMPが認識できるデータ値を提供できるように、変数置換をサポートしています。 詳しくは、「`amp-analytics`](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md) on GitHubでサポートされている[変数」を参照してください。

>[!NOTE]
>
>この方法を使用してAdobeに送信された画像リクエストには、多くのデフォルトレポート（ブラウザー、画面サイズ、リファラーなど）のデータは含まれません。 ヒットにこの情報を含める場合は、画像リクエストクエリ文字列の一部として含まれていることを確認してください。 イメージリクエスト クエリクエリパラメーターと関連する変数の完全なリストについては、[ データ収集クエリパラメーター](../validate/query-parameters.md)を参照してください。

アドビは、ビルトインの AMP 関数を使用して訪問者を識別し、`adobe_amp_id` Cookie を設定します。 この訪問者IDは、Adobe Analyticsが設定した他のIDと一意です。 訪問者がコンテンツを取得するCDNごとに異なるユニーク訪問者がカウントされ、ユニーク訪問者数が増加する可能性があります。 AMPが一意の訪問者を識別する方法のため、AMP ページ用に別のレポートスイートを使用することを強くお勧めします。 Adobe Visitor ID サービスはサポートされていません。

このソリューションは、既存のプライバシーポリシー制御が優先されるように、`host` プロパティで指定したトラッキングサーバーがメインサイトのトラッキングサーバーと一致している必要があるということです。 それ以外の場合は、AMP を使用するページに対して別のプライバシーポリシーを作成します。

## 方法2: `"adobeanalytics_nativeConfig"` テンプレートで`<amp-analytics>` タグを使用する

`"adobeanalytics_nativeConfig"` タグは、通常の Web ページで使用するのと同じタグ付け手法を使用するので、実装がより簡単です。 `amp-analytics` タグに次を追加します。

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

このアプローチは、`iframeMessage` リクエストパラメーターに追加された特別なクエリ文字列パラメーターを使用して、ユーティリティ web ページにデータを送信します。 これらのクエリ文字列パラメーターは、それらから適切なデータを収集するように `stats.html` ページが設定されている限り、好きなように名前を付けることができます。

`"adobeanalytics_nativeConfig"` テンプレートでは、`<amp-analytics>` タグの`extraUrlParams` セクションにリストされている変数に基づいて、クエリ文字列パラメーターも追加されます。 上記の例では、`pageName` パラメーターと `v1` パラメーターが含まれます。

>[!IMPORTANT]
>
>`stats.html` ページは、AMP 自体がホストされるドメインとは別のサブドメインでホストされる必要があります。 AMP フレームワークは、AMP ページ自体が存在するのと同じサブドメインからの iFrames を許可しません。 例えば、AMP が `amp.example.com` でホストされている場合は、`stats.html` ページを `ampmetrics.example.com` などの別のサブドメインでホストします。

この方法を使用すると、ユーザーがプライマリサイトのトラッキングをオプトアウトした場合、すべての AMP のトラッキングもオプトアウトされます。 このユーティリティページを使用すると、AMPがAdobe Visitor ID サービスをサポートできることも意味します。 別のレポートスイートは必要ありません。

リンクトラッキングとビデオトラッキングは、このメソッドでは使用できません。 AMP の `iframeMessage` タグは、ページごとに 1 回しか読み込めないので、フレームの読み込み後に他のイメージリクエストを送信することはできません。 この方法を使用するには、実行する処理リソースが増えるので、スクロールのパフォーマンスに影響を及ぼす可能性があります。 すべてのリソースが非同期的に読み込まれるので、このメソッドはページ読み込み時間に影響しません。

## FAQ

**AMP 訪問者をデータ内の他の訪問者と区別する方法を教えてください。**

すべての AMP ページに対して、[!UICONTROL JavaScript バージョン]ディメンションは、`AMP vX.X` に類似した値を収集します。 カスタムディメンションを「AMP」に設定して、これらの訪問者をセグメント化することもできます。

**この実装方法は Facebook インスタント記事と比較してどうですか。**

Facebook インスタント記事は、`"adobeanalytics_nativeConfig"` 方法と同様のソリューションをサポートします。 このメソッドの `stats.html` ページは、AMP と FIA の両方に対する分析ニーズに同時に対応できます。 FIA でのトラッキングの実装について詳しくは、[Facebook インスタント記事](fb-instant-articles.md)を参照してください。
