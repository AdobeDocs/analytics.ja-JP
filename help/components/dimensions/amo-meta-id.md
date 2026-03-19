---
title: AMO Meta 広告クリック ID
description: Adobe Media Optimizer Meta Ads Click ID は、Adobe Advertising統合で使用されます。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 10%

---

# AMO Meta 広告クリック ID

**[!UICONTROL AMO Meta広告クリック ID]** は、Adobe Advertising統合で使用される広告クリック識別子です。 [Analytics for Advertising](https://experienceleague.adobe.com/ja/docs/advertising/integrations/analytics/overview) 統合を有効にすると、ディメンションが自動的に作成されます。 主に、人間が読み取れるレポートディメンションではなく、生のトラッキング識別子として役立ちます。

## このディメンションへのデータ入力

このディメンションは、次の複数の方法で値を収集します。

* クリックスルートラフィックの場合、データは、通常、広告ドリブン型トラフィックがサイトに入るページにある `fbclid` ページ URL[&#x200B; の &#x200B;](page-url.md) クエリ文字列パラメーターから収集されます。
* クリックスルートラフィックは、URL にトラッキングコードが含まれていないが、Adobe Advertising JavaScriptによって過去 2 分以内にクリックが検出された場合にもキャプチャできます。

## ディメンション項目

Dimensionの商品には、Meta（Facebook）広告ネットワークが生成した広告クリック ID が含まれます。 ハッシュ化された値の長さは様々ですが、通常は数百文字です。 （切り捨てられた）値の例を次に示します。

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
