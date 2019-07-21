---
description: Facebook インスタント記事に Analytics を導入する方法です。
keywords: Analyticsの導入;embed;カスタム変数;カスタムイベント;訪問者の追跡;tracking;制限事項
seo-description: Facebook インスタント記事に Analytics を導入する方法です。
seo-title: Facebook インスタント記事
solution: Analytics
title: Facebook インスタント記事
topic: 開発者と導入
uuid: 04b6366b-7c52-4ae- b2dd- bb6b78fd409c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Facebook インスタント記事

Facebook インスタント記事に Analytics を導入する方法です。

Facebook インスタント記事は、発行者が Facebook で迅速にインタラクティブな記事を作成するための新しい手法です。インスタント記事は、モバイル Web よりも最大 10 倍高速にコンテンツを読み込めます。

Adobe Analytics は、Facebook インスタント記事内に埋め込んで、コンテンツでやり取りした訪問者の行動をトラッキングできます。発行者のコンテンツは Facebook アプリ内にあり、発行者の Web サイトにはないので、タグ付け方法は、標準的な Analytics 実装とは少し異なります。

## 手順 1. Analytics HTML ページを埋め込む {#section_0DF847F8BA624CF8A239C10003A39E59}

Facebook インスタント記事コンテンツを作成する際に、Analytics HTML コンテンツを iFrame 内に埋め込むことができます。以下に例を示します。

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## 手順 2：Analytics HTML を修正する {#section_76707B51D63A47FF833C2D3FFF8412B4}

次のサンプル HTML は、インスタント記事から統計値を取得するのに使用できます。このファイルは、通常、会社の Web サーバーのうちの 1 つでホストされます。インスタント記事が読み込まれるたびに、手順 1 で説明したように、iframe にファイルが読み込まれ、Adobe への分析データの送信がトリガーされます。

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**このサンプル HTML を具体的な実装用に修正するには**

1. VisitorAPI.js および AppMeasurement.js の未修正の最新コピーを会社の Web サーバー上の共通のディレクトリでホストすることをお勧めします。

   また、これらのファイルは、必要に応じて Analytics UI のコードマネージャーからダウンロードできます。

1. Analytics 実装の標準設定変数を含めます。

   1. Experience Cloud 組織 ID。
   1. Facebook インスタント記事トラフィックを取得するレポートスイート ID。
   1. 会社のトラッキングサーバードメイン。
   1. 訪問者名前空間変数。**注意：**&#x200B;これらの値の多くは、標準 Analytics 実装内に見けることができます。必要に応じて、適切な値の提供についてカスタマーケアまたはアドビコンサルティングにお問い合わせいただくこともできます。

1. [カスタム変数およびイベントトラッキングを設定](../../implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B)します。
1. Include the page view image request syntax `( s.t())`.

## 手順 3. カスタム変数およびイベントトラッキングを設定する {#section_932C41BD21154C25B99389299BDF3E0B}

カスタム変数およびイベントは、Analytics HTML 内で異なる方法でトラッキングできます。第 1 の方法は標準 Analytics 実装でおこなうのと同じように、JavaScript ロジックをカスタム設定に含めることです。例えば、prop の値を設定するには、通常の実装で使用しているのと同じ構文を使用するだけです。

```
s.prop10 = "Facebook Instant Article";
```

また、iframe `src` 属性のクエリ文字列パラメーターを利用することで、変数を iframe に動的に送信できます。次に例を示します。

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

続いて、これらのクエリ文字列パラメーターは、次のようにデフォルトの ライブラリ内の `Util.getQueryParam`[!DNL AppMeasurement] 関数を使用することで、Analytics HTML JavaScript のカスタム変数セクションに設定されます。

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## 訪問者トラッキング {#section_60F0C77659534949831E85B5FD9AE81E}

Analytics HTML ページがお使いの Web サーバーでホストされている限り、アドビは、既存のプライバシーポリシーをすべての Facebook インスタント記事にわたってサポートできます。これは、エンドユーザーがプライマリサイトのトラッキングをオプトアウトした場合、追加の手順を必要としないで、すべての Facebook インスタント記事のトラッキングもオプトアウトされることを意味します。また、このユーティリティページを使用すると、Facebookインスタント記事でキャプチャされた指標と変数を他のExperience Cloudと統合できるように、IDサービス（訪問者ID）がサポートされます。(An example is for targeted advertising using [!DNL Adobe Audience Manager]).

## トラッキングの制限 {#section_1EE1BB069A3148DB9446371AFE196567}

わずかですがこの方法で注意すべき問題があります。通常、Facebook インスタント記事の JavaScriptでのみアクセス可能な DOM 値（リファラーなど）が、トラッキング用の iframe で取得できなくなります。ただし、標準的な技術のレポート（ブラウザー、デバイス、画面サイズまたは解像度など）は、通常どおりに機能します。さらに、pageURL は、ユーティリティページから [!DNL document.referrer] を参照することで取得できます。

## What's Next? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] は、Facebook および発行者と提携して、モバイル Web の発行者に業界最先端の分析機能を提供し、超高速ユーザーエクスペリエンスを実現します。アドビは、長期的な最高のソリューションを構築し、お客様が抱える分析ニーズの発展に応えることに取り組んでいきます。

Facebook インスタント記事プロジェクトは、動きが速く常に変化が起こっているので、更新を頻繁にご確認ください。今後、統合はさらに強化され、より多くの発行者が Facebook インスタント記事を採用するようになるので、変更に留意してください。

質問や問題がある場合は、アドビコンサルタントまたはアドビカスタマーケアにお問い合わせください。
