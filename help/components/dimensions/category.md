---
title: カテゴリ
description: ヒットの製品カテゴリ。
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: 'https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 93%

---

# カテゴリ

「カテゴリ」 [&#x200B; ディメンション &#x200B;](overview.md)は、ヒットの製品カテゴリを報告します。 これは、`products` 変数を使用し、トップセラーや最も多く閲覧された製品のカテゴリに関する指標を確認したい場合に便利です。 サイトに製品が存在しない場合、このディメンションは意図的に空白にする可能性があります。

## このディメンションへのデータ入力

このディメンションは、[`products`](/help/implement/vars/page-vars/products.md) 変数内の文字列の最初の部分を参照します。 最初のセミコロン（`;`）より前にあるすべての要素が、このディメンションに入力されます。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。 「製品」ディメンションと「カテゴリ」ディメンションの両方を使用して、個々の製品を意味のあるカテゴリにグループ化することをお勧めします。

>[!TIP]
>
>以前のバージョンの Adobe Analytics では、処理アーキテクチャが原因で「カテゴリ」ディメンションに一部の制限が課されていました。 これらの制限は、それ以降削除され、指標や分類を使用できるようになりました。
