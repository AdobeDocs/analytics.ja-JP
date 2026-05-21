---
title: 入口ディメンション
description: 入口ディメンションとその使用をリストします。
keywords: 入口ページ、入口サイトセクション、入口サーバー、入口カスタムインサイト
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
TQID: https://experienceleague.adobe.com/6a6Xy8SEqjcnuB1Acbwkesw6OA7Nggld5ppWtjYaj5k
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 292
ht-degree: 75%

---

# 入口ディメンション

*このヘルプページでは、エントリが[ ディメンション ](overview.md)として機能する仕組みについて説明します。 入口が指標として機能する方法について詳しくは、[入口](../metrics/entries.md)指標を参照してください。*

エントリ ディメンションは[訪問ベース ](../metrics/visits.md)です。 これらは、最初のディメンション項目を記録し、その訪問の全期間保持します。 入口ディメンションは、レポートスイート設定の「[トラフィック変数](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)」でパスが有効になっているすべての変数で使用できます。

>[!TIP]
>訪問で最初に見た値ではなく、訪問の最初のヒットに基づくデータを表示する場合は、[ セグメント ](/help/components/segmentation/seg-overview.md)を使用できます。 「[ ヒットの深さ](hit-depth.md)」が1に等しいヒットコンテナを使用し、そのセグメントを目的の変数で使用します。

## 入口ディメンションへのデータ入力

指定されたエントリ [ ディメンション ](overview.md)は、関連するトラフィック変数に基づいています。 入口変数以外の変数にデータが含まれている場合は、関連する入口ディメンションにもデータが含まれます。 トラフィック変数にデータが含まれる場合、入口ディメンションに対して実装の変更は必要ありません。

## ディメンション項目

入口変数は通常、実装内のカスタム文字列に基づくので、組織でディメンション項目を決定します。 特定の入口ディメンションの値は、関連付けられた入口以外のディメンションのディメンション項目と一致します。 例えば、「入口ページ」ディメンションのディメンション項目には、「ページ」ディメンションに類似したディメンション項目が含まれています。

## オリジナルの入口ページ

「オリジナルの入口ページ」ディメンションの動作は、他の入口ディメンションとは異なります。 特定の訪問に関する入口ページを保持する代わりに、その訪問者の cookie が保持されるまで、最初の入口ページが保持されます。 例えば、サイトへの初回訪問で `https://example.com/page4` を訪問して、1 年後に `https://example.com/store` を訪問した場合は、「オリジナルの入口ページ」はディメンション項目として `https://example.com/page4` をリストします。
