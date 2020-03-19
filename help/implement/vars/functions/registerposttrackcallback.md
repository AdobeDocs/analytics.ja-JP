---
title: registerPostTrackCallback
description: アドビにヒットを送信した後に、コールバック関数を作成します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# registerPostTrackCallback

この変 `registerPostTrackCallback` 数を使用すると、組織で、ヒットが正常にアドビに送信された直後にJavaScript関数をフックできます。 トラッキングコールが失敗した場合、この関数は実行されません。 この変数を使用して、AppMeasurementによって収集されたデータをパートナーや社内インフラストラクチャに送信したり、単一ページのアプリケーションで変数の値をクリーンアップしたりできます。

> [!IMPORTANT] 変数内などのトラッキングコールを呼び出 [`t()`](t-method.md) さない [`tl()`](tl-method.md) でくだ `registerPostTrackCallback` さい。 この変数で関数をトラッキングすると、イメージリクエストが無限ループします。

変数を呼び出すたびに、 `registerPostTrackCallback` イメージリクエストが正常に送信された直後にその関数が実行されるようにフックします。 同じページの読み込みで同じ関数を複数回登録しないでください。

> [!NOTE] との間に呼び出される関数のタイミングと順 [`registerPreTrackCallback`](registerpretrackcallback.md) 序は保 `registerPostTrackCallback` 証されません。 この2つの関数間の依存関係を避けます。

## Adobe Experience Platform LaunchでのPost Trackコールバックの登録

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.registerPostTrackCallbackとカスタムコードエディターの起動

関数 `s.registerPostTrackCallback` は、関数を唯一の引数として受け取る関数です。 ネストされた関数は、イメージリクエストの送信直前に実行されます。

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

コード内でイメージリクエストURLを使用する場合は、ネストされた関数内で `requestUrl` 文字列引数を参照します。 この変数は、目的の `requestUrl` 用途に合わせて解析できます。この変数を調整しても、データ収集には影響しません。

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

関数には、ネストされた関数で使 `s.registerPostTrackCallback` 用できる追加の引数を含めることができます。

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## 使用例の例

トラック後のコ [`clearVars()`](clearvars.md) ールバックに関数を登録すると、シングルページアプリケーションに役立ちます。 ヒットが正常にアドビに送信されるたびに、関数が `clearVars()` 実行されます。 その後、誤って永続化された値を気にすることなく、変数を再び定義できます。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
