---
title: forceOnline
description: AppMeasurement のオンライン状態を手動で設定します。
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '141'
ht-degree: 100%

---

# forceOnline

`forceOnline()` メソッドを使用すると、自動的に検出された AppMeasurement の状態を上書きできます。

>[!IMPORTANT]
>
> このメソッドは、[`trackOffline`](../config-vars/trackoffline.md) が有効な場合にのみ使用します。この関数をオフライントラッキング以外で使用すると、データが失われる可能性があります。

AppMeasurement は、デバイスのオンライン状態を自動的に検出します。`forceOnline()` メソッドを使用すると、AppMeasurement がデバイスがオンラインの場合と同様にヒットを処理するように強制できます。このメソッドは引数を取らず、値を返しません。AppMeasurement でオンライン状態を上書きするのが目的です。

## Adobe Experience Platform のタグを使用したオンラインの強制

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.forceOnline()

Analytics オブジェクトをインスタンス化した後、実装の任意の場所で `s.forceOnline()` メソッドを呼び出すことができます。

```js
s.forceOnline();
```
