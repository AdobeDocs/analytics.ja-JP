---
title: 単位
description: すべての注文内で購入された製品の合計数。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# 単位

「数量」指標は、すべての注文内で購入された製品の合計数を示します。 この指標は、eコマースのサイトでコンバージョンを測定する際に重要です。 この指標を任意のディメンションと組み合わせて、どのディメンション値が製品の購入数に貢献したかを確認できます。 例えば、購入した商品に貢献したトップキャンペーン( [トラッキングコード](../dimensions/tracking-code.md) ディメンションを使用)またはトップ内検索用語(eVarを使用 [](../dimensions/evar.md))を確認できます。

## この指標の計算方法

変数内に `purchase` 存在するヒットごとに、変数内の「Quantity」フィールドの合計を求め [`events`](/help/implement/vars/page-vars/events/events-overview.md)[`products`](/help/implement/vars/page-vars/products.md) ます。

## 注文と数量の比較

[](orders.md) 注文件数指標には、購入イベント数のみが記録されます。 顧客は複数の製品を購入できるので、「購入点数」指標は通常「注文件数」を上回ります。 この場合、1つの注文に複数の数量が含まれます。

購入回数が数量を超える場合は、導入の整合性を確認することをお勧めします。 購入時に `products` 変数が正しく設定されない可能性があります。これは通常、望ましくない動作です。
