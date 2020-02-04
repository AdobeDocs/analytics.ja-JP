---
title: 変数、関数、メソッドおよびプラグインの概要
description: レポートを改善するためにアドビに送信するデータに含めることができる変数について説明します。
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# 変数、関数、メソッドおよびプラグインの概要

Analytics には、Analytics データを収集するための変数が多数用意されています。この節の変数は、次のセクションに分かれています。

* **ページ変数は** 、通常、レポートで直接使用される値です。 一般的なページ変数には、、 `props`および `eVars`が含まれま `events`す。
* **設定変数は** 、正しいデータがアドビに届くことを確認するのに役立つ設定値です。 一般的な設定変数には、、、 `trackingServerSecure`およ `charSet`びがありま `linkTrackVars`す。 通常、設定変数はディメンション値を設定しません。
* **関数とメソッドは** 、参照時に特定のタスクを実行するコードの一部です。 一般的な関数には、、 `t()`および `tl()`がありま `clearVars()`す。

## 変数と実装メソッド

アドビでは、Adobe Analyticsを実装する複数の方法を提供しています。 各ページには、LaunchとJavaScript版AppMeasurementを使用した変数の実装方法に関する節があります。

## 操作の順序

Adobe Analyticsによって公開されたAppMeasurementライブラリは、アドビにデータを送信する際に、特定の順序に従います。 これらのタスクを順不同で実行すると、データが不完全になる可能性があります。

1. サイトでデータレイヤーを使用している場合は、該当するすべての変数が最初に入力されていることを確認します。 See [Data layer](../prepare/data-layer.md) for more information.
2. データレイヤーを使用してAnalytics変数を入力します。 「起動」を使用する場合、このタスクは、データ要素を使用し、データ要素を変数に割り当てることで簡単に実行できます。 Launchユー [ザーガイドの](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html) Data elementsを参照してください。
3. トラッキング関数を呼び出します。 ほとんどのAppMeasurementライブラリは関数を `t()` 使用しますが、モバイルSDKの一部はこの関数を使用しま `track()`す。 トラッキング関数が呼び出されると、Analyticsオブジェクトで定義されたサポートされているすべての変数が、イメージリクエストの形式でアドビに送信されます。

## 不正な文字

次の文字と文字列は、JavaScript変数では使用できません。

* タブ (`0x09`)
* キャリッジリターン(`0x0D`)
* 改行 (`0x0A`)
* HTML tags (e.g. `<b></b>` or `&#153`)

一部の変数には、追加の制限や構文上の要件があります。 例えば、変数は製品とカ `products` テゴリを区切るためにセミコロンとコンマを予約します。
