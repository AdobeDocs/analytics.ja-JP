---
title: Util.cookieRead
description: cookie の値を取得します。
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '167'
ht-degree: 100%

---

# Util.cookieRead

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieRead()` メソッドを使用して Cookie から値を取得します。

## Adobe Experience Platform Launch での Cookie の読み取り

Cookie を読み取るには、データ要素の値を設定します。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL データ要素]」タブに移動し、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. 「[!UICONTROL 拡張機能]」ドロップダウンを「[!UICONTROL コア]」に設定し、「[!UICONTROL データ要素タイプ]」を「[!UICONTROL Cookie]」に設定します。
5. テキストフィールドに Cookie 名を入力します。

Cookie の値は、データ要素に格納されます。その後、ルール内のデータ要素を参照して、Analytics 変数を割り当てることができます。

## AppMeasurement および Launch カスタムコードエディターの s.Util.cookieRead()

`s.Util.cookieRead()` メソッドを呼び出して、目的の Cookie 値を読み取ります。唯一の引数は文字列で、必須です。このメソッドは、Cookie 値を含む文字列を返します。Cookie が存在しない場合は、空の文字列が返されます。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
