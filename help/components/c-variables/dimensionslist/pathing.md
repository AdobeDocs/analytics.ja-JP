---
description: パス分析に基づくレポートのグループ。技術的には、パスとは、あるページ名から別のページ名（ある値から別の値）に移動することです。
seo-description: パス分析に基づくレポートのグループ。技術的には、パスとは、あるページ名から別のページ名（ある値から別の値）に移動することです。
seo-title: パス
solution: Analytics
title: パス
topic: レポート
uuid: c4ff9fa8- e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# パス

パス分析に基づくレポートのグループ。技術的には、パスとは、あるページ名から別のページ名（ある値から別の値）に移動することです。

より柔軟なパスオプションについては、[Analysis Workspace のフロー](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html)を使用します。

>[!NOTE]
>
>To enable pathing, go to **[!UICONTROL Admin &gt; Report Suites &gt; Edit Settings &gt; Traffic &gt; Traffic Variables]**. サイトセクションおよびサーバーレポートでパスを有効にするには、カスタマーケアにお問い合わせください。

値が収集される順序がわかっている場合は、それらの値を収集する変数のパスを有効にする必要があります。ページのパスはデフォルトで有効になっています。prop のパスは、特定の場合にのみ当てはまるので、デフォルトで無効になっています。prop のパスを有効にする場合は、カスタマーケアにお問い合わせください。

>[!NOTE]
>
>Ad Hoc Analysisでは、propの分類を有効にすると、有効なpropに設定されているすべての分類でパス指標を利用できるようになります。

**例：サイトセクションのパス**

"*`s.channel`*&#x200B;変数のパスを有効にすると、サイトの訪問者がサイトセクション間をどのように移動しているかを（値の変化により）トラッキングできます。

![](assets/path_sections.png)

パスは、[!UICONTROL 次のサイトセクションのフロー] などの様々なパスレポートで利用できます。このレポートには、訪問者がサイトのページグループやセクションをどのように移動しているかが表示されます。

![](assets/paths_report.png)

**例：検索のパス**

ある値から別の値に移動するのと同じ概念が、他のトラフィック変数にも当てはまり、*`s.props`* と呼ばれる iFrame を読み込みます。For example, if you enable pathing for your Internal Search Term *`s.prop`*, you could see the path visitors take through search terms.

**例：ログインステータスごとのパス**

訪問者のログインステータスに基づき、人々が自分のサイトをどのようにたどっているかを知りたいことがあります。この情報を確認するために、パスレポートでログインステータスを確認したりはしません。これらのレポートは、訪問者がそのレポート内の値をどのように変更させたか、またはログインからログアウトの間に訪問者がどのように変化したかを示すものだからです。代わりに、セグメント値と *`s.pageName`*&#x200B;変数を連結し、その結果の変数をパスします。次に、メンバーステータスごとのページパスのサンプルコードを示します。

```js
s.pageName=“Home Page”; 
s.prop18=“Gold”; // Member Status 
s.prop19=s.prop18 + “:” + s.pageName;
```

次に、*`s.prop19`*&#x200B;のパスを有効にして、メンバーがページ間をどのようにパスするかを確認します。

>[!NOTE]
>
>ad hoc analysisを実行する場合、セグメント値を連結することなくページパスをセグメント化し、任意のセグメントをパスレポートに適用できます。

