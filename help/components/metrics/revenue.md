---
title: 売上高
description: すべての注文内で購入された商品の金額。
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '113'
ht-degree: 100%

---

# 売上高

「売上高」指標は、すべての注文内で購入された製品の金額を示します。この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。この指標を任意のディメンションと組み合わせて、売上高に貢献したディメンション項目を確認できます。例えば、トラッキングコード（[トラッキングコード](../dimensions/tracking-code.md)ディメンション）を使用した上位のキャンペーンや、[eVar](../dimensions/evar.md) を使用した上位の内部検索用語を確認できます。

## この指標の計算方法

[`events`](/help/implement/vars/page-vars/events/event-purchase.md) 変数内に `purchase` が存在するヒットごとに、[`products`](/help/implement/vars/page-vars/products.md) 変数内の「Price」フィールドの合計を求めます。

この指標は、ページ上の通貨がレポートスイートのネイティブ通貨と異なる場合、[currencyCode](/help/implement/vars/config-vars/currencycode.md) 変数に依存します。
