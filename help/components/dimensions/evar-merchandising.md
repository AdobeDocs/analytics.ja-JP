---
title: eVar（マーチャンダイジング）
description: 製品ディメンションに関連付けられるカスタム変数。
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# eVar（マーチャンダイジング）

*このヘルプページでは、eVar がディメンションとして機能するしくみについて説明します。eVar の実装方法について詳しくは、『実装ユーザガイド』の [eVar](/help/implement/vars/page-vars/evar.md) を参照してください。*

外部キャンペーンまたは外部検索用語の成功を測定する場合、一般的には発生する成功イベントすべてに対応するクレジットを受け取る 1 個の値が必要になります。例えば、顧客が電子メールキャンペーンのリンクをクリックして Web サイトを訪問した場合、その結果としておこなわれたすべての購入のクレジットがそのキャンペーンに付与される必要があります。

しかし、顧客が複数のアイテムを探しているときにサイト内検索またはカテゴリー閲覧によって発生したイベントはどうなるでしょうか。例えば、顧客がサイトで「`"goggles"`」を検索し、をカートに追加したとします。

![ゴーグルの例](assets/merch-example-goggles.png)

この顧客はチェックアウトの前に「`"winter coat"`」を検索し、ダウンジャケットをカートに追加しました。

![コートの例](assets/merch-example-coat.png)

訪問者がこの購入を完了すると、`"winter coat"` の内部検索に、ゴーグルの購入に対するクレジットが付与されます（eVar でデフォルトの配分である「最新」が使用される場合）。`"winter coat"` にとっては良いのですが、マーケティングの意思決定については良いものではありません。

| 内部検索キーワード | 売上高 |
|---|---|
| 冬物コート | $157 |

## マーチャンダイジング変数による問題解決

マーチャンダイジング eVar を使用して、成功イベントが発生した時点で eVar の現在の値を製品に割り当てることができます。その特定の eVar に 1 つ以上の新しい値が後から設定された場合でも、この値はその製品に結び付けられたままになります。

前の例で eVar のマーチャンダイジングを有効にした場合、「`"goggles"`」は雪山用ゴーグルに結び付けられ、検索用語「`"winter coat"`」はダウンジャケットに結び付けられます。マーチャンダイジング eVar では製品レベルで売上を割り当てるので、用語が結び付けられた製品の売上金額に相当するクレジットを各用語が受け取ります。

| 内部検索キーワード | 売上高 |
|---|---|
| 冬物コート | $119 |
| ゴーグル | $38 |

実装手順については、「[マーチャンダイジング eVar](/help/implement/vars/page-vars/evar-merchandising.md)」を参照してください。

## マーチャンダイジング変数とインスタンス

マーチャンダイジング変数での使用には、[インスタンス](../metrics/instances.md)指標の使用は推奨されません。

* 製品の構文を使用するマーチャンダイジング変数の場合、インスタンスはまったく増えません。
* コンバージョン変数の構文を使用するマーチャンダイジング変数の場合、eVar が設定されるたびにインスタンスがカウントされます。ただし、同じヒットで次のすべてが発生しない限り、ディメンション項目 `"None"` の属性になります。
   * マーチャンダイジング eVar が新しい値で上書きされます。
   * `products` 変数は値で定義されます。
   * バインディングイベントが設定される。

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

コンバージョン変数の構文のほとんどの使用例では、異なるヒットで eVar と products 変数を使用する必要があるので、「インスタンス」指標を使用することは現実的ではありません。
