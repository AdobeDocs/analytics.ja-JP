---
title: Util.getQueryParam
description: クエリー文字列パラメーターの値を返します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Util.getQueryParam

ブラウザー URL のクエリー文字列パラメーターには、Analytics の重要なデータが含まれることがよくあります。クエリー文字列からデータを取得するには、`Util.getQueryParam()` メソッドを使用します。

## Adobe Experience Platform Launch でのクエリー文字列パラメーターデータの取得

データ要素に値を設定することで、クエリー文字列パラメーターデータを取得できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Data Elements] tab, then click the desired data element (or create a data element).
4. ドロップダウ [!UICONTROL Extension] ンをに、 [!UICONTROL Core]をにに設定し [!UICONTROL Data Element Type] ます [!UICONTROL Query String Parameter]。
5. テキストフィールドにクエリー文字列パラメーターを入力します。

クエリー文字列パラメーター値は、データ要素に格納されます。その後、ルール内のデータ要素を参照して、Analytics 変数を割り当てることができます。

## AppMeasurement および Launch カスタムコードエディターの s.Util.getQueryParam()

`s.Util.getQueryParam()` メソッドを呼び出して、ブラウザー URL からクエリー文字列値を取得します。クエリー文字列パラメーターを含む文字列引数が必要です。このメソッドは、Analytics 変数に割り当て可能な文字列を返します。

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

2 つ目のオプションの引数を使用すると、クエリー文字列パラメーターを確認する文字列を指定できます。デフォルトでは、ユーティリティはブラウザーの URL を参照します。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

3 つ目のオプション引数を使用すると、クエリー文字列の区切り文字をカスタマイズできます。デフォルト値は `&` です。クエリー文字列に別の区切り文字が使用されている場合は、この値を変更できます。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP] 同様のプラグイン名を使用で [`s.getQueryParam`](../plugins/getqueryparam.md) きます。 このプラグインには、より高度な機能が含まれていますが、より複雑な機能で、デフォルトではAppMeasurementに含まれていません。
