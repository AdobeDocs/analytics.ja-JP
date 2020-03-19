---
title: contextData
description: コンテキストデータ変数を使用すると、処理ルールで読み取り可能な各ページでカスタム変数を定義できます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# contextData

コンテキストデータ変数を使用すると、処理ルールで読み取り可能な各ページでカスタム変数を定義できます。 コード内のAnalytics変数に値を明示的に割り当てる代わりに、コンテキストデータ変数でデータを送信できます。 次に、処理ルールは、コンテキストデータ変数の値を取得し、それぞれのAnalytics変数に渡します。 管理ユーザーガイドの「[処理ルール](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)」を参照してください。

コンテキストデータ変数は、開発チームが番号付き変数ではなく名前付きの要素でデータを収集するのに役立ちます。 例えば、開発チームにページの作成者の割り当てを依頼する代わりに、その作成者にペ `eVar10`ージの作成者の割り当てを依頼することがで `s.contextData["author"]` きます。 その後、組織のAnalytics管理者が処理ルールを作成し、コンテキストデータ変数をレポート用のAnalytics変数にマップできます。 開発チームは、最終的に、アドビが提供する多くのページ変数ではなく、コンテキストデータ変数についてのみ考慮する必要があります。

## Adobe Experience Platform Launchのコンテキストデータ変数

起動には、コンテキストデータ変数を設定するための専用の場所がありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.contextDataとカスタムコードエディターの起動

変数 `s.contextData` は値を直接取りません。 代わりに、この変数のプロパティを文字列に設定します。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有効なコンテキストデータ変数には、英数字、アンダースコアおよびピリオドのみが含まれます。 ハイフンなどの他の文字を含める場合、処理ルールでのデータ収集は保証されません。
* でコンテキストデータ変数を開始しないでくださ `"a."`い。 このプレフィックスはアドビが予約し、使用します。 例えば、を使用しないでくださ `s.contextData["a.InstallEvent"]`い。
* コンテキストデータ変数では、大文字と小文字が区別されません。 変数と変数 `s.contextData["example"]` は同 `s.contextData["EXAMPLE"]` じです。

## 処理ルールを使用したAnalytics変数の入力

> [!IMPORTANT] コンテキストデータ変数は、処理ルールの実行後に破棄されます。 変数に値を配置する処理ルールがアクティブでない場合、そのデータは永久的に失われます。

1. コンテキストデータ変数の名前と値を設定するには、実装を更新します。
2. Adobe Analyticsにログインし、管理者/レポートスイートに移動します。
3. 目的のレポートスイートを選択し、設定を編集/一般/処理ルールに移動します。
4. Analytics変数をコンテキストデータ変数値に設定する処理ルールを作成します。
5. 変更を保存します。

処理ルールは、保存するとすぐに有効になります。 履歴データには適用されません。

## リンクトラッキングコールでのコンテキストデータの送信

コンテキストデータ変数をのプロパティとして含め `contextData` ます。 [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
