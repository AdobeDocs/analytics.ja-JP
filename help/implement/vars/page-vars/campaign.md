---
title: キャンペーン
description: 「トラッキングコード」ディメンションを設定します。
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/4OF7xoZs8bLS4UW8wfJYHqSyc-gNVLAfPs5j3NwZCcM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 74%

---

# キャンペーン

`campaign` 変数は、サイトでのトラッキングコードの収集専用です。 以前のバージョンの Adobe Analytics では、ほとんどのディメンションの分類として使用できる特別な処理がおこなわれていました。 現在のバージョンの Adobe Analytics では、eVar と同じ動作をします。

この変数は、[&#x200B; トラッキングコード &#x200B;](/help/components/dimensions/tracking-code.md) ディメンションに入力されます。 通常、[`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) ユーティリティメソッドを使用して、クエリ文字列からその値を取得します。 ただし、この変数を設定する方法は、組織によって正確に決まります。

## Web SDKを使用したキャンペーン

Campaignは次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign`または`data.__adobe.analytics.v0`

## Adobe Analytics拡張機能を使用したキャンペーン

キャンペーンは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL キャンペーン]セクションを見つけます。

キャンペーンは、値またはクエリ文字列パラメーターに設定できます。

## AppMeasurementのs.campaignとAnalytics拡張機能のカスタムコードエディター

`s.campaign` 変数は、通常、マーケティング活動で使用されるトラッキングコードを含む文字列です。 最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
