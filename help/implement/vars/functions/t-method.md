---
title: t
description: ページビュートラッキングコールをアドビに送信します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# t()

この方 `t()` 法は、Adobe Analyticsの重要なコアコンポーネントです。 ページで定義されたすべてのAnalytics変数を取得し、それらをイメージリクエストにコンパイルし、そのデータをAdobeデータ収集サーバーに送信します。

例えば、次のJavaScriptコードを考えてみましょう。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

このメソッドを実 `t()` 行すると、定義されたすべてのAnalytics変数が使用され、これらの変数に基づいてURLが作成されます。 一部のAnalytics変数は画像のURLを決定し、他の変数はクエリ文字列パラメーターの値を決定します。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

アドビはイメージリクエストを受け取り、リクエストヘッダー、URLおよびクエリ文字列パラメーターを解析します。 次に、データ収集サーバーは、サイトに表示されない透過的な1 x 1ピクセルの画像を返します。

## Adobe Experience Platform Launchのページビュートラッキングコール

「起動」には、ページビュートラッキングコールを設定する専用の場所があります。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. 下の「 [!UICONTROL Actions]+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、「ビーコンの送 [!UICONTROL Action Type] 信」に設定します。
6. Click the `s.t()` radio button.

## s.t()メソッド（AppMeasurementおよびカスタムコードエディターの起動）

アドビにトラ `s.t()` ッキングコールを送信する場合は、このメソッドを呼び出します。

```js
s.t();
```

オプションで、変数の値を上書きする引数としてオブジェクトを使用できます。 詳しくは [、変数の上書き](../../js/overrides.md) を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] 以前のバージョンのAppMeasurementでは、この関数を呼び出すために複数行のコードを使用していました。 この追加コードは、異なるブラウザーの回避策を従来どおり取り入れていました。 最新のブラウザーでの標準化とベストプラクティスでは、このコードブロックは不要になりました。 メソッド呼び出しのみが `s.t()` 必要になりました。
