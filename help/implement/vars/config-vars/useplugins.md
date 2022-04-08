---
title: usePlugins
description: doPlugins() 関数を有効または無効にします。
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '98'
ht-degree: 100%

---

# usePlugins

`usePlugins` を有効にすると、AppMeasurement がコンパイルして、ヒットがアドビに送信される直前に [`doPlugins()`](../functions/doplugins.md) 関数が実行されます。`doPlugins()` 関数を使用する場合は、この変数を有効にします。

## Adobe Experience Platform のタグを使用したプラグインの使用

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.usePlugins

`s.usePlugins` 変数は、AppMeasurement が `doPlugins()` 関数を呼び出すかどうかを決定するブール値です。デフォルト値は `false` です。実装で `doPlugins()` 関数を使用する場合は、この変数を `true` に設定します。

```js
s.usePlugins = true;
```
