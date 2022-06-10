---
title: forceOffline
description: AppMeasurement のオンライン状態を手動で設定します。
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 70%

---

# forceOffline

`forceOffline()` メソッドを使用すると、自動的に検出された AppMeasurement の状態を上書きできます。

>[!WARNING]
>
> この関数は、[`trackOffline`](../config-vars/trackoffline.md) が有効な場合にのみ使用します。この関数をオフライントラッキング以外で使用すると、データが失われる可能性があります。

AppMeasurement は、デバイスのオンライン状態を自動的に検出します。`forceOffline()` メソッドを使用すると、AppMeasurement に対して、デバイスがオフラインの場合と同じようにヒットが処理されるように強制できます。このメソッドは引数を取らず、値を返しません。AppMeasurement でオンライン状態を上書きするのが目的です。

## Web SDK を使用してオフラインを強制

Web SDK は、オフライン追跡をサポートしていません。

## Adobe Analytics拡張機能を使用してオフラインを強制

Adobe Analytics拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.forceOffline()

Analytics オブジェクトをインスタンス化した後、実装の任意の場所で `s.forceOffline()` メソッドを呼び出すことができます。

```js
s.forceOffline();
```
