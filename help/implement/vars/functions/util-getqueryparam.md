---
title: Util.getQueryParam
description: クエリー文字列パラメーターの値を返します。
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 80%

---

# Util.getQueryParam

ブラウザー URL のクエリー文字列パラメーターには、Analytics の重要なデータが含まれることがよくあります。クエリー文字列からデータを取得するには、`Util.getQueryParam()` メソッドを使用します。

## Adobe Analytics拡張機能と Web SDK 拡張機能を使用したクエリー文字列パラメーターデータの取得

データ要素に値を設定することで、クエリー文字列パラメーターデータを取得できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. を [!UICONTROL 拡張] ドロップダウンリスト **[!UICONTROL コア]**、および [!UICONTROL データ要素タイプ] から **[!UICONTROL クエリー文字列パラメーター]**.
5. テキストフィールドにクエリー文字列パラメーターを入力します。

クエリー文字列パラメーター値は、データ要素に格納されます。その後、ルール内のデータ要素を参照して、目的の変数を割り当てることができます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.Util.getQueryParam()

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

>[!TIP]
>
> [`s.getQueryParam`](../plugins/getqueryparam.md) という名前の同様のプラグイン名を利用できます。このプラグインには、より高度な機能が含まれていますが、より複雑で、デフォルトでは AppMeasurement に含まれていません。
