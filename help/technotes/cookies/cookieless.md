---
title: ブラウザーの cookie 制限の影響を軽減するオプション
description: Adobe Analytics のデータ収集を改善するために、ブラウザーの cookie 制限の影響を軽減する方法について説明します。
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: ht
source-wordcount: '516'
ht-degree: 100%

---


# ブラウザーの cookie 制限の影響を軽減するオプション

このドキュメントでは、主要なブラウザーが cookie に対するトラッキング防止対策を実装する際に、プロパティやソリューション間で永続的な訪問者の識別を保持するためのオプションについて説明します。

Adobe Analytics は、ファーストパーティ cookie を利用して訪問者のオンサイトアクティビティを記録します。また、Analytics はサードパーティ cookie を利用して、自社の他のドメインでのアクティビティなど、訪問者のオフサイトアクティビティを把握します。サードパーティ cookie は多くのブラウザーでブロックされ、Chrome によるサポートの停止（現在は 2022 年に予定）によって、ほとんど利用できなくなります。ファーストパーティ cookie はすべてのブラウザーで許可されますが、Safari および他のブラウザーでは Apple の [ITP トラッキング防止](https://webkit.org/tracking-prevention)手段として、有効期限が制限されています。ブラウザー cookie に関する現在の制限について詳しくは、「[Adobe Analytics とブラウザーの cookie](cookies.md)」を参照してください。

これらのブラウザーの制限は、匿名のサードパーティトラッキングから、信頼するユーザーやブランド間での情報の明示的な共有への移行を反映しています。この移行をサポートするために、アドビは、ファーストパーティとの関係を通じて収集された永続的な識別子を含め、お客様が従来の cookie を補完する方法を提供します。

## Customer Journey Analytics とクロスデバイス分析

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) と[クロスデバイス分析](/help/components/cda/overview.md)によって、cookie に加えて、ハッシュ化されたログインなどの永続的な識別子を含めることができます。これにより、デバイスをまたいだカスタマージャーニー、また、Customer Journey Analytics の場合はオンラインチャネルとオフラインチャネルをまたいだカスタマージャーニーを把握できます。

* **Customer Journey Analytics** は Adobe Experience Platform を基に構築され、共通の顧客 ID に基づいて、Analysis Workspace でオンラインとオフラインのデータを組み合わせる柔軟性を提供します。任意の分析に使用する ID を指定し、Analysis Workspace でデータを調べることができます。Analytics Select、Prime および Ultimate のお客様は、これをアドオン製品として購入できます。

* **クロスデバイス分析** は、従来の Adobe Analytics の機能強化で、訪問者に代替識別子を使用できるようになりました。この機能を使用すると、デバイス中心のビューからユーザー中心のビューに移動できます。クロスデバイス分析は、Analytics Ultimate のお客様が利用できます。

## サーバーサイドのデータ収集

サーバーサイドの収集は、ブラウザーのメカニズムに依存して cookie を設定するのではなく、独自の識別子を提供する柔軟性を提供します。

[Data Insertion API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) または [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) を使用して、Analytics サーバーサイドにデータを送信できます。新しいサーバーサイド実装では、Bulk Data Insertion API をお勧めします。2 つの API の比較については、「[使用する Adobe Analytics ツール](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html?lang=ja)」を参照してください。

## 詳細情報

ビジネスがサードパーティ cookie から移行するための実用的な手順については、『[アドビで、クッキーのない世界で顧客を獲得して保つ](https://business.adobe.com/jp/solutions/cookieless.html)』と詳細な『[サードパーティ cookie を超えて考える：サードパーティ cookie のない世界への完全なガイド](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)』を参照してください。

>[!MORELIKETHIS]
[Adobe Analytics とブラウザーの cookie](cookies.md)>
>
