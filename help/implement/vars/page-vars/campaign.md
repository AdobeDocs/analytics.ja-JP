---
title: キャンペーン
description: 「トラッキングコード」ディメンションを設定します。
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 67%

---

# キャンペーン

`campaign` 変数は、サイトでのトラッキングコードの収集専用です。以前のバージョンの Adobe Analytics では、ほとんどのディメンションの分類として使用できる特別な処理がおこなわれていました。現在のバージョンの Adobe Analytics では、eVar と同じ動作をします。

この変数は、[&#x200B; トラッキングコード &#x200B;](/help/components/dimensions/tracking-code.md) ディメンションを設定します。 通常、[`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) ユーティリティメソッドを使用して、クエリ文字列から値を取得します。 ただし、組織はこの変数の設定方法を正確に決定しています。

## Web SDKを使用したキャンペーン

Campaign は、次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [Data オブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign` または `data.__adobe.analytics.v0`

## Adobe Analytics拡張機能を使用したキャンペーン

キャンペーンは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL &#x200B; アクションタイプ &#x200B;]」を [!UICONTROL &#x200B; 変数を設定 &#x200B;] に設定します。
6. [!UICONTROL キャンペーン]セクションを見つけます。

キャンペーンは、値またはクエリ文字列パラメーターに設定できます。

## AppMeasurementの s.campaign と Analytics 拡張機能のカスタムコードエディター

`s.campaign` 変数は、通常、マーケティング活動で使用されるトラッキングコードを含む文字列です。最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
