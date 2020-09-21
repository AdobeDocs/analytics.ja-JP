---
title: contextData
description: コンテキストデータ変数を使用すると、処理ルールで読み取ることのできる各ページにカスタム変数を定義できます。
translation-type: ht
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: ht
source-wordcount: '431'
ht-degree: 100%

---


# contextData

コンテキストデータ変数を使用すると、処理ルールで読み取ることのできる各ページにカスタム変数を定義できます。コード内の Analytics 変数に値を明示的に割り当てる代わりに、コンテキストデータ変数でデータを送信できます。次に、処理ルールは、コンテキストデータ変数の値を取得し、それぞれの Analytics 変数に渡します。『管理ユーザガイド』の「[処理ルール](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)」を参照してください。

コンテキストデータ変数は、開発チームが番号付き変数ではなく名前付きの要素でデータを収集する場合に役立ちます。例えば、開発チームにページの作成者の `eVar10` への割り当てをリクエストする代わりに、`s.contextData["author"]` への割り当てをリクエストすることができます。その後、組織の Analytics 管理者は、コンテキストデータ変数をレポート用の Analytics 変数にマップする処理ルールを作成できます。開発チームは、最終的に、アドビが提供する多くのページ変数ではなく、コンテキストデータ変数についてのみ懸念することになります。

## Adobe Experience Platform Launch のコンテキストデータ変数

Launch には、コンテキストデータ変数を設定するための専用の場所がありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.contextData

`s.contextData` 変数は値を直接取りません。代わりに、この変数のプロパティを文字列に設定します。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有効なコンテキストデータ変数には、英数字、アンダースコアおよびピリオドのみが含まれます。ハイフンなどの他の文字を含める場合、処理ルールでのデータ収集は保証されません。
* コンテキストデータ変数を `"a."` で開始しないでください。このプレフィックスはアドビが予約して使用します。例えば、`s.contextData["a.InstallEvent"]` を使用しないでください。
* コンテキストデータ変数では、大文字と小文字が区別されません。`s.contextData["example"]` 変数と `s.contextData["EXAMPLE"]` 変数は同じです。

## 処理ルールを使用した Analytics 変数の入力

>[!IMPORTANT]
>
> コンテキストデータ変数は、処理ルールの実行後に破棄されます。変数に値を配置する処理ルールがアクティブでない場合、そのデータは永久的に失われます。

1. コンテキストデータ変数の名前と値を設定するには、実装を更新します。
2. Adobe Analytics にログインし、管理者／レポートスイートに移動します。
3. 適切なレポートスイートを選択し、設定を編集／一般／処理ルールに移動します。
4. Analytics 変数をコンテキストデータ変数値に設定する処理ルールを作成します。
5. 変更を保存します。

処理ルールは、保存するとすぐに有効になります。履歴データには適用されません。

## リンクトラッキングコールでのコンテキストデータの送信

コンテキストデータ変数を `contextData` のプロパティとして [`s.linkTrackVars`](../config-vars/linktrackvars.md) に含めます。

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## コンテキストデータ変数を使用したイベントの増分

処理ルールを作成する際に、コンテキストデータ変数をイベントに割り当てることができます。

* コンテキストデータ変数に任意の種類のテキストが含まれている場合、イベント値は 1 ずつ増分されます。
* コンテキストデータ変数に整数が含まれる場合、イベントはその整数分だけ増加します。

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
