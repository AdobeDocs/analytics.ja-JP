---
title: Util.cookieRead
description: cookie の値を取得します。
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 73%

---

# Util.cookieRead

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieRead()` メソッドを使用して Cookie から値を取得します。

## Adobe Analytics拡張機能と Web SDK 拡張機能を使用した Cookie の読み取り

Cookie を読み取るには、データ要素の値を設定します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. 「[!UICONTROL 拡張機能]」ドロップダウンを「**[!UICONTROL コア]**」に設定し、「[!UICONTROL データ要素タイプ]」を「**[!UICONTROL Cookie]**」に設定します。
5. テキストフィールドに Cookie 名を入力します。

Cookie の値は、データ要素に格納されます。その後、ルール内のデータ要素を参照して、目的の変数を割り当てることができます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.Util.cookieRead()

`s.Util.cookieRead()` メソッドを呼び出して、目的の Cookie 値を読み取ります。唯一の引数は文字列で、必須です。このメソッドは、Cookie 値を含む文字列を返します。Cookie が存在しない場合は、空の文字列が返されます。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
