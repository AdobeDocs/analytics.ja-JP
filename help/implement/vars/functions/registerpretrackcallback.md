---
title: registerPreTrackCallback
description: アドビにヒットを送信する前に、コールバック関数を作成します。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPreTrackCallback

この変 `registerPreTrackCallback` 数を使用すると、イメージリクエストURLがコンパイルされた後、送信される前に、JavaScript関数をフックできます。 この変数を使用して、AppMeasurementによって収集されたデータをパートナーまたは社内インフラストラクチャに送信できます。

> [!IMPORTANT] 変数内などのトラッキング関数は呼び出 `t` さな `tl` いでく `registerPostTrackCallback` ださい。 この変数で関数をトラッキングすると、イメージリクエストが無限ループになります。

変数を呼び出すたびに、 `registerPreTrackCallback` その関数をフックして、イメージリクエストURLがコンパイルされるたびに実行します。 同じページの読み込みで同じ関数を複数回登録しないでください。

> [!NOTE] との間に呼び出される関数のタイミングと順序 `registerPreTrackCallback` は保証 `registerPostTrackCallback` されません。 この2つの関数間の依存関係を避けます。

## Adobe Experience Platform LaunchでのPre Trackコールバックの登録

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.registerPreTrackCallbackとカスタムコードエディターの起動

関数 `s.registerPreTrackCallback` は、関数を唯一の引数として受け取る関数です。 ネストされた関数は、イメージリクエストの送信直前に実行されます。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

コードでイメージリクエストURLを使用する場合は、ネストされた関数内で `requestUrl` 文字列引数を参照します。 この変数は、目的の `requestUrl` 用途に合わせて解析できます。この変数を調整しても、データ収集には影響しません。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

この関数には、次のような追加の引数を `s.registerPreTrackCallback` 含めることができます。この引数は、ネストされた関数で使用できます。

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] ページ変数の設定やこの関数内の文字 `requestUrl` 列の変更は、この関数呼び出し *の直後* に送信されるイメージリクエストには影響しません。
