---
title: 製品
description: 製品名。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 91%

---

# 製品

「製品」 [ ディメンション ](overview.md)は、ヒット内の製品の名前を報告します。 これは、`products` 変数を使用し、トップセラーや最も多く閲覧された製品に関する指標を確認したい場合に便利です。 サイトに製品が存在しない場合、このディメンションは意図的に空白にする可能性があります。

## このディメンションへのデータ入力

このディメンションは、[`products`](/help/implement/vars/page-vars/products.md) 変数内の文字列の 2 番目の部分を参照します。 最初と 2 番目のセミコロン（`;`）の間の文字は、このディメンションに入力されます。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。 製品に対して一貫した命名規則を設定することをお勧めします。 [分類](../classifications/classifications-overview.md)は、別の方法で製品をグループ化したり、わかりやすい名前を付けたりする場合に利用できます。 「製品」ディメンションと「カテゴリ」ディメンションの両方を使用することをお勧めします。
