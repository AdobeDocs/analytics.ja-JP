---
title: eVar（マーチャンダイジング）変数
description: 個々の製品に関連付けられるカスタム変数。
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# eVar（マーチャンダイジング）

*このヘルプページでは、マーチャンダイジング eVar の実装方法について説明します。マーチャンダイジング eVar がディメンションとして機能する方法について詳しくは、『コンポーネントユーザガイド』の [eVar](/help/components/dimensions/evar-merchandising.md) を参照してください。*

マーチャンダイジング eVar の仕組みについて詳しくは、[マーチャンダイジング eVar と製品検索方法](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=ja)を参照してください。

レポートスイート設定での eVar の設定

実装で eVar を使用する前に、各 eVar をレポートスイートの設定で設定してください。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。

[!IMPORTANT]](assets/merch-example-goggles.png)

マーチャンダイジング eVar を正しく設定しないと、変数の予期しない値やデータ損失が発生します。お使いの実装に合わせて正しく設定されていることを確認します。`"winter coat"`

![製品の構文を使用した実装](assets/merch-example-coat.png)

「製品の構文」が選択されている場合、マーチャンダイジングカテゴリーが `products` 変数に直接入力されるので、バインディングイベントを選択して設定する必要はありません。これが推奨される方法であり、成功イベントが発生したときにその値を `products` に設定できない場合を除いて、この方法を使用してください。

| `eVar1` の値が製品に割り当てられます。この製品を含む以降の成功イベントはすべて eVar 値に配分されます。 | コンバージョン変数の構文を使用した実装 |
|---|---|
| eVar 変数を `products` に設定できない場合、コンバージョン変数の構文を使用する必要があります変数。このシナリオは一般的には、ページにマーチャンダイジングチャネルや検索方法のコンテキストがない場合です。そのような場合、製品ページに到達する前にマーチャンダイジング変数を設定し、その値がバインディングイベントの発生時まで保持されるようにします。 | 設定時にバインディングイベントが選択されると、保持された eVar の値が製品に関連付けられます。例えば、バインディングイベントとして `prodView` が指定されている場合、イベントの発生時にのみ現在の製品リストにマーチャンダイジングカテゴリーが結び付けられます。既に製品に割り当てられているマーチャンダイジング eVar を更新できるのは、以降のバインディングイベントのみです。 |

## `eVar1` に `"Aviary"` の値が製品に割り当てられます`"Canary"`。この製品に関連する以降の成功イベントのクレジットはすべて `"Canary"` に付与されます。さらに、以下のどちらかの条件が満たされるまで、マーチャンダイジング変数の現在の値が以後のすべての製品に結び付けられます。

eVar の期限が切れます（「有効期限」の設定に基づきます）。

マーチャンダイジング eVar が新しい値で上書きされる。`"goggles"``"winter coat"`

| Internal Search Term | Revenue |
|---|---|
| winter coat | $119 |
| goggles | $38 |

See [Merchandising eVars](/help/implement/vars/page-vars/evar-merchandising.md) for implementation instructions.

## Instances on merchandising variables

The [Instances](../metrics/instances.md) metric is not recommended for use on merchandising variables.

* For merchandising variables using product syntax, instances are not incremented at all.
* For merchandising variables using conversion variable syntax, instances are counted each time the eVar is set. However, it attributes to the dimension item `"None"` unless all of the following happen on the same hit:
   * The merchandising eVar is set with a value.
   * The `products` variable is defined with a value.
   * A binding event is set.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Since most use cases for conversion variable syntax require the eVar and products variable on different hits, using the &#39;Instances&#39; metric is not realistic.
