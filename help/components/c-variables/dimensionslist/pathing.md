---
description: パス分析に基づくレポートのグループ。技術的には、パスとは、あるページ名から別のページ名（ある値から別の値）に移動することです。
title: パス
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# パス

パス分析に基づくレポートのグループ。技術的には、パスとは、あるページ名から別のページ名（ある値から別の値）に移動することです。

より柔軟なパスオプションについては、[Analysis Workspace のフロー](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/flow.html)を使用します。

>[!NOTE] パスを有効にするには、に進みま **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**&#x200B;す。 サイトセクションおよびサーバーレポートでパスを有効にするには、カスタマーケアにお問い合わせください。

値が収集される順序を把握する必要がある場合は、それらの値を収集する変数のパスを有効にする必要があります。 ページのパスはデフォルトで有効になっています。 propのパスは、特定の場合にのみ適しているので、デフォルトでは有効になっていません。 propのパスを有効にするには、カスタマーケアにお問い合わせください。

>[!NOTE]Ad Hoc Analysis では、prop の分類を有効にすると、有効な prop に設定されているすべての分類でパス指標を利用できるようになります。

**例：サイトセクションのパス**

Enabling pathing for the *`s.channel`* variable allows you to track how site visitors move between Site Sections (as the value changes).

![](assets/path_sections.png)

その後、様々なパスレポート(ページグループやサ [!UICONTROL Next Site Section Flow]イトのセクション間の訪問者の移動を示すレポートなど)でパスを使用できます。

![](assets/paths_report.png)

**例 — 検索のパス**

ある値から別の値に移動するのと同じ概念が、他のトラフィック変数（*`s.props`*）を含むにも当てはまります。例えば、内部検索キーワード&#x200B;*`s.prop`* のパスを有効にすると、訪問者が検索用語をたどったパスを確認できます。

**例：ログインステータスごとのパス**

訪問者のログインステータスに基づいて、訪問者がどのようにサイトを経由しているかを知りたい場合があります。 この情報を表示するには、パスレポートでログインステータスを確認しません。訪問者がそのレポート内の値をどのように変更したか、または訪問者がログインからログアウトにどのように変更したかが表示されます。 代わりに、セグメント値と   *`s.pageName`* 変数を連結し、その結果の変数をパスします。次に、メンバーのステータスごとのページパスのサンプルコードを示します。

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

次に、のパスを有効にして、メン *`s.prop19`* バーがページをどのようにパスしているかを確認します。

>[!NOTE]Ad Hoc Analysis を実行すると、セグメント値を連結することなく、ページパスをセグメント化でき、任意のセグメントをパスレポートに適用できます。

