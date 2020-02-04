---
title: Util.getQueryParam
description: クエリ文字列パラメータの値を返します。
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Util.getQueryParam

ブラウザーURLのクエリ文字列パラメーターには、Analyticsの重要なデータが含まれることがよくあります。 クエリ文字列 `Util.getQueryParam` からデータを取得するには、このメソッドを使用します。

## Adobe Experience Platform Launchでクエリ文字列パラメーターデータを取得する

データ要素に値を設定することで、クエリ文字列パラメーターデータを取得できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「データ要素 [!UICONTROL 」タブに移動し] 、目的のデータ要素をクリックします（またはデータ要素を作成します）。
4. 「拡張」ドロップダ [!UICONTROL ウンを「] Core [!UICONTROL 」に設定し、「]Data Element Type [!UICONTROL 」を「]String String Parameter Parameter」に設定します。
5. テキストフィールドにクエリ文字列パラメータを入力します。

クエリ文字列パラメーター値は、データ要素に格納されます。 その後、ルール内のデータ要素を参照して、Analytics変数を割り当てることができます。

## AppMeasurementのs.Util.getQueryParam()とカスタムコードエディターの起動

このメソッド `s.Util.getQueryParam()` を呼び出して、ブラウザーURLからクエリ文字列値を取得します。 クエリ文字列パラメータを含む文字列引数が必要です。 このメソッドは、Analytics変数に割り当て可能な文字列を返します。

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

2つ目のオプションの引数を使用すると、クエリ文字列パラメーターを確認する文字列を指定できます。 デフォルトでは、ユーティリティはブラウザのURLを参照します。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

3つ目のオプション引数を使用すると、クエリ文字列の区切り文字をカスタマイズできます。 Its default value is `&`. クエリ文字列に別の区切り文字が使用されている場合は、この値を変更できます。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!NOTE] 以前のバージョンのAppMeasurementには、「available」という名前のプラグインがあ `s.getQueryParam` りました。 このプラグインは、AppMeasurementにデフォルトで含まれるようになったので、不要になりました。
