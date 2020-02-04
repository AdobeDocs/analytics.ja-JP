---
title: 中止
description: abort変数は、ヒットがアドビのデータ収集サーバーに送信されないようにするブール値です。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# 中止

この変 `abort` 数は、次回のトラッキングコールがアドビに送信されるのを防ぐことができるブール値です。

## Adobe Experience Platform Launchでのabort変数の使用

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurement構文とカスタムコードエディター（起動）

変数 `abort` はブール値です。 Its default value is `false`.

* に設定した場 `true`合、次のトラッキングコール(`t()` また `tl()`は)はデータをアドビに送信しません。
* に設定した場合、ま `false` たは定義しなかった場合、この変数は何もしません。

```js
s.abort = true;
```

> [!NOTE] この変 `abort` 数は、トラッキングコー `false` ルのたびににリセットされます。 同じページで後続のトラッキングコールを中止する必要がある場合は、を再度に `abort` 設定 `true` します。

## 例

この変 `abort` 数は、イメージリクエストがア `doPlugins()` ドビに送信される前に実行される最後の関数である関数に設定できます。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

ディスプレイ広告内の一部のカスタムリンクや外部リンクなど、追跡しないアクティビティを識別するために使用するロジックを一元管理できます。
