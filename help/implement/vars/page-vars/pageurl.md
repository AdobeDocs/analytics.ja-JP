---
title: pageURL
description: 自動的に収集されたページの URL をサイトで上書きします。
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 84%

---

# pageURL

AppMeasurement は、各ヒットでページ URL を自動的に収集します。 AppMeasurement によって自動的に収集されたページ URL を上書きする場合は、この変数を使用できます。 ほとんどの場合、この変数を設定する必要はありません。

>[!NOTE]
>
>この変数は、Analysis Workspace では使用できないディメンションで、 Data Warehouse およびデータフィードでのみ使用できます。 さらに、アドビのデータ収集サーバーでは、すべての[リンクトラッキング](/help/implement/vars/functions/tl-method.md)画像リクエストからこのディメンションを除外します。 ページ URL を Analysis Workspace のディメンションとして使用する場合、またはこのディメンションをリンクトラッキングのヒットで使用する場合は、ヒットごとに `pageURL`eVar[&#128279;](evar.md) に  変数を渡すことを検討してください。

## Web SDKを使用したページ URL

ページ URLは、次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL`または`data.__adobe.analytics.g`

## Adobe Analytics拡張機能を使用したページ URL

Adobe Experience Platform Data CollectionのAnalytics拡張機能は、ページ URLを自動的に入力します。 ただし、Analytics 拡張機能の設定時（グローバル変数）またはルールで、ページ URL の上書きを設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「**[!UICONTROL ルール]**」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「**[!UICONTROL アクション]**」で、既存の「**[!UICONTROL Adobe Analytics - 変数を設定]**」アクションをクリックするか、「+」アイコンをクリックします。
5. **[!UICONTROL 拡張機能]**&#x200B;ドロップダウンリストを Adobe Analytics に設定し、**[!UICONTROL アクションタイプ]**&#x200B;を&#x200B;**[!UICONTROL 変数を設定]**&#x200B;に設定します。
6. **[!UICONTROL ページ URL]** セクションを見つけます。

ページ URL は任意の文字列値に設定できます。

## AppMeasurementのs.pageURLとAnalytics拡張機能のカスタムコードエディター

`s.pageURL` 変数は、ページの URL を含む文字列です。 AppMeasurement はこの変数を自動的に収集しますが、必要に応じてその値を上書きできます。

```js
s.pageURL = "https://example.com";
```

ページ URL をレポートのディメンションとして使用する場合は、実装で次の使用を検討してください。

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
