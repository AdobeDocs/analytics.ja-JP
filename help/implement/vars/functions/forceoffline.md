---
title: forceOffline
description: AppMeasurement のオンライン状態を手動で設定します。
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '141'
ht-degree: 100%

---

# forceOffline

`forceOffline()` メソッドを使用すると、自動的に検出された AppMeasurement の状態を上書きできます。

>[!IMPORTANT]
>
> この関数は、[`trackOffline`](../config-vars/trackoffline.md) が有効な場合にのみ使用します。この関数をオフライントラッキング以外で使用すると、データが失われる可能性があります。

AppMeasurement は、デバイスのオンライン状態を自動的に検出します。`forceOffline()` メソッドを使用すると、AppMeasurement に対して、デバイスがオフラインの場合と同じようにヒットが処理されるように強制できます。このメソッドは引数を取らず、値を返しません。AppMeasurement でオンライン状態を上書きするのが目的です。

## Adobe Experience Platform のタグを使用したオフラインの強制

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.forceOffline()

Analytics オブジェクトをインスタンス化した後、実装の任意の場所で `s.forceOffline()` メソッドを呼び出すことができます。

```js
s.forceOffline();
```
