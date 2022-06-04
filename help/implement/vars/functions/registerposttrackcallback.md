---
title: registerPostTrackCallback
description: アドビにヒットを送信した後に、コールバック関数を作成します。
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# registerPostTrackCallback

`registerPostTrackCallback` 変数を使用すると、ヒットが正常にアドビに送信された直後に実行する JavaScript 関数をフックできます。トラッキングコールが失敗した場合、この関数は実行されません。この変数を使用して、AppMeasurement によって収集されたデータをパートナーや社内インフラストラクチャに送信したり、単一ページのアプリケーションで変数の値をクリーンアップしたりできます。

>[!WARNING]
>
> [`t()`](t-method.md) や [`tl()`](tl-method.md) などのトラッキングコールは `registerPostTrackCallback` 変数内で呼び出さないでください。この変数で関数をトラッキングすると、イメージリクエストが無限ループになります。

`registerPostTrackCallback` 変数を呼び出すたびに、その関数をフックして、イメージリクエストが正常に送信された直後に実行します。同じページの読み込みで同じ関数を複数回登録しないでください。

>[!NOTE]
>
> [`registerPreTrackCallback`](registerpretrackcallback.md) と `registerPostTrackCallback` の間に呼び出される関数のタイミングと順序は保証されません。この 2 つの関数間の依存関係を避けます。

## Adobe Experience Platform のタグを使用したトラック後コールバックの登録

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.registerPostTrackCallback

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

## ユースケースの例

トラック後のコールバックに [`clearVars()`](clearvars.md) 関数を登録すると、シングルページアプリケーションで役立ちます。ヒットがアドビに正常に送信されるたびに、`clearVars()` 関数が実行されます。その後、誤って値が永続化されるのを気にすることなく、変数を再び定義できます。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
