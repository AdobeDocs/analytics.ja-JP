---
title: forceOffline
description: AppMeasurement のオンライン状態を手動で設定します。
feature: Appmeasurement Implementation
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---

# forceOffline

`forceOffline()` メソッドを使用すると、自動的に検出された AppMeasurement の状態を上書きできます。

>[!WARNING]
>
> この関数は、[`trackOffline`](../config-vars/trackoffline.md) が有効な場合にのみ使用します。この関数をオフライントラッキング以外で使用すると、データが失われる可能性があります。

AppMeasurement は、デバイスのオンライン状態を自動的に検出します。`forceOffline()` メソッドを使用すると、AppMeasurement に対して、デバイスがオフラインの場合と同じようにヒットが処理されるように強制できます。このメソッドは引数を取らず、値を返しません。AppMeasurement でオンライン状態を上書きするのが目的です。

## Web SDKを使用してオフラインを強制

Web SDKはオフライントラッキングをサポートしていません。

## Adobe Analytics拡張機能を使用してオフラインを強制

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの s.forceOffline （）と Analytics 拡張機能のカスタムコードエディター

Analytics オブジェクトをインスタンス化した後、実装の任意の場所で `s.forceOffline()` メソッドを呼び出すことができます。

```js
s.forceOffline();
```
