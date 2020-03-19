---
title: Util.getQueryParam
description: クエリ文字列パラメータの値を返します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.getQueryParam

ブラウザーURLのクエリ文字列パラメーターには、Analyticsの重要なデータが含まれることがよくあります。 クエリ文字列 `Util.getQueryParam()` からデータを取得するには、このメソッドを使用します。

## Adobe Experience Platform Launchでクエリ文字列パラメーターデータを取得する

データ要素に値を設定することで、クエリ文字列パラメータデータを取得できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し [!UICONTROL Data Elements] 、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. ドロップダウ [!UICONTROL Extension] ンをに、 [!UICONTROL Core]をにに設定し [!UICONTROL Data Element Type] ます [!UICONTROL Query String Parameter]。
5. テキストフィールドにクエリ文字列パラメータを入力します。

クエリ文字列パラメータ値は、データ要素に格納されます。 その後、ルール内のデータ要素を参照して、Analytics変数を割り当てることができます。

## AppMeasurementのs.Util.getQueryParam()とカスタムコードエディターの起動

このメソッド `s.Util.getQueryParam()` を呼び出して、ブラウザーURLからクエリ文字列値を取得します。 クエリ文字列パラメータを含む文字列引数が必要です。 このメソッドは、Analytics変数に割り当て可能な文字列を返します。

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

2つ目のオプションの引数を使用すると、クエリ文字列パラメーターをチェックする文字列を指定できます。 デフォルトでは、このユーティリティはブラウザのURLを参照します。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

3つ目のオプション引数を使用すると、クエリ文字列の区切り文字をカスタマイズできます。 Its default value is `&`. クエリ文字列に別の区切り文字が使用されている場合は、この値を変更できます。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!TIP] 同様のプラグイン名を使用で [`s.getQueryParam`](../plugins/getqueryparam.md) きます。 このプラグインには、より高度な機能が含まれていますが、より複雑な機能で、デフォルトではAppMeasurementに含まれていません。
