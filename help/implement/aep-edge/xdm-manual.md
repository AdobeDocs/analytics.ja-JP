---
title: XDMデータのAnalyticsへの手動マッピング
description: 'Experience PlatformからAdobe AnalyticsへのXDMデータの手動マッピング '
translation-type: tm+mt
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 6%

---


# XDMデータのAnalyticsへの手動マッピング

Adobe Experience Platform(AEP)Web SDKは、PlatformとAnalyticsの間でデータを手動でマッピングするのに役立つツールです。

Analyticsに自動的にマッピングされないXDMデータの場合は、 [コンテキストデータを追加して](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) 、 [スキーマに合わせることができます](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html)。 その後、Analyticsの [処理ルールでAnalytics変数に値を設定するために使用でき](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) ます。

また、デフォルトのアクションと製品リストのセットを使用して、AEP Web SDKでデータを送信または取得できます。 これを行うには、「 [製品](https://docs.adobe.com/content/help/en/experience-platform/edge/implement/commerce.html)」を参照してください。

## コンテキストデータ

Analyticsで使用されるXDMデータは、ドット表記を使用してフラット化され、として使用でき `contextData`ます。 次の値のペアのリストは、次の例を示していま `context data`す。

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "http://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## 処理ルール

All data collected by the edge network can be accessed via [processing rules](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html). Analyticsでは、処理ルールを使用して、コンテキストデータをAnalytics変数に組み込むことができます。

例えば、次のルールでは、Analyticsが **内部検索用語(eVar2)にa.x_atag.search.term（コンテキストデータ）に関連付けられたデータ** を入力するように設定されています ****。

![](assets/examplerule.png)


## XDM スキーマ

エクスペリエンスプラットフォームでは、スキーマを使用して、一貫性のある再利用可能な方法でデータの構造を記述します。 システム間で一貫したデータを定義することで、意味を保持しやすくなり、データから価値を得ることができます。 Analyticsのコンテキストデータは、スキーマで定義された構造と連携します。

次の例は、AEP Web SDKでデータを送信および取得する [`event`](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html)`xdm` オプションでコマンドを使用する方法を示しています。 この例では、 `event` コマンドはExperienceEvent Commerce Detailsスキーマに一致し [、productListItems](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) と `name``SKU` 値が追跡されるようにします。


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

AEP Web SDKを使用したイベントのトラッキングについて詳しくは、 [トラッキングイベントを参照してください](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html)。