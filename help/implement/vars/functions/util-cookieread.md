---
title: Util.cookieRead
description: cookie の値を取得します。
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 72%

---

# Util.cookieRead

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieRead()` メソッドを使用して Cookie から値を取得します。

## Adobe Analytics拡張機能と Web SDK拡張機能を使用して cookie を読み取る

Cookie を読み取るには、データ要素の値を設定します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. 「[!UICONTROL  拡張機能 ]」ドロップダウンリストを **[!UICONTROL Core]** に設定し、「[!UICONTROL  データ要素タイプ ] を **[!UICONTROL Cookie]** に設定します。
5. テキストフィールドに Cookie 名を入力します。

Cookie の値は、データ要素に格納されます。その後、ルールでデータ要素を参照して、必要な変数を割り当てることができます。

## AppMeasurementの s.Util.cookieRead （）と Analytics 拡張機能のカスタムコードエディター

`s.Util.cookieRead()` メソッドを呼び出して、目的の Cookie 値を読み取ります。唯一の引数は文字列で、必須です。このメソッドは、Cookie 値を含む文字列を返します。Cookie が存在しない場合は、空の文字列が返されます。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
