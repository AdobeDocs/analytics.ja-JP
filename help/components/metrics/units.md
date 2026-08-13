---
title: 単位
description: すべての注文内で購入された製品の合計数。
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 80%

---

# 単位

「単位」 [指標](overview.md)には、すべての注文で購入された製品の合計数が表示されます。 この指標は、e コマースのサイトでコンバージョンを測定する際に重要です。 この指標を任意のディメンションと組み合わせることで、どのディメンションが購入数に貢献したのかを確認できます。 例えば、購入した商品に貢献したトップキャンペーン（[トラッキングコード](../dimensions/tracking-code.md)ディメンションを使用）またはトップ内検索語（[eVar](../dimensions/evar.md) を使用）を確認できます。

## この指標の計算方法

[`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数内に `purchase` が存在するヒットごとに、[`products`](/help/implement/vars/page-vars/products.md) 変数内の「Quantity」フィールドの合計を求めます。

## 注文と単位の比較

[注文件数](orders.md)指標には、購入イベント数のみが記録されます。 顧客は複数の製品を購入できるので、「単位」指標は通常「注文件数」を上回ります。 この場合、1 つの注文に複数の単位が含まれます。

購入回数が単位を超える場合は、実装の整合性を確認することをお勧めします。 購入時に `products` 変数が正しく設定されていない可能性があります。これは通常、望ましくない動作です。
