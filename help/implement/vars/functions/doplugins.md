---
title: doPlugins
description: ヒットがコンパイルされてアドビに送信される直前にロジックを設定します。
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# doPlugins

`doPlugins` 変数は、実装に値を設定する「最後の呼び出し」として機能します。[`usePlugins`](../config-vars/useplugins.md) が有効になっている場合は、次のようなイメージリクエストがコンパイルされてアドビに送信される直前に自動的に実行されます。

* すべてのページビュー（[`t()`](t-method.md)）コール
* 自動ダウンロードリンクと出口リンクを含む、すべてのリンクトラッキング（[`tl()`](tl-method.md)）コール

`doPlugins` 変数を使用してプラグインコードを呼び出し、イメージリクエストがコンパイルされてアドビに送信される直前に、最終的な変数値を設定します。

## Adobe Experience Platform のタグを使用したプラグイン

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.doPlugins

目的のコードを含む関数に `s.doPlugins` 変数を設定します。この関数は、トラッキングコールをおこなうときに自動的に実行されます。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
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
