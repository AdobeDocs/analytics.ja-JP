---
title: Util.getQueryParam
description: クエリ文字列パラメーターの値を返します。
feature: Appmeasurement Implementation
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 79%

---

# Util.getQueryParam

ブラウザー URL のクエリ文字列パラメーターには、Analytics の重要なデータが含まれることがよくあります。クエリ文字列からデータを取得するには、`Util.getQueryParam()` メソッドを使用します。

## Adobe Analytics拡張機能と Web SDK拡張機能を使用してクエリ文字列パラメーターデータを取得する

データ要素に値を設定することで、クエリ文字列パラメーターデータを取得できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストを **[!UICONTROL Core]** に設定し、「[!UICONTROL &#x200B; データ要素タイプ &#x200B;]」を **[!UICONTROL クエリ文字列パラメーター]** に設定します。
5. テキストフィールドにクエリ文字列パラメーターを入力します。

クエリ文字列パラメーター値は、データ要素に格納されます。その後、ルールでデータ要素を参照して、必要な変数を割り当てることができます。

## AppMeasurementの s.Util.getQueryParam （）と Analytics 拡張機能のカスタムコードエディター

`s.Util.getQueryParam()` メソッドを呼び出して、ブラウザー URL からクエリ文字列値を取得します。クエリ文字列パラメーターを含む文字列引数が必要です。このメソッドは、Analytics 変数に割り当て可能な文字列を返します。

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

2 つ目のオプションの引数を使用すると、クエリ文字列パラメーターを確認する文字列を指定できます。デフォルトでは、ユーティリティはブラウザーの URL を参照します。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

3 つ目のオプション引数を使用すると、クエリ文字列の区切り文字をカスタマイズできます。デフォルト値は `&` です。クエリ文字列に別の区切り文字が使用されている場合は、この値を変更できます。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
> [`s.getQueryParam`](../plugins/getqueryparam.md) という名前の同様のプラグイン名を利用できます。このプラグインには、より高度な機能が含まれていますが、より複雑で、デフォルトでは AppMeasurement に含まれていません。
