---
title: registerPostTrackCallback
description: アドビにヒットを送信した後に、コールバック関数を作成します。
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 72%

---

# registerPostTrackCallback

`registerPostTrackCallback` 変数を使用すると、ヒットが正常にアドビに送信された直後に実行する JavaScript 関数をフックできます。トラッキングコールが失敗した場合、この関数は実行されません。この変数を使用して、AppMeasurement によって収集されたデータをパートナーや社内インフラストラクチャに送信したり、単一ページのアプリケーションで変数の値をクリーンアップしたりできます。

>[!WARNING]
>
>次のようなトラッキングコールを実行しない [`t()`](t-method.md) または [`tl()`](tl-method.md) 内側 `registerPostTrackCallback` 変数を使用します。 この変数でトラッキングコールを設定すると、イメージリクエストが無限ループに陥ります。

`registerPostTrackCallback` 変数を呼び出すたびに、その関数をフックして、イメージリクエストが正常に送信された直後に実行します。同じページの読み込みで同じ関数を複数回登録しないでください。

>[!NOTE]
>
> [`registerPreTrackCallback`](registerpretrackcallback.md) と `registerPostTrackCallback` の間に呼び出される関数のタイミングと順序は保証されません。この 2 つの関数間の依存関係を避けます。

## Web SDK 拡張機能を使用したトラック後のコールバック

準備中!

## 追跡後のコールバックによる Web SDK の手動実装

データがAdobeに正常に送信された後に、イベントを送信する際に JavaScript Promise を使用して、関数を登録できます。

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

詳しくは、 [イベントからの応答の処理](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#handling-responses-from-events) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したトラック後のコールバックの登録

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.registerPostTrackCallback

`s.registerPostTrackCallback` は、関数を唯一の引数として受け取る関数です。ネストされた関数は、画像リクエストが正常に送信された直後に実行されます。

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

コードでイメージリクエスト URL を使用する場合は、ネストされた関数内で `requestUrl` 文字列引数を参照します。`requestUrl` 変数は、目的の用途に合わせて解析できます。この変数を調整しても、データ収集には影響しません。

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

`s.registerPostTrackCallback` 関数には、次のような追加の引数を含めて、ネストされた関数で使用できます。

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## ユースケース

トラック後のコールバックに [`clearVars()`](clearvars.md) 関数を登録すると、シングルページアプリケーションで役立ちます。ヒットがアドビに正常に送信されるたびに、`clearVars()` 関数が実行されます。その後、誤って値が永続化されるのを気にすることなく、変数を再び定義できます。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
