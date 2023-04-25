---
title: キャンペーン
description: 「トラッキングコード」ディメンションを設定します。
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 68%

---

# キャンペーン

`campaign` 変数は、サイトでのトラッキングコードの収集専用です。以前のバージョンの Adobe Analytics では、ほとんどのディメンションの分類として使用できる特別な処理がおこなわれていました。現在のバージョンの Adobe Analytics では、eVar と同じ動作をします。

この変数は [トラッキングコード](/help/components/dimensions/tracking-code.md) ディメンション。 通常、値は [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) ユーティリティメソッド。 ただし、この変数の設定方法は組織によって決まります。

## Web SDK を使用したキャンペーン

キャンペーンは [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) XDM フィールドの下 `marketing.trackingCode`.

## Adobe Analytics拡張機能を使用したキャンペーン

キャンペーンは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. を [!UICONTROL 拡張] Adobe Analyticsのドロップダウンリスト [!UICONTROL アクションタイプ] から [!UICONTROL 変数を設定].
6. [!UICONTROL キャンペーン]セクションを見つけます。

キャンペーンは、値またはクエリー文字列パラメーターに設定できます。

## AppMeasurement の s.campaign と Analytics 拡張機能のカスタムコードエディター

`s.campaign` 変数は、通常、マーケティング活動で使用されるトラッキングコードを含む文字列です。最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
