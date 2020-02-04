---
title: linkTrackVars
description: リンクトラッキングイメージリクエストに含める変数を指定します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackVars

一部の実装では、すべてのリンクトラッキングイメージリクエストにすべての変数を含めないでください。 変数と変数を使 `linkTrackVars` 用して、呼び `linkTrackEvents` 出しにディメンションと指標を選択的に含め `tl()` ます。

この変数は、ページビュー呼び出し(関数`t()` )には使用されません。

## Adobe Experience Platform Launchを使用したリンクトラッキングコールの変数

「起動」は、インターフェイスで設定された変数に基づいて、バックエンドでこの変数を自動的に設定するので、常に「起動」を使用した実装で設定されます。

> [!IMPORTANT] カスタムコードエディターを使用して起動で変数を設定する場合は、カスタムコードを使用する際にも変数を含め `linkTrackVars` る必要があります。

## AppMeasurementおよび起動のカスタムコードエディターのs.linkTrackVars

変数 `s.linkTrackVars` は、リンクトラッキングイメージリクエスト（関数）に含める変数のコンマ区切りリストを含む文字列`tl()` です。 リンクトラッキングヒットにディメンションを含めるには、次の両方の条件を満たす必要があります。

* 目的の変数値を設定します。 例：`s.eVar1 = "Example value";`。
* 目的の変数を変数に設定し `linkTrackVars` ます。 例：`s.linkTrackEvents = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

この変数のデフォルト値は空の文字列です。 ただし、この変数がに設定されているコードマネージャーでAppMeasurementコードが提供されまし `"None"`た。 有効な値は、ディメンションを入力するページレベルの変数です。

* この変数を定義しない場合、または空の文字列に設定した場合 *、すべての* 変数がリンクトラッキングイメージリクエストに含まれます。
* この変数をに設定した場合、リ `"None"`ンクト *ラッキング* イメージリクエストに変数は含まれません。

> [!TIP] この変数で変数を指定する場合は、Analyticsオブジェクト識別子(`s.`)を使用しないでください。 例えば、は正し `s.linkTrackVars = "eVar1";` いが、は正し `s.linkTrackVars = "s.eVar1";` くない。

## 例

次のリンクトラッキング関数は、アドビに送信 `eVar1` されるイメ `eVar2`ージリクエストに（非）のみを含みます。

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
