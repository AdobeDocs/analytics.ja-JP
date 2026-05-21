---
title: 売上高
description: すべての注文内で購入された商品の金額。
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 74%

---

# 売上高

「収益」指標[指標](overview.md)には、すべての注文で購入された商品の金額が表示されます。 この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。 この指標を任意のディメンションと組み合わせることで、売上に貢献したディメンション項目を確認できます。 例えば、トラッキングコード（[トラッキングコード](../dimensions/tracking-code.md)ディメンション）を使用した上位のキャンペーンや、[eVar](../dimensions/evar.md) を使用した上位の内部検索語を確認できます。

## この指標の計算方法

[`events`](/help/implement/vars/page-vars/events/event-purchase.md) 変数内に `purchase` が存在するヒットごとに、[`products`](/help/implement/vars/page-vars/products.md) 変数内の「Price」フィールドの合計を求めます。

この指標は、ページ上の通貨がレポートスイートのネイティブ通貨と異なる場合、[currencyCode](/help/implement/vars/config-vars/currencycode.md) 変数に依存します。
