---
title: forceOffline
description: AppMeasurementのオンライン状態を手動で設定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOffline

このメソ `forceOffline()` ッドを使用すると、自動的に検出されたAppMeasurementの状態を上書きできます。

> [!IMPORTANT] この関数は、が有効な場合にのみ [`trackOffline`](../config-vars/trackoffline.md) 使用します。 この関数をオフライン追跡の外部で使用すると、データが失われる可能性があります。

AppMeasurementは、デバイスのオンライン状態を自動的に検出します。 このメソッドを使用すると、AppMeasurement `forceOffline()` で、デバイスがオフラインの場合と同じようにヒットが処理されるように強制できます。 このメソッドは引数を取らず、値を返しません。 AppMeasurementでオンライン状態を上書きする目的のみです。

## Adobe Experience Platform Launchでオフラインを強制

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.forceOffline()とカスタムコードエディターの起動

このメソッドは、Analyticsオブジ `s.forceOffline()` ェクトをインスタンス化した後、実装の任意の場所で呼び出すことができます。

```js
s.forceOffline();
```
