---
title: abort
description: abort 変数は、ヒットがアドビのデータ収集サーバーに送信されないようにするブール値です。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '193'
ht-degree: 100%

---

# abort

`abort` 変数は、次回のトラッキングコールがアドビに送信されるのを防ぐことができるブール値です。

## Adobe Experience Platform のデータ収集 UI での abort 変数の使用

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## データ収集 UI の AppMeasurement 構文とカスタムコードエディター

`abort` 変数はブール値です。デフォルト値は `false` です。

* `true` に設定した場合、次のトラッキングコール（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）はデータをアドビに送信しません。
* `false` に設定した場合、または定義しなかった場合、この変数は何もしません。

```js
s.abort = true;
```

>[!NOTE]
>
> `abort` 変数は、トラッキングコールのたびに `false` にリセットされます。同じページで後続のトラッキングコールを中止する必要がある場合は、`abort` を再度 `true` に設定します。

## 例

`abort` 変数は、イメージリクエストがアドビに送信される前に実行される最後の関数である [`doPlugins()`](../functions/doplugins.md) 関数に設定できます。

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。
