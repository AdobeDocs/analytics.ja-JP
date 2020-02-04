---
title: forceOnline
description: AppMeasurementのオンライン状態を手動で設定します。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# forceOnline

このメソ `forceOnline` ッドを使用すると、自動的に検出されたAppMeasurementの状態を上書きできます。

> [!IMPORTANT] この関数は、が有効な場合にのみ `trackOffline` 使用します。 この関数をオフライン追跡以外で使用すると、データが失われる可能性があります。

AppMeasurementは、デバイスのオンライン状態を自動的に検出します。 この方法を使用すると、AppMeasurement `forceOnline` に対して、デバイスがオンラインの場合と同様にヒットが処理されるように強制できます。 このメソッドは引数を取らず、値を返しません。 AppMeasurementでオンライン状態を上書きするのが目的です。

## Adobe Experience Platform LaunchでForce Online

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.forceOnline()およびカスタムコードエディターの起動

Analyticsオブジェクトをインスタ `s.forceOnline()` ンス化した後、実装の任意の場所でこのメソッドを呼び出すことができます。

```js
s.forceOnline();
```
