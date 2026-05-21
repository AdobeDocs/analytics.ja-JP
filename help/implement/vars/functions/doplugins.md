---
title: doPlugins
description: ヒットがコンパイルされてアドビに送信される直前にロジックを設定します。
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
TQID: https://experienceleague.adobe.com/T-AyesoP2IMk3J-ftdnR-o48HqTmoRsAYtaIgn9cc1Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 326
ht-degree: 61%

---

# doPlugins

`doPlugins` 変数は、実装に値を設定する「最後の呼び出し」として機能します。 イメージリクエストが送信される前に、[ プラグインメソッド ](../plugins/impl-plugins.md)を呼び出し、必要な変数を設定するのに最適な場所です。 [`usePlugins`](../config-vars/useplugins.md) が有効になっている場合は、次のようなイメージリクエストがコンパイルされてアドビに送信される直前に自動的に実行されます。

* すべてのページビュー（[`t()`](t-method.md)）コール
* 自動ダウンロードリンクと離脱リンクを含む、すべてのリンクトラッキング（[`tl()`](tl-method.md)）コール

`doPlugins` 変数を使用してプラグインコードを呼び出し、イメージリクエストがコンパイルされてアドビに送信される直前に、最終的な変数値を設定します。

## Web SDK拡張機能を使用したOn Before Event Send コールバックコードの使用

Web SDKでは、`doPlugins`の代わりに、同様の機能を持つ`onBeforeEventSend`を使用します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. [!UICONTROL 拡張機能] タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下にある&#x200B;**[!UICONTROL Configure]** ボタンをクリックします。
1. [!UICONTROL  データ収集]で、「**[!UICONTROL イベント送信前に編集」コールバックコード]** ボタンをクリックします。
1. エディターに目的のコードを配置します。

## `onBeforeEventSend`を使用してWeb SDKを手動で実装

Web SDKでは、`doPlugins`の代わりに、同様の機能を持つ`onBeforeEventSend`を使用します。 詳しくは、Web SDK ドキュメントの「[ グローバルにイベントを変更する](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)」を参照してください。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Adobe Analytics拡張機能を使用したプラグイン

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.doPlugins

目的のコードを含む関数に `s.doPlugins` 変数を設定します。 この関数は、トラッキングコールをおこなうときに自動的に実行されます。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>実装で 1 回だけ、関数を `doPlugins` 変数に設定します。 `doPlugins` 変数を複数回設定した場合は、最新のコードのみが使用されます。

## 例

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>以前のバージョンの AppMeasurement では、`doPlugins()` のコードが少し異なっていました。 アドビでは、上記の形式をベストプラクティスとして使用することをお勧めします。
