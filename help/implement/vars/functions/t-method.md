---
title: t
description: ページビュートラッキングコールをアドビに送信します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# t()

`t()` メソッドは、Adobe Analytics の重要なコアコンポーネントです。ページで定義されているすべての Analytics 変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをアドビのデータ収集サーバーに送信します。

例えば、次の JavaScript コードを考えてみましょう。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

`t()` メソッドを実行すると、定義されたすべての Analytics 変数が使用され、これらの変数に基づいて URL が作成されます。一部の Analytics 変数は画像の URL を決定し、他の変数はクエリー文字列パラメーター値を決定します。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

アドビはイメージリクエストを受け取り、リクエストヘッダー、URL およびクエリー文字列パラメーターを解析します。次に、データ収集サーバーは、サイトに不可視的に表示された、1 x 1 ピクセルの透明イメージを返します。

## Adobe Experience Platform Launch でのページビュートラッキングコール

Launch には、ページビュートラッキングコールを設定する専用の場所があります。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. 「`s.t()`」ラジオボタンをクリックします。

## AppMeasurement および Launch カスタムコードエディターの s.t() メソッド

アドビにトラッキングコールを送信する場合は、`s.t()` メソッドを呼び出します。

```js
s.t();
```

オプションで、オブジェクトを引数として使用して変数値を上書きできます。詳しくは、[変数のオーバーライド](../../js/overrides.md)を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE] 以前のバージョンの AppMeasurement では、この関数を呼び出すために複数行のコードを使用していました。この追加コードは、従来、異なるブラウザーに対する対処方法を用意していました。最新のブラウザーの標準化とベストプラクティスでは、このコードブロックは不要になりました。現在必要なのは `s.t()` メソッドの呼び出しのみです。
