---
title: doPlugins
description: ヒットがコンパイルされてアドビに送信される直前に、ロジックを設定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# doPlugins

この変 `doPlugins` 数は、実装内で値を設定する「最後の呼び出し」として機能します。 を有効 [`usePlugins`](../config-vars/useplugins.md) にすると、次のようなイメージリクエストがコンパイルされてアドビに送信される直前に、自動的に実行されます。

* すべてのページビュー([`t()`](t-method.md))呼び出し
* 自動ダウンロードリンクと離脱[`tl()`](tl-method.md)リンクを含む、すべてのリンクトラッキング()コール

この変数を `doPlugins` 使用して、プラグインコードを呼び出し、イメージリクエストがコンパイルされてアドビに送信される直前に、最終的な変数値を設定します。

## Adobe Experience Platform Launchのプラグイン

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.doPluginsとカスタムコードの起動

目的のコード `s.doPlugins` を含む関数に変数を設定します。 この関数は、トラッキングコールを行うときに自動的に実行されます。

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] 関数を変数に設定するのは、 `doPlugins` 実装で1回だけにします。 変数を複数回設定 `doPlugins` した場合は、最新のコードのみが使用されます。

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

> [!NOTE] 以前のバージョンのAppMeasurementでは、コードが少し異なって `doPlugins()` いました。 アドビでは、上記の形式をベストプラクティスとして使用することをお勧めします。
