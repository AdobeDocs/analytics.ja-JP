---
title: campaign
description: 「トラッキングコード」ディメンションを設定します。
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campaign

この変 `campaign` 数は、サイトでのトラッキングコードの収集専用です。 以前のバージョンのAdobe Analyticsでは、ほとんどのディメンションの分類として使用できる特別な処理が行われていました。 現在のバージョンのAdobe Analyticsでは、eVarと同じ動作をします。

この変数は、「トラッキングコード」ディメンションを設定します。

## Adobe Experience Platform Launch の Campaign

キャンペーンは、Analytics拡張機能（グローバル変数）の設定中にも、ルール下でも設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「キャンペーン」セク [!UICONTROL ションを見つけます] 。

campaignは、値またはクエリ文字列パラメーターに設定できます。

## AppMeasurementのs.campaignとカスタムコードエディターの起動

この変 `s.campaign` 数は、通常、マーケティング活動で使用されるトラッキングコードを含む文字列です。 最大長は255バイトです。100バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
