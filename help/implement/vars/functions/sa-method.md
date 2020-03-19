---
title: sa
description: 導入時にいつでもレポートスイートを変更できます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# sa

この方 `sa()` 法を使用すると、ページ上のレポートスイートをいつでも動的に変更できます。 ページを再読み込みせずに別のレポートスイートにデータを送信する場合は、この方法を使用できます。

## Adobe Experience Platform Launchでのsaメソッドの使用

インターフェイス内のレポートスイートを柔軟に変更する方法はありません。 Adobe Analyticsの拡張機能を設定する際に、アコーデ [!UICONTROL Library Management] ィオンの下にレポートスイートを設定できます。 ただし、ルールを使用してレポートスイートを変更または更新することはできません。 設定後にレポートスイートの値を更新する場合は、AppMeasurementの構文に従ってカスタムコードエディターを使用します。

## s.sa()（AppMeasurementおよびカスタムコードエディターの起動）

メソッドを呼び `s.sa()` 出して、送信先レポートスイートを変更します。 唯一の引数は、レポートスイートIDを含む文字列、またはコンマで区切られた複数のレポートスイートIDです。 レポートスイートID引数は必須です。 文字列引数にはスペースを使用しないでください。

```js
s.sa("examplersid");
```

## 例   

ユーザがサイト上で特定のアクションを行った場合は、レポートスイートを変更できます。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
