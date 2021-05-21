---
title: registerPreTrackCallback
description: アドビにヒットを送信する前に実行するコールバック関数を作成します。
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '262'
ht-degree: 100%

---

# registerPreTrackCallback

`registerPreTrackCallback` 変数を使用すると、イメージリクエスト URL がコンパイルされたがまだ送信されていないときに実行する JavaScript 関数をフックできます。この変数を使用して、AppMeasurement によって収集されたデータをパートナーまたは社内インフラストラクチャに送信できます。

>[!IMPORTANT]
>
> [`t()`](t-method.md) や [`tl()`](tl-method.md) などのトラッキングコールは [`registerPostTrackCallback`](registerposttrackcallback.md) 変数内で呼び出さないでください。この変数で関数をトラッキングすると、イメージリクエストが無限ループになります。

`registerPreTrackCallback` 変数を呼び出すたびに、その関数をフックして、イメージリクエスト URL がコンパイルされるたびに実行します。同じページの読み込みで同じ関数を複数回登録しないでください。

>[!NOTE]
>
> `registerPreTrackCallback` と `registerPostTrackCallback` の間に呼び出される関数のタイミングと順序は保証されません。この 2 つの関数間の依存関係を避けます。

## Adobe Experience Platform Launch でのトラック前コールバックの登録

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.registerPreTrackCallback

`s.registerPreTrackCallback` は、関数を唯一の引数として受け取る関数です。ネストされた関数は、イメージリクエストの送信直前に実行されます。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

コードでイメージリクエスト URL を使用する場合は、ネストされた関数内で `requestUrl` 文字列引数を参照します。`requestUrl` 変数は、目的の用途に合わせて解析できます。この変数を調整しても、データ収集には影響しません。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

`s.registerPreTrackCallback` 関数には、ネストされた関数で使用できる、追加の引数を含めることができます。

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
> ページ変数の設定やこの関数内の `requestUrl` 文字列の変更は、この関数呼び出しの直後に送信されるイメージリクエストには影響&#x200B;**しません**。代わりに、[`doPlugins()`](doplugins.md) 変数を使用します。
