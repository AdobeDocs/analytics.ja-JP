---
title: t
description: ページビュートラッキングコールをアドビに送信します。
feature: Appmeasurement Implementation
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xDA52lSi35dDd4zgvT3gt1Ufgbc-LTvLL84UEN2dQp8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 469
ht-degree: 55%

---

# t （）

`t()` メソッドは、Adobe Analytics の重要なコアコンポーネントです。 ページで定義されているすべての Analytics 変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをアドビのデータ収集サーバーに送信します。

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

`t()` メソッドを実行すると、定義されたすべての Analytics 変数が使用され、これらの変数に基づいて URL が作成されます。 一部の Analytics 変数は画像の URL を決定し、他の変数はクエリ文字列パラメーター値を決定します。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

アドビはイメージリクエストを受け取り、リクエストヘッダー、URL およびクエリ文字列パラメーターを解析します。 次に、データ収集サーバーは、サイトに不可視的に表示された、1 x 1 ピクセルの透明イメージを返します。

## Web SDK拡張機能を使用したSend event

アクションを使用して、XDM イベントデータをAdobeに送信するように設定します。 データストリームは、このデータを受け取り、設定されたマッピングを適用し、そのデータがそのデータストリームに追加されたサービスである場合、そのデータをAdobe Analyticsに転送します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. [!UICONTROL &#x200B; アクション &#x200B;]で、目的のアクションをクリックするか、**&#39;+&#39;** アイコンをクリックしてアクションを追加します。
1. [!UICONTROL 拡張機能] ドロップダウンリストを&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;に設定し、[!UICONTROL Action Type]を&#x200B;**[!UICONTROL Send event]**&#x200B;に設定します。

## Web SDKを手動で実装するSend event

Adobeにデータを送信するには、`sendEvent` コマンドを使用します。 データストリームは、このデータを受け取り、設定されたマッピングを適用し、そのデータがそのデータストリームに追加されたサービスである場合、そのデータをAdobe Analyticsに転送します。

```js
alloy("sendEvent", {
  "xdm": {}
});
```

詳しくは、Web SDK ドキュメントの[`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview)を参照してください。

## Adobe Analytics拡張機能を使用したページビュートラッキング呼び出し

Adobe Experience Platform Data CollectionのAdobe Analytics拡張機能には、ページビュートラッキング呼び出しを設定する専用の場所があります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. [!UICONTROL &#x200B; アクション &#x200B;]で、目的のアクションをクリックするか、**&#39;+&#39;** アイコンをクリックしてアクションを追加します。
1. [!UICONTROL 拡張機能] ドロップダウンリストを&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;に設定し、[!UICONTROL &#x200B; アクションタイプ &#x200B;]を&#x200B;**[!UICONTROL ビーコンを送信]**&#x200B;に設定します。
1. 「`s.t()`」ラジオボタンをクリックします。

## AppMeasurementのs.t （） メソッドとAnalytics拡張機能のカスタムコードエディター

アドビにトラッキングコールを送信する場合は、`s.t()` メソッドを呼び出します。

```js
s.t();
```

オプションで、オブジェクトを引数として使用して変数値を上書きできます。 詳しくは、[変数のオーバーライド](../../js/overrides.md)を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>以前のバージョンの AppMeasurement では、この関数を呼び出すために複数行のコードを使用していました。 この追加コードは、従来、異なるブラウザーに対する対処方法を用意していました。 最新のブラウザーの標準化とベストプラクティスでは、このコードブロックは不要になりました。 現在必要なのは `s.t()` メソッドの呼び出しのみです。
