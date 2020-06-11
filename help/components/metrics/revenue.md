---
title: 売上高
description: すべての注文内で購入された商品の金額。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# 売上高

「売上高」指標は、すべての注文内で購入された製品の金額を示します。 この指標は、eコマースのサイトでコンバージョンを測定する際に重要です。 この指標を任意のディメンションと組み合わせて、売上高に貢献したディメンション値を確認できます。 例えば、トラッ [キングコード](../dimensions/tracking-code.md) (Tracking code [)ディメンションを使用した上位のキャンペーンや、eVarを使用した上位の内部検索用語を確認できます](../dimensions/evar.md)。

## この指標の計算方法

変数内に `purchase` 存在するヒットごとに、変数内の「Price」フィールドの合計を求め [`events`](/help/implement/vars/page-vars/events/event-purchase.md)[`products`](/help/implement/vars/page-vars/products.md) ます。

この指標は、ページ上の通貨がレポートスイートのネイティブ通貨と異なる場合、 [currencyCode](/help/implement/vars/config-vars/currencycode.md) 変数に依存します。
