---
title: eVar（マーチャンダイジング）
description: productsディメンションに関連付けられるカスタム変数。
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 25%

---


# eVar（マーチャンダイジング）

*このヘルプページでは、マーチャンダイジングeVarがディメンションとして機能する方法を説明します。 マーチャンダイジングeVarの実装方法について詳しくは、『実装ユーザーガイド[](/help/implement/vars/page-vars/evar.md)』のeVarを参照してください。*

外部キャンペーンまたは外部検索用語の成功を測定する場合、一般的には発生する成功イベントすべてに対応するクレジットを受け取る 1 個の値が必要になります。例えば、顧客が電子メールキャンペーンのリンクをクリックして Web サイトを訪問した場合、その結果としておこなわれたすべての購入のクレジットがそのキャンペーンに付与される必要があります。

顧客が複数のイベントを探す場合、内部検索やカテゴリの閲覧によって引き起こされるアイテムについてはどうでしょうか。 For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![ゴーグルの例](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to the to their cart:

![コートの例](assets/merch-example-coat.png)

訪問者がこの購入を完了すると、一対のゴーグルの購入に `"winter coat"` クレジットが付与される内部検索が発生します（eVarでデフォルトの配分である「最新」が使用される場合）。 Good for `"winter coat"`, but bad for marketing decisions:

| 内部検索キーワード | 売上高 |
|---|---|
| 冬物コート | $157 |

## マーチャンダイジング変数による問題解決

マーチャンダイジングeVarを使用すると、成功イベントが発生した時点でeVarの現在の値を製品に割り当てることができます。 その特定の eVar に 1 つ以上の新しい値が後から設定された場合でも、この値はその製品に結び付けられたままになります。

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is tied to the snow goggles, and the search term `"winter coat"` is tied to the down jacket. マーチャンダイジングeVarは製品レベルで売上高を割り当てるので、各用語は、その用語が関連付けられた製品の売上高の額に対するクレジットを受け取ります。

| 内部検索キーワード | 売上高 |
|---|---|
| 冬物コート | $119 |
| ゴーグル | $38 |

導入手順については、 [マーチャンダイジングeVar](/help/implement/vars/page-vars/evar-merchandising.md) （英語のみ）を参照してください。

## マーチャンダイジング変数とインスタンス

マーチャンダイジング変数での使用には、 [](../metrics/instances.md) インスタンス指標の使用は推奨されません。

* 製品の構文を使用するマーチャンダイジング変数の場合、インスタンスはまったく増えません。
* コンバージョン変数の構文を使用するマーチャンダイジング変数の場合、eVarが設定されるたびにインスタンスがカウントされます。 ただし、同じヒットで次のすべてが発生しな `"None"` い限り、ディメンション値の属性になります。
   * マーチャンダイジングeVarに値が設定されている。
   * 変数は値で定義され `products` ます。
   * バインディングイベントが設定される。

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

コンバージョン変数の構文のほとんどの使用例では、異なるヒットでeVarとproducts変数を使用する必要があるので、「Instances」指標を使用することは現実的ではありません。
