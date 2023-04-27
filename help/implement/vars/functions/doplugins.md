---
title: doPlugins
description: ヒットがコンパイルされてアドビに送信される直前にロジックを設定します。
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 41154580c272514e504c5478215bb67795488de3
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 62%

---

# doPlugins

`doPlugins` 変数は、実装に値を設定する「最後の呼び出し」として機能します。通話をするのに最適な場所です [プラグインのメソッド](../plugins/impl-plugins.md) およびは、イメージリクエストが送信される前に必要な変数を設定します。 [`usePlugins`](../config-vars/useplugins.md) が有効になっている場合は、次のようなイメージリクエストがコンパイルされてアドビに送信される直前に自動的に実行されます。

* すべてのページビュー（[`t()`](t-method.md)）コール
* 自動ダウンロードリンクと出口リンクを含む、すべてのリンクトラッキング（[`tl()`](tl-method.md)）コール

`doPlugins` 変数を使用してプラグインコードを呼び出し、イメージリクエストがコンパイルされてアドビに送信される直前に、最終的な変数値を設定します。

## Web SDK 拡張機能を使用した、イベント送信前のコールバックコードの使用

の代わりに `doPlugins`を使用する場合、Web SDK は `onBeforeEventSend` 同様の機能を備えています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. の下 [!UICONTROL データ収集]、 **[!UICONTROL イベント送信コールバックコードの前に編集]** 」ボタンをクリックします。
1. エディターに目的のコードを配置します。

## 用途 `onBeforeEventSend` Web SDK の手動実装

の代わりに `doPlugins`を使用する場合、Web SDK は `onBeforeEventSend` 同様の機能を備えています。 詳しくは、 [イベントのグローバルな変更](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （ Web SDK ドキュメント）を参照してください。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Adobe Analytics拡張機能を使用したプラグイン

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.doPlugins

目的のコードを含む関数に `s.doPlugins` 変数を設定します。この関数は、トラッキングコールをおこなうときに自動的に実行されます。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
> 実装で 1 回だけ、関数を `doPlugins` 変数に設定します。`doPlugins` 変数を複数回設定した場合は、最新のコードのみが使用されます。

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
> 以前のバージョンの AppMeasurement では、`doPlugins()` のコードが少し異なっていました。アドビでは、上記の形式をベストプラクティスとして使用することをお勧めします。
