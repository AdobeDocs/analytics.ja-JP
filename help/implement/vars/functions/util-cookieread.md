---
title: Util.cookieRead
description: cookie の値を取得します。
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 72%

---

# Util.cookieRead

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieRead()` メソッドを使用して Cookie から値を取得します。

## Adobe Analytics拡張機能と Web SDK 拡張機能を使用した Cookie の読み取り

Cookie を読み取るには、データ要素の値を設定します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. を設定します。 [!UICONTROL 拡張] ドロップダウンリスト **[!UICONTROL コア]**、および [!UICONTROL データ要素タイプ] から **[!UICONTROL Cookie]**.
5. テキストフィールドに Cookie 名を入力します。

Cookie の値は、データ要素に格納されます。その後、ルール内のデータ要素を参照して、目的の変数を割り当てることができます。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.Util.cookieRead()

`s.Util.cookieRead()` メソッドを呼び出して、目的の Cookie 値を読み取ります。唯一の引数は文字列で、必須です。このメソッドは、Cookie 値を含む文字列を返します。Cookie が存在しない場合は、空の文字列が返されます。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
