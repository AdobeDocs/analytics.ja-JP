---
title: usePlugins
description: doPlugins() 関数を有効または無効にします。
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7ofbF5EloAUlvCmGv-CaTFxxZELX0wydJ8HzmU2f6EQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 32%

---

# usePlugins

`usePlugins` を有効にすると、AppMeasurement がコンパイルして、ヒットがアドビに送信される直前に [`doPlugins()`](../functions/doplugins.md) 関数が実行されます。 `doPlugins()` 関数を使用する場合は、この変数を有効にします。

## Web SDKを使用した`onBeforeEventSend` コールバックの使用

Web SDKには、データがAdobeに送信される前に追加のロジックの実行を処理するブール値はありませんが、`onBeforeEventSend` コールバックを登録してデータを変更できます。 詳しくは、Web SDK ドキュメントの「[&#x200B; グローバルにイベントを変更する](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja#modifying-events-globally)」を参照してください。

## Adobe Analytics拡張機能を使用したプラグインの使用

Adobeには、「Common Analytics Plugins」というラベルの付いた拡張機能が用意されており、ほとんどの[Plug-ins](../plugins/impl-plugins.md)を呼び出すことができます。 拡張機能をインストールし、ルール内で目的のプラグインを呼び出します。

目的のプラグインがAdobe拡張機能に含まれていない場合は、AppMeasurementの構文に従ってカスタムコードエディターを使用します。

## AppMeasurementのs.usePluginsとAnalytics拡張機能のカスタムコードエディター

`s.usePlugins` 変数は、AppMeasurement が `doPlugins()` 関数を呼び出すかどうかを決定するブール値です。 デフォルト値は `false` です。 実装で `doPlugins()` 関数を使用する場合は、この変数を `true` に設定します。

```js
s.usePlugins = true;
```
