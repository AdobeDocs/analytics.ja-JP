---
title: usePlugins
description: doPlugins() 関数を有効または無効にします。
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

`usePlugins` を有効にすると、AppMeasurement がコンパイルして、ヒットがアドビに送信される直前に [`doPlugins()`](../functions/doplugins.md) 関数が実行されます。`doPlugins()` 関数を使用する場合は、この変数を有効にします。

## Web SDKを使用した `onBeforeEventSend` コールバックの使用

Web SDKには、データがAdobeに送信される前に追加のロジックの実行を処理するブール値がありませんが、`onBeforeEventSend` コールバックを登録してデータを変更できます。 詳しくは、Web SDK ドキュメントの [ イベントのグローバルな変更 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) を参照してください。

## Adobe Analytics拡張機能を使用したプラグインの使用

Adobeには、「Common Analytics Plugins」というラベルの付いた拡張機能が用意されており、ほとんどの [ プラグイン ](../plugins/impl-plugins.md) を呼び出すことができます。 拡張機能をインストールし、ルール内で目的のプラグインを呼び出します。

目的のプラグインがAdobe拡張機能に含まれていない場合は、AppMeasurement構文に従ってカスタムコードエディターを使用します。

## AppMeasurementの s.usePlugins と Analytics 拡張機能のカスタムコードエディター

`s.usePlugins` 変数は、AppMeasurement が `doPlugins()` 関数を呼び出すかどうかを決定するブール値です。デフォルト値は `false` です。実装で `doPlugins()` 関数を使用する場合は、この変数を `true` に設定します。

```js
s.usePlugins = true;
```
