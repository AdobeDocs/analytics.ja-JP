---
title: Util.getQueryParam
description: クエリ文字列パラメーターの値を返します。
feature: Appmeasurement Implementation
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/99nBiI23QwY6J6qEVKKz901Bertmkxf21YeJdKTmWbo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 79%

---

# Util.getQueryParam

ブラウザー URL のクエリ文字列パラメーターには、Analytics の重要なデータが含まれることがよくあります。 クエリ文字列からデータを取得するには、`Util.getQueryParam()` メソッドを使用します。

## Adobe Analytics拡張機能とWeb SDK拡張機能を使用したクエリ文字列パラメーターデータの取得

データ要素に値を設定することで、クエリ文字列パラメーターデータを取得できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. [!UICONTROL 拡張機能] ドロップダウンリストを&#x200B;**[!UICONTROL Core]**&#x200B;に設定し、[!UICONTROL &#x200B; データ要素タイプ &#x200B;]を&#x200B;**[!UICONTROL クエリ文字列パラメーター]**&#x200B;に設定します。
5. テキストフィールドにクエリ文字列パラメーターを入力します。

クエリ文字列パラメーター値は、データ要素に格納されます。 その後、ルールのデータ要素を参照して、目的の変数を割り当てることができます。

## AppMeasurementのs.Util.getQueryParam （）とAnalytics拡張機能のカスタムコードエディター

`s.Util.getQueryParam()` メソッドを呼び出して、ブラウザー URL からクエリ文字列値を取得します。 クエリ文字列パラメーターを含む文字列引数が必要です。 このメソッドは、Analytics 変数に割り当て可能な文字列を返します。

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

2 つ目のオプションの引数を使用すると、クエリ文字列パラメーターを確認する文字列を指定できます。 デフォルトでは、ユーティリティはブラウザーの URL を参照します。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

3 つ目のオプション引数を使用すると、クエリ文字列の区切り文字をカスタマイズできます。 デフォルト値は `&` です。 クエリ文字列に別の区切り文字が使用されている場合は、この値を変更できます。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>[`s.getQueryParam`](../plugins/getqueryparam.md) という名前の同様のプラグイン名を利用できます。 このプラグインには、より高度な機能が含まれていますが、より複雑で、デフォルトでは AppMeasurement に含まれていません。
