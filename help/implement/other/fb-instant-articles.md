---
title: Facebook インスタント記事での実装
description: Facebook インスタント記事ページに Adobe Analytics を実装します。
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
role: Developer
TQID: 'https://experienceleague.adobe.com/S2ljH7WOuX6qvYplo-6k-MXw6FKG-vhk78EiGQFiImg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 468
ht-degree: 89%

---

# Facebook インスタント記事での実装

Facebook インスタント記事を使用すると、Facebook 上で高速でインタラクティブな記事を作成できます。 インスタント記事は、モバイル Web よりも最大 10 倍高速にコンテンツを読み込めます。

Adobe Analytics を Facebook インスタント記事に埋め込んで、訪問者の行動を追跡できます。 発行者のコンテンツは Facebook アプリ内にあり、発行者の Web サイトにはないので、タグ付け方法は、標準的な Analytics 実装とは少し異なります。

## ワークフロー

Adobe Analytics を実装するための包括的なワークフローは次のとおりです。

1. `stats.html` ページを作成します。 URL からクエリ文字列パラメーターを取り込み、各パラメーターを Analytics 変数に割り当てるには、このページをコード化します
1. Web サーバー上で `stats.html` ページをホストします
1. Iframe 内で `stats.html` ファイルを参照して Facebook インスタント記事に Analytics を実装します
1. Iframe の `src` 属性にクエリー文字列パラメーターを含めます

### 手順 1：`stats.html` ページを作成する

以下のサンプル HTMLを使用して、インスタント記事から統計を取得できます。 通常、このファイルは企業のweb サーバーのいずれかにホストされます。 インスタント記事が読み込まれるたびに、iframe にファイルが読み込まれ、アドビへのデータの送信がトリガーされます。

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
      var s_account = "examplersid1,examplersid2";
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

`stats.html` ページを最新バージョンの `AppMeasurement.js` および `VisitorAPI.js` と一緒にホストすることをお勧めします。 組織内の適切なエンジニアリングチームと協力して、このファイルを正しい場所にホストします。

### 手順 3：各 Facebook インスタント記事ページで `stats.html` を参照する

Facebook インスタント記事コンテンツを作成する際に、Analytics HTML コンテンツを iFrame 内に埋め込むことができます。 次に例を示します。

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 手順 4：カスタム変数およびイベントトラッキングを設定する

カスタム変数およびイベントは、Analytics HTML 内で 2 つの異なる方法でトラッキングできます。

* 変数の値とイベントを直接 `stats.html` ページに含めます。 ここで定義する変数は、すべての Facebook インスタント記事で通常同じ値に最適です。
* Iframe を参照するクエリ文字列の一部として変数値を含めます。 この方法を使用すると、Facebook インスタント記事から Analytics コードをホストする iframe に変数値を送信できます。

次の例は、クエリ文字列に含まれる複数のカスタム変数を示しています。 次に、`stats.html` の JavaScript が `s.Util.getQueryParam()` を使用してクエリ文字列を確認します。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>iframe の性質上、 リファラーディメンションは自動的には追跡されません。 トラッキングする場合は、クエリ文字列の一部にこのディメンションを含めてください。

## Facebook インスタント記事とプライバシー

Analytics HTML ページがお使いの Web サーバーでホストされている限り、アドビは、既存のプライバシーポリシーをすべての Facebook インスタント記事にわたってサポートできます。 プライマリサイトでの追跡をオプトアウトしたユーザーは、すべての Facebook インスタント記事の追跡をオプトアウトします。 ユーティリティページでは、訪問者ID サービスもサポートされているため、Facebook Instant Article データを他のCX Enterpriseと統合できます。
