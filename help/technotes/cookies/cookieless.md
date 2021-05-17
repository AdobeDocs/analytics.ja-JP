---
title: ブラウザーのCookie制限の影響を軽減するオプション
description: ブラウザーのCookie制限の影響を軽減して、Adobe Analyticsでのデータ収集を改善する方法を学びます。
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 5%

---


# ブラウザーのCookie制限の影響を軽減するオプション

このドキュメントでは、主要訪問者ーがcookieのトラッキング防止対策を実装する際に、プロパティやソリューション間で永続的なブラウザーの識別を保持するためのオプションについて説明します。

Adobe Analyticsは、訪問者のオンサイトアクティビティを記録するためにファーストパーティcookieを利用しています。 また、Analyticsは、サードパーティcookieを利用して、訪問者のオフサイトアクティビティ(所有する他のドメインのアクティビティなど)を把握します。 サードパーティCookieは多くのブラウザーでブロックされ、Chromeによるサポートの削除が予定されています（現在のところ2022年に予定されています）。 ファーストパーティcookieはすべてのブラウザーで許可されますが、SafariおよびAppleの[ITPトラッキング防止](https://webkit.org/tracking-prevention)対策に基づくその他のブラウザーでの有効期限は限られます。 ブラウザーcookieに関する現在の制限について詳しくは、[Adobe Analyticsとブラウザーcookie](cookies.md)を参照してください。

これらのブラウザーの制限は、匿名サードパーティの追跡から、信頼するユーザーとブランド間の情報の明示的な共有に向けて、より広い範囲に及ぶ動きを反映しています。 この移行をサポートするため、Adobeでは、ファーストパーティの関係で収集された永続的な識別子を含め、従来のcookieを補完する方法を提供しています。

## Customer Journey Analyticsとクロスデバイス分析

[Adobe顧客ジャーニー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) 分析と [デバイス間](/help/components/cda/overview.md) 分析のユーザーは、cookieに加えて、ハッシュ化されたログインなどの永続的な識別子を含めることができます。これにより、デバイス間や、Customer Journey Analyticsの場合は、オンラインチャネルとオフラインデバイス間での顧客のジャーニーを把握できます。

* **顧客ジャーニー** 分析は、Adobe Experience Platformに基づいて構築され、一般的な顧客IDに基づいて、Analysis Workspaceのオンラインデータとオフラインデータを柔軟に組み合わせることができます。任意の分析に使用するIDを指定し、Analysis Workspaceでデータを調べることができます。 Analytics Select、PrimeおよびUltimateのお客様は、この製品をアドオン製品として購入できます。

* **デバイス間** 分析は、従来のAdobe Analyticsの機能強化で、訪問者に対する代替識別子を使用できるようになりました。この機能を使用すると、デバイス中心の表示から個人中心の表示に移行できます。 デバイス間分析は、Analytics Ultimateのお客様が利用できます。

## サーバー側のデータ収集

サーバー側のコレクションは、cookieの設定のブラウザーのメカニズムに依存する代わりに、独自の識別子を柔軟に提供します。

[データ挿入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)または[バルクデータ挿入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)を使用して、Analyticsサーバー側にデータを送信できます。 Bulk Data Insertion APIは、新しいサーバー側実装に推奨されます。 2つのAPIの比較については、「[使用すべきAdobe Analyticsツール](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)」を参照してください。

## 詳細情報

サードパーティcookieからトランジションに移行するためにビジネスで実用的な手順については、[Adobeを使ってcookieを使わない世界で顧客を獲得し、維持する](https://business.adobe.com/solutions/cookieless.html)と、サードパーティcookieを越えた考え方を参照してください。サードパーティcookieのない世界への完全なガイド](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)です。」[

>[!MORELIKETHIS]
[Adobe Analytics とブラウザーの cookie](cookies.md)>
>
