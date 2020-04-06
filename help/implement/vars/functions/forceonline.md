---
title: forceOnline
description: AppMeasurement のオンライン状態を手動で設定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# forceOnline

`forceOnline()` メソッドを使用すると、自動的に検出された AppMeasurement の状態を上書きできます。

>[!IMPORTANT] このメソッドは、が有効な場合にの [`trackOffline`](../config-vars/trackoffline.md) み使用します。 この関数をオフライントラッキング以外で使用すると、データが失われる可能性があります。

AppMeasurement は、デバイスのオンライン状態を自動的に検出します。`forceOnline()` メソッドを使用すると、AppMeasurement がデバイスがオンラインの場合と同様にヒットを処理するように強制できます。このメソッドは引数を取らず、値を返しません。AppMeasurement でオンライン状態を上書きするのが目的です。

## Adobe Experience Platform Launch でのオンライン強制

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.forceOnline()

Analytics オブジェクトをインスタンス化した後、実装の任意の場所で `s.forceOnline()` メソッドを呼び出すことができます。

```js
s.forceOnline();
```
