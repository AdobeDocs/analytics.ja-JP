---
title: 出口ディメンション
description: 出口ディメンションと、その使用をリストします。
keywords: 出口ページ、出口サイトセクション、出口サーバー、出口 custom insight
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 175
ht-degree: 94%

---

# 出口ディメンション

*このヘルプページでは、終了が[&#x200B; ディメンション &#x200B;](overview.md)として機能する仕組みについて説明します。 出口が指標として機能する方法について詳しくは、[出口](../metrics/exits.md)指標を参照してください。*

出口ディメンションは、最後のディメンション項目を記録し、訪問のすべてのヒットに遡って適用します。 出口ディメンションは、レポートスイート設定の「[トラフィック変数](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)」でパスが有効になっているすべての変数で使用できます。

## 出口ディメンションへのデータ入力

特定の出口ディメンションは、関連付けられたトラフィック変数に基づいています。 出口以外の変数にデータが含まれる場合は、関連する出口ディメンションにもデータが含まれます。 トラフィック変数にデータが含まれる場合、出口ディメンションに対して実装の変更は必要ありません。

## ディメンション項目

出口変数は通常、実装内のカスタム文字列に基づくので、組織でディメンション項目を決定します。 特定の出口ディメンションの項目は、関連付けられた出口以外のディメンションのディメンション項目と一致します。 例えば、「出口ページ」ディメンションのディメンション項目には、「ページ」ディメンションに類似したディメンション項目が含まれています。
