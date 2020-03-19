---
title: 中止
description: abort変数は、ヒットがアドビのデータ収集サーバーに送信されるのを防ぐブール値です。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 中止

この変 `abort` 数は、次回のトラッキングコールがアドビに送信されるのを防ぐことができるブール値です。

## Adobe Experience Platform Launchでのabort変数の使用

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurement構文と、起動のカスタムコードエディター

変数 `abort` はブール値です。 Its default value is `false`.

* に設定した場 `true`合、次回のトラッキングコール(ま[`t()`](../functions/t-method.md) たは [`tl()`](../functions/tl-method.md))ではデータはアドビに送信されません。
* に設定した場合、ま `false` たは定義しなかった場合、この変数は何もしません。

```js
s.abort = true;
```

> [!NOTE] この変 `abort` 数は、トラッキングの `false` たびににリセットされます。 同じページで後続のトラッキングコールを中止する必要がある場合は、を再度に `abort` 設定し `true` ます。

## 例   

この変 `abort` 数は、イメージリクエストがア [`doPlugins()`](../functions/doplugins.md) ドビに送信される前に実行される最後の関数である関数に設定できます。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

追跡したくないアクティビティ（ディスプレイ広告の一部のカスタムリンクや外部リンクなど）を識別するために使用するロジックを一元化できます。
