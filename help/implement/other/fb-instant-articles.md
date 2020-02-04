---
title: Facebookインスタント記事を使用した実装
description: Facebookインスタント記事ページへのAdobe Analyticsの実装を参照してください。
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Facebookインスタント記事を使用した実装

Facebookインスタント記事を使用すると、発行者はFacebook上で高速でインタラクティブな記事を作成できます。 インスタント記事は、モバイル Web よりも最大 10 倍高速にコンテンツを読み込めます。

Adobe AnalyticsをFacebookインスタント記事に埋め込んで、訪問者の行動を追跡できます。 投稿者のコンテンツはFacebookアプリ内にあり、投稿者のWebサイトにはないので、タグ付けの方法は、標準的なAnalytics実装とは少し異なります。

## ワークフロー

Adobe Analyticsを実装するための包括的なワークフローは次のとおりです。

1. ページを作成 `stats.html` します。 URLからクエリ文字列パラメーターを取り込み、各パラメーターをAnalytics変数に割り当てるには、このページをコード化します
1. Webサーバー上 `stats.html` でページをホストする
1. iframe内のファイルを参照してFacebookインスタント記事にAnalytics `stats.html` を実装する
1. iframe属性にクエリ文字列パラメーターを含 `src` める

### 手順1:ページの `stats.html` 作成

次のサンプル HTML は、インスタント記事から統計値を取得するのに使用できます。このファイルは、通常、会社の Web サーバーのうちの 1 つでホストされます。インスタント記事が読み込まれるたびに、iframeにファイルが読み込まれ、アドビへのデータの送信がトリガーされます。

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
      var s_trackingServer = "example.sc.omtrdc.net";
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

### 手順2:Webサーバー上 `stats.html` でページをホストする

最新バージョンのおよびと `stats.html` 一緒にページをホストすることをお勧め `AppMeasurement.js` しま `VisitorAPI.js`す。 組織内の適切なエンジニアリングチームと協力して、このファイルを正しい場所にホストします。

### 手順3:各Facebookイン `stats.html` スタント記事ページのリファレンス

Facebookインスタント記事コンテンツを作成する場合は、iframe内に解析HTMLコンテンツを埋め込みます。 次に例を示します。

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 手順4:カスタム変数とイベントトラッキングの設定

カスタム変数とイベントは、次の2つの異なる方法でAnalytics HTML内で追跡できます。

* 変数の値とイベントを直接ページに含め `stats.html` ます。 ここで定義する変数は、すべてのFacebookインスタント記事で通常同じ値に最適です。
* iframeを参照するクエリ文字列の一部として変数値を含めます。 この方法を使用すると、Facebookインスタント記事からAnalyticsコードをホストするiframeに変数値を送信できます。

次の例は、クエリ文字列に含まれる複数のカスタム変数を示しています。 次に、内部のJavaScript `stats.html` が、を使用してクエリ文字列をチェックしま `s.Util.getQueryParam()`す。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] リファラーディメンションは、iframeの性質上、自動的には追跡されません。 追跡する場合は、クエリ文字列の一部にこのディメンションを含めてください。

## Facebookインスタント記事とプライバシー

Analytics HTMLページがWebサーバーでホストされている限り、アドビは、すべてのFacebookインスタント記事に対して既存のプライバシーポリシーをサポートします。 プライマリサイトでの追跡をオプトアウトしたユーザーは、すべてのFacebookインスタント記事の追跡をオプトアウトします。 ユーティリティページでは、Adobe Experience Cloud IDサービスもサポートされているので、Facebookインスタント記事のデータを他のExperience cloudと統合できます。
