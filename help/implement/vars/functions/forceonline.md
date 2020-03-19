---
title: forceOnline
description: AppMeasurementのオンライン状態を手動で設定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOnline

このメソ `forceOnline()` ッドを使用すると、自動的に検出されたAppMeasurementの状態を上書きできます。

> [!IMPORTANT] このメソッドは、が有効な場合にの [`trackOffline`](../config-vars/trackoffline.md) み使用します。 この関数をオフライン追跡の外部で使用すると、データが失われる可能性があります。

AppMeasurementは、デバイスのオンライン状態を自動的に検出します。 この方法を使用すると、AppMeasurement `forceOnline()` で、デバイスがオンラインであるかのようにヒットを処理するように強制できます。 このメソッドは引数を取らず、値を返しません。 AppMeasurementでオンライン状態を上書きする目的のみです。

## Adobe Experience Platform LaunchでForce Online

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.forceOnline()およびカスタムコードエディターの起動

このメソッドは、Analyticsオブジ `s.forceOnline()` ェクトをインスタンス化した後、実装の任意の場所で呼び出すことができます。

```js
s.forceOnline();
```
