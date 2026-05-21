---
title: linkURL
description: AppMeasurement がリンクトラッキングコールで使用する、自動生成されたリンク URL を上書きします。
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
TQID: https://experienceleague.adobe.com/O8Bd28njZQDnffeUwCiNGNSNRHk4FU-z48r4pt7Eths
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 34%

---

# linkURL

リンクトラッキング呼び出しがAdobeに送信されるたびに、AppMeasurementはクリックされたURLを検出します。 このURLは、ダウンロードリンクや終了リンクなどのリンクタイプを判断するのに役立ちます。 `linkURL` 変数は、検出された URL を上書きするために使用します。

Analysis Workspaceには、この変数に関するディメンションはありません。 [&#x200B; データフィード &#x200B;](/help/export/analytics-data-feed/data-feed-overview.md)の`page_event_var1`列にデータが入力されます。 クリックしたリンクのURLをトラッキングする場合は、[Prop](../page-vars/prop.md)などのカスタム変数を使用することをお勧めします。この場合、Adobeはカスタム変数を使用します。 [Activity Map](/help/analyze/activity-map/overview.md)を使用すると、クリックしたリンクのデータ収集を効率化できます。

## Web SDKを使用したURLのリンク

リンク URLは、次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL`または`data.__adobe.analytics.pev1`

## Adobe Analytics拡張機能を使用したURLのリンク

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.linkURLとAnalytics拡張機能のカスタムコードエディター

`s.linkURL`変数は、クリックしたリンクの完全なURLを含む文字列です。 この変数は、レポートで使用できるディメンションを入力しません。

```js
s.linkURL = "https://example.com";
```

[tl()](../functions/tl-method.md) メソッドの 3 番目の引数が設定されていない場合は、代わりに `linkURL` 変数が使用されます。
