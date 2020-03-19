---
title: Util.cookieRead
description: cookie の値を取得します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieRead

cookieは、同じドメインの複数のページにわたって情報を保存および取得できます。 このメソッド `Util.cookieRead()` を使用して、cookieから値を取得します。

## Adobe Experience Platform Launchでcookieを読み取る

Cookieを読み取るには、データ要素の値を設定します。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し [!UICONTROL Data Elements] 、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. ドロップダウ [!UICONTROL Extension] ンをに、 [!UICONTROL Core]をにに設定し [!UICONTROL Data Element Type] ます [!UICONTROL Cookie]。
5. テキストフィールドにCookie名を入力します。

cookieの値は、データ要素に格納されます。 その後、ルール内のデータ要素を参照して、Analytics変数を割り当てることができます。

## AppMeasurementのs.Util.cookieRead()とカスタムコードエディターの起動

このメソッドを `s.Util.cookieRead()` 呼び出して、目的のcookie値を読み取ります。 唯一の引数は文字列で、必須です。 このメソッドは、cookie値を含む文字列を返します。 cookieが存在しない場合は、空の文字列が返されます。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
