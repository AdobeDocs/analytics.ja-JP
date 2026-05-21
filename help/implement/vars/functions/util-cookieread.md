---
title: Util.cookieRead
description: cookie の値を取得します。
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
TQID: https://experienceleague.adobe.com/BuAe772j8DToDmAkr46Bg5kEAifNIFso0xQ423xdwxg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 72%

---

# Util.cookieRead

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。 `Util.cookieRead()` メソッドを使用して Cookie から値を取得します。

## Adobe Analytics拡張機能とWeb SDK拡張機能を使用したCookieの読み取り

Cookie を読み取るには、データ要素の値を設定します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. [!UICONTROL 拡張機能] ドロップダウンリストを&#x200B;**[!UICONTROL Core]**&#x200B;に設定し、[!UICONTROL  データ要素タイプ ]を&#x200B;**[!UICONTROL Cookie]**&#x200B;に設定します。
5. テキストフィールドに Cookie 名を入力します。

Cookie の値は、データ要素に格納されます。 その後、ルールのデータ要素を参照して、目的の変数を割り当てることができます。

## AppMeasurementのs.Util.cookieRead （）とAnalytics拡張機能のカスタムコードエディター

`s.Util.cookieRead()` メソッドを呼び出して、目的の Cookie 値を読み取ります。 唯一の引数は文字列で、必須です。 このメソッドは、Cookie 値を含む文字列を返します。 Cookie が存在しない場合は、空の文字列が返されます。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
