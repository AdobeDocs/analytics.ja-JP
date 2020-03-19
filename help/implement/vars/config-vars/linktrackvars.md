---
title: linkTrackVars
description: リンクトラッキングイメージリクエストに含める変数を指定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackVars

一部の実装では、すべてのリンクトラッキングイメージリクエストにすべての変数を含めたくない場合があります。 変数と変数を使 `linkTrackVars` 用して、 [`linkTrackEvents`](linktrackevents.md) 呼び出しにディメンションと指標を選択的に含め [`tl()`](../functions/tl-method.md) ます。

この変数は、ページビュー呼び出し（メソッド）には使`t()` 用されません。

## Adobe Experience Platform Launchを使用したリンクトラッキングコールの変数

Launchは、インターフェイスで設定された変数に基づいて、バックエンドでこの変数を自動的に設定するので、常にLaunchを使用する実装で設定されます。

> [!IMPORTANT] カスタムコードエディターを使用して起動で変数を設定する場合は、カスタムコードの使用に変数を含め `linkTrackVars` る必要があります。

## AppMeasurementと起動のカスタムコードエディターのs.linkTrackVars

変数 `s.linkTrackVars` は、リンクトラッキングイメージリクエスト（メソッド）に含める変数のコンマ区切りリストを含む文字列`tl()` です。 リンクトラッキングのヒットにディメンションを含めるには、次の両方の条件を満たす必要があります。

* 目的の変数値を設定します。 例：`s.eVar1 = "Example value";`。
* 変数に目的の変数を設定し `linkTrackVars` ます。 例：`s.linkTrackEvents = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

この変数のデフォルト値は空の文字列です。 ただし、この変数がに設定されているコードマネージャーにAppMeasurementコードがアドビから提供されまし `"None"`た。 有効な値は、ディメンションを入力するページレベルの変数です。

* この変数が定義されていない場合、または空の文字列に設定されている場合 *、すべての* 変数がリンクトラッキングイメージリクエストに含まれます。
* この変数をに設定した場合、リ `"None"`ンクト *ラッキング* イメージリクエストに変数は含まれません。

> [!TIP] この変数で変数を指定する場合は、Analytics`s.`オブジェクト識別子()の使用を避けます。 例えば、は正し `s.linkTrackVars = "eVar1";` いが、は正し `s.linkTrackVars = "s.eVar1";` くないとします。

## 例   

次のリンクトラッキング機能は、アドビに送 `eVar1` 信されるイメ `eVar2`ージリクエストに（非）のみを含みます。

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
