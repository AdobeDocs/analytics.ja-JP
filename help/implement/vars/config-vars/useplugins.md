---
title: usePlugins
description: doPlugins() 関数を有効または無効にします。
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 41154580c272514e504c5478215bb67795488de3
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 33%

---

# usePlugins

`usePlugins` を有効にすると、AppMeasurement がコンパイルして、ヒットがアドビに送信される直前に [`doPlugins()`](../functions/doplugins.md) 関数が実行されます。`doPlugins()` 関数を使用する場合は、この変数を有効にします。

## 以下を使用： `onBeforeEventSend` Web SDK を使用したコールバック

Web SDK には、データがAdobeに送信される前の追加ロジックの実行を処理するブール値はありませんが、 `onBeforeEventSend` データを変更するコールバック。 詳しくは、 [イベントのグローバルな変更](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したプラグインの使用

Adobeには、「Common Analytics Plugins」というラベルの付いた拡張機能が用意されており、これを使用するとほとんどの [プラグイン](../plugins/impl-plugins.md). 拡張機能をインストールし、ルール内で目的のプラグインを呼び出します。

目的のプラグインがAdobe拡張機能に含まれていない場合は、AppMeasurement 構文に従ったカスタムコードエディターを使用します。

## AppMeasurement の s.usePlugins と Analytics 拡張機能のカスタムコードエディター

`s.usePlugins` 変数は、AppMeasurement が `doPlugins()` 関数を呼び出すかどうかを決定するブール値です。デフォルト値は `false` です。実装で `doPlugins()` 関数を使用する場合は、この変数を `true` に設定します。

```js
s.usePlugins = true;
```
