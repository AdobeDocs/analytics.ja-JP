---
title: キャンペーン
description: 「トラッキングコード」ディメンションを設定します。
translation-type: tm+mt
source-git-commit: 7220b99268532adb2e425d52744dbc3efb615953
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---


# キャンペーン

`campaign` 変数は、サイトでのトラッキングコードの収集専用です。以前のバージョンの Adobe Analytics では、ほとんどのディメンションの分類として使用できる特別な処理がおこなわれていました。現在のバージョンの Adobe Analytics では、eVar と同じ動作をします。

この変数は、「トラッキングコード」ディメンションを設定します。

## Adobe Experience Platform Launch でのキャンペーン

キャンペーンは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL キャンペーン]セクションを見つけます。

キャンペーンは、値またはクエリー文字列パラメーターに設定できます。

## AppMeasurement および Launch カスタムコードエディターの s.campaign

`s.campaign` 変数は、通常、マーケティング活動で使用されるトラッキングコードを含む文字列です。最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
