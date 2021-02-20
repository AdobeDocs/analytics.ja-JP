---
title: sa
description: いつでも実装のレポートスイートを変更できます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---


# sa

`sa()` メソッドを使用すると、ページ上のレポートスイートをいつでも動的に変更できます。ページをリロードせずに別のレポートスイートにデータを送信する場合は、このメソッドを使用できます。

## Adobe Experience Platform Launch での sa メソッドの使用

インターフェイス内のレポートスイートを柔軟に変更する方法はありません。Adobe Analytics 拡張機能を設定する際に、「[!UICONTROL ライブラリ管理]」アコーディオンの下でレポートスイートを設定できます。ただし、ルールを使用してレポートスイートを変更または更新することはできません。設定後にレポートスイートの値を更新する場合は、AppMeasurement 構文に従ってカスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.sa()

`s.sa()` メソッドを呼び出して、送信先のレポートスイートを変更します。唯一の引数は、レポートスイート ID を含む文字列、またはコンマで区切られた複数のレポートスイート ID です。レポートスイート ID 引数は必須です。文字列引数にスペースを使用しないでください。

```js
s.sa("examplersid");
```

## 例

ユーザーがサイト上で特定のアクションを実行した場合は、レポートスイートを変更できます。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
