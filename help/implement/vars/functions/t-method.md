---
title: t
description: ページビュートラッキングコールをアドビに送信します。
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 52%

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

`t()` メソッドを実行すると、定義されたすべての Analytics 変数が使用され、これらの変数に基づいて URL が作成されます。一部の Analytics 変数は画像の URL を決定し、他の変数はクエリー文字列パラメーター値を決定します。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

アドビはイメージリクエストを受け取り、リクエストヘッダー、URL およびクエリー文字列パラメーターを解析します。次に、データ収集サーバーは、サイトに不可視的に表示された、1 x 1 ピクセルの透明イメージを返します。

## Web SDK 拡張機能を使用したイベントの送信

アクションを使用して、XDM イベントデータのAdobeへの送信を設定します。 Datastream は、このデータを受け取り、設定されたマッピングを適用し、そのデータがその Datastream に追加されたサービスである場合はAdobe Analyticsに転送します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. の下 [!UICONTROL アクション]、目的のアクションをクリックするか、 **&#39;+&#39;** アイコンをクリックしてアクションを追加します。
1. を [!UICONTROL 拡張] ドロップダウン **[!UICONTROL Adobe Experience Platform Web SDK]** そして [!UICONTROL アクションタイプ] から **[!UICONTROL イベントを送信]**.

## Web SDK を手動で実装するイベントの送信

以下を使用： `sendEvent` コマンドを使用してデータをAdobeに送信します。 Datastream は、このデータを受け取り、設定されたマッピングを適用し、そのデータがその Datastream に追加されたサービスである場合はAdobe Analyticsに転送します。

```js
alloy("sendEvent", {
  "xdm": {}
});
```

詳しくは、 [イベントの追跡](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したページビュートラッキングコール

Adobe Experience Platformデータ収集のAdobe Analytics拡張機能には、ページビュートラッキングコールを設定する専用の場所があります。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. の下 [!UICONTROL アクション]、目的のアクションをクリックするか、 **&#39;+&#39;** アイコンをクリックしてアクションを追加します。
1. を [!UICONTROL 拡張] ドロップダウン **[!UICONTROL Adobe Analytics]**、および [!UICONTROL アクションタイプ] から **[!UICONTROL ビーコンを送信]**.
1. 「`s.t()`」ラジオボタンをクリックします。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.t() メソッド

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
