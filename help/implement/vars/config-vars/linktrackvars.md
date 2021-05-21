---
title: linkTrackVars
description: リンクトラッキングイメージリクエストに含める変数を指定します。
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '271'
ht-degree: 100%

---

# linkTrackVars

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。`linkTrackVars` 変数と [`linkTrackEvents`](linktrackevents.md) 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

この変数は、ページビュー呼び出し（[`t()`](../functions/t-method.md) メソッド）には使用されません。

## Adobe Experience Platform Launch を使用したリンクトラッキングコールの変数

この変数は Launch ではインターフェイスで設定された変数に基づいて、バックエンドで自動的に設定するので、Launch を使用した実装では常に設定されます。

>[!IMPORTANT]
>
> カスタムコードエディターを使用して Launch で変数を設定する場合は、カスタムコードを使用して `linkTrackVars` にも変数を含める必要があります。

## AppMeasurement および Launch カスタムコードエディターの s.linkTrackVars

`s.linkTrackVars` 変数は、リンクトラッキングイメージリクエスト（`tl()` メソッド）に含める変数のコンマ区切りリストを含む文字列です。リンクトラッキングヒットにディメンションを含めるには、次の両方の条件を満たす必要があります。

* 目的の変数値を設定します。例：`s.eVar1 = "Example value";`。
* 目的の変数を `linkTrackVars` 変数に設定します。例：`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

この変数のデフォルト値は空の文字列です。ただし、Code Manager では、この変数が `"None"` に設定されている AppMeasurement コードを提供しています。有効な値は、ディメンションを入力するページレベルの変数です。

* この変数を定義しない場合、または空の文字列に設定した場合、*すべての*&#x200B;変数がリンクトラッキングイメージリクエストに含まれます。
* この変数を `"None"` に設定した場合、リンクトラッキングイメージリクエストには変数が含まれ&#x200B;*ません*。

>[!TIP]
>
> この変数で変数を指定する場合は、Analytics オブジェクト識別子（`s.`）を使用しないでください。例えば、`s.linkTrackVars = "eVar1";` は正しいですが、`s.linkTrackVars = "s.eVar1";` は正しくありません。

## 例

次のリンクトラッキング関数は、アドビに送信されるイメージリクエストに `eVar1` のみを含みます（`eVar2` は含みません）。

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
