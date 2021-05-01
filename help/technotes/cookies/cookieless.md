---
title: ブラウザーのCookie制限の影響を軽減するオプション
description: ブラウザーのCookie制限の影響を軽減して、Adobe Analyticsでのデータ収集を改善する方法を学びます。
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 6%

---


# ブラウザーのCookie制限の影響を軽減するオプション

このドキュメントでは、主要ブラウザーがcookieに対するトラッキング防止対策を実装する際に、プロパティやソリューション間で永続的な訪問者の識別を保持する方法を説明します。

Adobe Analyticsは、訪問者のオンサイトアクティビティを記録するためにファーストパーティcookieを利用しています。 また、Analyticsは、サードパーティcookieを利用して、訪問者のオフサイトアクティビティ(所有する他のドメインのアクティビティなど)を把握します。 サードパーティCookieは多くのブラウザーでブロックされ、Chromeによるサポートの削除が予定されています（現在のところ2022年に予定されています）。 ファーストパーティcookieはすべてのブラウザーで許可されますが、SafariおよびAppleの[ITPトラッキング防止](https://webkit.org/tracking-prevention)対策に基づくその他のブラウザーでの有効期限は限られます。 ブラウザーcookieに関する現在の制限について詳しくは、「[Adobe Analyticsとブラウザーcookie](cookies.md)」を参照してください。

これらのブラウザーの制限は、匿名サードパーティの追跡から、信頼するユーザーとブランド間の情報の明示的な共有に向けて、より広い範囲に及ぶ動きを反映しています。 この移行をサポートするため、Adobeでは、ファーストパーティの関係で収集された永続的な識別子を含め、従来のcookieを補完する方法を提供しています。

## Customer Journey Analyticsとクロスデバイス分析

[Adobe顧客ジャーニー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) 分析と [デバイス間](/help/components/cda/overview.md) 分析のユーザーは、cookieに加えて、ハッシュ化されたログインなどの永続的な識別子を含めることができます。

* **顧客ジャーニー** 分析は、Adobe Experience Platformとの統合を通じて、Analysis Workspaceのチャネル間分析を可能にします。任意のIDを使用して、クエリ時にExperience Platformで利用できるオンラインおよびオフラインの顧客データを統合します。

* **クロスデバイス** 分析では、Adobe Experience PlatformIDサービスを使用して、デジタルデバイスがユーザーにどのようにマッピングされ、IDをまたいでユーザージャーニーをステッチするかを識別します。これは、Adobe Experience Cloud・デバイスCo-opグラフ、プライベート・デバイス・グラフ、またはフィールド・ベースのステッチを使用します。

## サーバー側のデータ収集

サーバー側のコレクションは、cookieの設定のブラウザーのメカニズムに依存する代わりに、独自の識別子を柔軟に提供します。

[データ挿入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)または[バルクデータ挿入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)を使用して、サーバー側のデータをAnalyticsにインポートできます。 2つのAPIの比較については、「[使用すべきAdobe Analyticsツール](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)」を参照してください。

## 詳細情報

サードパーティcookieからトランジションに移行するためにビジネスで実行できる実用的な手順については、「[Adobeを使用してcookieを使用しない世界で顧客を獲得し、維持する」および「[サードパーティcookieを越えた考え方：サードパーティcookieのない世界への完全なガイド](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)です。」](https://business.adobe.com/solutions/cookieless.html)

>[!MORELIKETHIS]
>
>[Adobe Analytics とブラウザーの cookie](cookies.md)
