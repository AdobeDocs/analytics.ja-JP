---
title: 変数、関数、メソッド、プラグインの概要
description: レポートを改善するためにアドビに送信するデータに含めることができる変数について説明します。
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: ht
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: ht
source-wordcount: '318'
ht-degree: 100%

---


# 変数、関数、メソッド、プラグインの概要

Analytics には、Analytics データを収集するための変数が多数用意されています。この節の変数は、いくつかに分かれています。

* **ページ変数**&#x200B;は、通常、レポートで直接使用される値です。一般的なページ変数には、`props`、`eVars`、`events` が含まれます。
* **設定変数**&#x200B;は、正しいデータがアドビに届くことを確認するのに役立つ設定値です。一般的な設定変数には、`trackingServerSecure`、`charSet`、`linkTrackVars` があります。通常、設定変数はディメンション項目を設定しません。
* **関数とメソッド**&#x200B;は、参照時に特定のタスクを実行するコードの一部です。一般的な関数には、`t()`、`tl()`、`clearVars()` があります。

## 変数と実装メソッド

Adobe Analytics は様々な方法で実装できます。各ページには、Launch と JavaScript 版 AppMeasurement を使用した変数の実装方法に関する節があります。

## 演算の順序

Adobe Analytics によって公開された AppMeasurement ライブラリは、アドビにデータを送信する際に、特定の順序に従います。これらのタスクを順不同で実行すると、データが不完全になる可能性があります。

1. サイトでデータレイヤーを使用している場合は、該当するすべての変数が最初に入力されていることを確認します。詳しくは、[データレイヤー](../prepare/data-layer.md)を参照してください。
2. データレイヤーを使用して Analytics 変数を入力します。Launch を使用する場合、このタスクは、データ要素を使用し、データ要素を変数に割り当てることで簡単に実行できます。『Launch ユーザーガイド』の[データ要素](https://docs.adobe.com/content/help/ja-JP/launch/using/reference/manage-resources/data-elements.html)を参照してください。
3. トラッキング関数を呼び出します。ほとんどの AppMeasurement ライブラリでは `t()` メソッドを使用しますが、一部の モバイル SDK では `track()` メソッドを使用します。トラッキング関数が呼び出されると、Analytics オブジェクトで定義されたサポートされているすべての変数が、イメージリクエストの形式でアドビに送信されます。

## 無効な文字

次の文字と文字列は、JavaScript 変数では使用できません。

* タブ（`0x09`）
* キャリッジリターン（`0x0D`）
* 改行（`0x0A`）
* HTML タグ（例：`<b></b>`、`&#153`）

一部の変数には、追加の制限や構文上の要件があります。例えば、[`products`](page-vars/products.md) 変数は製品とカテゴリを区切るためにセミコロンとコンマを予約します。
