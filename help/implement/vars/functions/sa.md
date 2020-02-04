---
title: sa
description: 導入時にいつでもレポートスイートを変更できます。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# sa

この方 `sa` 法を使用すると、ページ上のレポートスイートをいつでも動的に変更できます。 ページをリロードせずに別のレポートスイートにデータを送信する場合は、この方法を使用できます。

## Adobe Experience Platform Launchでのsaメソッドの使用

インターフェイス内のレポートスイートを柔軟に変更する方法はありません。 Adobe Analytics拡張機能を設定する際に、ライブラ [!UICONTROL リ管理アコーディオンの下に] 、レポートスイートを設定できます。 ただし、ルールを使用してレポートスイートを変更または更新することはできません。 設定後にレポートスイートの値を更新する場合は、AppMeasurement構文に従ってカスタムコードエディターを使用します。

## s.sa()（AppMeasurementおよびカスタムコードエディターの起動）

メソッドを呼び `s.sa()` 出して、送信先のレポートスイートを変更します。 唯一の引数は、レポートスイートIDを含む文字列、またはコンマで区切られた複数のレポートスイートIDです。 レポートスイートID引数は必須です。 文字列引数にスペースを使用しないでください。

```js
s.sa("examplersid");
```

## 例

ユーザがサイト上で特定のアクションを実行した場合は、レポートスイートを変更できます。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
