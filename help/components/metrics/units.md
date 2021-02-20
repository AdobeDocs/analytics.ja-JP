---
title: 単位
description: すべての注文内で購入された製品の合計数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 100%

---


# 単位

「単位」指標は、すべての注文内で購入された製品の合計数を示します。この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。この指標を任意のディメンションと組み合わせて、どのディメンション項目が製品の購入数に貢献したかを確認できます。例えば、購入した商品に貢献したトップキャンペーン（[トラッキングコード](../dimensions/tracking-code.md)ディメンションを使用）またはトップ内検索用語（[eVar](../dimensions/evar.md) を使用）を確認できます。

## この指標の計算方法

[`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数内に `purchase` が存在するヒットごとに、[`products`](/help/implement/vars/page-vars/products.md) 変数内の「Quantity」フィールドの合計を求めます。

## 注文と単位の比較

[注文件数](orders.md)指標には、購入イベント数のみが記録されます。顧客は複数の製品を購入できるので、「単位」指標は通常「注文件数」を上回ります。この場合、1 つの注文に複数の単位が含まれます。

購入回数が単位を超える場合は、実装の整合性を確認することをお勧めします。購入時に `products` 変数が正しく設定されていない可能性があります。これは通常、望ましくない動作です。
