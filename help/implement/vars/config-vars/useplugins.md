---
title: usePlugins
description: doPlugins()関数を有効または無効にします。
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# usePlugins

を有効 `usePlugins` にすると、AppMeasurement `doPlugins()` がコンパイルされ、ヒットがアドビに送信される直前に関数が実行されます。 関数を使用する場合は、この変数を有効にし `doPlugins()` ます。

## Adobe Experience Platform Launchでのプラグインの使用

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.usePluginsとカスタムコードエディターの起動

この変 `s.usePlugins` 数は、AppMeasurementが関数を呼び出すかどうかを決定するブール値 `doPlugins()` です。 Its default value is `false`. 実装で関数を使 `true` 用する場合は、この変 `doPlugins()` 数をに設定します。

```js
s.usePlugins = true;
```
