---
title: t
description: ページビュートラッキングコールをアドビに送信します。
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: e47bee837faf9b8cf080d878da860795ced014d5
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 56%

---

# t()

`t()` メソッドは、Adobe Analytics の重要なコアコンポーネントです。ページで定義されているすべての Analytics 変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをアドビのデータ収集サーバーに送信します。

例えば、次の JavaScript コードを考えてみましょう。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

`t()` メソッドを実行すると、定義されたすべての Analytics 変数が使用され、これらの変数に基づいて URL が作成されます。一部の Analytics 変数は画像の URL を決定し、他の変数はクエリ文字列パラメーター値を決定します。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

アドビはイメージリクエストを受け取り、リクエストヘッダー、URL およびクエリ文字列パラメーターを解析します。次に、データ収集サーバーは、サイトに不可視的に表示された、1 x 1 ピクセルの透明イメージを返します。

## Web SDK 拡張機能を使用したイベントの送信

アクションを使用して、XDM イベントデータのAdobeへの送信を設定します。 データストリームは、このデータを受け取り、設定されたマッピングを適用し、そのデータストリームに追加されたサービスである場合は、そのデータをAdobe Analyticsに転送します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. [!UICONTROL &#x200B; アクション &#x200B;] で、目的のアクションをクリックするか、「**+」** イコンをクリックしてアクションを追加します。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストを **[!UICONTROL Adobe Experience Platform Web SDK]** に設定し、「[!UICONTROL &#x200B; アクションタイプ &#x200B;] を **[!UICONTROL イベントを送信]** に設定します。

## Web SDK を手動で実装してイベントを送信

`sendEvent` コマンドを使用して、データをAdobeに送信します。 データストリームは、このデータを受け取り、設定されたマッピングを適用し、そのデータストリームに追加されたサービスである場合は、そのデータをAdobe Analyticsに転送します。

```js
alloy("sendEvent", {
  "xdm": {}
});
```

詳しくは、Web SDK ドキュメントの [ イベントの追跡 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja) を参照してください。

## Adobe Analytics拡張機能を使用したページビュートラッキングコール

Adobe Experience Platform Data Collection のAdobe Analytics拡張機能には、ページビュートラッキング呼び出しを設定する専用の場所があります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. [!UICONTROL &#x200B; アクション &#x200B;] で、目的のアクションをクリックするか、「**+」** イコンをクリックしてアクションを追加します。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストを **[!UICONTROL Adobe Analytics]** に、「[!UICONTROL &#x200B; アクションタイプ &#x200B;] を **[!UICONTROL ビーコンを送信]** に設定します。
1. 「`s.t()`」ラジオボタンをクリックします。

## AppMeasurementの s.t （） メソッドと Analytics 拡張機能のカスタムコードエディター

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

>[!NOTE]
>
> 以前のバージョンの AppMeasurement では、この関数を呼び出すために複数行のコードを使用していました。この追加コードは、従来、異なるブラウザーに対する対処方法を用意していました。最新のブラウザーの標準化とベストプラクティスでは、このコードブロックは不要になりました。現在必要なのは `s.t()` メソッドの呼び出しのみです。
