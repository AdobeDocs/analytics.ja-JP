---
title: AMO Meta Ads クリック ID
description: Adobe Media Optimizer Meta Ads Click ID （Adobe Advertising統合で使用）。
feature: Dimensions
exl-id: c1def73a-51b9-46bf-9dc7-0fbd46fd6e17
TQID: 'https://experienceleague.adobe.com/3J-pLiOz4QwUewRSmEFsJCg0v-PbEmksUzGKOI0hHoA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 7%
---
# AMO Meta Ads クリック ID

**[!UICONTROL AMO Meta Ads クリック ID]**&#x200B;は、Adobe Advertising統合で使用される広告クリック IDです。 ディメンションは、[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)統合を有効にすると自動的に作成されます。 これは主に、人間が読み取れるレポートディメンションではなく、生のトラッキング識別子として役立ちます。

## このディメンションへのデータ入力

このディメンションは、[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)統合によって自動的に入力されます。設定する変数はありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobe Advertising統合によって設定されます） |
| **Web SDK / XDM フィールド** | なし（Adobe Advertising統合によって設定されます） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

このディメンションは、複数の方法で値を収集します。

* クリックスルートラフィックの場合、データは[ ページ URL](page-url.md)の`fbclid` クエリ文字列パラメーターから収集されます。通常は、広告駆動型トラフィックがサイトに入るページ上に収集されます。
* クリックスルートラフィックは、URLにトラッキングコードが含まれていない場合にもキャプチャできますが、Adobe Advertising JavaScriptでは、前の2分以内にクリックが検出されます。

## ディメンション項目

Dimensionのアイテムには、Meta（Facebook）広告ネットワークによって生成された広告クリックのIDが含まれます。 ハッシュ化された値の長さは様々ですが、通常は数百文字です。 例（切り捨てられた）値には、次のものがあります。

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
