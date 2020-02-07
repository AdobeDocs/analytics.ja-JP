---
title: t
description: ページビュートラッキングコールをアドビに送信します。
translation-type: tm+mt
source-git-commit: 8494e8bb08b45006b357dd114e6bf9507f0cd54a

---


# t

この方 `t` 法は、Adobe Analyticsの重要なコアコンポーネントです。 ページで定義されているすべてのAnalytics変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをAdobeデータ収集サーバーに送信します。

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

このメソッドを実 `t` 行すると、定義されたすべてのAnalytics変数が使用され、これらの変数に基づいてURLが作成されます。 一部のAnalytics変数は画像のURLを決定し、他の変数はクエリ文字列パラメーター値を決定します。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

アドビはイメージリクエストを受け取り、リクエストヘッダー、URLおよびクエリ文字列パラメーターを解析します。 次に、データ収集サーバーは、サイトに不可視的に表示された、1 x 1ピクセルの透過イメージを返します。

## Adobe Experience Platform Launchのページビュートラッキングコール

「起動」には、ページビュートラッキングコールを設定する専用の場所があります。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で「+」アイコンをクリックします
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクションタイプ [!UICONTROL 」を「送信ビーコン] 」に設定します。
6. Click the `s.t()` radio button.

## s.t()メソッド（AppMeasurementおよびカスタムコードエディターの起動）

アドビにトラ `s.t()` ッキングコールを送信する場合は、このメソッドを呼び出します。

```js
s.t();
```

オプションで、オブジェクトを引数として使用して変数値を上書きできます。 詳しくは [、変数のオーバーライド](../../js/overrides.md) を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] 以前のバージョンのAppMeasurementでは、この関数を呼び出すために複数行のコードを使用していました。 この追加コードは、異なるブラウザーに対する対処方法を従来どおり用意していました。 最新のブラウザーでの標準化とベストプラクティスでは、このコードブロックは不要になりました。 メソッド呼び出しのみ `s.t()` が必要になりました。
