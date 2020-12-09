---
title: Facebook インスタント記事での実装
description: Facebook インスタント記事ページに Adobe Analytics を実装します。
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 100%

---


# Facebook インスタント記事での実装

Facebook インスタント記事を使用すると、Facebook 上で高速でインタラクティブな記事を作成できます。インスタント記事は、モバイル Web よりも最大 10 倍高速にコンテンツを読み込めます。

Adobe Analytics を Facebook インスタント記事に埋め込んで、訪問者の行動を追跡できます。発行者のコンテンツは Facebook アプリ内にあり、発行者の Web サイトにはないので、タグ付け方法は、標準的な Analytics 実装とは少し異なります。

## ワークフロー

Adobe Analytics を実装するための包括的なワークフローは次のとおりです。

1. `stats.html` ページを作成します。URL からクエリー文字列パラメーターを取り込み、各パラメーターを Analytics 変数に割り当てるには、このページをコード化します
1. Web サーバー上で `stats.html` ページをホストします
1. Iframe 内で `stats.html` ファイルを参照して Facebook インスタント記事に Analytics を実装します
1. Iframe の `src` 属性にクエリー文字列パラメーターを含めます

### 手順 1：`stats.html` ページを作成する

次のサンプル HTML は、インスタント記事から統計値を取得するのに使用できます。このファイルは、通常、会社の Web サーバーのうちの 1 つでホストされます。インスタント記事が読み込まれるたびに、iframe にファイルが読み込まれ、アドビへのデータの送信がトリガーされます。

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.data.adobedc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;

      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### 手順 2：Web サーバー上で `stats.html` ページをホストする

`stats.html` ページを最新バージョンの `AppMeasurement.js` および `VisitorAPI.js` と一緒にホストすることをお勧めします。組織内の適切なエンジニアリングチームと協力して、このファイルを正しい場所にホストします。

### 手順 3：各 Facebook インスタント記事ページで `stats.html` を参照する

Facebook インスタント記事コンテンツを作成する際に、Analytics HTML コンテンツを iFrame 内に埋め込むことができます。次に例を示します。

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 手順 4：カスタム変数およびイベントトラッキングを設定する

カスタム変数およびイベントは、Analytics HTML 内で 2 つの異なる方法でトラッキングできます。

* 変数の値とイベントを直接 `stats.html` ページに含めます。ここで定義する変数は、すべての Facebook インスタント記事で通常同じ値に最適です。
* Iframe を参照するクエリー文字列の一部として変数値を含めます。この方法を使用すると、Facebook インスタント記事から Analytics コードをホストする iframe に変数値を送信できます。

次の例は、クエリー文字列に含まれる複数のカスタム変数を示しています。次に、`stats.html` の JavaScript が `s.Util.getQueryParam()` を使用してクエリー文字列を確認します。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>iframe の性質上、 リファラーディメンションは自動的には追跡されません。追跡する場合は、クエリー文字列の一部にこのディメンションを含めてください。

## Facebook インスタント記事とプライバシー

Analytics HTML ページがお使いの Web サーバーでホストされている限り、アドビは、既存のプライバシーポリシーをすべての Facebook インスタント記事にわたってサポートできます。プライマリサイトでの追跡をオプトアウトしたユーザーは、すべての Facebook インスタント記事の追跡をオプトアウトします。ユーティリティページでは、Adobe Experience Cloud ID サービスもサポートされているので、Facebook インスタント記事のデータを他の Experience Cloud と統合できます。
